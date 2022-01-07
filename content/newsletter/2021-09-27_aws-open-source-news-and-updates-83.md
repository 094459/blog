---
title: 'AWS open source news and updates #83'
date: '2021-09-27'
tags : [ oss-newsletter ]
---
## September 27th, 2021 - Instalment #83

Newsletter #83.

Welcome to issue #83 of this newsletter, and more great new open source projects to check out. For infrastructure as code practitioners we have several projects for both CDK and Terrafrom, a CI/CD project to help you scale GitHub Actions runners, a simple hosting project with some nice features you can use as a baseline for your own project, a reference architecture for data analytics on AWS with some comprehensive CDK stacks you can inspect and borrow for your own, a project to help you visualise some of your key cloud metrics and more.

On top of that we have new posts covering Apache Airflow, Open Telemetry, Cortex, Kubernetes, Suricata, Spring Boot, moto, GraphQL and more. This weeks videos cover AWS SAM and Open Telemetry, and to finish off we have the events sections with events happening later this week.



**Zappa**

Zappa makes it super easy to build and deploy serverless, event-driven Python applications. One of my first attempts in building serverless applications many moons ago was via this project, and the great tutorials and documentation that supported it.

Last week, [this tweet](https://aws-oss.beachgeek.co.uk/y5) announced that the maintainers are [deprecating this project](https://aws-oss.beachgeek.co.uk/y6). Take a look and see if this is something you want to take on. 

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Kenneth Winner, Jimmy Dahlqvist, Gokul Chandra, Michael Hausenblas, QP Hou, Björn Wilmsmann, Philip Riecks, Tom Hombergs, Adam Palmer, Jesper Eneberg, Talia Nassi, Ilan Gofman, Krzysztof Lis, Wojciech Matuszewski, Danilo Poccia, Jonas Birmé, Ian Mckay, Oscar Nord, Eddy Lin, Yin Song, Josiah Davis, Eden Duthie, Chen Wu, Nisha Notani, Timur Tulyaganov, and Yuriy Prykhodko.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest open source projects

**permissions.cloud**

[permissions.cloud](https://aws-oss.beachgeek.co.uk/xw) is an open source project from AWS Hero Ian Mckay that provides a handy IAM reference guide which I used this week when I was putting together my blog post (see below). You can view this online by heading over to [https://permissions.cloud/](https://aws-oss.beachgeek.co.uk/xx)

![demo](https://github.com/iann0036/permissions.cloud/blob/main/assets/img/screen1.png?raw=true)

**self-hosted-runners-on-aws**

[self-hosted-runners-on-aws](https://aws-oss.beachgeek.co.uk/y8) check out this project from Jimmy Dahlqvist, that helps you setup and run GitHub Actions CI/CD runners on AWS in an auto scaled way. Reacts on GitHub webhooks to trigger auto scaling of EC2 spot instances.

![arch](https://github.com/JimmyDqv/self-hosted-runners-on-aws/blob/master/images/architecture.png?raw=true)

**cdk-lambdaless-apigw-websockets**

[cdk-lambdaless-apigw-websockets](https://aws-oss.beachgeek.co.uk/xv) an interesting "experimental" project from Wojciech Matuszewski that explores how to build a websocket API without resorting to writing Lambda functions.

![arch](https://github.com/WojciechMatuszewski/cdk-lambdaless-apigw-websockets/blob/main/img/architecture.jpeg?raw=true)

**cdk-appsync-transformer**

[cdk-appsync-transformer](https://aws-oss.beachgeek.co.uk/ye) Kenneth Winner has put together this CDK construct following on from a blog post he wrote on using the AWS Cloud Development Kit with AppSync. Kenneth has written this transformer in order to emulate AWS Amplify's method of using GraphQL directives in order to template a lot of the Schema Definition Language.

**authenticated-static-site**

[authenticated-static-site](https://aws-oss.beachgeek.co.uk/yc) I love these kinds of projects, this one is an example CDK project that shows how you can set up an authenticated static site. Using Amazon Cognito for authentication and Amazon S3 for hosting your site, it integrates a simple pipeline to push out your site content stored in GitHub, via AWS CodePipeline. I can see this being useful for a number of my demo projects, might just have to convert these CDK stacks into Python...

**aws-cudos-framework-deployment**

[aws-cudos-framework-deployment](https://aws-oss.beachgeek.co.uk/yg)

The Cloud Intelligence Dashboards are a collection of Amazon QuickSight dashboards, and include The Cost Intelligence Dashboard, CUDOS Dashboard, Trusted Advisor Organization (TAO) Dashboard, and Trends Dashboard. This repository has everything you need to get you up and running to set those up. To help provide more background, check out the blog post [Visualize and gain insights into your AWS cost and usage with Cloud Intelligence Dashboards and CUDOS using Amazon QuickSight](https://aws-oss.beachgeek.co.uk/yh) from Nisha Notani, Timur Tulyaganov, and Yuriy Prykhodko.

![demo](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2021/09/09/CUDOS_under_the_hood.png)

**amazon-sagemaker-tsp-deep-rl**

[amazon-sagemaker-tsp-deep-rl](https://aws-oss.beachgeek.co.uk/y9) The Travelling Salesperson Problem (TSP) is summarised as ""Given a list of cities and the distances between each pair of cities, what is the shortest possible route that visits each city exactly once and returns to the origin city?" and this project provides code that demonstrates how to train, deploy, and make inferences using deep reinforcement learning to solve the Travelling Salesperson Problem. To walk you through it, Yin Song, Josiah Davis, Eden Duthie, and Chen Wu have come together to write, [Solving the Traveling Salesperson Problem with deep reinforcement learning on Amazon SageMaker](https://aws-oss.beachgeek.co.uk/ya)

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/09/13/song_traveling-salesperson_f1-learning_tsp_decoder.png)

**aws-analytics-reference-architecture**

[aws-analytics-reference-architecture](https://aws-oss.beachgeek.co.uk/y3) if you are looking to put together a data analytics solution, you should check out this reference architecture first. It combines a number of current good practices for design, the implementation and operation of an analytics platform. The documentation ([AWS Analytics Reference Architecture](https://aws-samples.github.io/aws-analytics-reference-architecture/)) is great, providing an easy way to navigate and understand the different components. Code contains CDK reference examples, which you can borrow in your own projects as well. 

![arch](https://aws-samples.github.io/aws-analytics-reference-architecture/resources/global-design.png)

**amazon-gamelift-plugin-unity**
 
[amazon-gamelift-plugin-unity](https://aws-oss.beachgeek.co.uk/xu) this project is a plugin for Unity that contains libraries and native UI that makes it easier to access GameLift resources and integrate GameLift into your Unity game. You can use the GameLift Unity Plugin to access GameLift APIs and deploy AWS CloudFormation templates for common gaming scenarios.

**terraform-aws-appconfig**

[terraform-aws-appconfig](https://aws-oss.beachgeek.co.uk/y1) a new Terraform module from clowd.haus which creates AWS AppConfig resources within your Terraform code.

**amazon-ecs-fullstack-app-terraform**

[amazon-ecs-fullstack-app-terraform](https://aws-oss.beachgeek.co.uk/y2) this repository contains Terraform code to deploy a complete demo application, including the infrastructure as well as a CI/CD pipeline that you can use as a baseline for your own projects.

![arch](https://github.com/aws-samples/amazon-ecs-fullstack-app-terraform/blob/main/Documentation_assets/Infrastructure_architecture.png?raw=true)

**Gist of the week**

This very handy snippet, [ingest-aws.js](https://aws-oss.beachgeek.co.uk/y0), from [Jonas Birmé](https://aws-oss.beachgeek.co.uk/xz) allows to create an event to watch for a video being uploaded to an Amazon S3 bucket, and this kicking off a transcode event. It uses the open source [ingest-application-framework](https://aws-oss.beachgeek.co.uk/xy) which was new to me, and provides a ready to go framework for building video on demand ingest applications.

![arch](https://eyevinn.github.io/ingest-application-framework/eyevinn-iaf.png)

### AWS and Community blog posts

**Apache Airflow**

A couple of posts this week.

First up, a post I somehow missed last year which is worth checking out, is this post from QP Hou, [Breaking up the Airflow DAG monorepo](https://aws-oss.beachgeek.co.uk/xp) where he explores how to bring multi-repo DAG development using a new open sourced project called objinsync](https://aws-oss.beachgeek.co.uk/xq), that is a stateless DAG sync daemon, which is deployed as a sidecar container. [hands on]

![arch](https://tech.scribd.com/post-images/2020-03-airflow/dag-release-pipeline.png)

Following that, a new blog post/tutorial from myself, [Integrating Amazon Timestream in you Amazon Managed Workflows for Apache Airflow v2.x](https://aws-oss.beachgeek.co.uk/xo), where I show you how you can orchestrate Amazon Timestream data using  Apache Airflow to help you with a number of different use cases. [hands on]

**Athena SQLite**

Damon Cortesi has put together this post a few months back, [Athena SQLite](https://aws-oss.beachgeek.co.uk/xs) that shows you how to query SQLite databases in S3 using Athena’s Federated Query functionality. It is implemented within the Serverless Application Repository (SAR) and you can check out the details of [how to deploy it here](https://aws-oss.beachgeek.co.uk/xt).

**Cortex**

Cortex is a distributed system that allows for a horizontally scalable, highly available, and long-term storage solution for Prometheus metrics. In this post, [Building a series deletion API in Cortex](https://aws-oss.beachgeek.co.uk/xn) from Ilan Gofman, he shares his experience of designing and implementing the series deletion feature inside of the Cortex open source project.

![design](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/09/13/alolitas_gofman_series-deletion-api-cortex_f1.png)

**OpenTelemetry**

More OpenTelemtry goodness this week, starting off with this post from Danilo Poccia, who wrote last week of the general availability of tracing in AWS Distro for OpenTelemetry in, [New for AWS Distro for OpenTelemetry – Tracing Support is Now Generally Available](https://aws-oss.beachgeek.co.uk/xr)

![demo](https://d2908q01vomqb2.cloudfront.net/da4b9237bacccdf19c0760cab7aec4a8359010b0/2021/09/13/aws-otel-annotations-1024x586.png)

Following that we have Eddy Lin, who discusses his experience building the Go MultiMod tool, an open source solution that automates most of the tedious work of releasing new versions with Golang. Read more in his post, [Simplifying OpenTelemetry Collector and Go library releases with the Go MultiMod tool](https://aws-oss.beachgeek.co.uk/yb)

**Spring Boot**

[Using PostgreSQL with Spring Boot on AWS — Part 1](https://aws-oss.beachgeek.co.uk/xg) and [Using PostgreSQL with Spring Boot on AWS — Part 2](https://aws-oss.beachgeek.co.uk/xh) is a follow up post from Björn Wilmsmann, Philip Riecks, and Tom Hombergs, authors of the book Stratospheric: From Zero to Production with Spring Boot and AWS. The original post was very well received, so they are back with more, this time exploring how you can use PostgreSQL from a Spring Boot web application. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/09/16/sueiras_wilmsmann-using-postgresql-amazon-rds_f1_small.png)

**Suricata**

If you ever wondered the origins of the name of the open source IDS/IPS Suricata, then you need to read this post (it kind of made sense after I knew, but still amazed me). Adam Palmer and Jesper Eneberg show you how to create an open-source IDS/IPS service running in Docker containers, using Amazon Elastic Container Service (ECS) and Amazon Linux 2 (AL2) in the post, [Building an Open Source IDS IPS service for Gateway Load Balancer](https://aws-oss.beachgeek.co.uk/xi) [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/5b384ce32d8cdef02bc3a139d4cac0a22bb029e8/2021/09/06/suricata-docker-Base.png)

**moto**

[moto](https://aws-oss.beachgeek.co.uk/xk) is an open source library that allows you to easily mock out tests based on AWS infrastructure. In the post [Getting started with testing serverless applications](https://aws-oss.beachgeek.co.uk/xj), Talia Nassi shows you how you can use this as part of your testing approach when building serverless applications. [hands on]

**GraphQL**

A series of two posts covering migration from a monolithic REST API and monolithic frontend to a modern federated GraphQL system. In [Building federated GraphQL on AWS Lambda](https://aws-oss.beachgeek.co.uk/xl) Krzysztof Lis from IMDb shares their experience and what they learned, including how open source tools helped with the learning curve as they migrated. Following that, in [Managing federated schema with AWS Lambda and Amazon S3](https://aws-oss.beachgeek.co.uk/xm) he looks at one of the biggest challenges they faced, GraphQL schema management.

![arch](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2021/09/16/graphql3.png.jpg)

**Kubernetes**

[Amazon EKS Anywhere & EKS Connector](https://aws-oss.beachgeek.co.uk/yf) Gokul Chandra provides a very comprehensive walk through of Amazon EKS Anywhere and EKS Connector, showing you how you can put these together as part of your hybrid cloud architecture. This post will require your focus, so grab your preferred hot beverage before reading.

**Eyevinn Ingest Application Framework**

Eyevinn Ingest Application Framework (IAF) allows you to build plugins in a modular way that can interact with different storage or transcoding solutions. Oscar Nord dives deeper into this in his post, [Building plugins for the Eyevinn Ingest Application Framework](https://aws-oss.beachgeek.co.uk/y7). He looks at two of the IAF plugins developed to easily transcode and make on demand video content (VOD) available on multiple devices using AWS Elemental MediaConvert and AWS Elemental MediaPackage. You can see in the projects section above for more details.

### Videos of the week

**AWS SAM**

Mehmet Nuri Deveci and Eric Johnson bring you the latest Serverless Office Hours, this week featuring AWS Serverless Application Model (SAM) and demonstrate how SAM Accelerate helps developers build serverless applications quickly. We demo how SAM Accelerate will help developers test in the cloud by speeding up the deployment process and bringing all logging to a central location.

{% youtube syHwvb_P4JM %}

**OpenTelemetry and FluentBit**

Michael Hausenblas discusses good practices and current developments around CNCF open source projects and specifications including OpenTelemetry and FluentBit. This has been on the events section for a few weeks, so am hoping some of view will have seen this already, if not, check out his presentation. [Embracing Observability in Distributed Systems](https://aws-oss.beachgeek.co.uk/yd).

**Distributed load testing**

This is something to keep an eye out for, a new series from Open Source-AWS on You Tube, taking a look and walking through open source projects on AWS. The first one is taking a look at distributed load testing using AWS Fargate.

{% youtube LXKavTaeo4E %}

### Quick updates

**Amazon EMR**

EMR Studio is an integrated development environment (IDE) that makes it easy for data scientists and data engineers to develop, visualise, and debug big data and analytics applications written in R, Python, Scala, and PySpark. You can now use (Version EMR 6.4.0 and later), Python, Scala, SparkSQL, and R within the same Jupyter notebook in EMR Studio, providing flexibility to use different programming languages for Spark workloads. Previously, you could only write code in one language within the same notebook for Spark workloads. With this feature enhancement to Jupyter notebooks, you can now switch between Python, Scala, SparkSQL, and R within the same Jupyter notebook and share data between cells via temporary tables. You can also use this feature from EMR Notebooks or from Jupyter notebooks talking to Jupyter Enterprise Gateway (JEG) on EMR 6.4.0 and later.


### Events for your diary

Coming up later this week we have...

**Secure Coding Virtual Summit**
**September 29, 2021**

The Secure Coding Virtual Summit is your source for everything you need to build secure code from the ground up. There are many interesting session, but check out the sessions covering how to secure and protect yourself when using open source.

Full details, including speaker line up and [how to register, here](https://aws-oss.beachgeek.co.uk/xb).

**GraphQL API security best practices with AWS AppSync and AWS Amplify**
**14th October, 11am AEST**

As a developer, the most important parts of managing your applications should always include enhancing performance while strengthening security. In this webinar, we take you through security best practices for your GraphQL API’s with AWS AppSync and AWS Amplify, providing you with an understanding of how these can be applied to your applications. In this session, you will learn about:

* GraphQL Protocol and how to configure a schema
* Possible ways to authenticate and authorise access to GraphQL APIs
* How to configure network security for your API
* How to enable observability for your API with logging, tracing or auditing

To [register for this event, use this link](https://aws-oss.beachgeek.co.uk/ue).


**Amazon SageMaker and Open-Source Tools for ML: Better Together**
**October 7 | 11 AM PT | 2 PM ET**

Many organisations rely on open-source tools to support the Machine Learning lifecycle. Amazon SageMaker has been rapidly evolving by introducing support and compatibility for various open-source frameworks. In this session, you will learn how to build a customisable ML Infrastructure based on Amazon SageMaker and open-source components. We will discuss pros and cons, the limitations of different tools that support specific stages of the ML workflow, and best practices for MLOps, to automate these stages into repeatable pipelines.

To read more and [register for this event, click here](https://aws-oss.beachgeek.co.uk/wz).


**Flink Forwards Global 2021**
**October 26th/27th**

Flink Forward Global 2021 is a 2-day virtual conference for the Apache Flink and stream processing communities. Apache Flink is an open-source distributed engine for processing data streams that can support both streaming and batch workloads. Flink Forward has keynote presentations and talks on production Flink use cases, technical deep dive sessions, and the growth of the Flink ecosystem. You can meet core Flink committers, new and experienced users, and thought leaders who share experiences and best practices in stream processing, real-time analytics, and the management of mission-critical Flink deployments in production.

[Read more and sign up here.](https://aws-oss.beachgeek.co.uk/wh)


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)