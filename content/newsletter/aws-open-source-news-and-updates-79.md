---
title: 'AWS open source news and updates #79'
date: '2021-08-27'
tags : [ oss-newsletter, AWS Open Source ]
---
## August 27th, 2021 - Instalment #79

Newsletter #79.

The combination of having been away on PTO for the past few weeks, and this coming Monday being a national holiday in the UK, I thought I would post the newsletter today. Covering nearly three weeks, a lot has happened so there is a lot to cover. 

We have 17 new open source projects and solutions, including EventBridge Canon, an essential project if you are working with event driven architectures on AWS, kics a security scanning tool for your IaC,  open source solutions such as aws-security-analytics-bootstrap and amazon-msk-with-apache-kafka-streams-api, and other new projects like aws-python-utilities, snap-xcompile, riFT,  rds_iamauth_proxy, aws-simple-websocket, ecs-external-instance-network-sentry and more.

We have a wide selection of great blog posts/tutorials too, with Apache Airflow, Redis, OpenTelemetry having several great posts and walk throughs. Other topics covered this week include Amundsen, Prometheus, AWS CDK, OpenSearch, Apache ActiveMQ, Apache Jena, Apache Spark, Suricata, Spring Boot, PostgreSQL, and for folks interested in all things containers, we have Bottlerocket, Docker and Kubernetes updates and posts.

We will resume with the Monday releases next time.

**Feedback**

