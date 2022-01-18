---
title: 'AWS open source news and updates #65'
date: '2021-04-26'
tags : [ oss-newsletter ]
---
## April, 26th, 2021 - Instalment #65

Newsletter #65. 

This week we have new projects covering security, AWS CDK, serverless and a very handy tool if you find yourself having to record your screen to do demos and wondering how to make sure you do not disclose sensitive information such as your AWS credentials. We have AWS and community blog posts covering Kubernetes, AWS Copilot, Rust, GraphQL, Apache Airflow, Linux, we have a couple of workshops on AWS Greengrass v2 and Observability on AWS and much more.

I have one small ask this week. I would love to know if these weekly updates are useful, so please let me know via this very simple survey that will take you around 30 seconds to complete.

[Complete Survey](https://eventbox.dev/survey/TVWJXPA)

**CDK Day**

Later this week we have the second CDK Day, and over 3K people have so far sign up for this community organised event. There is still time to register, and this post from Ignacio Riesgo, will show you what you can expect during [CDK Day 2021](https://aws.amazon.com/blogs/opensource/what-to-expect-at-cdk-day-2021/) - check out the full speaker sessions, there is just so much great content it is going to be even better than the first CDK Day!

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: 

Meir Gabay, Brice Pellé, Imaya Kumar Jagannathan, Rodrigue Koffi, Rafael Pereyra, Joseph Keating, Matt Hedges, Carlos Santos, Matthew Ostovarpour, Dave Currie, Christopher Christou, Richard Elberger, Eric Johnson, Ignacio Riesgo, Ian Mckay, Dino Bektaš, Pahud Hsieh, James Pether Sörling, Gourav Das, Arseny Zinchenko, Justin Garrison, Dylan Anthony, Florian Clanet, Danny Steenman, Laimonas Sutkus and Dr Tony Hoang.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.


### Latest from open source projects

**censor-shell**

[censor-shell](https://aws-oss.beachgeek.co.uk/fb) AWS Hero Ian Mckay is back with another open source tool that I know I will be using. This handy little tool allows you to hide phrases (such as passwords or AWS credentials) that you do not want to display on the screen when you are recording/sharing your screen whilst doing demos.

![demo](https://github.com/iann0036/iann0036/raw/master/static/censor-shell.gif?raw=true)

**sonar-cloudformation-plugin**

[sonar-cloudformation-plugin](https://aws-oss.beachgeek.co.uk/ff) this came in from James Pether Sörling, and this project provides a Sonarqube cloudformation plugin that supports cfn-nag and checkov and  helps you to secure your development pipeline with static application security test (SAST) / Dynamic application security test (DAST), software composition analysis (SCA). James got in touch to say the latest updates:

> Made it easier to handle false positives and override issues in cfn-nag (uses meta-data in cloudformation otherwise), also nice with an audit record who changed state of an detected issue.

**cdk-serverless**

[cdk-serverless](https://aws-oss.beachgeek.co.uk/fe) the folks at Taimos have created this nice open source tool to facilitate the use of the AWS CDK in serverless architectures. They have put together this video to show you how to get started.

{% youtube GGc0eg3E9MM %}

**cdk-image-moderation**

[https://github.com/pahud/cdk-image-moderation](https://aws-oss.beachgeek.co.uk/fd) Pahud Hsieh is back again this week, this time with an event-driven image moderation and notification service with AWS CDK. Once you deploy the sample code within the README.md, you can  upload any images into the defined bucket and you should be able to get the notification - in the example, they use Telegram chatrooms.

![arch](https://raw.githubusercontent.com/pahud/cdk-image-moderation/31e1900be4651b8b4b5956994ff30d1ed0fea0d6/images/cdk-image-moderation2.svg)

**aws-navbar-hue-safari-extension**

[aws-navbar-hue-safari-extension](https://aws-oss.beachgeek.co.uk/fc) this is a very handy little tool from Dino Bektaš for those using Safari web browser to access AWS resources via the Console - it changes the AWS console's navbar color depending on the region you selected.

**B.AwsS3Backup**

[B.AwsS3Backup](https://aws-oss.beachgeek.co.uk/fo) this open source library from Laimonas Sutkus is a python based package that allows you to back up, restore, and seed S3 buckets. From the description, this project: "Sometimes you want to make a small modification to your S3 bucket, however it usually requires destruction of the bucket itself. This library allows you to do those small modifications without any headache. You can easily backup all your data to your local computer, delete the bucket, create a new one with desired modifications, and then simply restore it"

### Community open source posts

**Terraform**

A few weeks ago I shared an open source project from AWS Hero Ian Mckay called iamlive, an open source tool to help you generate basic IAM policies by from AWS client-side monitoring. This great post from Meir Gabay came up on my radar late last week, [Determining AWS IAM Policies According To Terraform And AWS CLI](https://aws-oss.beachgeek.co.uk/fn) which is a nice post writing how to put this into practice as part of your CI/CD pipelines. In this post Meir uses Terraform, but you should be able to take this approach to whatever tool you are using. One of my favourite posts this week, so thank you Meir!

**DevSecOps**

This post from Gourav Das, [DevSecOps Introduction: Clear Instructions on How to Build a DevSecOps Pipeline in AWS [Part 1]](https://aws-oss.beachgeek.co.uk/fg), is Part One of a two part series on how to build a DevSecOps pipeline on AWS that uses many open source tools. Gourav provides associated source code and CloudFormation templates so you can reproduce this stack for yourself.

![arch](https://hackernoon.com/images/gv93oOBCpSQa2kRIURhv0A8fVP33-n11633ax.png)

**Istio**

[Istio: external AWS Application LoadBalancer and Istio Ingress Gateway](https://aws-oss.beachgeek.co.uk/fi) Arseny Zinchenko follows up on a previous post showing you how to run a service mesh on Amazon EKS, and walks you through how to add an AWS Application Load Balancer (ALB) before the Istio Ingress Gateway.

**Kubernetes**

[Living with Kubernetes: Cluster Upgrades](https://aws-oss.beachgeek.co.uk/fj) this is the first of a series of posts from my colleague Justin Garrison, called Living with Kubernetes. In this post Justin shares some things that will guide you through common patterns to consider when upgrading Kubernetes in any environment. He covers a number of patterns for upgrading your clusterings, covering: In place, Blue/Green, Rolling and Canary. 

**GraphQL on Rust**

[Running GraphQL on Lambda with Rust](https://aws-oss.beachgeek.co.uk/fk) Dylan Anthony explores writing API development using GraphQL in Rust. To quote Dylan:

> I've been pleasantly surprised so far at how easy it's been to write a GraphQL API using Rust, much easier than doing so with the OpenAPI tools I've tested so far.

This is a short post, and Dylan provides source code for you to explore further if you want to dive deep.

**Copilot**

A couple of posts this week on AWS Copilot, a tool for developers to build, release and operate production ready containerized applications on Amazon ECS and AWS Fargate. [v1.5.0](https://github.com/aws/copilot-cli/releases/tag/v1.5.0) was released a few weeks back, so what better way to celebrate that by reading these posts.

First up we have [Pilot your containers like a boss with AWS Copilot!](https://aws-oss.beachgeek.co.uk/fl) from Florian Clanet that is a great introduction, showing you how you can get started. The post shows you how to deploy a sample application using Copilot, and shares lots of great resources if you want to go further.

Following Florian we have Danny Steenman writing, [Use AWS Copilot CLI to deploy containers on an existing infrastructure - Tutorial](https://aws-oss.beachgeek.co.uk/fm). In this tutorial Danny shows how you can easily deploy containers on your existing VPC with AWS Copilot CLI, using a sample Django application.

So not one but two good reasons for you to try out AWS Copilot this week.

**Apache Airflow**

[Automating your ELT Workflows with Managed Workflows for Apache Airflow - Part One](https://aws-oss.beachgeek.co.uk/ey) this week I managed to get some time to write about one of my favourite open source projects, Apache Airflow. In this two part blog post I cover how you can use Apache Airflow to build a workflow to help you automate your ELT/ETL tasks using two AWS services, Amazon Athena and Amazon EMR. If you are currently using Apache Hive/Presto as part of your day to day data engineering/analytics work, then take a look to see if this might be a useful approach to automating some of your tasks.

![arch](https://raw.githubusercontent.com/094459/devday-elt-automation/main/images/demo-arch.png)

### Workshops

The One Observability Demo Workshop was made available last year, and provides a workshop in multiple languages (English/Spanish/Korean/Japanese) that help you get hands on with monitoring and observability tools such as Prometheus, Grafana and OpenTelemetry. Last week Imaya Kumar Jagannathan, Rodrigue Koffi, and Rafael Pereyra put together this blog post, [AWS One Observability Demo Workshop: What’s new with Prometheus, Grafana, and OpenTelemetry ](https://aws-oss.beachgeek.co.uk/f0) that goes into a little more detail about what this workshop covers, as well as announcing some new features of this workshop that have been recently added.

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/04/16/ijaganna_One-Observability-Whats-New_f4.jpg)

Also new this week was the [AWS IoT Greengrass v2 workshop](https://aws-oss.beachgeek.co.uk/fh). AWS IoT Greengrass is an Internet of Things (IoT) open source edge runtime and cloud service that helps you build, deploy, and manage device software. This workshop walks you through how to build an edge gateway running AWS IoT Greengrass Core software v2.

![arch](https://greengrassv2.workshop.aws/images/architecture_diagram.png)

### AWS open source posts

**Amazon Corretto/OpenJDK**

[TLS 1.0/1.1 changes in OpenJDK and Amazon Corretto](https://aws-oss.beachgeek.co.uk/f7) I covered this in last weeks newsletter, but this week we have Dave Currie who dives a little deeper into what is changing and provides some useful tools to help you audit your environments so you can plan you upgrade. This is essential reading this week.

**Python Flask**

[Deploying Python Flask microservices to AWS using open source tools](https://aws-oss.beachgeek.co.uk/f1) Joseph Keating and Matt Hedges show you how to deploy an API running in a microservice architecture, deploying a Python Flask application using Docker to containerise it and deploy on Amazon ECS and then using SoapUI to test it.

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/04/05/awsjoe_Flask-Microservice_f2.png)

**Amplify DataStore**

Amplify DataStore is a library that provides a programming model for leveraging shared and distributed data without writing additional code for offline and online scenarios. In this post, [Connect Amplify DataStore with existing SQL datasources; adding offline and sync features in your application](https://aws-oss.beachgeek.co.uk/ez) Brice Pellé shows you how you can use the Amplify CLI to build an AppSync API for your DataStore application, that connects to an existing Aurora MySql database using an AppSync Lambda resolver and an Amazon RDS Proxy.

![arch](https://d2908q01vomqb2.cloudfront.net/0a57cb53ba59c46fc4b692527a38a87c78d84028/2021/04/16/image-15.png)

**AWS SAM**

[Optimizing serverless development with samconfig](https://aws-oss.beachgeek.co.uk/fa) Eric Johnson with a post that shows you how you can optimise development time by customising the default settings for your serverless application by using the samconfig used by the AWS SAM cli. Eric provides some examples to show you how, 

**Amazon Linux 2**

I have not used Windows in a long time, but if this is your preferred developer setup then this post is going to interest you if you need to use that setup to develop, deploy or work on applications that use Amazon Linux2. In the post, [Developing on Amazon Linux 2 using Windows](https://aws-oss.beachgeek.co.uk/f2) Carlos Santos and Matthew Ostovarpour show you how you can use a feature of Windows, the Windows Subsystem for Linux (WSL) and Visual Studio Code to work with Amazon Linux 2.

![arch](https://d2908q01vomqb2.cloudfront.net/0716d9708d321ffb6a00818614779e779925365c/2021/04/19/developing-on-amazon-linux2-using-windows-overview.png)

**AWS Toolkit for Visual Studio**

[AWS Toolkit for Visual Studio](https://aws-oss.beachgeek.co.uk/f5) is an open source extension for Microsoft Visual Studio running on Microsoft Windows that makes it easier for developers to develop, debug, and deploy applications using. In this post [Introducing AWS Toolkit for Visual Studio support for AWS SSO and Assume Role with MFA](https://aws-oss.beachgeek.co.uk/f6) Christopher Christou shows you how you can use this extension to configure two sets of credentials: one that makes use of MFA, and another that uses AWS SSO, showing you how to configure the Toolkit to use these credentials.

**Prometheus**

[Monitoring your service mesh container environment using Amazon Managed Service for Prometheus](https://aws-oss.beachgeek.co.uk/f8) Vikram Venkataraman, Sathiyan Baskaran, Naseer Sayyad, and Shivkumar Rajendran join forces to show you how you can deploy an application running on EKS, integrate the app with AppMesh, scrape the Prometheus metrics using Grafana Agent and then to ingest the metrics into Amazon Managed Service for Prometheus (AMP) and and then visualise them in Amazon Managed Service for Grafana (AMG). This builds upon last weeks post that announced Prometheus now has native AWS Signature v4 support, making this solution simpler to implement.

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2021/04/20/Grafana-updated.png)

**FreeRTOS**

[FreeRTOS.org update for Q1 2021](https://aws-oss.beachgeek.co.uk/f9)  Richard Elberger provides a round up of all the key announcements, news and posts from Q1 2021 covering FreeRTOS. From using Visual Studio Code, AVR Controllers, SESIP certification and much more, if you work or are interested in the IoT/devices spaces, check this post out. 

### Quick updates

**Linux**

You can now launch AWS Cloud9 development environments with Amazon Linux 2 (AL2). Amazon Linux 2 is the next generation of Amazon Linux, a Linux server operating system from Amazon Web Services (AWS). It provides a secure, stable, and high performance execution environment to develop and run cloud and enterprise applications. AWS Cloud9 is a cloud-based integrated development environment (IDE) that lets you write, run, and debug your code with just a browser. It includes a code editor, debugger, and terminal. Cloud9 comes pre-packaged with essential tools for popular programming languages including JavaScript, Python, PHP, and more, so you don’t need to install files or configure your development machine to start new projects.

**Elasticsearch**

Amazon Elasticsearch Service now supports open source Elasticsearch 7.10 and its corresponding version of Kibana. This minor release includes bug fixes and enhancements. In this new release, Elasticsearch improves indexing speed by up to 20% for certain use cases and more space efficient indices through higher compression of stored fields.

**Redis**

You can now publish the Redis slow log from your Amazon ElastiCache for Redis clusters to Amazon CloudWatch Logs and Amazon Kinesis Data Firehose. The Redis slow log provides visibility into the execution time of commands in your Redis cluster, enabling you to continuously monitor the performance of these operations. You can choose to send these logs in either JSON or text format to Amazon CloudWatch Logs and Amazon Kinesis Data Firehose.

### Video of the week

If you missed Matt Asay's talk at the Cloud City Meetup last week, then you can relax, and watch it here. Well worth checking out this conversation about the complements and conflicts between the cloud and open source. It meanders over the past, present and future of open source in a cloud world, the evolution of business models and licenses, and the best models going forward for startups based on open source projects.

{% youtube nx8-UxLz7qI %}

### Podcast of the week

**PyTorch on AWS**

In Dr Tony Hoang's Artificial Intelligence podcast, [Open source model server for PyTorch on AWS - TorchServe](https://aws-oss.beachgeek.co.uk/fp) Dr Hoang does a deep dive on PyTorch and TorchServe, covering what it is and how some customers are using it and the benefits they are seeing.

{% spotify spotify:episode:0sryuht8jzTsjGmClGDXWb %}

### Events for your diary

Watch out for these events happening later this week and next. I am especially looking forward to CDK Day, so hope to see you there.

**CDK Day**
**April 30th**

There is still time to sign up for [CDK Day](https://sessionize.com/cdkday/), which will be on April 30th. Check out [the web page](https://sessionize.com/cdkday/) to find out more about the first CDK Day, which was incredible. This second event promises to be even better.

**Cloud Native Rust Day**
**May 3rd**

Rust is a language empowering everyone to build secure, reliable, and efficient software. Rust is becoming more widely used in cloud native, powering everything from lightning-fast service meshes and powerful developer tools to internet-scale distributed databases.

Come explore what makes Rust a fantastic choice for new cloud native development, and learn about how the community uses Rust today. 

**Container Day**
**May 4, 2021 | 10:00AM - 6:00PM CEST**

Container Day x KubeCon is a fully live, virtual day of sessions all about Amazon EKS and Kubernetes at AWS, hosted by Brent Langston and Adam Keller of Containers from the Couch. At this Day Zero KubeCon event, the AWS Kubernetes team will be revealing new launches, demoing products and features, covering best practices, and answering your questions live on Twitch! If you have a question before the event, you can email the team at awscontainerday@amazon.com and maybe get them answered.

**An Introduction to Amazon Managed Blockchain**
**5th May**

Amazon Managed Blockchain (AMB) is a fully managed service that makes it easier to build scalable blockchain networks using popular open source frameworks, including Hyperledger Fabric and Ethereum. AMB includes several features and enhancements beyond those provided by the open-source projects on which it is based. It supports public and private blockchain options, each of which favors different use cases. We review reference architectures outlining example applications on both Hyperledger Fabric and Ethereum. In this lecture, you will also hear several customer success stories building solutions on Amazon Managed Blockchain.


**Building And Maintaining Your Own Secure Container OS**
**May 13th 9am PST**

Curtis Rissi, a Principal Partner SA at AWS will walk attendees through the Bottlerocket (an open-source Linux-based operating system meant for hosting containers) build process, and provide some key use cases for customisation: how to add new configuration options; how to add new packages; how to configure your own update repositories; how to add security policy; and other common customisations. 


**Mobile and Front-End Live**
**May 25th, 9:00 - 15:00 PDT**

This is a LIVE streamed event on Twitch  focused on accelerating full-stack mobile and web development. Learn about AWS Amplify, a set of purpose-built tools and services for front-end web and mobile developers that simplify app development. Deep dive into GraphQL and AWS AppSync, a fully-managed GraphQL service that improves app performance and developer productivity.

You can read more about what you can expect in the blog post, [Mobile and Front-End Live, May 25](https://aws-oss.beachgeek.co.uk/f4)



### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen).