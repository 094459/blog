---

title: 'AWS open source news and updates #112'
date: '2022-05-13'
tags : [ oss-newsletter, aws open source, Amazon EMR, Kubernetes, Grafana, Prometheus, AWS AppSync, Delta Lake, Firecracker, OpenSearch, Istio, Steampipe, LAMP, MQTT, Kotlin, FreeRTOS]

---

## May 13th, 2022 - Instalment #112

Newsletter #112. 

Welcome to this weeks round up of AWS open source news. This weeks new projects features projects such as "aws-dataall" an open source framework for building a data marketplace, "backpack" a set of tools to help you work with the AWS Panorama devices, and we have other projects that help you automate DNS tasks, manage game servers, automate data ingestion, and more.

Topics featured in the weekly blog and technical articles roundup cover Amazon EMR, Grafana, Prometheus, AWS AppSync, Delta Lake, Firecracker, OpenSearch, Istio, Steampipe, LAMP, MQTT, and more. With KubeCon around the corner, check out the Kubernetes content and if you are going, pop along to the AWS booth and say hello. We have a number of the open source team attending, and it will be great to meet some of you.

This weeks videos feature a new open source project that I had not heard about before, that can help you migrate VMs to the cloud, as well as a walk through the Amazon EMR workshop. If you have been meaning to do that, now you have a great companion to work along to. 

We finish with the round up of events. Outside of KubeCon there are plenty of other events happening, so check them out. As always, if you have an event or meet-up you want me to include, drop me a line and I will add it to the list.

**Important end of support announcement**

