---
title: 'AWS open source news and updates #57'
date: '2021-02-22'
tags : [ oss-newsletter ]
---
## February 22nd, 2021 - Instalment #57

Newsletter #57.

This week we have another great selection of content to share with you. Starting off with a look at open source at AWS, which is a must read this week, we meander through a look at a write up of the open source technology stack that supported Fossdem a few weeks ago. Then it is off to the usual round up of latest open source projects, blog posts from the community and AWS as well as a look at some quick updates, videos and more. We also have a job working AWS SDK team, so if you love Rust why not take a look.

**Open source at AWS**

In this post in The New Stack, [The Open Source Strategy of Amazon Web Services](https://aws-oss.beachgeek.co.uk/79), Richard MacManus shares some thoughts on how AWS think about and contribute to open source. A nice piece with some great data points.

**Fossdem**

A few weeks ago Fossdem ran virtually, and there were a number of great sessions over the weekend. It was important to get the technology right given the numbers attending these remotely, and certainly from the sessions I attended, it was a great success. In this blog post, [How we hosted FOSDEM 2021 on Matrix](https://aws-oss.beachgeek.co.uk/7a) Matthew Hodgson shares how Matrix, an open source project which defines an open standard protocol for decentralised communication, was used to deliver a virtual Fossdem. Some really great data points, a look at the architecture and open source tools used, this is a fantastic write up which I urge you to check out to see how you can use open source tools to potentially run your own virtual events.

![fossdem](https://matrix.org/blog/img/upload_06b59bc2b2d518ffe616020e1fe5bee8.png)

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Pablo Redondo Sanchez, Pranshu Tople, Jiahang Zhong, Karen Xu, Mark Seufert, Jeff Wright, Kowshik Nagarajaan, Anush Krishnamurthy, Hugo Shi, Stephanie Kirmer, Kinnar Sen, Dan Kelly, Ram Vittal and Sireesha Muppala, Paul Roberts, Josh Izaac, Eric Kessler, William Cannady, Atiek Arian, Dominic Searle, Efe Selcuk, Apurup Chevuru, Michael Hausenblas, Martin Beeby, Adi Singh, Karsten Ploesser, Igor Alekseev, Scott Anderson, Guy Eisenkot, James Beswick, Richard MacManus, Matthew Hodgson, Christopher Catt, Tarık Yurt, Jochen Ullrich, Jon Grim, Prem Ranga, Jana Gnanachandran, Mona Mona, Nathalie Rauschmayr,  Rohit Yadav, Daniel Pinheiro, Johny Duval, and Shawn Sachdev.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

**introspector**

[introspector](https://aws-oss.beachgeek.co.uk/7d) this project from Gold Fig Labs is a tool and schema for importing cloud infrastructure configuration. The goal is to unlock the expressive power of SQL and relational databases to ask questions about what is currently deployed in your cloud.

**infracost**

[infracost](https://aws-oss.beachgeek.co.uk/7l) this project shows cloud cost estimates for Terraform projects. It helps developers, devops and others to quickly see the cost breakdown and compare different options upfront.

**aws-pca-issuer**

[aws-pca-issuer](https://aws-oss.beachgeek.co.uk/7e) this project from Jochen Ullrich's is an addon for cert-manager that issues certificates using the AWS Certificate Manager. cert-manager is a Kubernetes add-on to automate the management and issuance of TLS certificates from various issuing sources. It will ensure certificates are valid and up to date periodically, and attempt to renew certificates at an appropriate time before expiry. 

**roll-with-me**

[roll-with-me](https://aws-oss.beachgeek.co.uk/7f) this is a fun project from Jon Grim that I wish I had had during the days I used to do role playing (D&D, MERP and Judge Dredd if you were asking!). The project provides digital tools for playing roleplaying games online, with a sample demo you can try.

**reweb**

[reweb](https://aws-oss.beachgeek.co.uk/7g) is an interesting project from apparentorder that as the README.md says "enables classic web applications to run on AWS Lambda.". Apart from answering the "Why" and going on to share some examples, I will be interested to know how folks get on with this project.

**tecli**

[tecli](https://aws-oss.beachgeek.co.uk/7h) is an open source tool from awslabs that provides a command line interface for Terraform Enterprise/Cloud. In a world where everything is Terraform, teams use Terraform Cloud API to manage their workloads. TECLI increases teams productivity by facilitating such interaction and by providing easy commands that can be executed on a terminal or on CI/CD systems.

### Community open source posts

**Apache Spark**

[Run Spark Applications on AWS Fargate](https://aws-oss.beachgeek.co.uk/7o) this post from DataChef walks you through how you can run your Spark applications on AWS Fargate as a single node task. Aside from answering the question "why" and then exploring those use cases, they walk you through an example and provide source code too. Always good to have more choice, so whilst you will typically run your Spark applications on clusters, for those times when that is overkill, this might make a good alternative.

**Terraform**

[Terraform to manage application lifecycle](https://aws-oss.beachgeek.co.uk/7c) Tarık Yurt with a write up of lesson learned migrating and using Terraform as part of how they provision and deploy AWS resources.

**AWS SDKs**

[Jest: Mocking With AWS SDK V3](https://aws-oss.beachgeek.co.uk/7b) Christopher Catt with a useful post for folks using the v3 update to the AWS Javascript SDK. As part of the new V3 modular approach, it became less clear how developers might want to properly mock these new modules. Read this post and Chris will show you one way that makes mocking @aws-sdk client libraries a breeze.

**ec2instances.info**

ec2instances.info is an open source project that allows you to compare EC2 instance metrics and pricing on Amazon's site. Last week, in the post [Vantage has acquired ec2instances.info](https://aws-oss.beachgeek.co.uk/78) Vantage shared news about a change of home for this project and try and answer any questions you might have if you were using this project.

**Pupeteer**

[Serverless browser automation with AWS Lambda and Puppeteer](https://aws-oss.beachgeek.co.uk/77) AWS's very own James Beswick writes how you can use an open source npm module called Puppeteer to deploy browser automation tasks in AWS Lambda, allowing you to use the power and flexibility of AWS Lambda to schedule, be triggered on an event, and scale as needed the use of browser based automation tasks in a way that is cost effective. Really nice post.

**Cloud Drift Detection**

[Cloud Drift Detection: How to Resolve Out-of-State Changes](https://aws-oss.beachgeek.co.uk/75) a few weeks ago I shared news about the project, [#53](https://aws-oss.beachgeek.co.uk/76), so it was great last week to see this nice post from  Guy Eisenkot in TheNewStack. Understanding what is drift, knowing the risks, being able to detect drift and then how you respond are all topics Guy covers. Make sure you check this out as these are some really important concepts that are foundational when it comes to how you move to a more automated future.

**Parliament**

[Steampipe ❤ Parliament](https://aws-oss.beachgeek.co.uk/7m) this post from Steampipe  shows how they were able to build on top of Parliament. Parliament is an open-source project from Duo Labs that is designed to automate the evaluation of IAM policies. Steampipe ended up using SQL to query AWS Identity and Access Management (IAM), which helped them find new ways to assess and analyse our IAM risk

### AWS open source posts

**AWS App Mesh**

In the blog post, [Using mTLS with SPIFFE/SPIRE in AWS App Mesh on Amazon EKS](https://aws-oss.beachgeek.co.uk/70) Efe Selcuk, Apurup Chevuru and Michael Hausenblas team up to share you how the mutual TLS (mTLS) feature in AWS App Mesh works. This should be considered mandatory reading given that a) security is always job zero, and b) the post is nicely written and provides a great walkthrough you can try for yourself.

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2021/02/15/mtls-appmeshgraffle-1024x137.png)

**OpenTelemetry**

[Building a prototype for the Logging API and SDK for the OpenTelemetry C++ library](https://aws-oss.beachgeek.co.uk/6s) Karen Xu and Mark Seufert, intern engineers on the open source observability team describe their design and implementation of an open source prototype Logging API and SDK for the OpenTelemetry C++ library. This library allows users to write and collect logs from their distributed and instrumented applications. 

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/02/08/alolitas_Prototype-Logging-API-SDK-OpenTelemetry_f2.png)

**Elasticsearch**

[Getting started with Trace Analytics in Amazon Elasticsearch Service](https://aws-oss.beachgeek.co.uk/6t) Jeff Wright, Kowshik Nagarajaan, and Anush Krishnamurthy write about some new capabilities available within Elasticsearch, specifically aimed at helping operational teams  to troubleshoot performance and availability issues in their distributed applications. These feature provides a mechanism to ingest OpenTelemetry-standard trace data to be visualised and explored in Kibana.

![arch](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2021/02/16/BDB-1337-1.jpg)

**Flutter**

[Amplify Flutter is Now Generally Available: Build Beautiful Cross-Platform Apps](https://aws-oss.beachgeek.co.uk/72) nice post from Martin Beeby announcing the general availability of Amplify Flutter, which brings together AWS Amplify and Flutter, to help customers who have invested in the Flutter ecosystem and now want to take advantage of the power of AWS.

**AWS CDK**

[Process AWS Storage Gateway file upload notifications with AWS CDK](https://aws-oss.beachgeek.co.uk/6z) Atiek Arian and Dominic Searle provide a sample use case of how you can use the open source project AWS CDK, to build and deploy your entire application. Building from a previous post linked in this article, this is a very nicely written and clear example of how you can use AWS CDK.

![arch](https://d2908q01vomqb2.cloudfront.net/e1822db470e60d090affd0956d743cb0e7cdf113/2021/02/12/AWS-CDK-Application-AWS-Storage-Gateway-file-upload-notification-processing-Data-Vaulting-CDK-Stack-Architecture.png)

**Dask**

A couple of posts this week covering Dask, an open source library for parallel computing written in Python. Dask is a library composed of two parts. The first is a task scheduling component for building dependency graphs and scheduling tasks, and  second, it includes the distributed data structures with APIs similar to Pandas Dataframes or NumPy arrays. Dask can scale from a single node and scale to thousand node clusters.

In the first blog post, [Computer Vision at Scale with Dask and PyTorch on Amazon EC2 Spot Instances](https://aws-oss.beachgeek.co.uk/6u) Hugo Shi (Co-Founder and CTO at Saturn), Stephanie Kirmer, Sr. Data Scientist at Saturn as well as Kinnar Sen and  Dan Kelly from AWS explain how Saturn Cloud makes it easy for customers to satisfy the performance requirements of many data science and ML workloads while optimising price performance. The post walks through how to provision a cluster of On-Demand and Spot Instances to meet a set of required performance specifications, and compares this against other approaches.

![arch](https://d2908q01vomqb2.cloudfront.net/77de68daecd823babbb58edb1c8e14d7106e83bb/2021/02/12/Saturn-Python-EC2-Spot-2.png)

Next up we have Ram Vittal and Sireesha Muppala, [Machine learning on distributed Dask using Amazon SageMaker and AWS Fargate](https://aws-oss.beachgeek.co.uk/6v), which is a really nice follow on post where they demonstrate how to solve common ML problems such as exploratory data analysis on large datasets, preprocessing (such as one-hot encoding), and linear regression modelling using Fargate as the backend. They show you how to connect to a distributed Dask Fargate cluster from a SageMaker notebook, scale out Dask workers, and perform exploratory data analysis work using a sample data set along the way.

![arch](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2021/01/22/ML-1156-1.jpg)

**GluonTS**

[Training, debugging and running time series forecasting models with the GluonTS toolkit on Amazon SageMaker](https://aws-oss.beachgeek.co.uk/7j) Prem Ranga, Jana Gnanachandran, Mona Mona, and Nathalie Rauschmayr show you how to set up and run time series forecasting models at scale using Gluon Time Series (GluonTS) on Amazon SageMaker. GluonTS is a Python toolkit for probabilistic time series modelling, built around Apache MXNet. GluonTS provides utilities for loading and iterating over time series datasets, state-of-the-art models ready to be trained, and building blocks to define your own models and quickly experiment with different solutions.

**Robotics and IoT**

[Deploying ROS applications as Snaps with AWS IoT Greengrass 2.0](https://aws-oss.beachgeek.co.uk/74) my good friend Adi Singh has put together this really nice blog post that explores the recently announced release of AWS IoT Greengrass 2.0 that now some new options to package up your applications, why this improvement is useful for the robotics community, and walk through how you package and deploy Robot Operating System (ROS) applications to devices using AWS IoT Greengrass 2.0. Lots of great stuff, covering specifically how to use Snaps, the packaging tool developed by Canonical. This is on my weekend "to do" list. Great stuff Adi!

![robomaker](https://d2908q01vomqb2.cloudfront.net/a9334987ece78b6fe8bf130ef00b74847c1d3da6/2021/02/16/ROS-snaps-6.png) 

**MacOS workers on GitLab**

[Integrating EC2 macOS workers with EKS and GitLab](https://aws-oss.beachgeek.co.uk/6w) Paul Roberts walks through configuring GitLab with a mac1.metal Amazon EC2 instance using another open source infrastructure as code (IaC) automation tool, Pulumi, so that developers can build, test, and package their applications for all Apple platforms, such as macOS, iOS, iPadOS, tvOS, and watchOS.

**Babylon.js**

[How to: Hands-free interaction for AR/VR with Amazon Lex and Babylon.js](https://aws-oss.beachgeek.co.uk/6y) William Cannady takes a look at how you can use Babylon.js, and open source library that makes it easy get started working with 3D content, and use it in conjunction with AWS services to create immersive augmented/virtual reality applications. In this instance, by using voice/chat services that Amazon Lex provides.

![demo](https://d2mee59kmfnfxw.cloudfront.net/images/FinalProduct-min.gif)

**Amazon Athena Federated Queries**

[Create a custom data connector to Slack’s Member Analytics API in Amazon QuickSight with Amazon Athena Federated Query](https://aws-oss.beachgeek.co.uk/7n) Pablo Redondo Sanchez writes about how to use the Athena Query Federation SDK to write custom connectors and query any source accessible with a Java API, whether it is relational, non-relational, object, or a custom data endpoint. The Amazon Athena Query Federation SDK is an open source project that allows you to customise Amazon Athena with your own data sources and code. In this example, Pablo shows you how to create a custom connector to interact with Slack. Read on to find out what he does with it.

![graph](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2021/01/25/BDB-1121-2.jpg) 

**Apache Kafka**

[Amazon MSK backup for Archival, Replay, or Analytics](https://aws-oss.beachgeek.co.uk/7k) Rohit Yadav, Daniel Pinheiro, Johny Duval, and Shawn Sachdev with a post that shares an architecture to build a scalable, highly available real-time archival of Amazon MSK topics to long term storage in Amazon S3.

![archival](https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2021/02/18/Fig3-Replay.png)

### Case Studies

**SageMaker Clarify**

[How Zopa enhanced their fraud detection application using Amazon SageMaker Clarify](https://aws-oss.beachgeek.co.uk/7i) Jiahang Zhong, Head of Data Science at Zopa, writes how Zopa’s fraud detection system for loans use Amazon SageMaker Clarify to explain their ML models. Zopa is a UK-based digital bank and peer to peer (P2P) lender. In 2005, Zopa launched the first ever P2P lending company to give people access to simpler, better-value loans and investments. SageMaker Clarify is an open source project that helps you with bias detection and mitigation for datasets and models.

![arch](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2021/02/18/Zopa-Diagram.jpg)

### Partners

**PennyLane**

[Creating a bridge between machine learning and quantum computing with PennyLane](https://aws-oss.beachgeek.co.uk/6x) Josh Izaac (Quantum Software Team Lead at Xanadu) and Eric Kessler from AWS explain how the open source PennyLane project helps bridge the gap between the quantum computing and machine learning communities. The ambition here is that by integrating quantum computing into a rich scientific and machine learning ecosystem, the field of quantum computing can move forward.

![illustration](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/02/15/djnalley_PennyLane_f2.png) 

**Couchbase**

[Simplified Cloud Database Management Using Couchbase Cloud and AWS](https://aws-oss.beachgeek.co.uk/73) Scott Anderson, SVP Product Management and Business Operations at Couchbase describe how Couchbase Cloud leverages the underlying cloud resources. Couchbase NoSQL database administrators have been using Amazon Web Services (AWS) to host clusters for many years, including stand-alone servers, small or large clusters, and more recently Kubernetes-managed configurations. Couchbase Cloud takes aim at this challenge by providing customers access to sophisticated management software that allows them to co-manage their NoSQL cloud database directly inside their AWS-powered infrastructure.

![arch](https://d2908q01vomqb2.cloudfront.net/77de68daecd823babbb58edb1c8e14d7106e83bb/2021/02/08/Couchbase-Database-Management-1.png)

**Splunk**

[Monitoring Your Linux Workloads on AWS Graviton with Splunk Cloud](https://aws-oss.beachgeek.co.uk/71) Karsten Ploesser and Igor Alekseev share how you can use an AWS Partner solution (Splunk Cloud) with AWS Graviton2 instances using their Splunk Universal Forwarders to automate data collection and indexing of machine data.

![screen](https://d2908q01vomqb2.cloudfront.net/77de68daecd823babbb58edb1c8e14d7106e83bb/2021/02/11/Splunk-Linux-Graviton-7.1.png)

### Videos of the week

**Curiosity Rover**

To celebrate last weeks incredible MARS landing by the NASA Curiosity Rover, why not check out this video where Pranshu Tople simulates Curiosity using ROS.

{% youtube fq0DJSbwiZI %}

If you feel excited by that, why not check out the AWS RoboMaker workshop that was run last year with [JPL Open Source Rover challenge](https://aws-oss.beachgeek.co.uk/7m).

**Prometheus and Grafana**

Another great session from the Containers from the Couch team, together with guests Jaana Dogan, Alolita Sharma, and Imaya Jagannathan that show you how you can monitor container workloads with Amazon Managed Service for Prometheus and Grafana.

{% youtube Bh71xBQe92I %}


### Quick updates

**Kubernetes**

* Amazon EKS and EKS Distro now supports Kubernetes version 1.19. Kubernetes is rapidly evolving, with frequent feature releases and bug fixes. Highlights of the Kubernetes 1.19 release include Ingress API and Pod Topology Spread reaching stable status, EndpointSlices being enabled by default, and immutable Secrets and ConfigMaps. 

* Kubernetes version 1.15 will no longer be supported on May 3rd, 2021. [Read more here.](https://aws.amazon.com/about-aws/whats-new/2021/02/amazon-eks-supports-kubernetes-version-1-19/)


**Flutter**

Flutter support in AWS Amplify is now generally available (GA). Amplify is a set of tools and services that help frontend web and mobile developers build secure, scalable, full-stack applications. Flutter is an open-source UI software development kit created by Google for developing applications for Android and iOS from a single codebase. Amplify Flutter brings together Amplify and Flutter. It is designed for developers who have invested in the Flutter ecosystem and now want to take advantage of the power of AWS. You can use the Amplify Flutter libraries with Amplify-created backends, as well as existing AWS backends.

Compared to the initial Developer Preview, the GA release adds Data, API, and Auth capabilities. Amplify DataStore, now supported in Amplify Flutter, provides a local programming model that makes working with distributed, cross-user data as simple as working with local-only data. No additional code is required for offline and online scenarios. Amplify Flutter’s new API capabilities provide clients for making signed HTTP requests to both GraphQL and REST endpoints. Finally, today’s GA release adds support for authenticating app users using Hosted UI. Hosted UI is a customizable OAuth 2.0 flow that allows developers to launch a login screen without embedding the SDK for Cognito or a social provider—such as Facebook, Google, and Amazon—in your application.

**Elasticsearch**

Amazon Elasticsearch Service adds Trace Analytics, a new feature for distributed tracing that enables developers and IT operators to find and fix performance problems in distributed applications, leading to faster problem resolution times.  

Trace Analytics enables developers and IT Ops to troubleshoot performance and availability issues in their distributed applications, giving them end-to-end insights not possible with traditional methods of collecting logs and metrics from each component and service individually. By adding trace data to the existing log analytics capabilities of Amazon Elasticsearch Service, customers can use the same service to both isolate the source of performance problems and diagnose their root cause. Trace Analytics supports OpenTelemetry, a Cloud Native Computing Foundation (CNCF) project which provides a single set of APIs, libraries, agents, and collector services to capture distributed traces and metrics, enabling customers to leverage Trace Analytics without having to re-instrument they applications.  

Trace Analytics today supports collection of trace data from application libraries and SDK’s that are compatible with the open source OpenTelemetry Collector, including OpenTelemetry SDKs, X-Ray SDKs, Jaeger and Zipkin SDKs. Trace Analytics also integrates with AWS Distro for OpenTelemetry, which is a distribution of OpenTelemetry APIs, SDKs, and agents/collectors. It is a performant and secure distribution of OpenTelemetry supported by AWS. Customers can use AWS Distro for OpenTelemetry to collect traces and metrics for multiple monitoring solutions, including Amazon Elasticsearch Service and AWS X-Ray for trace data, and Amazon CloudWatch for metrics. For more information on configuring and using Trace Analytics, please see documentation.


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen).
