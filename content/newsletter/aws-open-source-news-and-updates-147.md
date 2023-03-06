---
title: 'AWS open source newsletter #147'
date: '2023-03-06'
tags : [ oss-newsletter, aws open source, Kubernetes, OpenSearch, Ubuntu, Vault, FreeRTOS, AWS SAM, MySQL, MariaDB, PostgreSQL, AWS Lambda Powertools, Debezium, Apache Kafka, Kafka Connect, Apache Spark, Apache Hudi, DeltaStreamer, Apicurio Registry, Apache Iceberg, FFMpeg, Prometheus, Babelfish for Amazon Aurora PostgreSQL, Redis, Mastadon, Amazon EMR]

---

## March 6th, 2023 - Instalment #147

**Welcome**

Welcome to edition #147 of the AWS open source newsletter, featured in the [latest episode of Build on Open Source](https://www.twitch.tv/videos/1754262947). This week we have new projects such as "metahub" and "savings-estimator" that we looked at in closer detail on the Build on Open Source livestream, "aws-iot-core-credential-provider-session-helper" a Python library to help simplify working with AWS IoT, "traffic-inspection-architectures-aws-cloud-wan" code that provides examples of different network architectures and how to do traffic inspection, "neptune-export" a tool to help you export your data in Amazon Neptune, "aws-organizations-tool" a command line tool to help you configure AWS Organisations, "sagemaker-external-repo-access" a nice reference architecture for Amazon Sagemaker, "aws-cdk-cfn-hook" a Python CDK app that will get you up and running quickly working with Cloudformation template hooks, and more!

Also covered in this edition is content on a number of popular open source technologies, including Kubernetes, OpenSearch, FreeRTOS, AWS Lambda Powertools, Debezium, Apache Kafka, Kafka Connect, Apache Spark, Apache Hudi, DeltaStreamer, Apicurio Registry, Apache Iceberg, FFMpeg, Prometheus, Babelfish for Amazon Aurora PostgreSQL, Redis, Mastadon, and more!

**Feedback**

Please please please take 1 minute to [complete this short survey](https://pulse.buildon.aws/survey/PJRTOUMK) and get some exclusive content as a thank you.

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes: Gary Stafford, Dhiraj Thakur, Rajdip Chaudhuri, Corry Haines, Tulip Gupta, Dennis Calhoun, Amir Khairalomoum, James McIntyre, Daniel Gross, Jimmy Ray, Emin Alemdar, and Toni de la Fuente.

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution.*

#### Tools

**metahub**

[metahub](https://aws-oss.beachgeek.co.uk/25c) is an AWS Security Finding Format (ASFF) security context enrichment and command line utility for AWS Security Hub. Using MetaHub, you can enrich your security findings with your context to use that context for filtering, deduplicating, grouping, reporting, automating, suppressing, or updating and enrichment directly in AWS Security Hub. MetaHub interacts with reading/writing from AWS Security Hub API or directly from ASFF files. You can combine these sources as you want to enrich your findings further.

![architecture of metahub tool](https://github.com/gabrielsoltz/metahub/blob/main/docs/imgs/diagram-metahub.drawio.png?raw=true)

Check out more details from [this Reddit thread](https://aws-oss.beachgeek.co.uk/2ke).

**savings-estimator**

[savings-estimator](https://aws-oss.beachgeek.co.uk/2kh) this is a native desktop application written in Go that allows you to estimate the cost savings you can achieve in your AWS account by converting your AutoScaling Groups to Spot instances. You can simulate various scenarios, such as to keep some of your instances as OnDemand in each group (maybe covered by Reserved Instances or Savings Plans), or only convert some of your AutoScaling Groups to Spot as part of a gradual rollout. You may use any mechanism to adopt Spot, such as applying the configuration yourself group by group as per your simulation. They also provide a helpful video to show you how you can get started. 

{{< youtube VXfCOXXtLwA >}}

**aws-iot-core-credential-provider-session-helper**

[aws-iot-core-credential-provider-session-helper](https://aws-oss.beachgeek.co.uk/2kf) this package provides an easy way to create a refreshable Boto3 Session using the AWS IoT Core credential provider. Needs Python version 3.8 to 3.11, and some of the features include:

* Automatic refresh of Boto3 credentials through requests to the AWS IoT Core credential provider. No need to manage or maintain refresh times.
* Uses the underlying AWS CRT Python bindings for querying the credential provider instead of the Python standard library. This provides support for both certificate and private keys as files or as environment variables.
* Extensible to using other TLS methods such as PKCS#11 hardware security modules (see Advanced section).
* Only requires four function calls to create a session helper, Boto3 session, Boto3 client, and then client API calls.

**traffic-inspection-architectures-aws-cloud-wan**

[traffic-inspection-architectures-aws-cloud-wan](https://aws-oss.beachgeek.co.uk/2kg) this repository contains code (in AWS CloudFormation and Terraform) to deploy several inspection architectures using AWS Cloud WAN - with AWS Network Firewall as inspection solution. The use cases covered are 1/ Centralized Outbound, 2/ East/West traffic, with both Spoke VPCs and Inspection VPCs attached to AWS Cloud WAN, 3/ East/West traffic, with both Spoke VPCs and Inspection VPCs attached to AWS Transit Gateway and peered with AWS Cloud WAN, and 4/ East/West traffic, with Spoke VPCs attached to a peered AWS Transit Gateway and Inspection VPCs attached to AWS Cloud WAN. The documentation provides nice architectural diagram that outline each of these use cases, a description of what is inspected, and some sample output.

![sample output for traffic-inspection](https://github.com/aws-samples/traffic-inspection-architectures-aws-cloud-wan/blob/main/images/east_west.png?raw=true)

**neptune-export**

[neptune-export](https://aws-oss.beachgeek.co.uk/2ki) is a command line tool that exports Amazon Neptune property graph data to CSV or JSON, or RDF graph data to Turtle. The repo provides details of how you can also deploy this as a service within your environment.

**aws-organizations-tool**

[aws-organizations-tool](https://aws-oss.beachgeek.co.uk/2kk) orgtool is a configuration management tool set for AWS Organizations written in python. This tooling enable the configuration and management of AWS Organization with code. This might be useful as you transition from ClickOps to automation via infrastructure as code. Check the docs for more details on how you might do this.

### Demos, Samples, Solutions and Workshops

**sagemaker-external-repo-access**

[sagemaker-external-repo-access](https://aws-oss.beachgeek.co.uk/2kj) the goal of this solution is to demonstrate the deployment of AWS CodeSuite Services (i.e., CodeBuild, CodePipeline) to orchestrate secure MLOps access to external package repositories in a data science environment configured with multi-layer security. Detailed documentation as well as links to a supporting blog post you can read to help you get started.

**mlops-sagemaker-github-actions**

[mlops-sagemaker-github-actions](https://aws-oss.beachgeek.co.uk/2hv) similar to the previous post, this repo is an example of MLOps implementation using Amazon SageMaker and GitHub Actions. The code helps you to build a solution that automates a model-build pipeline that includes steps for data preparation, model training, model evaluation, and registration of that model in the SageMaker Model Registry. The resulting trained ML model is deployed from the model registry to staging and production environments upon the approval.

![architecture of mlops on sagemaker](https://github.com/aws-samples/mlops-sagemaker-github-actions/blob/main/img/Amazon-SageMaker-GitHub-Actions-Architecture.png?raw=true)

**aws-cdk-cfn-hook**

aws-cdk-cfn-hook this solution demonstrates how to create, update, and deploy CloudFormation hooks through a CI/CD pipeline using AWS Cloud Development Kit as Infrastructure as Code. It leverages AWS CDK (Python) to deploy: an AWS CodeCommit source repo that contains hook handlers, hook schema and other parameters to create the hook and its related configuration; an AWS CodeBuild stage to package and deploy the hook; and an AWS CodePipeline.

![architecture of cdk-cfn-hook solution](https://github.com/aws-samples/aws-cdk-cfn-hook/blob/main/images/CFN_Hook.jpg?raw=true)

**aws-textract-cdk-commercial-acord**

[aws-textract-cdk-commercial-acord](https://github.com/aws-samples/aws-textract-cdk-commercial-acord) This repo contains all the code required to do an IDP solution on AWS from document splitting, classification to extraction. The repo use a sample commercial acord data set.

**rails-lambda-handler**

[rails-lambda-handler](https://github.com/aws-samples/rails-lambda-handler) This repository includes and AWS Lambda handler function that launches Ruby on Rails (or other Rack compliant) application, as well as a sample application so you can see how this works.

### AWS and Community blog posts

**Open Source Data Lakes**

Back with another epic blog post, Gary Stafford provides a gloriously detailed walk through together with supporting sample code, that takes a look at how you can combine a number of open source projects, together with AWS services to create a real time transactional data lake. From the post:

> Red Hat’s Debezium, Apache Kafka, and Kafka Connect will be used for change data capture (CDC). In addition, Apache Spark, Apache Hudi, and Hudi’s DeltaStreamer will be used to manage the data lake.  

Gary's posts are essential reading, so head on over to [Building Data Lakes on AWS with Kafka Connect, Debezium, Apicurio Registry, and Apache Hudi](https://aws-oss.beachgeek.co.uk/2ko) and dive right on into the lake! [hands on]

![architecture of real time transactional data lake on aws using open source software](https://github.com/garystafford/cdc-hudi-data-lake-demo/blob/main/diagram.png?raw=true)

**Apache Iceberg**

In the post, [Build a real-time GDPR-aligned Apache Iceberg data lake](https://aws-oss.beachgeek.co.uk/2kv), Dhiraj Thakur and Rajdip Chaudhuri show you  how you can use the Iceberg table format on Athena to implement GDPR use cases like data deletion and data upserts as required, when streaming data is being generated and ingested through AWS Glue streaming jobs in Amazon S3. [hands on]

![architecture of how you can build a real time GDPR apache iceberg solution for your data lake](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2023/01/28/image001-4.png) 

**Mastodon**

If you have been looking for a way to host your own Mastadon instance, then why not take a look at this blog post from Corry Haines. In [Deploying Mastodon on AWS](https://aws-oss.beachgeek.co.uk/2kn) shares the lessons he learned on the way to hosting his own instance. Essential reading this week.

**FFMPEG**

FFmpeg is an open source tool commonly used by media technology companies to encode and transcode video and audio formats. In [Run Open Source FFMPEG at Lower Cost and Better Performance on a VT1 Instance for VOD Encoding Workloads](https://aws-oss.beachgeek.co.uk/2kp), Tulip Gupta and Dennis Calhoun share how you can optimise how your run FFMpeg on AWS using VT1 instance types on Amazon EC2 instances.

**Other posts and quick reads**

* [Build a GNN-based real-time fraud detection solution using the Deep Graph Library without using external graph storage](https://aws-oss.beachgeek.co.uk/2kw) provides a step-by-step process for training and evaluating a Relational Graph Convolutional Network (RGCN) model for real-time fraud detection using the open source Deep Graph Library [hands on]
* [Reduce Amazon EMR cluster costs by up to 19% with new enhancements in Amazon EMR Managed Scaling](https://aws-oss.beachgeek.co.uk/2kt) provides an overview of enhancements in EMR Managed Scaling which show improved cluster utilisation (by up to 15 percent) and a reduction in cluster costs [hands on]

![reducing amazon emr cluster costs graph](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2023/02/27/BDB-2751_image_001-new.png)

* [Using OpsWatch to Create a Single Pane of Prometheus Metrics from Multiple Non-Native Sources](https://aws-oss.beachgeek.co.uk/2ks) explores how to integrate CloudWatch and other Amazon Web Services (AWS) data sources into a typical container and Prometheus-based monitoring world

![overview of single pane of prometheus metrics](https://d2908q01vomqb2.cloudfront.net/77de68daecd823babbb58edb1c8e14d7106e83bb/2023/01/24/OpsWatch-Arvato-Systems-4.png)

* [Automated Application Failover Across Availability Zones with Floating/Virtual IP on Amazon EKS](https://aws-oss.beachgeek.co.uk/2ku) looks at design patterns that let you fail-over your EKS based applications seamlessly to another AZ while using same IP addresses, in an automated way, with no change needed in the application code [hands on]
* [SaaS Data Isolation with Dynamic Credentials Using HashiCorp Vault in Amazon EKS](https://aws-oss.beachgeek.co.uk/2kx) examines a solution for implementing multi-tenant SaaS data isolation with dynamic credentials using HashiCorp Vault in an Amazon EKS environment [hands on]

![architecture for saas data isolation on EKS using HashiCorp Vault](https://d2908q01vomqb2.cloudfront.net/77de68daecd823babbb58edb1c8e14d7106e83bb/2023/02/06/HashiCorp-Vault-EKS-SaaS-4.png)

**Case Studies**

* [How Wiz used Amazon ElastiCache to improve performance and reduce costs](https://aws-oss.beachgeek.co.uk/2kq)  is a great case study on how they were able to improved overall application performance, reduce pressure on their database, and then right-size the database instances, to save their overall TCO.

![graph of performance enhancements Redis](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2023/03/01/06-reduced-load.png)

* [Rebura: Accelerate SQL Server database modernization with Babelfish for Amazon Aurora PostgreSQL](https://aws-oss.beachgeek.co.uk/2kr) explores how Rebura helps customers modernise their SQL Server on AWS using Babelfish for Amazon Aurora PostgreSQL.

![process overview of how to modernise sql server](https://d2908q01vomqb2.cloudfront.net/8effee409c625e1a2d8f5033631840e6ce1dcb64/2023/02/27/babelfishrebura3-1024x466.png)

### Quick updates

**AWS Lambda Powertools**

AWS Lambda Powertools, an open-source developer library, now supports .NET to help you incorporate Well-Architected Serverless best practices into your .NET Lambda function code as early and as fast as possible. Lambda Powertools for .NET is used when developing code for the .NET 6 Lambda runtime. To dive deeper into the GA announcement, read the post from Amir Khairalomoum, [Introducing AWS Lambda Powertools for .NET](https://aws-oss.beachgeek.co.uk/2km).

![dashboard from aws console powered by aws lambda powertools](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2023/02/24/AWS-X-Ray-waterfall-trace-view-1024x663.png)

**OpenSearch**

OpenSearch 2.6.0 is now available, with a new data schema built to OpenTelemetry standards that unlocks an array of future capabilities for analytics and observability use cases. This release also delivers upgrades for index management, improves threat detection for security analytics workloads, and adds functionality for visualization tools, machine learning (ML) models, and more. Read the full announcement from James McIntyre, [Introducing OpenSearch 2.6](https://aws-oss.beachgeek.co.uk/2kl).

In related news, Krishna Kondaka, Asif Sohail Mohammed, and David Venable collaborated on the post, [Announcing Data Prepper 2.1.0](https://aws-oss.beachgeek.co.uk/2ky) that shared news about the latest release of Data Prepper, an open source tool that that accepts, filters, transforms, enriches, and routes data into your OpenSearch environment.

**PostgreSQL**

Amazon Relational Database Service (Amazon RDS) for PostgreSQL now supports the latest major version PostgreSQL 15. New features in PostgreSQL 15 include the SQL standard "MERGE" command for conditional SQL queries, performance improvements for both in-memory and disk-based sorting, and support for two-phase commit and row/column filtering for logical replication. The PostgreSQL 15 release also adds support for new extension pg_walinspect, and server-side compression with Gzip, LZ4, or Zstandard (zstd) using pg_basebackup. 

**MySQL**

Amazon Aurora MySQL-Compatible Edition 3 (with MySQL 8.0 compatibility) now supports MySQL 8.0.26. In addition to several security enhancements and bug fixes, MySQL 8.0.26 includes several changes, such as enhanced tablespace file segment page configuration and new aliases for certain identifier names. For more details, please review Aurora MySQL 3 and MySQL 8.0.26 release notes.

**MariaDB**

Amazon Relational Database Service (Amazon RDS) for MariaDB now supports MariaDB minor versions 10.6.12, 10.5.19, 10.4.28 and 10.3.38. We recommend that you upgrade to the latest minor versions to fix known security vulnerabilities in prior versions of MariaDB, and to benefit from the numerous bug fixes, performance improvements, and new functionality added by the MariaDB community.

**AWS SAM**

Serverless application developers can now define multiple destinations when integrating AWS services with AWS Serverless Application Model (AWS SAM) connectors. Previously, SAM customers needed to create a SAM connector definition for every source and destination pair. For example, if a AWS::Serverless::Function needed to interact with three SNS topics using identical permissions, three SAM connectors would need to be defined for each connection from the function to each topic. 

### Videos of the week

**FreeRTOS**

Join Daniel Gross, Developer Advocate within the AWS IoT team as he shows you how you can debug FreeRTOS within VSCode using QEMU. Check out the links as you can follow along the blog post and supporting code. Very cool.

{{< youtube l2GmlDN_SPo >}}


**Improving Secret Management in K8s with ESO**

Managing secrets in Kubernetes can be a challenge. One of the optimal approaches to storing and making use of sensitive data in your clusters is to incorporate the use of external centralized secrets managers. Centralized secrets managers usually offer encryption of data at rest and expose an API for lifecycle management operations of your secrets. So how do you integrate secrets from external providers and securely expose them in your cluster? In this episode, your host Jimmy Ray is joined by Emin Alemdar who walks through the External Secrets Operator (ESO) and some good practices for managing secrets in Kubernetes. 

{{< youtube FityN80Cpto >}}


**OpenSearch**

This short video covers how to install and configure OpenSearch 2.5.0 with OpenSearch Dashboards On Ubuntu.

{{< youtube NL-B2Y508lU >}}


**Build on Open Source**

Episode two of Build on Open Source streamed live last Friday, 3rd March. Derek and myself covered newsletters #146 and this one, #147. We had a special guest, Toni de la Fuente who walked us through his open source projects prowler. **[prowler](https://aws-oss.beachgeek.co.uk/2ct)** helps keep your AWS environments secure by running audits against well know security compliance checks, and Toni walked us through a demo of it in action. I highly recommend you watch it if you can, as this project is awesome! You can watch it on [replay here](https://www.twitch.tv/videos/1754262947)

For those unfamiliar with this show, Build on Open Source is where we go over this newsletter and then invite special guests to dive deep into their open source project. Expect plenty of code, demos and hopefully laughs. We have put together a playlist so that you can easily access all (eight) of the episodes of the Build on Open Source show. [Build on Open Source playlist](https://aws-oss.beachgeek.co.uk/24u)

# Events for your diary

If you are planning any events in 2023, either virtual, in person, or hybrid, get in touch as I would love to share details of your event with readers. 

**Build on Open Source**
**March 17th, twitch.tv/aws**

The third episode of Build on Open Source features special guest AWS Community Builder John Preston who will be showing us compose-x, an open source tool to help you deploy applications using Amazon ECS (and other AWS services). Really looking forward to this one as John is a super start open source developer.

See you there on [twitch.tv/aws](https://twitch.tv/aws), Friday 3rd at 9am GMT, 10am CET.

**Power Up your Kubernetes**
**March 15th, AWS Office Zurich, Switzerland**

If you want to improve architecture, scaling and monitoring of your applications that run on AWS Elastic Kubernetes Service, this event is for you. During this event you will learn to scale Kubernetes applications with Karpenter, monitor your workloads, and build SaaS architectures for Kubernetes. 

Find out more and save your place by heading over to the registration page, [Power up your Kubernetes on AWS](https://aws-oss.beachgeek.co.uk/2jd)

**Everything Open**
**March14-15th Melbourne, Australia**

A new event for the fine folks in Australia. Everything Open is running for the first time, and the organisers (Linux Australia) have decided to run this event to provide a space for a cross-section of the open technologies communities to come together in person. Check out the [event details here](https://aws-oss.beachgeek.co.uk/2ds). The CFP us currently open, so why not take a look and submit something if you can.

**FOSSASIA**
**April 13th-15th, Singapore**

FOSSASIA Summit 2023 returns as an in-person and online event, taking place from Thursday 13th April to Saturday 15th April at the Lifelong Learning Institute in Singapore. 

If you are interested in attending in person, or virtually, find out more about the event at the [FOSSASIA Summit 2023 page](https://aws-oss.beachgeek.co.uk/2iq).

**Cortex**
**Every other Thursday, next one 16th February**

The Cortex community call happens every two weeks on Thursday, alternating at 1200 UTC and 1700 UTC. You can check out the GitHub project for more details, go to the [Community Meetings](https://aws-oss.beachgeek.co.uk/2h5) section. The community calls keep a rolling doc of previous meetings, so you can catch up on the previous discussions. Check the [Cortex Community Meetings Notes](https://aws-oss.beachgeek.co.uk/2h6) for more info.

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)

### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)

