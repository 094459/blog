---

title: 'AWS open source newsletter #140'
date: '2023-01-09'
tags : [ oss-newsletter, aws open source, MySQL, PostgreSQL, Next.js, AWS SDK for Java, AWS ParallelCluster, Docker, MariaDB, Amazon EKS, Kubernetes, MQTT, ArgoCD, AWS Distro for OpenTelemetry, Prometheus, DAMON, Crossplane, Log4Shell, .NET, Apache Spark, Apache Kafka, Apache Flink, Apache Pinot, Apache Superset, Apache NiFi, Delta Lake, OpenShift, Redis, Red Hat Enterprise Linux, SUSE Linux Enterprise Server, Ubuntu Pro, AWS Copilot, RabbitMQ, Apache Airflow, Rust, Terraform, Amazon EMR, Apache ShardingSphere-Proxy]

---

## January 9th, 2023 - Instalment #140

**Welcome**

Happy New Year and welcome to the first AWS open source newsletter of 2023, edition #140. If you have not already checked it out, I put together a short retrospective summary of 2022 in the post, [AWS open source newsletter - 2022 in review](https://aws-oss.beachgeek.co.uk/2dt). There are some interesting facts and figures in there. I am also taking time to collect feedback from readers to help shape where this newsletter goes in 2023. What do you want me to cover? What should I change?  What is working well for you? Interesting in all your feedback so that I can make sure that you continue to enjoy (I hope) reading this newsletter.

With there being several weeks since the last newsletter, there is no surprise that we have a bumper selection of great new projects for you this week. Kicking things off with "cloudwatch-dashboard-builder" a nice GUI to help you build your CloudWatch dashboards, "sfn-workflow-studio-sync" a great developer productivity tool for those building Step Functions, "renate" a Python library for automatic model re-training, "graph-explorer" a React-based web application to visualise graph data, "aws-mainframe-modernization-carddemo" go retro mainframe with this sample app, "csharp-code-converter-for-postgres" helps you modernise your .NET applications by moving to open source databases, "aws-terraform-dev-container" a must check out project if you use Terraform, and many more projects. If you have a project you want me to feature in this newsletter, please get in touch.

We also feature content covering a very wide selection of your favourite open source technologies, including MySQL, PostgreSQL, Next.js, AWS ParallelCluster, MariaDB, Amazon EKS, Kubernetes, ArgoCD, AWS Distro for OpenTelemetry, Prometheus, DAMON, Crossplane, Apache Spark, Apache Kafka, Apache Flink, Apache Pinot, Apache Superset, Apache NiFi, Delta Lake, OpenShift,  AWS Copilot, RabbitMQ, Apache Airflow, Rust, Terraform, Amazon EMR, and many more.

Finally, check out the Videos and Events section. This week I feature the best of re:Invent and a few other videos that you might have missed that are worth checking out, and we cover events coming up in the next few weeks. A reminder that if you have an open source event you want to us to include, then drop me a line via comments or social media.

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes: Ivica Kolenkaš, Lars Jacobsson, Harinder Seera, Danilo Poccia, Michael Larabel, Paul Vixie, Philipp Sacha, Faizal Khan, Saitkat Banerjee, Mayur Deqaikar, Abbey Fuller, Vikram Sethi, Nima Kaviani, Scott Rigney, Kiran Matty, Sanjay Rao, Abhijit Kshirsagar, Arunkumar Selvam, Gary Stafford, Noritaka Sekiyama, Kyle Duong, and Sandeep Adwankar

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution.*

#### Tools

**cloudwatch-dashboard-builder**

