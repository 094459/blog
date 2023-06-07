---
title: 'Integrating Keycloak as my Identity Provider for IAM Identity Centre: Part one, deploying Keycloak on AWS'
date: '2023-06-06'
tags : [ aws open source, Keycloak, CDK, Cloudformation, SAML2.0, AWS Identity Centre, AWS SSO]
---

### Integrating Keycloak as my Identity Provider for IAM Identity Centre: Part one, deploying Keycloak on AWS

"It was the best of times, it was the worst of times..." A Tale of Two Cities

It started out innocently enough. As part of working on a new blog post, I needed a way to use an open source tool called [saml2aws](https://aws-oss.beachgeek.co.uk/2uv) that generates AWS short lived credentials that you can use to access your AWS resources. This is a pretty common pattern, and a good practice to do and for many organisations this means they integrate with their "user directory" - sometimes this might be something like Active Directory, or an LDAP server. AWS IAM Identity Centre (which is the new name for AWS Single Sign-On) allows you to integrate those identity providers into your AWS Account, allowing your users to authenticate against that user directory and then get access to AWS resources. 

So I needed to set up an Identity Provider (IdP), and decided to use an open source Identity and Access Management solution called Keycloak rather than the usual suspects of Active Directory or something like Auth0. What I thought would be a simple deployment ended up being less than straightforward. This post outlines how you can get your own Keycloak IAM service up and running on AWS.

Why was it less than straightforward? As it turns out, that was down to some significant changes introduced in later versions of Keycloak that impacted how many tools created to simplify the deployment of Keycloak, worked. Or as I found, did not!


In this post I will share how you can get both the older versions of Keycloak (v16.1) as well as the latest versions (I am running v21.0.1)  up and running on AWS. In a future post, I will use the Keycloak service that this post helps you deploy, and integrate this into AWS Identity Centre as our SSO.

**Pre-reqs**

* An AWS account to which you have the right level of access to configure a new Identity Provider
* An available VPC in the region you will be deploying Keycloak
* The AWS cli (I am using version aws-cli/2.7.7 Python/3.9.11 Darwin/21.6.0 exe/x86_64 prompt/off) as well as AWS CDKv2 (I am running 2.82.0 (build 3a8648a))
* A domain that you have that allows you to create public certificates (I have a domain called ricsue.dev that is managed by Route53)
* Code resources used within the post,  located at [keycloak-aws](https://aws-oss.beachgeek.co.uk/2v1)

I checked how much it cost to run this on my AWS bill for 24 hours, and it was less than £10.

**Grabbing a public certificate**

A requirement of deploying Keycloak is to have a public certificate available. You need to use Amazon Certificate Manager (ACM) to create a certificate. You will use the Arn for this certificate in the provisioning tool.

> **Note!** A pre-req here is that I had a domain name managed by Route53. This allowed me to easily register the certificates.

These are the steps I followed:

1. Within the ACM, I created a new public certificate (keycloak.ricsue.dev) for a domain that I have setup previously to be managed by Route53 (ricsue.dev, whilst I registered this via my preferred domain registrar, I configured it to be managed by Route53)
2. When creating the certificate within ACM, the request contains a link that allows you to automatically create the Route53 verification entries, so I used this to update the domain records. This reduced the time to validate the certificate
3. After about 5 minutes, ACM issued me my new certificate, and I was able to extract the Certificate Arn running the following command

```
aws acm list-certificates

{
    "CertificateSummaryList": [
        {
            "CertificateArn": "arn:aws:acm:eu-west-1:xxxxxxx:certificate/aec6b1ac-df36-449b-a2e2-xxxxxx",
            "DomainName": "keycloak.ricsue.dev"
        }
    ]
}
```

So with our certificate created, we are now ready to go.

## Part One: Installing Keycloak

There are a number of ways you can deploy Keycloak into your AWS account. I did not want to do this manually, so I wanted to see what options I had when it came to automating the deployment. I found a few options that were open to me based on which ever infrastructure as code tooling I preferred.

* Using CDK via the [cdk-keycloak](https://aws-oss.beachgeek.co.uk/2uw) construct
* Using CDK via the [ecs-keycloak](https://aws-oss.beachgeek.co.uk/2ux) construct
* Using Terraform via a number of different third party modules such as [terraform-keycloak-aws](https://aws-oss.beachgeek.co.uk/2uy) or [ecs-keycloak](https://aws-oss.beachgeek.co.uk/2uz)
* Using CloudFormation via this deployment guide, [keycloak-on-aws](https://aws-oss.beachgeek.co.uk/2v0)

Exploring and trying these different options out made me realised something important, and something that I think will save you a lot of time and frustration. Many of the resources above help you deploy older versions of Keycloak, and do not work for the latest versions. So in this part of the blog, I have split it out into two parts: how you can install the older (v16) versions of Keycloak, and how you can install the later versions (v17 on newer).

>**Which Version?** Now you might be wondering which version should I be using. I think for most cases, you will probably want to use the latest versions. However, there may be some use cases where you need to get an older version up and running so am including that in this post. (to be completely honest, I did the work to review the different ways, and rather than throw that all away to >dev/null, I thought I would keep it as a timely reminder for why maintaining these tools and documentation is so important!

**Keycloak version v16 or older**

As you can see from the list above, I had a few options to get my Keycloa v16.1 server up and running. After going through the documentation of each, and looking at how much work/effort was required for each, and finally trying a few out, I ended up settling for the CloudFormation solution. You will find the template I used in the [GitHub repo](https://aws-oss.beachgeek.co.uk/2vs) in the cf folder. The file is called "keycloak-aurora-serverless-from-new-vpc.template" which is the template I used, and is slightly modified from the origin repo of the resources I shared above. You can see what it will deploy by [checking out the documentation here](https://aws-oss.beachgeek.co.uk/2v0)

![overview of keycloak architecture using cloudformation](https://aws-samples.github.io/keycloak-on-aws/en/images/architecture/01-keycloak-on-aws-architecture.png)

To deploy the CloudFormation stack, I needed to pass into the CloudFormation template the CertificateArn. We are providing a stack-name (keycloak-sso-provider) which you can change if you want, and we then provide the certificate Arn via the parameter-overrides.

```
aws cloudformation deploy --template-file keycloak-aurora-serverless-from-new-vpc.template --stack-name keycloak-sso-provider --parameter-overrides CertificateArn="arn:aws:acm:eu-west-1:xxxxxx:certificate/aec6b1ac-df36-449b-a2e2-xxxxxxx" --capabilities CAPABILITY_IAM --tags keycloak=demo
```

This will kick of the creation of your Keycloak environment, configuring and then deploying all the AWS services needed (you can track these in the CloudFormation console). 

```
aws cloudformation deploy --template-file keycloak-aurora-serverless-from-new-vpc.template --stack-name keycloak-sso-provider --parameter-overrides CertificateArn="arn:aws:acm:eu-west-1:xxxxxx:certificate/aec6b1ac-df36-449b-a2e2-xxxxxx" --capabilities CAPABILITY_IAM --tags keycloak=demo

Waiting for changeset to be created..
Waiting for stack create/update to complete

```
It was simple and quick, and within 10-15 minutes I had my Keycloak environment up and running. 

```
Successfully created/updated stack - keycloak-sso-provider
```

Before we access our Keycloak service however, there are a couple of things we need to do.

1. The initial login credential for Keycloak (the Admin user) is stored in AWS Secrets Manager. To grab the password, we can use the following command to grab the Arn of the AWS Secret which contains that password, and then use another command to display that password.

```
aws cloudformation describe-stack-resource  --stack-name keycloak-sso-provider --logical-resource-id KeyCloakKCSecretF8498E5C --query StackResourceDetail.PhysicalResourceId

"arn:aws:secretsmanager:eu-west-1:xxxxxxx:secret:KeyCloakKCSecretF8498E5C-1ZI9SjZjDsmJ-xxxxx"
```
Will display the arn, which we can then use in the following command to grab the password (in the below I have redacted it as XXXXX)

```aws secretsmanager get-secret-value  --secret-id arn:aws:secretsmanager:eu-west-1:xxxxxxx:secret:KeyCloakKCSecretF8498E5C-1ZI9SjZjDsmJ-xxxxxx

{
    "ARN": "arn:aws:secretsmanager:eu-west-1:xxxxxxxxx:secret:KeyCloakKCSecretF8498E5C-1ZI9SjZjDsmJ-xxxxx",
    "Name": "KeyCloakKCSecretF8498E5C-1ZI9SjZjDsmJ",
    "VersionId": "33c86cd0-f3ec-81ed-0d34-afdea36b69f2",
    "SecretString": "{\"password\":\"XXXXXXXXX\",\"username\":\"keycloak\"}",
    "VersionStages": [
        "AWSCURRENT"
    ],
    "CreatedDate": "2023-06-01T14:15:34.876000+01:00"
}

```

We now have our username (keycloak) and our password, we now need to login to Keycloak.

2. The actual URL you need to use will to login to Keycloak is provided as an OUTPUT when CloudFormation completes. We can access these values using the following command:

```
aws cloudformation describe-stacks --stack-name keycloak-sso-provider --query "Stacks[*].Outputs[0].{OutputKey: OutputKey, OutputValue: OutputValue}"

[
    {
        "OutputKey": "KeyCloakKeyCloakContainerSerivceEndpointURL9C81E19A",
        "OutputValue": "https://keycl-KeyCl-STKX4W34C61Y-756053114.eu-west-1.elb.amazonaws.com"
    }
]

```
The value of OutputValue is the URL of an AWS Load Balancer that routes traffic to the Keycloak services running on Amazon ECS. If we use this URL in a browser we  will generate errors as the URL does not match the name of the ACM generated certificate (which in this example was keycloak.ricsue.dev). To fix the issue around mismatch of the certificate and the load balancer URL, you need to create a CNAME record in your DNS to point to the Load Balancer URL. This is what mine looks like in Route53.

![screenshot of Route53 CNAME record](https://ricsuepublicresources.s3.eu-west-1.amazonaws.com/images/blog/keycloak-dns.png)

I can now use the address of https://keycloak.ricsue.dev to access my newly deployed Keycloak service, logging in as the admin user (keycloak) using the password I obtained via AWS Secrets Manager.

![screenshot of keycloak home page](https://ricsuepublicresources.s3.eu-west-1.amazonaws.com/images/blog/keycloak-admin.png)

The final part of my setup, which is optional, is to create a user that I will use to log in. From the Admin screen, it is easy to create a new user, set a password under Credentials, and then assign it to the admin role under Role Mapping. I then logout of the Keycloak console and log back in with these new credentials, to check it works and that I still have admin access.

Congrats, you now have a Keycloak v16.1 server up and running. If this is what you needed, then great you are done. Before leaving though, check out the next section to see how to clean up/remove resources created if you need to delete Keycloak from your AWS account.

*Cleaning up and removing all resources*

If you need to delete/clean up your Keycloak v16 installation, then you can do this using the following command

```
aws cloudformation delete-stack  --stack-name keycloak-sso-provider
```
The command will not generate any output, and you will need to go to the AWS CloudFormation console to check progress of your resources being cleaned up. When I ran this, it took around 10-15 minutes to complete.

> **Note!** When I used the original templates, some resources (the Aurora MySQL database) had deletion protection enabled. So if you do get an error when trying to clean up/delete the stack, make sure you check and remove the deletion protection and then try again.

**Keycloak version v21**

So I kind of left the details of how to deploy older versions of Keycloak for reference in case anyone finds themselves needing to do that. For most installations however,  you will most likely want to deploy newer (newest) versions of Keycloak. This is where I ran into a spot of bother, and spent three days trying to figure out how to do this. The approaches outlined above just didn't work, and I spent a lot of time trying to troubleshoot and find a solution. In the end, it was down to a bit of luck and the excellence of [Alexander Widera](https://aws-oss.beachgeek.co.uk/2vr) that I got something working.

In the end what worked was using the [CDKv2 construct](https://aws-oss.beachgeek.co.uk/2uw) with a bit of tweaking which I will go through now. Again, all the code is in the[ GitHub repo](https://aws-oss.beachgeek.co.uk/2v1). We still need the ACM certificate, so that has not changed. However, what we need to do to get this working is create a customer Keycloak container image that provides some additional configuration values that are critical to getting Keycloak to work, and provide some additional Java library files that Keycloak needs which are also missing.

*Building our custom Keycloak container image*

To help you build your container image, there is a script in the docker directory called **[build.sh](https://github.com/094459/keycloak-aws/blob/main/docker/build.sh)**. Review this script and **UPDATE** it, replacing {yourawsregion} and {replacewithyourawsaccount} to reflect your AWS account details. You can optionally change the name of the Elastic Container Registery that will be created and version number.

```
#!/usr/bin/env bash

AWS_DEFAULT_REGION={yourawsregion}
AWS_ACCOUNT={replacewithyourawsaccount}
AWS_ECR_REPO=keycloak
COMMIT_HASH="21.1.1"
...
```

Once updated, and BEFORE you run this script, you need to download and copy into the "providers" folder a bunch of jar files. There is a [README](https://github.com/094459/keycloak-aws/blob/main/docker/providers/README.required.md) file in the providers folder has helpful links.

Once you have downloaded the jar files into the providers folder, it should look something like this

```
├── LICENSE
├── README.md
├── app.py
├── cdk.json
├── docker
│   ├── Dockerfile
│   ├── build.sh
│   └── providers
│       ├── README.required.md
│       ├── aws-java-sdk-core-1.12.410.jar
│       ├── aws-java-sdk-s3-1.12.410.jar
│       ├── jgroups-aws-2.0.1.Final.jar
│       └── joda-time-2.12.2.jar
├── requirements.txt
```
Finally, you should review the Docker file and make sure it fits your needs (for example, the version of Keycloak you want to use - in the example in the rep, I am using v21.1.1 but you can get [newer versions by tracking the images](https://aws-oss.beachgeek.co.uk/2vt) on the Keycloak documentation)

```
FROM quay.io/keycloak/keycloak:21.1.1 as builder

# Enable health and metrics support
ENV KC_HEALTH_ENABLED=true
ENV KC_METRICS_ENABLED=true

# Configure a database vendor
ENV KC_DB=mysql

WORKDIR /opt/keycloak

COPY /providers /opt/keycloak/providers/
RUN /opt/keycloak/bin/kc.sh build

FROM quay.io/keycloak/keycloak:21.1.1
COPY --from=builder /opt/keycloak/ /opt/keycloak/
COPY --from=builder /opt/keycloak/providers/ /opt/keycloak/providers/

ENTRYPOINT ["/opt/keycloak/bin/kc.sh"]
```

You are now ready to run the build script. Running the script will build, tag and then push a container image to your Amazon ECR repo. This  might take a while depending on the speed of your internet.

```
Login Succeeded

An error occurred (RepositoryNotFoundException) when calling the DescribeRepositories operation: The repository with name 'keycloak' does not exist in the registry with id 'xxxxxx'
Creating repos as it does not exists

[+] Building 7.6s (6/7)                                                                                                                                             
 => [internal] load build definition from Dockerfile                                                                                                           0.1s
 => => transferring dockerfile: 424B                                                                                                                           0.0s
 => [internal] load .dockerignore                                                                                                                              0.0s
 => => transferring context: 2B                                                                                                                                0.0s
 => [internal] load metadata for quay.io/keycloak/keycloak:21.1.1                                                                                              2.9s
 => [builder 1/3] FROM quay.io/keycloak/keycloak:21.1.1@sha256:8ebb3930c41e8a066c4246eaf351ac09cdc984e11b1f607d6ff4ce10d69dc808                                0.1s
 => [builder 2/3] WORKDIR /opt/keycloak                                                                                                                        0.1s
..
..
The push refers to repository [xxxxxx.dkr.ecr.eu-west-1.amazonaws.com/keycloak]
2c490c92cb93: Pushed 
f23a3cabd8b8: Pushed 
83254a336a6f: Pushed 
2cd74f3c77b5: Pushed 
a4d3d498fdcc: Pushed 
21.1.1-amd64: digest: sha256:cbbe23c22adb37c12442d0fff2c1c94e165a0589bddf179f04fa75fb85a209ac size: 1373
Created manifest list xxxxxx.dkr.ecr.eu-west-1.amazonaws.com/keycloak:21.1.1
{
   "schemaVersion": 2,
   "mediaType": "application/vnd.docker.distribution.manifest.list.v2+json",
   "manifests": [
      {
         "mediaType": "application/vnd.docker.distribution.manifest.v2+json",
         "size": 1373,
         "digest": "sha256:cbbe23c22adb37c12442d0fff2c1c94e165a0589bddf179f04fa75fb85a209ac",
         "platform": {
            "architecture": "amd64",
            "os": "linux"
         }
      }
   ]
}
sha256:a08cb293aeb968c9f0b83bc13a28677c619b3c0ae857be50bd9ff5a6ebc13370

```

(Your output will be different, but you should get similar-ish text)

Once this has completed, make sure you grab the URI for the image you just uploaded. You can use this command, which will output the images based on the default ECR name of keycloak

```
aws ecr describe-images --repository-name keycloak  --query 'imageDetails[*].imageTags[0]' --output json | jq --arg v `aws ecr describe-repositories --repository-name keycloak  --query 'repositories[0].repositoryUri' --output text` '.[] | ($v + ":" + .)'

"704533066374.dkr.ecr.eu-west-1.amazonaws.com/keycloak:21.1.1-amd64"
"704533066374.dkr.ecr.eu-west-1.amazonaws.com/keycloak:21.1.1"
```

*Updating and running our CDK app*

Before we can use our CDK app to deploy Keycloak, we need to install the custom construct. The repo has an updated [requirements.txt](https://github.com/094459/keycloak-aws/blob/main/requirements.txt), so you can use that otherwise you just need to:

```
pip install cdk-keycloak==2.7.1
```

You will now need to review and update the **[app.py](https://github.com/094459/keycloak-aws/blob/main/app.py)** in the root folder.

```
#!/usr/bin/env python3
import os

import aws_cdk as cdk
import aws_cdk.aws_rds as rds 
import aws_cdk.aws_ecs as ecs
from cdk_keycloak import KeyCloak, KeycloakVersion

app = cdk.App()
env = cdk.Environment(region="{replacewithyourawsregion}", account="{replacewithyourawsaccount}")

stack = cdk.Stack(app, "keycloak-demo", env=env)

mysso = KeyCloak(stack, "KeyCloak",
    certificate_arn="{replacewithyourcertificatearn}",
    keycloak_version=KeycloakVersion.V21_0_1,
    cluster_engine = rds.DatabaseClusterEngine.aurora_mysql(version=rds.AuroraMysqlEngineVersion.VER_2_11_2),
    hostname = "{replacewithyourcustomdns}",
    env = { "KEYCLOAK_FRONTEND_URL" : "{replacewithyourcustomdns}"},
    container_image = ecs.ContainerImage.from_registry("{replacewithyourecrcontainerimage}"),
    database_removal_policy=cdk.RemovalPolicy.DESTROY
)

app.synth()
```

You will need to update a few lines:

* update {replacewithyourawsregion} and {replacewithyourawsaccount} to reflect your AWS Account
* update {replacewithyourcertificatearn} with the Certificate Arn you created at the beginning
* update {replacewithyourcustomdns} with the domain name you used for your certificate (for example, my-keycloak.demo.com)
* update {replacewithyourecrcontainerimage} with the URI for your custom Keycloak container image you creatd in step 4

Once you have updated, save the file.

You can now deploy the stack using the following command: 

```
cdk deploy keycloak-demo
```

You will be asked to confirm security details. Review and if happy, proceed to deploy by answering Y. The stack will take around 20-25 minutes to complete, and once finished you will be presented with some details of the resources that were created.

```
keycloak-demo: creating CloudFormation changeset...

 ✅  keycloak-demo

✨  Deployment time: 1012.98s

Outputs:
keycloak-demo.KeyCloakDatabaseDBSecretArn28BEB641 = arn:aws:secretsmanager:eu-west-1:xxxxx:secret:keycloakdemoKeyCloakDatabas-xxxxxx-1TosEJ
keycloak-demo.KeyCloakDatabaseclusterEndpointHostname38FB0D1E = keycloak-demo-keycloakdatabasedbcluster06e9c0e1-hzjlnplxzu6i.cluster-ceinb9vexcbc.eu-west-1.rds.amazonaws.com
keycloak-demo.KeyCloakDatabaseclusterIdentifierF00C290B = keycloak-demo-keycloakdatabasedbcluster06e9c0e1-hzjlnplxzu6i
keycloak-demo.KeyCloakKeyCloakContainerSerivceEndpointURL9C81E19A = https://keycl-KeyCl-7Y47664RLHT5-2141835688.eu-west-1.elb.amazonaws.com
keycloak-demo.KeyCloakSecret = arn:aws:secretsmanager:eu-west-1:xxxxx:secret:KeyCloakKCSecretF8498E5C-BmrYOayqQBmd-xxxx
Stack ARN:
arn:aws:cloudformation:eu-west-1:xxxxxx:stack/keycloak-demo/9a6e8260-045c-11ee-bb15-062703c4f3a7

✨  Total time: 1025.66s
```

Keycloak is now deployed but before we access it, we need to use the info from the output to update the DNS record for the certificate you created. We need to grab the URL from the load balancer, which you should be able to easily see as it will be the only resource which has a URL reference. In the above output, this is the line "keycloak-demo.KeyCloakKeyCloakContainerSerivceEndpointURL9C81E19A = https://keycl-KeyCl-7Y47664RLHT5-2141835688.eu-west-1.elb.amazonaws.com".

You will need to create a CNAME record pointing to the ELB to the domain record. This will allow you to access Keycloak via a simple link  "https://my-keycloak.demo.com"

The final step is obtaining the admin username and password, which the CDK construct configures AWS Secrets Manager to manage. The admin username is "keycloak" and we can find out the password by running the following command, passing in the value of the AWS Secret resource that was output by CDK. In the above, we can see this as " arn:aws:secretsmanager:eu-west-1:xxxxx:secret:KeyCloakKCSecretF8498E5C-BmrYOayqQBmd-xxxx" (your value will be different, but similar looking)

```
aws secretsmanager get-secret-value --secret-id "arn:aws:secretsmanager:eu-west-1:xxxxxx:secret:KeyCloakKCSecretF8498E5C-BmrYOayqQBmd-xxxx"
```

Which will output something like (password redacted)

```
{
    "ARN": "arn:aws:secretsmanager:eu-west-1:xxxxxxx:secret:KeyCloakKCSecretF8498E5C-BmrYOayqQBmd-xxxxx",
    "Name": "KeyCloakKCSecretF8498E5C-BmrYOayqQBmd",
    "VersionId": "3c9a0c39-00a3-15a2-7712-97a7f8980ca2",
    "SecretString": "{\"password\":\"xxxxxxx\",\"username\":\"keycloak\"}",
    "VersionStages": [
        "AWSCURRENT"
    ],
    "CreatedDate": "2023-06-06T12:24:05.939000+01:00"
}
```
Open up a browser, enter your domain name and you should see the following screen. Click on the admin link, you should now be able to use the admin and password to log in.

![screenshot of keycloak home page](https://ricsuepublicresources.s3.eu-west-1.amazonaws.com/images/blog/keycloak-v21-info.png)

![screenshot of keycloak home page](https://ricsuepublicresources.s3.eu-west-1.amazonaws.com/images/blog/keycloak-v21-screen.png)

Congratulations, you now have a Keycloak service up and running. 

*Cleaning up and removing all resources*

If you need to delete/clean up your Keycloak installation, then CDK makes that very easy to do. However, you will first need to remove the Deletion protection from your RDS database configuration before running this command. If you do not, the deletion process will fail.

```
aws rds describe-db-clusters  --query 'DBClusters[].{DBClusterIdentifier: DBClusterIdentifier}' --output text

keycloak-demo-keycloakdatabasedbcluster06e9c0e1-hzjlnplxzu6i
```
The output will provide you with the Keycloak DB cluster resource, which you can then use to disable deletion protection using the following command:

```
aws rds modify-db-cluster --db-cluster-identifier keycloak-demo-keycloakdatabasedbcluster06e9c0e1-hzjlnplxzu6i --no-deletion-protection
```
You can then run the cdk destroy command to remove your Keycloak resources.

```
cdk destroy keycloak-demo
```

## Next steps

In this post I shared how you can install the open source identity and access management project Keycloak in AWS. We looked at how you can use the CDKv2 construct with a few tweaks to make it easier to deploy this project, and
You are now ready for the next part of this post, integrating Keycloak into AWS Identity Centre as your Idp for SSO. I am writing this post as we speak, so stay tuned for this to drop soon.

If you have found this blog post helpful, please give me some feedback by [completing this very short survey here](https://pulse.buildon.aws/survey/D4L9Y3II).
