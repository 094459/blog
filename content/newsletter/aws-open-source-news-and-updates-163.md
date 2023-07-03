---
title: 'AWS open source newsletter #163'
date: '2023-07-03'
tags : [ oss-newsletter, aws open source, Redis, ActiveMQ, OpenSearch, AWS SAM, Kubernetes, Apache Flink, Amazon Linux, Spring, AWS CDK, AWS Amplify, Steampipe, AWS Lambda Powertools ]

---
## July 3rd, 2023 - Instalment #163

Welcome to #163 of the AWS open source newsletter. As always, we search high and low for the best and latest open source content, and I think you will love what we have lined up this week. This weeks featured projects include a Cedar authorisation service and demo examples, a tool to help you find dangling DNS records, a new CLI for those using Amazon ECR, an accelerator for observability on AWS, a serverless web analytics solution (so good, that I implemented it myself), and several more projects.

Also featured is content on Redis, ActiveMQ, OpenSearch, AWS SAM, Kubernetes, Apache Flink, Amazon Linux, Spring, AWS CDK, AWS Amplify, Steampipe, and AWS Lambda Powertools. Head over to the Videos section to check out a link for last weeks Build on Live open source and AI, and finally check out events that are coming up and put them in your diary.

Also, be sure to check out the events section as there are a few events happening this week.

**Feedback**

