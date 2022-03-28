---

title: 'AWS open source news and updates #106'
date: '2022-03-28'
tags : [ oss-newsletter, aws open source, Terraform, Hugging Face, AWS Proton, AWS GameKit, Amazon Corretto, OpenJDK, AWS Amplify, Quarkus, PostgreSQL, BotKube, Kubernetes, AWS Genomics CLI, Openswan, MySQL, OrgFormation, DataHub]

---

## March 28th, 2022 - Instalment #106

Newsletter #106. 

Welcome to the AWS open source newsletter, and this week we have more great new open source projects to tell you about. We have "access-undenied-aws", a tool that helps you better understand your CloudTrail logs and suggest remediation. "aws-slack-clickoops-watcher" provides you with a way to alert you when changes are made to your AWS environment. "kronicle" provides a way of illustrating your tech stack automagically, and we have many more tools, demos and sample projects to help get you started on a number of topics.

Also featured are community and AWS posts covering the following open source technologies, Terraform, Hugging Face, AWS GameKit, AWS Amplify, Quarkus, PostgreSQL, BotKube, Kubernetes, Openswan, MySQL, OrgFormation, DataHub, and more. Check out the video of the week featuring the AWS Genomics CLI, and as always, we have a round up of open source events coming up which you might find interesting.

**Do you have an interesting open source project you want to share?**

As always, if you are working on anything interesting you would like me to include in this weekly round up, please drop me a line at ricsue@amazon.com.


### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Paul Zietsman, Gary Stafford ,Will Dady, Simon Dean, Shan Kandaswamy, Mamata Vaidya, Eddie Jaoude, Matt Auerbach, Brendan Bouffler, Lee Pang, Aaron Wishnick, Heiko Hotz, Jonathan Katz, Joan Bonilla,  Elamaran Shanmugam, Jayaprakash Alawala, Re Alvarez-Parmar, Randy Westergren, Michael Hausenblas, Miedwar Meshbesher, Matt Lewis, Michael Bahr, and Olaf Conijn. 

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest open source projects

#### Community

**access-undenied-aws**

