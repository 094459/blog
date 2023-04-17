---
title: 'AWS open source newsletter #153'
date: '2023-04-17'
tags : [ oss-newsletter, aws open source, Babelfish for Aurora PostgreSQL, MySQL, Apache Airflow, MWAA, PostgreSQL, gMSA on Linux, Cloud Custodian, Delta Lake, Apache Kafka, Amazon EMR, Streamlit,  Crossplane, Flux, Amazon Corretto, Amazon EKS, Kubernetes]

---
## April 17th, 2023 - Instalment #153

**Welcome**

Hello and welcome to the AWS open source newsletter, #153 as featured in the [latest episode of Build on Open Source (S2E5) ](https://www.twitch.tv/videos/1793286178). We have lots of great projects for you this week, with a strong chatGPT influence. "pg_gpt", "cw-logs-insights-gpt", and "aiws" all integrate chatGPT to help you do different things on AWS, "semantic-search-aws-docs" is a very interesting demo on how to build a more coherent search for your documentation, "aws-chime-chat-demo" a very nice demo using the Chime SDK, "ckia" is an open source AWS Trusted Advisor tool, "AWS_ED" helps you keep your local IP in sync with external DNS records, "cfnctl" provides a Terraform like cli experience to CloudFormation, and more!

We also have content on some of your favourite open source projects, which this week include Babelfish for Aurora PostgreSQL, MySQL, Apache Airflow, PostgreSQL, gMSA on Linux, Cloud Custodian, Delta Lake, Apache Kafka, Amazon EMR, Streamlit,  Crossplane, Flux, Amazon Corretto, and Kubernetes. Make sure you check out the Video and Events section, some great videos this week as always.

**Feedback**

