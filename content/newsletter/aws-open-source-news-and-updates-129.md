---

title: 'AWS open source news and updates #129'
date: '2022-09-30'
tags : [ oss-newsletter, aws open source, Apache TinkerPop, Gremlin, AWS CDK, Apache Hudi, Apache Iceberg, Delta Lake, Apache Cassandra, GraphQL, Hive, Apache Spark, Apache Kafka Streams, Apache Flink, Apache Pinot, Apache Superset, Apache Airflow, Keycloak, Kubeapps, Babelfish for PostgreSQL, Linux, Ubuntu, PHP, MySQL, Bottlerocket]

---

## September 30th, 2022 - Instalment #129

**Welcome**

Welcome to the AWS open source newsletter, edition #129.

We have loads of great new projects this week, with plenty of variety to keep you all interested. We have "aws-ecr-cleaner", a great tool to help you manage your container images, "dotnet-lambda-sql-server-proxy" that shows you how you can use RDS Proxy with SQL Server and why, "minecraft-server-dashboard" perfect for those running their own minecraft servers, "YATAS" and "aws-security-survival-kit" for those working on security and governance, "aws-lambda-handler-cookbook" useful recipes to get you going, "autonomous-driving-data-framework" for folks working in the automotive space, and many more - make sure you check all the projects out. 

This week we also have a broad variety of open source topics covered, including Apache TinkerPop, Apache Hudi, Apache Iceberg, Delta Lake, Apache Cassandra, Apache Spark, Apache Kafka Streams, Apache Flink, Apache Pinot, Apache Superset, Apache Airflow, Keycloak, Kubeapps, Babelfish for PostgreSQL and more. 

I have added quite a few new events and webinars featuring a broad range of open source technologies. Some of these are physical in person events, others online. Make sure you check out that section so you do not miss out on these, as there are some great events happening over the next few weeks.

**Feedback**

Please let me know how we can improve this newsletter as well as how AWS can better work with open source projects and technologies by completing [this very short survey ](https://eventbox.dev/survey/NUSZ91Z)that will take you probably less than 30 seconds to complete. Thank you so much!

**Celebrating open source contributors**

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created. 

So thank you to the following open source heroes: Avijit Goswami, Ajit Tandale, Thippana Vamsi Kalyan, Jannik Wempe, Ran Isenberg, Greg Biegel, Aneel Murari, Rahul Popat, Matthew Overstreet, Mikhail Shapirov, Amir Shenavandeh, Amit Maindola, Melody Yang, Jianwei Li, Krish K B, Narayanan Venkateswaran, Partha Sarathi Sahoo, Phil Basford, Gary Stafford, Mohamed Radwan, Daniele Frasca, Artur Rodrigues, and Stan Girard.

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution.*

#### Tools

**aws-ecr-cleaner**

[aws-ecr-cleaner](https://aws-oss.beachgeek.co.uk/23q) this is a super useful open source project from DevOpsBox that helps you keep on top of your container image repository, specifically Amazon ECR. This tool augments capabilities such as ECR Lifecycle policies. Currently Amazon ECS, AWS Lambda, and App Runner are supported. Make sure you check out this tool if you use Amazon ECR. 

**dotnet-lambda-sql-server-proxy**

[dotnet-lambda-sql-server-proxy](https://aws-oss.beachgeek.co.uk/23m) this project from James Eastham enables Lambda functions to connect to SQL databases without having to manage the connections.

The recent release of RDS Proxy for SQL Server opens up a new, powerful set of possibilities for running .NET applications on AWS Lambda. As a default, AWS Lambda allows up to 1000 concurrent executions. If you are running an application using SQL Server these 1000 concurrent executions will create 1000 separate SQL connections, this can quickly exhaust the connection pool of your database. RDS for SQL Server does not support IAM based authentication. This means for applications using SQL server connection strings need to be managed and credentials stored somewhere, ordinarily either SSM Parameter Store or Secrets Manager.

RDS Proxy solves these two challenges. First, connections are pooled within the proxy. Meaning as Lambda scales connections to the underlying database can be re-used. Secondly, RDS Proxy supports IAM based authentication. This enables us to authenticate our application using IAM roles and policies.

Check out the docs for more details.

![architecture of rds proxy for sql server](https://github.com/jeastham1993/dotnet-lambda-sql-server-proxy/blob/main/assets/arch.drawio.png?raw=true)

**YATAS**

[YATAS](https://aws-oss.beachgeek.co.uk/23j) Stan Girard has put together this project that stands for Yet Another Testing & Auditing Solution (YATAS) and has a cute log to boot. The goal of YATAS is to help you create a secure AWS environment without too much hassle. It won't check for all best practices but only for the ones that are important for you based on Stan's experience. Please feel free to reach out to Stan if you find something that is not covered.

![demo of YATAS](https://github.com/StanGirard/YATAS/blob/main/docs/demo.gif?raw=true)

**aws-security-survival-kit**

[aws-security-survival-kit](https://aws-oss.beachgeek.co.uk/23r) this tool from zoph-io allows you to set up minimal alerting on typical suspicious activities on your AWS Account. This project brings security observability to your AWS account, it's complementary to the GuardDuty service. It works by deploying CloudWatch EventRules and CloudWatch alarms on a number of defined criteria. Check out the project and documentation to see what suspect activities it currently tracks.

**aws-lambda-handler-cookbook**

[aws-lambda-handler-cookbook](https://aws-oss.beachgeek.co.uk/23k) this repository from AWS Community Builder Ran Isenberg provides a working, deployable, open source based, AWS Lambda handler and CDK Python code. This handler embodies Serverless best practices and has all the bells and whistles for a proper production ready handler. What sets this repo apart is the detailed and expansive documentation and attention to detail. Ran will be appearing in a future episode of Build on Open Source, and he may cover and demo some of the code in this repository so keep an eye out for that.

**autonomous-driving-data-framework**

[autonomous-driving-data-framework](https://aws-oss.beachgeek.co.uk/23l) is a collection of modules, deployed using the SeedFarmer orchestration tool (a project we featured in [#118](https://blog.beachgeek.co.uk/newsletter/aws-open-source-news-and-updates-118/)). Autonomous Driving Data Framework (ADDF) modules enable users to quickly bootstrap environments for the process and analysis of autonomous driving data.

**minecraft-server-dashboard**

[minecraft-server-dashboard](https://aws-oss.beachgeek.co.uk/23g) this repo from Artur Rodrigues helps you build a real-time Minecraft Server dashboard using AWS Amplify and AWS Appsync to cost-effectively manage Minecraft Servers deployed on Amazon Elastic Compute Cloud (EC2). You can find out more by reading his post, [DIY Minecraft Dashboard to manage your kids games](https://aws-oss.beachgeek.co.uk/23f)

![example of dashboard for minecraft servers](https://miro.medium.com/max/1400/1*ISTk1IThhfiPvCH102BTlw.png)

### Demos, Samples, Solutions and Workshops

**amazon-sagemaker-bert-finetuning-for-search**

[amazon-sagemaker-bert-finetuning-for-search](https://github.com/aws-samples/amazon-sagemaker-bert-finetuning-for-search) this repo contains scripts and note books that will help you train a Sentence Transformer (SBERT) model using Amazon SageMaker to fine tune the pre-trained BERT embeddings on data retrieval task, deploy the fine-tuned BERT model on Amazon SageMaker for both real-time and batch inference, and use Amazon OpenSearch service to index and store the sentence embeddings and perform realtime search against query. The SBERT framework is based on PyTorch and Transformers and offers a large collection of pre-trained models tuned for various tasks. This repository focus' on fine tuning the BERT model on data retrieval (search) use case.

**amazon-transcribe-streaming-live-closed-captions**

[amazon-transcribe-streaming-live-closed-captions](https://aws-oss.beachgeek.co.uk/23o) this sample project will inject live closed captioning to an input video stream, and send the combined output to a destination.

**fine-grained-authorization-apigw-lambda-dynamodb**

[fine-grained-authorization-apigw-lambda-dynamodb](https://aws-oss.beachgeek.co.uk/23i) AWS Community Builder Daniele Frasca shares this project that looks like its written in Rust, that helps you enable fine-grained authorisation using any Identity and Access Management solution with API Gateway.

**graphql-lambda-java-sample**

[graphql-lambda-java-sample](https://aws-oss.beachgeek.co.uk/231) this repository consists of sample code for three applications. 1/ Self managed GraphQL API running on AWS Lambda, 2/ AWS AppSync hosted GraphQL API with Direct Lambda Resolvers, and 3/ AWS AppSync hosted GraphQL API with RDS Resolver. To help you get started, check out the accompanying blog post, [Building a GraphQL API with Java and AWS Lambda](https://aws-oss.beachgeek.co.uk/232), where Aneel Murari and Rahul Popat guide you through these three options for running a GraphQL application on AWS using serverless technologies.

![architecture of graphql-lambda](https://d2908q01vomqb2.cloudfront.net/0a57cb53ba59c46fc4b692527a38a87c78d84028/2022/09/26/mobile_1662_2-1.jpg)

**trusted-advisor-asana-task**

[trusted-advisor-asana-task](https://aws-oss.beachgeek.co.uk/23n) Trusted Advisor(TA) inspects your AWS environment, and then makes recommendations when opportunities exist to save money, improve system availability and performance, or help close security gaps. High priority TA checks require further investigation as they help you secure and optimise your account to align with AWS best practices. Engineering teams often dedicate resources to manually go through the TA recommendations to detect and handle the recommendations. Further, some of the less severe issues could be parked for a later date and needs to be tracked as a backlog item. 

If your team is already using Asana to manage all the work from company strategy to sprint plans and support issues, this solution automates the process to get notified on TA recommendations as a part of the same Asana ecosystem in the form of Asana tasks. This removes the need for manual intervention and enables teams to easily track, and provides visibility to the teams to address the issues in a timely manner.

![architecture of solution to integrate asana with ta](https://user-images.githubusercontent.com/108042843/192427607-be22d5a8-e099-4cee-9ed1-03530513ff7d.png)

**aws-sap-lens-well-architected**

[aws-sap-lens-well-architected](https://aws-oss.beachgeek.co.uk/23p) This repository holds the latest version of the SAP Lens for the AWS Well-Architected Framework. The Lens is for AWS customers and partners to use when assessing SAP Workloads for best practices and design principles according to the AWS Well-Architected framework. The SAP Lens is provided as a JSON file to upload into your AWS account to use when reviewing your workload.

### AWS and Community blog posts

**Open-source Stream Processing**

The open source data analytics toolset is vast. To help you break some of this down and explore one facet of this area, stream processing, we have the latest two part post from Gary Stafford, [Exploring Popular Open-source Stream Processing Technologies:Part One](https://aws-oss.beachgeek.co.uk/239) and [Part Two](https://aws-oss.beachgeek.co.uk/23a). Gary's posts are always must reads, and in this two parter he provides a great introduction into batch vs stream processing, an overview of open source stream processing projects, and of course, plenty of code and demos to bring this all to life. This posts covers Apache Spark Structured Streaming, Apache Kafka Streams, Apache Flink, and Apache Pinot with Apache Superset. Awesome stuff as always! [hands on]

![dashboard using superset for open source streaming posts](https://miro.medium.com/max/1400/1*DJTh-smKy7dzZ_3cqwzAPA.png)

**Keycloak & Kubeapps**

Kubeapps is an in-cluster web-based application that enables users with a one-time installation to deploy, manage, and upgrade applications on a Kubernetes cluster. Keycloak is an open source software product to allow single sign-on with Identity and Access Management. Combining these two and deploying them on Amazon EKS, is AWS Community Builder Mohamed Radwan. In his post, [Integrate Keycloak and Kubeapps on AWS EKS](https://aws-oss.beachgeek.co.uk/23d) he provides a detailed walk through of getting these deployed and configured. [hands on]

**Apache Airflow**

In [Running thousands of models a month with Apache Airflow on AWS](https://aws-oss.beachgeek.co.uk/23b), AWS Hero Phil Basford takes a look at Apache Airflow as an orchestrator for batch based model inferencing. He walks you through an example of running a PySpark job to process data, orchestrate training jobs using that data and then consolidating reporting.

![chart of apache airflow dag runs](https://inawisdom.com/wp-content/uploads/2022/09/airflow-cloudwatch-chart.png)

**AWS SAM**

Mukesh Murugan has put together this post, [AWS SAM CLI for .NET Developers – Getting Started with Serverless Application Model CLI Tool](https://aws-oss.beachgeek.co.uk/23c) that guides you through using the AWS Serverless Application Model (SAM) CLI for .NET Development. If you are a Windows developer, this is a must read for you this week. [hands on]

**AWS CDK**

What are CDK Aspects? In [Mastering AWS CDK Aspects](https://aws-oss.beachgeek.co.uk/23s) Jannik Wempe answers my question and dives deep into how you can use CDK Aspects to apply an operation to every construct in a given scope. Great deep dive and must read for anyone using CDK. [hands on]

**Apache Hudi, Apache Iceberg, and Delta Lake**

If you are interested in understanding the latest and emerging open source technologies in the data analytics space, then you will love this post, [Get a quick start with Apache Hudi, Apache Iceberg, and Delta Lake with Amazon EMR on EKS](https://aws-oss.beachgeek.co.uk/234). Amir Shenavandeh, Amit Maindola, and Melody Yang explore three open-source transactional file formats: Apache Hudi, Apache Iceberg, and Delta Lake and show you how they can overcome some challenges that you may face when building ACID-compliant data lakes. [hands on]

![architecture overview of acid data lakes](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2022/09/16/BDB-2360-image001.png)

**Delta Lake**

Delta Lake is an open-source project that helps implement modern data lake architectures commonly built on Amazon S3 or HDFS. If you want to know more about how to run Delta Lake on Amazon EMR, then check out this post, [Build a high-performance, transactional data lake using open-source Delta Lake on Amazon EMR](https://aws-oss.beachgeek.co.uk/23y) where Avijit Goswami, Ajit Tandale, and Thippana Vamsi Kalyan show how you can get started running Delta Lake (version 2.0.0) on Amazon EMR. If you were curious about this project, this is a great post to get started with. [hands on]

**Hive Metastore**

The Hive metastore is a relational database that stores metadata related to tables/schemas and allows you to easily query your data. In the post, [Upgrade Amazon EMR Hive Metastore from 5.X to 6.X](https://aws-oss.beachgeek.co.uk/236) Jianwei Li, Krish K B, Narayanan Venkateswaran, and Partha Sarathi Sahoo share the steps needed to upgrade the Hive Metastore schema using MySQL as the backend, although you can adjust if you are using other databases such as PostgreSQL.

![upgrading hive metastore diagram](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2022/09/05/BDB-2332-Hive-Metastore2Metastore-Upgrade.jpg)

**Apache TinkerPop Gremlin**

[Gremlin](https://aws-oss.beachgeek.co.uk/22z) is the graph traversal language of Apache TinkerPop, an open source graph computing framework for both graph databases (OLTP) and graph analytic systems (OLAP). In the post, [Automated testing of Amazon Neptune data access with Apache TinkerPop Gremlin](https://aws-oss.beachgeek.co.uk/230) Greg Biegel shows you how you can use a container running the Apache TinkerPop Gremlin Server to run functional tests against queries that have been written to run against a property graph in Neptune. Why? This is important because it enables Gremlin queries to be functionally tested within a CI/CD pipeline. [hands on]

![overview of apache tinkerpop gremlin](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2022/09/22/DBBLOG-2476_3.jpg)

**Other posts you might like from the past week**

* [Integrating Amazon MemoryDB for Redis with Java-based AWS Lambda](https://aws-oss.beachgeek.co.uk/237) shows you how to provision a MemoryDB Redis cluster and access it using Lambda
* [Understanding statistics in PostgreSQL](https://aws-oss.beachgeek.co.uk/23t) explain the types of statistics in PostgreSQL (these play a key role in improving the performance of the database) and how to read and understand them
* [How to automatically build forensic kernel modules for Amazon Linux EC2 instances](https://aws-oss.beachgeek.co.uk/238) walks you through the deployment and use of the EC2 forensic module factory solution to create specific versions of forensic kernel modules for Amazon Linux EC2 instances [hands on]

![architecture overview of ec2 forensic module](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2022/09/23/img1-1-1024x704.png)

* [Enabling Tiering and Throttling in a Multi-Tenant Amazon EKS SaaS Solution Using Amazon API Gateway](https://aws-oss.beachgeek.co.uk/235) examines key considerations for implementing throttling, tiering, and authentication in a multi-tenant Amazon EKS environment using Amazon API Gateway [hands on]

![architecture overview of multi-tenant solution](https://d2908q01vomqb2.cloudfront.net/77de68daecd823babbb58edb1c8e14d7106e83bb/2022/09/26/SaaS-EKS-API-Gateway-1.1.png)

* [How A&E Engineering Uses Serverless Technology to Host Online Machine Learning Models](https://aws-oss.beachgeek.co.uk/23v) shows you how to deploy an online serverless machine learning model using open source Python River and AWS Cloud Development Kit (AWS CDK)

![illustration from the A&E blog post ](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2022/09/27/architecture-diagram-ML-model.png)

**Case Studies**

* Apache Cassandra is a distributed NoSQL database used in many of the biggest “fast data” workloads being operated today. In [Scaling Amazon EKS and Cassandra Beyond 1,000 Nodes](https://aws-oss.beachgeek.co.uk/233) Matthew Overstreet from DataStax collaborates with Mikhail Shapirov describes a concrete experiment to prove k8ssandra scalability on Amazon EKS. Well worth checking out, if like me, you love benchmarking and scaling posts.

![graph of Cassandra scaling](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2022/09/27/mik-2.jpg)

### Quick updates

**Linux**

AWS Snow Family now offers the Snow Amazon Linux 2 (AL2) Amazon Machine Image (AMI) for all Snowball Edge and Snowcone jobs. With this launch, customers can get started running edge workloads on Snow devices using the Snow AL2 AMI. The Snow AL2 AMI is maintained and provided by AWS Snow, making it easier for customers who do not want to create their own AMI for Snow devices.

Prior to this launch, customers had a 2-step process to provisioning AMIs on Snow jobs. First, customers had to create their own AMI from Ubuntu or CentOS offerings from AWS Marketplace and then select these AMIs as part of the Snow job order. This 2-step process provided more control to the customers in selecting the right AMIs for their jobs. For customers not familiar with the AMI creation process, the 2-step process required more preparation before placing a Snow job order with AMIs on them. Now, customers who do not want to bring their own AMIs to a Snow job can add a Snow AL2 AMI to their Snow job with 1-click selection at the time of job ordering.

**Ubuntu**

Amazon WorkSpaces now offers support for Ubuntu Desktop 22.04 LTS. Ubuntu is a popular Linux distribution published by Canonical and the first third-party Linux operating system supported by Amazon Workspaces. With this launch, Amazon WorkSpaces customers now have the flexibility to select Amazon Linux, Microsoft Windows, or Ubuntu desktops depending on the specific needs of their end users. Customers can easily provision and scale Ubuntu WorkSpaces for developers, data scientists, and engineers as high-performance cloud-based development desktops, or for other non-technical users as general-purpose desktops.

Read more in the official launch post, [Amazon WorkSpaces Introduces Ubuntu Desktops](https://aws-oss.beachgeek.co.uk/23u) or the news release [AWS introduces Ubuntu Desktop for Amazon WorkSpaces](https://aws-oss.beachgeek.co.uk/23w)

![demo of amazon workspace running ubuntu](https://d2908q01vomqb2.cloudfront.net/da4b9237bacccdf19c0760cab7aec4a8359010b0/2022/09/07/2022-09-07_12-32-39-1024x588.png)

**Bottlerocket**

Bottlerocket, a Linux-based operating system that is purpose built to run container workloads, is now integrated with Amazon Inspector. Customers that have Inspector EC2 scanning already enabled do not need to take any additional action. If Amazon Inspector discovers a vulnerability, it will recommend an update to the version of Bottlerocket that fixes that vulnerability.

Amazon Inspector is a vulnerability management service that scans EC2 and container workloads for software vulnerabilities and unintended network exposure. Amazon Inspector leverages the AWS System Manager (SSM) agent to scan for vulnerabilities. In Bottlerocket hosts, the SSM agent runs within the control host container, so you need to make sure it is enabled in your hosts.

**MySQL**

You can now perform an in-place upgrade of your Amazon Aurora  database cluster from Amazon Aurora MySQL-Compatible Edition 2 (with MySQL 5.7 compatibility) to Aurora MySQL-Compatible Edition 3 (with MySQL 8.0 compatibility). Instead of backing up and restoring the database to the new version, you can upgrade with just a few clicks in the Amazon RDS Management Console or by using the AWS SDK or CLI.

MySQL 8.0 offers improved performance functionality from enhancements such as instant DDL and adds developer productivity features such as window functions. It also includes JSON functionality additions, new security capabilities, and more. MySQL 8.0 on Aurora MySQL-Compatible Edition supports popular Aurora features including Aurora Serverless v2, Global Database, RDS Proxy, Performance Insights, and Parallel Query.

To upgrade to Aurora MySQL Version 3 (compatible with MySQL 8.0), select the "Modify" option on the AWS Management Console corresponding to the database cluster you want to upgrade, choose the version of Aurora MySQL Version 3 you want to upgrade to, and proceed with the wizard. The upgrade may be applied immediately (if you select the "Apply Immediately" option), or during your next maintenance window (by default).

**PHP**

AWS X-Ray now support tracing end-to-end requests in PHP applications via the AWS Distro for OpenTelemetry (ADOT) in public preview. ADOT is a secure, AWS-supported distribution of the OpenTelemetry project. With this launch, you can now use the OpenTelemetry PHP SDK to instrument your PHP applications for tracing with X-Ray. X-Ray will help you to visualise and debug your distributed PHP applications in the CloudWatch console with its service map and trace analytics tools.

Customers can now use the AWS-supported OpenTelemetry components necessary to export trace data to AWS X-Ray, such as the X-Ray ID generator, X-Ray propagator, and resource detectors for Amazon ECS, Amazon EKS, Amazon EC2, and AWS Lambda services. Customers can also use the AWS SDK for PHP to trace requests made to the AWS SDK without the need to manually record each request. By using ADOT, applications can be easily configured to export traces to AWS X-Ray.

Check out the release post, [AWS X-Ray launches support for tracing PHP applications via OpenTelemetry in public preview](https://aws-oss.beachgeek.co.uk/23x). This provides links to resources to get you started.

**awscii-cli**

[awscii-cli](https://github.com/mhlabs/awscii-cli) is a command line tool that lets you render predefined AWS graphs in ASCII art using asciichart. In addition to  #AWS #Lambda, #DynamoDB, #APIGateway, awscii-cli has now added Kinesis Data Streams metrics to list of service metrics it can visualise. Check out more about this update in [Lars' tweet](https://aws-oss.beachgeek.co.uk/23e) earlier in the week.

### Videos of the week

**AWS CDK**

This is a must watch video for folks using AWS CDK, as AWS DevTools Hero Matthew Bonig takes an honest look at AWS CDK, exploring some of the frustrations that he has seen others share, and offering up some options on how to work around those. Must watch video this week.

{{< youtube AVMkjtJ21Co >}}


**Build on Open Source**

If you missed S01E02 where we talk with Gethin Webster of the CloudScape project, you can catch up by checking out the recording on [Twitch](https://www.twitch.tv/videos/1598818260).

{{< youtube XyZRRCJ-H7A >}}


**Babelfish for PostgreSQL**

Babelfish for Aurora PostgreSQL is a new capability for Amazon Aurora PostgreSQL-Compatible Edition that enables Aurora to understand commands from applications written for Microsoft SQL Server. In this video, Rob Vershoor provides an overview of Babelfish for Aurora PostgreSQL, use cases, when to use Babelfish vs. Traditional Migration and how to migrate to Babelfish in six steps.

{{< youtube X_6--RJ_bdM >}}


**Kubernetes**

In the latest episode from the Containers from the Couch team, find out and see the recently announced integration between Kubecost and EKS, giving customers better cluster cost visibility on AWS.

{{< youtube -mDPV1huzBY >}}


### Events for your diary

**ApacheCon North America 2022**
**October 3-6, New Orleans**

ApacheCon is the official open source software convention of the Apache Software Foundation (ASF), focused on the software projects hosted at the ASF. With over 160 sessions covering all your favourite Apache open source projects and more, 

[Check out the ApacheCon registration page](https://aws-oss.beachgeek.co.uk/221) for more details, including the sessions and keynotes.

**Addressing Cybersecurity challenges in open source software**
**October 5th, 7:30am India / 10am Hong Kong / 1pm Australia**

Recently, Snyk partnered with The Linux Foundation to develop a report that focuses on OSS security perspectives and how to improve OSS security and sustainability. OpenSSF, a Linux Foundation initiative of which Snyk and AWS are Premier Members, is a global cross-industry collaboration of organisations that is building an expert community, targeted initiatives, and best practices to improve OSS security.

For this webinar, Snyk, OpenSSF together with AWS and Australia Post will discuss key data points surrounding how organisations are addressing and prioritising their cybersecurity needs, the most important ways to improve open source software security, and who should be driving open source software security policies.

Find out more and [register via their online registration page](https://aws-oss.beachgeek.co.uk/23h).

**Jumpstart your Java applications with AWS Lambda and Micronaut**
**October 5th**

Don't miss the opportunity to attend this event if you are in or around London. Combining lectures, live coding demonstrations, AWS interaction, and hands-on exercises, you will learn:

* How AWS Lambda functions written with the Micronaut framework can be triggered with AWS Events (such as an S3 or DynamoDB event)
* How integrating Amazon API Gateway and AWS Lambda enables you to write your applications as you would with a Netty runtime (i.e., write your applications as you usually do; run them in AWS Lambda)
* How to deploy a Micronaut application as a GraalVM native image to AWS Lambda Java runtime or to a custom runtime
* How leveraging certain characteristics of Micronaut applications, including fast startup, low memory consumption, and GraalVM integration, can help you work around cold startups in AWS Lambda.

Check out and register while there are places available [at the link here](https://aws-oss.beachgeek.co.uk/223).

**Build on AWS Open Source**
**October 7th, 9am BST**

Join us for the third episode of the Build on AWS series, featuring a live round up of the latest projects and news as well as a special guest speaker. This week, we are delighted to have AWS Data Hero Alvaro Hernandez who will be talking about all things database on containers. Do not miss this!

**The Present and The Future of Infrastructure as Code**
**October 11th, 6 PM, Paris**

This promises to be a great meet-up and essential attendance if you are into infrastructure as code. AWS Hero Anton Babenko hosts this event, sponsored by Qovery.

Read more and register for this event by heading over to [their meet-up page](https://aws-oss.beachgeek.co.uk/220).

**Dev Day Workshop: Deploy, Manage and Scale Kubernetes to AWS EKS with GitLab**
**October 11th, 11:45am PT**

This four hour hands-on workshop is designed for development teams planning projects involving AWS EKS clusters. Join industry-leading experts from AWS and GitLab for a hands-on workshop that will enable you to deploy secure applications to AWS Elastic Kubernetes Service in record time. This is an in person workshop, so if you are near SJC18 2100 University Ave, East Palo Alto, CA 94303 then check this out.

Find out more and [save your spot here](https://aws-oss.beachgeek.co.uk/22w).

**Build Flutter apps with AWS Amplify for mobile, web, and desktop platforms**
**October 17th, 11am PT**

Building cross-platform apps is becoming increasingly prominent when building products. This is due to the cost savings and operational efficiency builders get from building apps that target multiple platforms such as mobile (iOS/Android), web, and desktop (Windows, MacOS, Linux). The Amplify Libraries allow developers to connect their Flutter apps to an AWS backend for building features such as Authentication, storage, and Data interchange operations. In this session, we'll show you can quickly build a feature-rich cross-platform apps that works across mobile, web, and desktop from a single codebase that delight your customers.

You can [register for this Webinar here](https://aws-oss.beachgeek.co.uk/22v).

**Accelerating Adoption of AWS Open-Source Observability Services**
**October 20th, 9am PT**

Join this online tech talk to learn how you can leverage AWS managed open-source observability solutions to monitor your containerised or serverless workloads at scale. Unlock observability functionalities in Amazon Managed Service for Prometheus, Amazon Managed Grafana, and AWS Distro for OpenTelemetry and learn how our managed solutions can help you improve MTTD and reduce MTTR, saving you time and money. We’ll demo the Amazon Elastic Kubernetes Service Observability Accelerator and also share what’s new and upcoming in AWS Open-Source Observability.

Find out more and [register via this link](https://aws-oss.beachgeek.co.uk/22u).

**What's new in Amazon Aurora MySQL version 3**
**October 25th, 9am PT**

Amazon Aurora MySQL version 3 compatible with MySQL 8.0, is the latest version of Aurora MySQL. Come learn what makes this the best version of Aurora MySQL to run your relational database workloads. You will learn about the latest innovations in Aurora MySQL version 3 and MySQL 8.0. You will also be introduced to important and breaking behavioural changes in the new version. We will discuss the new version currency adopted with Aurora MySQL version 3 and ways to upgrade from older versions. There will also be a demo of new features like Aurora Serverless v2.

[Save your place on this online event by checking out the registration page here](https://aws-oss.beachgeek.co.uk/22x).

**AWS Elastic Kubernetes Service (EKS) Workshop**
**November 10th, London 5pm**

Join us for an interactive workshop on containers, Docker, Fargate and Amazon EKS, hosted by ClearScale and AWS. This live, virtual workshop includes three hours of interactive presentation and hands-on lab work. You will take part in the setup and deployment of containers using EKS. Follow along and work directly with AWS professionals and ClearScale (an AWS Premier Tier Services Partner) in this Level 200 training session.

You can find out more about this event by [checking out the event page and signing up](https://aws-oss.beachgeek.co.uk/22y).


**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)