[access-undenied-aws](https://aws-oss.beachgeek.co.uk/1io) this project from Ermetic received a lot of attention and looks interesting. Access Undenied parses AWS AccessDenied CloudTrail events, explains the reasons for them, and offers actionable remediation steps. Nice detailed docs and quick demo to show you how it works, this looks super useful.

![demo of access-undenied](https://github.com/ermetic/access-undenied-aws/blob/main/examples/example.gif?raw=true)

**aws-slack-clickoops-watcher**

[aws-slack-clickoops-watcher](https://aws-oss.beachgeek.co.uk/1ir) this project from Paul Zietsman allows you to monitor your AWS accounts for changes being made in the console, messaging you in Slack when it detects changes. Hat tip to Corey Quinn's newsletter where I found this project.

**kronicle**

[kronicle](https://aws-oss.beachgeek.co.uk/1ik) Kronicle open source tool and dashboard for documenting and visualising a tech stack. Simon Dean [share a post on LinkedIn](https://aws-oss.beachgeek.co.uk/1il), where he shared how he had been working on a new AWS plugin. Check out the post and the repo for more info, looks interesting.

**cdk-iam-credentials-rotator**

[cdk-iam-credentials-rotator](https://aws-oss.beachgeek.co.uk/1im) this open source project from Will Dady is an AWS CDK construct for rotating IAM user credentials and sending to a third party. Simply provide a list of usernames of IAM users which exist in the target account and a Lambda function to handle the newly created credentials for a given user.

![architecture for cdk-iam-credentials-rotator project](https://github.com/willdady/cdk-iam-credentials-rotator/blob/main/images/diagram.png?raw=true)

#### Tools

**crossplane-aws-blueprints**

[crossplane-aws-blueprints](https://aws-oss.beachgeek.co.uk/1ih) Crossplane is an open source Kubernetes add-on that enables platform teams to assemble infrastructure from multiple vendors, and expose higher level self-service APIs for application teams to consume, without having to write any code. This repository to bootstrap EKS Clusters and provision AWS resources with a library of Crossplane Compositions (XRs) with Composite Resource Definitions (XRDs). Compositions in this repository enable platform teams to define and offer bespoke AWS infrastructure APIs to the teams of application developers based on predefined Composite Resources (XRs), encompassing one or more of AWS Managed Resources (MRs).

> **Note!** AWS Blueprints for Crossplane is under active development and should be considered a pre-production framework.

**aws-config-detect-environment-variables-secrets-terraform**

[aws-config-detect-environment-variables-secrets-terraform](https://aws-oss.beachgeek.co.uk/1ii) this repo contains a Terraform module that creates a custom rule on AWS Config that detects secrets/tokens in the Lambda functions in the account.

![architecture for aws-config detection of variables and secrets](https://github.com/aws-samples/aws-config-detect-environment-variables-secrets-terraform/blob/main/.images/lambda-secrets-detector.png?raw=true)

**aws-gamekit-unreal**

[aws-gamekit-unreal](https://github.com/aws/aws-gamekit-unreal) announced last week, AWS GameKit is an open sourced plugin that lets you configure and deploy a game feature from your Unreal Engine game project. AWS GameKit offers a suite of core game backend features at launch, including Identity and Authentication, Achievements, Game State Cloud Saving, and User Gameplay Data. To find out more, read the blog post [AWS Announces AWS GameKit for Unreal Engine](https://aws-oss.beachgeek.co.uk/1i3)

**rust-smt-ir-examples**

[rust-smt-ir-examples](https://aws-oss.beachgeek.co.uk/1ij) This project provides examples of using a rust-smt-ir, a Rust intermediate representation (IR) for SMT-LIB. Read the documentation to find out more about this and the three sample applications provided. 

#### Demos and Samples

**Mantil example-chat**

[example-chat](https://aws-oss.beachgeek.co.uk/1in) Mantil is a modern open-source framework for writing serverless apps in Go. This example shows how one can make a simple cloud native chat app with a serverless backend written in Go. Backend is built on AWS Lambda and uses WebSocket API and DynamoDB. 

**serverless-dotnet-demo**

[serverless-dotnet-demo](https://aws-oss.beachgeek.co.uk/1ig) With the release of .NET 6 AWS Lambda now supports .NET Core 3.1 and .NET 6 as managed runtimes. With the availability of ARM64 using Graviton2 there have been vast improvements to using .NET with Lambda. But how does that translate to actual application performance? And how does .NET compare to other available runtimes. This repository contains a simple serverless application across a range of .NET implementations and the corresponding benchmarking results.

![architecture of dotnet demo](https://github.com/aws-samples/serverless-dotnet-demo/blob/main/imgs/diagram.jpg?raw=true)

**aws-amplify-sample-registrationapp**

[aws-amplify-sample-registrationapp](https://aws-oss.beachgeek.co.uk/1i9) this demo repository provides a sample single page registration web application code to demonstrate how using AWS Amplify rapidly accelerates building a Serverless Full Stack Registration App. To help you with building this, you can read the blog post [Build a Serverless Full-Stack Registration App in minutes using AWS Amplify](https://aws-oss.beachgeek.co.uk/1ia) from Shan Kandaswamy and Mamata Vaidya.

![architecture of demo](https://d2908q01vomqb2.cloudfront.net/0a57cb53ba59c46fc4b692527a38a87c78d84028/2022/03/17/architecture-V3.drawio.png)

### AWS and Community blog posts

**DataHub**

[DataHub](https://aws-oss.beachgeek.co.uk/1ip) is an open-source metadata platform for the modern data stack. Gary Stafford has put together a new blog post, [End-to-End Data Discovery, Observability, and Governance on AWS with LinkedIn’s Open-source DataHub](https://aws-oss.beachgeek.co.uk/1iq) that dives deep into the topic of data cataloging options (open source and commercial), before diving deep on DataHub, showing how you can integrate this within AWS and some AWS services. Another must read post from Gary. [hands on]

![architecture of DataHub on AWS](https://miro.medium.com/max/1400/1*-2DT-TQ-UZ06WAL_eIx9TQ.png)

**MySQL**

If you are looking to connect to MySQL databases in your AWS Lambda functions, then this post from Randy Westergren, [Building pymssql (FreeTDS) for Lambda](https://aws-oss.beachgeek.co.uk/1id) elaborates from a previous post of his, and this time he shows you how he built the Lambda layer. [hands on]

**Openswan**

Openswan is an IPsec implementation for Linux, and I have used this myself many times when creating site to site VPNs between my home network and my VPN Gateway in a VPC. In this post from the folks at Kloudvm, [AWS Site to Site VPN Using OpenSwan IPSEC Step By Step Tutorial](https://aws-oss.beachgeek.co.uk/1ie), they share their way of setting this up. [hands on]

**Observability**

This post came from the always excellent [weekly newsletter from Michael Hausenblas, o11y news!](https://aws-oss.beachgeek.co.uk/1if) (make sure you sign up so you don't miss it). In the post, Who watches the watchers?, Miedwar Meshbesher shares a great post on how to make sure that you watch your monitoring tools - very much a case of watching the watchmen. This is a detailed walk through and tutorial of how you can do this, made easier by the fact that the code is provided as Terraform HCL. Very nice post, make sure you check this out. [hands on]

**OrgFormation**

Setting up a multi-account AWS environment is a great series of posts from AWS Hero, Matt Lewis that looks at building out a multi-account best practice landing zone, using an open source tool that regular readers of this newsletter will be familiar with, AWS Organization Formation (OrgFormation) from Olaf Conijn. Building on some great work from another AWS Hero, Michael Bahr, you will learn more about how you can use this project and take advantage of features to help you enforce security and compliance, and incident response. [hands on]

![architecture](https://res.cloudinary.com/practicaldev/image/fetch/s--cLvYwT_9--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/mibcsf8o8ef0a3k5i8a9.png)

**Terraform**

AWS Proton is a fully managed application deployment service for containers and serverless that platform teams can use to connect and coordinate all the different tools needed for infrastructure provisioning, code deployments, monitoring, and updates in a curated self-service interface for developers. The self-service interface provides developers access to approved infrastructure to build and deploy their applications. Aaron Wishnick takes a deep dive in how you can set this up in a two part blog, [AWS Proton Terraform Templates](https://aws-oss.beachgeek.co.uk/1i0) and [AWS Proton Self-Managed Provisioning](https://aws-oss.beachgeek.co.uk/1hz). One of the must read posts this week! [hands on]

![architecture of AWS Proton on Terraform](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2022/03/23/aws-proton-3.jpg)

**Hugging Face Transformers**

In this two part blog, Heiko Hotz provides a practical guide for organisations so you can assess the quality of text summarisation models for your domain. Text summarisation is the capability of a computer to read a given text and summarise its content. It’s one of the hardest tasks for a computer because it combines two fields within the field of natural language processing (NLP): reading comprehension and text generation. Dive deeper by reading part one, [Set up a text summarization project with Hugging Face Transformers: Part 1](https://aws-oss.beachgeek.co.uk/1i1) and the creatively titled part two, [Set up a text summarization project with Hugging Face Transformers: Part 2](https://aws-oss.beachgeek.co.uk/1i2) - I wonder if anyone is working on a GPT-3 model for creating titles ;-D! [hands on]

![architecture overview](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2022/03/09/ML-7391-image002.png)

**Quarkus**

Quarkus offers Java developers the capability of building native images based on GraalVM. Joan Bonilla shares how to integrate the Quarkus framework with AWS Lambda functions, using the AWS Serverless Application Model (AWS SAM) in this post, [Deploy Quarkus-based applications using AWS Lambda with AWS SAM](https://aws-oss.beachgeek.co.uk/1i6) [hands on]

**Kubernetes**

A couple of note worthy posts this week.

First up we have Jonathan Katz with the post, [Deploy Amazon RDS databases for applications in Kubernetes](https://aws-oss.beachgeek.co.uk/1i8) that walks you through deploying Jira, into a Kubernetes cluster provided by Amazon EKS, using Amazon RDS for PostgreSQL as the database. [hands on]

Following that we have a post that describes how you can send events from your Kubernetes cluster to a Slack channel using BotKube. BotKube is a messaging bot for monitoring and debugging Kubernetes clusters. Elamaran Shanmugam, Jayaprakash Alawala, and Re Alvarez-Parmar have collaborated on this post, [Streaming Kubernetes Events in Slack](https://aws-oss.beachgeek.co.uk/1i7), to show you how. [hands on]

![architecture for botkube](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2022/03/21/botkube-architecture.jpg)

**Other posts worth checking out**

* [How to re-platform and modernize Java web applications on AWS](https://aws-oss.beachgeek.co.uk/1i4) shows you how to use an open source project shared in [last weeks newsletter](https://dev.to/aws/aws-open-source-news-and-updates-105-38ch) that helps simplify the steps to re-platform a simple contact management Java application running on an open-source Tomcat application server

[architecture for modernising java apps](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2021/12/09/Image1.png)

* [Schema and code validator for Oracle to Amazon RDS for PostgreSQL or Amazon Aurora PostgreSQL migration](https://aws-oss.beachgeek.co.uk/1i5) walks you through an automated way to validate Oracle and PostgreSQL schema differences
* [Allowing external users to securely and directly upload files to Amazon S3](https://aws-oss.beachgeek.co.uk/1hy) demonstrate how you can build a modern web application to securely upload multiple files directly to Amazon Simple Storage Service (Amazon S3) using AWS Amplify

### Quick updates

**Amazon Corretto**

Amazon Corretto 18 is now generally available. This version supports the latest Java feature release OpenJDK 18 and is available on Linux, Windows, and macOS. OpenJDK 18 offers a new Internet-Address resolution capability, a Simple Web Server, an updated Vector API, a new @snippet Tag for JavaDoc, a new implementation of Core Reflection, a change to UTF-8 as the default character set (charset) of the standard Java APIs, a second iteration of the foreign memory API, advancements in pattern matching for switch statements, and the deprecation of finalisation.

Read more about these in the announcement, [Amazon Corretto 18 is now generally available](https://aws-oss.beachgeek.co.uk/1hx) as well as [this tweet from OpenJDK](https://aws-oss.beachgeek.co.uk/1ic)

**AWS GameKit**

AWS GameKit is a new open source solution that allows game developers to deploy and customise game backend features directly from Unreal Engine. AWS GameKit comes with AWS CloudFormation templates for each feature that follows AWS Solution Architect designs. AWS GameKit also comes with an integration code between the game backend features and Unreal Engine. 

AWS GameKit is for game developers looking to build AWS-powered game features directly from Unreal Engine with just a few clicks. With this release, developers have access to four game backend features: Identity and Authentication, Achievements, Game State Cloud Saving, and User Gameplay Data. AWS GameKit uses AWS CloudFormation templates to provision and connect all the necessary AWS resources together into a cohesive solution to power these features. Each feature follows the AWS well-architected framework to provide a secure, high-performing, resilient, and efficient infrastructure deployment that is fully customisable and runs in the developer's own AWS account.

AWS GameKit also provides Unreal Engine Blueprints, C++ code, libraries, documentation, and sample UIs for each of the four game features. The provided AWS CloudFormation templates automatically configure cloud resources that allows game developers to programmatically apply AWS best practices with common abstractions. This leads to the rapid creation of cloud-connected game features without being an AWS expert.

**Proton for Terraform Open Source**

Following on from this [Tweet from Rafael Alvarez](https://aws-oss.beachgeek.co.uk/1hw), the support for Terraform in Proton is now GA.

AWS Proton support for defining infrastructure in HashiCorp Configuration Language (HCL) and provisioning infrastructure using Terraform Open Source is now generally available in all regions where Proton is available. Platform teams can now define AWS Proton templates using Terraform modules, in addition to CloudFormation. AWS Proton leverages the customer-managed Terraform automation to provision or update the infrastructure. Customers can use Terraform as their infrastructure definition and provisioning tool, and AWS Proton keeps modules that are used consistently up to date. This generally available launch includes support for BitBucket repositories for infrastructure management, and improved messaging across the service to further clarify the status of provisioning.

**AWS Amplify**

AWS Amplify announces the new @mapsTo GraphQL directive, enabling developers to iterate and rename their GraphQL models without worrying about data migration. The AWS Amplify CLI is a command line toolchain that helps frontend developers create app backends in the cloud. With Amplify’s GraphQL Transformer, developers can configure their backend data model using the GraphQL Schema Definition Language, and Amplify CLI automatically transforms the schema into a fully functioning GraphQL API with its underlying database tables.

Before today, developers were required to manually export and migrate data when making changes to their GraphQL model names. Customers can now use the @mapsTo directive to rename the client-facing GraphQL model and retain the underlying DynamoDB table data. Amplify CLI, under the hood, will remap the new GraphQL model name to the original underlying DynamoDB tables.

### Videos of the week

**AWS Genomics CLI**

The AWS Genomics CLI (or AGC) removes all the grunt work involved in setting up bioinformatics pipelines to run in the cloud. We know that Snakemake, Cromwell, NextFlow and miniWDL all work happily in the cloud on AWS Batch, but AGC means you don't have to know to set all that stuff up - it does it for you. You can have completely separate tool chains using completely different workflow languages all running at the same time, on the same infrastructure (if you like), sharing data and tooling.

Brendan Bouffler and Lee Pang from the dev team that built this shows how it works, and - most importantly - how easy it is to get productive. Zero to hero in less than 30 mins - it's really impressive. 

{{< youtube 30cfBPdzykA >}}

### Events for your diary

> If you have an event you want me to publish here, please contact me and I will include it in this listing. 

**Getting started with AWS Amplify**
**March 28th, 3pm GMT**

Join Eddie Jaoude and Matt Auerbach in this [live session on You Tube](https://aws-oss.beachgeek.co.uk/1ib) where Matt will demonstrate how to deploy a React app with authentication using AWS Amplify


**Building an Open Data Lakehouse with Presto, Hudi, and AWS S3**
**March 29th, 10am PT**

In this 90 minute hands on-virtual lab that will walk you through how to build an Open Data Lakehouse stack with Presto, Apache Hudi, and AWS S3.

If you want to learn more about these open source projects, this looks like the perfect opportunity. Check it out and [register on their registration page](https://aws-oss.beachgeek.co.uk/1ep).

**GitOpsCon Europe**
**May 17th, Valencia Spain**

GitOpsCon Europe is designed to foster collaboration, discussion, and knowledge sharing on GitOps. This event is aimed at audiences that are new to GitOps as well as those currently using GitOps within their organisation. Get connected with others that are passionate about GitOps. Learn from practitioners about pitfalls to avoid, hurdles to jump, and how to adopt GitOps in your cloud native environment.

The event is vendor-neutral and is being organised by the CNCF GitOps Working Group. Topics include getting started with GitOps, scaling and managing GitOps, lessons learned from production deployments, technical sessions, and thought leadership.

Read more about this from the official page [here](https://events.linuxfoundation.org/gitopscon-europe/).

**CDK Day**
**May 26th - Virtual**

This is a community organised event about AWS CDK, cdktf, projen and cdk8s. This will be third year they run this event, and if the previous two are anything to go by, this will be essential viewing - live streamed via You Tube. Check out and register for the event over at their home page at [https://www.cdkday.com/](https://www.cdkday.com/)

**OpenSearch**
**Every Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting - Feb2022](https://aws-oss.beachgeek.co.uk/1az)


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)