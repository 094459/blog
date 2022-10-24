---

title: 'AWS open source news and updates #132'
date: '2022-10-21'
tags : [ oss-newsletter, aws open source, Red Hat Enterprise Linux, Swift, AWS Amplify, FreeRTOS, Amazon Corretto, PostgreSQL, Karpenter, Ray, EKS Blueprints, Plausible, Amazon Lightsail, cdk8s, Apache JMeter, Firecracker, FreeBSD, dotNET, Bottlerocket, Prometheus, AWS CDK, MySQL, Apache Hudi]

---

## October 21st, 2022 - Instalment #132

**Welcome**

Welcome to the AWS open source newsletter, edition #132. This newsletter was covered in last Friday's Build on Open Source, so if you missed it, don't worry as you can [view episode five of Build on Open Source](https://www.twitch.tv/videos/1630135246). In this episode special guest Abhishek Gupta walked us through how to use cdk8s using Golang, building a Wordpress site in minutes.

New projects this week include "duvet" a tool to help honour RFC in code, "aws-lambda-explorer" a gui tool to explore your AWS Lambda functions, "k3s-aws-terraform-cluster" deploy k3s on AWS via Terraform, "snow-transfer-tool" a tool to help you transfer data via Snowball devices, "amazon-emr-vscode-toolkit" a new VSCode plugin for Amazon EMR users, "aws-cdk-for-discourse" a quick way to deploy the open source discourse tool, "image-optimization" a reference example of how to do image optimising, and "gtfs-serverless-ticketing-sample" a sample application using public transport data.

We have a broad selection of written content this week, featuring open source projects that include Swift, FreeRTOS, Amazon Corretto, PostgreSQL, Karpenter, Ray, Plausible, Amazon Lightsail, cdk8s, Apache JMeter, Firecracker, FreeBSD, Bottlerocket, Prometheus, AWS CDK, MySQL, Apache Hudi, and more.

Finally, we have some great videos to watch and an updated events section. Speaking of which, we cover KubeCon and re:Invent next.

**KubeCon**

