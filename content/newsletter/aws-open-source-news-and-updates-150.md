---
title: 'AWS open source newsletter #150'
date: '2023-03-27'
tags : [ oss-newsletter, aws open source,  Apache Hudi, Apache Iceberg, Kubernetes, FFMpeg, Apache Airflow, Protobuf, MySQL, MariaDB, Amazon Corretto, Delta Lake]

---

## March 27th, 2023 - Instalment #150

**Welcome**

Hello and welcome to a milestone edition of the AWS open source newsletter, #150. Over two hundred thousand words later, thousands of contributors, hundreds of new open source projects, I hope this newsletter brings as much joy for readers as it does for me to put this together. Thank you all for your amazing support so far. What do we have in store for you this week? Yup, more great new projects and content. This week we have projects such "ZeusCloud" an open source solution for risk management, "balcony" a nice tool for cli wizards, "emr-trino-autoscale" for those of you running Trino, "amazon-kinesis-data-analytics-blueprints" a nice selection of ready made patterns for Apache Flink, and more! Also featured are some of your favourite open source projects, including Apache Hudi, Apache Iceberg, Kubernetes, FFMpeg, Apache Airflow, Protobuf, MySQL, MariaDB, Amazon Corretto, Delta Lake, and more.

Before diving into the newsletter, take a moment to read this post from Lukonde Mwila and Chris Short for those of you running Kubernetes workloads.

**ACTION: Read this if you use Kubernetes**

