---

title: 'AWS open source news and updates #131'
date: '2022-10-17'
tags : [ oss-newsletter, aws open source, re:Invent, PostgreSQL, AWS SAM, Apache Iceberg, Apache Kafka, Karpenter, AWS CDK, kubectl, Open Telemetry, AWS IoT Greengrass, KubeCon, Amazon EMR, Hive Tez, Apache Spark, zstd ]

---

## October 17th, 2022 - Instalment #131

Welcome to the AWS open source newsletter, edition #131. This week's new projects include "metahub", a command line way to interact with AWS Security Hub, "somod" a framework for creating micro applications in serverless, "terraform-aws-guardduty-multiaccount" a Terraform module to help you automate your AWS Guard Duty configuration, "aws-glue-cdk-cicd" a sample project to automate the creation data pipelines using AWS Glue, "go-kafka-event-source" an Apache Kafka client in Go, "project-tools" a tool to help you get insights from your GitHub repo, "eks-event-watcher" a command line tool to tail your Amazon EKS logs, "listmonk-based-edm-solution" an example of how to deploy this open source mailing list tool, and many more.

From projects to blog posts, we have another broad selection of great AWS and Community posts covered that include content that features PostgreSQL, AWS SAM, Apache Iceberg, Apache Kafka, Karpenter, AWS CDK, kubectl, Open Telemetry, Hive Tez, Apache Spark, zstd, and more.

Finally, make sure you check out this weeks videos and review the event listings. Speaking of which, there are a couple of big events around that I want to cover off fist.

**KubeCon**

With KubeCon happening next week, find out what you can expect to see from AWS by checking out this post from Avichal Chum and Phil Estes. In [Top AWS Open Source Talks at KubeCon + CloudNativeCon 2022](https://aws-oss.beachgeek.co.uk/259) they share what is happening on the AWS booth and the main conference breakout sessions. Also, if you are going, make sure you check out the Event section below - the Open Source After Dark party is running again. We held this at KubeCon Valencia and it was superb, so it is something you do not want to miss. The party is invite only so reserve your spot (link in the Events section below)

**re:Invent**

If you are going to re:Invent, you can now log in and reserve sessions. If you want a handy way to look at all the amazing open source sessions, then check out this [dashboard](https://aws-oss.beachgeek.co.uk/252) [sign up required]. Would love to hear which ones you are excited about so please let me know in the comments or via Twitter.

**Feedback**

Please let me know how we can improve this newsletter as well as how AWS can better work with open source projects and technologies by completing [this very short survey ](https://eventbox.dev/survey/NUSZ91Z)that will take you probably less than 30 seconds to complete. Thank you so much!

**Celebrating open source contributors**

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created. 

So thank you to the following open source heroes: Olly Pomeroy, Praseeda Sathaye, Valentin Widmer, Shardul Srivastava, Deniz Parmaksız, Allan Chua, Michele Mancioppi, Yvo van Zee, Saravanan Gnanaguru, Ali Alemi, Kurt Tometich, Phil Estes, Avichal Chum, Kurt Tometich, Stewart Smith, Murali Krishna, Jeff Marcinko, Brian Zambrano, Eric Johnson, and Gabriel Soltz.

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution.*

#### Tools

**go-kafka-event-source**

[go-kafka-event-source](https://aws-oss.beachgeek.co.uk/25p) is a Go/Kafka client library for developing event sourcing applications. GKES (Go Kafka Event Source) attempts to fill the gaps ub the Go/Kafka library ecosystem. It supplies EOS (Exactly Once Semantics), local state stores and incremental consumer rebalancing to Go Kafka consumer applications, making it a viable alternative to a traditional Kafka Streams application written in Java.

**somod**

[somod](https://aws-oss.beachgeek.co.uk/25d) this project gets its name from Serverless Optimized MODule. SOMOD is a framework to create reusable micro applications using serverless technologies. The framework helps to develop, build and merge multiple micro applications to create a complete solution. The [documentation](https://aws-oss.beachgeek.co.uk/25e) and examples resources provide a selection for you to get started.

**metahub**

[metahub](https://aws-oss.beachgeek.co.uk/25c) is a new open source project from Gabriel Soltz, a command-line utility for AWS Security Hub. MetaHub is a command line utility for AWS Security Hub that lets you work with multiple standards, multiple checks, and thousands of findings in a very simple and advanced way by sorting, aggregating, filtering, and updating your data. In addition, MetaHub adds MetaChecks, an effortless and flexible way to do any tests on top of your resources to improve the level of confidence in your findings.

**terraform-aws-guardduty-multiaccount**

[terraform-aws-guardduty-multiaccount](https://aws-oss.beachgeek.co.uk/25f) is a Terraform module can be used to implement AWS GuardDuty in a multi-account setup. That is designating a GuardDuty delegated admin account and then configuring the rest of GuardDuty in such account.

**project-tools**

[project-tools](https://aws-oss.beachgeek.co.uk/25o) is a neat tool fro the OpenSearch project that helps you create metrics reports on a bunch of things such as Pull Request stats, Contributor Lists, Contributor Stats, Issues and more. If you are looking to automate the reporting of your repo, check this tool out.

**eks-event-watcher**

[eks-event-watcher](https://aws-oss.beachgeek.co.uk/25q) Currently in Amazon EKS, the event TTL is set to 60m. Some customers have shown interest to increase the TTL. (aws/containers-roadmap#785). It will be an additional burden if EKS control plane provided the option to increase TTL as this will add load to ETCD and storage. This solution here tries to bridge the gap to capture events beyond 60 minutes to CloudWatch, if the customers still achieve the same. That way control plane event TTL is not modified but at the sametime, if customer wanted to capture the events beyond 60m, they could achieve the same.

![architecture of eks-event-watcher](https://user-images.githubusercontent.com/1725781/184262584-24302dee-2bf6-409e-9de5-c48a5578661c.jpg)

### Demos, Samples, Solutions and Workshops

**listmonk-based-edm-solution**

[listmonk-based-edm-solution](https://aws-oss.beachgeek.co.uk/25k) helps you deploy listmonk on AWS. [listmonk](https://aws-oss.beachgeek.co.uk/25l) is a standalone, self-hosted, newsletter and mailing list manager. It looks pretty nice, and this solution uses Amazon Simple Email Service (Amazon SES) as an email sending platform and integrates a simple and clear operation interface. Users do not need to know about functions of Amazon Web Services. All deployments and installations can be completed with one click, and they can enjoy 62,000 free emails per month on Amazon SES. The solution can easily manage mailing lists, subscribers, email templates, campaigns, and features statistics and multilingual support to help users achieve business success.

![architecture overview of listmonk deployment](https://github.com/aws-samples/listmonk-based-edm-solution/blob/main/resource/Architecture.png?raw=true)

**land-rdbms-to-data-lake-at-scale**

[land-rdbms-to-data-lake-at-scale](https://aws-oss.beachgeek.co.uk/25g) provide some sample code to help you build your data lake on AWS. When you look to build a data lake on AWS, a common data ingestion pattern is to use AWS Glue to perform extract, transform, and load (ETL) jobs from relational databases to Amazon Simple Storage Service (Amazon S3). A project often involves extracting hundreds of tables from source databases to the data lake raw layer. To walk you through the code, check out the accompanying blog post, [Land data from databases to a data lake at scale using AWS Glue blueprints](https://aws-oss.beachgeek.co.uk/25h)

![architecture diagram for land-rdbms](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2022/10/03/BDB1902.jpg)

**aws-glue-cdk-cicd**

[aws-glue-cdk-cicd](https://aws-oss.beachgeek.co.uk/25i) this repository demonstrates building a Continuous Integration and Continuous Delivery (CI/CD) pipeline using AWS CodeCommit, AWS CodeBuild and AWS CodePipeline to provision AWS Glue based data pipelines using AWS Cloud Development Kit (CDK).

The AWS CDK based solution deploys a CI/CD pipeline using AWS CodeCommit, AWS CodeBuild and AWS CodePipeline, executes docker based PyTests and deploys a data pipeline using AWS Glue. The data pipeline consists of AWS Glue Workflow, Triggers, Jobs and Crawlers. The data pipeline uses COVID-19 Harmonized Data managed by Talend / Stitch to construct a data pipeline.

![architecture diagram of glue cdk](https://github.com/aws-samples/aws-glue-cdk-cicd/blob/main/images/architecture-diagram.png?raw=true)

### AWS and Community blog posts

**zstd**

[Zstandard](https://aws-oss.beachgeek.co.uk/25n), or [zstd](https://aws-oss.beachgeek.co.uk/25n) as short version, is a fast lossless compression algorithm, targeting real-time compression scenarios at zlib-level and better compression ratios. In this post, [Reducing AWS Fargate Startup Times with zstd Compressed Container Images](https://aws-oss.beachgeek.co.uk/25m) Olly Pomeroy how to use zstd-compressed container images to reduce the time taken to start containerised workloads running on AWS Fargate. Very cool post indeed. [hands on]

**Apache Iceberg**

Apache Iceberg is an open source high-performance format for huge analytic tables. Iceberg brings the reliability and simplicity of SQL tables to big data. In this case study, [Apache Iceberg Reduced Our Amazon S3 Cost by 90%](https://aws-oss.beachgeek.co.uk/254), Deniz Parmaksız shares just why you should starting looking at open source technologies such as Apache Iceberg to enable more cost effective data analytics solutions (as well as providing other features too). This is a great primer post for those wanting to know more.

![overview of apache iceberg](https://miro.medium.com/max/1400/1*QP0D_ZRv_B0HmnIXt7PMeA.png)

**Apache Kafka**

In the post, [Split your monolithic Apache Kafka clusters using Amazon MSK Serverless](https://aws-oss.beachgeek.co.uk/258) Ali Alemi looks at how splitting Apache Kafka clusters helps improve the security, performance, scalability, and reliability of your overall data streaming services and applications.

![apache kafka splitting mono](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2022/10/03/bdb-2557-write-read-clusters.png)

**Tekton**

Canary deployment is a deployment strategy that releases a new software version in production by slowly rolling out the change to a small subset of users. Praseeda Sathaye and Valentin Widmer have collaborated on this post, [Canary Testing with AWS App Mesh and Tekton](https://aws-oss.beachgeek.co.uk/25j) where they show you a preview of the talk they will be giving at KubeCon, and provide a hands on guide on how you can automate changes and use popular open source tools such as Tekton and Helm to create some abstractions. [hands on]

![image of tekton canary deployment](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2022/10/06/app-mesh-solution-design-1024x628.png)

**AWS SAM**

We have a couple of posts this week covering AWS Serverless Application Model (SAM).

First up we have Kurt Tometich who writes about AWS SAM Connector in hist post, [Simplifying serverless permissions with AWS SAM Connectors](https://aws-oss.beachgeek.co.uk/25a). AWS SAW Connector simplifies permission management between serverless components and this post explores how you can speed up serverless development while maintaining secure best practices using AWS SAM Connector. [hands on]

![overview of components in aws sam connector](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2022/10/12/Screen-Shot-2022-10-12-at-10.26.26-AM.png)

Following that we have Allan Chua who writes, [An Opinionated View of AWS SAM Connectors](https://aws-oss.beachgeek.co.uk/253) where he provides his take on AWS SAM Connectors, constructs designed to reduce the complexity of authoring IAM permissions that adhere to the least privilege principles. He provides some in depth examples and wants to know if you are using AWS SAM Connectors, for your feedback.

**Open Telemetry**

Normally I feature blog posts, but in a break from tradition, I stumbled upon this excellent presentation, [Open Telemetry on AWS](https://aws-oss.beachgeek.co.uk/250) from Michele Mancioppi from Lumigo after reading the always excellent weekly Observability newsletter, [o11y.news](https://aws-oss.beachgeek.co.uk/24z) from Michael Hausenblas (make sure you subscribe, the content is always excellent).

**AWS Community Builder round-up**

Here are some posts from rhe AWS Heroes and Community Builders communities I though were well worth highlighting this week.

* [Scaling in EKS with Karpenter - Part 1](https://aws-oss.beachgeek.co.uk/255) Shardul Srivastava walks you through an overview of what Karpenter is and how it is different to other things you might have used, and then shows you with a hands on example setting this up. If you are looking to test this out, why not take a look at this post [hands on]
* [Securing CDK pipelines in an enterprise organization](https://aws-oss.beachgeek.co.uk/256) Yvo van Zee blogs about a presentation given at the AWS Community Day in the Netherlands, so if you missed it, then make sure you read this post on what to look out for when using and deploying using AWS CDK
* [Introduction to Kubectl CLI Plugins ctx and ns](https://aws-oss.beachgeek.co.uk/257) Saravanan Gnanaguru provides his insights into what and how to use plugins when using the kubectl tool for managing Kubernetes. A quick read that summarises things nicely, and looks at two specific plugins [hands on]

**Other posts and quick reads**

* [Developing a Remote Job Monitoring Application at the edge using AWS IoT Greengrass](https://aws-oss.beachgeek.co.uk/25b) a two part, hands on post that shows a UI application at the edge, jointly developed by AWS Professional Services and AWS Partner, TensorIoT, for remote industrial job monitoring and processing [hands on] 

### Quick updates

**Bottlerocket**

[Bottlerocket v1.10.0](https://aws-oss.beachgeek.co.uk/25r) was released this week. Check out the release notes to review all the OS, Orchestrator, Build, Documentation and Platform changes.

**Amazon EMR**

Last week it was announced that you can now monitor and debug jobs in EMR Serverless using native Apache Spark & Hive Tez UIs. The Apache Spark & Hive Tez UIs present visual interfaces with detailed information about your running and completed jobs. You can dive into job-specific metrics and information about event timelines, stages, tasks, and executors for each job.

After you submit a job to an EMR Serverless application, you can view the real-time Spark UI or the Hive Tez UI for the running job from the EMR Studio console or request a secure URL using the GetDashboardForJobRun API. For completed jobs, you can view the Spark History Server or the Persistent Hive Tez UI from the EMR Studio Console.

**PostgreSQL**

The AWS JDBC Driver for PostgreSQL is now generally available for use with your Amazon RDS or Amazon Aurora PostgreSQL-compatible edition database clusters. This wrapper driver is designed to work with the PostgreSQL community driver and provide improved failover handling for clustered databases such as Aurora PostgreSQL. The AWS JDBC Driver for PostgreSQL is drop-in compatible with your existing applications because it adds failover functionality alongside the community driver, reducing the need for you to make application changes. This release replaces the standalone AWS JDBC Driver for PostgreSQL previously released as a preview.

The wrapper driver minimizes failover time by monitoring database cluster status and caching the cluster’s topology. The cache is then used to improve DNS name resolution speed if a node fails, reducing failover time from minutes to seconds. It is an open-source project that uses the Apache License v2 and can be installed using Maven, Gradle, or by .jar file.

**AWS Serverless Application Model (SAM)**

Serverless application developers can now use the new AWS::Serverless::Connector resource available in AWS Serverless Application Model (AWS SAM) to simplify granting the appropriate level of access to the resources in their application’s infrastructure. With AWS::Serverless::Connector resources, developers describe how data and events need to flow between two resources and the type of access required. AWS SAM will compose purpose-built AWS Identity and Access Management (AWS IAM) policies in order to facilitate the interaction defined by the developer in the connector resource.

By using the AWS::Serverless::Connector resource, serverless application developers can quickly compose or update well-scoped IAM policies to their application, speeding up application development while reducing the IAM expertise required. The AWS::Serverless::Connector resource will transform into purpose-built IAM policies, using Read or Write permissions specified by the developer to compose the IAM policies from pre-defined sets of policy actions. Customers can use their existing policy review processes by reviewing a AWS CloudFormation change set or processed CloudFormation template prior to deployment.

### Videos of the week

**OpenSearch**

Fresh from the SDC (Storage Developer Conference) Murali Krishna presents this deep dive on the background of OpenSearch, the search engine storage structure, the need for remote storage, and also addresses design considerations and future-facing work.

{{< youtube S5e5fDRq8yA >}}


**Amazon Linux**

Stewart Smith from AWS presents how Amazon is working with Fedora to develop the latest version of Amazon Linux.

{{< youtube OZ_yeaAFTYM >}}


**AWS SAM**

Jeff Marcinko and Brian Zambrano join Eric Johnson to show how to use nested stacks to turbo charge your application lifecycle management when deploying complex serverless applications. See how AWS SAM Accelerate speeds up deployment from your local system by bypassing AWS CloudFormation to deploy code and resource updates when possible.

{{< youtube A9hk50R_jck >}}


**Build on Open Source**

We have put together a playlist so that you can easily access all episodes of the Build on Open Source show. For those unfamiliar with this show, it is where we go over this newsletter and then invite special guests to dive deep into their open source project. Expect plenty of code, demos and hopefully laughs.

[Build on Open Source playlist](https://aws-oss.beachgeek.co.uk/24u)

# Events for your diary

**Hacktoberfest**

Our friends at Steampipe are participating in Hacktoberfest this year, and have put together a page on how you can earn swag for contributions. Check it out for more details, [Hacktoberfest 2022: Steampipe](https://aws-oss.beachgeek.co.uk/24t)

**Build on AWS with Quarkus Workshop**
**Saturday, Oct 15th 3 - 9 pm CET**

"Build on AWS with Quarkus Workshop", with Julio Faerman, is a 100% practical, full-day workshop to get YOUR web application started and running on AWS, using modern Java with Quarkus and other open-source technologies. We'll start from scratch and build a sample application, step by step, so do not worry if you're new to Java or Cloud Computing. All you'll need is a web browser, an AWS account and your desire to build.

Check out more details and save your place, by heading over to the [Build on AWS with Quarkus Workshop landing page](https://aws-oss.beachgeek.co.uk/23z).

**Build Flutter apps with AWS Amplify for mobile, web, and desktop platforms**
**October 17th, 11am PT**

Building cross-platform apps is becoming increasingly prominent when building products. This is due to the cost savings and operational efficiency builders get from building apps that target multiple platforms such as mobile (iOS/Android), web, and desktop (Windows, MacOS, Linux). The Amplify Libraries allow developers to connect their Flutter apps to an AWS backend for building features such as Authentication, storage, and Data interchange operations. In this session, we'll show you can quickly build a feature-rich cross-platform apps that works across mobile, web, and desktop from a single codebase that delight your customers.

You can [register for this Webinar here](https://aws-oss.beachgeek.co.uk/22v).

**AWS Community Day**
**Dresden, Germany 19th October**

Check out this all day AWS Community driven and run event that features plenty of open source technologies. From open observability, AWS CDK, GitOps using Argo, there are is something for everyone. If you are in Dresden Germany, one to check out.

Find out the full schedule and sign up by checking out the [welcome page here](https://aws-oss.beachgeek.co.uk/240).

**Accelerating Adoption of AWS Open-Source Observability Services**
**October 20th, 9am PT**

Join this online tech talk to learn how you can leverage AWS managed open-source observability solutions to monitor your containerised or serverless workloads at scale. Unlock observability functionalities in Amazon Managed Service for Prometheus, Amazon Managed Grafana, and AWS Distro for OpenTelemetry and learn how our managed solutions can help you improve MTTD and reduce MTTR, saving you time and money. We’ll demo the Amazon Elastic Kubernetes Service Observability Accelerator and also share what’s new and upcoming in AWS Open-Source Observability.

Find out more and [register via this link](https://aws-oss.beachgeek.co.uk/22u).

**Build on AWS Open Source**
**October 21st, 9am BST**

Join us for the fifth episode of the Build on AWS series, featuring a live round up of the latest projects and news as well as a special guest speaker. We have another special guest lined up, more details to follow. Follow the show on @buildonopen for more details. Check it out on https://twitch.tv/aws

**KubeCon and CloudNativeCon North America**
**October 24th-28th, Detroit USA**

Check out this blog post from Nathan Taber, [AWS at KubeCon + CloudNativeCon North America 2022](https://aws-oss.beachgeek.co.uk/243) to hear more about what you can expect from AWS at this event, including Container Day. If you are going check this post out to see how you can reserve a spot to speak with one of the AWS specialists who will be at the booth.

![open source after dark picture](https://pbs.twimg.com/media/Fe4LAcZWYAEtoMh?format=jpg&name=small)

If you are attending KubeCon, make sure you do not miss the legendary Open Source After Dark party. You can expect lots of fun activities, great food, music and lots more. Make sure you register to save your spot, as spaces will be limited. Register and relax in the comfort of having your place saved [by heading over to this page.](https://aws-oss.beachgeek.co.uk/251)

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