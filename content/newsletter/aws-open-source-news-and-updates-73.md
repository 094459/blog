---
title: 'AWS open source news and updates #73'
date: '2021-06-21'
tags : [ oss-newsletter ]
---
## 21st June, 2021 - Instalment #73

*updated 18th, Jan to remove dead link*

Newsletter #73.

This week's new projects include a project than can help you reduce your costs if you are running Amazon EKS workloads, an AWS CDK pattern to help you easily create internal and external access points for your applications, a GraphQL solution and some sample AWS projects. We have community and AWS authored posts featuring Kubernetes, Apache Flink, Firecracker, OpenSearch, Apache Tinkerpop, Apache Kafka, as well as .NET, GraphQL and Amazon Corretto and many more. To add to that we have a new workshop if you want to get started with High Performance Computing, a great video walkthrough of the open source tool cfn_nag and all the videos from last weeks Open@Amazon, which leads me nicely to...

**Open@Amazon**

Most of my time last week was taken making sure that we were able to get the Open@Amazon show, supporting a number of fellow AWS open source enthusiasts as we put on sixteen sessions which were very well received. If you missed it, you still can check out the [recorded video over on Twitch](https://aws-oss.beachgeek.co.uk/nv).



If you want to catch the individual sessions, see below where I have broken them out.

**Tweet of last week**

This weeks "[Tweet of the week](https://aws-oss.beachgeek.co.uk/mz)" comes from Curtis Einsmann, who shares in a Twitter thread some of the details of how he was able to author over 550 PRs. Well worth a quick look. Nice job Curtis.

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Pete Wilcock, Jonathan Tuliani, Josh Haycraft, Jeremy Ber, Satish Sathiya, Jiayuan Chen, Lokesh Gupta, Debu Panda, Anna Kaur, Vishram Thatte, Xuejiao Zhang, Sheetal Joshi, Rajalakshmi Ramasubramanian, Andy Hopper, Curtis Einsmann, Viji Sarathy, Imaya Kumar Jagannathan, Rafael Pereyra, Mike George, Bruno Schaatsbergen, David Tippett, Vu Dao, Hidenori Koizumi, Chiaki Ishio, Christian Kniep, François Bouteruche, Pahud Hsieh, and Pedro Vallese

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

**kubesurvival**

[kubesurvival](https://aws-oss.beachgeek.co.uk/nc) this project KubeSurvival, allows you to significantly reduce your Kubernetes costs by finding the cheapest machines that successfully run your workloads. The docs cover how to get started, provide some examples and how it works as well as how you can contribute to the project. If you have a multi-tenant environment, ML training jobs, a large number of ML model servers, etc, this tool can help you optimize your K8s compute costs. 

**finderio**

[finderio](https://aws-oss.beachgeek.co.uk/nb) Finderio is a GraphQL interface server from Pedro Vallese that connects to a DynamoDB database and fetches DynamoDB data based on GraphQL data. Very much a starting point as Pedro points out there are still some things needed, but take a look and see if you want to collaborate.

![arch](https://github.com/molBR/finderio/blob/master/images/Finderio.png?raw=true)

**cdk-fargate-patterns**

cdk-fargate-patterns - saw this AWS CDK pattern last week from Pahud Hsieh last week and thought it was pretty nice, having needed to do this many times in the past, this is going to save folks a lot of effort. It allows you to create one or many Fargate services with both internet-facing ALB and internal ALB associated with all services.

**amazon-fraud-detector-end-to-end**

[amazon-fraud-detector-end-to-end](https://aws-oss.beachgeek.co.uk/nf) - if you wanted to get started with Amazon Fraud Detector (a fully managed service that makes it easy to identify potentially fraudulent online activities such as online payment fraud and the creation of fake accounts) then this repository has sample code, projects that will make it easy to get started with a number of use cases which you can use as a base for your own needs.

![arch](https://github.com/aws-samples/amazon-fraud-detector-end-to-end/blob/main/images/nb4-light.png?raw=true)


**I Love My Local Farmer**

[i-love-my-local-farmer](https://aws-oss.beachgeek.co.uk/na) François Bouteruche shared with me last week a series of posts together with all the code which has been open sourced around a fictional company inspired by customer interactions with AWS Solutions Architects. I Love My Local Farmer is an online marketplace that lets people buy and sell locally grown fruit and vegetables. You can follow the series of blogs, the first of which, [Launch announcement](https://aws-oss.beachgeek.co.uk/n9) provides much more background. This project (and post) definitely appeals to me, maybe because of my farming roots (both my parents were farmers from the north west of Spain)

### Community open source posts

**Firecracker**

Firecracker is an open source virtual machine monitor (VMM) that uses the Linux Kernel-based Virtual Machine (KVM) to create and manage microVMs. In the post [Behind the scenes, AWS Lambda](https://aws-oss.beachgeek.co.uk/n4) Bruno Schaatsbergen dives deep into the architecture behind AWS Lambda and shares how Firecracker is key to how it all hangs together.

![arch](https://www.bschaatsbergen.com/img/worker-anatomy.png)

**Kubernetes**

Vu Dao is on a streak (I think this might be the fourth or more post he has written in as many weeks). Last week he put together [EKS Cluster Console Credentials](https://aws-oss.beachgeek.co.uk/n3) which will help you understand in more detail how IAM and Kubernetes RBAC works.

**Open Distro, Elasticsearch and OpenSearch**

This post from David Tippett will answer the question you might be asking yourself if you thought what are these and how are they similar/different. In his post, [The Difference Between Elasticsearch, Open Distro, and OpenSearch](https://aws-oss.beachgeek.co.uk/n2) provides a concise and clear guide as to what the various capabilities and differences between Open Distro and Open Search.

![opensearch](https://miro.medium.com/max/1400/1*_u3TYQ5-_1IZJEiM_Umipg.png)

**HuggingFace**

Hugging Face and Amazon are introducing new Hugging Face Deep Learning Containers (DLCs) to make it easier than ever to train Hugging Face Transformer models in Amazon SageMaker. To find out more, read the post [Run training on Amazon SageMaker](https://aws-oss.beachgeek.co.uk/n8) which you can follow and try this out for yourself as well as find a bunch of useful links to do even more with HuggingFace on AWS.

**Wordpress**

[Serverless Static Wordpress on AWS for $0.01 a day](https://aws-oss.beachgeek.co.uk/nw) AWS Community Builder Pete Wilcock with  a post that Wordpress lovers will want to read.   Ihave spoken with many people who have been dreaming of a "serverless" Wordpress deployment. Could this be it? Read on to find out more...

### Workshop

**AWS ParallelCluster**

If you are looking to get started with High Performance Computing (HPC), then last week I found a new workshop after reading this blog post from Christian Kniep, [Getting started with containers in HPC at ISC’21](https://aws-oss.beachgeek.co.uk/n6) where he writes how AWS is hosting the ‘High Performance Container Workshop’ at ISC High Performance 2021 conference (ISC’21) in a few weeks.

You can find the workshop here, [Container Runtimes/Engines on AWS ParallelCluster](https://aws-oss.beachgeek.co.uk/n7)

### AWS and Amazon open source posts

**Cloud Custodian**

Cloud Custodian is an open source rules engine for managing public cloud accounts and resources. It allows users to define policies to enable a well managed cloud infrastructure. In the latest of a number of posts in this area, Xuejiao Zhang takes a look how you achieve compliance by default through a combination of Open Policy Agent policy checks integrated into your CI/CD pipeline, using Cloud Custodian to do real time scanning and auto remediation. Read her post, [Cloud governance and compliance on AWS with policy as code](https://aws-oss.beachgeek.co.uk/mu) 

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/06/09/zxuejiao_f1_high-level-arch.png)

**Kubernetes**

[A multi-cluster shared services architecture with Amazon EKS using Cilium ClusterMesh](https://aws-oss.beachgeek.co.uk/my) Viji Sarathy takes a look at the details of implementing a Cilium ClusterMesh with two or more Amazon EKS clusters. What is a Cilium ClusterMesh? Cilium provides network connectivity between applications deployed using Linux container management platforms like Docker and Kubernetes that enables users to set up cross-cluster connectivity with standard Kubernetes semantics for transparent service discovery.  ClusterMesh is Cilium’s multi-cluster implementation that is built on top of Cilium CNI. Liz Rice did a great session at Open@Amazon on this, so check this out if you want to dive deeper.

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2021/06/14/clustermesh-arch.png)

**Prometheus**

A couple of posts last week on Prometheus. First up we have this post, [Automating the installation and configuration of Prometheus using Systems Manager documents](https://aws-oss.beachgeek.co.uk/n0) from Mike George showing you how you can use a number of AWS services to automate and ensure that Prometheus is installed in exactly the same way every time.

Following that we have Imaya Kumar Jagannathan and Rafael Pereyra who have written Collect on-premises metrics using Amazon Managed Service for Prometheus where they show you how you can set up a secure environment to collect Prometheus metrics from an on-premises VM and remote write metrics to Amazon Managed Service for Prometheus (AMP).

![arch](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2021/06/14/Fig-1.png)

**Apache Kafka**

Anusha Dharmalingam takes a look at how to set up a highly resilient deployment across AWS Regions in the post, [Increase Apache Kafka’s resiliency with a multi-Region deployment and MirrorMaker 2](https://aws-oss.beachgeek.co.uk/mt). You can use this solution to build a data redundancy capability to meet regulatory compliance, business continuity, and DR requirements.

![arch](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2021/06/03/bdb1410-msk-mirrormaker-1.jpg)

**Apache Flink**

We have a couple of posts this week on Apache Flink, an open source distributed stream processing engine. First up we have Josh Haycraft with the post, [Collecting Apache Flink metrics in the Amazon CloudWatch agent](https://aws-oss.beachgeek.co.uk/mq), where he shoes you how you can not only view Flink metrics through its web UI, but generate events so you can react with them. Josh covers how to use the CloudWatch agent to collect Flink metrics into Amazon CloudWatch, where you can monitor them, add them to a dashboard, and trigger alerts or event-driven processes. Detailed walkthrough provided so you can try this out for yourself.

![arch](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2021/05/24/devops-776-fig1.png)

Following that we have Jeremy Ber who writes, [Top 10 Flink SQL queries to try in Amazon Kinesis Data Analytics Studio](https://aws-oss.beachgeek.co.uk/mr) where he shows you how you can run Apache Flink SQL queries in Kinesis Data Analytics Studio, powered by the open source Apache Calcite project. This implements the SQL standard, allowing you to write simple SQL statements to create, transform, and insert data into streaming tables defined in Apache Flink.

**GraphQL**

AWS AppSync is a fully managed service that makes it easy to develop GraphQL APIs. In the post, [Build a GraphQL API for Amazon DocumentDB (with MongoDB compatibility) using AWS AppSync](https://aws-oss.beachgeek.co.uk/mv) Anna Kaur and Vishram Thatte show you how you can build a simple GraphQL API using AWS AppSync to retrieve data from Amazon DocumentDB.

![arch](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2021/05/21/dbblog_922_01.jpg)

**Apache TinkerPop**

Hidenori Koizumi and Chiaki Ishio wrote [Build a graph application with Amazon Neptune and AWS Amplify](https://aws-oss.beachgeek.co.uk/n5) showing you how you can use Amplify to develop an application that interacts with a graph database, writing functions in AWS Lambda that uses Apache TinkerPop Gremlin.

![arch](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2021/06/14/dbblog-1462-1.png)

**.NET**

Porting Assistant is an open source tool from AWS that helps developers accelerate the conversion of their code from the Windows-only .NET Framework runtime to the cross-platform .NET runtime. In the post, [Accelerate .NET application modernization with Porting Assistant for .NET Visual Studio IDE extension](https://aws-oss.beachgeek.co.uk/mx) Andy Hopper explains how to analyse and port .NET Framework applications to .NET Core or .NET 5 using Visual Studio Extension for Porting Assistant for .NET.

![demo](https://d2908q01vomqb2.cloudfront.net/8effee409c625e1a2d8f5033631840e6ce1dcb64/2021/06/14/ToolsOptions-1024x635.png)

**Amazon Corretto**

[Announcing migration of the Java 8 runtime in AWS Lambda to Amazon Corretto](https://aws-oss.beachgeek.co.uk/mp) Jonathan Tuliani writes about a change to the Java 8 managed runtimes within AWS Lambda, that will be switching from the OpenJDK implementation to Amazon Corretto. The post covers what this will mean and look like and the impact and timelines. It also provides some useful tips around testing and validating your current functions, as well as what to do if you absolutely need to carry on using OpenJDK.

**XGBoost**

The XGBoost algorithm (eXtreme Gradient Boosting) is an optimized open-source implementation of the gradient boosted trees algorithm, and is designed from the ground up to handle many data science problems in a highly efficient, flexible, portable, and accurate way. XGBoost can be used for regression, binary classification, multi-class classification, and ranking problems. In this collaboration from Satish Sathiya, Jiayuan Chen, Lokesh Gupta, and Debu Panda, [Build XGBoost models with Amazon Redshift ML](https://aws-oss.beachgeek.co.uk/nx), they share how data scientists can train models using the XGBoost algorithm. covering how you can use Redshift ML to train ML models 

### Video of the week

**cfn_nag**

[cfn_nag](https://aws-oss.beachgeek.co.uk/ng) is an open source library from Mphasis Stelligent  that performs static analysis on AWS CloudFormation templates. This screencast is a complete walkthrough of developing rules for cfn_nag in a test-driven way.

{% youtube JRZct0naFd4 %}

### Quick updates

**Apache Cassandra**

Amazon Keyspaces (for Apache Cassandra) a fully managed Cassandra-compatible database service, is now in scope for AWS ISO and CSA STAR certifications and services to help you run highly regulated Cassandra workloads more easily. AWS has certification for compliance with ISO/IEC 27001:2013, 27017:2015, 27018:2019, ISO 9001:2015, and CSA STAR CCM v3.0.1. Now, you can run Cassandra workloads that are subject to ISO and CSA STAR compliance more easily by using a fully managed and serverless database service.

**Envoy**

AWS App Mesh is a service mesh that provides application-level networking to make it easy for your services to communicate with each other across multiple types of compute infrastructure.App Mesh uses the open source Envoy proxy, making it compatible with a wide range of AWS partner and open source tools. A couple of updates this week, which you can read about in more detail in the post from Sheetal Joshi and Rajalakshmi Ramasubramanian, [AWS App Mesh ingress and route enhancements](https://aws-oss.beachgeek.co.uk/mw)

* The AWS App Mesh introduces enhanced ingress traffic management capabilities. Now you can control how App Mesh rewrites external requests, so that they reach the correct destination within your mesh. You also have greater flexibility controlling how the requests are matched to the destinations in the Gateway and Virtual Router Routes. Now Gateway Routes provide flexible controls that allow you to enable or disable rewrites, add or remove prefix, edit path, and match the requests to destinations based on the hostname and header. This enables you adjust the behavior of traffic that enters your mesh and simplifies building applications with sophisticated structure of microservices.

* AWS App Mesh Controller for Kubernetes v1.4.0 is now available and includes support for enhanced ingress traffic management capabilities. The AWS App Mesh Controller for Kubernetes provides a way to configure and manage AWS App Mesh using Kubernetes directly.


**PostgreSQL**

A few quick updates this week covering PostgreSQL on Amazon Aurora and RDS:

* Amazon Aurora PostgreSQL-Compatible Edition adds support for the pg_bigm extension. pg_bigm extension provides full text search capability in PostgreSQL. This extension allows a user to create 2-gram (bigram) index for faster full text search. Characters that comprise text are represented as numbers to computers. Languages such as English, French, Russian, and Hebrew use character sets of fewer than 256 characters that can be encoded in a single byte. Languages with many characters (e.g., Japanese) require more numbers, which are represented by multi-byte encoding. pg_bigm allows you to create a 2-gram (bigram) index for faster full text search of text encoded with multi-byte characters.

* Amazon Aurora PostgreSQL-Compatible Edition supports the Partition Manager (pg_partman) extension. pg_partman is a PostgreSQL extension that helps you to manage both time series and serial-based table partition sets, including automatic management of partition creation and runtime maintenance. pg_partman works with PostgreSQL native partitioning so users can benefit from significant performance enhancements.

* Amazon Aurora PostgreSQL-Compatible Edition adds support for the pg_cron extension. pg_cron allows you to use cron syntax to schedule PostgreSQL commands directly within your database. You can use pg_cron to schedule tasks such as periodically rolling up data for analytic reports, refreshing materialized views, and scheduling vacuum jobs to reclaim storage. pg_cron includes an AWS open source contribution that adds an audit table so that you can query the outcome of each scheduled job.  

* Amazon Aurora PostgreSQL-Compatible Edition adds support for the pg_proctab extension. pg_proctab is a collection of stored functions that can access the operating systems process table so that system statistics can be queried through the database. pg_proctab functions make it easier to collect data on your PostgreSQL database including up-to-date information on processor and I/O statistics on SQL queries which makes troubleshooting easier.

* Following the announcement of updates to the PostgreSQL database by the open source community, we have updated Amazon Aurora PostgreSQL-Compatible Edition to support PostgreSQL versions 12.6, 11.11, 10.16, and 9.6.21. These releases contain bug fixes and improvements by the PostgreSQL community. As a reminder, Amazon Aurora PostgreSQL 9.6 will reach end of life on January 31, 2022.  You can initiate a minor version upgrade manually by modifying your DB cluster, or you can enable the “Auto minor version upgrade” option when creating or modifying a DB cluster. Doing so means that your DB cluster is automatically upgraded after AWS tests and approves the new version.

* Amazon RDS for PostgreSQL adds support for extension allowlists to provide database administrators more control over usage of extensions. RDS for PostgreSQL supports over 70 PostgreSQL extensions. Extensions expand on the functionality provided by the PostgreSQL engine. However, for regulatory or compliance purposes, some organizations would like to be able to specify approved extensions. With extension allowlists, you can specify which specific extensions can be installed on a PostgreSQL DB instance.

### Open@Amazon

Last week we were joined by thousands of attendees to check out some great open source on AWS sessions. We had sixteen sessions, so have broken them out here so you can catch them again.

**[Add some AWS into your TMUX: How to make a great Open Source tool even better from Darko Meszaros](https://aws-oss.beachgeek.co.uk/nh)**

**[Cloud native observability in practice: open source and open specifications from Michael Hausenblas](https://aws-oss.beachgeek.co.uk/ni)**

**[Accelerate robot application development in ROS with AWS RoboMaker from Emilia Brzozowska](https://aws-oss.beachgeek.co.uk/nj)**

**[Lambda Powertools: Lessons learned on the road to the first 1 million downloads from Heitor Lessa](https://aws-oss.beachgeek.co.uk/nk)**

**[Unify your data and ML projects with AWS Orbit Workbench with Antje Barth](https://aws-oss.beachgeek.co.uk/nl)**

**[StackGres: Running Postgres on EKS with AWS Hero Álvaro Hernández](https://aws-oss.beachgeek.co.uk/nm)**

**[Why and how to use Terraform AWS modules? with AWS Hero Anton Babenko](https://aws-oss.beachgeek.co.uk/nn)**

**[Kubernetes Network Policy with Cilium with AWS Hero Liz Rice](https://aws-oss.beachgeek.co.uk/no)**

**[How to use Docker as a front-end for Amazon ECS and AWS Fargate with Massimo Re Ferre’](https://aws-oss.beachgeek.co.uk/np)**

**[COBOL & AWS Lambda go together like? ....How to modernize your legacy COBOL applications by running them on AWS Lambda with Veliswa Boya](https://aws-oss.beachgeek.co.uk/nq)**

**[My journey contributing to Terraform. Demystifying the process of contributing upstream* with Tyler Lynch & K.G. Nesbit](https://aws-oss.beachgeek.co.uk/nr)**

**[Connected data with Apache TinkerPop and Amazon Neptune with Stephen Mallette](https://aws-oss.beachgeek.co.uk/ns)**

**[AI in Java with Deep Java Library (DJL) with Qing Lan & Frank Liu](https://aws-oss.beachgeek.co.uk/nt)**

**[AWS SaaS Boost: An Open-Source Tool for Accelerating SaaS Migration with Michael Beardsley](https://aws-oss.beachgeek.co.uk/nu)**

### Events for your diary

**AWS + Confluent Immersion Day**
**June 24th, 10am - 3pm PDT**

A free, half-day virtual workshop experience where you will learn more about Apache Kafka and what problems it can help you solve, taking a look at the features from Confluent that make running Confluent easier and how you can integrate with your favourite AWS services. Joseph Morais and Jobin George are your hosts, so you know this is going to be a must attend event.

Find out more and [register here](https://aws-oss.beachgeek.co.uk/ms).


**Cloud Native Day**
**23rd September, Bern Switzerland**

What is this, an in person event returning? A stellar line up including our own Michael Hausenblas, an event looking at CNCF projects and the future of IT. Find out more and to view prices/register, by clicking [here](https://cloudnativeday.ch/en/#speakers).


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen2