---
title: 'AWS open source newsletter #146'
date: '2023-02-27'
tags : [ oss-newsletter, aws open source, Kubernetes, Amazon EKS, Porting Advisor for Graviton, PostgreSQL, AWS Amplify, AWS ParallelCluster, AWS SAM, AWS CDK, CoreDNS, Amazon EMR, Terraform, Linux, Apache Hudi, Grafana, Prometheus, RabbitMQ, MariaDB, MySQL]

---

## Feb 27th, 2023 - Instalment #146

Welcome to edition #146 of the AWS open source newsletter. This week we have another great selection of brand new, shiny open source projects for you to practice your four freedoms on. Some of the projects this week include "aws-lambda-web-adapter" that will help you build portable Lambda functions, "aws-marketplace-cli" if you want to escape the GUI when working with AWS Marketplace, this one is for you, ""otel-config-validator" helps you sanity check your configuration files, "aws-serverless-openai-chatbot-demo" build a personal assistance powered by ChatGPT, "drone-video-analysis" if you have wanted to use AI services to process your drone video footage, check this project out, "mask-words-in-image" a nice command line tool to quick mask data based on your needs, and many more cool projects.

We also have content featuring some of your favourite open source topics, including Kubernetes, Porting Advisor for Graviton, PostgreSQL, AWS Amplify, AWS ParallelCluster, CoreDNS, Amazon EMR, Terraform, Linux, Apache Hudi, Grafana, Prometheus, RabbitMQ, and more!

**Feedback**

Please please please take 1 minute to [complete this short survey](https://pulse.buildon.aws/survey/PJRTOUMK) and get some exclusive content as a thank you.

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes: Uri Segev, Sebastian Grimberg, Hugh Carson, Andrew Keller, Joel Hans, Kevin Lewin, Hareesh Iyer, Bill Pfeiffer, Vikram Venkataraman, Sathish Arumugam, Manish Pandey, Joerg Woehrle and Mohamed Othman, Ryan Doty, Vishal Manan, Arun Chandapillai, Imaya Kumar Jagannathan, Mengdi Chen, Nikita Buldakov, Matt Vaughn, Matthew Bonig, Eric Johnson, and Evgeny Karasik.

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution.*

#### Tools

**aws-lambda-web-adapter**

[aws-lambda-web-adapter](https://aws-oss.beachgeek.co.uk/2jv) allows developers to build web apps (http api) with familiar frameworks (e.g. Express.js, Next.js, Flask, SpringBoot, and Laravel, anything speaks HTTP 1.1/1.0) and run it on AWS Lambda. The same docker image can run on AWS Lambda, Amazon EC2, AWS Fargate, and local computers. Uri Segev has put together a blog post, [Developing portable AWS Lambda functions](https://aws-oss.beachgeek.co.uk/2k2) providing some best practices for developing portable Lambda functions that allow you to easily port your code to containers if you later choose to.

![architecture of aws lambda web adapter](https://github.com/awslabs/aws-lambda-web-adapter/blob/main/docs/images/lambda-adapter-overview.png?raw=true)

**palace**

[palace](https://aws-oss.beachgeek.co.uk/2ju) which stands for PArallel LArge-scale Computational Electromagnetics, is an open-source, parallel finite element code for full-wave 3D electromagnetic simulations in the frequency or time domain, using the MFEM finite element discretisation library. I will be honest, I am not entirely sure what that means. However, the supporting blog post [AWS releases open-source software Palace for cloud-based electromagnetics simulations of quantum computing hardware](https://aws-oss.beachgeek.co.uk/2jt), from Sebastian Grimberg, Hugh Carson, and Andrew Keller helped me better understand what this project can do, explains why we released this project, and takes a look at examples of electromagnetics simulations for quantum hardware design - super interesting read!

![palace blog post illustration](https://d2908q01vomqb2.cloudfront.net/5a5b0f9b7d3f8fc84c3cef8fd8efaaa6c70d75ab/2023/02/21/pcj-2-1024x452.png)

**kubefirst**

[kubefirst](https://aws-oss.beachgeek.co.uk/2k3) if you are looking to get started with Kubernetes, then this project is going to be of interest. kubefirst is a cloud provisioning tool. With simple setup and two CLI commands, we create a Kubernetes cluster managed with automated Infrastructure as Code, GitOps asset management and application delivery, secrets management, a sample application delivered to development, staging, and production, and more.

![kubefirst architecture overview](https://github.com/kubefirst/kubefirst/blob/main/images/provisioning.png?raw=true)

Check out their supporting blog post, [What does it mean to have a cloud native application?](https://aws-oss.beachgeek.co.uk/2k5), where Joel Hans introduces you to some of the concepts you need to learn as you begin your cloud native journey.

**aws-marketplace-cli**

[aws-marketplace-cli](https://aws-oss.beachgeek.co.uk/2k4) provides a friendlier way to manage your AWS Marketplace products from the command line and based on the configuration persisted in source control. If you currently interact with the AWS Marketplace via the GUI and have been looking for a cli solution, this is the project for you.

**aws-parallelcluster-ui**

[aws-parallelcluster-ui](https://aws-oss.beachgeek.co.uk/2jo) this project is a front-end for AWS Parallel Cluster, that allows you to quickly and easily create HPC cluster in AWS using AWS ParallelCluster UI. This UI uses the AWS ParallelCluster 3.x API to Create, Update and Delete Clusters as well as access, view logs, and build Amazon Machine Images (AMI's). Check out the Videos of the Week section to see this in action.

![AWS Parallel Cluster UI demo](https://docs.aws.amazon.com/images/parallelcluster/latest/ug/images/ui-image.png)

**aws-scps-with-terraform**

[aws-scps-with-terraform](https://aws-oss.beachgeek.co.uk/2ka) this repo helps you setup a template to easily create and apply AWS Service Control Policies (SCPs) with Terraform. Users can drag + drop json templates in the correct directory in policies. The module will then do the heavy lifting and apply it to the specified OUs.

**otel-config-validator**

[otel-config-validator](https://aws-oss.beachgeek.co.uk/2jw) is an experimental OpenTelemetry Collector Configuraton Validator that is currently a work in progress (i.e. please give us feedback if you try this project out). The AWS Distro for OpenTelemetry (ADOT) provides a secure production-ready distribution of OpenTelemetry (OTel) that allows for instrumentation and collecting of metrics and traces. The ADOT collector can be used to collect and export telemetry data. Within the collector, observability pipelines are defined using a YAML configuration file. When creating these configuration files,  there is a potential for syntactic error in the YAML file which would prevent your pipeline from operating effectively. Having a telemetry pipeline non-functional may cause gaps in observability that can lead to application downtime. The goal of this project is to assist with error-checking OTEL configuration files during development so potential mis-configurations can be addressed before causing issues. Read more about this in the excellent post from Kevin Lewin, [Validating OpenTelemetry Configuration Files with the otel-config-validator](https://aws-oss.beachgeek.co.uk/2jx) [hands on]

![architecture of otel-config-validator](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2023/02/22/ADOT-collector-architecture.png)

**mask-words-in-image**

[mask-words-in-image](https://aws-oss.beachgeek.co.uk/2k9) is a command line tool that can mask words in an image file. User specifies which words should be masked, it can be any combinations of the following three types: Regular expressions, keywords, and PII (Personally Identifiable Information). Under the hood, it use the Text Detection capability in Amazon Rekognition or AWS Textract to detect the texts in the image, then use Amazon Comprehend to detect PII entities in texts.

### Demos, Samples, Solutions and Workshops

**aws-serverless-openai-chatbot-demo**

[aws-serverless-openai-chatbot-demo](https://aws-oss.beachgeek.co.uk/2k6) with ChatGPT capturing the imagination of everyone and bringing artificial intelligence into our daily conversations, this project capitalises on that interest by building a web front end that uses the OpenAI APIs to create a personal assistant type application. Check out the README.md for a much more detailed overview of what this does.

![aws serverless openai chatbot demo architecture](https://github.com/aws-samples/aws-serverless-openai-chatbot-demo/blob/main/assets/architecture-v2.png?raw=true) 

**drone-video-analysis**

[drone-video-analysis](https://aws-oss.beachgeek.co.uk/2k7) This repository contains an application that lets you ingest live drone streams and process them in real time. The solution has three big components; ingestion, processing of the video stream, and ML analysis of the video stream. This might be useful for processing real-time video streams from drones and other video sources. The solution can be used to detect objects in the video stream, and send alerts to the user when an object is detected. All I need now is to get my hands on a drone!

![architecture of drone video analysis architecture](https://github.com/aws-samples/drone-video-analysis/blob/main/docs/solution-overview.png?raw=true)

**aws-ugc-moderation-sample**

[aws-ugc-moderation-sample](https://aws-oss.beachgeek.co.uk/2k8) a nice sample repository showing you how you can implement a video content moderation process for user generated video content using AWS Step Functions. It makes use of Rekognition Moderation capabilities to scan video content for inappropriate images. The rationale behind this code sample is to block UGC from progressing further in the analysis pipeline, so that customers don't perform AI/ML workloads on inappropriate content.

![usg moderation sample architecture](https://github.com/aws-samples/aws-ugc-moderation-sample/blob/main/assets/architecture.png?raw=true)

**amazon-rekognition-face-detection-video-stream**

[amazon-rekognition-face-detection-video-stream](https://aws-oss.beachgeek.co.uk/2kc) this sample demonstrates how to create a Face Recognition through Stream Video application with a serverless architecture using Python CDK.

![overview of architecture detecting faces](https://camo.githubusercontent.com/a30e32247f2f9af062dce11134caa45d55ffad32b761636fa8560cef120cdb1a/68747470733a2f2f643139356b686f307479716a70682e636c6f756466726f6e742e6e65742f41727175697465747572612d426c6f67706f73742e64726177696f2e706e67)

**amazon-athena-queries-via-aws-lambda-cdk**

[amazon-athena-queries-via-aws-lambda-cdk](https://aws-oss.beachgeek.co.uk/2kb) this repository shows you how to build a solution where Amazon Athena SQL queries can be executed via AWS Lambda using the Boto3 API. Additionally, this architecture can be fully deployed using AWS CDK and is designed to fit into a larger serverless architecture. The CDK stack configures and deploys a Lambda function with the appropriate IAM permissions to make Athena SQL queries on an S3 bucket. The query results can then be found in an S3 output bucket specified by the user. This architecture can be used if Athena queries need to be run on a regular, scheduled basis.

### AWS and Community blog posts

**Kubernetes**

In the post, [Using Azure Active Directory to authenticate to Amazon EKS](https://aws-oss.beachgeek.co.uk/2jm), Hareesh Iyer shows you how to use Azure AD to authenticate users to Amazon EKS clusters using Amazon EKS OIDC authentication. Haressh walks you through the setup steps required on Azure portal and Amazon EKS to create this integration. [hands on]

![overview of active direction integration with amazon eks](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2023/02/16/Picture10-1.png)

Also published last week was this post, [Deploying Amazon EKS Windows managed node groups](https://aws-oss.beachgeek.co.uk/2jz) where Bill Pfeiffer provides step-by-step instructions on how to get started with Windows-based managed node groups, for those customers running containerised Windows workloads. [hands on]

**CoreDNS**

CoreDNS is a flexible, extensible Domain Name System (DNS) server that can serve as a Kubernetes cluster DNS, but DNS throttling issues can be challenging to identify and troubleshoot. In the post, [Monitoring CoreDNS for DNS throttling issues using AWS Open source monitoring services](https://aws-oss.beachgeek.co.uk/2jq) Vikram Venkataraman, Sathish Arumugam, and Manish Pandey provide some guidance on how you can tackle this problem using open source tools such as Grafana and Prometheus. [hands on]

![architecture of solution for managing coreDNS](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2023/02/17/cloudops_1194_1.png)

**AWS CDK**

AWS Cloud Development Kit and its Construct concept can help to ensure team independence and agility even though multiple teams (for example, an application development team, and an infrastructure team) work together to bring a new version of an application into production. If this is something that sounds interesting to you, check out the post, [Improve collaboration between teams by using AWS CDK constructs](https://aws-oss.beachgeek.co.uk/2js), where Joerg Woehrle and Mohamed Othman dive deep into the topic.

![overview of cdk enable cross team collaboration](https://d2908q01vomqb2.cloudfront.net/7719a1c782a1ba91c031a682a0a2f8658209adbf/2023/02/01/Flow_Publish_New_App_Version.png)

**Porting Advisor for Graviton**

The Porting Advisor for Graviton project was featured in Newsletter #144, and is a tool that helps you assess your workloads for moving to the AWS Graviton (arm based) instances. In the blog post, [Using Porting Advisor for Graviton](https://aws-oss.beachgeek.co.uk/2k1), Ryan Doty and Vishal Manan walk you through using this tool to help you quantify the amount of work that is required to port an application, reducing the iterative process of identifying and resolving source code and library dependencies. [hands on]

**Other posts and quick reads**

* [Babelfish for Aurora PostgreSQL Performance Testing Results](https://aws-oss.beachgeek.co.uk/2jh) shares results for Babelfish for Aurora PostgreSQL performance testing using the HammerDB database benchmarking tool
* [Setting up Babelfish for Aurora PostgreSQL for performance testing using HammerDB](https://aws-oss.beachgeek.co.uk/2jk) looks at how the benchmarking was setup from the previous post
* [Improve logical replication performance in Amazon Aurora PostgreSQL with the new write-through cache](https://aws-oss.beachgeek.co.uk/2jl) discusses the logical replication write-through cache for Amazon Aurora PostgreSQL and how using the write-through cache to improve read performance for your cluster

![graph of write through cache performance impact on replication on postgressql](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2023/02/14/DBBLOG-2812-image005.jpg)

* [Configure Kerberos authentication for Amazon RDS for PostgreSQL without joining an Active Directory domain](https://aws-oss.beachgeek.co.uk/2jr) demonstrates how to configure a Linux client outside of active directory domain to connect using Kerberos authentication to an Amazon RDS for PostgreSQL or Amazon Aurora PostgreSQL-Compatible Edition [hands on]

![architecture of kerberos on rds postgresql](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2023/02/08/DBBLOG-2506-Architect.png)

* [Using Kinesis Agent for Linux to stream application logs in AppStream 2.0](https://aws-oss.beachgeek.co.uk/2jp) walks you through a solution to push application logs from AppStream 2.0 streaming instances running Linux to a Kinesis Firehose delivery stream [hands on]
* [Accelerating Spark workloads on Amazon EMR with Windjammer’s Spark plugin](https://aws-oss.beachgeek.co.uk/2jy) shows you how to implement the Windjammer Spark plugin on your EMR cluster to achieve performance improvements and cost reduction on your Spark workloads [hand on]
* [Manage multiaccount and multi-Region infrastructure in Terraform using AWS Cloud9](https://aws-oss.beachgeek.co.uk/2k0) provides a hands on guide on how to deploy a multi-Region infrastructure with multiple accounts with Terraform infrastructure as code using AWS Cloud9 [hands on]

![terraform using cloud9 architecture overview](https://d2908q01vomqb2.cloudfront.net/b7eb6c689c037217079766fdb77c3bac3e51cb4c/2023/02/21/Cloud9-blog-arch-diag-4-1024x486.png)

**Case studies**

* [How Ruparupa gained updated insights with an Amazon S3 data lake, AWS Glue, Apache Hudi, and Amazon QuickSight ](https://aws-oss.beachgeek.co.uk/2ji) show how Ruparupa implemented an incrementally updated data lake to get insights into their business using Amazon Simple Storage Service (Amazon S3), AWS Glue, Apache Hudi, and Amazon QuickSight. The post goes into some of the benefits Ruparupa gained after the implementation.

![architecture overview of case study](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2023/02/03/Picture2.png)

### Quick updates

**Kubernetes**

Kubernetes 1.25 introduced several new features and bug fixes, and AWS announced last week that you can now use Amazon EKS and Amazon EKS Distro to run Kubernetes version 1.25. You can create new 1.25 clusters or upgrade your existing clusters to 1.25 using the Amazon EKS console, the eksctl command line interface, or through an infrastructure-as-code tool.

Some things to note in this release are the removal of PodSecurityPolicy (PSP), the graduation of Pod Security Admission to stable, and enhancements to cluster authentication. If you are using PSP in your cluster, then before upgrading your cluster to version 1.25, you must migrate your PSP to the built-in Kubernetes Pod Security Standards or to a policy-as-code solution to avoid interruptions and to protect your workloads.

Diver deeper into this release by checking out the post, [Amazon EKS now supports Kubernetes version 1.25](https://aws-oss.beachgeek.co.uk/2jj)

**Grafana**

Amazon Managed Grafana now supports inbound network access control that helps you to restrict user access to your Grafana workspaces. Amazon Managed Grafana is a fully managed service for Grafana, a popular open-source analytics platform that enables you to query, visualise, and alert on your metrics, logs, and traces. With this launch, you have granular security controls over the rollout of Grafana workspaces by defining customer-managed prefix lists and VPC endpoints to help you restrict the inbound network traffic that can reach your Grafana workspaces. 

Amazon Managed Grafana supports two modes for user and host access of your Grafana workspace: open access and restricted access. Open access is the default access setting for Grafana workspaces when there are no VPC endpoints or managed prefix list restrictions to reach your Grafana workspace URL; however, users must still authenticate with the configured identity provider(s) in order to log in to the workspace. Restricted access mode enables you to specify the inbound network traffic that is allowed to reach your workspace. To restrict access, you can configure prefix lists to specify IP address ranges from which users and hosts can reach your Grafana workspace. You can also create an interface VPC endpoints to allow AWS resources such as Amazon EC2 instances to access the Amazon Managed Grafana API to manage resources, or you can use a VPC endpoint as part of limiting network access to your Amazon Managed Grafana workspaces.

Arun Chandapillai, Imaya Kumar Jagannathan, and Mengdi Chen have collaborated on this post, [Announcing inbound network access control in Amazon Managed Grafana](https://aws-oss.beachgeek.co.uk/2jn) that dives deeper into this new capability.

![overview of inbound network access fro grafana](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2023/02/06/Architecture.jpg)

**RabbitMQ**

Amazon MQ is a managed message broker service for Apache ActiveMQ and RabbitMQ that makes it easier to set up and operate message brokers in the cloud. Amazon MQ now supports the AWS Key Management Service (AWS KMS) to create and manage keys for at-rest encryption of customer data for RabbitMQ brokers. Amazon MQ handles the encryption and decryption seamlessly, so you don’t have to change your applications to access your data. When you create a broker, you can now select the KMS key used to encrypt your data from the following three options: a KMS key in the Amazon MQ service account, a KMS key in your account that Amazon MQ creates and manages, or a KMS key in your account that you create and manage. In addition to encryption at rest, all data transferred between Amazon MQ and client applications is securely transmitted using TLS/SSL.

**AWS ParallelCluster**

AWS ParallelCluster 3.5 is now generally available and expands your choices and flexibility by adding the graphical user interface for AWS ParallelCluster to help you set up, monitor, and manage High Performance Computing (HPC) clusters on AWS. Updates with 3.5 include: enhancements designed to improve visibility for cluster errors during compute node bootstrap, execution of pre and post install script, enhancements designed to improve reliability for compute node reboot, support of long cluster names up to 40 characters, and programmatic interface you can use to access AWS ParallelCluster via a Python library

**MariaDB and MySQL**

Announced last week, Amazon Relational Database Service (Amazon RDS) for MariaDB and MSQL now support Cross-Region Automated Backups. This feature extends the existing Amazon RDS backup functionality, giving you the ability to setup automatic replication of system snapshots and transaction logs from a primary AWS Region to a secondary AWS Region. The Amazon RDS Cross-Region Automated Backups feature enables additional disaster recovery capabilities for mission critical databases by providing you the ability to restore your database to a specific point in time within your backup retention period. This allows you to quickly resume operations in the event that the primary AWS Region becomes unavailable. 

### Videos of the week

**SAM & Friends - AWS SAM with AWS CDK**

Join Matthew Bonig, Eric Johnson, and Evgeny Karasik as they discuss using AWS SAM and AWS CDK together to build serverless applications.

{{< youtube 2n28LUSMvGs >}}


**ParallelCluster UI**

AWS ParallelCluster has a new UI for designing, deploying, and managing clusters on AWS. It's packed with all the features you'd imagine, and is built to ensure you spend more time designing your clusters to suit your workloads and no time at all wrestling with YAML files or manually tweaking cluster operations. Nikita Buldakov and Matt Vaughn stopped by the HPC Tech Shorts studio to show us how it works and take us for a drive.

{{< youtube FAfVbiTVk24 >}}


**Build on Open Source**

We kicked off the new season of Build on Open Source, where we covered newsletter #142 through to #144 and had a special guest, Valter Silva who walked us through his open source projects aws-terraform-dev-container and aws-code-habbits. These projects are aimed at helping scale developer productivity, ensure consistency in setting up development environments, and apply current good practices to your development. You can watch it on [replay here](https://www.twitch.tv/videos/1740656009)

For those unfamiliar with this show, Build on Open Source is where we go over this newsletter and then invite special guests to dive deep into their open source project. Expect plenty of code, demos and hopefully laughs. We have put together a playlist so that you can easily access all (eight) of the episodes of the Build on Open Source show. [Build on Open Source playlist](https://aws-oss.beachgeek.co.uk/24u)

# Events for your diary

If you are planning any events in 2023, either virtual, in person, or hybrid, get in touch as I would love to share details of your event with readers. 

**Build on Open Source**
**March 3rd, twitch.tv/aws**

The second episode of Build on Open Source features special guest Toni de la Fuente who will be showing us prowler, an open source tool to help you assess your Cloud workloads against hundreds of controls covering CIS, PCI-DSS, ISO27001, GDPR, HIPAA, FFIEC, SOC2, AWS FTR, ENS and custom security frameworks.

See you there on [twitch.tv/aws](https://twitch.tv/aws), Friday 3rd at 9am GMT, 10am CET.

**OpenSearch Unplugged: Observability and Search**
**March 7th, 9am - 5pm EST, Better.com; 3 World Trade Center 57th Floor, New York, NY 10007**

Join us for this by-invitation-only event for AWS customers. The session will be from Opensource OpenSearch Engineering Leaders and senior Specialists from Amazon OpenSearch Service team members. The event will be full day, hands-on session with two labs. Find out more and reserve your spot by heading over to the registration page, [OpenSearch Unplugged: Observability and Search](https://aws-oss.beachgeek.co.uk/2kd)

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

