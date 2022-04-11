---
title: 'Amazon Aurora - setting up and configuration, four ways'
date: '2020-10-15'
tags: [Amazon Aurora, AWS CDK, AWS CloudFormation, AWS Cli, IaC]
---
In this post I want to share four different approaches to installing and configuring your Amazon Aurora database clusters. 

Everything in this post is covered in detail in the embedded video, but I wanted to share some additional information that I did not include in the video that was easier done in this blog.

{% youtube wZfh9PurE9E %}

### Why four ways?

The approach in the video was to look at the journey you might take when learning a new technology and then how you move to productise that technology. One of the principal building blocks of creating modern applications is that you move to repeatable and reproducible environments and the move towards Infrastructure as Code. 

But how do you start and what does that journey look like? I wanted to share what that **might** look like using a single AWS service. In this video I share how you build a sample Amazon Aurora architecture using these different approaches so you can see what the journey looks like.

![Architecture](https://ricsuepublicresources.s3-eu-west-1.amazonaws.com/images/ricsue-aurora-cbvid.png)

### 1. GUI/Console

As noted in the video, the GUI/Console is the first port of call when looking to experiment and understand a new AWS service. Beyond that however, there really is no reason why you would need to access the console.

### 2. AWS CLI / Scripts

The AWS CLI is the first stage of automating your installation/configuration steps. The ease of use and clear documentation make reduce the learning curve, especially if you are already used to using the AWS CLI for other AWS services.

If you come from a sysadmin background, are a bash/shell script whizz then creating some build/config scripts will be easy for you, and integrating these into automated build tools that you use should not be too difficult. The challenge however comes from you having to understand the inputs/outputs and sequencing of how to use the various commands. These might change over time, and what do you do to handle exceptions/errors? That's right, you need to code those in your scripts.

When you factor in the need to be able to update/roll back changes, managing the lifecycle of those scripts and even the skills you need to maintain/manage it is not surprising that many look for other ways to automate.

In the video I share a bunch of scripts, you will find those in the [GitHub repository here](https://github.com/094459/AmazonAurora4ways).

### 3. AWS CloudFormation

AWS CloudFormation takes a lot of those pain points away, and moves you to a declarative way of defining your end state and letting CloudFormation go about doing the heavy lifting. 

This does however, introduce a new DSL (domain specific language) which you need to learn and you will soon become very familiar with YAML or JSON configuration files. I found it reasonably straight forward to get started, thanks in part to the many examples and blog posts providing some great starting points with what you want to do. CloudFormation templates have a reputation for being big, with even simple tasks requiring lots of lines of YAML. I am not sure this is a problem for me, but be aware of that.

One final observation is that not all AWS services are launched with CloudFormation support, so that is something you need to look out for. You can use [Resource Providers](https://docs.aws.amazon.com/cloudformation-cli/latest/userguide/resource-types.html) to allow you to cover any gaps (as well as allowing you to integrate your own products) 

> It is worth noting that there are other third party solutions that I did not try as part of this video. I could have experimented with [HashiCorp's Terraform](https://www.terraform.io/) or perhaps [Pulumi](https://www.pulumi.com/) but ran out of time - maybe next time.

In the video I share a bunch of scripts, you will find those in the [GitHub repository here](https://github.com/094459/AmazonAurora4ways/tree/main/cloudformation).


### 4. AWS CDK

AWS CDK takes the familiar approach of defining the infrastructure and application in a declarative manor, providing a more opinionated approach with sensible, security first defaults, that allow you to very quickly install and configure your AWS resources, such as Amazon Aurora, very quickly indeed.

Installation is painless, and you have a number of options (AWS Cloud9) if you do not want (or cannot) install Node on your local machine. There are also loads of great tutorials on getting started with AWS CDK, including the very nice [AWS CDK Workshop](https://cdkworkshop.com/) which is a must do workshop.

Once familiar and having deployed a few Hello World projects, you are ready to write your CDK application. As you work with an IDE (I was using VSCode, but others will do) if you are a developer, things will look very natural. You code in your preferred language, importing the necessary AWS CDK constructs and then once finished, you run some CDK commands to synthesise and then deploy your application. Under the covers this creates and then deploys CloudFormation templates.

AWS CDK therefore inherits all of the same advantages that you get with AWS CloudFormation but you get started immediately via your preferred programming language (ok, as long as it is Python, Typescript/Javscript, C#, Java with Go coming soon) - no more needing to learn the CloudFormation DSL. Even if you are not a programmer, you can write much shorter applications in CDK, that during synthesis expand out to many hundreds of lines of CloudFormation.

One thing that I did notice about AWS CDK - once I started, I just could not stop. It is strangely compelling...

In the video I share a bunch of scripts, you will find those in the [GitHub repository here](https://github.com/094459/AmazonAurora4ways/blob/main/cdk/cdk.md).

### Lessons Learned

Whilst I knew about the internals and architecture of Amazon Aurora, getting to understand how these translated as things I could do myself was where the AWS Console experience really helped. What I did find however, later whilst I was experimenting with how to configure Auto Scaling policy sets is that sometimes information that was configured did not appear in the console (this manifested itself as when trying to delete/remove a cluster, it would refuse saying that there was still components configured).

Incase you come into this, the trick was to use the aws cli to first find and then remove these. Here are the commands I used, they may help you one day.

To show all your Amazon Aurora related Auto Scaling policies you can use this command.

```
aws application-autoscaling describe-scalable-targets --service-namespace rds --region={your region}
```

You can then use the following to de-register and remove them. **WARNING** use with care and only if you know what you are doing. You will need to provide the cluster id of the database cluster you are looking to fix.

```
application-autoscaling deregister-scalable-targets --service-namespace rds --resource-id cluster:{clustername} --scalable-dimension rds:cluster:ReadReplicaCount --region={your region}
```

Using the AWS CLI was a joy, and the documentation was clear and provided simple examples that allowed me to get everything I needed configured with speed and accuracy. I think using the AWS CLI is a really great place to start, as it gets you in the mental model of how these services you are working with work and what information they need during setup and configuration. These come in handy later on when using AWS CloudFormation and AWS CDK.

I found AWS CloudFormation easier than I thought, and I think that if you are coming from a SysAdmin background, are more infrastructure than developer, you may find the same. I would use the CloudFormation templates I had created as a way of understanding how to craft and write my AWS CDK applications where there were gaps or lack of clarity in the  documentation. 

Starting off with a given programming language did make a difference when it came to using AWS CDK. If you are a Javascript/Typescript developer then you will be glad to hear that this looks to have the broadest set of examples and patterns you can use to get started. I was using Python and there are fewer examples, which meant more work for me to do!

AWS CDK was a lot easier to get started than I had anticipated. Not only that, but once I had understood the basics it became incredibly addictive, and the progression from simple single stack CDK apps to more structured and compossible apps soon followed.

Going forward I think I will now start to build using AWS CDK first. With an increasing number of patterns and examples thanks to the CDKPatterns.com initiative, the only thing I really now need to do is dust off my javascript skills and start learning Typescript.

#### Prior Art

One of the ways of understand how some of these AWS developer tools work is reading how others are using or developing with them. I found the following invaluable, they saved me time and provided some great starting points, and help me have those aha! moments.

**Standing on the shoulder of...**

I would also recommend you follow some of these folks who I would consider experts in this field and regular post on the topic of infrastructure as code, build automation and more.

[Darko](https://twitter.com/darkosubotica)
[Elad Ben Israel](https://twitter.com/emeshbi)
[Matt Coulter](https://twitter.com/NIDeveloper)

*https://dev.to/cdkpatterns
* https://gist.github.com/jonnyyu/980dfa9e40c7401130d78fe153b4d629
* https://www.openconstructfoundation.org/guides/open-cdk/
* https://www.europeclouds.com/blog/deploying-cloud-infrastructure-using-the-aws-cdk
* https://www.reddit.com/r/aws/comments/hnuizz/cdk_help_not_able_to_get_scaling_config_for_an/
* https://github.com/martinbpeters/cdk-vpc-postgres/blob/master/stacks/rds_postgres.py

**AWS CLI references**

* Installation of the AWS CLI (make sure you install v2)-https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-install.html
* AWS CLI reference documentation - https://awscli.amazonaws.com/v2/documentation/api/latest/reference/index.html

**AWS CloudFormation references**

* The only video you will probably ever need when it comes to CloudFormation, courtesy of Ian Massingham. https://www.youtube.com/watch?v=6R44BADNJA8
* AWS CloudFormation documentation - https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/GettingStarted.html
* AWS CloudFormation templates - https://aws.amazon.com/cloudformation/resources/templates/

**AWS CDK references**

* Installation of AWS CDK -https://docs.aws.amazon.com/cdk/latest/guide/cli.html
* AWS CDK Workshop - https://cdkworkshop.com/
* Documentation of AWS CDK - https://docs.aws.amazon.com/cdk/latest/guide/home.html
* AWS CDK Construct reference documentation, some of the ones I have used include:


* https://docs.aws.amazon.com/cdk/api/latest/python/aws_cdk.aws_rds.README.html#
* https://docs.aws.amazon.com/cdk/api/latest/python/aws_cdk.aws_rds/CfnDBCluster.html
* https://docs.aws.amazon.com/cdk/api/latest/python/aws_cdk.aws_rds/CfnDBInstance.html
* https://docs.aws.amazon.com/cdk/api/latest/python/aws_cdk.aws_applicationautoscaling.README.html





