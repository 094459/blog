---
title: 'Setting up MWAA to use a KMS key'
date: '2021-12-14'
tags: [ Apache Airflow, mwaa, kms, encryption ]
---
### Introduction

In a [previous post](https://dev.to/aws/using-aws-cdk-to-deploy-your-amazon-managed-workflows-for-apache-airflow-environment-12cf), I shared how you can using AWS CDK to provision your Apache Airflow environments using the Managed Workflows for Apache Airflow service (MWAA). 

I was contacted this week by Michael Grabenstein, who flagged an issue with the code in that post. The post used code that configured a kms key for the MWAA environment, but when trying to deploy the app it would fail with the following error:

```
14:59:15 | CREATE_FAILED        | AWS::MWAA::Environment         | airflowtestenvironment
Resource handler returned message: "Creation failed" (RequestToken: 5b5b5a02-8cee-e48a-66ea-a07a8b1ad41a, HandlerErrorCode: NotStabilized)
```

This issue was that the CDK stack did not have everything needed to properly configure a customer KMS key, so I wanted to address that in this post, how to configure MWAA so that you can use your own KMS key to properly ensure that everything is encrypted.

I want to thank Michael for flagging the issue and his PR to the project and help getting this tested.

### Configuring KMS for MWAA

In order to get KMS configured, we need to do a number of things:

* amend the existing MWAA execution policy
* create new IAM policies to configure access to our KMS keys
* create our KMS key 
* configure MWAA to use that KMS key

Once we have done that, we can then deploy our stack and create our MWAA environment. Lets get started.

**Amending the existing MWAA execution policy**

In the original CDK stack, we created IAM policies for the MWAA execution role which covered what was defined in the [MWAA docs](https://docs.aws.amazon.com/mwaa/latest/userguide/custom-keys-certs.html). In the stack, this was as follows:

```
{
            "Effect": "Allow",
            "Action": [
                "kms:Decrypt",
                "kms:DescribeKey",
                "kms:GenerateDataKey*",
                "kms:Encrypt"
            ],
            "Resource": "arn:aws:kms:{your-region}:{your-account-id}:key/{your-kms-cmk-id}",
            "Condition": {
                "StringLike": {
                    "kms:ViaService": [
                        "sqs.{your-region}.amazonaws.com",
                        "s3.{your-region}.amazonaws.com"
                    ]
                }
            }
```

We needed to adjust this and add another permission, "kms:PutKeyPolicy" so we end up with

```
								iam.PolicyStatement(
                    actions=[
                        "kms:Decrypt",
                        "kms:DescribeKey",
                        "kms:GenerateDataKey*",
                        "kms:Encrypt",
                        "kms:PutKeyPolicy"
                    ],
                    effect=iam.Effect.ALLOW,
                    resources=["*"],
                    conditions={
                        "StringEquals": {
                            "kms:ViaService": [
                                f"sqs.{self.region}.amazonaws.com",
                                f"s3.{self.region}.amazonaws.com",
                            ]
                        }
                    },
                ),
```


During testing we found that we also needed to amend the existing MWAA logging policy as follows, adding the "logs:DescribeLogGroups":

```
                iam.PolicyStatement(
                    actions=[
                        "logs:CreateLogStream",
                        "logs:CreateLogGroup",
                        "logs:PutLogEvents",
                        "logs:GetLogEvents",
                        "logs:GetLogRecord",
                        "logs:GetLogGroupFields",
                        "logs:GetQueryResults",
                        "logs:DescribeLogGroups"
                    ],
                    effect=iam.Effect.ALLOW,
                    resources=[f"arn:aws:logs:{self.region}:{self.account}:log-group:airflow-{mwaa_props['mwaa_env']}-*"],
                ),
```

These were the two changes we made to the MWAA execution policy.

**Creating new IAM policies to configure access to our KMS keys**

Now that the existing MWAA execution policy is good to go, we needed to create a new policy that will be used and assigned to our KMS key. This policy will provide the right permissions for MWAA and the workers to be able to access the keys to decrypt/encrypt messages and logs.

Within the MWAA CDK stack, we create a new policy as follows (and thanks to Michael for his help with this):

```
  kms_mwaa_policy_document = iam.PolicyDocument(
            statements=[
                iam.PolicyStatement(
                    actions=[
                        "kms:Create*",
                        "kms:Describe*",
                        "kms:Enable*",
                        "kms:List*",
                        "kms:Put*",
                        "kms:Decrypt*",
                        "kms:Update*",
                        "kms:Revoke*",
                        "kms:Disable*",
                        "kms:Get*",
                        "kms:Delete*",
                        "kms:ScheduleKeyDeletion",
                        "kms:GenerateDataKey*",
                        "kms:CancelKeyDeletion"
                    ],
                    principals=[
                        iam.AccountRootPrincipal(),
                        # Optional:
                        # iam.ArnPrincipal(f"arn:aws:sts::{self.account}:assumed-role/AWSReservedSSO_rest_of_SSO_account"),
                    ],
                    resources=["*"]),
                iam.PolicyStatement(
                    actions=[
                        "kms:Decrypt*",
                        "kms:Describe*",
                        "kms:GenerateDataKey*",
                        "kms:Encrypt*",
                        "kms:ReEncrypt*",
                        "kms:PutKeyPolicy"
                    ],
                    effect=iam.Effect.ALLOW,
                    resources=["*"],
                    principals=[iam.ServicePrincipal("logs.amazonaws.com", region=f"{self.region}")],
                    conditions={"ArnLike": {"kms:EncryptionContext:aws:logs:arn": f"arn:aws:logs:{self.region}:{self.account}:*"}},
                ),
            ]
        )
```

We will use this policy in the next step, when we create the key.

> Note! When I originally put this together, I did not have the "principals=[iam.AccountRootPrincipal(),..." statement, and it did work for me. However, Michael saw the following error:
> ```
> Resource handler returned message: "The new key policy will not allow you to update the key policy in the future. (Service: Kms, Status Code: 400
> ```
> Which was resolved by adding that additional statement

**Creating our KMS key**

Now that we have our policy, we can create the key. The previous code is modified slightly to incorporate this new policy. (policy=kms_mwaa_policy_document)

```

        key = kms.Key(
            self,
            f"{mwaa_props['mwaa_env']}Key",
            enable_key_rotation=True,
            policy=kms_mwaa_policy_document
        )
        
        key.add_alias(f"alias/{mwaa_props['mwaa_env']}")   
```

When the key is created, it will incorporate the policy we created which you can see from the KMS console.

**Configuring MWAA to use that KMS key**

Now that we have that done, we can now configure MWAA to use this. In the original CDK code, I incorrectly used key_id instead of key_arn. The correct CDK code is as follows:

```
        managed_airflow = mwaa.CfnEnvironment(
            scope=self,
            id='airflow-test-environment',
            name=f"{mwaa_props['mwaa_env']}",
            airflow_configuration_options={'core.default_timezone': 'utc'},
            #airflow_version='1.10.12',
            airflow_version='2.0.2',
            dag_s3_path="dags",
            environment_class='mw1.small',
            execution_role_arn=mwaa_service_role.role_arn,
            kms_key=key.key_arn,
            logging_configuration=logging_configuration,
            max_workers=5,
            network_configuration=network_configuration,
            #plugins_s3_object_version=None,
            #plugins_s3_path=None,
            #requirements_s3_object_version=None,
            #requirements_s3_path=None,
            source_bucket_arn=dags_bucket_arn,
            webserver_access_mode='PUBLIC_ONLY',
            #weekly_maintenance_window_start=None
        )
```

You can view the complete code in the GitHub repo, [blogpost-cdk-mwaa](https://github.com/094459/blogpost-cdk-mwaa) and the [changeset here](https://github.com/094459/blogpost-cdk-mwaa/commit/dc8e25c552cadd90c398b84d81e457a7050588a9)

### Deploying MWAA

You can now deploy and create your MWAA environment in the same way, using the following CDK command, and responding Y when prompted.

```
cdk deploy MWAA-Backend
cdk deploy MWAA-Environment
```

> I have upgraded to v2. of CDK, so this was tested on 2.0.0 (build 4b6ce31)
> 

Once deployed (it will take 25-30 minutes typically) you should now be able to access your MWAA environment as per usual. The only difference is that now all the interactions between MWAA and the worker nodes, the messages in the scheduler, the log files written to CloudWatch are all encrypted using that key.

**Other observations and possible improvements**

One thing to be aware of when enabling KMS is that you can run into issues with the Task logs not appearing in the CloudWatch logs log group. 

> What we observed was that whilst everything looked ok, and we could access the Apache Airflow UI and trigger DAGs, when it came to looking at the logs, we received errors like:
> 
> ```
> *** Reading remote log from Cloudwatch log_group: airflow-seam-mwaa-cdk-demo-Task log_stream: hello_world_ondemand/hello_task/2021-12-14T15_30_49.698602+00_00/1.log.
> Could not read remote logs from log_group: airflow-seam-mwaa-cdk-demo-Task log_stream: hello_world_ondemand/hello_task/2021-12-14T15_30_49.698602+00_00/1.log.
> ```

During testing, we saw this a few times, and using CloudWatch Trail (see below) we were able to see that this was down to the wrong KMS key being used to encrypt the logs. This can happen if you have destroyed/deployed your MWAA multiple times. Every time you do that cycle, the KMS key gets deleted/recreated. Unless you delete the CloudWatch log groups, they appear to maintain the originally configured KMS key.

The resolution was to do a clean deploy. To do this, we first deleted the MWAA environment (cdk destroy..) and then deleted the log groups within CloudWatch. Once cleared, we redeployed the MWAA environment and the issue was resolved.

Whilst troubleshooting this, CloudWatch Trail is helpful in narrowing down the source of the problem. For example, looking through the events, we could observe that there were some AccessDenied errors, 

```
...
    "eventTime": "2021-12-14T10:36:43Z",
    "eventSource": "kms.amazonaws.com",
    "eventName": "Decrypt",
    "awsRegion": "eu-central-1",
    "sourceIPAddress": "airflow.amazonaws.com",
    "userAgent": "airflow.amazonaws.com",
    "errorCode": "AccessDenied",
    "errorMessage": "User: arn:aws:sts::704533066xxx:assumed-role/MWAA-Environment-V2-mwaaservicerole26CF19B9-1VOIDCIZRBxxx/AmazonMWAA-airflow is not authorized to perform: kms:Decrypt on resource: arn:aws:kms:eu-central-1:704533066374:key/cf448xxx-7b60-4db6-9b52-b8b00047xxx because no resource-based policy allows the kms:Decrypt action",
    "requestParameters": null,
...
```

One final note, I could improve this setup by encrypting the S3 bucket that is configured for MWAA using the same kms key. When I have some time, I will come back and revisit that.