Before you dive in however, I need your help!  Please please please take 1 minute to [complete this short survey](https://pulse.buildon.aws/survey/PJRTOUMK) and you will forever have my gratitude!

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes:  Ran Isenberg, Bob Tordella, Spot, Mo Malaka, Vacha Shah, Benoit Tellier, Suraj Narwade, Rehan van der Merwe, Aniruddha Biyanithat, Daniel Aniszkiewicz, Jared Evans, Chris Fregly and Antje Barth.

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution.*

#### Tools

**cedar-authorization-service**

[cedar-authorization-service](https://aws-oss.beachgeek.co.uk/2z3) is a lightweight, standalone server developed in Rust that is designed to evaluate and enforce access control policies written in Cedar, an open-source policy language developed by AWS. Creator Daniel Aniszkiewicz adds that whilst there is an official Cedar playground, this is a view-only mode for the Rust code, which means you can't edit the Rust code there. This project provides a playground where you can play around with both the Cedar policies and the Rust code. Check out Daniels blog post, the second in the series, [Authorization and Cedar: A New Way to Manage Permissions - Part II](https://aws-oss.beachgeek.co.uk/2z4) that looks at how you might use Cedar in a typical e-commerce use case.

**findmytakeover**

[findmytakeover](https://aws-oss.beachgeek.co.uk/2z5) is a tool from Aniruddha Biyanithat detects dangling DNS record in you cloud environment. It does this by scanning all the DNS zones and the infrastructure present within the configured cloud service provider either in a single account or multiple accounts and finding the DNS record for which the infrastructure behind it does not exist anymore rather than using wordlist. It can easily detect and report potential subdomain takeovers that exist. Make sure you check out the project README for full details, including limitations.

**cdk-aws-observability-accelerator**

[cdk-aws-observability-accelerator](https://aws-oss.beachgeek.co.uk/2z0) is a set of opinionated modules to help you set up observability for your AWS environments with AWS Native services and AWS-managed observability services such as Amazon Managed Service for Prometheus,Amazon Managed Grafana, AWS Distro for OpenTelemetry (ADOT) and Amazon CloudWatch. It provides curated metrics, logs, traces collection, cloudwatch dashboard, alerting rules and Grafana dashboards for your EKS infrastructure, Java/JMX, NGINX based workloads and your custom applications.

![cdk-aws-observability-accelerator open source architecture](https://raw.githubusercontent.com/aws-observability/cdk-aws-observability-accelerator/811ec42307d41f35f2fec95f2f2b8a20bddc7646/docs/images/CDK_Architecture_diagram.png)

**ecrctl**

[ecrctl](https://aws-oss.beachgeek.co.uk/2yz) is the latest project from AWS Community Builder Suraj Narwade, and one that I think I will most certainly be using a lot. Taking inspiration from kubectl, ecrctl provides a CLI tool for working with Amazon Elastic Container Registry (ECR). I guess the only remaining question is how exactly should you pronounce this tool!

**serverless-website-analytics**

[serverless-website-analytics](https://aws-oss.beachgeek.co.uk/2yx) is a fantastic project from AWS Hero Rehan van der Merwe that provides a very feature rich click stream analytics solution that you can easily integrate into your projects. I was so impressed I decided to ditch what I was using and switch over to this project, so the AWS open source newsletter is now getting its clickstream data using this tool. I put together a quick blog post, [Deploying a serverless web analytics solution for your websites](https://aws-oss.beachgeek.co.uk/2yy) to share my setup, but Rehan has put together detailed docs on how you can configure and tailor this to your own needs.

**cloud-seed**

[cloud-seed](https://aws-oss.beachgeek.co.uk/2z1) is a very minimal alternative to cloud-init. If you are not familiar with [cloud-init](https://aws-oss.beachgeek.co.uk/2z2), it is an open source package that bootstraps Linux images in a cloud computing environment. cloud-seed exists because it is often necessary to provide some "seed" data to an otherwise-ready-to-run image: some values should not be baked into the image due to them varying from server to server. It can set the hostname and write files based on directives provided in user data. The doc provides additional information as to what you can define. 

**OpenAPI-AWS-Decorator**

[OpenAPI-AWS-Decorator](https://aws-oss.beachgeek.co.uk/2z7) this tool from Jared Evans will decorate an Open API v3 document with specific x-amazon- OpenAPI syntax. The README provides a useful example of how you can get started with this tool.

### Demos, Samples, Solutions and Workshops

**data-science-on-aws**

[data-science-on-aws](https://aws-oss.beachgeek.co.uk/2z8) this workshop shows AWS users how to use Amazon SageMaker and other associated services to build, train, and deploy generative AI models. These labs go through data science topics such as data processing at scale, model fine-tuning, real-time model deployment, and MLOps practices all through a generative AI lens. This workshop is based on the O'Reilly Book, "Data Science on AWS", from my colleagues Chris Fregly and Antje Barth. Essential reading, so if you are looking for a book recommendation or something to add to your wish list, this might be the one!

![overview of book cover](https://github.com/aws-samples/data-science-on-aws/blob/main/img/book_full_color_sm.png?raw=true)

**llm-hosting-container**

[llm-hosting-container](https://aws-oss.beachgeek.co.uk/2za) This repository contains Dockerfile and associated resources for building and hosting containers for large language models, specifically the HuggingFace Text Generation Inference (TGI) container. Watch this repo to keep up to date as others are added.

**llm-apps-workshop**

[llm-apps-workshop](https://aws-oss.beachgeek.co.uk/2z9) this repository provides the source code for Large Language Model (LLM) based applications that include inference, generating embeddings, question answer (zero-shot and few-shot learning, prompt engineering), retrieval augmented generation (RAG) and domain adapted fine-tuning. The repo links to a walk through blog post to help guide you through this.

**Introduction to Terraform on AWS**

[Introduction to Terraform on AWS](https://aws-oss.beachgeek.co.uk/2z6) this is a new workshop that will help you gain hands-on experience in creating and managing AWS resources using Terraform and leverage Terraform best practices.


### AWS and Community blog posts

**AWS Lambda Powertools**

AWS Hero and regular contributor to this newsletter Ran Isenberg has put together another great post, [Serverless API Idempotency with AWS Lambda Powertools and CDK](https://aws-oss.beachgeek.co.uk/2zf). In this post Ran helps you get to grips idempotency, looking at what it is and why it's essential, using a sample serverless "orders" service to bring it to life. Expect plenty of open source goodness with AWS CDK, and AWS Lambda Powertools for Python. Make sure you check this post out. [hands on]

![overview of serverless idempotency](https://static.wixstatic.com/media/2e76fb_0e5c02a10f5c4a418732f84b640a5f6a~mv2.png/v1/fill/w_1254,h_495,al_c,q_90,enc_auto/2e76fb_0e5c02a10f5c4a418732f84b640a5f6a~mv2.png)

**Steampipe**

Steampipe is an open source CLI to instantly query cloud APIs using SQL. In [Using Steampipe Relationship Graphs to Navigate Cloud Resources on AWS](https://aws-oss.beachgeek.co.uk/2zc), Spot and Bob Tordella follow up on previous posts, this time showing you how you can navigate between resources using the new relationship graph capabilities added to Steampipe AWS Insights dashboards. [hands on]

![example steampip relationship graph diagram](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2023/06/23/IAM-user.png)

**AWS Amplify**

AWS Amplify is an open source project that lets frontend web and mobile developers easily build, ship, and host full-stack applications on AWS. The AWS Amplify team recently announced a brand new way to recognise and reward the hard work and dedication of our open source community contributors:The Amplify Badge Program. Mo Malaka has put together more details in his post, [New: Introducing the AWS Amplify Badge Program](https://aws-oss.beachgeek.co.uk/2zd) that looks at what these badges look like and how this will work.

**OpenSearch**

Vacha Shah and Benoit Tellier have put together [Improving JSON parsing performance in opensearch-java](https://aws-oss.beachgeek.co.uk/2ze), that looks at how Benoit  and his team at Linagora, contributing to the Apache James project, we able to identify and address a performance issue in the OpenSearch Java client using benchmark tools and flame graphs, in collaboration with the OpenSearch community. 

![flame graph example in opensearch](https://opensearch.org/assets/media/blog-images/2023-04-10-opensource-perf/flame2.png)

**Other posts and quick reads**

* [Announcing watchOS and tvOS Support on AWS Amplify Library for Swift](https://aws-oss.beachgeek.co.uk/2zh) is a hands on guide on how to build an app for the iOS, macOS, watchOS, and tvOS platforms using a single Swift project powered by Amplify Library for Swift [hands on]

![overview of swift amplify and ios and watchos](https://d2908q01vomqb2.cloudfront.net/0a57cb53ba59c46fc4b692527a38a87c78d84028/2023/06/27/Screenshot-2023-06-27-at-2.48.48-PM-1024x623.png)

* [Deploy a serverless ML inference endpoint of large language models using FastAPI, AWS Lambda, and AWS CDK](https://aws-oss.beachgeek.co.uk/2zi)  shows you how to easily deploy and run serverless ML inference by exposing your ML model as an endpoint using FastAPI, Docker, Lambda, and Amazon API Gateway (and automated using AWS CDK) [hands on]
* [Approach to migrate Spring Cloud microservices applications to Amazon EKS](https://aws-oss.beachgeek.co.uk/2zj) explains how you can migrate microservices from Spring Cloud to Amazon EKS [hands on]

![spring cloud to eks migration](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2023/06/01/MIGMOD-174-EKSArchitecture-scaled.jpg)

**Case Studies**

* [Life360’s journey to a multi-cluster Amazon EKS architecture to improve resiliency](https://aws-oss.beachgeek.co.uk/2zg) looks at how Life360 improved our resiliency by implementing a multi-cluster Amazon EKS architecture.

![overview of Life360 architecture](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2023/06/21/Availability-Zone.png)

### Quick updates

**Apache Flink**

Customers can now use Apache Flink 1.15 with Amazon Kinesis Data Analytics Studio to perform ad hoc queries to quickly inspect data streams and build and run stream processing applications in minutes. Kinesis Data Analytics Studio allows you to query data streams in real time, and more easily build and run stream processing applications using standard SQL, Python, and Scala in an interactive notebook. Studio notebooks are powered by Apache Zeppelin and use Apache Flink as the stream processing engine. Studio notebooks seamlessly combine these technologies to make advanced analytics on data streams accessible to developers of all skill sets.

**Amazon Linux**

Support for UEFI Secure Boot on Amazon Linux instances is now available. Starting with AL2023.1, customers can now use Secure Boot on Amazon Linux instances to verify the digital signature of all boot components. Secure Boot is a feature of UEFI that builds on EC2’s long-standing secure boot process, and provides additional defense-in-depth that helps customers secure software from threats that persist across reboots. It ensures that EC2 instances run authentic software by verifying the digital signature of all boot components, and halts the boot process if signature verification fails. Starting today, customers who want to use this capability on EC2, can use this capability on Amazon Linux instances. Secure boot is supported on all AWS Nitro based AL2023 instances with UEFI capability. To get started with secure boot on AL2023 instances see[ the documentation here](https://aws-oss.beachgeek.co.uk/2zb). 

**AWS Serverless Application Model (SAM)**

The AWS Serverless Application Model (SAM) Command Line Interface (CLI) announces the launch of remote invoke command which enables developers to quickly invoke their AWS Lambda functions deployed to the AWS cloud. The AWS SAM CLI is a developer tool that makes it easier to build, test, package, and deploy serverless applications. Customers can now use the SAM CLI to test a Lambda function with a simple command sam remote invoke. This command takes an event payload and Lambda logical id as input to invoke the Lambda function, then outputs the response. It supports multiple invocation modes such as response streaming, asynchronous invoke, dry run and request-response. Previously, customers had to use AWS Console or AWS CLI to test their Lambda functions. With this launch, SAM CLI users can use this feature along with sam sync command to speed up the build-deploy-test iteration loop. This feature is available with SAM CLI version 1.88.0+.

**ActiveMQ**

Amazon MQ now supports cross-region data replication for ActiveMQ brokers on Amazon MQ. This feature allows you to build regionally resilient messaging applications using continuous asynchronous message replication from a primary broker to a replica broker in a standby AWS region with a few clicks, eliminating the need to use third-party tools or custom code to replicate data between regions. Cross-region data replication enables messages to be replicated across ActiveMQ brokers in different regions with robust monitoring metrics. In case of a regional failure, you can trigger a failover quickly and confidently from the primary to standby region, allowing you to resume operations. 

Cross-region data replication pricing consists of cross-region data replication charges, plus broker instance and storage charges for both brokers. Data transfer between the primary AWS Region and a secondary AWS Region is billed based on the data transfer pricing of the applicable AWS Regions. 

**Redis**

Amazon MemoryDB for Redis is now in scope for FedRAMP Moderate in the US East (Ohio), US East (N. Virginia), US West (N. California), and US West (Oregon) Regions. You can now use MemoryDB to build applications for workloads that are subject to FedRAMP Moderate compliance. In addition to achieving FedRAMP Moderate authorization, MemoryDB is also HIPAA eligible, HITRUST, ISO certified, SOC, and PCI DSS compliant.

### Videos of the week

**Build on Open Source & AI**

If you missed the latest Build on Live! event last week, fear not. The latest instalment was all about open source and machine learning, with Falcon40 and Hugging Face featured. Check out the [show notes here](https://aws-oss.beachgeek.co.uk/2zl)

{{< youtube nI7UaHJbm5Q >}}

**Build on Open Source**

For those unfamiliar with this show, Build on Open Source is where we go over this newsletter and then invite special guests to dive deep into their open source project. Expect plenty of code, demos and hopefully laughs. We have put together a playlist so that you can easily access all (sixteen) of the episodes of the Build on Open Source show. [Build on Open Source playlist](https://aws-oss.beachgeek.co.uk/episodes).

We are currently planning the third series - if you have an open source project you want to talk about, get in touch and we might be able to feature your project in future episodes of Build on Open Source.

# Events for your diary

If you are planning any events in 2023, either virtual, in person, or hybrid, get in touch as I would love to share details of your event with readers. 

**OpenSearchCon**
**Seattle, September 27-29, 2023**

Registration is now open source OpenSearchCon. Check out this post from Daryll Swager, [Registration for OpenSearchCon 2023 is now open!](https://aws-oss.beachgeek.co.uk/2zk) that provides you with what you can expect, and resources you need to help plan your trip.

**CDK Day, 2023**
**Online, 29th September 2023**

Back for the fourth instalment, this Community led event is a must attend for anyone working with infrastructure as code using the AWS Cloud Development Kit (CDK). It is intended to provide learning opportunities for all users of the CDK and related libraries. The CFP is open, so if you have some ideas for some talks then make sure you check that section out. Also, this year they are accepting talks in Espanol! Woohoo, love it!

Check more at the website, [CDK Day](https://aws-oss.beachgeek.co.uk/fr) 

**Cortex**
**Every other Thursday, next one 16th February**

The Cortex community call happens every two weeks on Thursday, alternating at 1200 UTC and 1700 UTC. You can check out the GitHub project for more details, go to the [Community Meetings](https://aws-oss.beachgeek.co.uk/2h5) section. The community calls keep a rolling doc of previous meetings, so you can catch up on the previous discussions. Check the [Cortex Community Meetings Notes](https://aws-oss.beachgeek.co.uk/2h6) for more info.

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)

### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)