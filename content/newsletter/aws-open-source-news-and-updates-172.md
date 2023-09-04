---
title: 'AWS open source newsletter #172'
date: '2023-09-04'
tags : [ oss-newsletter, aws open source, AWS SAM, cedarpy, Cedar, AWS Lambda SnapStart, GraalVM, OpenSearch, Lustre, Kubernetes, MariaDB, MySQL, PostgreSQL, AWS Amplify, GitLab, Next.js, AWS ParallelCluster, Apache Spark, Amazon EMR, Apache Flink, Apache Airflow, Kyverno, CDK8s, sudo-rs, Sphinx]

---

## September 4th, 2023 - Instalment #172

Welcome to #172 of the AWS open source newsletter, your reliable source for all open source on AWS goodness. What do we have for you this week? Well, more new projects to check out, and plenty of fresh content on the open source projects you all love.

We have tools to help you export your DynamoDB tables as csv files, a tool that goes beyond tracking cost and actually shuts down resources to help you manage your AWS budget, a cool dashboard to help you stay on top of your EC2 configurations, a couple of useful utilities to simplify working with files on Amazon S3, and then a sample Cedar project that helps you implement a Lambda authoriser. 

Also featured in this edition is content covering open source technologies including AWS SAM, cedarpy, Cedar, AWS Lambda SnapStart, GraalVM, OpenSearch, Lustre, Kubernetes, MariaDB, MySQL, PostgreSQL, AWS Amplify, GitLab, Next.js, AWS ParallelCluster, Apache Spark, Amazon EMR, Apache Flink, Apache Airflow, Kyverno, CDK8s, sudo-rs, and Sphinx. 

Also, be sure to check out the events section as there are a few events happening this week.

**Feedback**

Before you dive in however, I need your help!  Please please please take 1 minute to [complete this short survey](https://www.pulse.aws/promotion/10NT4XZQ) and you will forever have my gratitude! 

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes:  Iliyas Maner, Sonia García-Ruiz, k.goto, Stephen Kuenzli,  Rehan van der Merwe, Josh Aas, Julian Michel, Olawale Olaleye, Shuting Zhao, Abhishek Gupta, Suman Debnath, Elliott Cordo, Channy Yun,  Le Clue Lubbe, Munish Dabra, Lucas Vieira Souza da Silva, Rajiv Upadhyay, Abdallah Shaban, Srinivas Jasti, Sheetal Joshi, Raj Ramasubbu,  Brandon Carroll, Stephen Kuenzli,  Vadym Kazulkin, and  Brad Knowles

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution. The projects mentioned here do not represent any formal recommendation or endorsement, I am just sharing for greater awareness as I think they look useful and interesting!*

#### Tools

**dynamodump**

[dynamodump](https://aws-oss.beachgeek.co.uk/37m) is a new tool from Iliyas Maner that provides a simple way to dump your AWS DynamoDB table contents to a comma separated value file.

**cdk-cost-limit**

[cdk-cost-limit](https://aws-oss.beachgeek.co.uk/37h) is a Collection of CDK Constructs to deploy Cost-Aware Self-Limiting Resources. This package lets you set spending limits on AWS. While existing AWS solutions merely alert, this library disables resources, using non-destructive operations, when budgets are hit. This library includes an Aspect and a collection of AWS CDK Level-2 Constructs. They deploy additional resources to compute real-time spending and halt resources when budgets are met (e.g. Lambda Functions reserved concurrency is set to 0). Check out the README for important details around how this works, and the potential impact for your applications. The project is looking for feedback, so take a look and let them know what you think.

**ec2-flexibility-score-dashboard**

[ec2-flexibility-score-dashboard](https://aws-oss.beachgeek.co.uk/37i) is a nice project that helps you to assess any configuration used to launch instances through an Auto Scaling Group (ASG) against the recommended EC2 best practices. It converts the best practice adoption into a “flexibility score” that can be used to identify, improve, and monitor the configurations (and subsequently, overall organisation level adoption of Spot best practices) which may have room to improve the flexibility by implementing architectural best practices.

The following illustration shows the EC2 Flexibility Score Dashboard:

![example ec2 assessment dashboard](https://github.com/aws-samples/ec2-flexibility-score-dashboard/blob/main/docs/dashboard.png?raw=true)

**aws-s3-integrity-check**

[aws-s3-integrity-check](https://aws-oss.beachgeek.co.uk/37j) this simple tool from Sonia García-Ruiz provides a Bash script to check the md5 integrity of a set of files that have previously been uploaded into an AWS S3 bucket. Detailed README on how this works together with plenty of examples and some limitations you should be aware of. 

**cls3**

[cls3](https://aws-oss.beachgeek.co.uk/37k) is a very handy tool from AWS Community Builder k.goto that helps you to CLear S3 Buckets. It empties (so deletes all objects and versions/delete-markers in) S3 Buckets or deletes the buckets themselves. You can check out the supporting blog post, [Tool for fast deletion and emptying of S3 buckets (versioning supported)](https://aws-oss.beachgeek.co.uk/37l)

### Demos, Samples, Solutions and Workshops

**cedarpy-example-hello-photos**

[cedarpy-example-hello-photos](https://aws-oss.beachgeek.co.uk/37g) this is a sample project that AWS Community Builder Stephen Kuenzli that provides and example of how to build a Lambda Authorizer using Cedar Policy and cedarpy. If you check out the Videos section below, you can check out the Twitch session that Stephen did with my colleague Brandon that walks you through this demo.

**kendra_retriever_samples**

[kendra_retriever_samples](https://aws-oss.beachgeek.co.uk/370) This repo contains a number of example code samples and supporting CloudFormation templates that help you  work with Langchain and Amazon Kendra. It currently has samples for working with a Kendra retriever class to execute a QA chain for SageMaker, Open AI and Anthropic providers. To help you deploy this code and help you understand how it all works, you can follow along the blog post, [Deploy self-service question answering with the QnABot on AWS solution powered by Amazon Lex with Amazon Kendra and large language models](https://aws-oss.beachgeek.co.uk/36z)

![example qna chatbot screenshot](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2023/08/11/ml-14990-image001.jpg)

### AWS and Community blog posts

**Community round up**

We have another great selection of community originated content this week, covering a broad set of open source technologies. First up is AWS Hero Rehan van der Merwe taking a look at TypeScript Remote Procedure Call (or better known as tRPC). What is it I can hear you all asking. Over-fetching and under-fetching are common issues with RESTful APIs. Like GraphQL, tRPC allows you to use TypeScript to define and get only the data you need avoiding bloated responses and duplicate requests. Rehan dives deep in his post, [AWS Lambda with tRPC and separate repos using OpenAPI](https://aws-oss.beachgeek.co.uk/378) that provides a detailed, hands on guide on how you can use tRPC, trpc-openapi (OpenAPI support for tRPC), and AWS CDK to deploy this on AWS Lambda. Be sure to check out the other posts Rehan has been publishing on this topic.

Josh Aas shared details of the first stable release of sudo-rs, a Rust rewrite of the critical sudo utility, in his post [The First Stable Release of a Memory Safe sudo Implementation](https://aws-oss.beachgeek.co.uk/379). This is a good example of the ongoing commitment from AWS to supporting  the work of the Internet Security Research Group (ISRG) to improve the memory safety of critical open source tools used by developers.

Sphinx is a great tool for writing documentation, and something that I first got to grips with when contributing to the Apache Airflow project (which I blogged about a while back). AWS Community Builder Julian Michel has put together [How to automatically release Sphinx documentation using CDK Pipelines and a custom CodeBuild image](https://aws-oss.beachgeek.co.uk/37a) that describes how to publish Sphinx projects using CDK pipelines. Very nice indeed. 

![overview of Sphinx in CDK Pipeline architecture](https://community.aws/_next/image?url=https%3A%2F%2Fcommunity.aws%2Fraw-post-images%2Fposts%2Fautomatically-release-sphinx-documentation-cdk-pipelines-custom-codebuild-image%2Fimages%2Fsphinx-documentation-architecture.png&w=1920&q=75)

Next up is Olawale Olaleye with his post, [Building an Amazon EKS Cluster Preconfigured to Run High Traffic Microservices](https://aws-oss.beachgeek.co.uk/37b) which is a nice tutorial that shows you how you can deploy high traffic Kubernetes workloads on Amazon EKS. Staying in Cloud Native land, we have Shuting Zhao who wrote, [Verifying images in a private Amazon ECR with Kyverno and IAM Roles for Service Accounts (IRSA)](https://aws-oss.beachgeek.co.uk/37c) that shows how you can securely verify your container images using Kyverno, a CNCF policy engine designed for Kubernetes. Make sure you read this one. To wrap up the Kubernetes content in this section we have my colleague Abhishek Gupta who has put togehter [Simplifying Your Kubernetes Infrastructure With CDK8s](https://aws-oss.beachgeek.co.uk/37d), that shares details from his talk on how you can use CDK for Kubernetes, or CDK8s,  an open-source CNCF project that helps represent Kubernetes resources and application as code (not YAML!). There is not enough content on this project, so make sure you check that out too.

To finish up this weeks community round up, we have a couple of data related posts. First up is my good friend Suman Debnath who has put together, [The Ultimate Guide to Running Apache Spark on AWS](https://aws-oss.beachgeek.co.uk/37e) where he helps you explore the various decision-making questions to help developers navigate the options and choose the most suitable AWS service for your Spark workloads. Finally we have AWS Hero Elliott Cordo who writes about one of my favourite open source projects, Apache Airflow, in [ The Wrath of Unicron - When Airflow Gets Scary](https://aws-oss.beachgeek.co.uk/37f). And whilst this does sound like an episode of Star Trek, I can assure you it is well worth reading as it provides a nice approach on how you can SNS and SQS to orchestrate your workflows across orchestrators (multiple Airflow environments). Whilst this might not be suitable for every use case, posts like this provide useful ideas to keep in your back pocket should the need arise.

**Apache Flink**

I was super happy with the announcement last week that we renamed Amazon Kinesis Data Analytics to Amazon Managed Service for Apache Flink. The name change is effective in the AWS Management Console, documentation, and service webpages. There are no other changes, including to service endpoints, APIs, the AWS Command Line Interface (AWS CLI), the AWS Identity and Access Management (IAM) access policies, Amazon CloudWatch metrics, or the AWS Billing console dashboard. Your existing applications will continue to work as they did previously. My colleague Channy Yun has put together everything you need to know in the blog post, [Announcing Amazon Managed Service for Apache Flink Renamed from Amazon Kinesis Data Analytics](https://aws-oss.beachgeek.co.uk/36v)

![aws console rename for apache flink](https://d2908q01vomqb2.cloudfront.net/da4b9237bacccdf19c0760cab7aec4a8359010b0/2023/08/16/2023-amazon-managed-service-apache-flink-1.jpg)

**Apache Spark**

In [Monitor Apache Spark applications on Amazon EMR with Amazon Cloudwatch](https://aws-oss.beachgeek.co.uk/373) Le Clue Lubbe demonstrates how to publish detailed Spark metrics from Amazon EMR to Amazon CloudWatch. By default, Amazon EMR sends basic metrics to CloudWatch to track the activity and health of a cluster. Spark’s configurable metrics system allows metrics to be collected in a variety of sinks, including HTTP, JMX, and CSV files, but additional configuration is required to enable Spark to publish metrics to CloudWatch. Read this post to see how you can configure those metrics, and produce nice. looking dashboards in Amazon CloudWatch. [hands on]

![example CloudWatch dashboard from Apache Spark data](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2023/08/08/BDB-3297-dashboard-screenshot-executors.png)

There was more content on this topic last week, and in Monitor your [Databricks Clusters with AWS managed open-source Services](https://aws-oss.beachgeek.co.uk/377) Munish Dabra, Lucas Vieira Souza da Silva, and Rajiv Upadhyay explored how you can leverage AWS managed open-source services to monitor your Apache Spark workloads running on Databricks clusters. [hands on]

![overview of dashboard for databricks workloads ](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2023/08/22/figure5-dashboard-1.png)

**Other posts and quick reads**

* [Detect real users with AWS Amplify and Face Liveness](https://aws-oss.beachgeek.co.uk/371) provides a nice demo and walkthrough of how to setup the Amplify Face Liveness component using Next.js and a REST API, an AWS Amplify  component that helps verify if your app is being used by real users [hands on]
* [Bursting your HPC applications to AWS is now easier with Amazon File Cache and AWS ParallelCluster](https://aws-oss.beachgeek.co.uk/372) walks you through the features of File Cache (a high-speed cache on AWS to facilitate efficient file data processing, regardless of its storage location) that are important for HPC environments, and shows you, step-by-step, how you can quickly deploy this and try it out for yourself [hands on]

![architecture of using Amazon File Cache and AWS ParallelCluster](https://d2908q01vomqb2.cloudfront.net/e6c3dd630428fd54834172b8fd2735fed9416da4/2023/08/30/CleanShot-2023-08-30-at-13.30.08.png)

* [Monitor real-time Amazon RDS OS metrics with flexible granularity using Enhanced Monitoring](https://aws-oss.beachgeek.co.uk/374) provides more monitoring goodness this week, showing you how you can use a feature of Amazon RDS called Enhanced Monitoring, that provides an additional layer of telemetry, which can be useful during investigations that require highly granular monitoring data [hands on]
* [Generate security insights from Amazon Security Lake data using Amazon OpenSearch Ingestion](https://aws-oss.beachgeek.co.uk/375) explores how you can use the Open Cybersecurity Schema Framework, an open standard for storing security events in a common and shareable format, in combination with OpenSearch to generate actionable insights from your security events [hands on]

![dashboard in opensearch showing security data](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2023/08/24/10.png)

* [Setting Up OpenID Connect with GitLab CI/CD to Provide Secure Access to Environments in AWS Accounts](https://aws-oss.beachgeek.co.uk/376) provides a breakdown between three methods for connecting GitLab CI/CD pipelines to AWS, that as your team implements new CI/CD pipelines with AWS or hardens the security of existing pipelines, you can evaluate the tradeoffs based on your organisational goals and security needs. [hands on]

![setting up openid with gitlab on aws info graphic](https://d2908q01vomqb2.cloudfront.net/77de68daecd823babbb58edb1c8e14d7106e83bb/2023/08/04/GitLab-OIDC-CI-CD-6.png)

### Quick updates

**PostgreSQL**

Amazon Relational Database Service (RDS) for PostgreSQL now supports the Rust programming language as a new trusted procedural language in PostgreSQL major versions 13 and 14, expanding support for Rust from major version 15. This helps you build high performance user-defined functions to extend PostgreSQL for compute-intensive data processing.  Rust combines the performance and resource efficiency of compiled languages like C with mechanisms that limit the risks from unsafe memory use. As a PostgreSQL trusted procedural language, PL/Rust provides memory safety so that an unprivileged user can run code in the database with minimal risk of crashing the database due to a software defect that corrupts memory. Developers can also package PL/Rust code as a Trusted Language Extension for PostgreSQL to run on Amazon RDS.

PL/Rust version 1.2.3 with crate support for aes, ctr, and rand is available on database instances in Amazon RDS running PostgreSQL 13.12 and higher, PostgreSQL 14.9 and higher, and 15.2-R2 and higher in all applicable AWS Regions

**AWS Amplify**

Android, Swift, and Flutter libraries now support Time-Based One-time Passwords (TOTP) as a multi-factor authentication (MFA) method. This feature enables developers to provide their users with a secure option for validating a user’s identity after they provide their username and password. Users of apps with TOTP enabled can register their apps with an Authenticator app such as Google Authenticator, Authy, or the Microsoft Authenticator app. After a user provides their username or password, they would then be presented with a challenge to complete their sign in by providing the code generated by their Authenticator app.

Check out the blog post [AWS Amplify supports Time-Based One-Time Password (TOTP) for MFA on Android, Swift, and Flutter](https://aws-oss.beachgeek.co.uk/36w), where Abdallah Shaban provides a hands on guide through this new feature. [hands on]

![demo of aws amplify and totp](https://d2908q01vomqb2.cloudfront.net/0a57cb53ba59c46fc4b692527a38a87c78d84028/2023/08/26/totp-flutter.gif)

**Kubernetes**

The Amazon VPC Container Networking Interface (CNI) Plugin now supports the Kubernetes NetworkPolicy resource. Customers can use the same open-source Amazon VPC CNI to implement both pod networking and network policies to secure the traffic in their Kubernetes clusters. This reduces the need to run additional software for network access controls and will work alongside all existing VPC CNI capabilities.

By default, in Kubernetes, any pod can talk to any other pod within a cluster with no restriction. For better network isolation, Kubernetes NetworkPolicy allows cluster administrators to secure access to and from applications by defining which entities a pod is allowed to communicate with and vice-versa. However, this requires customers to use additional software to implement NetworkPolicy, often resulting in operational overhead and cost to install and maintain those third party plugins.

With support for NetworkPolicy in Amazon VPC CNI, customers running Kubernetes on AWS can now allow or deny traffic between their pods based on label selectors, namespaces, IP blocks, and ports with minimal overhead. With native VPC integration, they can secure their applications using standard components including security groups, and network access control lists (ACL), as part of additional defence-in-depth measures. In addition, customers can trace and troubleshoot configured policies at a cluster and node level using the Amazon VPC CNI plugin. Starting with VPC CNI v1.14, NetworkPolicy support is available on new clusters running Kubernetes version 1.25 and above but turned off by default at launch.

Srinivas Jasti and Sheetal Joshi have put together a detailed blog post, [Amazon VPC CNI now supports Kubernetes Network Policies](https://aws-oss.beachgeek.co.uk/36x) where they demonstrate how you can enforce fine-grained control over communication, isolate workloads, and enhance the overall security of your AWS Kubernetes clusters—all without the need to manage third-party network policy plugins.

**MySQL and MariaDB**

Amazon Relational Database Service (Amazon RDS) Optimized Writes now supports m6i and m6g database (DB) instances. With Amazon RDS Optimized Writes you can improve the write throughput for Amazon RDS for MySQL and MariaDB workloads by up to 2x at no additional cost. This is especially useful for write-intensive database workloads, commonly found in applications such as digital payments, financial trading, and online gaming.

In MySQL or MariaDB, you are protected from data loss due to unexpected events, such as a power failure, using a built-in feature called the “doublewrite buffer” that takes up to twice as long, consumes twice as much I/O bandwidth, and reduces the throughput and performance of your database. Amazon RDS Optimized Writes protects you from data loss by writing only once. With Optimized Writes you can improve write throughout by up to 2x at no additional cost.

Amazon RDS Optimized Writes is available as a default option from RDS for MySQL version 8.0.30 and higher, and RDS for MariaDB version 10.6.10 and higher.

**Lustre**

Amazon FSx for Lustre, a fully managed service that makes it easy and cost effective to launch, run, and scale the world’s most popular high-performance file system, now supports project quotas. With project quotas, you can group multiple files or directories on your file system into a project, and monitor storage consumption on a per-project basis. Project quotas are ideal for storage administrators who manage file systems that serve multiple projects or teams who want to ensure that no project exceeds its allocated storage capacity.

Until today, you could set and enforce user- and group-level storage consumption using user quotas and group quotas. With project quotas, you can also set and enforce storage limits based on the number of files or storage capacity consumed by a specific project. You can set a hard limit to prevent projects from consuming additional storage after exceeding their project quota, or set a soft limit that provides users with a grace period to complete their workloads before converting into a hard limit. 
Support for project quotas is now available at no additional cost on all Amazon FSx for Lustre file systems running on Lustre version 2.15.

**OpenSearch**

AWS User Notifications lets you centrally setup and view notifications from AWS services, such as Amazon OpenSearch Service, AWS Health events, Amazon CloudWatch alarms, or EC2 Instance state changes, in a consistent, human-friendly format. Last week it was announced that you could now integrate Amazon OpenSearch Serverless with AWS User Notifications. OpenSearch Serverless is the serverless option for Amazon OpenSearch Service that makes it simple for you to run search and analytics workloads without having to think about infrastructure management.

If you are looking for more details on how you might implement this, then Raj Ramasubbu has you covered in his post, [Monitoring Amazon OpenSearch Serverless using AWS User Notifications](https://aws-oss.beachgeek.co.uk/36y).

![example aws user notification integration with aws opensearch](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2023/08/29/BDB-3638-image008.png)

### Videos of the week

**Building a simple Lambda Authorizer using cedarpy**

Join my colleague Brandon Carroll and AWS Community Builder Stephen Kuenzli as they take a look at building an AWS Lambda authoriser using Stephen's open source project, cedarpy. This is something I featured in last weeks newsletter, and that I used my self in my own Python based application.

Check it out over at Twitch, [on this link](https://www.twitch.tv/aws/video/1907340509?filter=archives&sort=time).

**How to reduce cold starts for Java Serverless applications in AWS**

Check out Vadym Kazulkin's session at FroSCon as he looks at the best practices, features and possibilities AWS offers for the Java developers to reduce the cold start times like GraalVM Native Image and AWS Lambda SnapStart based on CRaC (Coordinated Restore at Checkpoint) project.

{{< youtube gdlY_8Ur1q4 >}}

**Level Up with AWS SAM: The Ultimate Serverless Toolkit!**

One for all you .NET developers, Brad Knowles takes you on a journey of introducing the AWS Serverless Application Model (SAM) toolkit into your serverless development workflow. You will see how you can take a C# .NET API from File...New Project to a fully deployed AWS application using Amazon API Gateway, AWS Lambda, and Amazon DynamoDB. While it may seem like magic, Brad digs into the details to demystify that magic so you walk away with a full understanding of the process. No application development journey is complete without testing. AWS SAM has you covered here as well. This session explores SAM's secret weapon to aid in keeping that dev-test-deploy feedback loop as tight as possible. Great stuff!

{{< youtube 6ba3mGjVGLs >}}

**Open Source Brief**

Now featured every week in the AWS Community Radio show, grab a quick five minute recap of the weekly open source newsletter from yours truly. Last week's issue is featured in this video.

{{< youtube v1ZNYlifBV0 >}}

Check out the [playlist here](https://aws-oss.beachgeek.co.uk/359).

**Build on Open Source**

For those unfamiliar with this show, Build on Open Source is where we go over this newsletter and then invite special guests to dive deep into their open source project. Expect plenty of code, demos and hopefully laughs. We have put together a playlist so that you can easily access all (sixteen) of the episodes of the Build on Open Source show. [Build on Open Source playlist](https://aws-oss.beachgeek.co.uk/episodes).

We are currently planning the third series - if you have an open source project you want to talk about, get in touch and we might be able to feature your project in future episodes of Build on Open Source.

# Events for your diary

This week, check out the Developer Webinar series, where we have three great open source topics for you. It is online, so there is still time for you to check it out. 

If you are planning any events in 2023, either virtual, in person, or hybrid, get in touch as I would love to share details of your event with readers. 

**Developer Webinar Series, Open Source At AWS**
**Online, 7th September 11am - 2pm AEST**

As part of the Developer Webinar series, we are delighted to showcase three sessions that look at open source on AWS. We have Aish Gunasekar who will be talking about "Leveraging OpenSearch for Security Analytics". I will be doing a talk on Cedar, in my session "Next generation Authz with Cedar", and to wrap things up we have Keita Watanabe who will be looking at "Scaling LLM/GenAI deployment with NVIDIA Triton on Amazon EKS". The sessions are technical deep dives, and there will be Q&A as well.

Jump over to the [registration page and sign up](https://aws-oss.beachgeek.co.uk/34j), and hope to see many of you there.

**Building ML capabilities with PostgreSQL and pgvector extension**
**YouTube, 14th September 4pm UK time**

Generative AI and Large Language Models (LLMs) are powerful technologies for building applications with richer and more personalized user experiences. Application developers who use Amazon Aurora for PostgreSQL or Amazon RDS for PostgreSQL can use pgvector, an open-source extension for PostgreSQL, to harness the power of generative AI and LLMs for driving richer user experiences. Register now to learn more about this powerful technology.

Watch it [live on YouTube](https://aws-oss.beachgeek.co.uk/325).

**Build ML into your apps with PostgreSQL and the pgvector extension**
**YouTube, 21st September 4pm UK time**

This office hours session is a follow up for those who attended the fireside chat titled "Building ML capabilities into your apps with PostgreSQL and the open-source pgvector extension". Others are also welcome. Office hours attendees can ask questions related to this topic. Application developers who use Amazon Aurora for PostgreSQL or Amazon RDS for PostgreSQL can use pgvector, an open-source extension for PostgreSQL, to harness the power of generative AI and LLMs for driving richer user experiences. Join us to ask your questions and hear the answers to the most frequently asked questions about the pgvector extension for PostgreSQL.

Watch it [live on YouTube](https://aws-oss.beachgeek.co.uk/326).

**Open Source Summit, Europe**
**September 19th-21st, Bilboa Spain**

"Open Source Summit is the premier event for open source developers, technologists, and community leaders to collaborate, share information, solve problems, and gain knowledge, furthering open source innovation and ensuring a sustainable open source ecosystem. It is the gathering place for open-source code and community contributors." You will find AWS as well as myself at Open Source Summit this year, so come by the AWS booth and say hello - from the glimpses I have seen so far, it is going to be awesome! Find out more at the official site, [Open Source Summit Europe 2023](https://aws-oss.beachgeek.co.uk/31f).

**OpenSearchCon**
**Seattle, September 27-29, 2023**

Registration is now open source OpenSearchCon. Check out this post from Daryll Swager, [Registration for OpenSearchCon 2023 is now open!](https://aws-oss.beachgeek.co.uk/2zk) that provides you with what you can expect, and resources you need to help plan your trip.

**CDK Day, 2023**
**Online, 29th September 2023**

Back for the fourth instalment, this Community led event is a must attend for anyone working with infrastructure as code using the AWS Cloud Development Kit (CDK). It is intended to provide learning opportunities for all users of the CDK and related libraries. The event will be live streamed on YouTube, and you check more at the website, [CDK Day](https://aws-oss.beachgeek.co.uk/fr) 

**Open Source India**
**October 12-13th, NIMHANS Convention Center, Bengaluru**

One of the most important open source events in the region, Open Source India will be welcoming thousands of attendees all to discuss and learn about open source technologies. I will be there too, doing a talk so I would love to meet with any of you who are also planning on attending. Check out more details on their web page, [here](https://aws-oss.beachgeek.co.uk/31d).

**All Things Open**
**October, 15th-17th, Raleigh Convention Center, Raleigh, North Carolina**

I will be attending and speaking at All Things Open, looking at Apache Airflow as an container orchestrator. I will be there with a bunch of fellow AWS colleagues, and I hope to meet some of you there. Check us out at the AWS booth, where you will find me and the other AWS folk throughout the event. Check out the event and sessions/speakers at the official webpage for the event, [AllThingsOpen 2023](https://aws-oss.beachgeek.co.uk/31e)
 
**Cortex**
**Every other Thursday, next one 16th February**

The Cortex community call happens every two weeks on Thursday, alternating at 1200 UTC and 1700 UTC. You can check out the GitHub project for more details, go to the [Community Meetings](https://aws-oss.beachgeek.co.uk/2h5) section. The community calls keep a rolling doc of previous meetings, so you can catch up on the previous discussions. Check the [Cortex Community Meetings Notes](https://aws-oss.beachgeek.co.uk/2h6) for more info.

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)

### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)