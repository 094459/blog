---
title: 'AWS open source newsletter #179'
date: '2023-11-13'
tags : [ oss-newsletter, aws open source, Test Containers, WordPress, PySpark, Amazon EMR, Kubernetes, Amazon EKS, FluxCD, OpenSearch, PostgreSQL, LangChain, Kani, MySQL, MariaDB, dbt, Apache Ranger, Apache Hudi, Prometheus, Grafana, Jupyter, Apache Airflow, Karpenter, AWS CDK, Ragna ]
---

## November 13th, 2023 - Instalment #179

Welcome to #179 of the AWS open source newsletter, the place for all your AWS and open source needs. This weeks new projects include an open source tool that provides similar capabilities to AWS Control Tower, a tool for enrolling your Mac based EC2 instances into mobile device management (MDM) solution, a very neat tool to help you compare costs of running your CodePipeline jobs, as well as sample code that shows you how you can use Karpenter to optimise IP address use, examples of using Test Containers with AWS CDK, generative AI technologies such as LangChain, and more.

We have some great blog posts to share this week, including one on Kani, an open source automated reasoning tool which is a must read, and an extensive selection of data and analytics content that really hit the spot. Also featured this week is content featuring WordPress, PySpark, Amazon EMR, Kubernetes, Amazon EKS, FluxCD, OpenSearch, PostgreSQL, LangChain, MySQL, MariaDB, dbt, Apache Ranger, Apache Hudi, Prometheus, Grafana, Jupyter, Apache Airflow and more. As always, we finish strong with videos and events for your diary, so make sure you do not miss those.

**Feedback**

