---

title: 'AWS open source news and updates #119'
date: '2022-07-01'
tags : [ oss-newsletter, aws open source, Redis, AWS Toolkit for Visual Studio, RStudio, Amazon Corretto, Terraform, Linux, Hugging Face, Syne Tune, Apache Airflow, AWS CDK, OpenSearch, Apache Iceberg, Pulumi, Lustre, Amazon EMR, Apache Spark, PostgreSQL]

---

## July 1st, 2022 - Instalment #119

Welcome to regular and new readers alike, to the AWS open source newsletter episode #119.

This week we feature more new open source projects, such as "cdk-bill-bot", a tool that can help you reduce AWS bill surprises, "steampipe-mod-aws-perimeter" helps you look for resources that are publicly accessible, "aws-cloudformation-diagrams" is a nice visualisation tool for CloudFormation users, "aws-swagger-ui" a project to help you set up Swagger UI for API Gateway, "kinesis-hot-shard-advisor" a handy tool that helps you identify whether you have hot key or hot shard issues on your Kinesis data streams, and many more.

We also have blog posts, tutorials and videos on topics that include RStudio, Amazon Corretto, Terraform, Linux, Hugging Face, Syne Tune, Apache Airflow, OpenSearch, Apache Iceberg, Pulumi, Lustre, Apache Spark, PostgreSQL and many more. Finally, make sure you check out the events section for the latest open source events, there are some great events coming up over the next week.

**Feedback**

At Amazon we work backwards from our customers, and one of the ways we do that is collecting data to help us know what is important and what we should focus on. Please could you [complete this simple](https://eventbox.dev/survey/8G7HRWY), anonymous survey. The first 25 will get an AWS $25 credit code.

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created. 

So thank you to the following open source heroes: David Tippett, Steven Hillon, Adam Bien, Lerna Ekmekcioglu, Jack Iu, Arun Km, Rohit Bhosale, Abhishek Ray, Jeremy Cowan, Akshit Khanna, Arun Thangaraj, Chaitanya Varma Mudundi, Sekar Srinivasan and Christian Bonzelet


### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution.*

#### Tools

**cdk-bill-bot**

[cdk-bill-bot](https://aws-oss.beachgeek.co.uk/1v8) this project from Christian Bonzelet enables AWS customers to proactively monitor their infrastructure costs and identify unforeseen expenses in a timely manner. Bill wants to prevent AWS customers from receiving bad surprises in their monthly bill. Therefore he addresses two primary problem areas, first, cost history is not monitored on a regular basis, and second, basic cost optimisation best practices are not setup.

As Christian points out in his README, this is an alpha stage project so use at your own risk and beware of potentially breaking changes.

**steampipe-mod-aws-perimeter**

[steampipe-mod-aws-perimeter](https://aws-oss.beachgeek.co.uk/1v7) the latest open source project from the fine folk at Turbot, this project provides an AWS perimeter checking tool that can be used to look for resources that are publicly accessible, shared with untrusted accounts, have insecure network configurations, and more.

![example warning message](https://raw.githubusercontent.com/turbot/steampipe-mod-aws-perimeter/main/docs/images/aws_perimeter_public_access_output.png)

**aws-cloudformation-diagrams**

[aws-cloudformation-diagrams](https://aws-oss.beachgeek.co.uk/1v9) another visualisation project, this time allowing you to generate dynamic diagram of AWS Cloudformation template from YAML file. Using Python, you will be able to quickly create some pdf architecture from your CloudFormation templates in no time at all.

**aws-icons-for-plantuml**

[aws-icons-for-plantuml](https://aws-oss.beachgeek.co.uk/1va) PlantUML is an open-source tool allowing users to create diagrams from a plain text language. This repository contains images, sprites, macros, and other includes for Amazon Web Services (AWS) services and resources. You can use this repository to create PlantUML diagrams with AWS components. All elements are generated from the official AWS Architecture Icons and when combined with PlantUML and the C4 model, are a great way to communicate your design, deployment, and topology as code.

![example plantuml diagram for architecture](https://camo.githubusercontent.com/f3d5cd42fa288fc38fea8a3c7bf13cf588443c1cb3ef5004c4b868d5d8812c9f/687474703a2f2f7777772e706c616e74756d6c2e636f6d2f706c616e74756d6c2f70726f78793f6964783d30267372633d68747470732533412532462532467261772e67697468756275736572636f6e74656e742e636f6d2532466177736c6162732532466177732d69636f6e732d666f722d706c616e74756d6c2532467631332e302532466578616d706c657325324653657175656e636525323532302d2532353230546563686e6963616c2e70756d6c)

**aws-swagger-ui**

[aws-swagger-ui](https://aws-oss.beachgeek.co.uk/1v3) this repo shows how to set up Swagger UI for API Gateway. It uses Lambda for serving Swagger UI.

![architecture of setting up Swagger UI](https://github.com/aws-samples/aws-swagger-ui/blob/main/architecture.png?raw=true)

**kinesis-hot-shard-advisor**

[kinesis-hot-shard-advisor](https://aws-oss.beachgeek.co.uk/1v2) The Amazon Kinesis Hot Shard Advisor is a CLI tool that simplifies identifying whether you have hot key or hot shard issues on your Kinesis data streams. The tool can also identify whether you are hitting the shard level throughput limit per-second basis.

![example output of khs tool](https://github.com/awslabs/kinesis-hot-shard-advisor/blob/main/images/samplereport.png?raw=true)

**simpleiot-cli**

[simpleiot-cli](https://aws-oss.beachgeek.co.uk/1v1) last week I shared the SimpleIOT SDK. This week we have the command-line-interface (CLI) for the SimpleIOT framework. SimpleIOT abstracts out IoT device connectivity and hides the underlying details so you can focus on your application's unique features.

### Demos, Samples, Solutions and Workshops

**eventbridge-events-to-vpc**

[eventbridge-events-to-vpc](https://aws-oss.beachgeek.co.uk/1v0) shows you how to send EventBridge events to a private endpoint in a VPC using a Lambda function to relay events. This solution deploys the Lambda function connected to the VPC and uses IAM permissions to enable EventBridge to invoke the Lambda function. In this solution, you set up an example application with an EventBridge event bus, a Lambda function to relay events, a Flask application running in an EKS cluster to receive events behind an Application Load Balancer (ALB), and a secret stored in Secrets Manager for authenticating requests. This application uses EKS and Secrets Manager to demonstrate sending and authenticating requests to a containerized workload, but the same pattern applies for other container orchestration services like ECS and your preferred secret management solution.

![architecture of solution for eventbridge to vpc](https://github.com/aws-samples/eventbridge-events-to-vpc/blob/main/diagrams/solution-architecture.jpg?raw=true)

**step-functions-workflows-collection**

[step-functions-workflows-collection](https://aws-oss.beachgeek.co.uk/1uz) this repo contains Step Functions workflows that shows how to orchestrate multiple services into business-critical workflows with minimal code. You can use these workflows to help develop your own projects quickly.

**aws-test-automation-for-devops-using-aws-cdk**

[aws-test-automation-for-devops-using-aws-cdk](https://aws-oss.beachgeek.co.uk/1uy) this sample code shares methods and patterns for applying test automation in CI/CD of AWS in order to transform DevOps through test automation. With this sample, you can implement test automation directly through practice.

![architecture of solution for test automation](https://github.com/aws-samples/aws-test-automation-for-devops-using-aws-cdk/blob/main/docs/images/0.0.architecture.png?raw=true)

**aws-sso-configuration-automation**

[aws-sso-configuration-automation](https://aws-oss.beachgeek.co.uk/1ux) this project accelerate AWS Single Sign-On (SSO) implementation using AWS CDK. This CDK program allows you to conveniently define your own permission sets and assignments without the need to tediously create your own AWS CloudFormation templates for your AWS SSO deployment minimising the risk of human misconfigurations.

### AWS and Community blog posts

**Spring Boot**

Gary Stafford has put together his latest blog post, [Developing Spring Boot Applications for Querying Data Lakes on AWS](https://aws-oss.beachgeek.co.uk/1v4). In this post Gary explores how to build an example Java Spring Boot RESTful Web Service that allows end-users to query data stored in a data lake on AWS. The RESTful Web Service will access data stored as Apache Parquet in Amazon S3 through an AWS Glue Data Catalog using Amazon Athena. The service will use Spring Boot and the AWS SDK for Java to expose a secure, RESTful Application Programming Interface (API). As always, must read post this week. [hands on]

![architecture of solution](https://miro.medium.com/max/1400/1*kOUJkq5ILsZfM6rWW784vw.png)

**Amazon Corretto**

Check out [Using Amazon Corretto (OpenJDK) for lean, fast, and efficient AWS Lambda Applications](https://aws-oss.beachgeek.co.uk/1uh) where Adam Bien discusses how you can launch large, monolithic applications on top of AWS Lambda, showing that they perform well and are cost effective. He also introduces running Amazon Corretto on ARM64 using Lambda’s Graviton2-based offering. Finally Adam demonstrates how you can use Amazon Corretto with Quarkus to build micro services quickly and at low cost. Must read for Java developers this week. [hands on]

**Pulumi**

Pulumi is an open-source Infrastructure as Code (IaC)tool, similar to Terraform, with a key difference between Pulumi and Terraform is that Pulumi lets you choose a number of different general-purpose programming languages whereas Terraform has a domain-specific language called Hashicorp Configuration Language (HCL). Abhishek Ray has put together this blog post, [How to use Pulumi and Python to create an EC2 instance](https://aws-oss.beachgeek.co.uk/1ur) to show you the basics and help you get started [hands on]

**Apache Iceberg**

Apache Iceberg is an open table format, originally designed at Netflix in order to overcome the challenges faced when using existing data lake formats. It is getting a lot of interest, and this week we have a couple of blog posts that will help you get to know this open source technology in more detail.

First up we have Chaitanya Varma Mudundi from RedHat, who provides a nice overview of Apache Iceberg and some ideas of how you can run this on AWS in his post, [Apache Iceberg: An Introduction from Rackspace on Running the New Open Table Format on AWS](https://aws-oss.beachgeek.co.uk/1uu)

![apache iceberg reference diagram](https://d2908q01vomqb2.cloudfront.net/77de68daecd823babbb58edb1c8e14d7106e83bb/2022/06/22/Rackspace-Apache-Iceberg-1.png)

Following that we have the post, [Build a high-performance, ACID compliant, evolving data lake using Apache Iceberg on Amazon EMR](https://aws-oss.beachgeek.co.uk/1uv) from Sekar Srinivasan. In this post, Sekar discuss' the modern data lake requirements and the challenges—including support for ACID transactions and concurrent writers, partition and schema evolution—that come with these, before showing how Apache Iceberg solves these challenges. There is a sample notebook that you can use to follow along, to see how you can run Apache Iceberg on Amazon EMR using the AWS Glue Data Catalog as the metastore, and query the data using Athena. [hands on]

**Terraform**

Very nice post, [Multi-Region Terraform Deployments with AWS CodePipeline using Terraform Built CI/CD](https://aws-oss.beachgeek.co.uk/1ul) from Lerna Ekmekcioglu and Jack Iu where they demonstrate the best practice for multi-Region deployments using HashiCorp Terraform as infrastructure as code (IaC), and AWS CodeBuild , CodePipeline as continuous integration and continuous delivery (CI/CD) for consistency and repeatability of deployments into multiple AWS Regions and AWS Accounts. [hands on]

![diagram showing cicd flow](https://d2908q01vomqb2.cloudfront.net/7719a1c782a1ba91c031a682a0a2f8658209adbf/2022/06/18/devops_2021_2.png)

**Kubernetes**

A couple of posts this weeks for those of you who are interested or follow Kubernetes. First up we have Jeremy Cowan who writes, [Amazon EKS improves control plane scaling and update speed by up to 4x](https://aws-oss.beachgeek.co.uk/1um) and shares some of the insights around how AWS has been able to optimise and speed up the performance of the Amazon EKS control plane, with the aim of making the EKS user experience even better.

The second post is a hands on tutorial from Akshit Khanna and Arun Thangaraj, where you will leverage several AWS services, including AWS App Mesh, Amazon Route 53, and Amazon EKS, to run a resilient, highly available application in two different regions. Read on if this sounds like something you want to try, in [Run an active-active multi-region Kubernetes application with AppMesh and EKS](https://aws-oss.beachgeek.co.uk/1us)

![architecture of eks and app mesh tutorial](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2022/06/28/akshit1.png)

To round this section off, we have [Leverage AWS secrets stores from EKS Fargate with External Secrets Operator](https://aws-oss.beachgeek.co.uk/1v5) penned by Ryan Stebich. In this post, Ryan walks through using the External Secrets Operator on an Amazon EKS Fargate cluster to consume secrets stored in AWS Secrets Manager. [hands on]

![architecture of secrets manager on eks fargate](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2022/06/28/Screen-Shot-2022-03-27-at-7.29.52-AM-copy.png)

**Lustre**

Lustre is an open source type of parallel distributed file system, generally used for large-scale cluster computing. Arun Km and Rohit Bhosale show you how you can safeguard your data using FSx for Lustre’s encryption feature, in their post, [Protecting your high-performance file systems with Amazon FSx for Lustre](https://aws-oss.beachgeek.co.uk/1uq) [hands on]

![architecture of securing Lustre fs](https://d2908q01vomqb2.cloudfront.net/e1822db470e60d090affd0956d743cb0e7cdf113/2022/06/10/Data-protection-for-Amazon-FSx-for-Lustre-file-systems-use-case.jpg)

**Other posts you might like from the past week**

* [Hyperparameter optimization for fine-tuning pre-trained transformer models from Hugging Face](https://aws-oss.beachgeek.co.uk/1un) discusses hyperparameter optimisation for fine-tuning pre-trained transformer models from Hugging Face based on Syne Tune [hands on]

![illustration of fine tuning graphs](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2022/06/16/ML-9045-test_error_mrpc.png)

* [How to integrate Linux instances with AWS Gateway Load Balancer](https://aws-oss.beachgeek.co.uk/1ui) presents a sample handler that implements Linux virtual Layer 3 interfaces (using Linux’s TUN support, explained here) to handle the AWS Gateway Load Balancer connectivity.[hands on] 

![architecture of AGLB](https://d2908q01vomqb2.cloudfront.net/5b384ce32d8cdef02bc3a139d4cac0a22bb029e8/2022/05/13/gwlbtun-fig-1.png)

* [Use AWS Nitro Enclaves to perform computation of multiple sensitive datasets](https://aws-oss.beachgeek.co.uk/1uj) provides a walk through of how to build the Proof of Concept (POC) bidding service application I shared in [#118](https://dev.to/aws/aws-open-source-news-and-updates-118-12h4) [hands on]

![architecture of bidding service using AWS Nitro Enclaves](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2022/06/14/nitroenclaves_figure1-1024x780.png)

* [Archive and Purge Data for Amazon RDS for PostgreSQL and Amazon Aurora with PostgreSQL Compatibility using pg_partman and Amazon S3](https://aws-oss.beachgeek.co.uk/1uo) shares how you can efficiently use PostgreSQL’s native range partition to partition current (hot) data with pg_partman and archive historical (cold) data in Amazon S3
* [Automate Amazon RDS for PostgreSQL horizontal scaling and system integration with Amazon EventBridge and AWS Lambda](https://aws-oss.beachgeek.co.uk/1v6) provides a solution to automate horizontal scaling of your Amazon RDS for PostgreSQL environment using an event-driven architecture [hands on]
* [Disaster recovery considerations with Amazon EMR on Amazon EC2 for Spark workloads](https://aws-oss.beachgeek.co.uk/1ut) shows you how to architect your Amazon EMR environment for disaster recovery to maintain business continuity with minimum Recovery Time Objective (RTO) during Availability Zone failure or when your EMR cluster is inoperable [hands on]
* [Jenkins high availability and disaster recovery on AWS](https://aws-oss.beachgeek.co.uk/1up) shares the challenges to scale Jenkins for high availability (HA) and disaster recovery (DR) and how you can address these using AWS services [hands on]

![architecture of Jenkins HA and DR](https://d2908q01vomqb2.cloudfront.net/7719a1c782a1ba91c031a682a0a2f8658209adbf/2022/06/24/devops_2067_2-1024x729.png)

### Quick updates

**Transport Layer Security (TLS)**

To respond to evolving technology and regulatory standards for Transport Layer Security (TLS), we will be updating the TLS configuration for all AWS service API endpoints to a minimum of version TLS 1.2. This update means you will no longer be able to use TLS versions 1.0 and 1.1 with all AWS APIs in all AWS Regions by June 28, 2023. 

To find out more, read the post [TLS 1.2 to become the minimum TLS protocol level for all AWS API endpoints](https://aws-oss.beachgeek.co.uk/1uk)

**Redis**

Amazon MemoryDB for Redis is now a Payment Card Industry Data Security Standard (PCI DSS) compliant service. MemoryDB is a fully managed, Redis-compatible, in-memory database that provides low latency, high throughput, and durability at any scale. You can now use MemoryDB to store sensitive payment card data with low latency and high throughput for use cases such as payment processing, mobile wallet, and payment fraud prevention that are subject to PCI DSS.

**RStudio**

You can now bring your own development environment in a custom image to RStudio on Amazon SageMaker. RStudio on SageMaker is the industry’s first fully managed RStudio Workbench in cloud. You can quickly launch the familiar RStudio Integrated Development Environment (IDE), dial up and down the underlying compute resources without interrupting your work, and even switch to programming using Python on Amazon SageMaker Studio Notebooks. All your work, including code, datasets, repositories, and other artefacts are synchronised between the two environments. You can bring your current RStudio license to Amazon SageMaker at no additional charge to quickly get started.

RStudio on SageMaker already comes with a built-in image pre-configured with R programming and data science tools including SageMaker SDK, AWS CLI, AWS SDK, and Reticulate package for integration with Python-based interfaces. Starting today, you can register your own custom image with packages and tools of your choice, and make them available to all the users sharing the RStudio on SageMaker domain. Bringing your own custom image has several benefits. You can standardise and simplify the getting started experience for data scientists and developers by providing a starter base image, pre-configure the drivers required for connecting to data stores, or pre-install specialised data science software for your business domain.

Check out this blog post, [Use a custom image to bring your own development environment to RStudio on Amazon SageMaker for more details of how this will work](https://aws-oss.beachgeek.co.uk/1ug).

![architecture of rstudio blog post](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2022/06/29/rstudio-byoi-solution.png)

**AWS Toolkit for Visual Studio**

The [AWS Toolkit for Visual Studio](https://aws-oss.beachgeek.co.uk/f5) is an open source extension for Microsoft Visual Studio running on Microsoft Windows that makes it easier for developers to develop, debug, and deploy applications using Amazon Web Services, allowing you to get started faster and be more productive. Developers can now access Amazon CloudWatch Logs within Visual Studio using the AWS Toolkit for Visual Studio. Directly from the IDE, it is now possible to search and filter log groups, log streams, and events. Additionally, log groups can be accessed from their associated resources, and log events can be downloaded to a file.

The latest release of the toolkit includes several convenient CloudWatch logs features. Visual Studio users can list CloudWatch Log groups from the CloudWatch Logs node in the AWS Explorer. Individual log groups can be opened in a document tab, where you can view the log group’s streams, as well as export stream events to a local file. While viewing a log stream, you can search and filter log messages using keywords or phrases, such as "Exception" or "Error". You can also search using a time range, to see events that led up to and resulted from the error you were searching.

### Videos of the week

**AWS CDK**

Join my colleague in a recording of his user group meetup last week, where you will understand how you can implement Infrastructure as Code (IaC) and Continuous Integration and Continuous Deployment (CI/CD) using AWS Cloud Development Kit. Donnie shows you with step-by-step demos and after you will understand the overall concept of IaC and CI/CD, AWS services you need to use and developer tool for seamless integration with your development workflow.

{{< youtube ocL5ctQu0sw >}}


**Apache Airflow**

Great video from the re:Mars event from the lovely folks at Astronomer, one of the leading groups behind engineering efforts on Apache Airflow. In this session, Steven Hillon VP of Data shows you how data science teams use Airflow to run models in production. 

{{< youtube jmg_NPvvL-Y >}}


**OpenSearch**

David Tippett, Developer Advocate in the OpenSearch team joins the HPE Technology developer community to share news about OpenSearch and how you can use it to help you search through all your data.

{{< youtube KdssEOIdO_0 >}}


### Events for your diary

**Build On Live: Data Analytics**
**July 7th, 9am PDT**

Don't miss this live streamed event from my colleagues in AWS, where they cover all things data on AWS. There are some fabulous sessions covering some of your favourite open source data technologies (Apache Airflow, Apache Hudi, Amazon EMR and more). 

This is being live streamed on Twitch, so you do not need to register. Make sure you put it in your diary so you remember, and find out more info on the [Build On Live 2022 Schedule](https://aws-oss.beachgeek.co.uk/1uw) page


**BOSC 2022**
**July 13-14, Madison, Wisconsin, USA**

The Bioinformatics Open Source Conference (BOSC) has been held annually since 2000, and this year AWS is proud to be a platinum sponsor for this event. BOSC covers all aspects of open source bioinformatics software and open science, including (but not limited to) these topics, Open Science and Reproducible Research, Open Biomedical Data, Citizen/Participatory Science, Standards and Interoperability, Data Science Workflows, Open Approaches to Translational Bioinformatics, Developer Tools and Libraries, Inclusion, and Outreach and Training. This is a hybrid event (in person/virtual) and you find out more by checking out the event page, [BOSC 2022](https://aws-oss.beachgeek.co.uk/1li)

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)

**OpenSearchCon 2022**
**Sept 21st, 2022 Seattle**

Come to the first annual OpenSearchCon!

This day-long conference will be packed with presenters who build and innovate with OpenSearch. It doesn’t matter if you’re just getting started on your OpenSearch journey, running giant clusters, or contributing tons of code; the event is for everyone. Join us to celebrate the progress and look into the future of the project. Admission is free, and registration will be open in the next few weeks. All you will need to do is sign up, and get to Seattle!

Check out the full details, including signing up and location, at the [meetup page here](https://aws-oss.beachgeek.co.uk/1n1).


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)