I have shared this before, but now my colleagues Lukonde Mwila and Chris Short have put together this post, [Changes to the Kubernetes Container Image Registry](https://aws-oss.beachgeek.co.uk/2mw) to raise awareness of some critical changes to the Kubernetes image registries that are happening very soon and that you need to review and action. The post provides some tips on what you need to do, so do yourself a favour and make sure you read this before skipping on.

**Feedback**

Please please please take 1 minute to [complete this short survey](https://pulse.buildon.aws/survey/PJRTOUMK) and get some exclusive content as a thank you.

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes: Franck Pachot,  Guillaume Marchand, Daisy Riley, Oğuzhan Yılmaz, Veena Vasudevan, Soumil Shah, Sashi Varanasi, Lakshmi Peri, Noritaka Sekiyama, Scott Long, Sean Ma, Surendar Munimohan, Chelluru V N S S Vidyadhar, José Gardiazabal and Donato Azevedo  

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution.*

#### Tools

**ZeusCloud**

[ZeusCloud](https://aws-oss.beachgeek.co.uk/2n1) is a new (to me at least) tool to help you discover, prioritise, and remediate your risks in the cloud. What does it do? Well according to the README, it: builds an asset inventory of your AWS accounts, continuously monitors your environments for misconfigurations and attack paths, lets you customise security and compliance controls to fit your needs, provides contextual information to help you prioritise and remediate security findings, and helps you to meet compliance standards such as PCI DSS, CIS, and more!

![demo screenshot of zeus cloud](https://user-images.githubusercontent.com/20483346/217993491-69bbb84b-ce5f-4432-9aac-8a362c01c1bd.gif)

**balcony**

[balcony](https://aws-oss.beachgeek.co.uk/2n2) is an open source Python based CLI tool from Oğuzhan Yılmaz for cli wizards and fans, that simplifies the process of enumerating AWS resources. Use it to effortlessly automate the managed of the AWS resources in your account. I installed it and was up and running in minutes, using the excellent documentation to get me going. The README has plenty of examples of how you can use this tool, as well as a super nice documentation site complete with sample recipes.

![demo of balcony running](https://oguzhan-yilmaz.github.io/balcony/visuals/reading-a-resource-node.gif)

**cronrange.info**

[cronrange.info](https://aws-oss.beachgeek.co.uk/2n0) this project is not AWS specific, but I love what Ivica Kolenkaš has put together here - the essential guide to undersanding cron patterns. Run your cron settings through his script, and it will helpfully output samples to make sure it is what you expect. The docs contain plenty of examples, but great for testing out before you put your crontab together.

**visualize-iam-access-analyzer-policy-validation-findings**

[visualize-iam-access-analyzer-policy-validation-findings](https://aws-oss.beachgeek.co.uk/2ii) provides code that helps you build a useful dashboard in Quicksight  to visualise the policy validation findings from AWS Identity and Access Management (IAM) Access Analyzer. The repo shares a supporting blog post to help you get started deploying this project.

![architecture of iam access analyzer visualisation](https://github.com/aws-samples/visualize-iam-access-analyzer-policy-validation-findings/blob/main/multi-account-deployment/architecture-diagram-multi-account-setup.png?raw=true)

**emr-trino-autoscale**

[emr-trino-autoscale](https://aws-oss.beachgeek.co.uk/2n6) This project provides a custom auto-autoscaling for Amazon EMR on EC2 clusters running with Trino. The utility can be installed on external EC2 instances or on the Amazon EMR master of the cluster you want to control. The package support out of the box Instance Groups and Instance Fleets clusters with On Demand / SPOT instances. Check out the doc for features this project provides, such as scaling based on cluster CPU utilisation, metrics collection using Trino JMX REST API, scaling hints using Trino required_workers SESSION parameter, and more!

**aws-glue-connector-google-spreadsheet**

[aws-glue-connector-google-spreadsheet](https://aws-oss.beachgeek.co.uk/2n7) This repository provides a tutorial on how to use AWS Glue for Python Shell to access your Data in Google Spreadsheet and import it to your Amazon S3 bucket.

![architecture of glue to google spreadsheet connector](https://github.com/aws-samples/aws-glue-connector-google-spreadsheet/blob/main/res/images/Architecture.png?raw=true)

### Demos, Samples, Solutions and Workshops

**amazon-kinesis-data-analytics-blueprints**

[amazon-kinesis-data-analytics-blueprints](https://aws-oss.beachgeek.co.uk/2n5) are a curated collection of Apache Flink applications. Each blueprint will walk you through how to solve a practical problem related to stream processing using Apache Flink. These blueprints can be leveraged to create more complex applications to solve your business challenges in Apache Flink.

**aws-cdk-localgov-drupal-fargate-efs-auroraserverlessv2**

[aws-cdk-localgov-drupal-fargate-efs-auroraserverlessv2](https://aws-oss.beachgeek.co.uk/2n8) provides a nice way to automate the deployment of Drupal using AWS CDK.  The stack will deploy the infrastructure needed as well as deploying Drupal using Amazon ECS and Fargate.

![overview of drupal on aws architecture](https://github.com/aws-samples/aws-cdk-localgov-drupal-fargate-efs-auroraserverlessv2/blob/main/docs/drupal-localgov.png?raw=true)

**sqs-fargate-eventbridge-pipe**

[sqs-fargate-eventbridge-pipe](https://aws-oss.beachgeek.co.uk/2n3) provides a sample for how to invoke a Fargate Task from SQS using Eventbridge Pipes. To make it super simple, rhlarora84 has packaged this up as a CDK app. Once setup, you can kick off your ECS Task as simple as sending an SQS message.

![overview of architecture for sqs fargate](https://github.com/rhlarora84/sqs-fargate-eventbridge-pipe/blob/main/image.png?raw=true)

### AWS and Community blog posts

**Kubernetes**

I have featured previous Kubernetes posts from Franck Pachot, and this time he is back with another instalment of his Kubernetes on AWS series. In this post, he dives deep into a powerful but less known feature of the Linux Kernel: Pressure Stall Information (PSI) and how you can use this to understand capacity and resource patterns in your workloads. [hands on]

**Apache Airflow**

I put pen to digital paper this week and wrote about a very cool open source project called Data on EKS (or DoEKS) which provides reference patterns for the installation of many common open source data tools. In this short post, [Self managed Apache Airflow with Data on EKS](https://aws-oss.beachgeek.co.uk/2mu), I share my experiences of getting this up and running (including the messy bits when it goes horribly wrong!). [hands on]

**FFmpeg**

FFmpeg is an open source and widely used utility for handling video. I have used it myself many times to create [time lapse videos](https://www.youtube.com/watch?v=DVliJjTHb3E) capturing frames from my Raspberry Pi. In the post, [Create a Managed FFmpeg Workflow for Your Media Jobs Using AWS Batch](https://aws-oss.beachgeek.co.uk/2mt), Guillaume Marchand and Daisy Riley show you how to integrate FFmpeg with AWS Services to build a more easily managed FFmpeg. They have created an open source solution to deploy FFmpeg packaged in a container and managed by AWS Batch, which you can then execute an FFmpeg command as a job through a REST API. Very nice! [hands on]

![overview of ffmpeg solution delivered as an api](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2023/03/20/FFmpeg-AWSBatch-architecture.png)

**Other posts and quick reads**

* [Optimize costs by moving your self-managed open source software (OSS) Redis workloads to Amazon ElastiCache](https://aws-oss.beachgeek.co.uk/2my) looks at why you should consider moving your self-managed open source software (OSS) Redis workloads to managed Amazon ElastiCache for Redis

![overview of managed vs unmanaged open source](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2023/03/20/DBBLOG-3029_img1-272x300.png)

* [How to build smart applications using Protocol Buffers with AWS IoT Core](https://aws-oss.beachgeek.co.uk/2ms) shares how you how working with Protobuf on AWS IoT Core is as simple as writing a SQL statement [hands on]
* [Improve query performance using Optimized Reads on Amazon RDS for MySQL and Amazon RDS for MariaDB](https://aws-oss.beachgeek.co.uk/2mv) dives deep into how MySQL and MariaDB engines process complex queries and how the Optimized Reads feature can improve the performance of complex queries [hands on]

![graph of performance improvement using optimise reads on mysql and mariadb](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2023/03/15/DBBLOG-2731-img3-1024x329.png)

* [Introducing native support for Apache Hudi, Delta Lake, and Apache Iceberg on AWS Glue for Apache Spark, Part 2: AWS Glue Studio Visual Editor ](https://aws-oss.beachgeek.co.uk/2mx) shows you how to process Apache Hudi datasets using the AWS Glue Studio visual editor

![screen shot of apache hudi in aws glue studio editor](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2023/03/03/BDB2812-p2-data-target.jpg)

* [Interact with Apache Iceberg tables using Amazon Athena and cross account fine-grained permissions using AWS Lake Formation](https://aws-oss.beachgeek.co.uk/2n4) is a hands on, deep dive look at fine-grained access control policies in Amazon Athena queries for data stored in Apache Iceberg  table format [hands on]

### Quick updates

**Amazon Corretto 20**

You can now download Corretto 20 from the[ Amazon Corretto downloads page](https://aws-oss.beachgeek.co.uk/2mz). This latest version supports the most recent OpenJDK feature release and is available on Linux, Windows, and macOS.

Highlights of OpenJDK 20 include a second preview of Record Patterns, which are used to more easily work with record-based objects. You can use record patterns and type patterns together to create more powerful data navigation. Virtual threads are also in their second preview. Virtual Threads will make it easier to write multi-threaded applications. OpenJDK 20 also introduces a new incubation feature for scoped values, which allows you to share data between threads. OpenJDK 20 includes a second preview of the Foreign Function & Memory API, which makes it easier to integrate with native code. There are updates to the Pattern Matching for switch statements preview feature and the incubating Vector API. Structured Concurrency, which makes tasks distributed over multiple threads appear as a single unit of work, is now in its second incubation release.

**PostgreSQL**

Amazon Relational Database Service (RDS) Proxy is a fully managed and highly available database proxy for Aurora and RDS databases. RDS Proxy helps improve application scalability, resiliency, and security. RDS Proxy now supports PostgreSQL major version 15. PostgreSQL 15 includes new features such as the SQL standard "MERGE" command for conditional SQL queries, performance improvements for both in-memory and disk-based sorting, support for two-phase commit, and row/column filtering for logical replication. The PostgreSQL 15 release also adds support for server-side compression with Gzip, LZ4, or Zstandard (zstd) using pg_basebackup. For more details about this release, refer to the PostgreSQL community announcement. You can also enforce SCRAM (Salted Challenge Response Authentication Mechanism) password-based authentication for your proxy. 

**.NET on AWS**

I shared recently how AWS is supporting the growing number of open source projects from the .NET community. In [this tweet](https://aws-oss.beachgeek.co.uk/2mr) we share the latest project, Nuke. Make sure you check out [the full list here](https://aws-oss.beachgeek.co.uk/2lo)

### Videos of the week

**Dive deep of Apache Iceberg on AWS**

In this video, Veena Vasudevan looks at some of the common challenges of using traditional file formats on premises and how leveraging Apache Iceberg on AWS helps you overcome these challenges. You will also learn about the comprehensive and advanced features of Apache Iceberg with elaborate demos that showcase the unique capabilities of Apache Iceberg on AWS.

{{< youtube Eqgs67sOOow >}}
{% youtube Eqgs67sOOow %}

**Apache Hudi**

I discovered a new series of short videos from Soumil Shah that looks at how you can leverage Apache Hudi on AWS to build an open source data lake. There are lots of topics covered, and this is perfect for the technical viewer.

Check out the [full playlist here](https://aws-oss.beachgeek.co.uk/2mq) and will leave you with the opening session.

{{< youtube 5zF4jc_3rFs >}}
{% youtube 5zF4jc_3rFs %}

**Build on Open Source**

For those unfamiliar with this show, Build on Open Source is where we go over this newsletter and then invite special guests to dive deep into their open source project. Expect plenty of code, demos and hopefully laughs. We have put together a playlist so that you can easily access all (eight) of the episodes of the Build on Open Source show. [Build on Open Source playlist](https://aws-oss.beachgeek.co.uk/24u)

# Events for your diary

If you are planning any events in 2023, either virtual, in person, or hybrid, get in touch as I would love to share details of your event with readers. 

**Build on Open Source**
**March 31st, twitch.tv/aws**

The fourth episode of Build on Open Source features special guests Devansh Bawari and Saurav Pathak from Bagisto, a leading open source e-commerce technology.  See you there on [twitch.tv/aws](https://twitch.tv/aws), Friday 31st March at 9am GMT, 10am CET.

**FOSSASIA**
**April 13th-15th, Singapore**

FOSSASIA Summit 2023 returns as an in-person and online event, taking place from Thursday 13th April to Saturday 15th April at the Lifelong Learning Institute in Singapore. 

If you are interested in attending in person, or virtually, find out more about the event at the [FOSSASIA Summit 2023 page](https://aws-oss.beachgeek.co.uk/2iq).

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