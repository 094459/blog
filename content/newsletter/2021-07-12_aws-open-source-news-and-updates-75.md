---
title: 'AWS open source news and updates #75'
date: '2021-07-12'
tags : [ oss-newsletter ]
---
## 12th July, 2021 - Instalment #75

Newsletter #75.

This week we have a bumper edition, due to the fact I did not publish last week and it looks like everyone has been very busy. We have new open source projects include a light weight Java client, a tool to help you manage your AWS resources and some sample applications to help you get started with location based services, Bottlerocket and algorithmic trading. We have a new workshop on GraphQL as well as the usual round up of community and AWS blog posts, featuring lots of great content for machine and data scientists, container and devops specialists as well as developer tools and IoT. We have posts on Apache Airflow, Apache Kafka, Apache Spark, Apache Flink, Spring Boot, AWS Data Wrangler, Bottlerocket, Kubernetes, Drupal, RabbitMQ, Suricata, MySQL, Redis and many more.

I have introduced a [hands on] tag so you can see which posts have code or are walk throughs where you can end up (hopefully) with the same result as the blog post they came from!

**Feedback**

If you read this newsletter, I would love to hear what you think so I can improve it. Please [complete this very short survey](https://eventbox.dev/survey/CHG06PE) (will take you less than 60 seconds) and you may get an AWS $25 credit voucher. Thank you.

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Pratik Bhavsar, Damon Cortesi, Vu Dao, Dave Moten, Adam McQuistan, Sheldon Hull, Jens Schmidt Hansen, Steve Sklar, Kyle Neideck, Oliver Steffmann, Fernando Rocha Silva, Panna Shetty, Talia Nassi, Sam Mokhtari, Mitesh Patel, Joseph Morais, Jobin George, Roberto Luna Rojas, Shawn Wang, Asaf Porat Stoler, Itay Maoz, Yehonatan Yulazari, Maish Saidel-Keesing, Amar Mehta, Royal O’Brien, Amit Chowdhury, Saurabh Shrivastava, Michael DeRan, Chris Friedline, Netsanet Gebremadhin, Jenna Lang, Lee Pang, Nick Ragusa, Dirk Michel, Zach Gardner, Rashed Talukder, Jae M. Kim, Eddie Pick, Scott Perry, Mony Kiem, Frenil Randeria, Ripunjaya Pattnaik, Sean McArthur, Ugur Kira, Jeremy Cowan, Steve Borrelli, Rob Clark, Manabu McCloskey, Vikrant Kahlir, Nima Kaviani, Sai Sharanya Nalla, Kartik Kannapur, Narayana Vemburaj, Anjani Reddy, Shivkumar Rajendran, Ananth Vaidyanathan, and Prem Nambi.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

**aws-lightweight-client-java**

[aws-lightweight-client-java](https://aws-oss.beachgeek.co.uk/ps) if you are looking for a really  lightweight java client for the AWS API, then Dave Moten has you covered with this project. This standalone artefact (about 57K) that performs authentication (signing requests with AWS Signature Version 4) and helps you build requests against the AWS API. It includes nice concise builders, a lightweight inbuilt xml parser (to parse responses), and useful convenience methods. Perfect for those situations this is important (Mobile and functions for example)

**serverless-transformers-on-aws-lambda**

[serverless-transformers-on-aws-lambda](https://aws-oss.beachgeek.co.uk/py) Pratik Bhavsar shared his latest open source project late last week, which looks very interesting. It provides a serverless way to run your machine learning transformers. A [transformer](https://en.wikipedia.org/wiki/Transformer_(machine_learning_model)) is a deep learning model that adopts the mechanism of attention, differentially weighing the significance of each part of the input data. It is used primarily in the field of natural language processing (NLP) and in computer vision (CV)


**bottlerocket-ecs-updater-cdk**

[bottlerocket-ecs-updater-cdk](https://aws-oss.beachgeek.co.uk/pt) this project from Adam Keller provides an example of a bottlerocket deployment to Amazon ECS with the updater built as a construct. 

**collie-cli**

[collie-cli](https://aws-oss.beachgeek.co.uk/pk) is a new open source project from meshcloud that allows you to manage your AWS resources through a single view. View your tenants, tags, costs, users, access rights and more through a single common model. Check it out.

![demo](https://github.com/meshcloud/collie-cli/blob/develop/.github/collie-demo.gif?raw=true)

**amazon-location-service-musterpoint-tracker-ios**

[amazon-location-service-musterpoint-tracker-ios](https://aws-oss.beachgeek.co.uk/p2) this project helps you build a sample mobile application that show cases how to integrate both location based services as well as geofencing using the recently launched Amazon Location Service. You can dive deeper and follow along with the blog post that accompanies this project, [Create an iOS tracker application with Amazon Location Service and AWS Amplify ](https://aws-oss.beachgeek.co.uk/p3) from Fernando Rocha Silva and Panna Shetty.

![arch](https://d2908q01vomqb2.cloudfront.net/0a57cb53ba59c46fc4b692527a38a87c78d84028/2021/06/24/architecture-updated.png)

**algorithmic-trading**

[algorithmic-trading](https://aws-oss.beachgeek.co.uk/ov) this project is a hands on workshop where you will learn how to load and store financial data to build and backtest algorithmic trading strategies that use technical indicators and advanced machine learning models. You can read more about this project via the blog post from Oliver Steffmann, [Building algorithmic trading strategies with Amazon SageMaker](https://aws-oss.beachgeek.co.uk/ou)

![demo](https://github.com/aws-samples/algorithmic-trading/blob/master/assets/chart.png?raw=true)

### Community open source posts

**Apache Airflow**

[Building and Testing a new Apache Airflow Plugin](https://aws-oss.beachgeek.co.uk/px) Damon Cortesi has put together this great blog post that tells you everything you need to know about contributing an operator to Apache Airflow, sharing his experience during the work he did on a new EMR on EKS plugin to Apache Airflow. Great stuff.

**AWS Data Wrangler**

If you work with data on AWS, then there is a good chance you will find the open source project [AWS Data Wrangler](https://aws-oss.beachgeek.co.uk/pp) something you need to know more about. Not to be confused with SageMaker Data Wrangler, AWS Data Wrangler extends the capabilities of Pandas to AWS by connecting data frames to AWS data-related services. Last week it was included in ThoughtWorks Technology Radar under Trial (to find out more about this, I highly recommend you read about and subscribe to the [ThoughtWorks Technology Radar](https://aws-oss.beachgeek.co.uk/po))

Check out what they said, but I think this is a great summary:

>We've used AWS Data Wrangler in production and like that it lets you focus on writing transformations without spending too much time on the connectivity to AWS data services.

**AWS Greengrass**

I loved this post from Kyle Neideck, [Cloud-printing for Restaurants with AWS IoT Greengrass](https://aws-oss.beachgeek.co.uk/pj) which really appealed to the inner device hacker/maker in me. In this post Kyle shows you how he build a new open source project that enables restaurants to connect customers to the kitchen. Really well worth reading this project.

![arch](https://miro.medium.com/max/1225/1*H7-sLIPEJpZlWZD9bHn7TQ.png)

**Spring Boot**

[How to Create an AWS ALB and ASG](https://aws-oss.beachgeek.co.uk/ph) in this post you will learn how you can take your Spring Boot application and then configure a load balancer and an auto scaling group that will allow you to scale up and down your application in response to demand. [hands on]

**KinD**

Amazon EKS-Distro was launched during re:Invent, and is a distribution of Kubernetes that can be run in a number of different environments, including your own. In this post, [Using KinD to run EKS-D](https://aws-oss.beachgeek.co.uk/pg) Jeremy Cowan takes a look at how you can use Kubernetes in Docker (KinD) to run EKS-D clusters on your local machine. [hands on] 

**cdk8s**

Another great post from Vu Dao, this week he writes about using cdk8s (an open-source software development framework for defining Kubernetes applications and reusable abstractions using familiar programming languages - a la AWS CDK), to deploy an AWS Load Balancer for your Kubernetes application in the post [Create AWS Load Balancer Controller Ingress With CDK8S](https://aws-oss.beachgeek.co.uk/pu) 

**Terraform**

If you are a user of Terraform and have wanted to deploy an Amazon EMR cluster that can consume data from other AWS accounts (Cross Account S3 bucket access for example), then you need to read this blog post from Adam McQuistan, [How To Provision AWS EMR Cluster with Cross Account S3 Bucket Access Using Terraform](https://aws-oss.beachgeek.co.uk/pf) [hands on]

I also enjoyed reading another Terraform post from Steve Sklar, [Running Scheduled Jobs in AWS Using Terraform](https://aws-oss.beachgeek.co.uk/pi) where he shows you how you can use Terraform to automate the provisioning of a solution based on AWS Fargate, and outlines why he choose Fargate over a number of other technologies within AWS that allow you to schedule jobs. Nice post. 

**Leapp**

I have featured Leapp in previous newsletter posts, and have it running on my mac when I need to connect to various AWS instances. In this post, [Simplify Aws Developer Security With Leapp](https://aws-oss.beachgeek.co.uk/pe) Sheldon Hull shares his experience in using it so far. [hands on]

**PostgreSQL**

[Install pg_cron on AWS RDS](https://aws-oss.beachgeek.co.uk/pd) Jens Schmidt Hansen has put together this short guide on upgrading your PostgreSQL database on Amazon RDS to support scheduling jobs using pg_cron. pg_cron is a simple cron-based job scheduler for PostgreSQL (9.5 or higher) that runs inside the database as an extension. It uses the same syntax as regular cron, but it allows you to schedule PostgreSQL commands directly from the database.

### Workshops

**GraphQL**

This is a new workshop that will help you get hands on with GraphQL, building a fully functioning application for a fast-paced sports event called the GraphQL Real-time Race.

Start your engines [here](https://aws-oss.beachgeek.co.uk/pc)

### AWS and Amazon open source posts

**Open 3D Engine**

Big news last week for game developers and enthusiasts, as we announced the open sourcing of a new project Open 3D Engine (O3DE) a AAA-capable, cross-platform open source game engine. In the post, [Built for Builders: The Story of AWS and Open 3D Engine – Developer Preview](https://aws-oss.beachgeek.co.uk/oy) Amar Mehta and Royal O’Brien share the open source journey, the differences from its Lumberyard ancestor, take a look at the key features of this project and share what is coming up next.As the authors conclude:

>Our hope is that this open-source effort provides a game and simulation development platform that anyone can leverage to quickly build even more amazing games and real-time simulations.

![image](https://d2908q01vomqb2.cloudfront.net/91032ad7bbcb6cf72875e8e8207dcfba80173f7c/2021/07/01/O3DE-002.jpg)

**AWS IoT C-SDK**

In [How being open led to greater customer value with the AWS IoT Device SDK for Embedded C](https://aws-oss.beachgeek.co.uk/p6), Rashed Talukder writes how adopting and collaborating with leading open source projects helped developers make the AWS IoT C-SDK more trustworthy and flexible, while increasing ease of use. A great post when considering what you can apply when thinking about your own particular use case.

**curl**

Curl is one of those foundational libraries that we take for granted, but that influences our lives online. Following from a Webinar that discussed memory safety and the internet, Sean McArthur shares some of the key talking points from that webinar, which you can check out in the post [How using hyper in curl can help make the internet safer](https://aws-oss.beachgeek.co.uk/pa)

**VS Code**

Nick Ragusa has put together probably my most favourite blog post this week in , [Field Notes: Use AWS Cloud9 to Power Your Visual Studio Code IDE](https://aws-oss.beachgeek.co.uk/p4). In this blog post and walkthrough, he shows you how you can combine the power of AWS Cloud9 together with VS Code (which is also my day to day development tool) to overcome challenges such as disk space or CPU exhaustion. Very nice post. 

![arch](https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2021/06/30/Visual-Studio-Ref-Architecture.png)

**Apache Flink**

[Get started with Flink SQL APIs in Amazon Kinesis Data Analytics Studio](https://aws-oss.beachgeek.co.uk/os) in this blog post, Sam Mokhtari and Mitesh Patel demonstrate different query patterns you can use to get insight from streaming data using Apache Flink SQL APIs. The post provides you with examples of Flink SQL queries that you can run within Kinesis Data Analytics Studio, so you can experiment for your self. [hands on]

We also had this two part post, Build and optimise real-time stream processing pipeline with Amazon Kinesis Data Analytics for Apache Flink,[Part1](https://aws-oss.beachgeek.co.uk/p1) [Part 2](https://aws-oss.beachgeek.co.uk/p0) from Amit Chowdhury and Saurabh Shrivastava who show you how you can build a reliable, scalable, and highly available streaming application based on Apache Flink and Kinesis Data Analytics. They use the telemetry data of a taxi fleet in New York City in real time to optimise fleet operation. Whilst part one focused on getting this setup, part two dive deep into the things you need to look to ensure the health and performance of the Amazon Kinesis Data Analytics for Apache Flink application. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2021/06/29/bdb1482-1-image015.png)

**Apache Kafka**

Joseph Morais, AWS Evangelist over at Confluent, in collaboration with Jobin George and Roberto Luna Rojas from AWS have put together this post, [Low Latency Real-Time Cache Updates with Amazon ElastiCache for Redis and Confluent Cloud Kafka](https://aws-oss.beachgeek.co.uk/ot) that shows you how you can power a logistics and inventory system with microsecond read performance powered Redis and Apache Kafka (powered by Confluent Cloud) [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/77de68daecd823babbb58edb1c8e14d7106e83bb/2021/06/29/Confluent-ElastiCache-Redis-4.png)

**MySQL**

MySQL binlog replication is a popular feature serving multiple use cases, including offloading transactional work from a source database, replicating changes to a separate dedicated system to run analytics, and streaming data into other systems. In the post, [Introducing binlog I/O cache in Amazon Aurora MySQL to improve binlog performance](https://aws-oss.beachgeek.co.uk/p7) Jae M. Kim shows you show performance improvements of the new binlog I/O cache introduced in the Aurora MySQL 2.10 release and explores its related monitoring metrics and status variables.

![arch](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2021/06/23/dbblog-1727_01.png)

**Redis**

In this post [Reduce cost and boost throughput with Global Datastore for Amazon ElastiCache for Redis](https://aws-oss.beachgeek.co.uk/ow) Shawn Wang, Asaf Porat Stoler, Itay Maoz, and Yehonatan Yulazari show you how you can use Redis (specifically some features available in Amazon ElastiCache for Redis) to reduce latency of data access for better geo-local performance, thanks to improvements made from Redis 6 that resulted in significant throughput improvements. Read on to find out more.

![bench](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2021/06/25/dbblog1424-01.png)

In another Redis post, Dirk Michel from MYCOM OSI together with Zach Gardner from AWS share the story of how they moved from self-managed Redis to using Amazon ElastiCache for Redis, including the benefits achieved, the migration journey, and the architectures involved. Read more in [MYCOM OSI Service Impact Engine migration to Amazon ElastiCache for Redis](https://aws-oss.beachgeek.co.uk/p5).

![arch](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2021/06/30/dbblog1656-03.png)

**Nextflow**

The Genome Analysis Toolkit (GATK), is a BSD open source genomic analysis toolkit developed by the Data Sciences Platform team at the Broad Institute, that provides tools for genomic variant discover and genotyping. The blog post, [Running GATK workflows on AWS: a user-friendly solution](https://aws-oss.beachgeek.co.uk/oz) that was co-authored by Michael DeRan, Chris Friedline, Netsanet Gebremadhin at Diamond Age Data Science and Jenna Lang and Lee Pang from AWS, shows you how you can simplify how you run this on AWS using Nextflow, an open source bioinformatics workflow manager that enables the development of portable and reproducible workflows.

![arch](https://d2908q01vomqb2.cloudfront.net/c5b76da3e608d34edb07244cd9b875ee86906328/2021/06/24/Architecture-B-Workflow-infrastructure-using-FSx-for-Lustre-storage-deployed-with-Nextflow-Tower.png)

The post links to a GitHub repository where you can find the resources you need to dive deeper. 

**RabbitMQ**

RabbitMQ is an open-source message broker to which applications connect in order to transfer a message or messages between services. In this post, [Using Amazon MQ for RabbitMQ as an event source for Lambda](https://aws-oss.beachgeek.co.uk/or) Talia Nassi shows you how to set up a RabbitMQ broker and networking configuration, and how to create a Lambda function that is invoked by messages from Amazon MQ RabbitMQ queues. [hands on]

**Hugging Face**

Hugging Face Transformers is a popular open-source project that I have written about in previous editions of this newsletter, and makes it super easy to use a variety of pre-trained, natural language processing (NLP) models for a wide variety of use cases. In the blog post, [Hosting Hugging Face models on AWS Lambda for serverless inference](https://aws-oss.beachgeek.co.uk/p8) Eddie Pick and Scott Perry have put together this solution that automatically provisions container image-based Lambda functions that perform ML inference using pre-trained Hugging Face models. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2021/06/28/architecture-1.png)

To add to that, Sai Sharanya Nalla and Kartik Kannapur put this post together last week, [Announcing managed inference for Hugging Face models in Amazon SageMaker](https://aws-oss.beachgeek.co.uk/pq) where they discuss different methods to create a SageMaker endpoint for a Hugging Face model.

**Bottlerocket**

Bottlerocket OS in an open source project that was built to provide a secure foundation for hosts running containers, minimising operational overhead to manage them at scale. In the blog post, [Getting started with Bottlerocket and Amazon ECS](https://aws-oss.beachgeek.co.uk/ox) Maish Saidel-Keesing walks you through how you can use Amazon ECS and Bottlerocket together to run your applications in a safe and secure manner.

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2021/07/06/image-2021-07-06T104447.977.png)

We also had Narayana Vemburaj and Anjani Reddy post [Persistent Storage using EFS for EKS on Bottlerocket](https://aws-oss.beachgeek.co.uk/pv) showing you how you can set up persistent storage with Amazon Elastic Kubernetes Service (Amazon EKS) clusters running on Bottlerocket OS with Amazon Elastic File System (Amazon EFS).

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2021/07/02/EFS-Persistent-Diagram-19May.png)

**Fluentd**

Fluentd is a popular open source project for streaming logs from Kubernetes pods to different backends aggregators like CloudWatch. It is often used with the kubernetes_metadata filter, a plugin for Fluentd that enriches the logs with basic metadata such as the pod’s namespace, UUIDs, labels, and annotations. In this post, [Fluentd considerations and actions required at scale in Amazon EKS](https://aws-oss.beachgeek.co.uk/pb), Ugur Kira and Jeremy Cowan analyze the impact the plug-in has on the Kubernetes API and recommend how to optimally configure Fluentd and the kubernetes_metadata plug-in in large clusters. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2021/06/22/image4-1.png)

**OpenTelemetry**

Alolita Sharma and Nizar Tyrewalla announced the latest release of AWS Distro for OpenTelemetry, which you can read about in the post [AWS Distro for OpenTelemetry (ADOT) 0.11.0 is now available](https://aws-oss.beachgeek.co.uk/pr).

**Spinnaker**

Steve Borrelli and Rob Clark from Upbound, and Manabu McCloskey, Vikrant Kahlir, and Nima Kaviani from AWS collaborated on this post, [Declarative provisioning of AWS resources with Spinnaker and Crossplane](https://aws-oss.beachgeek.co.uk/pn). The post looks at the setup and configuration required for Spinnaker and Crossplane to work together. Crossplane is an open source project that allows teams to manage cloud resources in a Kubernetes-native way, which means you can provision and manage Amazon Simple Storage Service (Amazon S3) buckets, VPCs, databases, and Lambda functions in the same way you manage Pods, Ingresses, and StatefulSets. [hands on]

**Suricata**

Suricata is open-source network threat detection engine is capable of real-time intrusion detection (IDS), that also provides inline intrusion prevention (IPS), network security monitoring (NSM), and offline packet capture processing. AWS Network Firewall uses Suricata and in the blog post, [Integrate AWS Network Firewall with your ISV Firewall Rulesets](https://aws-oss.beachgeek.co.uk/p9) you can read from Mony Kiem, Frenil Randeria, and Ripunjaya Pattnaik how to operate a hybrid architecture using the same firewall and IPS rules for both your on-premises and cloud networks.

![arch](https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2021/06/23/Fig1-Firewall.png)

**Drupal**

[Deploy serverless Drupal applications using AWS Fargate and Amazon EFS](https://aws-oss.beachgeek.co.uk/pw) in this post, Shivkumar Rajendran, Ananth Vaidyanathan, and Prem Nambi show you how to build a highly available, cost-effective, scalable Drupal-based website on AWS Cloud. The architecture uses serverless compute, serverless storage, and a serverless database, with no infrastructure to manage.

![arch](https://d2908q01vomqb2.cloudfront.net/e1822db470e60d090affd0956d743cb0e7cdf113/2021/07/08/Deploy-serverless-Drupal-using-AWS-Fargate-and-Amazon-EFS-architecture-diagram.png)

### Quick updates

**RabbitMQ**

You can now use the consistent hash exchange type on your Amazon MQ for RabbitMQ brokers. This exchange type uses consistent hashing to uniformly distribute messages across queues. Consistent hash exchanges are useful in applications like transaction processing to maintain the order of dependent messages while scaling up the number of consumers.

**AWS ParallelCluster**

AWS ParallelCluster is a fully supported and maintained open source cluster management tool that makes it easy for scientists, researchers, and IT administrators to deploy and manage High Performance Computing (HPC) clusters in the AWS cloud. HPC clusters are collections of tightly coupled compute, storage, and networking resources that enable customers to run large scale scientific and engineering workloads. Significant feature enhancements to this latest release of AWS ParallelCluster 2.11 include:

* Support for Ubuntu 20.04 Operating System - Customers can now choose Ubuntu 20.04 as their base operating system of choice to run their clusters for both x86 and Arm architectures
* FSx for Lustre in isolated subnets - Customers can now set up and mount an Amazon FSx for Lustre file system in AWS ParallelCluster without requiring public internet access. This gives customers an additional option for how they can help keep their HPC environments secure and isolated inside of AWS.

**Bottlerocket**

Announced last week was the General Availability of the Amazon ECS optimised Bottlerocket Amazon Machine Image (AMI). Bottlerocket is an open source Linux-based Operating System (OS) that is purpose-built to run containers. 

Bottlerocket only includes essential software that are required to run containers, helping customers significantly reduce the attack surface and impact of vulnerabilities. Bottlerocket’s root filesystem is read-only, backed by dm-verity. The kernel blocks all direct writes, and behind the scenes will detect any modification as corruption and reboot the host. It also comes with Security-Enhanced Linux (SELinux) policies enabled in enforcing mode for additional isolation. In addition to these security enhancements, updates to Bottlerocket are applied and rolled back in an atomic manner, reducing update complexity and failures.

**Linux**

AWS Client VPN now supports SAML based federated authentication for opening a VPN connection from a Linux Desktop Operating system (Ubuntu 64bit 18.04 and 20.04 LTS). The Linux Desktop client has feature parity with the existing Windows and macOS Desktop clients.

AWS Client VPN allows you to choose from AWS VPN Desktop Client or OpenVPN-based clients, giving your employees the option to use the device of their choice.

AWS Client VPN Desktop Clients are available free of charge, and can be downloaded [here](https://aws-oss.beachgeek.co.uk/oq).


**Apache Kafka**

AWS Lambda functions that are triggered from self-managed Apache Kafka topics can now access usernames and passwords secured by AWS Secrets Manager using SASL/PLAIN, a simple username/password authentication mechanism that is typically used with TLS for encryption to implement secure authentication. This is in addition to SASL/SCRAM, which is already supported on Lambda. To get started, customers who select Apache Kafka as the event source for their Lambda function can choose SASL/PLAIN as their authentication mechanism, and select their credentials from Secrets Manager on the AWS Management Console, AWS CLI or AWS SDK for Lambda.

**MariaDB**

Amazon Relational Database Service (Amazon RDS) for MariaDB now supports MariaDB minor versions 10.2.37, 10.3.28, 10.4.18, and 10.5.9. 

### Events for your diary

**Developing Secure Open Source Software (OSS)** [FREE Event]
**July 20th, 9:30 – 11:00am PDT**

David Wheeler, Director of Open Source Supply Chain Security at The Linux Foundation will discuss steps you can take to develop more secure OSS and evaluate OSS for security.

Read more and [register here](https://aws-oss.beachgeek.co.uk/pm)

**ML Dev Day Live Workshop** [FREE Event]
**July 21st 9:00am PDT**


Learn how to build highly scalable and reliable pipelines for analytics using open source technologies such as Apache Spark, Delta Lake and open source machine learning frameworks such as TensorFlow, XGBoost, scikit-learn and MLFlow.

Read more and [register here](https://aws-oss.beachgeek.co.uk/pl).

**Cloud Native Day**
**23rd September, Bern Switzerland**

What is this, an in person event returning? A stellar line up including our own Michael Hausenblas, an event looking at CNCF projects and the future of IT. Find out more and to view prices/register, by clicking [here](https://cloudnativeday.ch/en/#speakers).


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen