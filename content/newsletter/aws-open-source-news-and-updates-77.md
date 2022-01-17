---
title: 'AWS open source news and updates #77'
date: '2021-07-26'
tags : [ oss-newsletter ]
---
## 26th July, 2021 - Instalment #77

Newsletter #77.

This week we have more new open source projects including schema-manager, maildog, ddbcereal, ecr-scan-reporter and more. This weeks AWS and community blog posts cover topics such as PartiQL, ConsoleMe, Yor, Kubernetes, Debezium, Apache Kafka, Apache Spark, Redis, HPC and more. Also, don't miss the great video on getting up and running with Amazon EMR on Apache Airflow.

**Observability (o11y) newsletter**

If you had not already signed up for this, then perhaps now is a great time. Colleague Michael Hausenblas has been curating this essential weekly list of everything you need to know about Observability in the o11y newsletter. You can subscribe via https://o11y.news/ and you can check out last weeks edition [here](https://aws-oss.beachgeek.co.uk/r1)

This really is a great way to stay on top of all things Observability.

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Damon Cortesi, Justin Turner Arthur, Dominic Nightingale, John Preston, Edmund Hung, Taylor Smith, Jones Zachariah Noel, Bhuvanesh R, Viktor Pankov, Ian Lim, Seungjune Kim, Ben Smith, José Lorenzo Cuéncar, Nina Vogl, Matthew Miller, Brendan Bouffler, Sukhpreet Kaur Bedi, Elizabeth Nguyen, Melody Yang, Shiva Achari, Avnish Jain, Justin Garrison, Jesse Butler, Matt Auerbach, Abhinav Krishna Vadlapatla, Pablo Redondo Sanchez and Johannes Kupser.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

These are the latest projects from the last week or so that popped up on my radar. Check them out.

**schema-manager**

[schema-manager](https://aws-oss.beachgeek.co.uk/rr) this is a new open source tool from the AWS Proserve team, that enables developers to develop and test their schemas without the burden of deploying a schema just to find out that the schema is incomplete. Schema Manager is a tool that fills the gap between a schema's development process and the running environment where a schema registry (SR) is deployed. Detailed guidance on how to set up and configure is provided too. 

**maildog**

[maildog](https://aws-oss.beachgeek.co.uk/rq) this open source project from Edmund Hung allows you to hosting your own email forwarding service on AWS and manage it with Github Actions. The project comes with detailed installation and setup instructions, some things to be aware of when it comes to your usage as well as guidance on how much this might cost you based on the size/volume of emails. 

**ddbcereal**

[ddbcereal](https://aws-oss.beachgeek.co.uk/rp) this open source project from Justin Turner Arthur provides a high performance Python library for serialising and deserialising DynamoDB attribute values. Serializers and deserializers created with ddbcereal work with the input and output of AWS SDKs like botocore, aiobotocore, and the low-level client interfaces of boto3 and aioboto3. Docs and examples to get you started.

**ecr-scan-reporter**

[ecr-scan-reporter](https://aws-oss.beachgeek.co.uk/ro) John Preston follows up last weeks project with another one which this time provides a serverless application to monitor ECR Repositories and capture scan results. John has also put together this blog post, [Automated ECR Scans & Reports with ecr-scan-reporter](https://aws-oss.beachgeek.co.uk/rs) that provides background on why he created this project and how to get started.

![arch](https://github.com/compose-x/ecr-scan-reporter/blob/main/EcrScanReporterWorkflow.jpg?raw=true)

**ucsd_robo_car_aws_deepracer**

[ucsd_robo_car_aws_deepracer](https://aws-oss.beachgeek.co.uk/rn) this is a great open source project from Dominic Nightingale for those of you with AWS DeepRacers. It is a simple ROS2 package using OpenCV on aws deepracer rc car with ackerman steering that can follow a line or stay between two lines. Detailed docs and examples provided mean you should have no excuses for getting this up and running.

![demo](https://user-content.gitlab-static.net/fcfbfbbd7eb27bcf5f99c50ce769aa44657fa8fa/68747470733a2f2f6a2e676966732e636f6d2f516b6e674d5a2e676966)

**aws-groundstation-cli-contact-control**

[aws-groundstation-cli-contact-control](https://aws-oss.beachgeek.co.uk/r2) this project provides an interactive CLI utility for scheduling AWS Ground Station satellite contacts. Viktor Pankov put together this blog post, [Scheduling satellite contact using AWS Ground Station and Python SDK](https://aws-oss.beachgeek.co.uk/r3) to show you how you can use it, and how it makes it easier to schedule AWS Ground Station satellite contacts directly from your terminal.

**amazon-ivs-chime-messaging-ugc-demo**

[amazon-ivs-chime-messaging-ugc-demo](https://aws-oss.beachgeek.co.uk/r5) this open sourced demo project is designed to show you how you can build a live streaming platform with chatting feature. To help you navigate this project, you can check out the blog post, [Build a live streaming chat application using Amazon IVS and Amazon Chime SDK](https://aws-oss.beachgeek.co.uk/r6), where Ian Lim and Seungjune Kim show you the steps to build an application that uses live streaming and chat using a number of AWS capabilities.

![demo](https://d2908q01vomqb2.cloudfront.net/98fbc42faedc02492397cb5962ea3a3ffc0a9243/2021/07/19/ivs-ugc-blog-gif.gif)

### Community open source posts

**Yor**

Yor is an open-source tool that helps add informative and consistent tags across infrastructure-as-code frameworks such as Terraform, CloudFormation, and Serverless. In this post, [Best Practices for AWS Tagging With Yor](https://aws-oss.beachgeek.co.uk/rm) Taylor Smith shows you how you can use it to apply some best practices to your AWS environments. This is a must read post this week, great stuff.

**PartiQL**

PartiQL is an open source project that provides a SQL-compatible query language that makes it easy to efficiently query data, regardless of where or in what format it is stored. In this post, [DynamoDB with PartiQL](https://aws-oss.beachgeek.co.uk/rk) Jones Zachariah Noel shows you how you can use this with AWS DynamoDB, and how this can make it easier for developers to with a SQL background to get started with DynamoDB.

**Debezium**

[Debezium](https://aws-oss.beachgeek.co.uk/rj) is an open source distributed platform for change data capture. In this post, [Integrate Debezium with AWS Secret Manager For Retrieving Passwords](https://aws-oss.beachgeek.co.uk/ri) AWS Community Builder Bhuvanesh R shares how you can integrate this project with AWS Secret manager for storing and rotating passwords. This is important given the nature of the tool and how it manages connection strings to your systems. [hands on]

**ConsoleMe**

ConsoleMe is an open source web service from Netfix that makes AWS IAM permissions and credential management easier for end-users and cloud administrators, providing numerous ways to log in to the AWS Console. This post, [Improving database security at FollowAnalytics with AWS IAM database authentication and ConsoleMe](https://aws-oss.beachgeek.co.uk/rt) from Hugo Henley shares how he has used ConsoleMe to provide secure access to his databases.

![arch](https://miro.medium.com/max/700/0*ZkZF6K-FPynfTESs)

### AWS and Amazon open source posts

**Kubernetes**

A couple of posts this week worth diving deep into.

First up we have [Catching up with Managed Node Groups in Amazon EKS](https://aws-oss.beachgeek.co.uk/rd) from Jesse Butler who brings you up to speed with the updates from Managed Node Groups in Amazon EKS, including feature updates, AMI changes and version support and a look ahead to what is coming soon.

Following that we have Justin Garrison with [Amazon EKS now supports Kubernetes 1.21](https://aws-oss.beachgeek.co.uk/re), everything you need to know about the latest version supported. The post covers highlights and new features worth knowing about, feature deprecations, some upgrade consideration and end of life reminders.

**AWS Copilot**

AWS Copilot CLI is a tool for developers to build, release and operate production ready containerized applications on AWS App Runner, Amazon ECS, and AWS Fargate. In this post, [Fast forward on your first serverless container deployment on AWS](https://aws-oss.beachgeek.co.uk/rh), Johannes Kupser shows you how you can use it to deploy your first containerised application on AWS. He shows you how it makes it easy not just to initially deploy the application, but to redeploy once you have made changes.

**AWS Amplify**

Matt Auerbach shared last week this post, [MLH Fellows Spring 2021](https://aws-oss.beachgeek.co.uk/rf), that brings us up to speed with the latest cohort of students that are part of the Major League Hacking (MLH) Fellowship, and their work as part of the Amplify cli. The post covers introductions to the four Amplify Fellows, a description of their projects and what they learned. 

![project](https://d2908q01vomqb2.cloudfront.net/0a57cb53ba59c46fc4b692527a38a87c78d84028/2021/07/17/github-issues-kanban.png)

**Apache Spark**

Apache Spark is an open-source, distributed data processing framework capable of performing analytics on large-scale datasets, enabling businesses to derive insights from all of their data whether it is structured, semi-structured, or unstructured in nature. However, for organisations accustomed to SQL-based data management systems and tools, adapting to the modern data practice with Apache Spark may not come as quickly as they would like.

In this post, [Build a SQL-based ETL pipeline with Apache Spark on Amazon EKS](https://aws-oss.beachgeek.co.uk/rb), from Melody Yang, Shiva Achari, and Avnish Jain, show you how you can use another open source data processing framework, [Arc](https://aws-oss.beachgeek.co.uk/rc), to address this challenge. Arc is an opinionated framework for defining predictable, repeatable and manageable data transformation pipelines and takes a SQL first approach. This enables you to combine the best of both worlds, abstracting the Apache Spark and container technologies, so you can build a modern data solution on AWS managed services simply and efficiently. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2021/06/23/image1-arch-diag.png)

**Apache Flink**

Apache Flink is an open-source framework and engine for processing data streams. In this post, [Secure multi-tenant data ingestion pipelines with Amazon Kinesis Data Streams and Kinesis Data Analytics for Apache Flink](https://aws-oss.beachgeek.co.uk/rg) Abhinav Krishna Vadlapatla and Pablo Redondo Sanchez show you how you can use Apache Flink to continuously process messages in near-real time and store them in Amazon S3. [hands on]

**Redis and Memcached**

Elizabeth Nguyen provides news about some new training videos that you can use to learn about how to set up, run, and scale in-memory data stores in the cloud with Redis or Memcached via Amazon ElastiCache. The training materials will walk you through key use cases, Redis and Memcached data structures, caching patterns, and more. 

If this sounds like something you want to dive deeper into, go ahead and check out the post, [Get started with Amazon ElastiCache for Redis and Memcached: Introducing the ElastiCache learning path](https://aws-oss.beachgeek.co.uk/ra)

**PostgreSQL**

Sukhpreet Kaur Bedi wrote this post last week, [Schedule jobs with pg_cron on your Amazon RDS for PostgreSQL or Amazon Aurora for PostgreSQL databases](https://aws-oss.beachgeek.co.uk/r9) that provides you some reasons why you might want to use pg_gron, and then how you can use pg_cron to automate some maintenance tasks on your RDS for PostgreSQL or Aurora PostgreSQL workloads. [hands on]

**AWS ParallelCluster**

José Lorenzo Cuéncar and Nina Vogl show you how to bring up an HPC cluster, prepare, install, and run applications and visualise the results, all without needing a single piece of hardware in the blog post, [How to put a supercomputer in the hands of every scientist](https://aws-oss.beachgeek.co.uk/r7)

![arch](https://d2908q01vomqb2.cloudfront.net/9e6a55b6b4563e652a23be9d623ca5055c356940/2021/07/19/figure-13-temperature-volume.png) 

*Bonus*

Also, check out this [Tweet thread](https://twitter.com/boofla/status/1418133166469042178) from Brendan Bouffler that provides some additional info on how AWS ParallelCluster was able to support a global Hackathon. Some great nuggets in there.

**AWS Serverless Application Model (SAM)**

AWS Serverless Application Model (SAM) is an open-source framework for building serverless applications. In this post, [Introducing AWS SAM Pipelines: Automatically generate deployment pipelines for serverless applications](https://aws-oss.beachgeek.co.uk/r4), Ben Smith shares news of the public preview of AWS SAM Pipelines, a new capability of AWS Serverless Application Model (AWS SAM) CLI. AWS SAM Pipelines makes it easier to create secure continuous integration and deployment (CI/CD) pipelines for your organisations preferred continuous integration and continuous deployment (CI/CD) system. This post covers how you can do that with GitLab CI/CD, but others are supported (GitHub Actions, Jenkins and AWS CodePipeline) [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2021/07/21/Screenshot-2021-07-19-at-12.54.55.png)

### Videos

**Apache Airflow**

Damon Cortesi put this video together last week showing you how you to use Amazon EMR on EC2 and EKS with Amazon Managed Workflows for Apache Airflow.

{% youtube Z--sNHqkM7c %}

### Quick updates

**AWS SDK for Java**

We have released the AWS SDK for Java 2.17, which removes the SDK’s external dependency on the popular third-party JSON library, Jackson. This means that AWS SDK for Java 2.x no longer requires an external copy of Jackson-databind, Jackson-core, or Jackson-dataformat-cbor in order to function. This release does not change any of the public AWS SDK APIs.

Read more in the blog post from Matthew Miller, [The AWS SDK for Java 2.17 removes its external dependency on Jackson](https://aws-oss.beachgeek.co.uk/r8)

### Events for your diary

**Open Data Lakes with Presto, Apache Hudi & AWS Glue and S3 – the next generation of analytics**
**July 27th at 10am PT/ 1pm ET**

Sign up for this roundtable discussion where experts from each layer in this stack – Presto, AWS, and Apache Hudi – will discuss why they are seeing a pronounced adoption to this next generation of cloud data lake analytics and how these technologies enable open, flexible, and highly performant analytics in the cloud.

Read more [and register here](https://aws-oss.beachgeek.co.uk/q7)


**Cloud Native Day**
**23rd September, Bern Switzerland**

What is this, an in person event returning? A stellar line up including our own Michael Hausenblas, an event looking at CNCF projects and the future of IT. Find out more and to view prices/register, by clicking [here](https://cloudnativeday.ch/en/#speakers).


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen