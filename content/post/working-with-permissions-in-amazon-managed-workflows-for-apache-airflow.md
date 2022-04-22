---
title: 'Working with permissions in Amazon Managed Workflows for Apache Airflow'
date: '2021-01-27'
tags: [Apache Airflow, mwaa, IAM Permissions, Security]
---
![innovate](https://raw.githubusercontent.com/094459/innovateaiml-airflow/main/images/banner.png)
Part of a series of posts to support an up-coming online event, the Innovate AI/ML on February 24th, from 9:00am GMT - you can sign up [here](https://aws.amazon.com/events/aws-innovate/machine-learning/online/emea/?sc_channel=em&sc_campaign=EMEA_FIELD_WEBINAR_innovate-AIML_20210224_7014z000001MJbu&sc_medium=em_&sc_content=REG_t1_field&sc_geo=emea&sc_country=mult&sc_outcome=reg&sc_publisher=aws&trkCampaign=emea21_innovatemlq1&trk=em_emea21_innovatemlq1_ricardosueiras)

* **Part 1** - [Installation and configuration of Managed Workflows for Apache Airflow](https://aws-oss.beachgeek.co.uk/3h)
* **Part 2** - Working with Permissions <- this post
* **Part 3** - [Accessing Amazon Managed Workflows for Apache Airflow environments](https://aws-oss.beachgeek.co.uk/3o)
* **Part 4** - [Interacting with Amazon Managed Workflows for Apache Airflow via the command line](https://aws-oss.beachgeek.co.uk/4s)
* **Part 5** - [A simple CI/CD system for your development workflow](https://aws-oss.beachgeek.co.uk/4t)
* **Part 6** - [Monitoring and logging](https://aws-oss.beachgeek.co.uk/5r)
* **Part 7** - Automating a simple AI/ML pipeline with Apache Airflow 

In this post I will be covering Part 2, how to ensure that you control access to Apache Airflow following best practices such as default no access/least privilege.

Specifically I will cover a couple of things:

1. How to understand the permissions that the Apache Airflow workers will operate under so you can control and reduce the permissions needed
2. How to setup IAM Groups/Permissions to manage different types of Apache Airflow access levels - in this post I will cover User and Admin

**What will you need**

* An AWS account with the right level of privileges
* An environment with the AWS CLI tools configured and running
* Access to an AWS region where Managed Workflows for Apache Airflow is supported
* An environment of Amazon Managed Workflows for Apache Airflow already setup - you should ideally have followed [part one here](https://aws-oss.beachgeek.co.uk/3h).

**Introduction and documentation**

It is worth starting out with the documentation available for the Amazon Managed Workflows for Apache Airflow as it contains some useful reference information as well as some terms that I will follow to avoid confusion.

The documentation page, [Managing access to Amazon Managed Workflows for Apache Airflow](https://aws-oss.beachgeek.co.uk/3k) is a good starting point to understand in more depth how permissions work in MWAA. The [Identity and access management for Amazon MWAA](https://aws-oss.beachgeek.co.uk/3l) documentation page is also helpful and there is also a Best Practices page within the documentation which you can find at this link, [Best practices](https://aws-oss.beachgeek.co.uk/3m) too.

The documentation refers to Service Users, Service Administrators and IAM Administrators. For the purposes of this walkthrough, you can think of the Service Users as the Airflow developers who will develop/create the DAGs, the Service Administrators as Airflow Admins who might ensure that the environments are setup and they are integrated with the required resources and then the IAM Administrators who are the folks that the Service Administrators will typically work with to identify and limit permissions to the least required.

With that out of the way, let us get started.

**Permissions for Apache Airflow Workers**

One of the key jobs you will have to do is to manage permissions policies so that they provide just the right level of access for the specific tasks that your workflows will need to do.

As part of the installation and configuration of your MWAA environment, an execution role will have been created. You can find this by issuing the following command (this assumes you have jq installed)

```
aws mwaa get-environment --name blog-post-airflow-install-MwaaEnvironment --region=eu-central-1 | jq -r '.Environment | .ExecutionRoleArn'
``` 

And you should get something like the following. This is the Execution role that your Apache Airflow workers will use as the basis for what they can or cannot do.

```
arn:aws:iam::xxxxxxxxxxxx:role/service-role/blog-post-airflow-install-MwaaExecutionRole-HYGFPT48A7TZ
```

You can now now use the following command to actually find the policies that contain the permissions. For role name, use the role name rather than the full arn (so in the above example it would be just log-post-airflow-install-MwaaExecutionRole-HYGFPT48A7TZ) 

```
aws iam list-attached-role-policies --role-name blog-post-airflow-install-MwaaExecutionRole-HYGFPT48A7TZ
```
Which will display something like the following:

```
{
    "AttachedPolicies": [
        {
            "PolicyName": "blog-post-airflow-install-MwaaExecutionPolicy-1VZE277CIW1VA",
            "PolicyArn": "arn:aws:iam::704533066374:policy/blog-post-airflow-install-MwaaExecutionPolicy-1VZE277CIW1VA"
        }
    ]
}
```
Now run the following command to get some additional information about the policy - here we are specifically looking for the version ID. Depending on how many revisions/changes you have made this might change. If I take a look at the output I get, it says the following:

```
{
    "Policy": {
        "PolicyName": "blog-post-airflow-install-MwaaExecutionPolicy-1VZE277CIW1VR",
        "PolicyId": "ANPA2ICLROKDGZSYSOYDH",
        "Arn": "arn:aws:iam::704533066374:policy/blog-post-airflow-install-MwaaExecutionPolicy-1VZE277CIW1VR",
        "Path": "/",
        "DefaultVersionId": "v5",
        "AttachmentCount": 1,
        "PermissionsBoundaryUsageCount": 0,
        "IsAttachable": true,
        "CreateDate": "2021-01-26T14:39:37Z",
        "UpdateDate": "2021-01-26T14:39:37Z"
    }
}
```

Now that I know the latest version, I can use the following command to output the actual policy itself.

```
aws iam get-policy-version --policy-arn arn:aws:iam::704533066374:policy/blog-post-airflow-install-MwaaExecutionPolicy-1VZE277CIW1VR --version-id "v5"
```

Which will give you the actual policy being used.

```
{
    "PolicyVersion": {
        "Document": {
            "Version": "2012-10-17",
            "Statement": [
                {
                    "Action": "airflow:PublishMetrics",
                    "Resource": [
                        "arn:aws:airflow:eu-central-1: xxxxxxxxxxxx:environment/blog-post-airflow-install-MwaaEnvironment"
                    ],
                    "Effect": "Allow"
                },
                {
                    "Action": "s3:ListAllMyBuckets",
                    "Resource": [
                        "arn:aws:s3:::airflow-blog-post-ricsue",
                        "arn:aws:s3:::airflow-blog-post-ricsue/*"
                    ],
                    "Effect": "Deny"
                },
                {
                    "Action": [
                        "s3:GetObject*",
                        "s3:GetBucket*",
                        "s3:List*"
                    ],
                    "Resource": [
                        "arn:aws:s3:::airflow-blog-post-ricsue",
                        "arn:aws:s3:::airflow-blog-post-ricsue/*"
                    ],
                    "Effect": "Allow"
                },
                {
                    "Action": [
                        "logs:CreateLogStream",
                        "logs:CreateLogGroup",
                        "logs:PutLogEvents",
                        "logs:GetLogEvents",
                        "logs:GetLogRecord",
                        "logs:GetLogGroupFields",
                        "logs:GetQueryResults",
                        "logs:DescribeLogGroups"
                    ],
                    "Resource": [
                        "arn:aws:logs:eu-central-1: xxxxxxxxxxxx:log-group:blog-post-airflow-install-MwaaEnvironment-*"
                    ],
                    "Effect": "Allow"
                },
                {
                    "Action": "cloudwatch:PutMetricData",
                    "Resource": "*",
                    "Effect": "Allow"
                },
                {
                    "Action": [
                        "sqs:ChangeMessageVisibility",
                        "sqs:DeleteMessage",
                        "sqs:GetQueueAttributes",
                        "sqs:GetQueueUrl",
                        "sqs:ReceiveMessage",
                        "sqs:SendMessage"
                    ],
                    "Resource": [
                        "arn:aws:sqs:us-east-1:*:airflow-celery-*"
                    ],
                    "Effect": "Allow"
                },
                {
                    "Condition": {
                        "StringLike": {
                            "kms:ViaService": [
                                "sqs.eu-central-1.amazonaws.com"
                            ]
                        }
                    },
                    "Action": [
                        "kms:Decrypt",
                        "kms:DescribeKey",
                        "kms:GenerateDataKey*",
                        "kms:Encrypt"
                    ],
                    "Effect": "Allow",
                    "NotResource": "arn:aws:kms:*:xxxxxxxxxxxx:key/*"
                }
            ]
        },
        "VersionId": "v1",
        "IsDefaultVersion": true,
        "CreateDate": "2021-01-26T14:39:37Z"
    }
}
```

**Enabling access to other services**

You can attach multiple policies to the execution role as you need to allow your workers to access additional AWS resources. For example, let us take a look at how we would enable Amazon EMR and Amazon SageMaker access.

We would create a json policy that contained the narrowest permissions we could configure. This is what one for Amazon EMR might look like:


```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "elasticmapreduce:DescribeStep",
                "elasticmapreduce:AddJobFlowSteps",
                "elasticmapreduce:RunJobFlow"
            ],
            "Resource": "arn:aws:elasticmapreduce:*:xxxxxxxxxxxx:cluster/*"
        },
        {
            "Effect": "Allow",
            "Action": "iam:PassRole",
            "Resource": [
                "arn:aws:iam::xxxxxxxxxxxx:role/EMR_EC2_DefaultRole",
                "arn:aws:iam::xxxxxxxxxxxx:role/EMR_DefaultRole"
            ]
        }
    ]
}
```
You would change out the EMR ARNs at the bottom for the ones you have configured within your own environment.

Attaching this policy to the MWAA execution role will now allow the MWAA workers to submit EMR Jobs. Following [this great blog post](https://aws-oss.beachgeek.co.uk/19) from Gary Stafford, after attaching the above policy I was able to kick off a workflow and looking at the logs we can see this was successful.

```
[2021-01-25 12:38:41,280] {{emr_create_job_flow_operator.py:66}} INFO - Creating JobFlow using aws-conn-id: s3_default, emr-conn-id: emr_default
[2021-01-25 12:38:41,526] {{emr_create_job_flow_operator.py:73}} INFO - JobFlow with id j-1JC12TT1N90S1 created
[2021-01-25 12:38:41,587] {{taskinstance.py:1070}} INFO - Marking task as SUCCESS.dag_id=bakery_sales, task_id=create_job_flow, execution_date=20210125T123836, start_date=20210125T123840, end_date=20210125T123841
[2021-01-25 12:38:41,842] {{logging_mixin.py:112}} INFO - [2021-01-25 12:38:41,842] {{local_task_job.py:102}} INFO - Task exited with return code 0
```

It is the same process if we wanted to be able to submit training jobs to Amazon SageMaker. Many AWS services document these kinds of permissions within their documentation pages, and for Amazon SageMaker you can view those [here](https://docs.aws.amazon.com/sagemaker/latest/dg/sagemaker-roles.html).

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "cloudwatch:PutMetricData",
                "logs:CreateLogStream",
                "logs:PutLogEvents",
                "logs:CreateLogGroup",
                "logs:DescribeLogStreams",
                "ecr:GetAuthorizationToken"
            ],
            "Resource": "*"
        },
        {
            "Effect": "Allow",
            "Action": [
                "s3:ListBucket"
            ],
            "Resource": [
                "arn:aws:s3:::{sagemaker-inputbucket}"
            ]
        },
        {
            "Effect": "Allow",
            "Action": [
                "s3:GetObject",
                "s3:PutObject"
            ],
            "Resource": [
                "arn:aws:s3:::{sagemaker-inputbucket/object}",
                "arn:aws:s3:::{sagemaker-outputbucket/path}"
            ]
        },
        {
            "Effect": "Allow",
            "Action": [
                "ecr:BatchCheckLayerAvailability",
                "ecr:GetDownloadUrlForLayer",
                "ecr:BatchGetImage"
            ],
            "Resource": "arn:aws:ecr:::*"
        }
    ]
}

```

Attaching this policy would allow the DAG to submit the job for training, but would fail if it tried to submit a hyper-parameter training job.

So, how do you attach policies via the command line? You first create a file with the above policies (for example, airflow-emr-access.json) and then use a command like the following:

```
aws iam create-policy --policy-name emr-airflow-permission-policy --policy-docume
nt file://airflow-emr-access.json
```

This would create a new policy called emr-airflow-permission-policy, and the command should output something like:

```
{
    "Policy": {
        "PolicyName": "emr-airflow-permission-policy",
        "PolicyId": "ANPA2ICLROKDKX74UZOME",
        "Arn": "arn:aws:iam:: xxxxxxxxxxxx:policy/emr-airflow-permission-policy",
        "Path": "/",
        "DefaultVersionId": "v1",
        "AttachmentCount": 0,
        "PermissionsBoundaryUsageCount": 0,
        "IsAttachable": true,
        "CreateDate": "2021-01-27T16:57:16Z",
        "UpdateDate": "2021-01-27T16:57:16Z"
    }
}
```

This has created the policy, but it is not yet attached to the MWAA Execution role - which means it is not yet being used. We can now attach it to the execution policy of MWAA using the following command.

```
aws iam attach-role-policy --role-name AmazonMWAA-apache-airflow-aimlinnovate-BT6dVb --policy-arn arn:aws:iam::xxxxxxxxxxxx:policy/emr-airflow-permission-policy
```
You will not see any output when you run this command, but you can check it has been added by using the following command:

```
aws iam list-attached-role-policies --role-name blog-post-airflow-install-MwaaExecutionRole-HYGFPT48A7TZ
```
Which should output something like:

```
{
    "AttachedPolicies": [
        {
            "PolicyName": "blog-post-airflow-install-MwaaExecutionPolicy-1VZE277CIW1VR",
            "PolicyArn": "arn:aws:iam:: xxxxxxxxxxxx:policy/service-role/MWAA-Execution-Policy-1f882fe6-c6da-424f-a7aa-5365ad28b307"
        },
        {
            "PolicyName": "emr-airflow-permission-policy",
            "PolicyArn": "arn:aws:iam::xxxxxxxxxxxx:policy/emr-airflow-permission-policy"
        }
    ]
}
```


**Troubleshooting Permissions**

In pretty much all the DAGs I have been putting together I have had permissions related errors. For example, something in the Apache UI task log might appear such as:

```
[2021-01-27 15:20:06,445] {taskinstance.py:1145} ERROR - An error occurred (AccessDeniedException) when calling the CreateTrainingJob operation: User: arn:aws:sts::xxxxxxxxxx:assumed-role/AirflowInstanceRole/i-09c07034f4fdb5edf is not authorized to perform: sagemaker:CreateTrainingJob on resource: arn:aws:sagemaker:eu-west-1: xxxxxxxxxx:training-job/trng-recommender-2021-01-27-15-20-05-672
Traceback (most recent call last):
```

By looking at the logs, either in the Apache Airflow UI or in the Amazon CloudWatch log groups (making sure you have enabled/set to INFO) you will see any potential messages that allude to lack of permissions. The most common errors I have seen are Access Denied, but I am good with those - it means that I am locking things down nice and tight, and after all,  we do want to limit the permissions we give. It becomes a game of tracking down what the DAG is trying to do and match that to the required permissions.

With the above error, I tracked it down to an Execution policy within Amazon SageMaker that didn't have everything it needed as per the documentation.


**Setting up permissions to the Apache Airflow UI**

You ideally want to setup different permissions for just Developers and Administrators within Apache Airflow. You can do this easily by creating groups within IAM, attaching an IAM policy that governs the permissions and then adding IAM users to that group.

In the following snippet of CloudFormation template, we can see we are creating a couple of groups and adding some in-line policies that control the authorisation. Once this template is run, all you are left to do is assign the IAM users to the groups.

```
MwaaDeveloperAccess:
    Type: AWS::IAM::Group
    Properties:
      GroupName: MWAA-Developer-Access
      Policies:
      - PolicyName: MWAA-Developer-Access-Policy-cfn
        PolicyDocument:
          Version: 2012-10-17
          Statement:
          - Effect: Allow
            Action:
            - airflow:CreateWebLoginToken
            Resource:
            - !Sub "arn:aws:airflow:${AWS::Region}:${AWS::AccountId}:role/*/User"

  MwaaAdminAccess:
    Type: AWS::IAM::Group
    Properties:
      GroupName: MWAA-Administrator-Access
      Policies:
      - PolicyName: MWAA-Administrator-Access-Policy-cfn
        PolicyDocument:
          Version: 2012-10-17
          Statement:
          - Effect: Allow
            Action:
            - airflow:CreateWebLoginToken
            Resource:
            - !Sub "arn:aws:airflow:${AWS::Region}:${AWS::AccountId}:role/*/Admin"

```

You can see an example full CloudFormation template that includes the permissions [here](https://aws-oss.beachgeek.co.uk/3i).

If you followed the previous post, all you have to do is adjust the CloudFormation template to incorporate these and then use the UPDATE stack and use this new version. This will install just these new resources.

Assuming that your IAM users do not have Administrator access, then:

* When your IAM users try and login via the Apache Airflow UI they will fail
* When you add a user to the Developer group, and then try and access the Apache Airflow UI they will access the UI with User level access
* When you add a user to the Administrator group and try accessing the Apache Airflow UI, they will now have the full Administrator access

You could further tighten the permissions in the template by locking down access by environment. To do this, you would adjust the following entry:

```
- !Sub "arn:aws:airflow:${AWS::Region}:${AWS::AccountId}:role/*/User"
```

to something like (assuming you were using the same CloudFormation template as in the examples I have provided. Otherwise you would change your [${AWS::StackName}-MwaaEnvironment] based on your own references.

```
- !Sub "arn:aws:airflow:${AWS::Region}:${AWS::AccountId}:role/${AWS::StackName}-MwaaEnvironment/User"
```
This might make more sense to lock down for developers rather than Admins on the assumption that one Administrator may manage/provision many environments for the developers.

**Accessing other MWAA resources**

You can create permissions policies that allow you to define access to view in a read only capacity or to be able to create new environments. You might uses these permissions to define roles that are used for operational activities such as spinning up or removing environments, reporting etc. 

Rather than repeat those, the MWAA documentation has this very well presented [here](https://aws-oss.beachgeek.co.uk/3k). You can use the same approach as above to automate these into your CloudFormation templates. 


**Conclusion**

This concludes the second post. Make sure you check the official MWAA documentation that covers security and permissions in a lot of detail.

In the next post we will look at accessing the Apache Airflow UI and how we can access it via the command line.


If there is specific content you want to see, please get in touch.