With KubeCon happening next week, find out what you can expect to see from AWS by checking out this post from Avichal Chum and Phil Estes. In [Top AWS Open Source Talks at KubeCon + CloudNativeCon 2022](https://aws-oss.beachgeek.co.uk/259) they share what is happening on the AWS booth and the main conference breakout sessions. Also, if you are going, make sure you check out the Event section below - the Open Source After Dark party is running again. We held this at KubeCon Valencia and it was superb, so it is something you do not want to miss. The party is invite only so reserve your spot (link in the Events section below)

**re:Invent**

As we get closer to re:Invent, I want to share a few things that will hopefully be of interest.

First up, we will be running the Build On Live stream throughout re:Invent and we would love to feature you! If either yourself, or perhaps you know a community member going to re:Invent and think they will absolutely love to attend the livestream, we want to hear from you. Please nominate a community member you want to hear from during Build On Live [using this survey](https://eventbox.dev/survey/6B0ED1J).

Second, check out this handy way to look at all the amazing open source sessions, then check out this [dashboard](https://aws-oss.beachgeek.co.uk/252) [sign up required]. I would love to hear which ones you are excited about so please let me know in the comments or via Twitter. If you want to hear what my top three, must watch sessions, then this is what I would attend (sadly, as an AWS employee I am not allowed to attend sessions)

1. OPN306 AWS Lambda Powertools: Lessons from the road to 10 million downloads - Heitor Lessa is going to deliver an amazing session on the journey from idea to one of the most loved and used open source tools for AWS Lambda users
2. BOA204 When security, safety, and urgency all matter: Handling Log4Shell - Cannot wait for this session from Abbey Fuller who will walk us through how we managed this incident
3. OPN202 Maintaining the AWS Amplify Framework in the open - Matt Auerbach and Ashish Nanda are going to share details on how Amplify engineering managers work with the OSS community to build open-source software

There are many other great open source sessions, and hopefully I will try and put together a more comprehensive list as approach re:Invent.


**Feedback**

Please let me know how we can improve this newsletter as well as how AWS can better work with open source projects and technologies by completing [this very short survey ](https://eventbox.dev/survey/NUSZ91Z)that will take you probably less than 30 seconds to complete. Thank you so much!

**Celebrating open source contributors**

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created. 

So thank you to the following open source heroes: Lorenzo Garuti, Chris Fregly, Ramesh Dwarakanath, Tuana Celic, Omar Sanseviero, David Tippett, Harinder Seera, Damon Cortesi, Lorena Jinchuk, Raj Seshadri, Vu Dao, Brian Graf, Colin Percival, Amit Maindola, Srinivas Kandi, and Mitesh Patel.

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution.*

#### Tools

**duvet**

[duvet](https://aws-oss.beachgeek.co.uk/263) is an open source tool from developers at AWS that extracts [RFC 2119](https://aws-oss.beachgeek.co.uk/264) requirements from IETF specifications, then generates a report on each requirement, where it is honoured in source code, as well as how that code is tested. This tool is still in beta, so if you use it please provide feedback on your experience to the project.

**aws-lambda-explorer**

[aws-lambda-explorer](https://aws-oss.beachgeek.co.uk/265) Harinder Seera has put together this graphical tool that helps you explore your AWS lambda functions. All I need now is to find a Windows machine to try it on.

![screenshot of aws lambda explorer](https://raw.githubusercontent.com/hseera/aws-lambda-explorer/main/images/aws-lambda-explorer.png)

**k3s-aws-terraform-cluster**
[k3s-aws-terraform-cluster](https://aws-oss.beachgeek.co.uk/266) Lorenzo Garuti has put together this Terraform project to help you deploy a high available K3s cluster on Amazon AWS using mixed on-demand and spot instances. K3s is a lighter weight Kubernetes distribution that you might find on IoT or edge devices, and is also optimised for Arm, so make sure to try it out on those AWS Graviton instance types.

![architecture of k3s terraform cluster](https://camo.githubusercontent.com/4fb3f48e6f7a2d93eec611e8bd14c9b6fbc8df743a45db0bf856d3d95135f78e/68747470733a2f2f6761727574696c6f72656e7a6f2e6769746875622e696f2f696d616765732f6b33732d6177732d636c75737465722e706e673f)

**snow-transfer-tool**

[snow-transfer-tool](https://aws-oss.beachgeek.co.uk/261) Migrating large amount of small files to the cloud is challenging because of the increased time to transfer and cost implications. Customers often use AWS Snowball for bulk-data migrations to the cloud when there are connectivity limitations, bandwidth constraints, and high network costs. When you transfer small files to any system there are performance implications and batching is a key solution. This tool is built on top of Yongki Kim’s [s3booster](https://aws-oss.beachgeek.co.uk/262) script to automate batching small files to improve copy performance to Snowball devices.

**amazon-emr-vscode-toolkit**

[amazon-emr-vscode-toolkit](https://aws-oss.beachgeek.co.uk/25y) is a VS Code Extension via Damon P. Cortesi that is currently in developer preview, and will make it easier to develop Spark jobs on EMR. Check out the project to see what this looks like and give it a go. Damon is looking for folks to kick the tyres of this project and provide feedback. I have a challenge coin up for grabs for the best feedback!

### Demos, Samples, Solutions and Workshops

**aws-cdk-for-discourse**

[aws-cdk-for-discourse](https://aws-oss.beachgeek.co.uk/260) Discourse is a popular open source community discussion tool. This repo contains code that demonstrates how to create a full environment for Discourse. This example will create all assets required to utilise AWS services. The Discourse site will be automatically setup with an initial admin user and an OpenID plugin is set up to allow users to register and login via Amazon Cognito. Very cool.

![architecture of discourse on aws](https://github.com/aws-samples/aws-cdk-for-discourse/blob/main/images/architecture.jpeg?raw=true)

**image-optimization**

[image-optimization](https://aws-oss.beachgeek.co.uk/25x) Images are usually the heaviest components of a web page, both in terms of bytes and number of HTTP requests. Optimizing images on your website is critical to improve your users’ experience, reduce delivery costs and enhance your position in search engine ranking. For example, Google’s Largest Contentful Paint metric in their search ranking algorithm is highly impacted by how much you optimise the images on your website. In the solution, we provide you with a simple and performant solution for image optimisation using serverless components such as Amazon CloudFront, Amazon S3 and AWS Lambda.

![architecture for image optimisation solution](https://github.com/aws-samples/image-optimization/blob/main/architecture.png?raw=true)

**gtfs-serverless-ticketing-sample**

[gtfs-serverless-ticketing-sample](https://aws-oss.beachgeek.co.uk/26l) The General Transit Feed Specification (GTFS) is a data specification that allows public transit agencies to publish their transit data in a format that can be consumed by applications. 

![architecture for gtfs solution](https://github.com/aws-samples/gtfs-serverless-ticketing-sample/blob/main/static/architecture.png?raw=true)

This repository contains the sample project called GTFS ticketing, a sample transit ticketing service that uses public GTFS data for offering transit routes to customers. You can customise this project so it uses the GTFS data of your choice, hence being able to tailor the transits that the project will offer users.

![example of application screenshot](https://github.com/aws-samples/gtfs-serverless-ticketing-sample/blob/main/static/ui-result-list.png?raw=true)

**amazon-sagemaker-deepar-mlops-pipeline-cdk**

[amazon-sagemaker-deepar-mlops-pipeline-cdk](https://aws-oss.beachgeek.co.uk/25z) this repo provides a CDK implementation that demonstrates how MLOps workflow for Time Series Forecasting with SageMaker Built-in DeepAR can be automated with AWS Serverless Services. DeepAR is a supervised learning algorithm for forecasting scalar time series, and in this particular demo, the user is building a DeepAR model with UCI Electricity Dataset.

![architecture for time series and deepar](https://github.com/aws-samples/amazon-sagemaker-deepar-mlops-pipeline-cdk/blob/main/asset/architecture.png?raw=true)

**codepipeline-for-lambda-using-cdk-constructs**

[codepipeline-for-lambda-using-cdk-constructs](https://aws-oss.beachgeek.co.uk/26k) this repo provides a sample approach to using CDK Constructs to build AWS Lambda functions by packaging them up as an OCI container image and then using this as your deployment source.

![architecture for deploying AWS lambda functions via OCI images](https://github.com/aws-samples/codepipeline-for-lambda-using-cdk-constructs/blob/main/img/cdk-constructs.png?raw=true)

### AWS and Community blog posts

**Firecracker**

AWS Hero Colin Percival put together this post and announcement in his blog, [Announcing the FreeBSD/Firecracker platform](https://aws-oss.beachgeek.co.uk/26a) adding a third operating system that you can now run - FreeBSD. Be sure to follow [this Tweet thread](https://aws-oss.beachgeek.co.uk/26b) where he provides some additional colour.

**Bottlerocket**

In the post, [Secure AWS Bottlerocket deployments on Amazon EKS with KubeArmor](https://aws-oss.beachgeek.co.uk/25w), Raj Seshadri provides a nice hands on guide on how to use KubeArmor, a cloud native solution that operates on top of AWS Bottlerocket to secure pods and containers using BPF-LSM and help you build defence in depth. BPF-LSM is a new LSM (Linux Security Modules) introduced in the newer kernels (version > 5.7). BPF-LSM allows KubeArmor to attach bpf-bytecode at LSM hooks that contains user-specified policy controls. [hands on]

![architecture of bottlerocket and kubearmor](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2022/10/19/kube-1.png)

**Apache JMeter**

Apache JMeter is an open source project that can be used as a load testing tool for analysing and measuring the performance of a variety of services, with a focus on web applications. It was the first tool I used in anger to do this many moons ago, and it remains a favourite project of mine. Lorena Jinchuk has put together this post, [How to Handle Dynamic AWS SigV4 in JMeter](https://aws-oss.beachgeek.co.uk/267) where she shares how to add an AWS SigV4 signature to your JMeter tests, so that you can test your APIs served via Amazon API Gateway. [hands on]

![Jmeter screenshot ](https://cdn2.hubspot.net/hubfs/208250/Blog_Images/sig4.png)

**Apache Hudi**

Apache Hudi is an open-source transactional data lake framework that greatly simplifies incremental data processing and streaming data ingestion. In [Get started with Apache Hudi using AWS Glue by implementing key design concepts – Part 1](https://aws-oss.beachgeek.co.uk/26j), Amit Maindola, Srinivas Kandi, and Mitesh Patel collaborate and show how you can get started with Apache Hudi, focusing on the Hudi CoW (Copy on Write) table type on AWS using AWS Glue, and implementing key design concepts for different use cases. [hands on]

![overview of process flow in Apache Hudi](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2022/10/07/image009-1-1.jpg)

**cdk8s**

[KEDA](https://aws-oss.beachgeek.co.uk/269) is an open source Kubernetes-based Event Driven Autoscaling component that allows for fine-grained autoscaling (including to/from zero) for event driven Kubernetes workloads. AWS Community Builder and prolific writer Vu Dao has put together another deep dive post, [Keda ScaledObject As Code Using CDK8S](https://aws-oss.beachgeek.co.uk/268) showing you how you can deploy this using cdk8s, an infrastructure as code tool that enables you to define your infrastructure in code - in this example, Vu uses TypeScript. In this example, he shows you how you can scale an Apache Airflow worker workload. [hands on]

![architecture overview of keda on cdk8s](https://res.cloudinary.com/practicaldev/image/fetch/s--VfjWU14P--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://raw.githubusercontent.com/vumdao/keda-hands-on/master/docs/images/keda-arch.png)

**Plausible**

The Plausible project is a simple, open-source, lightweight (< 1 KB) and privacy-friendly web analytics alternative to Google Analytics. My good friend Brian Graf who now is the Developer Advocate for Amazon Lightsail, has put together this blog post [Ditch Google Analytics for Plausible Analytics on Amazon Lightsail](https://aws-oss.beachgeek.co.uk/25v)

![illustration of plausible dashboard](https://camo.githubusercontent.com/9e9844ffbcc24afd6356c25343e958d5079f5a6016337b61ff0c77e2beb86b14/68747470733a2f2f646f63732e706c61757369626c652e696f2f696d672f706c61757369626c652d616e616c79746963732e706e67)

**.NET**

How do you decide on what to develop in your project? What about new features or improvements? Open Source has solved this by using asynchronous mechanisms such as request for design and public road maps, using documents to help community proposals for discussion and ultimately a transparent record of what has been decided. The AWS .NET team is exploring creating an AWS native framework that simplifies development of .NET message processing applications using AWS services. Check out the [Design Doc: AWS Messaging Framework](https://aws-oss.beachgeek.co.uk/25u) and have your say.

**Other posts and quick reads**

* [How to deploy CDK v2 to an account that requires boundary policies](https://aws-oss.beachgeek.co.uk/26c) shows you how you can work around IAM boundary policy issue that you might encounter and enabled AWS CDK v2 to successfully bootstrap into a new account [hands on]
* [Enhance Operational Insight by Converting the Output of any AWS SDK Commands to Prometheus Metrics](https://aws-oss.beachgeek.co.uk/26d) will walk you through using an open source tool output AWS commands and enrich your dashboards or alerts [hands on]
* [Implement RStudio on your AWS environment and access your data lake using AWS Lake Formation permissions](https://aws-oss.beachgeek.co.uk/26e) presents two ways to easily deploy and run RStudio on AWS to access data stored in data lake [hands on]
* [Minimize HPC compute costs with all-or-nothing instance launching](https://aws-oss.beachgeek.co.uk/26f) shows you how to configure ParallelCluster to use an all-or-nothing instance launch strategy, which means no instances in a multi-node job will launch unless all the instances can launch together - helping you to to prevent idle EC2 resources, and the costs associated with them [hands on]

![illustration of hpc compute post](https://d2908q01vomqb2.cloudfront.net/e6c3dd630428fd54834172b8fd2735fed9416da4/2022/09/28/CleanShot-2022-09-28-at-13.07.08.png)

* [Amazon EKS add-ons preserve customer edits](https://aws-oss.beachgeek.co.uk/26g) helps you understand how Amazon EKS add-ons can reduce the heavy-lifting required to manage common operational software in your clusters [hands on]
* [Configure a performance testing framework for Amazon Aurora PostgreSQL](https://aws-oss.beachgeek.co.uk/26h) demonstrates how you can use AWS CloudFormation, open-source Apache JMeter, and Python to generate a performance testing framework for Amazon Aurora PostgreSQL-Compatible Edition databases [hands on]

![architecture of testing solution](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2022/10/11/DBBlog2278-arch-1.jpg)

* [Migrate Google Cloud for MySQL to Amazon Aurora MySQL](https://aws-oss.beachgeek.co.uk/26i) provides an overview of how you can migrate from Google Cloud for MySQL to Amazon Aurora MySQL-Compatible Edition in an automated way and minimise downtime using AWS DMS [hands on]

![architecture of mysql migration](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2022/10/05/gcpnonssl.jpg)

### Quick updates

**Amazon Corretto**

On October 18th, 2022 Amazon announced quarterly security and critical updates for Amazon Corretto Long-Term Supported (LTS) versions of OpenJDK. Corretto 19.0.1, 17.0.5, 11.0.17, 8u352 are now available for download. Amazon Corretto is a no-cost, multi-platform, production-ready distribution of OpenJDK.

**PostgreSQL**

Amazon RDS for PostgreSQL 15 Release Candidate 2 (RC2) is now available in the Amazon RDS Database Preview Environment, allowing you to test the release candidate of PostgreSQL 15 on Amazon RDS for PostgreSQL. You can deploy PostgreSQL 15 RC2 for development and testing in the Amazon RDS Database Preview Environment without the hassle of installing, provisioning, and managing the database. 

The PostgreSQL community released PostgreSQL 15 RC2 on October 6, 2022. New features in PostgreSQL 15 RC2 include the SQL standard "MERGE" command for conditional SQL queries, performance improvements for both in-memory and disk-based sorting, and support for two-phase commit and row/column filtering for logical replication. The PostgreSQL 15 RC2 release also adds support for server-side compression with Gzip, LZ4, or Zstandard (zstd) using pg_basebackup. Please refer to the PostgreSQL community announcement for more details about the release.

The Amazon RDS Database Preview Environment supports both Single-AZ and Multi-AZ deployments on the latest generation of instance classes, and can be encrypted at rest using KMS keys. Amazon RDS Database Preview Environment database instances are retained for a maximum period of 60 days and are automatically deleted after the retention period. Amazon RDS database snapshots that are created in the preview environment can only be used to create or restore database instances within the preview environment. You can use standard PostgreSQL dump and load functionality to import or export your databases from the preview environment.

**Red Hat Enterprise Linux**

Red Hat Enterprise Linux (RHEL) Workstation for accelerated GPU instances are now available via the AWS Marketplace. RHEL Workstation is a cloud-based remote desktop solution that allows end users from anywhere in the world to access a workstation instance to do their work and collaborate with team members. RHEL Workstation is designed for advanced Linux users working on more powerful hardware, and is optimised for activities such as animation, computer-aided design and engineering, scientific research, medical imaging etc. It is delivered via NICE DCV, a secure, high-performance remote display protocol. RHEL Workstation on AWS allows customers to provide high-end hardware capabilities to a distributed workforce, without the need for large capital investments in expensive workstation equipment.

The RHEL Workstation Amazon Machine Images (AMIs) are built on RHEL version 8.6 with NICE DCV remote display software and support both Tesla and GRID NVIDIA drivers. RHEL Workstation is available on AWS Marketplace for GPU Accelerated instance families including the G3, G4dn, G5, P2, and P3 instances for Tesla drivers and G3, G4dn, G5, and P3 instances for GRID drivers. RHEL Workstation is now available in all AWS Commercial regions, and AWS provides tier 1 and tier 2 support for this product. 

**AWS Amplify Library for Swift**

This week the general availability of Amplify Library for Swift (previously Amplify iOS) was announced. This release allows Swift developers to easily build cloud-connected iOS apps. Since its Developer Preview release in April 2022, we have re-written our APIs to support idiomatic Swift features like async/await that makes it easier for developers to implement structured concurrency. We also want to take this opportunity to introduce beta availability of macOS support--one of our most requested features--with watchOS and tvOS support coming in future releases. As with the Preview, the Amplify Library for Swift is open source on GitHub, and we deeply appreciate the feedback we have gotten from the community.

Starting today, developers can use Amplify Library for Swift via the Swift Package Manager to build apps for iOS and macOS (currently in beta) platforms with Auth, Storage, Geo and more features. Developers will continue to have access to the same Command Line Interface (CLI) tools to configure and manage their cloud resources. With the Amplify Library for Swift, you will also have direct access to the underlying AWS SDK for Swift through the escape hatch to unlock additional capabilities from AWS services.

Kyle Lee has put together a blog post, [Introducing the AWS Amplify Library for Swift](https://aws-oss.beachgeek.co.uk/25s) that dives deeper into the library.

**FreeRTOS**

The second release of FreeRTOS Long Term Support (LTS) - FreeRTOS 202210.00 LTS was announced last week. This release includes new libraries such as AWS IoT Fleet Provisioning and Cellular LTE-M Interface for easier device provisioning and cellular connectivity. It also includes coreMQTT and FreeRTOS-Plus-TCP libraries with improved modularity and robustness. All libraries included in this FreeRTOS LTS version, [summarised in this post](https://aws-oss.beachgeek.co.uk/25t), will receive security and critical bug fixes until October 2024. With an LTS release, you can continue to maintain your existing FreeRTOS code base and avoid any potential disruptions resulting from FreeRTOS version upgrades.

Similar to the previous FreeRTOS LTS release, FreeRTOS 202210.00 LTS includes libraries that have been validated for memory safety with the C Bounded Model Checker (CBMC) automated reasoning tool to help mitigate code security issues such as buffer overflow. In addition, all LTS libraries have undergone certain code quality checks including MISRA-C compliance and Coverity static analysis to help improve code safety, portability, and reliability in embedded systems (see LTS Code Quality Checklist).

The support period for the previous LTS release will end on March-2023, providing you a six-month overlap between the LTS releases for easy migration of your project. See the migration guide and corresponding validation tests to upgrade your project to FreeRTOS 202210.00 LTS. If you prefer not to upgrade and want to continue receiving critical fixes on the previous LTS version beyond its expiry, you can consider the FreeRTOS Extended Maintenance Plan.

### Videos of the week

**Ray**

Open source Ray is great for modern high-performance data processing and machine learning workloads. In this talk, Chris Fregly explains distributed Ray - what it is and how it differs from other distributed solutions such as Dask and Apache Spark. Chris also shares various tips and tricks to optimising Ray on AWS and Kubernetes. Chris also highlights some AWS key contributions to the open source Ray project to improve performance, scalability, and operational efficiency. Lastly, he conclude sthe talk with a demo using Ray's AI Runtime (AIR) to train and serve a large, distributed BERT model with Amazon Elastic Kubernetes Services (EKS).

{{< youtube fGqE2tO5mOo >}}


**Karpenter**

The folks at Fairwinds walk you through how you can use their tool Polaris together with Karpenter to stay on top of Kubernetes autoscaling to make sure you stay in control.

{{< youtube QAlprgujhAM >}}


**EKS Blueprints**

Ramesh Dwarakanath shares how you can deploy and scale Kubernetes Production Workloads using EKS Blueprints to configure Amazon EKS Clusters that are fully bootstrapped and ready to go.

{{< youtube tUauWe8JiT0 >}}


**Contributing to Open Source**

From the OpenSearch channel, Tuana Celic (@tuanacelik) from Deepset.ai, Omar Sanseviero from Hugging Face, and David Tippett from OpenSearch discuss what you need to know about contributing to open-sourcewe walking you through everything you need to know about how to start your open source journey.

{{< youtube _g46WiGPhFs >}}


**Build on Open Source**

For those unfamiliar with this show, Build on Open Source is where we go over this newsletter and then invite special guests to dive deep into their open source project. Expect plenty of code, demos and hopefully laughs.

If you missed us live on Friday, you can [view episode five of Build on Open Source](https://www.twitch.tv/videos/1630135246), where we chat with Abhishek Gupta who walks us through how to use cdk8s using Golang, building a Wordpress site in minutes.
 
We have put together a playlist so that you can easily access all the other episodes of the Build on Open Source show. [Build on Open Source playlist](https://aws-oss.beachgeek.co.uk/24u)

# Events for your diary

**KubeCon and CloudNativeCon North America**
**October 24th-28th, Detroit USA**

Check out this blog post from Nathan Taber, [AWS at KubeCon + CloudNativeCon North America 2022](https://aws-oss.beachgeek.co.uk/243) to hear more about what you can expect from AWS at this event, including Container Day. If you are going check this post out to see how you can reserve a spot to speak with one of the AWS specialists who will be at the booth.

![open source after dark picture](https://pbs.twimg.com/media/Fe4LAcZWYAEtoMh?format=jpg&name=small)

If you are attending KubeCon, make sure you do not miss the legendary Open Source After Dark party. You can expect lots of fun activities, great food, music and lots more. Make sure you register to save your spot, as spaces will be limited. Register and relax in the comfort of having your place saved [by heading over to this page.](https://aws-oss.beachgeek.co.uk/251)

**What's new in Amazon Aurora MySQL version 3**
**October 25th, 9am PT**

Amazon Aurora MySQL version 3 compatible with MySQL 8.0, is the latest version of Aurora MySQL. Come learn what makes this the best version of Aurora MySQL to run your relational database workloads. You will learn about the latest innovations in Aurora MySQL version 3 and MySQL 8.0. You will also be introduced to important and breaking behavioural changes in the new version. We will discuss the new version currency adopted with Aurora MySQL version 3 and ways to upgrade from older versions. There will also be a demo of new features like Aurora Serverless v2.

[Save your place on this online event by checking out the registration page here](https://aws-oss.beachgeek.co.uk/22x).

**Build on AWS Open Source**
**November 4th, 9am BST**

Join us for the sixth episode of the Build on AWS series, featuring a live round up of the latest projects and news as well as a special guest speaker. We have another special guest lined up, and I am very excited to welcome Javier Ramirez from QuestDB who will be coming on the show and sharing more about this open source times series database that is blazingly fast. Follow the show on @buildonopen for more details. Check it out on https://twitch.tv/aws

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