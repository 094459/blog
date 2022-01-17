---
title: 'AWS open source news and updates #91'
date: '2021-11-22'
tags : [ oss-newsletter, AWS Open Source ]
---
## November 22nd, 2021 - Instalment #91

Newsletter #91.

This week I feature eleven new open source projects, covering a diverse array of use cases. From securing your Kubernetes clusters, a couple of nifty Amazon Neptune tools, a Python library that provides state-of-the-art distributed hyper parameter optimising, a sample NFT marketplace and more. This weeks AWS community and AWS content features topics including AWS SAM, Bottlerocket, Babelfish, Apache Airflow, PartiQL, Suricata, Slurm, Apache Kafka, AWS Amplify, PHP and more. We have lots of smaller updates in the Quick Updates section, so make sure you do not miss those as well as some fresh new videos to check out.

Finally, as we approach re:Invent (next week) make sure you check out the extended Events section which includes the sessions to watch out for. 

**re:Invent 2021**

If you are going or attending virtually, there is plenty of great open source related sessions this year. Head down to the Events section where I have provided some of the highlights I think that should be on your list of sessions to watch/attend. Also, check the noticeboard to make sure you do not miss the best re:Invent party, After Dark.

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Vu Dao, Álvaro Hernández, Justin Wheeler, Aditya Samant, Vlad Vlasceanu, Rolando Santamaria Maso, Ramy Nasreldin, Prasanna Tuladhar, Shiva Vaidyanathan, Brian Lazear, Lakshmikanth Pandre, Gary Stafford, Federico Garza Ramírez, Uma Ramadoss, Rene Brandel, Josiah Bjorgaard, Austin Cherian, Angel Pizarro, Joseph Keating, Blayze Stefaniak, David Salinas, Cedric Archambeau, Aaron Klein, and Matthias Seeger.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Community noticeboard

**After Dark Party**

If you are attending re:Invent next week, then make sure you check out and sign up for the After Dark Party. Whilst sadly I will not be there, it promises to be a great evening of networking with peers. There will be beverages, appetisers, entertainment, swag and more! No presentations, no pitches, just fun!