Please please please take 1 minute to [complete this short survey](https://pulse.buildon.aws/survey/PJRTOUMK) and bask in the warmth of having helped improve how we support open source.

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes: Nithya Ruff , Nick Karpov, Chandrapal Badshah, Walter McCain II, Kyaw Soe Hlaing, Sai Kiran Akula, Samiullah Mohammed, Masudur Rahaman Sayem, Akeef Khan, Bret Edwards, Roger Welin, Brittan DeYoung, Roberson Andrade, Damon Cortesi,  Arthur Petitpierre, Andreas Cavagna, Join Sheetal Joshi and Sai Vennam

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution.*

#### Tools

**cfnctl**

[cfnctl](https://aws-oss.beachgeek.co.uk/2ox)  [[ pronounced cfn control or cloudformation control ]] is a great tool from Roger Welin that provides a CLI that brings the Terraform cli experience to Cloudformation. With cfnctl, you write Cloudformation templates as usual but use the cli workflow that you are already used to from Terraform, including: apply, plan, destroy, and output. Still work in progress, so why not give this a try and provide Roger feedback, or even better contribute back to the project. Very neat indeed!

{{< youtube -ZpbvEoC9rc >}}

**ckia**

[ckia](https://aws-oss.beachgeek.co.uk/2oy) is a new tool from Brittan DeYoung that provides an open source alternative to AWS Trusted Advisor, that is intended to run opinionated checks against your cloud environment and provide recommendations. The full suite of AWS trusted advisor checks is the inspiration for this project. The current focus for the project is providing check parity with the current AWS Trusted Advisor offerings, but the README does state that this is early days for the project. It is worth [reading the Reddit thread](https://aws-oss.beachgeek.co.uk/2ph) where Brittan discusses why he created this tool and how it compares to others that provide similar capabilities. 

**AWS_ED**

[AWS_ED](https://aws-oss.beachgeek.co.uk/2oz) is a new project from Bret Edwards that I seemed to have missed when it was first published (sorry Bret!)  is intended to allow you to leverage your own Domain name to keep track of your public IP address. If you are a residential customer or you are a small/medium business that does not have a static IP at your office and you want to be able to access resources remotely, this is something you may want to leverage. It uses AWS's Route53 platform to update your personal IP address dynamically. This tool will track your IP address locally and if it detects a change in your IP, it will make a call to route53 using boto and update your resource record (your "A" name record) for your domain. This currently assumes that you are using a subdomain instead of using the Apex record. 

**pg_gpt**

[pg_gpt](https://aws-oss.beachgeek.co.uk/2p0) is an experimental extension from the lovely folks at Cloudquery that brings OpenAI API to your PostgreSQL to run queries in human language. Check out the details and the short demo they have put together. You will need to have an OPENAI API key to use this, and as the README states, do not use this for production as the plugin does send the schema info to OpenAI.

{{< youtube HQVgVDYDa5k >}}

**aiws**

[aiws](https://aws-oss.beachgeek.co.uk/2p1) is another project that has been inspired by ChatGPT, this time Hüseyin BABAL has put together this tool that provides an AI driven AWS CLI to help you to generate and use AWS commands to manage your resources in AWS. You will need to have an OPENAI API key to use this.

![demo of aiws](https://user-images.githubusercontent.com/1237982/228968604-953dd131-ba9d-47dd-a8d0-19bf59e37664.gif)

**cw-logs-insights-gpt**

[cw-logs-insights-gpt](https://aws-oss.beachgeek.co.uk/2p2) is the final project this week that looks to integrate chatGPT, this time it is AWS Community Builder Lars Jacobsson who has put together this Chrome extension that generates CloudWatch Logs Insights queries from ChatGPT prompts. As with the other projects that feature chatGPT, you need to bring your OpenAI key to use this. I have to say that I think this is a very useful tool, as I always end up having to google these so this is going to save me a lot of time/effort. Lars is our special guest in the next episode of Build on Open Source, so make sure you put that on your calendar as he will be talking about some of his open source projects.

![demo of cw-logs-insights-gpt](https://github.com/ljacobsson/cw-logs-insights-gpt/blob/main/images/demo.gif?raw=true)

**transformers-neuronx**

[transformers-neuronx](https://aws-oss.beachgeek.co.uk/2p3) is an open-source library built by the AWS Neuron team that helps run transformer decoder inference workflows using the AWS Neuron SDK. Currently, it has examples for the GPT2, GPT-J, and OPT model types. Find out more how you can use this project to optimise how you run those models using AWS silicon innovations such as AWS Inferentia and AWS Trainium by reading the post, [Deploy large language models on AWS Inferentia2 using large model inference containers](https://aws-oss.beachgeek.co.uk/2pi).

![overview of where transformers-neuronx sits in the stack](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2023/04/11/inf2_DJL.png)

### Demos, Samples, Solutions and Workshops

**semantic-search-aws-docs**

[semantic-search-aws-docs](https://aws-oss.beachgeek.co.uk/2p6) this is a very promising sample project that demonstrates how to set up AWS infrastructure to perform semantic search and question answering on documents using a transformer machine learning models like BERT, RoBERTa, or GPT (via the Haystack open source framework). What do you think of these kinds of tools to help you find what you are looking for in your documentation? I would love to know as I am putting together some thoughts in this area.

![demo of semantic search of aws docs](https://raw.githubusercontent.com/aws-samples/semantic-search-aws-docs/main/appdemo.gif)

**aws-chime-chat-demo**

[aws-chime-chat-demo](https://aws-oss.beachgeek.co.uk/2p4) is a side-project that  Roberson Andrade has been working on that provides an example of how to build a chat for real-time messaging using AWS Chime Messaging service.  From his [Reddit post](https://aws-oss.beachgeek.co.uk/2pj):

>The goal of this project is to use it as a reference for a future developer-friendly guide on how to use this Amazon service. I believe it would be of great use since there are not many projects created for this purpose for Chime Messaging.
>
>The main point of the project is to create a demo of a real application that uses AWS Chime Messaging service to work with real-time messaging, using the AWS infrastructure itself. For this, a simple React frontend was developed using the Chakra UI component library to accelerate development. For message rendering, the React Virtuoso library was used to generate a virtualized list and enable infinite scrolling, loading messages as the user scrolls.
>
> To enable communication between the frontend and Chime, temporary AWS credentials need to be generated. For this, the authentication service offered by Cognito and the generation of credentials through the Cognito Identity Pool were used. Finally, to perform the action of creating a user in Chime Messaging, a trigger was configured that invokes a lambda when a Cognito account is confirmed. To create this entire infrastructure, Terraform was used as an IaC (Infrastructure as code) platform to facilitate the creation, modification, and destruction of all infrastructure created in AWS. To exemplify the application flow, I created a diagram that shows the entire user creation flow and communication between AWS services, as well as a video that shows the application in action,.

{{< youtube FP7BrV9W8s8 >}}

**emr-cli-examples**

[emr-cli-examples](https://aws-oss.beachgeek.co.uk/2p5) is a repo from colleague Damon Cortesi that provide examples on how to use another project [amazon-emr-cli](https://aws-oss.beachgeek.co.uk/2ly) that he put together and we shared in [#148](https://dev.to/aws/aws-open-source-newsletter-148-5h2b). These examples show how EMR CLI can be used to easily deploy a variety of different jobs to EMR Serverless and EMR on EC2. So dive in and explore the varied ways that you can deploy PySpark code to EMR and how the EMR CLI can make it all as easy as a single command.

*Bonus*

When I put demos together, I am often having to work with files that contain data. Those files are very often CSV formatted, and have always looked out for a good primer on how to optimise working with this kind of source data. Well, I need look no longer as Damon has put together this very cool tutorial, [Intro to Data Processing on AWS](https://aws-oss.beachgeek.co.uk/2pg) that shows what happens when you read both raw (TSV) and optimised (Apache Parquet) data from S3 using Apache Spark. [hands on]

![ illustration for intro to data processing post](https://notebooks.dacort.dev/notebooks/intro_data_processing_aws/image_008.png)

### AWS and Community blog posts

**Delta Lake**

Nick Karpov has put together this post, [Introducing Support for Delta Lake Tables in AWS Lambda](https://aws-oss.beachgeek.co.uk/2pe) that shares news about how the AWS SDK for pandas (what was formally AWS Data Wrangler) and how it now supports the deltalake package for read and write access to Delta Lake tables. The post provides a nice walk through to get you started and show you how you can build your own Lambda layer with deltalake. [hands on]

**Cloud Custodian**

Cloud Custodian is an open source project that enables you to manage your cloud resources by filtering, tagging, and then applying actions to them. Chandrapal Badshah has put together a blog post, [My Love/Hate Relationship with Cloud Custodian](https://aws-oss.beachgeek.co.uk/2pd) where he shares his experiences in working with this open source tool over the past year. If you are thinking about using this project, or maybe a seasoned user, take a look and see what you think.

**gMSA on Linux**

group Managed Service Account (gMSA) is an open sourced credentials-fetcher daemon, that allows Linux users (initial support on Amazon Linux 2023, Fedora Linux 36, and Red Hat Enterprise Linux 9) to integrate with Microsoft Active Directory and use Microsoft AD group Managed Service Accounts capability. In this post, [AWS Now Supports Credentials-fetcher for gMSA on Amazon Linux 2023 ](https://aws-oss.beachgeek.co.uk/2p8) Walter McCain II, Kyaw Soe Hlaing, Sai Kiran Akula, and Samiullah Mohammed share more details on the use cases they see, and provide an example of   using an Active Directory domain joined Linux server with gMSA. Warning, may contain Windows! [hands on]

![example use cases for gMSA on Linux overview](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2023/04/10/gMSA-use-case-scenarios.png)

**Apache Kafka**

In this post, [Connect to Amazon MSK Serverless from your on-premises network](https://aws-oss.beachgeek.co.uk/2pc), Masudur Rahaman Sayem and Akeef Khan speak to my inner Hybrid geek and explore the option of on-premises connectivity with MSK Serverless and how by establishing this integration, you can gain access to a wide range of real-time analytics use case possibilities and unlock the full potential of your data, whether it is in AWS or within your existing on-premises infrastructure. Nice! [hands on]

![overview of hybrid kafka infrastructure](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2023/04/03/img20-1024x396.png)

**Other posts and quick reads**

* [Amazon EMR on EKS widens the performance gap: Run Apache Spark workloads 5.37 times faster and at 4.3 times lower cost](https://aws-oss.beachgeek.co.uk/2pk) describes the benchmark setup and results of running Amazon EMR on the EKS environment
* [Push Amazon EMR step logs from Amazon EC2 instances to Amazon CloudWatch logs](https://aws-oss.beachgeek.co.uk/2pb) shares how you can entralise the EMR step logs of the jobs in CloudWatch [hands on]
* [Build Streamlit apps in Amazon SageMaker Studio](https://aws-oss.beachgeek.co.uk/2p9) provides a hands on example of hosting a Streamlit demo for an object detection task using Amazon Rekognition on SageMaker Studio [hands on]

![overview of architecture of streamlit apps on sagemaker](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2023/03/16/Streamlit-Demo-Blog-Streamlit-App-Revised.jpg)

* [Part 2: Multi-Cluster GitOps — Cluster fleet provisioning and bootstrapping](https://aws-oss.beachgeek.co.uk/2pa) is a follow up post that shows you how to use a decentralised, hub-and-spoke model to manage the lifecycle of Amazon EKS clusters using Crossplane and Flux [hands on]

![gitops multicluster architecuture with flux and crossplane](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2023/04/07/Bootstrapping-Flux.png)

### Quick updates

**Kubernetes**

The Amazon Elastic Kubernetes Service (Amazon EKS) team announced support for Kubernetes version 1.26 for Amazon EKS and Amazon EKS Distro. Just in time for KubeCon next week, you can dive deeper by reading the post, [Amazon EKS now supports Kubernetes version 1.26](https://aws-oss.beachgeek.co.uk/2pl), where Leah Tucker looks at some of the key features you need to know about.

{{< youtube nK9iC_U2fVA >}}

**Apache Airflow**

You can now create Apache Airflow version 2.5 environments on Amazon Managed Workflows for Apache Airflow (MWAA). Apache Airflow 2.5 is the latest minor release of the popular open-source tool that helps customers author, schedule, and monitor workflows. With Apache Airflow version 2.5 on Amazon MWAA, customers can enjoy the same scalability, availability, security, and ease of management that Amazon MWAA offers with the improvements of Apache Airflow 2.5, such as annotations for DAG runs and task instances, auto-refresh for task log view, and a better dataset user-interface. Apache Airflow version 2.5 on Amazon MWAA includes Python version 3.10 and comes pre-installed with recently released Amazon Provider Package version 7.1.0, enabling access to new AWS integrations, such as Amazon SageMaker Pipelines, Amazon SageMaker Model Registry, and Amazon EMR Notebooks.

**PostgreSQL**

A few updates this week for PostgreSQL users.

Amazon Relational Database Service (Amazon RDS) for PostgreSQL now supports Amazon RDS Optimized Reads for up to two times faster query processing compared to previous generation instances. Complex queries that utilise temporary tables, such as queries involving sorts, hash aggregations, high-load joins, and Common Table Expressions (CTEs) can now execute up to two times faster with Optimized Reads on RDS for PostgreSQL. Optimized Read-enabled instances achieve faster query processing by placing temporary tables generated by PostgreSQL on the local NVMe-based SSD block-level storage, thereby reducing your traffic to Elastic Block Storage (EBS) over the network. Refer to our recent blog post to learn more about performance improvements using local disk based database instances for workloads that have highly concurrent read/write processing. Amazon RDS Optimized Reads is available by default on RDS for PostgreSQL versions 15.2 and higher, 14.7 and higher, and 13.10 and higher. This feature is now available on Intel-based M5d and R5d instances with up to 3,600 GiB of NVMe-based-SSD block-level storage and AWS Graviton2-based M6gd and R6gd database (DB) instances with up to 3,800 GiB of NVMe-based SSD block-level storage and up to 25 Gbps of network bandwidth. You can configure these disk based DB instances as Multi-AZ DB cluster, Multi-AZ DB instances, and Single-AZ DB instances. 

If you want to dive deeper, make sure you read the blog post from Naga Appani, [Introducing Optimized Reads for Amazon RDS for PostgreSQL](https://aws-oss.beachgeek.co.uk/2p7).

Amazon Aurora PostgreSQL-Compatible Edition now supports PostgreSQL major version 15 (15.2). New features in PostgreSQL 15 include the SQL standard "MERGE" command for conditional SQL queries, performance improvements for both in-memory and disk-based sorting, and support for two-phase commit and row/column filtering for logical replication.

Following the open source community announcement of updates to the PostgreSQL database, we updated Amazon Aurora PostgreSQL-Compatible Edition to support PostgreSQL 14.7, 13.10, 12.14, and 11.19. These releases contain bug fixes and improvements by the PostgreSQL community. Refer to the Aurora version policy to help you decide how often and how to plan your upgrade. As a reminder, if you are running any version of Amazon Aurora PostgreSQL 11, you must upgrade to a newer major version by January 31, 2024. This release contains optimisations that improve database availability during patching or minor version upgrades. The optimisations will be used when applying patches or newer minor version upgrades to Aurora PostgreSQL versions 11.18 or higher, 12.13 or higher, 13.9 or higher, or 14.6 or higher. This release also contains logical replication performance improvements and new features for Babelfish for Aurora PostgreSQL version 3.1.

**MySQL**

A couple of important updates from last week.

Amazon Relational Database Service (Amazon RDS) for MySQL now supports inbound replication from Amazon RDS Single-AZ database (DB) instances and Amazon RDS Multi-AZ DB instances with one standby to Amazon RDS Multi-AZ deployments with two readable standby database (DB) instances. You can use this inbound replication to help migrate your existing Amazon RDS MySQL deployments within minutes to Amazon RDS Multi-AZ deployments with two readable standby db instances, which has one writer instance and two readable standby instances across three availability zones. By creating a Multi-AZ deployment with two readable standby db instances as a read replica of your existing RDS MySQL database instance, you can promote the read replica to be your new primary, typically within minutes.  Amazon RDS Multi-AZ deployments provide enhanced availability and durability, making them a natural fit for production database workloads. Deployment of Amazon RDS Multi-AZ with two readable standby database instances supports up to 2x faster transaction commit latencies than a Multi-AZ deployment with one standby instance. In this configuration, automated failovers typically take under 35 seconds. In addition, the two readable standbys can also serve read traffic without needing to attach additional read replicas. 

Amazon RDS for MySQL now supports up to 15 asynchronous read replicas from Amazon RDS Multi-AZ deployments with two readable standbys delivering up to 8x the previous read capacity. Amazon RDS Multi-AZ deployments with two readable standbys have one writer instance and two readable standby instances across three availability zones. You can now create 15 additional asynchronous read replicas outside the cluster in addition to the two reader instances thereby scaling up your read capacity to 17 instances. Amazon RDS Read Replicas provide enhanced performance and durability for RDS database (DB) instances. For read heavy database workloads, the additional read replicas provide the option to elastically scale out beyond the capacity constraints of the two readable instances inside the Multi-AZ deployment with two readable standbys. You can create one or more read replicas and serve high-volume application read traffic from multiple copies of your data, thereby increasing aggregate read throughput. Read replicas can also be promoted and modified to be a Multi-AZ deployment option with two readable standbys when needed.

**Amazon EMR**

Last week we announced support for Apache Spark with Java 11 in EMR on EKS. Amazon EMR on EKS enables customers to run open-source big data frameworks such as Apache Spark on Amazon EKS. AWS customers can now leverage Java 11 as a supported Java runtime to run Spark workloads on Amazon EMR on EKS. Until now, Amazon EMR on EKS ran Spark with Java 8 as the default Java runtime. In order to run Spark with Java 11, customers will need to create a custom image and install the Java 11 runtime to replace the default Java 8. This required additional engineering effort when the customer first started to use Amazon EMR on EKS and when the customer upgraded to a new release version. With this new feature, Amazon EMR on EKS supports launching Spark with Java 11 runtime by simply passing in a new release label. 


### Videos of the week

**Hands on with EKS Networking (2023) | Amazon EKS Workshop**

Join Sheetal Joshi and Sai Vennam as they dive into a hands-on demo focusing on the Networking module in the [all-new Amazon EKS Workshop: [https://www.eksworkshop.com/](https://aws-oss.beachgeek.co.uk/2pf)]

{{< youtube EAZnXII9NTY >}}


**Java on Graviton - How to Use Amazon Corretto**

Java is one of the most popular languages when running applications on AWS. Did you know about Amazon Corretto, a no-cost, multi-platform, production-ready distribution of the Open Java Development Kit? Did you know that the kit runs on Graviton-based Amazon EC2 instances? During this session, Arthur Petitpierre shares more info about Amazon Corretto,  and how to install it on Graviton-based Amazon EC2 instances.

{{< youtube zANOBN4jZfI >}}


**Nithya Ruff from Amazon on Building Successful Open Source Businesses**

Nithya Ruff heads up Amazon's Open Source Program Office, and in this video podcast, she talks about various aspects of open source with hosts Avi Press and Matt Yonkovit. They cover a broad range of topics, including the challenges facing open source today, how to evaluate new open source projects, the importance of Open Source Program Offices (OSPOs) for startups, building successful and sustainable open source businesses, reducing friction for developers, open source diversity, managing diverse talent and competing ideals in open source governance, and more!

{{< youtube SswwJyzU7po >}}


**Build on Open Source**

If you missed the fifth episode which we streamed live last Friday, special guest and AWS Community Builder Andreas Cavagna came on the show to talk about Leapp, a tool that anyone who develops on AWS needs to know about. Andreas shares his passions on automation and open source and how they combined to create this project.  [Catch the replay here](https://www.twitch.tv/videos/1793286178)
For those unfamiliar with this show, Build on Open Source is where we go over this newsletter and then invite special guests to dive deep into their open source project. Expect plenty of code, demos and hopefully laughs. We have put together a playlist so that you can easily access all (eight) of the episodes of the Build on Open Source show. [Build on Open Source playlist](https://aws-oss.beachgeek.co.uk/24u)

# Events for your diary

If you are planning any events in 2023, either virtual, in person, or hybrid, get in touch as I would love to share details of your event with readers. 

**AWS at KubeCon + CloudNativeCon Europe 2023**
**April 18th live on twitch.tv/aws**

AWS Container Day ft. Kubernetes at KubeCon + CloudNativeCon Europe 2023 is a day-long virtual event dedicated to helping Kubernetes practitioners optimise their workloads and reduce their Ops burden. AWS and guest speakers will dive deep into the latest trends, techniques, and best practices for deploying, managing, securing, and scaling with Kubernetes. The day will feature new solution demos and interactive challenges designed to provide hands-on experience and practical insights. Attendees will walk away with new tools, mental models, and resources to innovate, optimise, and scale their applications.

Check out the amazing schedule that has been published on the event page, [AWS at KubeCon + CloudNativeCon Europe 2023](https://aws-oss.beachgeek.co.uk/2na) and register to set yourself a reminder.

**AWS Community Nordics**
**April, 20th Helsinki**

The AWS Community Day Nordics is a free full day event for AWS users to come together to network, learn from each other and get inspired. The event is organised by the community - for the community. The cfp is currently open, so if you are in the area and want to talk then here is your chance. Check out the full event details and save your space here, [AWS Community Nordics registration page](https://aws-oss.beachgeek.co.uk/2l5)

**Reducing the costs of your openCypher applications**
**May 8th, 4pm UK - online**

openCypher is an open-source project for creating graph applications. Neptune supports openCypher graph query language, and in this webinar you will learn more about the cost benefits for moving openCypher workloads to Neptune serverless. With Neptune serverless, customers can see up to 90% cost savings compared to provisioning for peak capacity. A demo of Neptune in action will be included in this session.

Head over to the You Tube holding page, [Reducing the costs of your openCypher applications](https://aws-oss.beachgeek.co.uk/2mp) 

**Cortex**
**Every other Thursday, next one 16th February**

The Cortex community call happens every two weeks on Thursday, alternating at 1200 UTC and 1700 UTC. You can check out the GitHub project for more details, go to the [Community Meetings](https://aws-oss.beachgeek.co.uk/2h5) section. The community calls keep a rolling doc of previous meetings, so you can catch up on the previous discussions. Check the [Cortex Community Meetings Notes](https://aws-oss.beachgeek.co.uk/2h6) for more info.

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)

### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)
