---
title: 'AWS open source news and updates No. 27'
date: '2020-07-06'
tags : [ oss-newsletter ]
---
*Updated, 18th Jan to remove dead links*

## July 6th - Instalment #27

Week No.27, and as the days start getting shorter, these weekly newsletters just keep getting longer. There is so much activity and energy in open source, and I am continuously amazed at what new stuff I unearth and uncover.

This week we have more machine learning goodness, containers, a splattering of serverless, some very interesting .NET updates as well as some more esoteric articles.

Remember, if you have a project you want me to mention or talk about, then please reach out. I do provide prizes for the ones that I particularly like, so there is also that incentive too.

### Job of the week

**Senior Developer Advocate - Open Source**

Are you passionate about building, promoting and supporting an inclusive and growing open source community? Do you want to have direct and immediate impact on a large number of open source and AWS users? Do you want to be part of a fast-growing AWS service and work in a fast paced startup style environment?

We are looking for senior developer advocate and open source community leader to drive forward Open Distro for Elasticsearch and help make it the de facto choice for users who want to run open source Elasticsearch.

Check out the [job description](https://www.amazon.jobs/en-gb/jobs/1165938/senior-developer-advocate-open-source) for more details. Do not hesitate to get back to me if you have any questions, I am here to answer any thing you might want to know.

### Want to help this project?

This open source project from Daniel Burke at Steamhaus, **[kubeswitch](https://github.com/dannyburke1/kubeswitch)** allows you to easily switch between different kubectl binaries. Currently working on Mac, but Danny is looking to bring this to a broader audience and is looking for people to get involved. If you use kubectl and are looking for a project to help, then get in touch with Danny.


### Looking for your feedback please

I have put together a short feedback survey, which I would ask you to take - it will take no more than 2 minutes. You can access [here](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn). Many thanks!

[Take the survey](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn)

### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created.

So thank you to  Brian Annis, Kisan Tamang, Daniel Burke, Moez Ali, Luca Bianchi, Amrish Thakkar, Elvira Dzhuraeva, Amit Saha, Debo Dutta, Alex Smola, Hana Thier, Pulkit Kapur, Rahul Iyer, Eric Kim, Laurence Rouesnel, Rocky Zhang, Dweep Sharma, Steve Roberts, Shrinath Kurdekar, Baha Chammakhi, Jimmy Dahlqvist, Mirko Vukušić, Jeremy Daly, Alexandre Freire, Matthieu Napoli, Jason Ly and Liz Percak Dennett

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

**cfn-resource-actions**

[cfn-resource-actions](https://github.com/mhlabs/cfn-resource-actions) is an open source project from the Mathem tech team that provides you with a VS Code extension that lets you perform actions against deployed AWS resources direction from the CloudFormation/SAM Tempaltes. Checkout the info from the [Visual Studio Marketplace here](https://marketplace.visualstudio.com/items?itemName=ljacobsson.cfn-resource-actions), or check out the code in the[ GitHub repository](https://github.com/mhlabs/cfn-resource-actions). 


**cloudeecms**

[CloudeeCMS](https://github.com/WebGateConsultingAG/CloudeeCMS) is a serverless  web content management system developed by WebGate in Switzerland that lets you publish web pages without having to worry about managing any EC2 servers. The project provides a cloudformation template to get you started as well as documentation so you know what to do.

**terraform-aws-nlb**

[terraform-aws-nlb](https://github.com/cloudposse/terraform-aws-nlb) from the Cloud Posse is a Terraform module to create an NLB and a default NLB target and related security groups. 

**Guardicore**

[Guardicore](https://github.com/guardicore/monkey) Infection Monkey is an open source security tool for testing a data centre's resiliency to perimeter breaches and internal server infection. The Monkey uses various methods to self propagate across a data centre and reports success to a centralised Monkey Island server. This project has two components, Monkey, which infects machines and propagates and the other component, Monkey Island (I kid you not!) which is the control plane. I am feeling all nostalgic for one of my favour adventure games of all time now. Why not check out the well organised and easy to read docs [here](https://www.guardicore.com/infectionmonkey/docs/).

![monkey](https://github.com/guardicore/monkey/raw/develop/.github/map-full.png)

**awesome-aws**

[Awesome AWS](https://github.com/donnemartin/awesome-aws) is less code and more a curated list of resources from many contributors. Within this you will find a well organised list of ever resources that you might possibly need, including a list of the open source projects within AWS repositories. Still being updated and maintained, so bookmark this today.

**WireViz**

[WireViz](https://github.com/formatc1702/WireViz) is not specific to AWS, however, when working with IoT or Robotics, the need to provide clear and easy to follow documentation around electronic and wiring is important, and this s a tool for easily documenting cables, wiring harnesses and connector pinouts. It takes plain text, YAML-formatted files as input and produces beautiful graphical output (See the sample below). The output is very nice indeed, and far better than what I currently produce today so if you are a Maker, IoT or Robotics builder and are looking for a better way to present your work, look no further. 

![wiring](https://github.com/formatc1702/WireViz/raw/master/examples/demo02.png)

**RedDolphin**

[RedDolphin](https://github.com/elitest/Reddolphin) is a collection of scripts that use the Amazon SDK for Python boto3 to perform red team operations against the AWS API. Easily installed, it provides a number of scripts you can use to check you EC2 instances, AWS keys and more.

**aws-xd-ui-kit**

If you are a user of Adobe's XD then this project will be of interest. It provides a template for you to start using Adobe XD to visualise your AWS architecture. You can get these resources from the [aws-xd-ui-kit GitHub repository](https://github.com/ExamProCo/aws-xd-ui-kit), and ExamPro have written a little about their motivation on this blog post, [AWS Quickly Build Architectural Diagrams on Adobe XD](https://dev.to/exampro/aws-free-ui-kit-on-adobe-xd-496h)


### Blog posts you should check out

[Building a Multi-Tenant gRPC Development Platform with Ambassador and AWS EKS](https://hackernoon.com/building-a-multi-tenant-grpc-development-platform-with-ambassador-and-aws-eks-hgt3uh0?source=rss) - this post from [Brian Annis](https://www.linkedin.com/in/brianannis/) is a fantastic read, shows how the PlaceExchange team extended their existing RESTful services running on Amazon EKS to support gRPC services using the Ambassador Edge Stack.

![architecture](https://hackernoon.com/photos/4sk6eGzDnrU1CLYT7UcYe31UdUm2-mg23wcx)

Make sure you follow Brian so you don't miss out future posts he shares.

**PyCaret, Streamlit and AWS Fargate**

[Deploy PyCaret and Streamlit app using AWS Fargate — serverless infrastructure](https://towardsdatascience.com/deploy-pycaret-and-streamlit-app-using-aws-fargate-serverless-infrastructure-8b7d7c0584c2), another great deep dive post from Moez Ali, walks you through deploying a PyCaret model served via Streamlit (an open source web application framework for Python), deploying this onto AWS Fargate. This tutorial is very detailed and is intended so that anyone can get started with these technologies quickly. Nice work Moez!

**Getting started with AWS CDK**

[AWS CDK: Boilerplating to Build Node.js Apps in TypeScript](https://dev.to/jasonlyy/aws-cdk-boilerplating-to-build-node-js-apps-in-typescript-5a6a) - if you looking for some quick start boilerplate code to quickly get started using TypeScript, how to get setup and some examples then Jason Ly has just what you need. Here is a [link to the corresponding GitHub repository](https://github.com/JasonLyy/cdk-ts-boilerplate) as well.

**PHP and Bref**

So, on a PHP streak over the past few weeks and that streak continues with some more posts on running PHP on AWS. I have shared a few articles on PHP over the past few weeks, so it is good to see more PHP content for builders.

**Modern scalable PHP applications**

[Creating and running modern and scalable PHP applications](https://dev.to/alexandrefreire/creating-and-running-modern-and-scalable-php-applications-b4i), Alexandre Freire's post talks about what is a modern application and how you can achieve this through PHP. It is a short read, but if you are a PHP developer that is curious about serverless and modern applications and how they fit with PHP, this is the post for you.

**Serverless Chats - Matthieu Napoli**

If you have not already signed up to Jeremy Daly's Serverless chats then take a moment to do that now. In this episode, he talks with Matthieu Napoli (@matthieunapoli) about why PHP is still an important part of the web landscape, how Bref can help you make existing PHP workloads #serverless, and whether or not PHP devs will embrace serverless design patterns.  

{% youtube H8tkZcjQxOA %}

**Build and Deploy with SAM**

[Build & deploy all AWS resources as easy as: npm run deploy-prod (AWS Sam worflow)](https://dev.to/psiho/build-deploy-all-aws-resources-as-easy-as-npm-run-deploy-prod-aws-sam-worflow-4d83) - this post from Mirko Vukušić, he shares his first steps in using AWS Serverless Application Model (AWS SAM) to simplify and make it easy to deploy to production. 

**GitHub runners**

[GitHub Self hosted runners on AWS, part 2 EC2](https://dev.to/jimmydqv/github-self-hosted-runners-on-aws-part-2-ec2-3jhj) - this post from Jimmy Dahlqvist, is the follow up of a post I shared before on running GitHub runners on AWS Fargate. This time though, Jimmy covers how to get this up and running on Amazon EC2 instances.

**Getting started with minio**

Minio is an open source project that provides object storage server compatible with the Amazon S3 cloud storage service. In [this post](https://www.bahachammakhi.tn/articles/5ef78fa5f13e2b0017c086d9) from Baha Chammakhi, he walks you how to get this up and running on your local development setup. 

**Quarkus vs Java**

[AWS Lambda: Quarkus vs Plain Java](https://dev.to/josemyduarte/aws-lambda-quarkus-vs-plain-java-25l9) - this post from Josemy Duarte is a quick introduction for java developers looking at options for modern applications in Java. Josemy walks you through what Quarkus is and then shares his findings from some experimentation he understood. Learn and be Curious...

### AWS updates

**High performance Machine Learning workloads on Kubernetes**

[Using high-performance storage for machine learning workloads on Kubernetes](https://aws.amazon.com/blogs/storage/using-high-performance-persistent-storage-for-machine-learning-workloads-on-kubernetes/) - this post from Shrinath Kurdekar shows you how to use an Amazon FSx for Lustre persistent file system with Amazon SageMaker to train a machine learning model on an Amazon EKS cluster. 

![architecture](https://d2908q01vomqb2.cloudfront.net/e1822db470e60d090affd0956d743cb0e7cdf113/2020/07/02/This-diagram-shows-the-high-level-architecture-for-the-use-case-covered-in-the-GitHub-tutorial.png)

Shirnath has provided a tutorial you can access via GitHub, which you can get [here](https://github.com/aws-samples/amazon-fsx-tutorial/tree/master/lustre/SageMaker-training-using-FSxL-on-EKS).

**Porting assistance for .NET**

[Porting Assistant for .NET](https://aws.amazon.com/blogs/aws/announcing-the-porting-assistant-for-net/) - in this post from Steve Roberts, walks you through a new free tool available to customers that helps you migrate your .NET applications onto open source .NET Core. This is an analysis tool that scans .NET Framework applications and generates a .NET Core compatibility assessment, helping you port your applications to Linux faster.

![net assistance](https://d2908q01vomqb2.cloudfront.net/da4b9237bacccdf19c0760cab7aec4a8359010b0/2020/06/29/portassistant_assessment_dependencies.png)

Porting some .NET Framework applications to .NET Core can be difficult as you need to spend time identifying the dependencies and APIs that are incompatible with .NET Core, and estimating the level of effort involved. Porting Assistant for .NET scans .NET Framework applications to identify incompatibilities with .NET Core, finds known replacements, and generates detailed compatibility assessment reports. This reduces the manual effort involved in modernizing your applications to Linux.

[You can check out this post](https://visualstudiomagazine.com/articles/2020/07/02/aws-net-porting-tool.aspx) in Visual Studio Magazine from David Ramel if you want another perspective.

**Elastic Beanstalk adn .NET Core**

[Environment Variables with .NET Core and Elastic Beanstalk](https://aws.amazon.com/blogs/developer/environment-variables-with-net-core-and-elastic-beanstalk/) - another post from Norm Johanson on .NET Core and Elastic Beanstalk, this time though it is to share how support for environment variables across both the Linux and Windows .NET Core Beanstalk platforms is now available. This means using the latest platform version for either the Linux or Windows, you can set environment variables on the Beanstalk environment. The applications that have been deployed to the environment will be able to access the new values without redeploying the application.

**redBus: Building a Data Plaform**

[redBus: Building a Data Platform with AWS & Apache Software Foundation](https://aws.amazon.com/blogs/startups/redbus-building-a-data-platform-with-aws-apache-software-foundation/) is a guest post by Dweep Sharma, Data Engineering, redBus. redBus, India’s largest online bus ticketing platform, uses AWS and open source technologies for its data platform, and in this post, he shares how they built this.

![data platform](https://d2908q01vomqb2.cloudfront.net/cb4e5208b4cd87268b208e49452ed6e89a68e0b8/2020/06/30/Redbus-2-architecture-diagram.png)

**Amazon SageMaker and XGBoost**

[Introducing the open-source Amazon SageMaker XGBoost algorithm container](https://aws.amazon.com/blogs/machine-learning/introducing-the-open-source-amazon-sagemaker-xgboost-algorithm-container/) - in this collaboration with Rahul Iyer, Eric Kim, Laurence Rouesnel, and Rocky Zhang, you will get to know more about the open source XGBoost algorithm container that you can use within Amazon SageMaker, and they share a few use cases to get you going. The post covers how to make use of Spot instances, using script mode and training with Parquet files.

**Automatic testing of Robotics Applications**

[Introduction to Automatic Testing of Robotics Applications](https://aws.amazon.com/blogs/robotics/automatic-testing-robotics/) - this post from Pulkit Kapur talks about the different functional testing operations, especially the scenario-based simulation testing of robotics applications and you can achieve this with AWS RoboMaker.

![robomaker](https://d2908q01vomqb2.cloudfront.net/a9334987ece78b6fe8bf130ef00b74847c1d3da6/2020/06/30/testing-gif.gif)

**Live events solution with Amazon Chime SDK**

[How to deploy a live events solution built with the Amazon Chime SDK](https://aws.amazon.com/blogs/opensource/how-to-deploy-a-live-events-solution-built-with-the-amazon-chime-sdk/) - in this tutorial,  Hana Thier walks you through how to deploy an interactive live events solution where speakers can present to a large pre-selected audience, and moderators can screen attendees to participate in the broadcast. This interactive live events solution, built with the Amazon Chime SDK, and this project has been open sourced and you can find the source code at the GitHub repository [here](https://github.com/aws-samples/amazon-chime-live-events).

![chime](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2020/06/23/thier-fig.1.gif)

**AWS Machine Learning and Open Source**

In this webinar, Alex Smola introduces AWS Machine Learning and then dives deep into the open source tools and projects (from minute 7). Well worth checking out the whole video so you can see how open source fits into the AWS Machine Learning landscape. This is a deep dive, so data scientists and machine learning specialists will feel at home, but if you are just entering this field don't worry, Alex does a great job of explaining everything and you will get a good grounding in some of these advanced topics.

{% youtube 0Z52MU1PYrs %}

There is a very good reason to watch this video, at around 28m Alex provides an update that a lot of customers had been asking for. No spoilers, check out the video to find out what that is.

**Cisco, Amazon SageMaker and KubeFlow**

[Cisco uses Amazon SageMaker and Kubeflow to create a hybrid machine learning workflow](https://aws.amazon.com/blogs/machine-learning/cisco-uses-amazon-sagemaker-and-kubeflow-to-create-a-hybrid-machine-learning-workflow/) - this guest post from members of Cisco's AI/ML best practices team (Elvira Dzhuraeva, Amit Saha, and Debo Dutta) shares how they combine open source machine learning tools like Kubeflow, MLPerf and MLCommons with Amazon SageMaker to create solutions and reference architectures that provide hybrid capabilities, reduce the complexity for their data scientists and ensure they comply with the strictest standards and policies to safeguard data privacy.

![hybrid](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2020/06/30/cisco-sagemaker-1.jpg)


**Making container scanning Trivy(al)**

[How to build a CI/CD pipeline for container vulnerability scanning with Trivy and AWS Security Hub](https://aws.amazon.com/blogs/security/how-to-build-ci-cd-pipeline-container-vulnerability-scanning-trivy-and-aws-security-hub/) - in this post from Amrish Thakkar, you will walk through how to build a continuous integration and continuous delivery (CI/CD) pipeline using AWS Developer Tools, and use Aqua Security‘s open source container vulnerability scanner, Trivy, to scan Docker images for critical vulnerabilities.

![Trivy](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2020/06/26/CICD-Container-Scannning-Figure-1s.png)

### Quick updates

**AWS AppSync introduces new 12xlarge instance for server-side API caching**

AWS AppSync is a managed GraphQL service that simplifies application development by letting you create a flexible API to securely access, manipulate, and combine data from one or more data sources. With AppSync, you can build scalable applications on a range of data sources such as NoSQL data stores, relational databases, HTTP APIs, and any custom data sources with AWS Lambda.  Now you can use a new 12xlarge instance with 317.77Gb of memory to cache GraphQL calls to AWS AppSync APIs. AWS AppSync’s managed server-side data caching capabilities reduce the need to directly access data sources by making data available in a high speed in-memory cache, improving performance and decreasing latency.

**Active MQ**

You can now launch Apache ActiveMQ 5.15.12 brokers on Amazon MQ. This patch update to ActiveMQ contains several fixes and improvements compared to the previously supported version, ActiveMQ 5.15.10. Amazon MQ is a managed message broker service for Apache ActiveMQ that makes it easy to set up and operate message brokers in the cloud. Message brokers allow different software systems–often using different programming languages, and on different platforms–to communicate and exchange information. With Amazon MQ, you can use industry standard APIs and protocols for messaging, including JMS, NMS, AMQP, STOMP, MQTT, and WebSocket. You can easily move from any message broker that uses these standards to Amazon MQ because you don’t have to rewrite any messaging code in your applications.

Also, check out this [great short video](https://www.linkedin.com/feed/update/urn:li:activity:6683824093004914688/) from Liz Percak Dennett on what Amazon MQ is.

**AWS System Manager: Linux platforms**

Patch Manager, a capability of AWS Systems Manager, now allows you to deploy patches automatically to instances running Red Hat Enterprise Linux 7.8, 8.0, 8.1, and 8.2; CentOS 7.8, 8.0, and 8.1; and Oracle Linux 7.5, 7.7 and 7.8. This support provides more patching options for your mixed Linux environments. 

Patch Manager can automatically patch Linux instances running Red Hat Enterprise Linux (RHEL), Ubuntu Server, Amazon Linux, Amazon Linux 2, CentOS, Oracle Linux, Debian, and SUSE Linux Enterprise Server (SLES).

**Kernel Live Patching for Amazon Linux 2 is GA**

Kernel Live Patching enables customers to patch security vulnerabilities and bugs in the Linux kernel without reboots or disruptions to running applications. As a result, Amazon Linux 2 customers benefit from improved service availability and a better security posture. This feature is now generally available to all Amazon Linux 2 customers, free of charge.

### In other news

**Principals and tenets to guide your organisation**

Whilst not related to open source specifically, I wanted to share this post from Luca Bianchi on [A Practical application of Amazon Leadership Principals](https://medium.com/@aletheia/a-practical-application-of-amazon-leadership-principles-1aad8ce26a0d). In this post Luca shares how they are using these as a baseline for codifying the culture they want within their startup, Neosperience.

**.NET Foundation updates for June/July**

[.NET Foundation June/July 2020 Update](https://dotnetfoundation.org/blog/2020/06/17/blog/posts/net-foundation-june-july-2020-update) is a monthly update from the .NET Foundation covering some general news, foundation updates and a call for speakers who want to present .NET on AWS on a number of different topics.


### Share your open source projects 

Do you have some content you want to share with a broader audience? We are always looking for guest content for the AWS Open blog. Please get in touch (via comments below) and I would love to speak with you about what you are doing in open source. We are always looking for interesting new content.

The best submissions will get some AWS Credit codes as a thank you.


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)