[cloudwatch-dashboard-builder](https://aws-oss.beachgeek.co.uk/2ei) is the latest tool from AWS Community Builder Harinder Seera that provides a graphical user interface (Windows only, but maybe someone out there can build a Linux GUI from the source) that helps you build CloudWatch Dashboards from CloudWatch metrics. Check out the repo from plenty of screenshots and a short video of how this works. Harinder has also thoughtfully put together a three part blog post that dives deep into how to use this tool, so make sure you read [AWS CloudWatch Dashboard Builder - Tool For SRE, Performance Engineers and DevOps](https://aws-oss.beachgeek.co.uk/2ej)

![screenshot of cloudwatch-dashboard builder](https://raw.githubusercontent.com/hseera/cloudwatch-dashboard-builder/main/images/cloudwatch-dashboard.png)

**sfn-workflow-studio-sync**

[sfn-workflow-studio-sync](https://aws-oss.beachgeek.co.uk/2el) is another great tool from AWS Community Builder Lars Jacobsson, that enables real-time sync between StepFunctions Workflow Studio and your local machine. This extension uses the File System Access API to give Chrome temporary access to a single file on your filesystem, so make sure you check your browser compatibility (link in the repo)

![demo of sfn-workflow-studio-sync](https://github.com/ljacobsson/sfn-workflow-studio-sync/blob/main/images/demo.gif?raw=true)

**renate**

[renate](https://aws-oss.beachgeek.co.uk/2eh) is an open-source Python library for automatic model re-training. The library implements continual learning algorithms to train deep neural networks incrementally when new data becomes available. Applications of machine learning require updating models as new batches of data become available. Repeatedly re-training deep neural network models from scratch is costly and fine-tuning them with the new data only will lead to a phenomenon called “catastrophic forgetting”. This means that the model will have good performance on the most recent data, but the performance will degrade on the older data. Renate provides algorithms that alleviate the problem of catastrophic forgetting and helps to automate the re-training process. With Renate, users run small scale continual learning experiments on their local machine or run large continual learning jobs using Amazon SageMaker. Renate also supports state-of-the-art hyper-parameters tuning out-of-the-box, thanks to the integrations with SyneTune.

![example graph of improvements](https://raw.githubusercontent.com/awslabs/Renate/main/doc/_images/improvement_renate.svg)

**graph-explorer**

[graph-explorer](https://aws-oss.beachgeek.co.uk/2eg) The graph-explorer open source tool provides a React-based web application that can be deployed as a Docker image to visualise graph data. You can connect to Amazon Neptune or another graph database that provides an Apache TinkerPop Gremlin or SPARQL 1.1 endpoint. You can search the data quickly using faceted search filters and interactively explore connections around nodes and edges. You can also customise the graph layout, colours, icons, and default properties to display for nodes and edges, and save images for future use.

![demo of graph-explorer screenshot](https://github.com/aws/graph-explorer/blob/main/images/LPGIMDb.png?raw=true)

To get started, build the graph-explorer Docker image and run it on a local machine or on AWS via an EC2 instance or perhaps your favourite container orchestrator.

**csharp-code-converter-for-postgres**

[csharp-code-converter-for-postgres](https://aws-oss.beachgeek.co.uk/2em) is a useful tool for those looking to move to open source databases and provides a Visual Studio extension which helps migrating the Microsoft C# ADO.NET code that is connected to Microsoft SQL Server to PostgreSQL database.

**aws-terraform-dev-container**

[aws-terraform-dev-container](https://aws-oss.beachgeek.co.uk/2en) is a VSCode Dev Container with tools to help you build and manage AWS infrastructure with Terraform. Check out the documentation and sample screenshots, if you are using Terraform then this might be a great way to ensure consistency within your teams.

![screenshot of aws terraform dev container](https://github.com/awslabs/aws-terraform-dev-container/blob/main/doc/images/screenshot-3.gif?raw=true)

### Demos, Samples, Solutions and Workshops

**lambda-rust-and-cdk**

[lambda-rust-and-cdk](https://aws-oss.beachgeek.co.uk/2ek) is a proof of concept project from my colleague Danilo that uses AWS CDK to provision two AWS Lambda functions developed in Rust.


**aws-mainframe-modernization-carddemo**

[aws-mainframe-modernization-carddemo](https://aws-oss.beachgeek.co.uk/209) is a Mainframe application designed and developed to test and showcase AWS and partner technology for mainframe migration and modernisation use-cases such as discovery, migration, modernisation, performance test, augmentation, service enablement, service extraction, test creation, test harness, etc. Check out the supporting blog post, [Introducing Open Source AWS CardDemo for Mainframe Modernization](https://aws-oss.beachgeek.co.uk/2eb) where Sanjay Rao, Abhijit Kshirsagar, and Arunkumar Selvam describe the functions, the technical components and the structure of the CardDemo application before showing how to install the application on a mainframe.

![sample architecture for carddemo mainframe](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2022/12/13/CardDemo-architecture-diagram.png)

### AWS and Community blog posts

**Apache Airflow**

In 2022 I did a number of talks around how to orchestrate hybrid workflows, using a combination of Apache Airflow and AWS services such as AWS ECS Anywhere. I first met Ivica Kolenkaš during PyCon Italia, and he got in touch to say that he has put together this post, [Solving data governance with Airflow and AWS ECS Anywhere](https://aws-oss.beachgeek.co.uk/2ep), which I cannot recommend highly enough. Much like the original idea behind my talk, this dives deep into one aspect of this (Governance/Compliance) and provides a rich, hands on example of how you can use the power of AWS ECS Anywhere and Apache Airflow as the orchestrator to solve this tricky problem. Very nice.

![architecture of airflow and governance blog post](https://miro.medium.com/max/1400/1*RiXDUSl5UHKEiLwJS3xmlA.webp)

**Delta Lake**

Delta Lake is an open-source project that helps implement modern data lake architectures commonly built on Amazon S3 or other cloud storages. In the post, [Introducing native Delta Lake table support with AWS Glue crawlers](https://aws-oss.beachgeek.co.uk/2ee), Noritaka Sekiyama, Kyle Duong, and Sandeep Adwankar collaborate and demonstrates how AWS Glue crawlers work with native Delta Lake tables and describes typical use cases to query native Delta Lake tables. [hands on]

![sample screenshot of delta lake querying](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2022/12/14/BDB-2772-image005.jpg)

**Apache Kafka**

In [Analyze real-time streaming data in Amazon MSK with Amazon Athena](https://aws-oss.beachgeek.co.uk/2ed) Scott Rigney and Kiran Matty look at the recently released Athena connector for Amazon MSK. With it, you can run interactive queries on data held in Kafka topics running in MSK or self-managed Apache Kafka. [hands on]

![example screenshot showing athena source of kafka](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2022/12/15/bdb-2934-image003.jpg)

**MQTT**

MQTT is a lightweight, publish-subscribe, machine to machine network protocol for message queue/message queuing service. In the post, [Use AWS IoT Core MQTT broker with standard MQTT libraries](https://aws-oss.beachgeek.co.uk/2e5) Philipp Sacha shares how you can use standard MQTT libraries for different languages like Python, Node.js, or Java to interact with the AWS IoT Core message broker. [hands on]

**DAMON**

Have you heard about DAMON? I have shared details about this project that originated from Amazon in earlier newsletters ([#114](https://aws-oss.beachgeek.co.uk/2e9)), but what does it do? DAMON is a data access monitoring framework subsystem for the Linux kernel. In the post, [Amazon Reflects On The Great Year For DAMON In The Linux Kernel](https://aws-oss.beachgeek.co.uk/2ea) Michael Larabel provides a quick post for those yearning to know more about this project.

**DNS**

Our own VP of Security Paul Vixie (and DNS contributor/ legend) gave a talk this autumn explaining why open source supply chain security is such a big issue. Check out the post which dives deep into this talk, [Why Bad Bugs in DNS (And Other Open Source Code) Just Won’t Go Away](https://aws-oss.beachgeek.co.uk/2e8)

**Cloud native related posts**

* [Unlock the power of EC2 Graviton with GitLab CI/CD and EKS Runners](https://aws-oss.beachgeek.co.uk/2ef) is a great post on how you can quickly and easily construct multi-architecture container images with GitLab, Amazon EKS, Karpenter, and Amazon EC2, using both x86 and Graviton instance families [hands on]

![architecture of multi architecture pipeline](https://d2908q01vomqb2.cloudfront.net/7719a1c782a1ba91c031a682a0a2f8658209adbf/2022/12/15/devops-2115_2.png)


* [Blue/Green or Canary Amazon EKS clusters migration for stateless ArgoCD workloads](https://aws-oss.beachgeek.co.uk/2e2) demonstrates various strategies for upgrading clusters and provided a solution for automating the migration of stateless workloads from one cluster to another [hands on]

![architecture of blue green solution for deployments using argocd](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2022/12/22/blue-green.png)

* [Adding metrics and traces to your application on Amazon EKS with AWS Distro for OpenTelemetry, AWS X-Ray and Amazon CloudWatch](https://aws-oss.beachgeek.co.uk/2e0) walks you through building a sample application written in Python, the PetAdoptionsHistory micro service, to demonstrate how to add distributed tracing and metrics to your applications using OpenTelemetry Python client SDKs [hands on]

![architecture of sample application](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2022/12/16/cloudops_1066_1.png)

**Open Source database related posts**

* [Upgrade Amazon Aurora PostgreSQL and Amazon RDS for PostgreSQL version 10](https://aws-oss.beachgeek.co.uk/2dy) explains the different options available to you and why you should be planning your PostgreSQL upgrade now
* [Reduce network transfer time with connection compression in Amazon RDS for MySQL and Amazon RDS for MariaDB](https://aws-oss.beachgeek.co.uk/2dz) looks at how connection compression is helpful for certain kinds of workloads where network bandwidth is a constraint and result sets are large [hands on]
* [Generate Excel workbooks from Amazon RDS for PostgreSQL or Amazon Aurora PostgreSQL](https://aws-oss.beachgeek.co.uk/2e1) walks you through a solution that provides a mechanism to generate Excel workbooks from your PostgreSQL databases [hands on]

![architecture of solution to generate excel sheets from postgres db](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2022/12/28/DBBLOG_1962_Solution-Overview-Picture1.png)

* [Read/Write Capability Enhancements in Amazon Aurora with Apache ShardingSphere-Proxy](https://aws-oss.beachgeek.co.uk/2eo) shows you how to use ShardingSphere-Proxy to build database clusters, covering aspects such as sharding, read/write splitting, and dynamic configuration [hands on]

![architecture using apache shardingsphere-proxy](https://d2908q01vomqb2.cloudfront.net/77de68daecd823babbb58edb1c8e14d7106e83bb/2022/12/30/SphereEx-Read-Write-Aurora-1.png)

**Other posts and quick reads**

* [Running Next.js applications with serverless services on AWS](https://aws-oss.beachgeek.co.uk/2du) demonstrates how to build a Next.js application with Serverless services on AWS and explains Next.js Server-Side rendering [hands on]
* [Amazon CloudFront Signed URLs and Cookies are now supported in AWS SDK for Java 2.x](https://aws-oss.beachgeek.co.uk/2dv) provides a hands on guide that covers the basic functionalities of CloudFront signed URLs and signed cookies [hands on]
* [New: AWS CLI v2 Docker images available on Amazon ECR Public](https://aws-oss.beachgeek.co.uk/2dw) looks at the announcement of the official Docker images of the AWS Command Line Interface (AWS CLI) v2 that are now available on Amazon Elastic Container Registry Public (Amazon ECR Public) gallery
* [AWS ParallelCluster 3.3.0 now supports On-Demand Capacity Reservations](https://aws-oss.beachgeek.co.uk/2dx) explains what On-Demand Capacity Reservations (ODCR) are, how they work, and how to configure your HPC cluster to use them [hands on]
* [Amazon EMR Serverless cost estimator](https://aws-oss.beachgeek.co.uk/2e3) shows you how you can use a project shared in [#116](https://aws-oss.beachgeek.co.uk/2e4) to understand how it can help you estimate the cost of running your EMR applications using EMR Serverless [hands on]
* [Decoding USP protobuf data sent by USP agents, using the recent AWS IoT Rules Engine native SQL decode function](https://aws-oss.beachgeek.co.uk/2e6) detailed post on how to set up and use the native AWS IoT Rules Engine protobuf decoding SQL function, in order to decode USP records and messages sent by USP agents [hands on]
* [Building a Serverless Trigger-Based Data Movement Pipeline Using Apache NiFi, DataFlow Functions, and AWS Lambda](https://aws-oss.beachgeek.co.uk/2ec) looks at how you can use Amazon S3 to launch an Apache NiFi flow [hands on]

![apache nifi flow example](https://d2908q01vomqb2.cloudfront.net/77de68daecd823babbb58edb1c8e14d7106e83bb/2022/12/15/Cloudera-Serverless-NiFi-4.png)


### Quick updates

**Apache Airflow**

You can now create Apache Airflow version 2.4 environments on Amazon Managed Workflows for Apache Airflow (MWAA) with Python 3.10 support. Amazon MWAA is a managed orchestration service for Apache Airflow that makes it easier to set up and operate end-to-end data pipelines in the cloud. With Apache Airflow 2.4 on Amazon MWAA, customers can enjoy the same scalability, availability, security, and ease of management that Amazon MWAA offers with the improvements of Apache Airflow 2.4. Further, with Airflow 2.4 MWAA has increased the Python version to 3.10, providing support for newer Python libraries, features, and improvements.

**AWS Copilot**

AWS Copilot (v1.24) now supports Amazon Elastic Container Service (Amazon ECS) Service Connect, a capability that simplifies building and operating resilient distributed applications. Service Connect enables you to have easier network setup and seamless communication between services deployed across multiple Amazon ECS clusters and virtual private clouds (VPCs). Service Connect enables you to add a layer of resilience to your Amazon ECS service communication and get traffic insights with no changes to your application code. 

With the new AWS Copilot release (v1.24), customers can now enable Amazon ECS Service Connect in their service manifest file by specifying network: connect: true. AWS Copilot enables Amazon ECS Service Connect by default for new applications and services, like load balanced web service and backend web service patterns. 

**MySQL**

Amazon Aurora MySQL Version 3 (Compatible with MySQL 8.0) now offers support for Backtrack. Backtrack allows you to move your database to a prior point in time without needing to restore from a backup, and it completes within seconds, even for large databases.

**Redis**

Amazon ElastiCache for Redis now supports updates to encryption in transit on existing cluster resources. You can change the TLS configuration of your Redis clusters without re-building or re-provisioning them or impacting application availability. When enabling encryption in transit, your overall solution can remain connected to Redis clusters.

**RabbitMQ**

Amazon MQ now provides support for RabbitMQ version 3.9.24, which includes several fixes to the previously supported version, RabbitMQ 3.9.20.

**OpenShift**

Red Hat OpenShift Service on AWS (ROSA) now provides an AWS Management Console experience that simplifies the process for satisfying the AWS account prerequisites for provisioning and operating ROSA clusters. The new AWS ROSA console page automatically checks whether ROSA prerequisites are met and provides automated configuration and step-by-step guidance where manual configuration is required. 

Before a cluster administrator can provision ROSA clusters, their AWS account must have ROSA enabled, adequate service quotas, and the Elastic Load Balancing service-linked role. The new AWS ROSA console page automatically checks if these ROSA prerequisites are met, and provides automation and active step-by-step guidance for meeting the requirements. The new AWS ROSA console page helps you provision clusters faster. 

**Linux**

AWS License Manager announces support for cross-region, cross-account tracking of commercial Linux subscriptions you run on AWS. This includes subscriptions purchased as part of EC2 subscription-included AMIs, on the AWS Marketplace, or brought to AWS via Red Hat Cloud Access Program. You can track subscription usage by number of instances for Red Hat Enterprise Linux, SUSE Linux Enterprise Server, and Ubuntu Pro distributions in the Linux subscriptions tab of the AWS License Manager console. 

Once data is discovered and aggregated, you will have insight into all your instances using commercial Linux subscriptions. To view historical usage patterns and set alarms when key thresholds are met for a particular subscription type, you can view the data as Amazon CloudWatch dashboards in the AWS License Manager console and set Amazon CloudWatch alarms from within the AWS License Manager console for monitoring. For data analysis, you can view and export the list of EC2 instances by commercial Linux subscription type (or across all subscriptions types) with instance attributes such as subscription type, AMI id, instance ID, account ID, region, usage operation, and product code.   

**AWS ParallelCluster**

AWS ParallelCluster 3.4 is now generally available and introduces the ability to create HPC clusters that can access and aggregate compute capacity across multiple AWS Availability Zones (AZ) in a Region. Other important features in this release include:

* Amazon VPC configuration for AWS Lambda functions used by ParallelCluster for managing your clusters.
* Custom AWS IAM prefixes for ParallelCluster IAM roles and policies to enable permission boundaries. 
* Secure file-system mounting for Amazon EFS to enable in-transit encryption and IAM authorizations. 
* Ability to set up custom actions for cluster updates. 

**Delta Lake**

You can now query Delta Lake tables seamlessly in Amazon Athena, giving you the benefit of increased operational efficiency, improved query performance and reduced cost. Delta Lake is an open-source table format that helps implement modern data lake architectures commonly built on Amazon S3. Prior to this launch, reading Delta Lake tables in Athena required a complex process of generating and managing additional metadata files. Now you can use Athena to query Delta Lake tables directly without this additional effort.

Athena enables interactive analytics and dashboard reporting for Delta Lake-formatted data lakes and now your Delta Lake table updates are available for analysis in Athena as soon as they are completed. Athena uses metadata contained in Delta Lake files to optimise your queries, so you reduce your data scan costs and get up to 40% performance improvement in your Athena queries. Athena makes it easier for you to create and manage Delta Lake tables in AWS Glue Data Catalog by using simple DDL statements such as CREATE EXTERNAL TABLE and DESCRIBE TABLE, which are consistent with other table types supported in Athena. You can also use AWS Glue Crawler to discover Delta Lake table schemas and manage schema updates in Glue Data Catalog for Delta Lake files, making newly cataloged data available for analysis in Athena seamlessly.

### Videos of the week

**Exploring Popular Open-source Stream Processing Technologies**

Gary Stafford has been busy over the holidays and put together this new video Based on the two-part blog post: "Exploring Popular Open-source Stream Processing Technologies: A brief demonstration of Apache Spark Structured Streaming, Apache Kafka Streams, Apache Flink, and Apache Pinot with Apache Superset".

*Part One*
 
{{< youtube m2IjTPjKbUk >}}


*Part Two*

{{< youtube P46crpse96Q >}}



**AWS IoT and open source**

AWS Community Hero Faizal Khan runs this extended video covering all things open source and AWS IoT. Well worth watching, and covers many of the familiar things such as FreeRTOS, AWS IoT for Greengrass, as well as looking at new things you may not be familiar with. Original link is over at [Open Source and AWS IoT](https://aws-oss.beachgeek.co.uk/2e7) 

{{< vimeo 771917254 >}}

**re:Invent roundup**

It feels like only yesterday, but re:Invent is now but a memory. Luckily, thanks to the fact that many of the sessions were recorded, you can check out some of the best open source related sessions. Here are my top three, but I will feature others in coming editions of the newsletter.

*When security, safety, and urgency all matter: Handling Log4Shell (BOA204)*

On December 9, 2021, there was a report of a potential remote code execution issue in the widely used open-source Apache logging library Log4j. This issue allowed a user to use Java Naming and Directory Interface (JNDI) and LDAP endpoints to execute arbitrary code on a system. Over the next 10 days, 5 additional common vulnerabilities and exposures affecting Log4j were made public. This event as is now referred to as Log4Shell. In this session, Abbey Fuller shares our response to Log4Shell, from initial notification to hot patch, fleet scanning, and customer communications.

{{< youtube pkPkm7W6rGg >}}


*.NET open source on AWS (OPN207)*

.NET is the third most-used programming stack by AWS customers and is used by a dedicated community of over 10 million developers worldwide. Increasingly, the non-enterprise .NET open-source ecosystem has been neglected and often termed “third party,” which has been detrimental to the growth of the community. AWS is trying to change that. Saitkat Banerjee and Mayur Deqaikar share how AWS is making an impact in the .NET open-source community, and discover some of the long-term bets that AWS is investing in today. Walk away equipped with an understanding of the possibilities for .NET open source on AWS.

{{< youtube NWMqBG31NqM >}}


*Secure and multi-tenant infrastructure as code with Crossplane & Argo (OPN309)*

Secure and multi-tenant automation of application and infrastructure rollout on Kubernetes can be complicated, particularly at enterprise scale. Adobe, AWS, and Deutsche Kreditbank collaborated on a solution that has been able to address this challenge by using a combination of GitOps, Crossplane Compositions, open policy agent, and Argo CD. Vikram Sethi and Nima Kaviani talk about the collaborative effort that yielded a solution for a scalable, secure, and multi-tenant infrastructure-as-code deployment strategy working at enterprise scale. Hear about the technical complexities, observations, solutions, lessons learned, and best practices uncovered as part of this effort.

{{< youtube 7In1PquH5tc >}}


**Build on Open Source**

For those unfamiliar with this show, Build on Open Source is where we go over this newsletter and then invite special guests to dive deep into their open source project. Expect plenty of code, demos and hopefully laughs. We have put together a playlist so that you can easily access all (eight) of the episodes of the Build on Open Source show. [Build on Open Source playlist](https://aws-oss.beachgeek.co.uk/24u)

# Events for your diary

If you are planning any events in 2023, either virtual, in person, or hybrid, get in touch as I would love to share details of your event with readers. 

**FOSSDEM**
**Feb 4-5th, 2023 in Brussels**

FOSDEM is a free event for software developers to meet, share ideas and collaborate. Every year, thousands of developers of free and open source software from all over the world gather at the event in Brussels. 4 & 5 February 2023. A must attend event for all open source fans, check out and [register via this link](https://aws-oss.beachgeek.co.uk/2dc).

**State of Open Con 23**
**Feb 7-8th, 2023 in London**

OpenUK will be hosting a 1000 person plus two day conference in Central London, “State of Open Con 23”  in association with IEEE, the headline sponsor. Check out more info and [sign up here](https://aws-oss.beachgeek.co.uk/2dd).

**Everything Open**
**March14-15th Melbourne, Australia**

A new event for the fine folks in Australia. Everything Open is running for the first time, and the organisers (Linux Australia) have decided to run this event to provide a space for a cross-section of the open technologies communities to come together in person. Check out the [event details here](https://aws-oss.beachgeek.co.uk/2ds). The CFP us currently open, so why not take a look and submit something if you can.

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)