Nothing lasts for ever they say, and so it is that in this post, 
[Announcing the end of support for Internet Explorer 11 in the AWS SDK for JavaScript (v3)](https://aws-oss.beachgeek.co.uk/1oq) Trivikram Kamat shares that starting October 1, 2022, AWS SDK For JavaScript (v3) will end support for Internet Explorer 11 (IE 11) and the browser artefacts published in our npm packages will no longer target ES5.

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: David Alvarez, Trivikram Kamat, Janos Tolgyesi, Michael Liendo, Dakota Riley, Dustin Whited, Elamaran Shanmugam, Gokul Chandra, Rama Ponnuswami, Johnny Chivers, Jaehyeon Kim, Sushain Cherivirala, and Matt Assay

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest open source projects

#### Community

**cfn-language-discussion**

[cfn-language-discussion](https://aws-oss.beachgeek.co.uk/1ox) this repo is a place to propose and discuss new language features for the CloudFormation template language. It is also a great place to request CloudFormation template language features, report CloudFormation template language bugs or any general discussion related to the CloudFormation template language. There are a number of open RFCs, so if you are a CloudFormation users, then have a look and provide your input and feedback.

**chico**

[chico](https://aws-oss.beachgeek.co.uk/1oy) if you need to register lots of DNS entries on Route53, take a look at this quick hack/script from David Alvarez that helps you to automate some of the tedious tasks.

#### Tools

**aws-dataall**

[aws-dataall](https://aws-oss.beachgeek.co.uk/1ot) this is a super interesting project, which is an open source development framework to help you build a data marketplace on AWS. data.all builds a modern data workspace that makes collaboration among diverse users (like business, analysts and engineers) easier, increasing efficiency and agility in data projects.

![screenshot of catalog](https://github.com/awslabs/aws-dataall/blob/main/documentation/userguide/docs/pictures/catalog/catalog.png?raw=true)

**backpack**

[backpack](https://aws-oss.beachgeek.co.uk/1oj) is a toolset that makes development for AWS Panorama hopefully more enjoyable. The repo contains a number of tools (AutoIdentity, Timepiece, Annotation , and SpyGlass) with details docs and examples to get you going. Janos Tolgyesi has put together this blog post, [Remote View your Computer Vision Models Running on AWS Panorama](https://aws-oss.beachgeek.co.uk/1ok) that dives deep into one of those tools, SpyGlass. This is a really nice set of tools, so nice work!

**amazon-qldb-ledger-load-java**

[amazon-qldb-ledger-load-java](https://aws-oss.beachgeek.co.uk/1ow) This is a framework for asynchronous loading of data into an Amazon QLDB ledger. The framework receives events from a delivery channel and writes them to the target ledger, performing idempotency checks and ensuring that document revisions are written in order. The project currently supports a number of deliver channels (Amazon SQS, Amazon SNS, Amazon Kinesis, Amazon MSK, and Amazon EventBridge)

![architecture for ingestion for eventbridge](https://github.com/awslabs/amazon-qldb-ledger-load-java/blob/main/img/eventbridge.png?raw=true)

#### Demos, Samples and Workshops

**personal-game-server-manager**

[personal-game-server-manager](https://aws-oss.beachgeek.co.uk/1o6) Hosting your own personal gaming server is increasingly common and this project makes it easy for you to host your own game server.  You can follow along in the blog post, [Hosting your own dedicated Valheim server in the cloud](https://aws-oss.beachgeek.co.uk/1o7), which uses this project to host the game Valheim.

![architecture of running your own game server](https://d2908q01vomqb2.cloudfront.net/91032ad7bbcb6cf72875e8e8207dcfba80173f7c/2022/05/09/HL-arch.drawio.png)

**lambda-edge-resizing-images-custom-origin**

[lambda-edge-resizing-images-custom-origin](https://aws-oss.beachgeek.co.uk/1ou) this is a nice example of how you can use AWS Lambda@Edge to resize images. You can resize the images and convert the image format by query parameters. This Lambda@Edge sample code using the custom origin as the original image source.

![archotecture of solution](https://github.com/aws-samples/lambda-edge-resizing-images-custom-origin/blob/main/images/image-resizing.png?raw=true)

**amazon-devops-guru-rds**

[amazon-devops-guru-rds](https://aws-oss.beachgeek.co.uk/1ov) Amazon DevOps Guru is a service powered by machine learning (ML), available for Amazon Relational Database Service (RDS) MySQL and Postgres to quickly detect, diagnose, and remediate a wide variety of database-related issues in Amazon RDS. This repository contains CloudFromation template, some scripts and guidance how to use these resources on your own for creating and exploring DevOps Guru insights.

### AWS and Community blog posts

**AWS AppSync**

Great post from Michael Liendo, who dives deep into Velocity Template Language (VTL) in his post, [The frontend engineers guide to VTL](https://aws-oss.beachgeek.co.uk/1oh). The post walks you through some of the core features of VTL, and how AWS AppSync uses it to provide low-latency responses while handling millions of connections. This weeks essential read.

![screen shot of appsync queries](https://cdn.hashnode.com/res/hashnode/image/upload/v1651860693313/t6ndBB8T1.png?auto=compress,format&format=webp)

**Kubernetes**

Dakota Riley and Dustin Whited from Aquia take a look at your options when it comes to threat detection for your Amazon EKS workloads in the blog post, [Threat Detection on EKS – Comparing Falco and GuardDuty For EKS Protection](https://aws-oss.beachgeek.co.uk/1of). The post looks at some commonalities and differences between Falco and recently added capabilities within GuardDuty, enabling threat detection.

Amazon EKS Anywhere is a deployment option for Amazon EKS that enables you to easily create and operate Kubernetes clusters on a customer-managed vSphere environment. Making sure that you are able to integrate these into your observability solution is the subject of this blog post, [Monitoring Amazon EKS Anywhere using Amazon Managed Service for Prometheus and Amazon Managed Grafana](https://aws-oss.beachgeek.co.uk/1op) a collaboration between Elamaran Shanmugam, Gokul Chandra, and Rama Ponnuswami. [hands on]

![solution overview for eks anywhere monitoring](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2022/05/10/grafana-1.jpg) 

Along similar lines we have Elamaran Shanmugam write [Monitor Istio on EKS using Amazon Managed Prometheus and Amazon Managed Grafana](https://aws-oss.beachgeek.co.uk/1or) where you will learn how you can configure an Amazon Elastic Kubernetes Service (Amazon EKS) cluster with Istio as a service mesh, Amazon Managed service for Prometheus, and Amazon Managed Grafana for monitoring your Istio Control and Data plane metrics. [hands on]

![solution architecture overview](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2022/04/29/741_1-1024x573.png)

**Firecracker**

I love how builders use open source software in so many different ways. A twitter thread last week showcased how one customer was leveraging Firecracker to improve the speed of their software builds. Check out the full post, 
[Fast builds, secure builds. Choose two](https://aws-oss.beachgeek.co.uk/1od) from Sushain Cherivirala on the Stripe engineering blog.

![architecture of stripe build with firecracker](https://images.ctfassets.net/fzn2n1nzq965/6lgPxekiZrH8cqyiMEs9ii/e5e335641ee62d8c9565e86b15853658/remote-builds-sad-path-diagram-3.png?w=1620&q=80&fm=webp)

Matt Asay also put together a very nice blog post, [Why your open-source project definitely should not be the next Kubernetes](https://aws-oss.beachgeek.co.uk/1og), pulling together some of the threads and sharing some other examples. Make sure you read it.

**Amazon EMR**

In the post, [Develop and Test Apache Spark Apps for EMR Locally Using Docker](https://aws-oss.beachgeek.co.uk/1ol), Jaehyeon Kim shares an approach in how you can create a Spark local development environment for Amazon EMR using Docker and/or VSCode. Grab a cup of your favourite drink and then walk through this deep dive. This is on my (ever growing!) to do list[hands on]

![screen shot showing local development](https://cevo.com.au/wp-content/uploads/2022/05/06-notification-01.png)

**Other posts worth checking out**

* [Introducing vended metrics for Amazon Managed Service for Prometheus](https://aws-oss.beachgeek.co.uk/1o8) you can now send usage metrics to Amazon CloudWatch
* [Instantly query AWS with SQL in CloudShell](https://aws-oss.beachgeek.co.uk/1oi) shares how you can quickly get the Steampipe CLI up and running in your AWS CloudShell [hands on]
* [Monitor AWS IoT connections in near-real time using MQTT LWT](https://aws-oss.beachgeek.co.uk/1on) dives deep into how to detect error and mitigate actions using Last Will and Testament (LWT) method for MQTT [hands on]
* [Create a more secure LAMP stack with AWS WAF (web application firewall)](https://aws-oss.beachgeek.co.uk/1os) is a great walk through in how to create a robust, modern LAMP stack [hands on]

![architecture for modern lamp](https://d2908q01vomqb2.cloudfront.net/b7eb6c689c037217079766fdb77c3bac3e51cb4c/2022/05/09/secure-lamp-stack-AWS-WAF-architecture-diagram-1.jpg)

**Case Studies**

* [Toyota Connected optimizes EMR costs and improves resiliency of batch jobs](https://aws-oss.beachgeek.co.uk/1o9) is great case study showing you how they orchestrate various analytical batch jobs using Apache Airflow
* [How Paytm modernized their data pipeline using Amazon EMR](https://aws-oss.beachgeek.co.uk/1om) see how Paytm, India’s leading payment platform, migrated their Apache Spark data pipeline to AWS

### Quick updates

**Kotlin**

The developer Preview of the Amplify Android library was announced earlier this week that has been rewritten for Kotlin. This initial release enables Android developers to add cloud-based app features, including Auth, Storage, DataStore, and APIs for their Kotlin-based Android projects. Developers will benefit from Kotlin-based language features like coroutines. This release also includes re-architected Auth (sign-up/sign-in), now completely written in Kotlin, which provides better debuggabilty and visibility into underlying state management. Finally, we have layered the new library on the new AWS SDK for Kotlin that was released as Developer Preview last year. This allows developers to use Amplify’s use case-centric APIs—like Auth and DataStore—and access the AWS SDK for Kotlin for a breadth of AWS service APIs.

**Apache Hive**

You can now use Amazon Athena to query views stored in your self-managed Apache Hive metastores. Hive views are defined using the Hive Query Language (HiveQL) which is not fully compatible with Athena's standard SQL. With this new capability, Athena automatically handles HiveQL syntax differences so you can query Hive views without changing your view definitions or maintaining a complex translation layer. 

A view is a logical table created using the results of a query that executes against a physical table each time the view is referenced. Views are commonly used to focus, simplify, and optimise access to underlying data. They can provide users with an isolated subset of curated data, combine disparate tables with optimised JOIN operations, or hide the complexities of data partitioning. With Athena’s new Hive views support, you can bring these same benefits and use cases that you’ve developed for your Hadoop users directly to your Athena users. Views can be listed and examined from the Athena console to provide your analysts with a more complete picture of your Hive metastore. Views can be queried using the Athena drivers, API, or console and are available in all supported regions.

**NodeJS**

You can now develop AWS Lambda functions using the Node.js 16 runtime. Read the post, [Node.js 16.x runtime now available in AWS Lambda](https://aws-oss.beachgeek.co.uk/1oo) from Dan Fox for the full details.

**OpenSearch**

Charlotte Henkle writes about the upcoming OpenSearch 2.0.0 in the post, [OpenSearch 2.0.0 release candidate is available and ready for testing and feedback](https://aws-oss.beachgeek.co.uk/1oc)

**Delta Lake**

Check out the latest updates in Delta Lake 1.2 in the post, [Delta Lake 1.2 - More Speed, Efficiency and Extensibility Than Ever](https://aws-oss.beachgeek.co.uk/1ob). The post outlines and dives deep into some of the new updates, so if you are using Delta Lake, then this is worth while reading.

**Firecracker**

[v1.1.0 of Firecracker](https://aws-oss.beachgeek.co.uk/1oa) was released last week, with plenty of new features added as well as fixes and some changes. One of the key changes was that the Instance Metadata Service Version 2 (MmdsV2) is now Generally Available, and that MmdsV1 is now deprecated and will be removed in Firecracker v2.0.0.

**FreeRTOS**

Introducing an updated and more flexible AWS Device Qualification Program (DQP) for FreeRTOS that aligns with the modular structure of the latest FreeRTOS and Long Term Support (LTS) library releases. The AWS DQP for FreeRTOS allows microcontroller (MCU) vendors to verify their integration of FreeRTOS AWS IoT libraries running on a specific MCU-based development board against AWS's published best practices for AWS IoT Core connectivity, and against tests specified by the qualification program. Previously, to qualify their development boards, MCU vendors had to structure their projects around a fixed directory structure and repository. Now, MCU vendors have the flexibility to include only the FreeRTOS libraries directly relevant to their application, choose the project structure and repository that best use their toolchains, and run tests relevant to their board features. By using AWS IoT Device Tester for FreeRTOS, MCU vendors can run the mandatory tests specified by AWS DQP and validate their FreeRTOS ports. With this program, developers can more confidently enable connectivity for their designs knowing that the FreeRTOS ports have been validated for AWS IoT connectivity, interoperability, updateability, and improved security.


### Videos of the week

**Amazon EMR**

Johnny Chivers shares his years of experience working in big data to go through the Amazon EMR workshop and walk you through how to get starting using all those open source big data tools.

{{< youtube v9nk6mVxJDU >}}

**Xmigrate**

Xmigrate is an opensource cloud migration tool which helps in migrating servers from anywhere to AWS (and other locations). I had never heard of this tool before, so I have this video in my weekend viewing pile. In the video they will walk you through using this tool do do a migration to AWS. Can't wait to check it out.

{{< youtube mWhxrDV3j2Q >}}

### Events for your diary

Super excited about KubeCon next week. If you are going, pop by the AWS stand, we would love to meet you.

**KubeCon**
**May 16th-20th, Valencia Spain**

The Cloud Native Computing Foundation’s flagship conference gathers adopters and technologists from leading open source and cloud native communities in Valencia, Spain from 16 – 20 May 2022. I will be there with many of the open source team and other AWS colleagues, so if you are going, make sure you swing by the AWS Booth. Also, the After Dark party promises to be something else....stay tuned.

Find out more about the [event here](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/).

**SST 1.0 Conf
May 17, 9am PDT**

SST 1.0 Conf is the first-ever Serverless Stack (SST) conference! It's a free virtual event featuring talks from folks in the community. And a couple of us from the SST team will be speaking as well! It's a way for all of us to come together and share what we've learnt.

Take a look at the speaker line up and register, [via this link](https://aws-oss.beachgeek.co.uk/1oe).


**AWS User Group - Open Source**
**May 17th, Valencia**

I will be speaking to the local AWS user group on all things open source. From why it matters to business to how to get started as a developer (and why). Check out more details on the [meetup page here](https://aws-oss.beachgeek.co.uk/1nz). The location will be shared via Twitter, so sign up if you are around and come meet the local AWS community.


**GitOpsCon Europe**
**May 17th, Valencia Spain**

GitOpsCon Europe is designed to foster collaboration, discussion, and knowledge sharing on GitOps. This event is aimed at audiences that are new to GitOps as well as those currently using GitOps within their organisation. Get connected with others that are passionate about GitOps. Learn from practitioners about pitfalls to avoid, hurdles to jump, and how to adopt GitOps in your cloud native environment.

The event is vendor-neutral and is being organised by the CNCF GitOps Working Group. Topics include getting started with GitOps, scaling and managing GitOps, lessons learned from production deployments, technical sessions, and thought leadership.

Read more about this from the official page [here](https://events.linuxfoundation.org/gitopscon-europe/).

**CDK Day**
**May 26th - Virtual**

This is a community organised event about AWS CDK, cdktf, projen and cdk8s. This will be third year they run this event, and if the previous two are anything to go by, this will be essential viewing - live streamed via You Tube. Check out and register for the event over at their home page at [https://www.cdkday.com/](https://www.cdkday.com/)

**BOSC 2022**
**July 13-14, Madison, Wisconsin, USA**

The Bioinformatics Open Source Conference (BOSC) has been held annually since 2000, and this year AWS is proud to be a platinum sponsor for this event. BOSC covers all aspects of open source bioinformatics software and open science, including (but not limited to) these topics, Open Science and Reproducible Research, Open Biomedical Data, Citizen/Participatory Science, Standards and Interoperability, Data Science Workflows, Open Approaches to Translational Bioinformatics, Developer Tools and Libraries, Inclusion, and Outreach and Training. This is a hybrid event (in person/virtual) and you find out more by checking out the event page, [BOSC 2022](https://aws-oss.beachgeek.co.uk/1li)

**OpenSearch**
**Every Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting - Feb2022](https://aws-oss.beachgeek.co.uk/1az)

**OpenSearchCon 2022**
**Sept 21st, 2022 Seattle**

Come to the first annual OpenSearchCon!

This day-long conference will be packed with presenters who build and innovate with OpenSearch. It doesn’t matter if you’re just getting started on your OpenSearch journey, running giant clusters, or contributing tons of code; the event is for everyone. Join us to celebrate the progress and look into the future of the project. Admission is free, and registration will be open in the next few weeks. All you will need to do is sign up, and get to Seattle!

Check out the full details, including signing up and location, at the [meetup page here](https://aws-oss.beachgeek.co.uk/1n1).


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)