Please let me know how you found this newsletter - how could I improve it or what would you like to see that is not currently covered? It will take you all of 60 seconds, so [Take the Survey](https://eventbox.dev/survey/6JGUUJK) (the first 20 will get $25 AWS credit codes too!)

**Job of the Week**

[Principal Technical Product Manager, Amazon Corretto](https://aws-oss.beachgeek.co.uk/tz)

Amazon Corretto is a public distribution of OpenJDK as well as the primary Java distribution used by Amazon's own developers. Many of AWS's and Amazon's signature service run on the Java runtime, you will have a direct opportunity to influence them in this role.

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: David Boyne, Nomaan Butt, Seth Miller, Harinder Seera, Gus Verdun, Peter Hanssens, Don Simpson, Evan Diewald, Arun Donti, Jeroen Reijn, Aleksandr Filichkin, Shiva Vaidyanathan, Rashpal Kler, Matt Cline, Ulili Nhaga, Hendrik Schoeneberg, Junjie Tang, Adam Andrews, Chris Smith, Eli Fisher, Carl Meadows, Jules Graybill, Kyle Davis, Mehul Shah, Virendhar Sivaraman, Kishan Desai, Zach Gardner, Danilo Poccia, Qu Chen, Asaf Porat Stoler, Jim Gallagher, Nathaniel Braun, Hrvoje Grgic, Mart Noten, Aru Petchimuthu, Laura Dawson, Maish Saidel-Keesing, Adi Singh, Alex Pulver, Srikanth Kodali, Drew Dennis, Olly Pomeroy, Jesus Escudero Lopez, Javier Martin, Pinglei Guo, Min Xia, Karen Xu, Kelvin Lo, Mike George, Seth Dobson, Paul Ramsey, Sheetal Joshi, Shibo Wang, Avnish Jain, Melody Yang, Shiva Achari, Daniel Maldonado, Igor Izotov, Dipankar Kushari, Gaurav Gundal, Naveen Madhire, Ashok Padmanabhan, Aubrey Oosthuizen and Gary Stafford.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest open source projects

**eventbridge-canon**

[eventbridge-canon](https://aws-oss.beachgeek.co.uk/u7) David Boyne has put together another great open source tool, EventBridge Canon. This tool helps you manage and publish events into EventBridge. You can create Events and publish them into EventBridge and reuse previous events too. Make sure you read the launch post, [Introducing EventBridge Canon](https://aws-oss.beachgeek.co.uk/ua). This weeks project of the week, so make sure you check it out.

**ecs-external-instance-network-sentry**

[ecs-external-instance-network-sentry](https://aws-oss.beachgeek.co.uk/tv) this open source tool is something that I will be looking at having experimented with ECS Anywhere recently. eINS provides an additional layer of resilience for ECS external instances in deployment scenarios where connectivity to the on-region ECS control-plane may be unreliable or intermittent.

![demo](https://raw.githubusercontent.com/aws-samples/ecs-external-instance-network-sentry/main/images/eins-no-connectivity-v0.01.png)

**kics**

[kics](https://aws-oss.beachgeek.co.uk/tw) this open source tool from Checkmarx will help you to find security vulnerabilities, compliance issues, and infrastructure misconfigurations early in the development cycle of your infrastructure-as-code. KICS stands for Keeping Infrastructure as Code Secure, and supports AWS CloudFormation, Terraform, Kubernetes and more. This should definitley be on your "check out"/"to do" list.

**nitro-enclave-tensorflow**

[nitro-enclave-tensorflow](https://aws-oss.beachgeek.co.uk/sq) This open source repository from Evan Diewald is a great sample/demo to show you how you can use the power of AWS Nitro Enclaves to run confidential machine learning inference. To help you get this project up and running, make sure you read the post, [Privacy Preserving Deep Learning with AWS Nitro Enclaves](https://aws-oss.beachgeek.co.uk/sr).

**amazon-api-gateway-cors-configurator**

[amazon-api-gateway-cors-configurator](https://aws-oss.beachgeek.co.uk/t8) this open source project  helps you properly configure CORS for Amazon API Gateway and HTTP APIs. The CORS configurator assumes you are using AWS SAM to build an API Gateway endpoint with a proxy integration to an AWS Lambda function. Eric Johnson has put together this blog post, [Configuring CORS on Amazon API Gateway APIs](https://aws-oss.beachgeek.co.uk/t7) to help walk you through how this works.

![cors](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2021/08/16/Screen-Shot-2021-08-16-at-1.23.51-PM.png)

**snap-xcompile**

[snap-xcompile](https://aws-oss.beachgeek.co.uk/t9) this new open source tool enables you to cross-compile snaps for x86_64 and arm64 machines using remote AWS buildfarms. The ability to cross-compile deployable assets is key to development workflows in IoT, robotics, and other embedded systems. In this post from Adi Singh, [Snap xCompile: An AWS tool for cross-compiling snaps privately](https://aws-oss.beachgeek.co.uk/ta) you can explore this tool in more detail, walking through how to xCompile an example project. 

**aws-security-analytics-bootstrap**

[aws-security-analytics-bootstrap](https://aws-oss.beachgeek.co.uk/tb) this new open source solution enables customers to perform security investigations on AWS service logs by providing an Amazon Athena analysis environment that's quick to deploy, ready to use, and easy to maintain. To find out more, including use cases and a walk through of how to get started, check out the blog post from Ryan Smith and Mohit Gadkari, [Introducing AWS Security Analytics Bootstrap](https://aws-oss.beachgeek.co.uk/tc)

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/08/11/smthyym_security_analytics_bootstrap_f1-1024x874.png)

**amazon-msk-with-apache-kafka-streams-api**

[amazon-msk-with-apache-kafka-streams-api](https://aws-oss.beachgeek.co.uk/te) this is an open source solution that shows you how you can build a real-time stream processing application using Amazon MSK, AWS Fargate and the Apache Kafka Streams API. To help you, follow along in the blog post [Power your Kafka Streams application with Amazon MSK and AWS Fargate](https://aws-oss.beachgeek.co.uk/tf) by Karen Grygoryan

**print**

[print](https://aws-oss.beachgeek.co.uk/tu) Gus Verdun has put together this open source project to help simplify how you can deploy static files to AWS S3 and CloudFront. This tool keeps track of the file time stamps that have been uploaded and only uploads files that have been touched since the last time the tool was run.

**awsboilerplate**

[awsboilerplate](https://aws-oss.beachgeek.co.uk/u9) if you are looking for a quick way to set up a starter environment, then check this project out. It provides a complete starter kit to get your project live on AWS in minutes and a CICD pipeline to allow you to move quickly. From getting started and running locally to being able to deploy this to AWS using an automated pipeline, well worth checking this out.

![arch](https://raw.githubusercontent.com/geod/awsboilerplate/master/documentation/AWS-Boilerplate-Architecture.jpg) 

**aws-simple-websocket**

[aws-simple-websocket](https://aws-oss.beachgeek.co.uk/u8) if you are looking for a quick sample project to use as a baseline for experimenting with websockets on AWS, this project from 
Seth Miller uses AWS's API Gateway + Lambda to run a simple websocket application. 

![demo](https://github.com/four43/aws-simple-websocket/blob/master/docs/example.gif?raw=true)

**riFT**

[riFT](https://aws-oss.beachgeek.co.uk/tx) - in my experience, many open source projects are born out of past experiences, putting together something to fix/improve/address a gap. Nomaan Butt has created riFT, an open source tool that provides elastic EC2 instance monitoring tool that put cost first. It has some nice integration with Microsoft Teams that allows you to send notifications/reports directly, or email if you prefer that.

![arch](https://github.com/buttnomaan9/riFT/blob/main/backend/images/dynamic_ec2_monitor.png?raw=true)

**rds_iamauth_proxy**

[rds_iamauth_proxy](https://aws-oss.beachgeek.co.uk/u0) if you work with Amazon RDS then this open source tool is going to be of interest to you. This project from Gold Fig Labs developed in Rust provides a Postgres proxy which allows tools that don't natively supports IAM auth to connect to AWS RDS instances.

**serverless-rds-proxy-demo**

[serverless-rds-proxy-demo](https://aws-oss.beachgeek.co.uk/uh) this project demos the benefits of using RDS proxy with serverless workloads that depend on relational database like RDS Aurora. It shows end to end automated setup of RDS Aurora(Mysql) with RDS proxy. Basic serverless architecture is set up using API gateway HTTP API and Lambda Functions.

![arch](https://github.com/aws-samples/serverless-rds-proxy-demo/blob/main/images/architecture.png?raw=true)

**Diggie**

[Diggie](https://aws-oss.beachgeek.co.uk/u6) if you have begun using/experimenting with OpenSearch, this project will be of interest. Diggie is a GUI client for OpenSearch, providing a desktop app for Mac / Windows environments that makes operating with OpenSearch easier. This project is currently a developer preview version.

![demo](https://raw.githubusercontent.com/DiggieApp/Diggie/master/diggie.gif)

**cdk-pipelines-github**

[cdk-pipelines-github](https://aws-oss.beachgeek.co.uk/u4) this is an experimental library, that will help you to deploy CDK applications through GitHub workflows. An overview of how this works and how you can use it is provided in the docs, as well as a list of what does and does not currently work.

**aws-python-utilities**

[aws-python-utilities](https://aws-oss.beachgeek.co.uk/u3) I only discovered this GitHub repo from 
Harinder Seera this week, and it is his collection of Python utilities for AWS. These utilities help save time with different facets (RCA/reporting/cost saving) of performance testing. You can use these stand alone, or as part of your automated developer workflows.


### AWS and Community blog posts

**Amundsen**

Amundsen is an open source metadata and data lineage tool that helps you easily trace data lineage from source to dashboard. I was very happy to see this post, [Building a data discovery solution with Amundsen and Amazon Neptune](https://aws-oss.beachgeek.co.uk/ti) from AWS Hero Peter Hanssens and Don Simpson from AWS, showing you how you can deploy this and provides a sample walkthrough taking some data from a number of AWS services and then exploring them in the Amundsen dashboard. This is a must read post this week for Data nerds. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2021/08/05/DBBLOG-1499-image003.png)

**GraalVM**

Aleksandr Filichkin takes AWS Lambda cold start challenges in his post, [GraalVM + AWS Lambda or solving Java cold start problem](https://aws-oss.beachgeek.co.uk/ub). In this study, Aleksandr benchmarks a sample book microservice, and provides source code so you can try this for yourself. To find out more, read the post. This graph should tempt you.

![graph](https://miro.medium.com/max/1400/1*j-Su8oeM-tr6du1c1HjeMw.png)

**OpenSearch**

[Keeping clients of OpenSearch and Elasticsearch compatible with open source](https://aws-oss.beachgeek.co.uk/sx) the OpenSearch crew, Eli Fisher, Carl Meadows, Jules Graybill, Kyle Davis, and Mehul Shah share an important update for developers who use any number of the clients to work with OpenSearch or Elasticsearch. With some recent changes to some of the client libraries, this could impact your applications ability to interact with OpenSearch or Elasticsearch so make sure you read this post and check out the new forks of some of the client libraries.

**Apache Airflow**

We had a number of Apache Airflow posts over the past few weeks (and some really nice ones coming soon as well, so keep a look out for them too).

First up we have, [Field Notes: Deploying Autonomous Driving and ADAS Workloads at Scale with Amazon Managed Workflows for Apache Airflow](https://aws-oss.beachgeek.co.uk/su) where Hendrik Schoeneberg, Junjie Tang, and Adam Andrews share a sample solution of how Apache Airflow is used to help orchestrate the image data collection and processing you see in autonomous driving workloads. This is a deep dive with resources provided so you can try this out for yourself/ [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2021/07/22/Architecture-for-Deploying-Autonomous-Driving-ADAS-workloads-at-scale.jpg)

Next up we have a great post from Virendhar Sivaraman and Kishan Desai, [Bolster security with role-based access control in Amazon MWAA](https://aws-oss.beachgeek.co.uk/sy) that takes a deep dive on how you can ensure that the tasks you create in Apache Airflow use role based access controls and fine-grained IAM task roles to support least privilege access for your tasks. [hands on]

![explain](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2021/07/29/BDB-1448-image002-1.jpg)

**Apache Jena**

[Introducing Graph Store Protocol support for Amazon Neptune](https://aws-oss.beachgeek.co.uk/sv) Chris Smith takes a look at how you can use the built in support of Graph Store Protocol within [Apache Jena](https://aws-oss.beachgeek.co.uk/sw), when creating applications that work on highly connected datasets on Amazon Neptune. Graph Store Protocol support in Amazon Neptune provides efficient methods to interact with complete named graphs within a Resource Description Framework (RDF) dataset. Apache Jena is a popular open-source Java framework for building RDF graph applications that makes extensive use of Graph Store Protocol behind the scenes.

**Apache Spark**

Following from a [previous post](https://dev.to/aws/aws-open-source-news-and-updates-77-3bog) I covered in the last newsletter, we have Melody Yang, Shiva Achari, Daniel Maldonado, and Igor Izotov who collaborated on, [Run a Spark SQL-based ETL pipeline with Amazon EMR on Amazon EKS](https://aws-oss.beachgeek.co.uk/tq) building on the first post, show you how you can use Arc, an open source  framework for defining predictable, repeatable and manageable data transformation pipelines, to managed your Spark applications declaratively, a widely accepted best practice. Using Amazon EMR on EKS, running your applications that are built upon that declarative framework maximises data process productivity, performance, reliability, and availability at scale. This pattern abstracts Spark technology away from you, and helps you to focus on deliverables that optimise business outcomes. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2021/07/08/bdb1267-new-solution-diag.png)

We also had this post, [Run and debug Apache Spark applications on AWS with Amazon EMR on Amazon EKS](https://aws-oss.beachgeek.co.uk/u1) from Dipankar Kushari, Gaurav Gundal, Naveen Madhire, and Ashok Padmanabhan which is a really great introduction in how you can get started with Apache Spark  on Amazon EMR when using Amazon EKS. It walks you through setting up an EMR cluster on EKS, using a sample application using the NOAA weather data set - all resources are available in the GitHub repo so you can try this yourself and use this as a baseline for your own projects. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2021/08/13/BDB-1277-image002.png)

**Big Data - Debezium/Apicurio and Apache Kafka**

When it comes to Big Data blog posts, I always enjoy working through Gary Staffords posts. In his latest, [Hydrating a Data Lake using Log-based Change Data Capture (CDC) with Debezium, Apicurio, and Kafka Connect on AWS](https://aws-oss.beachgeek.co.uk/uc), building on from an earlier post (that you should also check out) this post dives deep into log-based CDC as a marked improvement over query-based CDC to continuously stream changes from the PostgreSQL database to your data lake.  Gary explores a number of open source technologies, performing log-based CDC using Debezium, storing messages as Apache Avro, with Avro message schemas stored in Apicurio Registry. This is what you will build following this post:

![arc](https://miro.medium.com/max/700/1*TpXpTlb8Y_Z6PIhdkl52Pw.png)

**Apache ActiveMQ**
 
Dominic Gagné and Mithun Mallick have come together to create this post, [Authenticating and authorizing Amazon MQ users with Lightweight Directory Access Protocol](https://aws-oss.beachgeek.co.uk/tg). Read on to find out more on Amazon MQ’s authentication and authorisation model. It covers the steps you need in order to set up Microsoft Active Directory as they authenticated user store for Amazon MQ. [hands on]

**Redis**

Over the last week or so, we announced a new AWS service called Amazon MemoryDB. This is a new Redis compatible, durable, in-memory database. In the launch post, [Introducing Amazon MemoryDB for Redis – A Redis-Compatible, Durable, In-Memory Database Service](https://aws-oss.beachgeek.co.uk/sz) colleague Danilo Poccia shares details about this new service, including how it compares with other Redis services such as Amazon ElastiCache for Redis. 

Zach Gardner followed that post with, [Build with Redis data structures for microservices using Amazon MemoryDB for Redis and Amazon ECS](https://aws-oss.beachgeek.co.uk/t0) which provides a practical application and example of how you might use this to increase the performance of your applications (in this instance, using a sample container application running on Amazon ECS.

![arch](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2021/08/20/dbblog-1828-image005-1.png)

If you find yourself wanting to access your Amazon ElastiCache Redis clusters in private subnets, then Hrvoje Grgic and Mart Noten have you covered in the post, [Use AWS Systems Manager Session Manager for port forwarding to Amazon ElastiCache for Redis inside a private subnet](https://aws-oss.beachgeek.co.uk/t2). Using AWS Systems Manager as well as HAProxy, to seamlessly forward ports from a local development machine to a provisioned bastion host. In this way, you obtain access to reach all other private resources in your VPC without exposing any surface in your cloud infrastructure to attack. This post provides source code which you can use to implement or change to suit your needs. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2021/08/02/SSMBlog_Architecture.png)

To finish up the Redis posts this week we have a great post from Qu Chen, Asaf Porat Stoler, Jim Gallagher, and Nathaniel Braun, [Best practices: Redis clients and Amazon ElastiCache for Redis](https://aws-oss.beachgeek.co.uk/t1). In this post, they cover best practices for interacting with Amazon ElastiCache for Redis resources with commonly used open-source Redis client libraries. Make sure you read it to avoid some of the pitfalls, and ensure you make the best use of Redis within your applications.

**Suricata**

Suricata is an open source threat detection engine that provides capabilities including intrusion detection, intrusion prevention and network security monitoring. AWS Network Firewall uses Suricata  to provide network protections for all of your Amazon Virtual Private Clouds (VPCs). Another open source project, Squid Proxy can also be used to provide some of the capabilities. In the post, [Migrating from Squid Web Proxy to AWS Network Firewall](https://aws-oss.beachgeek.co.uk/st) Shiva Vaidyanathan and Rashpal Kler share some of the common architectures that use Squid Proxy, and how you might move/migrate these to AWS Network Firewall.

![arch](https://d2908q01vomqb2.cloudfront.net/5b384ce32d8cdef02bc3a139d4cac0a22bb029e8/2021/08/19/Picture1-7.png)

**Bottlerocket**

Bottlerocket is a free and open-source Linux-based operating system meant for hosting containers. In this post, [A deep dive into Bottlerocket ECS Updater](https://aws-oss.beachgeek.co.uk/td) by Maish Saidel-Keesing, you will find out more how the service works, and how updates are applied in Bottlerocket. [hands on]

![demo](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2021/08/09/image-2021-08-09T105533.028.png)

**Docker**

A couple of Docker related posts that I found interesting. First up, we have [Deploy a Docker application on AWS Elastic Beanstalk with GitLab](https://aws-oss.beachgeek.co.uk/tj) a blog post from Srikanth Kodali and Drew Dennis that shows you how to deploy a Docker-based Node.js application on Elastic Beanstalk with GitLab’s DevOps platform. Source code provided so you can follow along and use as a base for your own projects. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/7719a1c782a1ba91c031a682a0a2f8658209adbf/2021/08/09/Picture1-3.png)

Up next we have [Migrating from Docker Swarm to Amazon ECS with Docker Compose](https://aws-oss.beachgeek.co.uk/tk) from Olly Pomeroy and Jesus Escudero Lopez who show you how to use Docker Compose as a migration tool, moving a workload from Docker Swarm to Amazon ECS. [hands on]

**gRPC**

gRPC is an open-source framework designed to efficiently connect services, sending messages via a compact binary format called Protocol Buffers, or protobuf. It is often used to improve speed and efficiency of how microservices communicate. In this blog post, [Build Next-Generation Microservices with .NET 5 and gRPC on AWS](https://aws-oss.beachgeek.co.uk/ss) Matt Cline and Ulili Nhaga share how AWS supports gRPC through building a sample .NET micro service running on AWS Graviton2 instances. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/7719a1c782a1ba91c031a682a0a2f8658209adbf/2021/08/17/next-generation-microservices-dotnet-grpc-grpc-architecture.png)

**Spring Boot**

Jeroen Reijn has put together this blog post, [Deploying Spring Boot applications to AWS App Runner with AWS CodePipeline](https://aws-oss.beachgeek.co.uk/ui) that walks you through how you can take a Spring Boot application and deploy it via AWS App Runner, a container service that lets deploy your application in minutes without setting up any infrastructure.

**Prometheus**

Another excellent post from John Preston, in his latest post titled [AWS ECS & CloudWatch with Prometheus](https://aws-oss.beachgeek.co.uk/tt) he dives deep and shares how to funnel your Prometheus captured metrics into AWS CloudWatch metrics. John has put together some great open source projects to make your life easy, and in this post he shows how you can use one of those tools (ECS Compose-X) to configure this and reduce the complexity. In the blog post he shows you how to set this up with Apache Kafka, exporting the Java JMX metrics so you can then access them in CloudWatch. Very nice! [hands on]

![arch](https://labs.compose-x.io/_images/ECSCWInsightsPrometheus.png)

**OpenTelemetry**

Over the past couple of weeks there have been a number of OpenTelemetry posts. AWS Distro for OpenTelemetry (ADOT) is a secure and supported distribution of the APIs, libraries, agents, and collectors defined in the OpenTelemetry Specification.

In [Introducing CloudWatch Container Insights Prometheus Support with AWS Distro for OpenTelemetry on Amazon ECS and Amazon EKS](https://aws-oss.beachgeek.co.uk/tl), Javier Martin, Pinglei Guo, and Min Xia how to setup and use AWS Distro for OpenTelemetry (ADOT) to monitor Prometheus metrics for Amazon ECS and Amazon EKS on CloudWatch Container Insights. 

In [Deployment patterns for the AWS Distro for OpenTelemetry Collector with Amazon Elastic Container Service](https://aws-oss.beachgeek.co.uk/tn), Mike George takes a look at two patterns for deploying ADOT and the AWS OpenTelemetry Collector and the implications and considerations you need to think about.

Following that we have a collaboration between Seth Dobson (Southwest Airlines) and Paul Ramsey and Sheetal Joshi from AWS with [Implementing CloudWatch-centric observability for Kubernetes-native developers in Amazon Elastic Kubernetes Service](https://aws-oss.beachgeek.co.uk/to) where they show how to build an end-to-end, CloudWatch-centric observability solution using a number of open source tools such as the OpenTelemetery collector and Fluent Bit. They provide a GitHub repo with code so you can try this out for yourself. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/08/13/sheetjos_cloudwatch_eks_f1_x700.png)

Next up we have [Adding security workflows to OpenTelemetry](https://aws-oss.beachgeek.co.uk/tm) from Karen Xu and Kelvin Lo, who share their experiences working in the OpenTelemetry project, in this case to apply/reinforce security best practices - in this case specifically looking at some security workflows and how to implement status badges for the project.

If you are a PHP developer, no need to feel left out. Oliver Hamuy shared his experience of enhancing the OpenTelemetry PHP SDK to support AWS X-Ray in [Adding AWS X-Ray support to the OpenTelemetry PHP library](https://aws-oss.beachgeek.co.uk/u2)

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/08/24/hamuy_aws_xray_opentelemetry_php_f4.jpg)

The final OpenTelemetry post is [Building a Helm chart for deploying the OpenTelemetry Operator](https://aws-oss.beachgeek.co.uk/tp) from Shibo Wang who shares his experience of designing and building the OpenTelemetry Operator Helm chart and integrating the OpenTelemetry Operator into the AWS Distro for OpenTelemetry (ADOT). This open source Helm chart allows you to install the OpenTelemetry Operator to an on-premises or managed Kubernetes cluster with a one-line Helm command, and provides increased flexibility in configuring the Operator. This post walks through the design and implementation of the components and the challenges addressed along the way.

![design](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/08/13/alolitas_shibw_helm-telemetry_f6_x1000.png)

**AWS CDK**

Alex Pulver gets my "must read post of the week" award for his blog post, [Recommended AWS CDK project structure for Python applications](https://aws-oss.beachgeek.co.uk/th). As someone who has been working with AWS CDK for the past 12 months, I have learned a lot about how to structure my CDK apps when working with Python. This post puts together lots of great practical advice for Python developers, and will help supercharge your CDK applications. [hands on]

A community post from Luciano Mammino, [Provision an Ubuntu-based EC2 instance with CDK](https://aws-oss.beachgeek.co.uk/ty) provides a very nice walkthrough of how to provision Ubuntu based ECS instances (which happens to be my preferred instance type, so I will defo be using this). I really love the style of this post, including showing up issues and how he fixed them - this is something I try and do as I find that you often learn more when you need to fix things, than when things work  first time. Great stuff. [hands on]

The final AWS CDK related post this week is from Arun Donti, who writes in [Virus scan S3 buckets with a serverless ClamAV based CDK construct](https://aws-oss.beachgeek.co.uk/ug) on how to leverage an aws-cdk construct that uses the open source ClamAV® antivirus engine to scan new objects in Amazon S3 for viruses. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/0716d9708d321ffb6a00818614779e779925365c/2021/08/23/cdk-serverless-clamscan-architecture.png)

**PostgreSQL**

If you are looking at or thinking about migrating your PostgreSQL database, then make sure you check out this series of posts - [Upgrade your Amazon RDS for PostgreSQL database, Part 1: Comparing upgrade approaches](https://aws-oss.beachgeek.co.uk/t4). In these posts, Aru Petchimuthu dives deep into in-place and out-of-place upgrade options, weighing up their pro's and cons, and showing you how you can minimise your downtime if you have critical workloads that just cannot have downtime.

**ROS**

Aubrey Oosthuizen and Junjie Tang have put this post, [Field Notes: Deploy and Visualize ROS Bag Data on AWS using rviz and Webviz for Autonomous Driving](https://aws-oss.beachgeek.co.uk/uf) to illustrate how to deploy common tools used to visualise ROS bag files. In this particular post, they focus on one particular use case, data collected from drive data from test vehicles configured with cameras, LIDAR, GPS, and other input devices. The data for each device is stored as a topic in the ROS bag file. Developers and engineers need to visualize and inspect the contents of ROS bag files to identify issues or replay the drive data. [hands on]

![example](https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2021/08/23/figure-2-1.jpg)

### Case studies

[How governments can benefit from open source solutions to solve common challenges](https://aws-oss.beachgeek.co.uk/t3) Laura Dawson provides a round the world update on how governments are able to use open source to tackle a wide range of problems. As the post says:

> "“Open source tools allow governments to gain access to the best thinking and tools that are available and then quickly customize them to meet the needs of citizens,” 

Read the post to find out more.

### Quick updates

Lots of quick updates this week, given that a lot has happened over the past three weeks.

**PostgreSQL**

Amazon Aurora PostgreSQL-Compatible Edition now supports the oracle_fdw extension, which allows your PostgreSQL database to connect to and retrieve data stored in Oracle databases. Foreign Data Wrappers are libraries for PostgreSQL databases that can communicate with an external data source, abstracting the details of connecting to the data source and obtaining data from it. oracle_fdw is a PostgreSQL extension that provides a Foreign Data Wrapper for easy and efficient access to Oracle databases. Oracle_fdw is supported for PostgreSQL 12.7 or higher. To read more, check out the [full announcement](https://aws-oss.beachgeek.co.uk/tr).

**Parquet, Avro, ORC in Amazon Athena**

Amazon Athena now lets you store results in the format that best fits your analytics use case. Using Athena's new UNLOAD statement, you can format results in your choice of Parquet, Avro, ORC, JSON or delimited text. Athena's SQL-based interface and support for open formats are well suited for creating extract, transform, and load (ETL) pipelines that prepare your data for downstream analytics processing.

**TensorFlow 2**

AWS Neuron, the SDK for running machine learning inference on AWS Inferentia-based Amazon EC2 Inf1 instances now supports TensorFlow 2. Starting with Neuron 1.15.0 you can execute your TensorFlow 2 BERT based models on Inf1 instances with support for additional models coming soon.

We have also updated our resources with new documentation including a tutorial that help you get started with TensorFlow 2, a tutorial that will guide you on how to deploy a HuggingFace BERT model container on Inferentia using AWS Sagemaker hosting, the inference performance page to help you compare and replicate our results and a new application note to help you discover the types of deep learning architectures that will perform well out of the box on Inferentia.

Read more [here](https://aws-oss.beachgeek.co.uk/ts).

**Amazon SageMaker / Amazon Linux 2**

You can now choose Amazon Linux 2 for your new SageMaker notebook instance to take advantage of the latest update and support provided by Amazon Linux 2. To find out more, read the blog post [Amazon SageMaker notebook instances now support Amazon Linux](https://aws-oss.beachgeek.co.uk/t5) from Michael Hsieh, Jun Lyu, and Sam Liu. You can then read this blog post, [Migrate your work to an Amazon SageMaker notebook instance with Amazon Linux 2](https://aws-oss.beachgeek.co.uk/t6) that describes an approach to migrate your work from an existing notebook instance to a new notebook instance (as well as providing the resources/code you need to help) [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2021/08/18/ML-4924-image001.jpg)

**Kubernetes**

Amazon Elastic Kubernetes Service (EKS) now supports the Multus Container Networking Interface (CNI) plugin, enabling pods running in EKS clusters to attach multiple network interfaces in support of advanced networking configurations.

Multus is an open source CNI plugin for Kubernetes that enables attaching multiple network interfaces to pods. Multus acts as a meta plugin, invoking additional CNI plugins that can operate on multiple network interfaces attached to pods. Use cases that commonly require pods with multiple interfaces include running 5G and streaming networks on Kubernetes.

**AWS Copilot**

AWS Copilot announced the release of version 1.9. With this release, AWS Copilot now allows you to configure a friendly DNS name for your request driven web services deployed with AWS App Runner. This feature was already available for load balanced web services deployed with Amazon Elastic Container Service (Amazon ECS). Customers using AWS App Runner can now provide a friendly DNS name, such as api.example.com, directly in the manifest file and AWS Copilot will provision and manage the necessary infrastructure to associate the domain name with the customer’s service deployed with App Runner.
 
AWS Copilot v1.9 also adds support for creating multiple environments in the same Amazon Virtual Private Cloud (VPC). This enables customers to save costs during development stages by sharing a single VPC across multiple AWS Copilot environments. By default, AWS Copilot will continue to to create separate VPCs for each environment. Furthermore, with this release, AWS Copilot now automatically sets the Docker default platform to be linux/amd64 to improve compatibility with customers’ ARM-based machines.

**Next.js**

AWS Amplify Hosting now supports deploying and hosting server-side rendered (SSR) apps built with version 11 of Next.js with zero configuration. Amplify Hosting supports all the latest Next.js features including incremental static regeneration, automatic image optimisation, and script optimisation.

Next.js is a React framework that combines build-time static site generation (SSG) and dynamic server-side rendering (SSR) to enable developers to build performant, SEO-friendly web apps. Next.js developers can leverage all of Amplify’s build and hosting capabilities such as PR previews, easy custom domains, pattern-based branch deployments, password protection, redirects, and custom headers.

### Events for your diary

**Cloud DevSecOps with Bridgecrew and Terraform**
**8th September, 9am PST**

From scanning infrastructure as code (IaC) for security misconfigurations to implementing automated DevSecOps workflows, this workshop will provide a hands-on experience to automate your cloud security. Find out more and [register via this link](https://aws-oss.beachgeek.co.uk/ud).

**Cloud Native Day**
**23rd September, Bern Switzerland**

What is this, an in person event returning? A stellar line up including our own Michael Hausenblas, an event looking at CNCF projects and the future of IT. Find out more and to view prices/register, by clicking [here](https://cloudnativeday.ch/en/#speakers).

**GraphQL API security best practices with AWS AppSync and AWS Amplify**
**14th October, 11am AEST**

As a developer, the most important parts of managing your applications should always include enhancing performance while strengthening security. In this webinar, we take you through security best practices for your GraphQL API’s with AWS AppSync and AWS Amplify, providing you with an understanding of how these can be applied to your applications. In this session, you will learn about:

* GraphQL Protocol and how to configure a schema
* Possible ways to authenticate and authorise access to GraphQL APIs
* How to configure network security for your API
* How to enable observability for your API with logging, tracing or auditing

To [register for this event, use this link](https://aws-oss.beachgeek.co.uk/ue).

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)