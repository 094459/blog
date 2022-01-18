---
title: 'AWS open source news and updates No.44'
date: '2020-11-16'
tags : [ oss-newsletter ]
---
## November 16th - Instalment #44

Week No.44 and in a weekend just gone where Lewis Hamilton was crowned the world champion for the seventh time, it was interesting to learn that he has used the number 44 since 2014. From the grand prix to the grand prize of open source, and this week we have open source posts from a number of the AWS Hero communities, Spring Boot fans and a selection for those interested in GraphQL as well as the usual round up of projects, events and case studies. This week we have KubeCon to look forward to, so make sure you check out the AWS Container Day (details in the events section)  

Without further ado, lets begin...

**AWS Architecture Monthly - open source special**

This month's AWS Architecture Monthly has an open source special. You can check out the open source magazine (available either as a pdf which you can download or put on your kindle) [here](https://d1.awsstatic.com/whitepapers/architecture-monthly/AWS-Architecture-Monthly-November-December-2020.pdf) at [https://aws.amazon.com/whitepapers/kindle/](https://d1.awsstatic.com/whitepapers/architecture-monthly/AWS-Architecture-Monthly-November-December-2020.pdf). From Ask an Expert to case studies, reference architectures, white papers and more, there is plenty of awesome open source goodness in this issue. Many thanks for Tom Callaway for putting this together.

### Open Source Job of the Week

If you fancy working with the AWS Amplify crew, including folks such as Matt Auerbach and Nader Dabit then check out this new opening within their team. They are looking for folks excited about OSS to support Amplify developers in their GitHub repos and Discord channels. This is a great opportunity to work on the Amplify product team, and even better this is a remote role.

