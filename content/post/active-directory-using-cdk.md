---
title: 'Using CDK to deploy AWS managed Active Directory'
date: '2023-06-12'
tags : [ Active Directory, aws, CDK]

---

CIFS (Common Internet File System) and SMB (Server Message Block) are both Windows file-sharing protocols used in storage systems. As part of a new demo/blog post that looks at how to use data stored on SMB/CIF file shares with Apache Airflow, I have been exploring the various options of creating SMB/CIF compatible resources. (There are LOTS of ways you could do this, so there is plenty for me to play around with!)

One thing that I have so far found in the different AWS options that provide SMB/CIFs shares, is the need to have an Active Directory server. Rather than do this manually, I decided to put together a quick CDK app to do this. It was at this point I realised there is no dedicated CDK construct or third party one to help me.

This post and supporting CDK code, will help you to deploy your own Active Directory server on AWS.

**Pre-reqs**

* Admin access to an AWS account
* CDKv2 - I am using version 2.83.1 (build 006b542)
* Code from the support repo on Github

Also, it is worth checking to make sure how many VPCs you have in the AWS Account you are deploying to. The default value (five) will cause this stack to fail. You will need to either clean up and remove a VPC or increase the limits via the AWS Support Centre.

**Updating the CDK app**

The CDK stack is simple to use, and only has a few configuration values you need to change. Review the "app.py"

```
#!/usr/bin/env python3
import os

import aws_cdk as cdk

from active_directory_cdk.active_directory_cdk_stack import ActiveDirectoryCdkStack
from active_directory_cdk.active_directory_vpc_cdk_stack import ActiveDirectoryVPCCdkStack

env_EU=cdk.Environment(region="eu-west-1", account="xxxxx")
ad_props = {
    'adminpw': 'XXXXX'
    }

app = cdk.App()

ad_vpc = ActiveDirectoryVPCCdkStack(
    scope=app,
    id="ad-demo-vpc",
    env=env_EU
)
ad_svc = ActiveDirectoryCdkStack(
    scope=app,
    ad_props=ad_props,
    vpc=ad_vpc.vpc,
    id="ad-demo-svc",
    env=env_EU
)

app.synth()

```

You will need to update:

* "env_EU=cdk.Environment(region="eu-west-1", account="xxxxx")" - update this to the AWS region you want to deploy this into and your AWS account ID
* adminpw - the password for your Active Directory server

Once saved, you are ready to go. There are two stacks, a VPC which configures a set of subnets and other supporting configuration, and the Active Directory service itself.

Feel free to review and update the Active Directory stack, as there are some defaults (for example, I am using Standard version of Active Directory) which you might want to change. You can [review the CDK options here](https://aws-oss.beachgeek.co.uk/2wx).

**Deploying the VPC**

To deploy the VPC, we issue the following command:

```
cdk deploy ad-demo-vpc
```

After the security review screen appears, review the changes it wants to make and then if  happy, accept by entering Y. It will then begin the deployment, which will not take very long (around 5 minutes)

```
Do you wish to deploy these changes (y/n)? y
ad-demo-vpc: deploying... [1/1]
ad-demo-vpc: creating CloudFormation changeset...

 ✅  ad-demo-vpc

✨  Deployment time: 189.92s

Outputs:
ad-demo-vpc.ExportsOutputRefActiveDirectoryVPC2144D098DCB0A199 = vpc-0c27816a836fbf6xx
ad-demo-vpc.VPCId = vpc-0c27816a836fbf6xx
Stack ARN:
arn:aws:cloudformation:eu-west-1:xxxxx:stack/ad-demo-vpc/65ff5c40-0928-11ee-977a-0aa2508e9exx

✨  Total time: 207.76s
```

Thats it, you now have your Active Directory VPC ready.

**Deploying the AWS managed Active Directory service**

You can now deploy your AWS managed Active Directy by running the following command:

```
cdk deploy ad-demo-svc
```
After a short period of time, you should start to see the following:


```
Including dependency stacks: ad-demo-vpc

✨  Synthesis time: 42.1s

ad-demo-vpc
ad-demo-svc:  start: Building 0e81c87131646c8920aeade9138ffa084a619c43e9300d80f227601b2b2727ee:xxxx-eu-west-1
ad-demo-svc:  success: Built 0e81c87131646c8920aeade9138ffa084a619c43e9300d80f227601b2b2727ee:xxxx-eu-west-1
ad-demo-vpc: deploying... [1/2]

 ✅  ad-demo-vpc (no changes)

✨  Deployment time: 0.56s

Outputs:
ad-demo-vpc.ExportsOutputRefActiveDirectoryVPC2144D098DCB0A199 = vpc-0c27816a836fbf647
ad-demo-vpc.ExportsOutputRefActiveDirectoryVPCprivateSubnet1Subnet8412232C20F4D83D = subnet-0f0559dbc264e044e
ad-demo-vpc.ExportsOutputRefActiveDirectoryVPCprivateSubnet2Subnet8590169196038FD9 = subnet-017995205bfa2ce07
ad-demo-vpc.VPCId = vpc-0c27816a836fbf647
Stack ARN:
arn:aws:cloudformation:eu-west-1:xxxx:stack/ad-demo-vpc/65ff5c40-0928-11ee-977a-0aa2508e9e95
..
..
..

```

This did take around 15-20 minutes to complete. You can check your progress by looking at the Cloudformation screen, or by heading over to the Directory Service console and checking on the creation progress.

When finished, you should see something like:


```
✨  Total time: 42.66s

ad-demo-svc:  start: Publishing 0e81c87131646c8920aeade9138ffa084a619c43e9300d80f227601b2b2727ee:xxxx-eu-west-1
ad-demo-svc:  success: Published 0e81c87131646c8920aeade9138ffa084a619c43e9300d80f227601b2b2727ee:xxxx-eu-west-1
ad-demo-svc
ad-demo-svc: deploying... [2/2]
ad-demo-svc: creating CloudFormation changeset...

 ✅  ad-demo-svc

✨  Deployment time: 1794.84s

Outputs:
ad-demo-svc.ActiveDirectoryId = d-936xx443ba
Stack ARN:
arn:aws:cloudformation:eu-west-1:xxxx:stack/ad-demo-svc/88c80a10-0932-11ee-b326-0a5a6e0a9f8d

✨  Total time: 1836.94s
```

Thats it, you have now completed the deployment of Active Directory. If you go to the AWS Console, you can see this as being up and running.

**Cleaning up**

Once you have had your Active Directory fun, you can clean up/delete the setup by running the following commands:

```
cdk destroy ad-demo-svc
cdk destroy ad-demo-vpc
```

It will take about 10-15 minutes to complete the deletion of all the resources. This is a destructive process, so make sure you understand this before deleting.


## Conclusion

In this post I shared how you can install an AWS managed Active Directory service using AWS CDK.

If you have found this blog post helpful, please give me some feedback by [completing this very short survey here](https://pulse.buildon.aws/survey/D4L9Y3II).