Find and more and[ RSVP, here](https://aws-oss.beachgeek.co.uk/13n).

### Latest open source projects

**syne-tune**

[syne-tune](https://aws-oss.beachgeek.co.uk/14d) this open source Python library provides state-of-the-art distributed hyperparameter optimizers (HPO) where trials can be evaluated with several backend options (local backend to evaluate them locally; SageMaker to evaluate them as separate SageMaker training jobs; another backend with fast startup times is also in the making). To help you get started, David Salinas, Cedric Archambeau, Aaron Klein, and Matthias Seeger have put together this blog post, [Run distributed hyperparameter and neural architecture tuning jobs with Syne Tune](https://aws-oss.beachgeek.co.uk/14e)

![demo](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2021/11/19/8-6903_A.jpg)

**amazon-neptune-gremlin-dotnet-sigv4**

[amazon-neptune-gremlin-dotnet-sigv4](https://aws-oss.beachgeek.co.uk/13q)
last week we saw released a small, open-source library that enables AWS SigV4 signing for connecting to Amazon Neptune on AWS with the TinkerPop .Net client. Repository contains sample code and documentation on how to use this.

**amazon-neptune-jdbc-driver**

[amazon-neptune-jdbc-driver](https://aws-oss.beachgeek.co.uk/13t) this open source project provides read-only JDBC connectivity for the Amazon Neptune service using SQL, Gremlin, openCypher and SPARQL queries. Repo contains how to get started with this as well as some sample code.

**amazon-rds-init-cdk**

[amazon-rds-init-cdk](https://aws-oss.beachgeek.co.uk/13v) I always find code samples and projects a great way to learn how to use AWS, and so this repository will show to support Amazon RDS instances initialisation using CDK and CloudFormation Custom Resources. Rolando Santamaria Maso, Ramy Nasreldin, and Prasanna Tuladhar also have put together this blog post, [Use AWS CDK to initialize Amazon RDS instances](https://aws-oss.beachgeek.co.uk/13w) to provide further guidance on how to use this code.

![arch](https://d2908q01vomqb2.cloudfront.net/b7eb6c689c037217079766fdb77c3bac3e51cb4c/2021/11/18/rds-initialization-cdk-architecture-diagram-1024x475.png)

**K8s-SAProbe**

[K8s-SAProbe](https://aws-oss.beachgeek.co.uk/13z) this project from Jayden Aung should be on your list to checkout if you are working on Kubernetes and are looking for tools to help you secure your clusters. Jayden has helpfully put together this blog post, [SAProbe — A simple tool that discovers exposed Kubernetes Secrets via Service Accounts](https://aws-oss.beachgeek.co.uk/140)

**apigw-websocket-pusher**

[apigw-websocket-pusher](https://aws-oss.beachgeek.co.uk/14f) this project provides a fast and cost effective way for broadcasting messages to multiple users. Showing you how you can use this is the post, [AWS API Gateway Websocket Asynchronous Notifications Pusher](https://aws-oss.beachgeek.co.uk/14m)

![arch](https://github.com/obytes/apigw-websocket-pusher/raw/main/docs/images/arch.svg)

**s3-data-pump**

[s3-data-pump](https://aws-oss.beachgeek.co.uk/14g) if you are looking for a way of moving large collections of S3 objects among buckets, then check out this open source project which you can use as the base for your own experimentation.

![arch](https://github.com/aws-samples/s3-data-pump/blob/main/docs/s3-data-pump-architecture.png?raw=true)

**streaming-endpoint-for-apache-hbase**

[streaming-endpoint-for-apache-hbase](https://aws-oss.beachgeek.co.uk/14h) this project helps you create a custom Apache HBase replication endpoint, to stream records into Apache Kafka, Amazon Kinesis or others.

**simple-nft-marketplace**

[simple-nft-marketplace](https://aws-oss.beachgeek.co.uk/14i) whilst personally I am still on the fence around the useful applications of NFTs, if you are looking to explore this area then you can try out this sample project that helps you build a simple NFT marketplace with Amazon Managed Blockchain.

![arch](https://github.com/aws-samples/simple-nft-marketplace/blob/main/imgs/simple-nft-marketplace.png?raw=true)

**azure-eventhub-consumer-with-dynamodb**

[azure-eventhub-consumer-with-dynamodb](https://aws-oss.beachgeek.co.uk/14n) if you are looking for some example code on how to build applications that span and integrate between AWS and Microsoft Azure, then check this project that shows how you can consume events from Azure Event Hub, storing checkpoint and ownership information in a DynamoDB table, and saving all the event data to a S3 bucket and if needed, logging metrics for consumer latency to CloudWatch Metrics.

![arch](https://github.com/aws-samples/azure-eventhub-consumer-with-dynamodb/blob/main/docs/img/architecture.png?raw=true)

**rekognition-video-people-blurring-cdk**

[rekognition-video-people-blurring-cdk](https://aws-oss.beachgeek.co.uk/14o) this sample project demonstrates how AWS Step Functions can be used to orchestrate AWS Lambda functions that call Amazon Rekognition for face detections, and use OpenCV to blur these detections per frame in the video. Check out the sample below.

![arch](https://github.com/aws-samples/rekognition-video-people-blurring-cdk/blob/main/images/rekognition-video-face-blur-cdk-app.png?raw=true)

![demo](https://github.com/aws-samples/rekognition-video-people-blurring-cdk/blob/main/images/output.gif?raw=true)

### AWS open source project revisit

This section will feature projects that may not be new, but are ones that you should probably check out. 

**awsudo**

[awsudo](https://aws-oss.beachgeek.co.uk/14s) this open source project from Meltwater is a simple utility for easily executing AWS cli commands with an assumed role. Andy Desmarais has put together a blog post, Assuming roles in AWS with sudo-like agility, to help you get started.

### AWS and Community blog posts

**AWS Amplify**

The big news last week was the announcement that you can now add custom resources when using the Amplify cli that enables developers to add additional resources beyond Amplify’s built-in use cases.

Rene Brandel shared more details in his posts, [Extend Amplify backend with custom AWS resources using AWS CDK or CloudFormation](https://aws-oss.beachgeek.co.uk/143) and [Override Amplify-generated backend resources using CDK](https://aws-oss.beachgeek.co.uk/144) [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/0a57cb53ba59c46fc4b692527a38a87c78d84028/2021/11/16/Screen-Shot-2021-11-16-at-6.46.56-AM-1024x514.png)

We also had a post from Nikhil Swaminathan and Eric Clemmons of the AWS Amplify team, [Amplify UI’s new Authenticator component makes it easy to add customizable login pages to your React, Angular, or Vue app](https://aws-oss.beachgeek.co.uk/14k) walking you through the recently announced new version of the Authenticator component for JavaScript (JS)-based web apps, giving developers the easiest way to add login experiences to their app with a single line of code. [hands on]

![demo](https://d2908q01vomqb2.cloudfront.net/0a57cb53ba59c46fc4b692527a38a87c78d84028/2021/11/18/authenticator2.gif)

**Bottlerocket**

A couple of Bottlerocket posts this week. First up we have AWS Community Builder Vu Dao, who has been busy writing [AWS BottleRocket On EKS NodeGroup](https://aws-oss.beachgeek.co.uk/14q) with a hands on guide on how to launch a Bottlerocket managed node group on EKS cluster.

Following that we have a post from Ritesh Patel and Mikhail Shapirov on how to use  Bottlerocket OS and Kyverno (an open source Kubernetes native policy engine) on Amazon EKS managed by Nirmata Kubernetes Platform to help secure your Kubernetes environments. To find out more, read on in [Provisioning and Securing Bottlerocket OS-Based Amazon EKS Clusters Using Nirmata Kubernetes Platform](https://aws-oss.beachgeek.co.uk/14a) [hands on]

![demo](https://d2908q01vomqb2.cloudfront.net/77de68daecd823babbb58edb1c8e14d7106e83bb/2021/11/10/Bottlerocket-Amazon-EKS-Nirmata-Kubernetes-3r.png)

**AWS SAM**

In [Modernizing deployments with container images in AWS Lambda](https://aws-oss.beachgeek.co.uk/148), Joseph Keating demonstrates how to use AWS continuous integration and deployment (CI/CD) services, AWS SAM and Docker to separate the container build process from the application deployment process of Lambda container images. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2021/11/17/Picture1-4.png)

**Babelfish**

[Easily Running Babelfish for PostgreSQL on Kubernetes](https://aws-oss.beachgeek.co.uk/14r) AWS Hero Álvaro Hernández shares how using StackGres 1.1.0, now includes Babelfish, making it easy to run Babelfish on Kubernetes. Do not worry if you are not super knowledgable on Kubernetes, Álvaro has you covered. Awesome stuff, and an essential read this week. [hands on]

**Apache Kafka**

AWS Lambda now supports mutual TLS authentication for Amazon MSK and self-managed Kafka as an event source. This means you can provide a client certificate to establish a trust relationship between Lambda and MSK or self-managed Kafka brokers. To find out more, Uma Ramadoss provides a hands on guide to getting this going in [Introducing mutual TLS authentication for Amazon MSK as an event source](https://aws-oss.beachgeek.co.uk/141) [hands on]

**PartiQL**

In the post, [Build faster with Amazon DynamoDB and PartiQL: SQL-compatible operations](https://aws-oss.beachgeek.co.uk/142) Pete Naylor and Akshat Vig show you how you can use PartiQL in DynamoDB to describe your data operations using SQL-compatible statements. PartiQL support in DynamoDB provides a familiar path so you can build faster, and also provides powerful new batched capabilities. [hands on]

**Suricata**

The follow up post from a previous post I have shared in this newsletter, in [Hands-on walkthrough of the AWS Network Firewall flexible rules engine – Part 2](https://aws-oss.beachgeek.co.uk/13y) Shiva Vaidyanathan, Brian Lazear, and Lakshmikanth Pandre show you how you can fetch the latest Suricata rules from Proofpoint’s Emerging Threats OPEN ruleset within to help establish a baseline for your rule groups. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2021/11/17/Network-Firewall-Suricata-rule.png)

**Open Source Deep Learning**

Federico Garza Ramírez shares an alternative to the AWS Deep Learning AMIs, describing how to set up GPU infrastructure automatically using conda, Docker, make and terraform in his post, [Open Source Alternative to the AWS Deep Learning AMI](https://aws-oss.beachgeek.co.uk/13p). I have not tried it yet, but it is on my todo list.  [hands on]

**HPC**

We had a couple of posts for those interesting in open source tools in the HPC space. 

First up we had a post showing you how to integrate Slurm with AWS ParallelCluster. [Slurm](https://aws-oss.beachgeek.co.uk/145) is an open-source cluster resource management and job scheduling system that strives to be simple, scalable, portable, fault-tolerant, and interconnect agnostic. Josiah Bjorgaard shows you the way in his post, [Using the Slurm REST API to integrate with distributed architectures on AWS](https://aws-oss.beachgeek.co.uk/146) [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/e6c3dd630428fd54834172b8fd2735fed9416da4/2021/11/03/hpcblog-53-fig1.png)

Next we had Austin Cherian and Angel Pizarro with [Deep dive into the AWS ParallelCluster 3 configuration file](https://aws-oss.beachgeek.co.uk/147) perfect if you want to know more about the format changes between ParallelCluster 2 and 3 as well as going deeper with the new features available AWS ParallelCluster 3.

**Linux**

In the post [Stream applications at a lower cost with Amazon AppStream 2.0 Elastic fleets and Linux compatibility](https://aws-oss.beachgeek.co.uk/14j) Blayze Stefaniak shows you how you can use the recently announced Linux support in Amazon AppStream to stream Linux applications. Using another new capability, Elastic Fleets, AWS manages the capacity users stream from, eliminating the need for you to create autoscaling policies or manage buffer capacity for your end users. 

**PHP**

PHP is still a very popular programming language, and it always makes me happy when I see new posts covering how to combine PHP with modern application techniques, such as this post [Creating Serverless Websites with AWS, Bref, and PHP](https://aws-oss.beachgeek.co.uk/14l) from AWS Community Builder Justin Wheeler.

### Quick updates

**JDBC driver for Amazon Neptune**

AWS released an open source Java (JDBC) driver to connect to Amazon Neptune. This makes it easy for customers to connect to Neptune with tools and libraries that support JDBC, such as popular Business Intelligence (BI) tools.

Amazon Neptune is a fast, reliable, fully managed graph database service that makes it easy to build and run applications that work with highly connected datasets. Customers have asked us for an easy way to connect Neptune to BI tools in order to visualise their data and better understand the results of their queries. Customers can now connect their graph database to these tools, such as Tableau, to visualise the results of their queries.

See the projects section above for links to the GitHub repo.

**Linux**

Amazon Linux 2 is now available with an updated Linux kernel (5.10) as an Amazon Machine Image (AMI). Kernel 5.10 brings a number of features and performance improvements, including optimisations for Intel Ice Lake processors and AWS Graviton2 processors powering the latest generation Amazon EC2 instances. Live patching for Kernel 5.10 is supported in Amazon Linux 2 for both x86 and ARM architectures.

The updated kernel 5.10 includes various security features including WireGuard VPN that helps setup a virtual private network with low attack surface and allows encryption with less overhead compared to alternatives. The updated kernel brings a kernel lockdown feature to prevent unauthorised modification of the kernel image and a number of BPF improvements, including the CO-RE (Compile Once - Run Everywhere). Customers will benefit from improved write performance, throughput, and support for the new exFAT system for better compatibility with storage devices. In addition, with the availability of MultiPath TCP (MPTCP), customers with several network interfaces can combine all available network paths to increase throughput and reduce network failures.

**.NET 6**

Congratulations to all the development teams and community involved in the .NET 6 GA release. .NET developers here at AWS are excited about the performance improvements in JIT compilation, Garbage Collection, JSON processing, and many other areas of the new release. We’re also excited about the new features including the Minimal API Framework, new data types, Priority Queues, and more in this new Long Term Support (LTS) release and C# 10.

.NET 6 has improved performance for ARM64, and over the last 12 months we have expanded the number of AWS Graviton2 Processor options, providing customers with more choices to target ARM64 with their .NET 6 applications. Targeting ARM64 can add up to 40% better price performance over comparable current generation x86-based instances.

Read more in the announcement, [.NET 6 on AWS](https://aws-oss.beachgeek.co.uk/149)

**MySQL**

Amazon Aurora MySQL-Compatible Edition now supports MySQL major version 8.0. MySQL 8.0 includes improved performance functionality from enhancements such as instant DDL to speed up the overall process of creating and loading a table and its associated indexes and SKIP LOCKED and NOWAIT options to avoid waiting for other transactions to release row locks. MySQL 8.0 adds developer productivity features such as window functions to more easily solve query problems and common table expressions to enable use of named temporary result sets. It also includes JSON functionality additions, new security capabilities, and more. MySQL 8.0 on Aurora MySQL-Compatible Edition supports popular Aurora features including Global Database, RDS Proxy, Performance Insights, and Parallel Query.

We also had the blog post, [Amazon Aurora MySQL 3 with MySQL 8.0 compatibility is now generally available](https://aws-oss.beachgeek.co.uk/13x) from Aditya Samant and Vlad Vlasceanu that dives deeper into this announcement.

**FreeRTOS**

A couple of quick updates covering FreeRTOS.

First up we had the news last week that the cellular LTE-M interface library is now generally available in FreeRTOS. With this launch, developers will find it easier to build IoT devices that use the cellular LTE-M protocol to connect to the cloud. The main [FreeRTOS download](https://aws-oss.beachgeek.co.uk/13r) includes AWS IoT reference integrations with cellular modules from vendors such as Sierra Wireless, u-blox, and Quectel.

And then we had news that FreeRTOS now contains an example code that demonstrates a method of minimising the time an application spends in privileged mode in FreeRTOS ports on microcontrollers (MCU) with Memory Protection Unit (MPU) support. FreeRTOS ports with MPU support enable MCU applications to be more robust and secure by running application tasks in unprivileged mode, where they have access only to their own stacks and pre-configured memory regions. The only application code that runs in privileged mode on these MPU enabled MCUs are Interrupt Service Routines (ISRs). The example code demonstrates an approach to keep ISRs short and defer most of the application work to unprivileged FreeRTOS tasks, which helps improve security of the application by minimising the time it spends in privileged mode.

**Kubernetes**

Last week we saw the general availability of Amazon Elastic Kubernetes Service (EKS) Connector. With EKS Connector, you can now extend the EKS console to view your Kubernetes clusters outside of AWS. You can use the EKS console to visualise Kubernetes clusters including your on-premises Kubernetes clusters, self-managed clusters running on Amazon Elastic Compute Cloud (EC2), and clusters from other cloud providers. Once connected, you can see all of your clusters’ statuses, configurations, and workloads in one place on the EKS console.

We also added support for connected cluster tagging and Kubernetes version display on the EKS console. Registering a cluster is now easier with fewer steps as we’ve automated the Service Linked Role creation. You can also use the Service Quotas console to request connecting more than 10 clusters per region at a time. 

**AWS Data Wrangler**

In case you missed this last week, AWS Data Wrangler is available as a Lambda Managed layer in a number of AWS regions. Check out the [installation documentation for more details](https://aws-oss.beachgeek.co.uk/14c).

**RabbitMQ**

You can now launch RabbitMQ 3.8.23 brokers on Amazon MQ. This patch update to RabbitMQ contains several fixes and enhancements compared to the previously supported version, RabbitMQ 3.8.22.

**AWS IoT Greengrass**

AWS IoT Greengrass is an Internet of Things (IoT) edge runtime and cloud service that helps customers build, deploy, and manage device software. With this release, AWS IoT Greengrass version 2.5 adds support for Microsoft Windows devices. Windows gateway devices are commonly used in industrial IoT scenarios to automate manufacturing operations by collecting local sensor and equipment data and triggering local actions using application business logic. For example, consider an automotive assembly line where a steel stamping press creates a complex part that is prone to defects. Quality Control (QC) automation can be built using a video camera stream fed to a gateway device that uses local ML inference to check part dimensions and find cosmetic defects. The gateway could then notify operators if defects are identified.

Read more in the full announcement, [AWS IoT Greengrass now supports Microsoft Windows devices](https://aws-oss.beachgeek.co.uk/13s)

### Workshop

**AWS SAM**

If you have been looking to get started with AWS SAM, why not check out this workshop, [Building Serverless Apps with SAM](https://aws-oss.beachgeek.co.uk/14b). Find out how to use this open source project to start building serverless applications.

### Video of the week

**Apache Airflow**

Gary Stafford is back again, this time with a session on [Building a Data Lake on AWS with Apache Airflow](https://aws-oss.beachgeek.co.uk/13u). In this video, he shows you how to programmatically build a simple data lake on AWS using a combination of services, including Amazon Managed Workflows for Apache Airflow (Amazon MWAA), AWS Glue Data Catalog, AWS Glue Crawlers, AWS Glue Jobs, AWS Glue Studio, Amazon Athena, Amazon Relational Database Service (Amazon RDS), and Amazon S3.

{% youtube u3uL55nyr1M %}

**HashiCorp Consul Service Mesh**

Been a while since I have featured a Containers from the Couch video, but the team are back and this time they are joined by Hashicorp as they walk through deploying Consul as service mesh to Amazon ECS using the AWS CDK.

{% youtube agkIx4k2tUk %}

### Events for your diary

**re:Invent 2021 | Virtual and Las Vegas**
**November 28th to Friday 3rd December**

Make sure you check out the Open Source track at re:Invent this year. As from previous years, there are plenty of great sessions, chalk talks, workshops and builder sessions. There are also open source events across other tracks too. Here is what you can expect:

* OPN201 - How Apache Lucene's community built merge-on-refresh
* OPN202 - Babelfish architecture and design (Chalk Talk)
* OPN204 - Introduction to GraphQL
* OPN205 - Construct Hub: An open-source catalog for CDK libraries (Chalk Talk)
* OPN206 - Getting started as a Bottlerocket contributor (Chalk Talk)
* OPN207 - Top 10 observability challenges and how open source can help
* OPN301 - Using Rust to minimize environmental impact
* OPN302 - Upgrade to OpenSearch (Chalk Talk)
* OPN303 - Working in the open with OpenSearch (Chalk Talk)
* OPN304 - Async Rust: Hurry up and .await! (Workshop)
* OPN305 - Securing your OpenSearch data (Builder Session)
* OPN307 - OpenSearch: Building the future of search together
* OPN308 - ML with Metaflow and Kubernetes: Prototype to production on Amazon EKS
* OPN309 - AWS SaaS Boost vNext: Enabling new patterns and extensibility
* OPN311 - Build your AWS Cloud-connected embedded Linux OS faster (Chalk Talk)
* OPN312 - Building a multi-architecture CI/CD pipeline for Kubernetes (Chalk Talk)
* OPN313 - When life hands you data, grab OpenSearch (Workshop)
* OPN314 - Dive deep into cross-SDK features on AWS (Workshop)
* OPN315 - Build a PostgreSQL database cluster with Babelfish (Builder Session)
* OPN316 - Prometheus and Grafana: Integrated metrics, logs, and traces (Builder Session)

Other sessions of note include:

* AIM409 - Accelerate deep learning with cloud custom environments
* AIM12 - Deep learning applications with TensorFlow (Chalk Talk)
* ANT204 - Dive into Amazon OpenSearch Service (Workshop)
* ANT401 - Deep dive: Accelerating Apache Spark with Amazon EMR
* ARC311 - Accelerate building media analysis workflows on AWS
* CON204 - Observability & beyond with container-based services on AWS (Workshop)
* CON210 - Kubernetes scalability and dynamic scheduling
* CON305 - Automatic node provisioning with Karpenter
* CON320 - Keeping your host operating system secure with Bottlerocket (Chalk Talk)
* COP206 - Observability the open-source way
* COP316 - Open-source observability (Chalk Talk)
* COP402 - Optimizing AWS workflows with the CDK for Terraform
* DPR203 - The AWS DeepRacer open-source robotics showcase
* IOT302 - Build intelligent IoT devices faster with AWS IoT Greengrass (Chalk Talk)
* HJS304 - Code Green! The sustainability data hackathon and workshop
* NET301 - Open-source security appliances with AWS Gateway Load Balancer (Workshop)
* QTC306 - Using Julia to program quantum computers (Chalk Talk)

If you are there in person, a few things you should check out:

* Developer Lounge - there will be open source projects being show cased as well as open source builders on hand to speak with you.
* [After Dark](https://aws-oss.beachgeek.co.uk/13n) - an open source social that the open source team is organising. 

There is still time to register and attend, so find out more by checking out the [event home page.](https://aws-oss.beachgeek.co.uk/13m)

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)