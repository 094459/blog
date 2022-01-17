---
title: 'AWS open source news and updates #89'
date: '2021-11-08'
tags : [ oss-newsletter , AWS Open Source]
---
## November 8th, 2021 - Instalment #89

Newsletter #89. This week we have another selection of great new projects for you to take a look at. Kicking things off with the latest open source project from Airbnb, ottr, a Public Key Infrastructure framework that handles end-to-end certificate rotations, the other projects include cloudkey, clock-bound, aws-recon, cdk-dia and more. Make sure you check these out.

As always, we have a wide selection of new blog posts from the AWS and Community bloggers covering topics from Alphafold, BayerCLAW, and Babelfish to OpenSearch, AWS CDK, ffmpeg, Amazon Corretto, Spring Boot, Bottlerocket, Snyk, MariaDB and GitHub actions. 

To finish things off we have a new video covering Suricata on AWS, as well as a new event coming up later this week which you still have time to sign up for.

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Qi Wang, Tom Roshko, Christos Matskas, Vadivelu Murali Pranavan, Kenneth Yang, Danny Gitelman, Daniel Begimher, Afza Wajid, Sudhir Reddy Maddulapally, Alexey Vorovich, Jesse Butler, Damien Martins, Masahiro Imai, Hidenori Koizumi, Jorge Lanzarotti, Ramesh Kumar Venkatraman, Dave Currie, Frank Dallezotte, Maxwell Moon, Jack Tabaska, Ian Davis, Jani Muuriaisniemi, Jose Juhala, Vacha Shah, Sarat Vemulapalli, Irshad Buchh and Yang Xiao.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Community noticeboard

**Hackathon winners**

Great news from Vadivelu Murali Pranavan last week, where he shared the following updated:

> I'm happy to share with you that myself along with my peers Sanjay Thiyagarajan, Naresh Kumar, Jayanth Vikash S, Xavier Emmanuel and Sri Varmaa won the first place in Amazon Web Services (AWS) Graviton Hackathon 2021 in Migration track. Check out the project they created, [Genie](https://aws-oss.beachgeek.co.uk/12a)

### Latest open source projects

**ottr**

[ottr](https://aws-oss.beachgeek.co.uk/12d) this is the latest open source project from Airbnb engineering, Ottr. Ottr is a serverless Public Key Infrastructure framework that handles end-to-end certificate rotations without the use of an agent. You can check out the super detailed blog post, [Meet Ottr: A Serverless Public Key Infrastructure Framework](https://aws-oss.beachgeek.co.uk/12e) from  Kenneth Yang provides an overview on Ottr with details of the architecture, logical and network flows and details on how to deploy.

![arch](https://miro.medium.com/max/2000/1*yUXlXD6mzsLGmMEgAGeIhQ.png)

**cloudkey**

[cloudkey](https://aws-oss.beachgeek.co.uk/12p) this project from Aidan Steele is perfect if you have a Yubikey and want to use it to assume IAM roles to interact with AWS. As Aidan says:

>  "I could create certificates on the Yubikey, enrol them into AWS IoT (for free) and assume roles in AWS with no IAM secret access keys stored on disk."
> 

Worth checking out Aidan's [thread on twitter, here](https://aws-oss.beachgeek.co.uk/12q) for more context.

**clock-bound**

[clock-bound](https://aws-oss.beachgeek.co.uk/12b) this new project provides you with a consistent, trusted time service will allow you to compare timestamps to determine order and consistency for events and transactions, independent from the instances’ respective geographic locations.

![diagram](https://github.com/aws/clock-bound/blob/main/ClockErrorBound.png?raw=true)

**aws-recon**

[aws-recon](https://aws-oss.beachgeek.co.uk/12h) this project from Darkbit is a multi-threaded AWS security-focused inventory collection tool written in Ruby, and was created to facilitate efficient collection of a large amount of AWS resource attributes and metadata. It aims to collect nearly everything that is relevant to the security configuration and posture of an AWS environment. It is being used by some interesting customers, so well worth checking this out.

**cdk-dia**

[cdk-dia](https://aws-oss.beachgeek.co.uk/12i) this project from Tom Roshko looks super neat, it diagrams your CDK provisioned infrastructure using the Graphviz dot language. After getting Graphviz running on my Macbook (thanks Mac Ports) I tried it on one of my projects, and here is the output. What do you think? A great start, so it will be interesting to see how this project evolves and develops. Nice work Tom!

![demo](https://ricsuepublicresources.s3.eu-west-1.amazonaws.com/images/diagram.png)


**aws-cdk-github-oidc**

[aws-cdk-github-oidc](https://aws-oss.beachgeek.co.uk/12j) is a CDK constructs to use OpenID Connect for authenticating your Github Action workflow with AWS IAM. These constructs allows you to harden your AWS deployment security by removing the need to create long-term access keys for Github Actions and instead use OpenID Connect to Authenticate your Github Action workflow with AWS IAM.

![arch](https://raw.githubusercontent.com/aripalo/aws-cdk-github-oidc/4eb53714ec69583f057141afab57c6c2cd7dae0b/assets/github-aws-oidc.svg)

You can check out last weeks newsletter where Richard Boyd shows you using this new capability of GitHub Actions. 

**fiware-orion-on-aws**

[fiware-orion-on-aws](https://aws-oss.beachgeek.co.uk/125) FIWARE is a curated framework of open source platform components to help with the development of smart applications and solutions. This repository is a reference implementation of one of those components, the Orion Context Broker which uses another component in that project, Cygnus. To help you get started, check out the blog post [How to build smart cities with FIWARE Orion Context Broker and Cygnus on AWS](https://aws-oss.beachgeek.co.uk/124)from Masahiro Imai, Hidenori Koizumi, and Jorge Lanzarotti

![arch](https://d2908q01vomqb2.cloudfront.net/9e6a55b6b4563e652a23be9d623ca5055c356940/2021/11/02/orion-cygnus-onaws.png)

**Retro corner**

Thanks to Corey Quin for highlighting this tool I had missed.

**aws-key-disabler**

[aws-key-disabler](https://aws-oss.beachgeek.co.uk/129) this open source project is a small lambda script that will disable access keys older than a given amount of days. Small but perfectly formed, I think this is a great solution if you find yourself needing to automate the vending of your keys.

### Tweet of the week

This [tweet](https://aws-oss.beachgeek.co.uk/11y) from Christos Matskas (@ChristosMatskas) came up on my timeline last week, where he shared how he was able to use the open sourced NodeJS library for verifying JWTs that I shared in the last episode, and verify AAD access tokens from Azure Active Directory. He also shared the code, which you can check out at [here](https://aws-oss.beachgeek.co.uk/11z). Christos also put this post together, [Open Standards, Security, Azure AD and AWS](https://aws-oss.beachgeek.co.uk/120) which shows you the end to end story. Nice!

### AWS and Community blog posts

**AWS CDK**

Building Software as a Service (SaaS) is an increasingly popular approach for open source projects to provide customers with immediate access to their capabilities. There are several approaches you can take, but being able to well and ensure a good experience during on boarding, you need to have a reliable, fast, and multi-region capable provisioning and software lifecycle management. In the post, [Parallel and dynamic SaaS deployments with AWS CDK Pipelines](https://aws-oss.beachgeek.co.uk/12k) Jani Muuriaisniemi and Jose Juhala describe a deployment system for achieving this using AWS CDK and AWS CDK Pipelines. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/7719a1c782a1ba91c031a682a0a2f8658209adbf/2021/10/27/figure1-1.png)

**BayerCLAW**

I shared details of BayerCLAW in a previous newsletter (#86). BayerCLAW a workflow orchestration system for AWS, targeted at bioinformatics pipelines. Jack Tabaska and Ian Davis from the Bayer Crop Sciences team have put together this blog post, [BayerCLAW – Open-Source, Serverless Orchestrator for Scientific Workflows on AWS](https://aws-oss.beachgeek.co.uk/12f) that takes a look at the motivations and technical implementation of BayerCLAW.

![arch](https://d2908q01vomqb2.cloudfront.net/c5b76da3e608d34edb07244cd9b875ee86906328/2021/10/27/bayer-figure-1-CLAW.png)

**AlphaFold**

AlphaFold is an artificial intelligence program developed by Alphabets's/Google's DeepMind which performs predictions of protein structure. In this post, [Run AlphaFold v2.0 on Amazon EC2](https://aws-oss.beachgeek.co.uk/12m), Qi Wang provides a step-by-step guide on how to install AlphaFold on an EC2 instance with Nvidia GPU.

![alpha](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2021/10/25/ML_5671_3Dview.png)

**Babelfish**

In the post [Migrate from SQL Server to Amazon Aurora using Babelfish](https://aws-oss.beachgeek.co.uk/126), Ramesh Kumar Venkatraman provides and overview of how you can migrate from SQL Server to Babelfish for Aurora PostgreSQL. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2021/11/04/DBBLOG-1441-image001-cropped.png)

**Amazon Corretto**

Dave Currie shares details of the Amazon Corretto support roadmap in his post, [Announcing Amazon Corretto 17 support roadmap](https://aws-oss.beachgeek.co.uk/127). Make sure you read this short post and understand what this means for any workloads you have running Amazon Corretto 8 or 11.

**Spring Boot**

[Build and deploy a Spring Boot application to AWS App Runner with a CI/CD pipeline using Terraform](https://aws-oss.beachgeek.co.uk/12o) is the perfect post if you want to learn about how to setup a really nice automated deployment pipeline for your Spring Boot applications on AWS. Irshad Buchh and Yang Xiao walk you through setting up a pipeline for automatic build and deployment onto AWS App Runner. Read on to find out more [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2021/09/22/springbootapprunner1.png)

**Bottlerocket**

Jesse Butler opens this post up with the question “Does the OS even matter anymore?” - intrigued? Have your own opinion? Well find out what he thinks in the excellent post, [Bottlerocket, A Year in the Life](https://aws-oss.beachgeek.co.uk/123) - (and I totally agree, for anyone interested!) [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2021/10/25/br_update.png)

**Snyk**

Danny Gitelman and Daniel Begimher share how to use tools like Snyk in combination with an automated workflow to reduce the risk of downloading new packages from public repositories. Read more in their post, [How to automate your software-composition analysis on AWS](https://aws-oss.beachgeek.co.uk/121) [hands on]

[arch](https://d2908q01vomqb2.cloudfront.net/b7eb6c689c037217079766fdb77c3bac3e51cb4c/2021/10/15/software-composition-analysis-architecture-diagram.jpg)

**MariaDB**

SkySQL is a database as a service (DBaaS) solution on AWS that makes it easy for customers to start using MariaDB Enterprise in the cloud. In the post, [MariaDB Collaborates with AWS to Deliver SkySQL on AWS](https://aws-oss.beachgeek.co.uk/122) Afza Wajid and Sudhir Reddy Maddulapally speak with Alexey Vorovich, VP of Engineering for SkySQL at MariaDB Corporation, about the recent SkySQL launch.

**FFmpeg**

Damien Martins shares with you a how-to guide describes the steps to invoke an automatic extraction of media asset metadata through ffprobe (part of the FFmpeg project) in his post, 
[Analyzing media files using ffprobe in AWS Lambda](https://aws.amazon.com/blogs/media/analyzing-media-files-using-ffprobe-in-aws-lambda/) [hands on]

**GitHub Actions**

Frank Dallezotte and Maxwell Moon have collaborated on this post, [Building ARM64 applications on AWS Graviton2 using the AWS CDK and Self-Hosted Runners for GitHub Actions](https://aws-oss.beachgeek.co.uk/128) where they show how to configure of a self-hosted GitHub Runner on an EC2 instance with a Graviton2 processor, the required network resources, and a workflow that will run on the Runner on each repository push or pull request for the example application. This will allow you to start to create multi architecture builds so that you can start leveraging Arm based AWS Graviton2 instances and the improved price/performance as well as power characteristics. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2021/10/25/0_Graviton2GHRunnerArchDrawing-1.png)

**OpenSearch**

In the post, [Backwards Compatibility Testing for OpenSearch](https://aws-oss.beachgeek.co.uk/12n) Vacha Shah and Sarat Vemulapalli show you how backwards compatibility testing works within OpenSearch, something that is used to test and determine the safe upgrade paths from a supported version to the current version.


### Quick updates

**Amazon Time Sync Service**

Amazon Time Sync Service now allows you to easily generate and compare timestamps from Amazon EC2 instances with ClockBound, an open source daemon and library. This information is valuable to determine order and consistency for events and transactions across EC2 instances, independent from the instances’ respective geographic locations. ClockBound calculates your Amazon EC2 instance’s clock error bound to measure its clock accuracy and allows you to check if a given timestamp is in the past or future with respect to your instance’s current clock. On every call, ClockBound simultaneously returns two pieces of information: the current time and the associated absolute error range. This means that the actual time of a ClockBound timestamp is within a set range.

To get started, first make sure you are using Chrony. Then install the ClockBound daemon and library, or build your own library to integrate ClockBound into your application. For the best clock accuracy, we also recommend using the Amazon Time Sync Service. The Amazon Time Sync Service and Chrony are configured by default on Amazon Linux 2 instances.

Check out the code repo at the top of this post.

### Video of the week

**Suricata**

Nick Coval & Adam Palmer presented "[Building an Open Source IDS/IPS Service on AWS with Suricata](https://aws-oss.beachgeek.co.uk/12l)" at SuriCon, where they talk about how they built a quick-start solution on AWS that creates a Suricata-based solution, powered by AWS Gateway Load Balancer service (GWLB); enabling centralized and distributed deployment models.

{% youtube 2itI5zgXDP4 %}

### Events for your diary

**MLOps: End-to-End Hugging Face Transformers with the Hub & SageMaker Pipelines**
**November 10th 2021 - 6:00 PM (GMT)**

Later this week, we have this workshop where you will learn how to build an End-to-End MLOps Pipeline for Hugging Face Transformers from training to production using Amazon SageMaker. Join the always amazing Julien Simon, together with Matteu Desve and Phillip Schmid for this webinar. [Read more and register here.](https://aws-oss.beachgeek.co.uk/12g)


**Databricks | AWS Lakehouse Dev Day Live Workshop**
**November 16th 9:00 AM PT**

Delta Lake is an open source storage layer that provides ACID transactions, scalable metadata handling, and unifies streaming and batch data processing. You can use Delta Lake on top of your existing data lake. During this workshop you will learn how to:

* Make your existing Amazon S3 data lakes into a lakehouse with Delta Lake.  
* Provide an easy-to-use platform for analysts to directly query data on your data lake using SQL Analytics
* Simplify and automate data pipelines for streaming and batch data to lower costs and boost productivity for your data teams

[Read more and sign up here](https://aws-oss.beachgeek.co.uk/zs).

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)