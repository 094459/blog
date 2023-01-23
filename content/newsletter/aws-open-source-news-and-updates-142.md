---

title: 'AWS open source newsletter #142'
date: '2023-01-23'
tags : [ oss-newsletter, aws open source, Memcached, Amazon EMR, OpenLineage, Marquez, Apache Airflow, MWAA, AWS SAM, Amazon Corretto, Flagger, Amazon EKS, Kubernetes, AWS CDK, Apache Tika, OpenSearch, GraphQL, Flintrock, ]

---

## January 23rd, 2023 - Instalment #142

**Welcome**

Welcome to edition #142 of the AWS open source newsletter.

We have another great round up of new projects for you to get stuck into. Here are just a taste of some of the projects, kicking off with "sls-mentor" a new tool to help you assess your serverless applications, "subnet-watcher", a tool to help you monitor your IP addresses, "aws-cdk-web-administered-apps" a very nice reference solution for applications that have a user and admin component, "serverless-newsletter-app" if you are looking for a newsletter solution and want to host your own, look here first, "aws-iot-with-privatelink" shows you how you use private networks for your IoT traffic, "emr-spark-benchmark" benchmarking tool for assessing your Amazon EMR environments, and "update-aws-ip-ranges" keep automatically updated on Amazon's IP address ranges. There are many more projects to check out, so make sure you give them your time.

For those looking for blogs, tutorials, this week we have content featuring Memcached, OpenLineage, Marquez, Apache Airflow, Amazon Corretto, Flagger, AWS CDK, Apache Tika, OpenSearch, GraphQL, Flintrock, and more. Finally, make sure you check out the videos and events section at the end of this newsletter so you don't miss out on these events.

**Raffle prize winner**

Before Christmas we had a raffle to win some cool AWS SWAG. I can now reveal that the winning ticket is **038C123F-DA73-4584-ABE2-** - if this matches your ticket, then please contact me at ricsue@amazon.com with the LAST portion of the ticket. If yours matches what I have, you are a winner!


### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes: Ethan Steininger, Stephen Said, Paul Villena, Vishwanatha Nayak, Brian Beach, Ran Isenberg, Jayesh Vartak, Allen Helton, James Eastham, Julian Wood and John Jackson.

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution.*

#### Tools

**sls-mentor** 

[sls-mentor](https://aws-oss.beachgeek.co.uk/2g4) is an open source tool that analyses the configuration of your AWS resources against best practice rules, helping you to remove before they occur, and optimises your app’s performances and costs. Check out the blog post [sls-mentor: your serverless quality teacher has arrived!](https://aws-oss.beachgeek.co.uk/2g5) where Pierre Chollet provides more info as to the origins of why this project was created, walks you through some of its capabilities, and then looks forward to what they are hoping to do next. Well worth checking out.

![demo of sls-mentor](https://github.com/sls-mentor/sls-mentor/blob/master/docs/images/guardian-run.gif?raw=true)

**subnet-watcher**

[subnet-watcher](https://aws-oss.beachgeek.co.uk/2fs) is a neat tool that monitors the remaining free IP addresses in AWS VPC subnets (both public and private) using some CloudWatch custom metrics. It also sets up alerts to provide complete visibility on your VPC CIDR IP space. Hat Tip to Corey Quinn who shared this tool in his weekly AWS Newsletter.

**aws-cdk-web-administered-apps**

[aws-cdk-web-administered-apps](https://aws-oss.beachgeek.co.uk/2ft) this looks like it is going to help a lot of folk automate the deployment of well known open source software. This CDK+Python project is designed to support the web administered app model, where the admin interface is hosted within the same codebase as the front-end application. To achieve this outcome more securely, this project creates two groups of server hosts - one with admin access and one with only read access. This enables you to restrict all write operations to a server (or servers) that can only be accessed from specific allowed IP addresses. Comes with a couple of examples (Wordpress and Node-RED) to help you see how this works.

![architecture of aws cdk web admin apps](https://github.com/aws-samples/aws-cdk-web-administered-apps/blob/main/assets/sol_diagram.png?raw=true)

**serverless-newsletter-app**

[serverless-newsletter-app](https://aws-oss.beachgeek.co.uk/2fr) provides a complete Newsletter application that you can deploy yourself, leveraging AWS serverless services and SendGrid. AWS Hero Allen Helton shares his story in hist post, [How I Built An Open Source Serverless Newsletter Platform](https://aws-oss.beachgeek.co.uk/2fq). In it he writes how he came to build this open source project, and how you can use it to create your own Newsletter app. Very cool indeed.

![architecture of serverless newsletter app](https://camo.githubusercontent.com/babfd8c7825fd7ce8594fbee9720155e94dc259a66e916d91378bdd1da9951e8/68747470733a2f2f7265616479736574636c6f75642e73332e616d617a6f6e6177732e636f6d2f6e6577736c65747465725f706c6174666f726d5f312e6a666966)

**slapo**

[slapo](https://aws-oss.beachgeek.co.uk/2g2) Slapo is a schedule language for progressive optimisation of large deep learning model training. Large deep learning models demonstrate dominating model accuracy on a range of tasks in NLP and CV, but it is hard to train the model efficiently while preserving the usability. Slapo aims to address this tension through separation of concerns. Slapo decouples model execution from definition, enabling developers to use a set of schedule primitives to convert a PyTorch model for common model training optimizations without directly changing the model itself.

**update-aws-ip-ranges**

[update-aws-ip-ranges](https://aws-oss.beachgeek.co.uk/2fz) AWS publishes a list of it's IP address ranges (you can [see the list here](https://aws-oss.beachgeek.co.uk/2g0)) This project creates Lambda function that automatically create or update AWS resource with AWS service's IP ranges from that ip-ranges.json file. You can configure which service and region to get range. You can also configure to which resources you want to create or update with those ranges. Use cases include allowing CloudFront requests, API Gateway requests, Route53 health checker and EC2 IP range (which includes AWS Lambda and CloudWatch Synthetics). The resources are created or updated in the region where the CloudFormation stack is created.

**emr-spark-benchmark**

[emr-spark-benchmark](https://aws-oss.beachgeek.co.uk/2fw) This repository provides a general tool to benchmark Spark performance on Amazon EC2 and Amazon EMR. The repos use an open source tool Flintrock to launch EC2 based Apache Spark clusters. If you want to baseline or compare how your Apache Spark performs, why not give this repo a try.

**unlock-mainframe-data-files-on-aws**

[unlock-mainframe-data-files-on-aws](https://github.com/aws-samples/unlock-mainframe-data-files-on-aws) This solution is designed to help you unlock legacy mainframe data by migrating data files from mainframe systems to AWS. The solution involves transferring data from mainframe datasets, converting it into a CSV format, and then storing the data in AWS.

![architecture of unlock mainframe data](https://raw.githubusercontent.com/aws-samples/unlock-mainframe-data-files-on-aws/main/samples/images/Lambda-based-deployment.png)


**axios-based-http-testing-tool**

[axios-based-http-testing-tool](https://aws-oss.beachgeek.co.uk/2fx) [Axios](https://aws-oss.beachgeek.co.uk/2fy) is a simple promise based HTTP client for the browser and node.js. This repo provides everything you need to help you deploy an axios based HTTP testing tool solution on AWS.

![architecture for axios on aws](https://github.com/aws-samples/axios-based-http-testing-tool/blob/main/images/architecture.png?raw=true)

### Demos, Samples, Solutions and Workshops

**aws-iot-with-privatelink**

[aws-iot-with-privatelink](https://aws-oss.beachgeek.co.uk/2fv) The goal of this project is to create IOT private link for customer who wants to send data from IoT device securely through private network without using public internet. The repo contains detailed breakdown of how this is achieved, and you can try it for yourself as they have a nice simulator to help you kick the tyres.

![architecture for iot with privatelink](https://github.com/aws-samples/aws-iot-with-privatelink/blob/main/docs/IOT-privatelink.png?raw=true)

**serverless-smart-streaming-engine**

[serverless-smart-streaming-engine](https://aws-oss.beachgeek.co.uk/2g1) this repo is for football fans (especially if you support Tottenham Hotspurs), and is a demo that shows how you can use CDK and amplify to build a streaming service with a smart backend that analyse the streaming media using a AI/ML service. 

![architecture for serverless smart streaming](https://github.com/aws-samples/serverless-smart-streaming-engine/blob/main/images/2022-12-28-20-38-37.png?raw=true)


In this particular demo, it sends a soccer game that Tottenham plays, generate clips, and services only clips that Son Heung-min appears. (other teams and players would work). Make sure you check the demo clips in the repo. Very cool.

![demo of spurs clips](https://github.com/aws-samples/serverless-smart-streaming-engine/blob/main/images/2023-01-05-09-57-31.png?raw=true)

**amazon-personalize-online-recommendations-with-google-tag-manager**

[amazon-personalize-online-recommendations-with-google-tag-manager](https://aws-oss.beachgeek.co.uk/2fu) this repo provides some help to get you started working with Amazon Personalize, and AWS service that allows developers to quickly build and deploy curated recommendations and intelligent user segmentation at scale using machine learning (ML). If you are using Google Tag Manager (GTM) then see how you can integrate that date to create more personalised recommendations for your customers.

![architecture and overview of tag manager for amazon personalize](https://github.com/aws-samples/amazon-personalize-online-recommendations-with-google-tag-manager/blob/main/Architecture.png?raw=true)

### AWS and Community blog posts

**OpenLineage**

If you are looking to dive into data lineage, an increasingly important area of your data governance strategy, then read on as this post is for you. OpenLineage is an open source project provides a technology-agnostic metadata model for capturing data lineage and integrates with widely used tools, including Apache Airflow, the topic for this blog post. In the post, [Automate data lineage on Amazon MWAA with OpenLineage](https://aws-oss.beachgeek.co.uk/2fj), Stephen Said, Paul Villena, and Vishwanatha Nayak show you how you can get started,  using Marquez, an open-source metadata service for collection and visualisation of data lineage with support for the OpenLineage standard. [hands on]

![architecutre of marquez and mwaa](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2023/01/13/BDB2522-04-solution-overview-1.png)

**OpenSearch**

We have a couple of great posts this week for OpenSearch fans.

Starting us off we have Ethan Steininger, who has written this post, [Searching PDFs in S3 Using OpenSearch and Tika](https://aws-oss.beachgeek.co.uk/2g3) where he shows you a hands on guide in how to build a Python script that is able to search the contents of PDF files in an Amazon S3 bucket using Apache Tika and OpenSearch. Apache Tika is an open source project that helps you extract data from files, and in this tutorial the focus is on searching PDFs. Very nice little project. [hands on]

Next up we have [Introducing identity and access control for OpenSearch](https://aws-oss.beachgeek.co.uk/2g6) from Peter Nied who explores the current and future direction of the OpenSearch security model. This direction presents a significant departure from the current security model, but these OpenSearch security features will help it be more efficient, more reliable, and simply easier and more enjoyable to work with. As OpenSearch is an open source project, they are currently inviting folk to share there views and comments, so check out the blog post for more details.

**AWS CDK**

A couple of posts featuring AWS CDK this week. Kicking off with, [Manually Approving Security Changes in CDK Pipeline](https://aws-oss.beachgeek.co.uk/2fk) Brian Beach provides a nice overview of how to add a manual approval to AWS Cloud Development Kit (CDK) Pipelines to confirm security changes before deployment. With this solution, when a developer commits a change, CDK pipeline identifies an IAM permissions change, pauses execution, and sends a notification to a security engineer to manually approve or reject the change before it is deployed. [hands on]

![screenshot of cdk permissions change](https://d2908q01vomqb2.cloudfront.net/7719a1c782a1ba91c031a682a0a2f8658209adbf/2023/01/17/sdevops-2230_3.png)

Following that we had AWS Community Builder (and Build on Open Source guest) Ran Isenberg put together [Build AWS Lambda Layers with AWS CDK](https://aws-oss.beachgeek.co.uk/2fp) giving you a gentle introduction into AWS Lambda layers and then how you can build your own using Docker and AWS CDK.

**Kubernetes**

If you are self managing Kubernetes, this post is for you. Jayesh Vartak looks at how to use pod priority and dummy pods that have a pause container to eliminate or minimise the time required for provisioning the worker nodes during scaling in hist post, [Eliminate Kubernetes node scaling lag with pod priority and over-provisioning](https://aws-oss.beachgeek.co.uk/2fo) [hands on]

![overview of kubernetes solution](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2023/01/12/pic-01-flow-1.png)

**Other posts and quick reads**

* [Is the GitHub Actions self-hosted runner safe for Open Source?](https://aws-oss.beachgeek.co.uk/2g8) is a great post that will get you to think about your options around both why you might want to run your own self-hosted runners, and what you need to thin about
* [Visualize and gain insights into your AWS cost and usage with Amazon Managed Grafana](https://aws-oss.beachgeek.co.uk/2fm) demonstrates how you can visualise and analyse your AWS Cost and Usage data with Amazon Managed Grafana [hands on]

![dashboard of aws cost displayed in grafana](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2023/01/17/cloudops_860_13.png)

* [Journey to adopt Cloud-Native DevOps platform Series #2: Progressive delivery on Amazon EKS with Flagger and Gloo Edge Ingress Controller](https://aws-oss.beachgeek.co.uk/2fi) looks at the technical steps to build a DevOps platform using open source components that enables the progressive deployment of microservices on Amazon Managed Amazon EKS [hands on]
* [Set up Amazon SageMaker Studio with Jupyter Lab 3 using the AWS CDK](https://aws-oss.beachgeek.co.uk/2fl) guides you through the steps to get started with setting up and deploying Studio to standardize ML model development and collaboration with fellow ML engineers and ML scientists using a CDK app written in Python [hands on]
* [Automate backups for AWS Amplify GraphQL backends with AWS Backup](https://aws-oss.beachgeek.co.uk/2fn) shows how you can easily build a modern full stack cloud based application with an automated backup solution to meet your data protection needs [hands on]

![architecture of graphql backup](https://d2908q01vomqb2.cloudfront.net/e1822db470e60d090affd0956d743cb0e7cdf113/2022/12/20/AwsBackupAmplifyAppsync.png)

### Quick updates

**Amazon Corretto**

On January 17, 2023 Amazon announced quarterly security and critical updates for Amazon Corretto Long-Term Supported (LTS) versions of OpenJDK. Corretto 19.0.2, 17.0.6, 11.0.18, 8u362 are now [available for download](https://aws-oss.beachgeek.co.uk/2fh). Amazon Corretto is a no-cost, multi-platform, production-ready distribution of OpenJDK. 

**Memcached**

Amazon ElastiCache for Memcached has added support for Memcached version 1.6.17. This version is a cumulative update and contains all changes and improvements from version 1.6.12 to 1.6.17. For the full list of improvements and bug fixes in Amazon ElastiCache for Memcached 1.6.17, see the [release notes](https://aws-oss.beachgeek.co.uk/2fg).

**Amazon EMR**

Amazon EMR is a cloud big data platform for data processing, interactive analysis, and machine learning using open-source frameworks such as Apache Spark, Apache Hive, and Presto. Announced last week, Amazon EMR has made it 30% faster to launch an EMR on EC2 cluster in a private subnet. Customers can get the faster cluster start-up times by simply relaunching their EMR on EC2 private subnet clusters. No further action is needed.

### Videos of the week

**AWS SAM - Building Java Serverless applications**

The AWS Serverless Application Model (AWS SAM) is an open-source framework that helps to build Serverless applications on AWS. It provides a command-line interface (CLI) and extensions on top of AWS Cloud Formation to simplify the development of serverless applications.

In this video, James Eastham walks you through how to initialise, build, deploy and develop against your first serverless Java application. He looks at how SAM compiles and deploys your code and also an easy way to speed up the software development life cycle.

{{< youtube gde38Yk5PQI >}}


**Apache Airflow**

Great video featuring two of my most favourite people, Julian Wood and John Jackson take a look at how to effectively run Amazon Managed Workflows for Apache Airflow (Amazon MWAA) at scale. You hear about options available to scale workloads, explore different techniques to optimise performance when running at scale, with a demo running thousands of DAGs at scale.

{{< youtube VAyhnFX_zb8 >}}


**Build on Open Source**

For those unfamiliar with this show, Build on Open Source is where we go over this newsletter and then invite special guests to dive deep into their open source project. Expect plenty of code, demos and hopefully laughs. We have put together a playlist so that you can easily access all (eight) of the episodes of the Build on Open Source show. [Build on Open Source playlist](https://aws-oss.beachgeek.co.uk/24u)

# Events for your diary

If you are planning any events in 2023, either virtual, in person, or hybrid, get in touch as I would love to share details of your event with readers. 

**AWS Java Panel #2 SnapStart and SpringCloud AWS**
**Jan 25th, 6:15PM GMT**

Join this free online event with a great lineup of speakers who will discuss all about latest "AWS coldstart killer: SnapStart" and how and how much it improves startup times for Java Serverless Lambda functions. They will introduce you to what SnapStart is, and then discuss first month of production experience. Following that presentation the next talk lined up is "SpringCloud AWS", presented by Maciej Walkowiak Let's see what are the latest updates and how this library improves AWS + Spring experience.

Find out more and register to take part at [the meetup link here](https://aws-oss.beachgeek.co.uk/2g7).

**FOSSDEM**
**Feb 4-5th, 2023 in Brussels**

FOSDEM is a free event for software developers to meet, share ideas and collaborate. Every year, thousands of developers of free and open source software from all over the world gather at the event in Brussels. 4 & 5 February 2023. A must attend event for all open source fans, check out and [register via this link](https://aws-oss.beachgeek.co.uk/2dc).

**State of Open Con 23**
**Feb 7-8th, 2023 in London**

OpenUK will be hosting a 1000 person plus two day conference in Central London, “State of Open Con 23”  in association with IEEE, the headline sponsor. Check out more info and [sign up here](https://aws-oss.beachgeek.co.uk/2dd).

**PGConf India**
**Feb 22nd to 24th, Radisson Blu Bengaluru, India**

If you are in or can get to Bengaluru, then checkout this conference for PostgreSQL developers and enthusiasts. Check out the session line up and get [your tickets here](https://aws-oss.beachgeek.co.uk/2ff).


**Everything Open**
**March14-15th Melbourne, Australia**

A new event for the fine folks in Australia. Everything Open is running for the first time, and the organisers (Linux Australia) have decided to run this event to provide a space for a cross-section of the open technologies communities to come together in person. Check out the [event details here](https://aws-oss.beachgeek.co.uk/2ds). The CFP us currently open, so why not take a look and submit something if you can.

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)