Details [here](https://www.amazon.jobs/en-gb/jobs/1345338/developer-support-engineer-amplify-framework) but feel free to reach out to Matt, Nader or myself.

### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to Anna Anisienia, James Randall, Valentin Radu, Tomasz Łakomy, Slobodan Stojanović, Kevin Deldycke, Jordan Guymon, Sandeep Batchu, Harish Bannai, Amandeep Bhatia, Aswin Sankarapillai, Aaron Sempf, Julian Wood, Varderes Barsegyan, Emily Doherty, Ian Mckay, Hunter Werlla, Elise Greve, Sascha Moellering, Björn Wilmsmann, Philip Riecks, Tom Hombergs, Tom Callaway and Lucas Le Ray.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

**awesome-iam**

[awesome-iam](https://github.com/kdeldycke/awesome-iam) Kevin Deldycke has put together this awesome curated list of IAM resources. So if you are looking for a comprehensive list of IAM related articles, everything from Authentication and Authorisation to Zero Trust, then check this out.

**lambda-log-shipper**

[lambda-log-shipper](https://github.com/lumigo-io/lambda-log-shipper) this open source tool from the lovely folks at Lumigo, uses the new extensions feature to trigger a new process that handles your logs and transfers to your chosen shipping method (currently Amazon S3 is available, but if you need others why not contribute or raise an issue).

**amazon-transcribe-streaming-sdk**

[amazon-transcribe-streaming-sdk](https://github.com/awslabs/amazon-transcribe-streaming-sdk) is an open source project that enables you to send an audio stream and receive a stream of text in real time, via the Amazon Transcribe service. To learn more about this SDK and how to use it, check out the blog post from Jordan Guymon, [Asynchronous Amazon Transcribe Streaming SDK for Python](https://aws.amazon.com/blogs/developer/transcribe-streaming-sdk-for-python-preview/).

**aws-config-rdklib**

[aws-config-rdklib](https://github.com/awslabs/aws-config-rdklib) is an open source Python library to enable you to run custom AWS Config Rules at scale, using Lambda Layer. Sandeep Batchu has helpfully put together this blog post, [AWS Config Rule Development Kit library: Build and operate rules at scale](https://aws.amazon.com/blogs/mt/aws-config-rule-development-kit-library-build-and-operate-rules-at-scale/) that shows you how to use the RDK to build a custom AWS Config rule and then deploy it with the RDKLib.

**aws-lambda-extensions-s3-logs-extension-demo**

s3-logs-extension-demo this new open source project shows you how you can use AWS Lambda extensions to send logs directly from Lambda to Amazon S3. Julian Wood has written up, [Using AWS Lambda extensions to send logs to custom destinations](https://aws.amazon.com/blogs/compute/using-aws-lambda-extensions-to-send-logs-to-custom-destinations/) that walks you through how you can do this, as well as provide a list of other providers where you can send your logs to.

**aws-iam-authenticator HTTP Proxy**

[aws-iam-authenticator HTTP Proxy](https://github.com/camptocamp/aws-iam-authenticator-proxy) is an open source proxy that allows external users to access an AWS EKS cluster without requiring access to AWS credentials. You are responsible for implementing whatever security measure you wish to enforce in front of it, and Raphaël Pinson has put together this blog post, [A Simple Auth Proxy for EKS](https://dev.to/camptocamp-ops/a-simple-auth-proxy-for-eks-24dh) to show you how to use it. Raphael talks about some use cases such as demos or training where this might be useful.

### AWS open source posts

**Fromer2**

[Accelerate infrastructure as code development with open source Former2](https://aws.amazon.com/blogs/opensource/accelerate-infrastructure-as-code-development-with-open-source-former2/) I am delighted to share this post from AWS Hero Ian Mckay that highlights the capabilities of Former2, an open source project that enables you to generate infrastructure as code (IaC) templates from existing AWS resources in your account. This post covers how Ian created Former2, how to use it, the challenges around it, and the future for Former2. 

![former2](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2020/11/09/ricsue_Ian-McKay_Former2_f5.png)

**Spring Boot on AWS**

[Getting started with Spring Boot on AWS: Part 1](https://aws.amazon.com/blogs/opensource/getting-started-with-spring-boot-on-aws-part-1/) and [Getting started with Spring Boot on AWS: Part 2](https://aws.amazon.com/blogs/opensource/getting-started-with-spring-boot-on-aws-part-2/) is a guest post from Björn Wilmsmann, Philip Riecks, and Tom Hombergs, authors of the book Stratospheric: From Zero to Production with Spring Boot and AWS. Spring Cloud AWS makes AWS a first-class citizen cloud provider for Spring Boot applications, and this post walks you through some examples to show you how easy it is to integrate core AWS services like SQS, S3, or the Parameter Store. Make sure you check the author's blog but also their book which looks like an essential companion for Java developers.

**Quarkus**

[Field Notes: Optimize your Java application for Amazon ECS with Quarkus](https://aws.amazon.com/blogs/architecture/field-notes-optimize-your-java-application-for-amazon-ecs-with-quarkus/) another Java related blog post, this time Sascha Moellering shows  an interesting approach to implement a Java-based application and compile it to a native image using Quarkus. Quarkus is a Supersonic Subatomic Java framework that uses OpenJDK HotSpot as well as GraalVM and over fifty different libraries like RESTEasy, Vertx, Hibernate, and Netty. Sascha's post will show you how Java applications can be implemented using Quarkus, compiled to a native-image, and then run using Amazon ECS or Amazon EKS on AWS Fargate. He also shows how you can use AWS CDK to set up the basic infrastructure. Nice post Sascha.

![arch](https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2020/11/06/faragte-cluster-1024x642.png)

**AWS Amplify**

[Integrating Existing Applications Into DevOps with AWS Amplify](https://aws.amazon.com/blogs/mobile/4707-2/) Aaron Sempf takes a brief look at the advantages of and how to integrate existing AWS resources into AWS Amplify, and the benefits AWS Amplify provides in improving the speed of which changes are deployed from developers code into the hands of the customer. For those unfamiliar with AWS Amplify, it is an open source framework that provisions and manages the resources and environments that are required for your web and mobile applications, and generates code for the application integration based on the developers’ requirements. The default implementation works with AWS, but AWS Amplify is designed to be open and pluggable for any custom backend or service.

![arch](https://d2908q01vomqb2.cloudfront.net/0a57cb53ba59c46fc4b692527a38a87c78d84028/2020/11/09/action3.png)

**Kafka**

[Streaming data to Amazon Managed Streaming for Apache Kafka using AWS DMS](https://aws.amazon.com/blogs/database/streaming-data-to-amazon-managed-streaming-for-apache-kafka-using-aws-dms/) Harish Bannai, Amandeep Bhatia, and Aswin Sankarapillai collaborate on this solution that uses an example source application (in this case a demo e-commerce application) and sets up an end ot end pipeline with the order data being persisted in an Aurora MySQL database before being replicated using the database migration service into Amazon MSK. There is lots going on in this solution, so buckle in before you start!

![arch](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2020/11/03/blogpost3.jpg)

**ROS**

[AWS Robotics announces an open source Cloud Robotics Curriculum](https://aws.amazon.com/blogs/robotics/cloud-robotics-curriculum-students-educators/) Emily Doherty announces in this post the release of an introductory Cloud Robotics Curriculum designed to help students, educators, and entry level developers build robotics applications with Robot Operating System (ROS) and AWS RoboMaker. Students can use AWS Educate and the use the curriculum materials in the Github repo [here](https://github.com/aws-robotics/aws-robomaker-robotics-curriculum).

**AWS Toolkit for Jetbrains**

[Seamlessly connect to RDS and Redshift Instances with the AWS Toolkit for JetBrains](https://aws.amazon.com/blogs/developer/seamlessly-connect-to-rds-and-redshift-instances-with-the-aws-toolkit-for-jetbrains/) Hunter Werlla writes about a recently launched feature that allows you to connect to databases instances without leaving your JetBrains IDE. The AWS Toolkit for JetBrains is a plugin for JetBrains’s IDEs that makes it easier to develop applications for AWS. Features include debugging Lambda functions locally, browsing S3 buckets, and viewing CloudWatch Logs. If you are doing databases work and using the JetBrains IDE, this post is for you.

### Partner / Industry spotlight

**SUSE**

[SUSE and AWS – 10 Years of Collaboration and Innovation](https://www.suse.com/c/suse-and-aws-10-year/) Andrew Rabin recaps the collaboration between SUSE and AWS over the past ten years: one of the first enterprise grade Linux distributions and the SAP certified workloads with SUSE. Read on to find out more as well as what you can expect to hear from them at re:Invent.

### Case Studies and Industries

**DNAnexsus**

[How DNAnexus used the open source Former2 project to create infrastructure as code templates for their disaster recovery pipeline](https://aws.amazon.com/blogs/opensource/how-dnanexus-used-the-open-source-former2-project-to-create-infrastructure-as-code-templates-for-their-disaster-recovery-pipeline/) in this guest post by Varderes Barsegyan, a former DevOps engineer at DNAnexus, outlines the solution that he created using Former2 to regularly capture and archive DNAnexus platform resources and configurations to support their disaster recovery efforts. Former2 is an open source project that allows you to generate IaC templates (for example, AWS CloudFormation or HashiCorp Terraform) from the existing resources within your AWS account (you can read a post from the author of Former2 above). The end result was reduced Recovery Time Objective (RTO). Read on to find out how.

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2020/10/23/mwweiler_DNAnexus-Former2-DR_f1.png)

### Spotlight on Startups

[Building Our Startup MVP – Why We Chose AWS Amplify](https://aws.amazon.com/blogs/mobile/building-our-startup-mvp-why-we-chose-aws-amplify/) Elise Greve provides a case study on how All of Us Financial, an online trading platform, chose AWS Amplify to build their fintech startup. It is a short post so no spoilers, and Iain Clarke the CIO of All of Us Financial provides a video commentary on this.

{% youtube XlhP8yctvng %}

### Latest blog posts

**.NET Core**

[.NET 5 – ARM vs x64 in the Cloud](https://www.azurefromthetrenches.com/net-5-arm-vs-x64-in-the-cloud/) from James Randall is this week's unexpected AWS Graviton2 benchmark blog post. James runs through two different .NET 5 workloads, a Mandelbrot and a simulated await workload and is pleasantly surprised at the end. No spoilers as you need to read James' post to get to the good stuff, but all I will say is that it looks like this is going to bring plenty of benefits to customers who end up running .NET workloads on AWS Graviton2.

![mandelbrot](https://www.azurefromthetrenches.com/wp-content/uploads/2020/11/image-1024x852.png)

**GraphQL**

We have a number of great GraphQL posts this week.

Starting off with Slobodan Stojanović, who creates a great story in this post, [The Power of Serverless GraphQL with AWS AppSync](https://serverless.pub/the-power-of-serverless-graphql-with-appsync/). This is a great primer on what GraphQL is and where and when you might use this within your own solutions, and uses a really well done narrative of every story needing a hero. I have to also say that this illustrations on this post are amazing, I really love the style Slobodan has used and I wish more posts used visuals as well done as this post. Read this post and maybe you will become that hero too.

Following that we have Lucas Le Ray and hist tutorial, [Build a Serverless GraphQL API on AWS](https://lucas-le-ray.com/blog/build-serverless-graphql-api). This post does what it says and now that you know a little more about GraphQL (previous post) you can use this to build and deploy your own GraphQL API's.  (check out Lucas' other blog posts too, he has written some great stuff)

Finally we have Tomasz Łakomy who shows you how you can power up your CV driven development :-) with, [Build a simple GraphQL server with Apollo Server and AWS CDK](https://dev.to/aws-builders/build-a-simple-graphql-server-with-apollo-server-and-aws-cdk-27jd). This post will walk you through building an AWS Lambda powered Apollo GraphQL server with AWS Cloud Development Kit (CDK). Tomasz provides full source code [here](https://github.com/tlakomy/cdk-graphql-lambda-example).  

**Conversational Standard Meta Language - CSML**

[Announcement: CSML Studio partners with Amazon Lex for the Launch of 4 new languages](https://blog.csml.dev/amazon-lex-launch-partners-csml/) Francois Falala-Sechet walks you through creating a simple French Conversational Standard Meta Language (CSML) based chat bot using Amazon Lex. This post builds upon the recent announcement of the availability of four new languages that Amazon Lex supports, including French. Whilst this post focus' on the French language, Francois also points you to an english alternative.

![arch](https://blog.csml.dev/content/images/2020/11/image-8.png)

**FastAPI**

[FastAPI + AWS = robust API](https://towardsdatascience.com/fastapi-aws-robust-api-part-1-f67ae47390f9) this is a great post from Anna Anisienia, where she walks you through the process of deploying a REST API to AWS using FastAPI, API Gateway, and AWS Lambda as well as how to package the code and create deployment pipelines. Anna goes onto deep dive and discuss how all those components work together. 

**Rust**

[AWS Lambda + Rust](https://dev.to/rad_val_/aws-lambda-rust-292g) Valentin Radu provides a very quick introduction on how to start working with Rust on AWS Lambda. I find these posts super helpful for getting a quick way to understand the key concepts.

### Quick updates

**Apache httpd**

[How do I tune memory allocation for an Apache web server running on an Amazon EC2 Linux instance? ](https://aws.amazon.com/premiumsupport/knowledge-center/ec2-apache-memory-tuning/)  If you are running Apache web servers in your environment then check out this post from the AWS Premium support team that show you how to optimise your memory configurations so you can avoid some common issues and errors that you may see in your logs.

**Container Networking**

Amazon VPC Container Networking Interface (CNI) Plugin version 1.7 is now the default for newly created Amazon EKS clusters. Version 1.7 of the open source Amazon VPC CNI plugin includes support for pod security groups, and an update to automatically detect new IP address ranges added to existing VPCs without requiring a plugin restart. Additionally, v1.7 includes performance enhancements for iptables rules and controller upgrades, and a number of bug fixes that improve the overall reliability and performance of networking for Amazon EKS clusters. To learn more, see the Amazon VPC CNI v1.7 [release notes](https://github.com/aws/amazon-vpc-cni-k8s/releases/tag/v1.7.0).

**FreeRTOS**

FreeRTOS version 202011.00 is now available with refactored IoT and AWS libraries: coreMQTT, coreJSON, corePKCS11, and AWS IoT Device Shadow, in addition to the FreeRTOS kernel and FreeRTOS+TCP library. These refactored libraries have been optimized for modularity and memory usage for constrained microcontrollers, and have undergone code quality checks (e.g. MISRA-C compliance, Coverity static analysis), and memory safety validation with the C Bounded Model Checker (CBMC) automated reasoning tool. For more details on these libraries and other features of this release, see the 202011.00 release blog on FreeRTOS.org. 

FreeRTOS is an an MIT licensed open source, real-time operating system for microcontrollers that makes small, low-power edge devices easy to program, deploy, secure, connect, and manage. You can get started by downloading source code from FreeRTOS.org, GitHub, or the FreeRTOS console, and can find more information on FreeRTOS.org.

**Kubernetes and AWS App Mesh**

AWS App Mesh Controller for Kubernetes v1.2.0 is now available with support for outlier detection and configurable connections pools for circuit breaking. The AWS App Mesh Controller for Kubernetes provides a way to configure and manage AWS App Mesh using Kubernetes directly. AWS App Mesh is a service mesh that provides application-level networking to standardise how your services communicate, giving you end-to-end visibility and allowing high availability for your applications.

This update includes the ability to configure two new resiliency features for App Mesh directly from Kubernetes–outlier detection and configurable connection pools for circuit breakers. Outlier detection is a form of passive health checking that tracks the health status of individual hosts in your App Mesh service mesh, automatically rejecting endpoints that are unhealthy. Configurable connection pools for circuit breakers allow fine-tuning request concurrency so that high-throughput applications can have effective retry policies. This release also enhances the Jaeger, Prometheus, and Grafana observability integrations, making it even easier to have end-to-end visibility into your applications.

**Lustre**

Amazon FSx for Lustre, a service that provides high-performance shared storage, now supports storage quotas. With storage quotas, you can monitor and control user- and group-level storage consumption on your file systems to ensure that no user or group consumes excessive amounts of capacity. Storage quotas are ideal for storage administrators who manage multi-user file systems such as user shares for data scientists, computational engineers, and genomics researchers. Starting today, you can set and enforce storage limits based on the number of files or storage capacity consumed by a specific user or group. You can set a hard limit that denies users and groups from consuming additional storage after exceeding their quota, or set a soft limit that provides users with a grace period to complete their workloads before converting into a hard limit. To simplify file system administration, you can also monitor user- and group-level storage usage on FSx for Lustre file systems. 

**Amazon Athena**

Federated queries in Amazon Athena enable users to run SQL queries across data stored in relational, non-relational, object, and custom data sources. The feature enables customers to submit a single SQL query that scans data from multiple sources running on-premises or hosted in the cloud.  

Running analytics on data spread across applications can be complex and time consuming. Data required for analytics is often spread across relational, key-value, document, in-memory, search, graph, object, time-series and ledger data stores. To analyze data across these sources, analysts build complex pipelines to extract, transform and load data into a warehouse so that the data can be queried. Accessing data from various sources requires learning new programming languages and data access constructs. Federated SQL queries in Athena eliminate this complexity by allowing users to query the data in-place from wherever it resides. Analysts can use familiar SQL constructs to JOIN data across multiple data sources for quick analysis and store results in Amazon S3 for subsequent use. 

Athena executes federated queries using Athena Data Source Connectors that run on AWS Lambda. AWS has open sourced Data Source connectors for Amazon DynamoDB, Apache HBase, Amazon Document DB, Amazon Redshift, AWS CloudWatch, AWS CloudWatch Metrics, and JDBC-compliant relational databases such as MySQL and PostgreSQL under the Apache 2.0 license. Customers can use these connectors to run federated SQL queries in Athena across these data sources. Additionally, using Athena Query Federation SDK, developers can build connectors to any data source to enable Athena to run SQL queries against that data source. Athena Query Federation Connector extends the benefits of federated querying beyond AWS provided connectors. Since connectors run on AWS Lambda, customers do not have to manage infrastructure or plan for scaling to peak demands.

### Events for your diary

This week, don't miss KubeCon and specifically the AWS Container Day. A great line up of speakers and content.

**AWS Container Day: Kubernetes Edition**
**November 17th, 10:00am to 6:00pm EST**

Join us for AWS Container Day, a fully live, virtual day of sessions all about Amazon EKS and Kubernetes at AWS, hosted by Containers from the Couch. At this Day Zero KubeCon event, the AWS Kubernetes team will be discussing new launches, demoing products and features, covering best practices, and answering your question live on Twitch.

**Deep Dive Into AWS Nitro Enclaves**
**November 20, 2020, 11:00 AM (PT) | 2:00 PM (ET)**

AWS Nitro Enclaves enables customers to create isolated compute environments to further protect and securely process highly sensitive data such as personally identifiable information (PII), healthcare, financial, and intellectual property data within their Amazon EC2 instances. In this tech talk, we'll deep dive into Nitro Enclaves including the architecture, benefits, how it works, and the use cases when considering confidential computing.

**Virtual ROS-Industrial Conference 2020**
**December 15 - 16, 2020**

The 8th edition of ROS-Industrial Conference will be held as a virtual event. It is not only the annual community meeting for the European ROS-Industrial community but this years event is also the final event of the H2020 ROSIN project. The conference gives you the chance to see the newest technical developments and to meet people and companies, which are active in the ROS community.

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen).