Please please please take 1 minute to [complete this short survey](https://www.pulse.aws/promotion/10NT4XZQ). I have AWS credit codes for the first 50 as a thank you! 

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes:  Oguzhan Yilmaz, Telophase,  Ian Mckay, Elizabeth Fuentes, James Eastham, Qasim H, Daniel German Rivera, Salam Shaik, Sophia Parafina, Banjo Obayomi, Abhishek Gupta, Rahul Kumar, Manasi Bhutada, Hernan Garcia, Donnie Prakoso, Peipei Yin, Jeremy Schneider, Muhammad Ali, Vadim Savin, Fahd Mirza, and all the others featured in the blog posts this week.

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution. The projects mentioned here do not represent any formal recommendation or endorsement, I am just sharing for greater awareness as I think they look useful and interesting!*

#### Tools

**amazon-ec2-mac-mdm-enrollment-automation**

[amazon-ec2-mac-mdm-enrollment-automation](https://github.com/aws-samples/amazon-ec2-mac-mdm-enrollment-automation)  enroll-ec2-mac is an AppleScript made to automatically enrol Amazon Web Services Elastic Compute Cloud (EC2) Mac instances into a mobile device management (MDM) solution. enroll-ec2-mac is made to ensure the MDM “pairing“ relationship isn't broken for MDM enrolment. Without that pairing, an EC2 Mac instance isn’t able to ”listen“ for new or updated profiles from the MDM server. enroll-ec2-mac performs all of this without any user interaction after AMI configuration (as per the instructions below). Included is a subroutine to automate the issuance and retrieval of Jamf enrolment profiles.

**telophasecli**

[telophasecli](https://aws-oss.beachgeek.co.uk/3eu) is a new tool from the folks at Telophase that provides an open source alternative to AWS Control Tower. If you are looking for a solution that provides capabilities similar to AWS Control Tower, but are looking for less ClickOps and more DevOps, then why not check this project out.

**codepipeline-cost-compare**

[codepipeline-cost-compare](https://aws-oss.beachgeek.co.uk/3ev) is the latest tool from AWS Hero Ian Mckay,  that allows you to compare the costs of V1 and V2 CodePipeline types based on historic usage. The script will process all pipelines within your AWS account and may take a few minutes to run in its entirety. Per-pipeline costs will be printed as they complete. Very cool indeed.

![screenshot of tool output](https://repository-images.githubusercontent.com/716962610/5ae62dfd-bc45-485f-8f02-563ac03f122b)

### Demos, Samples, Solutions and Workshops

**aws-private-assistant**

[aws-private-assistant](https://aws-oss.beachgeek.co.uk/3et) is a really cool demo from my colleague Elizabeth Fuentes, that helps you deploy an application integrated with WhatsApp that allows you to chat with an LLM hosted on Amazon Bedrock and you can also send it voice notes and it will return the transcription of it.

![overview of architecture of aws private assistant](https://github.com/elizabethfuentes12/aws-private-assistant/blob/main/imagenes/arquitectura.png?raw=true)

**karpenter-eks-vpc-secondary-cidr**

[karpenter-eks-vpc-secondary-cidr](https://aws-oss.beachgeek.co.uk/3ew) Oguzhan Yilmaz has put together this repo to provide examples of how you can use Karpenter when creating an EKS setup with Secondary CIDR block for Pod IP addresses. He provides details as to why you might want to do this, and code needed to get you up and running quickly.

![overview of karpenter and secondary cidr](https://github.com/oguzhan-yilmaz/karpenter-eks-vpc-secondary-cidr/raw/main/docs/images/secondary-cidr-block-diagram.png?raw=true)

**java-fm-playground**

[java-fm-playground](https://aws-oss.beachgeek.co.uk/3er) my colleagues have been hard at work creating some cool demo repositories to help Java developers get started with generative AI.
 
 ![example screenshot of java playground](https://github.com/build-on-aws/java-fm-playground/blob/main/screenshot.png?raw=true)
 
**serverless-test-containers**

[serverless-test-containers](https://aws-oss.beachgeek.co.uk/3es) James Eastham leverages Test Containers, an open source framework for providing throwaway, lightweight instances of databases, message brokers, web browsers, or just about anything that can run in a Docker container, in this repo to provide some samples that show how you can do testing integrations between: AWS CDK to define serverless applications with .NET, a CRUD API build with ASP.NET for a web application, and xUnit along with TestContainers to test with emulation. 

### AWS and Community blog posts

**Community round up**

In this weeks community round up we start with AWS Community Builder Qasim H who has put together [Batch Processing using PySpark on AWS EMR](https://aws-oss.beachgeek.co.uk/3ek) which is perfect for those of you who are curious to learn more about batch processing, and specifically how you can do this with PySpark using Amazon EMR. From batch processing we move to GitOps and AWS Community Builder Daniel German Rivera with his post, [SmartCash Project - GitOps with FluxCD](https://aws-oss.beachgeek.co.uk/3el). This is part of a series that Daniel is doing, and in this post he looks at FluxCD and how you can use this to create a GitOps workflow. If you want to know about either of these, then check it out. Next up we have AWS Community Builder Salam Shaik with his post [Using DMS to replicate data from RDS(MySQL) to Open Search](https://aws-oss.beachgeek.co.uk/3en).  Salam provides a hands on guide on how you can use the Database Migration Service tooll to help you move data between these two open source databases.

To finish up this week, I have a few of posts from my colleagues. First up is Sophia Parafina with [Migrating to WordPress on AWS Lightsail for Easier Maintenance](https://aws-oss.beachgeek.co.uk/3eo), with an essential read for those of you still using WordPress. Next up is Banjo Obayomi with [Building Custom LangChain Agents and Tools with Amazon Bedrock](https://aws-oss.beachgeek.co.uk/3ep). I love reading and checking out Banjo's code, as I always learn something new and interesting, and in this post Banjo walks you through what is a LangChain Agent, before embarking on an adventure to build something with it (no spoilers, but it might be something to do with interacting with the Well Architected Framework). To finish up this week we have Abhishek Gupta, who Goes wherever Go is, in his post [Building LangChain applications with Amazon Bedrock and Go - An introduction](https://aws-oss.beachgeek.co.uk/3eq) and shows you that it is not just Python folk who can play with LangChain, Go developers can too!

**Kani**

Rahul Kumar takes a look at the Kani Rust Verifier (or Kani, for short), an open source automated reasoning tool developed by Amazon Web Services for analysing and proving properties of your Rust code in the post, [How Open Source Projects are Using Kani to Write Better Software in Rust](https://aws-oss.beachgeek.co.uk/3eg). At AWS, we have used Kani on projects such as Firecracker and s2n-quic, and we are excited that the broader open source community continues to find more applications for Kani as well. This post highlights some of the notable examples of Kani’s impact. Great post, and a must read this week.

**Ragna**

I am always on the look out for interesting new projects to check out, and this week I came across [Ragna](https://aws-oss.beachgeek.co.uk/3e6), an open source Retrieval Augmented Generation [RAG](https://aws-oss.beachgeek.co.uk/3e7) orchestration framework. It is a new project with a committed and active community, so I wanted to find out more about this project. I spent a couple of days kicking the tyres and then looking at how to integrate the foundation models that are available within Amazon Bedrock. You can find out more and try for yourself by reading my post, [Unboxing Ragna: Getting hands on and making it to work with Amazon Bedrock](https://blog.beachgeek.co.uk/getting-started-with-ragna/)

![ragna with amazon bedrock fm anthropic claudev2](https://ricsuepublicresources.s3.eu-west-1.amazonaws.com/images/ragna-bedrock-query.png)

**Data and Analytics**

* [Automating application-consistent Amazon EBS Snapshots for MySQL and PostgreSQL](https://aws-oss.beachgeek.co.uk/3ei) walks through the use of Amazon Data Lifecycle Manager and AWS Systems Manager to automate the creation of application-consistent EBS Snapshots for self-managed MySQL and PostgreSQL databases [hands on]

* [Accelerate HNSW indexing and searching with pgvector on Amazon RDS for PostgreSQL](https://aws-oss.beachgeek.co.uk/3ej) explores several strategies to help maximise performance when using HNSW indexing with pgvector on Amazon Relational Database Service (Amazon RDS) for PostgreSQL [hands on]

![benchmark graph of HNSW indexing impact](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2023/11/06/DBBLOG-3708_graph4_v2.png)

* [Create a modern data platform using the Data Build Tool (dbt) in the AWS Cloud](https://aws-oss.beachgeek.co.uk/3ed) explores why you should check out dbt to build high performing and effecient data platforms [hands on]

![dbt on aws architecture](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2023/10/03/DBT373arch.png)

* [Implement fine-grained access control in Amazon SageMaker Studio and Amazon EMR using Apache Ranger and Microsoft Active Directory](https://aws-oss.beachgeek.co.uk/3ee) walks you through how you can implement fine-grained access control in SageMaker Studio and Amazon EMR using Apache Ranger and Microsoft Active Directory [hands on]

![overview of amazon emr and apache ranger architecture](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2023/10/27/BDB3441_image002.png)

* [How Onehouse Makes it Easy to Leverage Open Source Data Services on AWS](https://aws-oss.beachgeek.co.uk/3ef) takes a closer look at why you should look at Apache Hudi on AWS when building high performance, low-latency data lakehouse solutions

**Other posts and quick reads**

* [Monitoring GPU workloads on Amazon EKS using AWS managed open-source services](https://aws-oss.beachgeek.co.uk/3eb) explores how to leverage the AWS CDK Observability Accelerator (mentioned in [#163](https://dev.to/aws/aws-open-source-newsletter-163-m0a))  to quickly build observability for GPU workloads on Amazon EKS, using AWS managed open-source services and NVIDIA tools [hands on]

![overview of open source monitoring services on aws](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2023/11/06/CO1555_Fig1-2.png)

* [On-premises egress design patterns for Amazon EKS](https://aws-oss.beachgeek.co.uk/3ec) dives deep into four uses cases of Egress Architecture Patterns that solve the egress source IP challenge (source IP address is still used by on-premise firewalls as the identifier of a certain system or service, and is used for controlling access) [hands on]

![architecture for source ip and kubernetes](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2023/11/09/Source-NAT.png)

* [How to improve your security incident response processes with Jupyter notebooks](https://aws-oss.beachgeek.co.uk/3eh) is a hands on guide on how to use Jupyter Notebook to investigate a security event, showing you how you can automate the tasks of gathering data, presenting the data, and providing procedures and next steps for the findings [hands on]

### Quick updates
 
 **Apache Airflow**
 
 Big news last week from one of my favourite AWS services, Amazon Managed Workflows for Apache Airflow (MWAA). You can now create Apache Airflow version 2.7 environments and execute deferrable operators on Amazon Managed Workflows for Apache Airflow (MWAA). Apache Airflow 2.7 is the latest minor release of the popular open-source tool that helps customers author, schedule, and monitor workflows.

Amazon MWAA is a managed orchestration service for Apache Airflow that makes it easier to set up and operate end-to-end data pipelines in the cloud. Apache Airflow version 2.7 on Amazon MWAA introduces deferrable operator support, enabling a higher number of tasks to run concurrently with fewer resources. Deferrable operators free up worker slots while they wait for their tasks to complete, and are supported with popular AWS services such as Amazon EMR, Amazon ECS, and AWS Glue. This update also brings improvements such as the cluster activity page, automatic setup/teardown tasks, and secrets cache. Additionally, Airflow 2.7 on Amazon MWAA now runs on Python 3.11 and is built on the Amazon Linux 2023 (AL2023) base image, offering enhanced security, modern tooling, and support for the latest Python libraries and features.

Why not check out the supporting blog post, [Introducing Amazon MWAA support for Apache Airflow version 2.7.2 and deferrable operators](https://aws-oss.beachgeek.co.uk/3e8), where Manasi Bhutada and Hernan Garcia look at some of the great new features available to you, including deferrable operators and triggers, setup and teardown tasks, and more!

![screenshot of apache airflow 2.7.2 new features](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2023/11/04/Picture-7-1.png)
  
 **MySQL and MariaDB**

We had a few updates this week.
 
Amazon Relational Database Service (Amazon RDS) for MySQL now supports MySQL minor version 5.7.44. We recommend you upgrade to the latest minor versions to benefit from the security patches, bug fixes, and performance improvements added by the MySQL community. MySQL 5.7 reached community end of life in October, 2023 and will reach RDS end of standard support on Feb 29, 2024. If you do not plan to use MySQL 5.7 after Feb 29, 2024, we recommend you upgrade to MySQL 8.0 at the earliest. If you are planning to use MySQL 5.7 beyond that date, we recommend you opt in to Amazon RDS Extended Support starting in December 2023. RDS Extended Support is offered exclusively on Amazon RDS for MySQL version 5.7.44. 
 
Amazon RDS Optimized Writes now supports M5 database (DB) instances. With Amazon RDS Optimized Writes you can improve the write throughput for Amazon RDS for MySQL and MariaDB workloads by up to 2x at no additional cost. This is especially useful for write-intensive database workloads, commonly found in applications such as digital payments, financial trading, and online gaming. In MySQL or MariaDB, you are protected from data loss due to unexpected events, such as a power failure, using a built-in feature called the “doublewrite buffer” that takes up to twice as long, consumes twice as much I/O bandwidth, and reduces the throughput and performance of your database. Amazon RDS Optimized Writes only once while protecting you from data loss. With Amazon RDS Optimized Writes you can improve write throughout by up to 2x at no additional cost. Amazon RDS Optimized Writes is available as a default option from RDS for MySQL version 8.0.30 and higher, and RDS for MariaDB version 10.6.10 and higher. 

Amazon Aurora MySQL zero-ETL integration with Amazon Redshift is now generally available, enabling near real-time analytics and machine learning (ML) using Amazon Redshift to analyse petabytes of transactional data from Amazon Aurora MySQL-Compatible Edition. Within seconds of transactional data being written into Aurora, the data is available in Amazon Redshift. You don’t need to build and maintain complex data pipelines to perform extract, transform, and load (ETL) operations. Amazon Aurora MySQL zero-ETL integration with Amazon Redshift is now available for Amazon Aurora Serverless v2 and Provisioned and Amazon Redshift Serverless and RA3 instance types. Zero-ETL integration helps you derive holistic insights across many applications and break data silos in your organisation, making it simpler to analyse data from one or multiple Aurora database clusters in an Amazon Redshift warehouse. Enhance your data analysis with the rich analytics capabilities of Amazon Redshift, such as high performance SQL, built-in ML and Spark integrations, materialised views, data sharing, and direct access to multiple data stores and data lakes. Amazon Aurora MySQL zero-ETL integration with Amazon Redshift is now available for Aurora MySQL 3.05 (compatible with MySQL 8.0.32) and higher.

Check out the supporting blog post from Donnie Prakoso, [Amazon Aurora MySQL zero-ETL integration with Amazon Redshift is now generally available](https://aws-oss.beachgeek.co.uk/3e9).

Amazon RDS for MySQL saw improvements delivered last week,  that provides up to 3X higher write throughput at no additional charge, starting with RDS for MySQL version 8.0.35. If you're running RDS for MySQL version 8.0.34 or lower, you can upgrade to RDS for MySQL version 8.0.35 to benefit from this performance improvement. We recommend that you upgrade to the latest minor versions to fix known security vulnerabilities in prior versions of MySQL, and to benefit from the bug fixes, performance improvements, and new functionality added by the MySQL community.

**PostgreSQL**

A couple of nice updates this week for folks interested in PostgreSQL.

Amazon Aurora Global Database for PostgreSQL now lets you forward write requests from a secondary to a primary Region, simplifying writing from multiple Regions and making it easier to develop globally distributed applications. With this launch, write forwarding is now available on both Aurora Global Database for MySQL and PostgreSQL. Amazon Aurora Global Database allows a single Aurora database to span multiple AWS Regions, providing disaster recovery from Region-wide outages and enabling fast local reads for globally distributed applications. With write forwarding, your applications can simply send both read and write requests to a reader in a secondary Region, and Global Database will take care of forwarding the write requests to the writer in the primary Region. You can also use different consistency levels that meet your application needs. Global Database write forwarding is supported on Aurora MySQL versions 2.08.1 or higher, and Aurora PostgreSQL versions 14.9, 15.4, or higher. You can enable the feature using the AWS Management Console, Command Line Interface (CLI), or RDS API by turning on the "enable global write forwarding" option. The feature is available in all AWS regions where Aurora Global Database for PostgreSQL is available.

AWS announced Amazon Aurora Optimized Reads for Aurora PostgreSQL, a new price-performance capability available on new r6gd and r6id instances that delivers up to 8x improved query latency and up to 30% cost savings compared to instances without it, for applications with large datasets that exceed the memory capacity of a database instance. Optimized Reads uses the local NVMe-based SSD block-level storage available on r6gd and r6id instances to store ephemeral data, reducing the data accesses to/from network-based storage offering improved read latency and throughput. These instances host temporary tables on the local storage (instead of network-based storage), delivering improved query performance for complex queries and faster index rebuild operations. Optimized Reads instances using I/O-Optimized use the local storage to extend their caching capacity. Database pages that are evicted from the in-memory buffer cache are cached onto local storage to speed subsequent retrievals of that data. This delivers up to 8x improved query latency, and enables Amazon Aurora PostgreSQL Optimized Reads with pgvector to increase queries per second for vector search by up to 9x in workloads that exceed available instance memory, accelerating the performance of Machine Learning and Generative AI applications.

Gowri Balasubramanian, Peipei Yin, and Jeremy Schneider have come together to share more details about this update in their post, [New – Amazon Aurora Optimized Reads for Aurora PostgreSQL with up to 8x query latency improvement for I/O-intensive applications](https://aws-oss.beachgeek.co.uk/3ea).

![screenshot of benchmark](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2023/11/01/dbblog-3512-image007.jpg)

### Videos of the week

**Building an open source observability platform with AWS**

Fresh from the ASEAN summit we have this video from Muhammad Ali, that looks at how you can use open-source tools, SDKs, and standards with Amazon OpenSearch Service to make your applications observable. Did you know an average company loses over $100K for every hour of downtime in their business applications and 90% of issue resolution time is spent identifying the problem? Making your distributed application observable and improving your incident response is vital in reducing the meantime to resolution. Observability platform provides tooling to accelerate the process of detecting, investigating and remediating issues. Check out this video to find out more how open source can help you. 

{{< youtube YyG9aQSsWFk >}}

**AWS EKS 101: Deploying Kubernetes to AWS Cloud**

Vadim Savin takes you on this extended video diving deep into deploying Kubernetes to AWS Cloud using AWS's powerful EKS service. This video includes a lot of tools and technologies, providing an excellent opportunity to learn about: an overview of AWS EKS and its integration with Kubernetes, a step-by-step instructions for setting up a Kubernetes cluster on EKS, best practices for managing and monitoring your EKS deployments, and finally, integrating Cast.ai with AWS EKS for optimized performance and cost reductions of up to 50%.

{{< youtube qRSB0aPcf_s >}}


**Using LangChain Templates for AWS Bedrock**

Check out Fahd Mirza's short video that walks you through the recently out LangChain Templates, to see how you can use these with Amazon Bedrock. LangChain Templates offers a collection of easily deployable reference architectures that anyone can use. 

{{< youtube 986CKmvLSjs >}}

# Events for your diary

If you are planning any events in 2023, either virtual, in person, or hybrid, get in touch as I would love to share details of your event with readers. 

**AWS User Group, Palma**
**November, 14th, 5pm-9pm Parc Bit - Fundació IBIT**

I am happy to join Miguel Salvà at the PAWS (AWS User Group in Palma) for an evening of open source talks, covering a broad range of topics from OSPO's, working with open source communities, and open source at Aamzon. Going to be great. You can find out more by checking out the user groups page, [PAWS User Group](https://aws-oss.beachgeek.co.uk/3b6)

**Big Data Europe**
**21st-24th November, Online/Vilnius, Lithuania**

I will be speaking at the Big Data Europe event, talking about how you can shift left and apply modern developer approaches to manage your Apache Airflow workflows. This builds upon a lot of the other work I have done in this space, so am really looking forward to doing this talk.

Check out the[ event page ](https://labsoflatvia.com/en/events/big-data-conference-europe-2023)for registration details, as well as to check out all the other sessions - many of which feature open source projects and technologies.

**re:Invent**
**November, 27th-1st December, Las Vegas, USA**

The annual must attend conference for all AWS developers is back, and with another strong line up of open source sessions, chalk talks, builder sessions, workshops and more. There will be a super cool open source booth, with a line up of great demos - I have taken a sneak look and so make sure you check out the demo schedule on the booth.

Find out more by checking out the event page, [re:Invent 2023](https://reinvent.awsevents.com/)


**Cortex**
**Every other Thursday, next one 16th February**

The Cortex community call happens every two weeks on Thursday, alternating at 1200 UTC and 1700 UTC. You can check out the GitHub project for more details, go to the [Community Meetings](https://aws-oss.beachgeek.co.uk/2h5) section. The community calls keep a rolling doc of previous meetings, so you can catch up on the previous discussions. Check the [Cortex Community Meetings Notes](https://aws-oss.beachgeek.co.uk/2h6) for more info.

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)

### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)