---
title: 'AWS open source news and updates #69'
date: '2021-05-24'
tags : [ oss-newsletter ]
---
## May 24th, 2021 - Instalment #69

Newsletter #69. 

This week we celebrate more new open source projects, covering tools that can help you lock down and monitor your IAM policies, reference solutions that make it easy to deploy a number of open source projects, and a great tool to help you monitor/debug your serverless functions. On top of that the usual round up of community and AWS blog posts, featuring lots of updates on Kubernetes, performance tuning HTTP on EC2, LLVM, Apache Kafka, Triton inference, the next version of Cloudformation guard, Bottlerocket, AWS Graviton2, Tensorflow and more. What are you waiting for, dive straight in...but first :) 

**Please help me improve this newsletter**

Really would love to hear from you to know how I can make this newsletter better - what do you like, what should we do more of and most importantly what do you dislike too.

The first 20 will get an AWS credit voucher for $25 - you will get a link to the code, so make sure you don't miss that as once they are gone they are gone.

[Take me to the survey!](https://eventbox.dev/survey/LR71YHM)

Many thanks!

**Job of the Week**

[Senior Developer Advocate - OpenSearch](https://aws-oss.beachgeek.co.uk/jc)

Are you passionate about building, promoting and supporting an inclusive and growing open source community? Do you want to have direct and immediate impact on a large number of open source and AWS users? Do you want to be part of a fast-growing AWS service and work in a fast paced startup style environment?

We are looking for a Senior Developer Advocate to help us build a great and inclusive community for OpenSearch - an open source search and analytics suite derived from Apache 2.0 licensed Elasticsearch 7.10.2 & Kibana 7.10.2. This role will help us make OpenSearch the de facto choice for users that previously had relied upon open source Elasticsearch. As a Senior Developer Advocate, you will play a central role in helping us building a vibrant community of users and contributors.

Read more by clicking on the job description above.


### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Gary Stafford, Sofian Hamiti, Olajide Enigbokan, Lorenz Vanthillo, Ian McKay, Hassan Tahhan, Sofian Hamiti, Stephen Siegert, Carl Chenet, Marc Richards, Re Alvarez-Parmar, Jimmy Hayes, Santosh Bhavani, Vamshidhar Dantu, Eddie Zaneski, Nikhil Swaminathan, Matteo Rinaudo, Vijoy Choyi, Josef Viehhauser, Vu Dao and Nelson Elhage.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

**iamlive-lambda-extension**

[iamlive-lambda-extension](https://aws-oss.beachgeek.co.uk/iy) AWS Hero Ian McKay provides an extention to the iamlive project, offering a Lambda Extension that helps generate a least-privilege IAM policy by monitoring the AWS calls made within the Lambda execution environment.

**iamcanary**

[iamcanary](https://aws-oss.beachgeek.co.uk/iz) Hassan Tahhan with a tool that helps detect IAM access misconfigurations in your AWS account using periodic dry runs. This open source project can help you answer questions such as: Do you need to deploy a canary test into your AWS account to be notified when certain IAM actions do not succeed? Are you concerned about sudden changes to IAM permission boundaries impacting your workloads? Do you need to detect IAM access misconfigurations not in your control such as overly restrictive AWS Organisations Service Control Policies (SCPs)? If the answer to any of these is yes, then check this project out.

**cdk-watch**

[cdk-watch](https://aws-oss.beachgeek.co.uk/j0) this is a CLI to watch and live-update your CDK Stack's Lambdas, which means you can get real-time logs over web-sockets to make the development feedback-loop faster when debugging your lambdas. An image is worth a hundred words, so check this out.

![demo](https://camo.githubusercontent.com/26e4a63a3f4db93c99e443c7e4dfde5f24fb6fff7c3b7d51d7583cfde9ad02aa/68747470733a2f2f63646b2d77617463682d7374617469632e73332e65752d776573742d322e616d617a6f6e6177732e636f6d2f64656d6f2e676966)

**digital-pathology-on-aws**

[digital-pathology-on-aws](https://aws-oss.beachgeek.co.uk/je) OMERO (Open Microscopy Environment Remote Objects) is a well known open source solution, a collaboration between academia and commercial business, to digitise microscopy images. This repo contains everything you need to get this up and running within your AWS account.

![arch](https://github.com/aws-samples/digital-pathology-on-aws/blob/main/Figures/omero-on-aws-ha.jpg?raw=true)  

**aws-orbit-workbench**

[aws-orbit-workbench](https://aws-oss.beachgeek.co.uk/hy) [Orbit Workbench] is a new open source framework for building team-based secured data environment, that is built on Kubernetes using Amazon Managed Kubernetes Service (EKS), and provides both a command line tool for rapid deployment as well as Python SDK, Jupyter Plugins and more to accelerate data analysis and ML by integration with AWS analytics services such as Amazon Redshift, Amazon Athena, Amazon EMR, Amazon SageMaker and more. Lots of documentation to help you get started, if you work with data then make sure you check this project out.

![arch](https://raw.githubusercontent.com/wiki/awslabs/aws-orbit-workbench/Orbit-WorkBench-Arch.svg)

### Community open source posts

**LLVM**

LLVM is an open source toolchain that helps make it easier to develop new programming languages or enhance existing ones and has been extensively used in the development of languages such as Swift, Rust and Kotlin. In this post, [Building LLVM in 90 seconds using Amazon Lambda](https://aws-oss.beachgeek.co.uk/jh) Nelson Elhage provides a super post on how you can use Llama so you can run and scale compilation jobs using AWS Lambda, making it easier to compile C or C++ code.

**TensorFlow**

[Automating the Setup of SageMaker Studio Custom Images](https://aws-oss.beachgeek.co.uk/j1) this post from Sofian Hamiti walks you through the process of creating your own custom container images, in this instance one that has TensorFlow 2.5, and then using a CI/CD pipeline to build and then publish this so you can then use it within the Amazon SageMaker Studio. I am currently playing around in SageMaker Studio as part of a review for Julien Simon's 2nd edition [Learn Amazon SageMaker book](https://aws-oss.beachgeek.co.uk/j2) so was able to have a play around with this. The only clarification for those going through this walkthrough is that when you are asked for the ImageRoleArn, use your Amazon Studio's Execution role arn (that is what I used when I followed this post, and it worked for me)

**Triton**

Triton Inference Server is an open source cloud and edge inferencing project from Nvidia that is optimised for both CPUs and GPUs. In this post, [Deploying an Nvidia Triton Inference Server on Amazon ECS](https://aws-oss.beachgeek.co.uk/jk), Sofian Hamiti shows you how you can use AWS CDK to deploy this on Amazon ECS containers.

**FastAPI**

[Deploying a FastAPI backend using AWS Amplify Container-based REST APIs](https://aws-oss.beachgeek.co.uk/j3) Stephen Siegert with a great walkthrough on how to get FastAPI, a framework for setting up APIs for data science and analytics-based workloads, up and running with AWS Amplify in ...well, very Fast indeed.

**Mailtrain**

Mailtrain is a self hosted newsletter application built on Node.js (v14+) and MySQL (v8+) or MariaDB (v10+). In this post, [How to save up to 500€/year switching from Mailchimp to Open Source Mailtrain and AWS SES](https://aws-oss.beachgeek.co.uk/j4) Carl Chenet walks you through how you can reduce your costs by self hosting your newsletter subscribers using this open source project and running it on AWS and using some services such as Amazon Simple Email Service. I had not heard about Mailtrain before, and it looks super nice and feature rich so will be taking a closer look.

**Apache Kakfa / Spring**

[Eventual Consistency with Spring for Apache Kafka](https://aws-oss.beachgeek.co.uk/jl) another great post from Gary Stafford, the first of two parts, where he takes you on journey to understand how you can ensure you maintain data consistency in distributed systems that are made up of many microservices. As you might expect from the title, Apache Kakfa holds the key. So get comfortable, grab something to drink and read on to find out more.

![arch](https://miro.medium.com/max/700/0*UpyRPNG_WkV7UnrD.png)

**Tuning HTTP**

If you have been reading this newsletter for any amount of time you will know I enjoy a good performance tuning/benchmarking post, and this week we have a real treat. Marc Richards has put together this post, [Extreme HTTP Performance Tuning: 1.2M API req/s on a 4 vCPU EC2 Instance](https://aws-oss.beachgeek.co.uk/j5) showing how you can really squeeze every last bit of performance from HTTP running on an EC2 instance, iterating through a number of techniques which each time push the performance bar higher. Really compelling read this one.

![graph](https://talawah.io/blog/extreme-http-performance-tuning-one-point-two-million/libreactor-dhcp-fg.png)

**AWS Chalice**

Chalice is an open source framework for writing serverless apps in python that allows you to quickly create and deploy applications that use AWS Lambda. In this post, [CI/CD For CDN Invalidation Using AWS Lambda Function And Gitlab Pipeline](https://aws-oss.beachgeek.co.uk/jf) Vu Dao shows you how you can use this framework and address how you can clear edge stored copies of your static assets.

**AWS CDK**

A couple of posts this week. First up we have [Build Serverless Applications using CDK and SAM](https://aws-oss.beachgeek.co.uk/ji), this post is the perfect read given the recent new a few weeks ago that it is now easier to use AWS CDK and SAM together as you build your serverless applications. AWS Community Builder Lorenz Vanthillo shows you how this look by providing a nice simple walkthrough.

Then we have [AWS CDK for EKS — Handling Helm Charts](https://aws-oss.beachgeek.co.uk/jm) from Jimmy Ray, with a post showing you how you can use AWS CDK with Amazon EKS to deploy applications packaged as Helm charts.


### AWS and Amazon open source posts

**Bottlerocket**

[Getting started with Bottlerocket on AWS Graviton2](https://aws-oss.beachgeek.co.uk/jb) Vijoy Choyi brings together two technologies, Bottlerocket and AWS Graviton2, and spins up some Kubernetes clusters running the Bottlerocket OS hosted on Graviton2 based worker nodes. Why might you be interested in doing something similar? Aside from the security benefits brought by Bottlerocket, many customers are finding a better price/performance optic when running on Arm based instances that AWS Graviton2 provides.

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/04/28/vijoy_Getting-Started-Bottlerocket_f1.png)

**Kubernetes**

Big news last week as the Containers team announced the availability of Kubernetes 1.20 in Amazon EKS. Eddie Zaneski dives deeper into this announcement in his post, [Amazon EKS 1.20 Released](https://aws-oss.beachgeek.co.uk/j8) taking a look at the main features of this release, changes you should be aware of, specifics to Amazon EKS and a few things to consider as you ponder migrating from 1.19.

**Next.js**

Big news last week for folks who love to use AWS Amplify to host their websites with the announcement of now supporting server-side rendering (SSR) apps built with the Next.js framework. In this post, [Host a Next.js SSR app with real-time data on AWS Amplify](https://aws-oss.beachgeek.co.uk/j9) Nikhil Swaminathan walks you through an example so you can see how simple this is, with very little configuration for you to do and plenty of flexibility. Nikhil provides some additional resources to get you going.

**Amplify**

[Restoring AWS Amplify project after deleting it from the cloud](https://aws-oss.beachgeek.co.uk/jj) Olajide Enigbokan put together a nice guide to help you if you ever find yourself needing to recover from deleting your Amplify projects. Covering what is and is not recovered to how to actually do this, essential reading for those of you who use and love AWS Amplify.

**AWS CloudFormation Guard 2.0**

AWS CloudFormation Guard is an open-source general-purpose policy-as-code evaluation tool. It provides developers with a simple-to-use, yet powerful and expressive domain-specific language (DSL) to define policies and enables developers to validate JSON- or YAML- formatted structured data with those policies. Announced last week, the Guard 2.0 release is a complete re-write to make the tool general-purpose. In this post, [Introducing AWS CloudFormation Guard 2.0](https://aws-oss.beachgeek.co.uk/ja) Matteo Rinaudo covers some of those changes, and walks you through some examples of the new features.

![demo](https://raw.githubusercontent.com/aws-cloudformation/cloudformation-guard/main/images/guard-demo.gif)

**AutoGluon**

[AWS releases code to help reduce bias in machine learning models](https://aws-oss.beachgeek.co.uk/jg) Valerio Perrone and Michele Donini present details of a new paper demonstrating how to help mitigate bias via tuning a models hyper-parameters. You can find more details including a link to the research paper and code samples and tutorials in this post.

![bias](https://assets.amazon.science/dims4/default/5bb5921/2147483647/strip/true/crop/2424x890+0+0/resize/1200x441!/quality/90/?url=http%3A%2F%2Famazon-topics-brightspot.s3.amazonaws.com%2Fscience%2F0c%2F1c%2F3178f4e74280b842c10e813e0d28%2Fbo-vs-cbo.png)

**YOLO**

YOLO (You Only Look Once) is part of the DL single-stage object detection model family, which includes models such as Single Shot Detector (SSD) and RetinaNet. Santosh Bhavani and Vamshidhar Dantu help open your eyes on how you can use Neo to improve the performance of image classification in their post, [Speed up YOLOv4 inference to twice as fast on Amazon SageMaker](https://aws-oss.beachgeek.co.uk/j7)

**Wordpress**

We all remember our first website, and after a brief reminis of days gone by, Re Alvarez-Parmar and Jimmy Hayes take time to write about how many people now start creating their websites on the web - via Wordpress. In, [Running WordPress on Amazon ECS on AWS Fargate with Amazon EFS](https://aws-oss.beachgeek.co.uk/j6) they apply modern cloud approaches to build a scalable and robust architecture that ensures Wordpress can serve the next generation of creators. 

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2021/05/20/image-2021-05-20T153609.196.png)

### Quick updates

**Spring**

If you are a java developer and use Spring on AWS, make sure you read the announcement last week, [Spring Integration for AWS 2.5 went GA last week.](https://aws-oss.beachgeek.co.uk/jd) 

**Kubernetes - 1.20**

Amazon EKS and EKS Distro now support Kubernetes version 1.20. Highlights of the Kubernetes 1.20 release include RuntimeClass and Process ID Limits reaching stable status, API Priority and Fairness being enabled by default, and kubectl debug reaching beta status.

Amazon EKS provides support for at least 4 Kubernetes versions at any given time. Kubernetes 1.16, 1.17, 1.18, 1.19, and 1.20 are all fully supported by EKS today, and new clusters can be started using any of these releases. However, given the Kubernetes quarterly release cycle, it is critical for all customers to have an ongoing upgrade plan.

Kubernetes version 1.16 will no longer be supported on July 25th, 2021. On this day, you will no longer be able to create new 1.16 clusters and all existing EKS clusters running Kubernetes version 1.16 will eventually be updated to the latest available platform version of Kubernetes version 1.17.

We recommend customers upgrade existing 1.16 clusters and worker nodes to at least 1.17 as soon as practical.

**Kubernetes - CoreDNS and kube-proxy**

Amazon EKS now supports using the Amazon EKS console, CLI, and API to install and manage CoreDNS and kube-proxy in addition to existing support for the Amazon VPC CNI networking plugin. This makes it easier to define consistent Kubernetes clusters and keep them up to date using Amazon EKS.

CoreDNS and kube-proxy provide critical networking functionality for Kubernetes applications. Now, these operational software components, “add-ons”, can be installed, managed, and updated directly through the EKS console, CLI, and API. Each add-on is validated by AWS and can be deployed and updated during cluster setup or at any time. You can see available add-ons and compatible versions in the EKS API, select the version of the add-on you want to run on your cluster, and configure key settings such as the IAM role used by the add-on when it runs. Using EKS add-ons you can go from cluster creation to running applications in a single command and keep your cluster up to date using the Amazon EKS console, CLI, or API.

**AWS Copilot**

Today, AWS Copilot announced the general availability of version 1.7, which enables you to easily deploy request-driven web services with AWS App Runner in addition to Amazon Elastic Container Service (Amazon ECS). AWS App Runner is a fully managed container application service that makes it easy for customers without any prior containers or infrastructure experience to build, deploy, and run containerised web applications and APIs in just a few clicks.

**Visual Studio Code**

The AWS Toolkit for VS Code is an open-source plugin that lets you leverage the integrated development environment (IDE) for the creation, debugging, and deployment of software applications on Amazon Web Services. The AWS Toolkit extension shows resources in your AWS account through the AWS Explorer view. This interface option enables you to interact with an array of AWS services to carry out tasks such as viewing S3 resources, opening CloudWatch logs, and invoking Lambda functions.

With this update to the AWS Toolkit for VS Code, customers can now create, locally debug, and deploy Lambda functions written in Java and Go. Java users will be able to step-through debug Lambdas built with Maven and Gradle in Java 8, Java 8.al2, and Java 11, while Go users will be able to do the same with Lambdas built in Golang 1.14+.

### Videos of the week

First up, very happy to see the folks at BMW talking about their open source plans for their Autonomous Driving Data Lake architecture. Check out the whole video as it is an very interesting sector, but if you just want to check out the BMW story and hear Josef Viehhauser dive deep into this topic, skip forward to 9min.

{% youtube 2Cr2EYp8WgM %}


AWS Community Builder Luc van Donkersgoed, put together this video exploring how AWS CDK brings infrastructure-as-code closer to DevOps engineers, covering three segments: the power of a multi-language framework, the benefits of applying unit testing to your infrastructure and applying the time-proven concepts of object oriented design and DRY to your infrastructure-as-code.

{% youtube tiyjhWTSExg %}

### Events for your diary

Several events for you this week...

**How to Run Your First HPC Job on AWS**
**May 25th, 8:00PM CET**

In this online webinar you will learn how to set up your first HPC cluster on AWS. We'll cover everything from installing AWS ParallelCluster (and open source cluster management tool to deploy and manage HPC clusters in the AWS cloud), selecting the your Amazon EC2 instances, when to use Spot Instances to save up to 90% on compute, to launching your first MPI “hello world” job from the command line.

Find out more and register by clicking over [here.](https://aws-oss.beachgeek.co.uk/io)

**Mobile and Front-End Live**
**May 25th, 9:00 - 15:00 PDT**

This is a LIVE streamed event on Twitch  focused on accelerating full-stack mobile and web development. Learn about AWS Amplify, a set of purpose-built tools and services for front-end web and mobile developers that simplify app development. Deep dive into GraphQL and AWS AppSync, a fully-managed GraphQL service that improves app performance and developer productivity.

You can read more about what you can expect in the blog post, [Mobile and Front-End Live, May 25](https://aws-oss.beachgeek.co.uk/f4) and [register via this link](https://aws-oss.beachgeek.co.uk/f3).

**OpenSearch: The open source successor of Elasticsearc**
**May 27th, 9am EST/3pm CET**

Join Dotan Horovits and Kyle Davis for this fireside chat talking about the recent beta of OpenSearch, the community and what lies ahead.

Streamed [via YouTube here](https://www.youtube.com/watch?v=UDvWdTeH5V4).


**Cloud Native Day**
**23rd September, Bern Switzerland**

What is this, an in person event returning? A stellar line up including our own Michael Hausenblas, an event looking at CNCF projects and the future of IT. Find out more and to view prices/register, by clicking [here](https://cloudnativeday.ch/en/#speakers).


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen).