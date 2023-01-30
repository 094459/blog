---

title: 'AWS open source newsletter #143'
date: '2023-01-30'
tags : [ oss-newsletter, aws open source, MySQL, PostgreSQL, MariaDB, OpenSearch, RabbitMQ, Apache Flink, Apache Velocity Template Language, AWS ParallelCluster, Kubernetes, EKS Anywhere, Apache Kafka, AWS Distro for OpenTelemetry, Prometheus, OpenShift, ROSA, AWS SAM, Terraform, OpenJDK, DataHub, AWS CDK, Pulumi, SST, Serverless Framework, Apache Iceberg, ]

---

## January 30th, 2023 - Instalment #143

Welcome to edition #143 of the AWS open source newsletter, and another week of great new open source projects for you to try out. This week we feature projects including "aws-cdk-in-electron", a project that lets you put AWS CDK in a graphical user interface, "lightsail-k8s-installer" that helps you deploy Kubernetes into Amazon Lightsail, "porting-advisor-for-graviton" a great project to help you migrate to Arm based AWS Graviton instance types, "aws-ebook-downloader" a browser tool to help you easily download pdf's on AWS topics, "lake-formation-permissions-sync" a useful tool to help you keep on top of your Lake Formation setups, and many more.

For those who prefer reading up on the latest open source topics, this week we have content on some of your favourite open source projects such as MySQL, PostgreSQL, MariaDB, OpenSearch, RabbitMQ, Apache Flink, Apache Kafka, AWS Distro for OpenTelemetry, Prometheus, OpenShift, DataHub, Apache Iceberg, and many more. Don't forget to check out the videos and events section at the end too, as there are some great videos this week that you do not want to miss.

**Raffle prize winner**

*No one has claimed the winning ticket - it is out there somewhere. I will post this number again this week, and if I get no takers, I will publish another ticket.*

Before Christmas we had a raffle to win some cool AWS SWAG. I can now reveal that the winning ticket is **038C123F-DA73-4584-ABE2-** - if this matches your ticket, then please contact me at ricsue@amazon.com with the LAST portion of the ticket. If yours matches what I have, you are a winner!


### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes: Rio Astamal, Yankee Maharjan, Praneeta Prakas, Mohamed ElAsmar, Julian Wood, Francisco Losada, Brandon Minnick, Anand Shah, John Preston, Sebastian Bille, Rafael Pereyra, James McIntyre, Eli Fisher, David Tippett, Pavani Baddepudi, Gary Stafford, Mark Sailes, Maciej Walkowiak, Serkan Ozal, Vadym Kazulkin, and Goran Opacic Esteh

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution.*

#### Tools

**porting-advisor-for-graviton**

[porting-advisor-for-graviton](https://aws-oss.beachgeek.co.uk/2g9) is a fork of Porting advisor, an open source project by the ARM High Performance Computing group. Originally, it was coded as a Python module that analysed some known incompatibilities for C and Fortran code. It is a command line tool that analyses source code for known code patterns and dependency libraries. It then generates a report with any incompatibilities with our Graviton processors. This tool provides suggestions of minimal required and/or recommended versions to run on Graviton instances for both language runtime and dependency libraries. It can run on non-ARM based machines (no Graviton processor needed). This tool does not work on binaries, just source code. The tool supports C/C++, Fortran, Go 1.11+, Java 8+, and Python 3+. Very nice indeed, and this weeks must check out project. Dive into the detailed README for more details.

**iam-roles-anywhere-session**

[iam-roles-anywhere-session](https://aws-oss.beachgeek.co.uk/2gy) provides an easy way to create a refreshable boto3 Session with AWS Roles Anywhere. You can use AWS Roles Anywhere to obtain temporary security credentials in IAM for workloads such as servers, containers, and applications that run outside of AWS. Read more about this here, [What is AWS Identity and Access Management Roles Anywhere?](https://aws-oss.beachgeek.co.uk/2gz)

![an overview of iam anywhere architecture](https://pbs.twimg.com/media/FYmSga3WAAApFeY?format=jpg&name=medium)

**aws-cdk-in-electron**

[aws-cdk-in-electron](https://aws-oss.beachgeek.co.uk/2h0) This project demonstrates how you can deploy CDK projects, and run SDK commands from within an Electron app. The app can contain all the dependencies the end user needs, meaning they will not have to install AWS SDK for JavaScript, AWS CDK, or use the command line. This sample project can be built as a standalone app that is able to both query and deploy changes to an account. What the standalone app is able to do is dependant on the permissions you give it when you configure it with credentials. Very cool.

![overview of cdk in electron app](https://github.com/aws-samples/aws-cdk-in-electron/blob/main/assets/ui.png?raw=true)

**lake-formation-permissions-sync**

[lake-formation-permissions-sync](https://aws-oss.beachgeek.co.uk/2h1) is a utility developed to create alternate backup of Glue Catalog objects and LakeFormation permissions and replicate to a target region. It supports both batch and realtime modes of operation, so check out the docs for more details on how these work.

![architecture of lake formation permissions sync](https://github.com/aws-samples/lake-formation-permissions-sync/blob/main/img/LakeFormationDRRealTime.png?raw=true)

**leverage**

[leverage](https://aws-oss.beachgeek.co.uk/2gq) is an open source tool that helps you easily deploy ready made AWS Cloud infrastructure based on the AWS Well Architected Framework provided by Binbash. Their mission is to simplify the process of building, and deploying software in the Cloud. You can find out more about how they have laid out their open source projects by reading a post they put together, [Open source Github repository pre-launch checklist](https://aws-oss.beachgeek.co.uk/2gw)

![example of one of their architectures](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*t64DmJ6Zjf5LaPRPa4nXHw.png)

**lightsail-k8s-installer**

[lightsail-k8s-installer](https://aws-oss.beachgeek.co.uk/2gv) is a shell script from AWS Developer Advocate Rio Astamal that simplifies the process of setting up a Kubernetes cluster on Amazon Lightsail. Not only it automates the creation of necessary resources using AWS CloudFormation, but it also automates the installation of Kubernetes packages. With just one simple command, your Kubernetes cluster should up and running in no time!

**aws-ebook-downloader**

[aws-ebook-downloader](https://aws-oss.beachgeek.co.uk/2gx) is a handy Chrome extension from Yankee Maharjan that helps you easily download AWS documentation from the AWS Resource Hub. Check out this short video he has linked in the repo to see it in action.

{{< youtube TEmndTI01dU >}}

### Demos, Samples, Solutions and Workshops

**transactional-datalake-using-apache-iceberg-on-aws-glue**

[transactional-datalake-using-apache-iceberg-on-aws-glue](https://aws-oss.beachgeek.co.uk/2h3) This repository provides you cdk scripts and sample code on how to implement end to end pipeline for transactional data lake by ingesting stream change data capture (CDC) from MySQL DB to Amazon S3 in Apache Iceberg format through Amazon Kinesis using Amazon Data Migration Service(DMS) and Glue Streaming.

![architecture of transactional data lake using apache iceberg on aws glue](https://raw.githubusercontent.com/aws-samples/transactional-datalake-using-apache-iceberg-on-aws-glue/be6dd694bf70596966ca51e7f094cec2b93ccf80/transactional-datalake-arch.svg)

**aws-glue-streaming-etl-with-apache-iceberg**

[aws-glue-streaming-etl-with-apache-iceberg](https://aws-oss.beachgeek.co.uk/2h4) this project helps you to buid a streaming ETL job in AWS Glue to integrate Iceberg with a streaming use case and create an in-place updatable data lake on Amazon S3. AWS CDK scripts are provided to help simplify the installation and configuration, and after ingested to Amazon S3, you can query the data with Amazon Athena.

![architecture of aws glue streaming etl with apache iceberg](https://raw.githubusercontent.com/aws-samples/aws-glue-streaming-etl-with-apache-iceberg/dbfa011d2611e48c84d47de56ca5914a86a6f0c5/glue-streaming-data-to-iceberg-table.svg)

**amazon-opensearch-batch-indexing-with-aws-lambda**

[amazon-opensearch-batch-indexing-with-aws-lambda](https://aws-oss.beachgeek.co.uk/2gn) This repository provides guidance on how to use the Amazon OpenSearch Python client to perform batch operations using Lambda functions and how to architect your solution using a data lake architecture. You can read the supporting blog post, [Text analytics on AWS: implementing a data lake architecture with OpenSearch](https://aws-oss.beachgeek.co.uk/2go), where Francisco Losada provides an overview of the architecture and dives deeper into how this project works.

![architecture of opensearch batch indexing project](https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2023/01/19/Figure1.png)

**LambdaTriggersSample**

[LambdaTriggersSample](https://aws-oss.beachgeek.co.uk/2gp) if you are looking for a sample .NET app demonstrating AWS Lambda triggers, then Brandon Minnick has you covered. This is a sample app demonstrating an end-to-end mobile workflow using .NET MAUI, + Serverless AWS Lambda + AWS S3 Storage in C#.

![architecture for lambdatriggersample](https://user-images.githubusercontent.com/13558917/214541434-0244c7f0-cc13-4273-89b0-af5ffd9f9786.png)

**aws-mwaa-openlineage**

[aws-mwaa-openlineage](https://aws-oss.beachgeek.co.uk/2h2) this repo contains all the code from the post I shared in last weeks newsletter, #142 [Automate data lineage on Amazon MWAA with OpenLineage](https://aws-oss.beachgeek.co.uk/2fj). This code will help you get started with how to integrate Marquez and OpenLineage with Apache Airflow.

![overview of aws mwaa openlineage architecture ](https://res.cloudinary.com/practicaldev/image/fetch/s--vLCvZ9l3--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2023/01/13/BDB2522-04-solution-overview-1.png)

### AWS and Community blog posts

**Apache Flink**

In the post [Automate deployment and version updates for Amazon Kinesis Data Analytics applications with AWS CodePipeline](https://aws-oss.beachgeek.co.uk/2ge), Anand Shah show how you can automate deployment and version updates for Kinesis Data Analytics applications that enables better collaboration with your Platform and engineering teams. [hands on]

![architecture of cicd and apache flink ](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2022/11/17/image005-3.jpg)

We also had this post, [Exploring Apache Flink & AWS KDA: Realtime data streaming](https://aws-oss.beachgeek.co.uk/2gs) where engineers at Capitol One share their experience building realtime data streaming apps with Apache Flink and AWS Kinesis Data Analytics. [hands on]

![architecture of apache flink at capitol one](https://ecm.capitalone.com/WCM/tech/images/screen-shot-2022-12-21-at-10.05.11-am.png)

**Apache Kafka**

AWS Community Builder and Apache Kafka wizard John Preston has a great post for you this week. Using an open source tool that John created and we have featured on the AWS open source blog, you can speed up and simplify how you deploy and integrate Apache Kafka and Conduktor in as little as three commands. Don't believe me? Well I will hand you over to John in hist post, [Deploy Conduktor & a MSK Cluster in 3 commands](https://aws-oss.beachgeek.co.uk/2gu). [hands on]

![architecture of solution for msk and conductor](https://images.compose-x.io/labs/conduktor_msk/architecture.jpg)

**Open Source Serverless frameworks**

With a number of open source serverless frameworks available for developers to use, which one should you use? AWS Community Builder Sebastian Bille has just what you need to help you explore this area in his post, [Serverless Frameworks for 2023](https://aws-oss.beachgeek.co.uk/2gt). Settle in and grab a cup of your favourite warm beverage whilst he takes you on a serverless framework journey.

**AWS Distro for OpenTelemetry**

Rafael Pereyra has put together, [Using AWS Distro for OpenTelemetry and IAM Roles Anywhere on-premises to ingest metrics into Amazon Managed Service for Prometheus](https://aws-oss.beachgeek.co.uk/2gm). In it he shows how to programmatically access your AWS resources running in your on-premises using IAM Roles Anywhere. IAM Roles Anywhere allows your workloads such as servers, containers, and applications to use X.509 digital certificates to obtain temporary AWS credentials and use the same IAM roles and policies that you have configured for your AWS workloads to access AWS resources. Very nice post. [hands on]

![aws distro for opentelemetry hybrid architecture](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2023/01/19/cloudops_11192_2.png)

**Other posts and quick reads**

* [Scaling container workloads with shared storage for Red Hat OpenShift Service on AWS](https://aws-oss.beachgeek.co.uk/2gk) demonstrates the use of FSx for ONTAP as a persistent storage layer for  Red Hat OpenShift Service on AWS (ROSA) applications [hands on]

![architecture for ROSA storage post](https://d2908q01vomqb2.cloudfront.net/e1822db470e60d090affd0956d743cb0e7cdf113/2023/01/13/Figure-1-ROSA-Integration-with-Amazon-FSx-for-NetApp-ONTAP-1024x659.png)

* [5G Core implementation on Amazon Elastic Kubernetes Service Anywhere on bare metal](https://aws-oss.beachgeek.co.uk/2gf) looks at how customers can utilise Amazon Elastic Kubernetes Service Anywhere (Amazon EKS-A) to automate the deployment of 5G Core on their customer-managed on-premises infrastructure on bare metal [hands on]

![5G core amazon eks anywhere architecture](https://d2908q01vomqb2.cloudfront.net/c5b76da3e608d34edb07244cd9b875ee86906328/2023/01/25/Figure-2-Open5GS-Mobile-Core-deployment-on-Amazon-EKS-A-on-COTS-server-1.png)

* [Leveraging Slurm Accounting in AWS ParallelCluster](https://aws-oss.beachgeek.co.uk/2gh) shows how to use new features in AWS ParallelCluster 3.3.0 that enables you to configure and enable Slurm accounting for you automatically [hands on]
* [Best practices for working with the Apache Velocity Template Language in Amazon API Gateway](https://aws-oss.beachgeek.co.uk/2gi) discusses best practices for using Apache Velocity Templates for direct service integration in API Gateway
* [Enhancing IoT device security using Hardware Security Modules and AWS IoT Device SDK](https://aws-oss.beachgeek.co.uk/2gl) walks you through some notable examples of security challenges across IoT Industry verticals [hands on]

![architecture of iot security](https://d2908q01vomqb2.cloudfront.net/f6e1126cedebf23e1463aee73f9df08783640400/2023/01/17/Blog-HSMGraphics-Architecture.drawio-1024x467.png)

* [Four key application protocols for the internet of things (IoT)](https://aws-oss.beachgeek.co.uk/2gr) explores the application protocols that are best suited for internet data messaging, focusing on criteria such as range, availability, maturity, and market segment applicability

### Quick updates

**OpenSearch**

We have a few updates for OpenSearch users and developers.

First up, check out [OpenSearch Project 2022 recap and what's next](https://aws-oss.beachgeek.co.uk/2ga) where Eli Fisher and David Tippett look back at the key accomplishments in 2022 and then looks ahead to what you can expect this year.

Also announced last week was the availability of OpenSearch 2.5. James McIntyre shares more info in his post, [OpenSearch 2.5 is live!](https://aws-oss.beachgeek.co.uk/2gb)

![OpenSearch 2.5 announcement demo](https://opensearch.org/assets/media/blog-images/2023-01-24-opensearch-2-5-is-live/dashboard-maps-preview.gif)

Finally, for those moving from self managed to managed OpenSearch, Amazon OpenSearch Serverless is now generally available. You can check out the announcement, [Amazon OpenSearch Serverless is now generally available](https://aws-oss.beachgeek.co.uk/2gc), for more details and read the post, [Amazon OpenSearch Serverless is now generally available!](https://aws-oss.beachgeek.co.uk/2gg) where Pavani Baddepudi shares the design and high-level architecture of OpenSearch Serverless. 

![architecture of opensearch serverless](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2023/01/23/BDB-3011-img3-500.png)

**MariaDB**

Amazon Relational Database Service (Amazon RDS) for MariaDB supports encrypted SSL/TLS connections to the database instances. Starting today, you can enforce SSL/TLS client connections to your Amazon RDS for MariaDB database instance for enhanced transport layer security. To enforce SSL/TLS, enable the require_secure_transport parameter (disabled by default) through the Amazon RDS Management Console, the AWS CLI or the API. When the require_secure_transport parameter is enabled, a database client will be able to connect to the RDS for MariaDB instance only if it can establish an encrypted connection. require_secure_transport parameter is supported on RDS for MariaDB versions 10.5 and higher.

**PostgreSQL**

A couple of updates this week.

First, following the announcement of updates to the PostgreSQL database by the open source community, we have updated Amazon Aurora PostgreSQL-Compatible Edition to support PostgreSQL 14.6, 13.9, 12.13, and 11.18. 

Also announced last week was that Amazon RDS for PostgreSQL now supports inbound replication from Amazon RDS Single-AZ database (DB) instances and Amazon RDS Multi-AZ DB instances with one standby to Amazon RDS Multi-AZ deployments with two readable standbys. You can use this inbound replication to help migrate your existing Amazon RDS PostgreSQL deployments to Amazon RDS Multi-AZ deployments with two readable standbys, which have one writer instance and two readable standby instances across three availability zones. By creating a Multi-AZ deployment with two readable standbys as a read replica of your existing RDS PostgreSQL database instance, you can promote the read replica to be your new primary, typically within minutes. 

Amazon RDS Multi-AZ deployments provide enhanced availability and durability, making them a natural fit for production database workloads. Deployment of Amazon RDS Multi-AZ with two readable standbys supports up to 2x faster transaction commit latencies than a Multi-AZ deployment with one standby instance. In this configuration, automated failovers typically take under 35 seconds. In addition, the two readable standbys can also serve read traffic without needing to attach additional read replicas. 

**MySQL**

Amazon Aurora now supports Aurora MySQL 3 (with MySQL 8.0 compatibility) as a source cluster or blue environment within Amazon RDS Blue/Green Deployments. This enables you to use Blue/Green Deployments for minor version upgrades for Aurora MySQL 3 (with MySQL 8.0 compatibility).

Read more about this in the announcement, [Amazon RDS Blue/Green Deployments now supports Aurora MySQL 3 (with MySQL 8.0 compatibility) as a source cluster](https://aws-oss.beachgeek.co.uk/2gd)

**RabbitMQ**

Amazon MQ now provides support for RabbitMQ version 3.8.34, which includes several fixes to the previously supported version, RabbitMQ 3.8.30.

### Videos of the week

**DataHub**

Check out the video version of Gary Stafford's post, [DataHub on AWS:  Data Discovery, Observability, and Governance on AWS with DataHub, the Open Source Data Catalog.](https://aws-oss.beachgeek.co.uk/1iq)

{{< youtube ODalP0-hFmQ >}}

**Java**

A stellar cast of Java developers, Mark Sailes, Maciej Walkowiak, Serkan Ozal, Vadym Kazulkin, and Goran Opacic take a look at SnapStart and SpringCloud AWS. A must watch for all Java fans.

{{< youtube nhwgm9J4F9A >}}

**AWS SAM and Terraform**

Praneeta Prakash, and software engineer, Mohamed ElAsmar, join Julian Wood to go through how you can now use the AWS SAM CLI together with Terraform configuration to develop and test serverless applications. See how you can speed up your local development workflow with testing and debugging. Find out how to contribute to help improve the local development process.

{{< youtube xUag7BSv6iE >}}


**Build on Open Source**

For those unfamiliar with this show, Build on Open Source is where we go over this newsletter and then invite special guests to dive deep into their open source project. Expect plenty of code, demos and hopefully laughs. We have put together a playlist so that you can easily access all (eight) of the episodes of the Build on Open Source show. [Build on Open Source playlist](https://aws-oss.beachgeek.co.uk/24u)

# Events for your diary

If you are planning any events in 2023, either virtual, in person, or hybrid, get in touch as I would love to share details of your event with readers. 

**FOSSDEM**
**Feb 4-5th, 2023 in Brussels**

FOSDEM is a free event for software developers to meet, share ideas and collaborate. Every year, thousands of developers of free and open source software from all over the world gather at the event in Brussels. 4 & 5 February 2023. A must attend event for all open source fans, check out and [register via this link](https://aws-oss.beachgeek.co.uk/2dc).

**State of Open Con 23**
**Feb 7-8th, 2023 in London**

OpenUK will be hosting a 1000 person plus two day conference in Central London, “State of Open Con 23”  in association with IEEE, the headline sponsor. Check out more info and [sign up here](https://aws-oss.beachgeek.co.uk/2dd).

**PGConf India**
**Feb 22nd to 24th, Radisson Blu Bengaluru, India**

If you are in or can get to Bengaluru, then checkout this conference for PostgreSQL developers and enthusiasts. Check out the session line up and get [your tickets here](https://aws-oss.beachgeek.co.uk/2ff).


**Everything Open**
**March14-15th Melbourne, Australia**

A new event for the fine folks in Australia. Everything Open is running for the first time, and the organisers (Linux Australia) have decided to run this event to provide a space for a cross-section of the open technologies communities to come together in person. Check out the [event details here](https://aws-oss.beachgeek.co.uk/2ds). The CFP us currently open, so why not take a look and submit something if you can.

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)

