---
title: 'AWS open source newsletter #180'
date: '2023-11-20'
tags : [ oss-newsletter, aws open source, Ragna, ezsmdeploy, SnapStart, GraalVM, Amazon Corretto, Amazon EMR, Apache Airflow, LangChain, AWS Copilot, Karpenter, MWAA, Grafana, Prometheus, Amazon EKS, Kubernetes, Apache Flink,  Apache Kafka, Avro, Apache Cassandra, Apache Spark, Red Hat Linux, Amazon Linux 2023, NodeJS, AWS Amplify, Redis, MySQL, PostgreSQL, eksctl, MapLibre, Overture Maps ]
---

## November 20th, 2023 - Instalment #180

Welcome to #180 of the AWS open source newsletter, the place for all your AWS and open source needs. As we ramp up to re:Invent, it is good to see that pre:Invent is giving us plenty of open source goodies. In this weeks newsletter, we have some of those in the way of new projects such as **res** and **aws-iatk**, but we also have lots of really great content too. In this edition, we have a curated set of observability content which I think you will really enjoy, as well as featuring posts that cover projects like Ragna, ezsmdeploy, SnapStart, GraalVM, Amazon Corretto, Amazon EMR, Apache Airflow, LangChain, AWS Copilot, Karpenter, Grafana, Prometheus, Kubernetes, Apache Flink,  Apache Kafka, Avro, Apache Cassandra, Apache Spark, AWS Amplify, Redis, MySQL, PostgreSQL, eksctl, MapLibre, Overture Maps, and more! As always, do not skip the end, where videos and events await your gaze.

Speaking of events, I am heading to Vilnius later this week to speak at Big Data Europe. I have a couple of sessions related to Apache Airflow, so if you are going to be attending get in touch, would love to meet up. Before driving into the newsletter, make sure you check the following launch we did last week which I was super excited about.

**Open source security**

I was very happy to see two new important resources launched this week. First up was news that we now have a dedicated page for open source security. You can view the page, [AWS Open Source Security](https://aws-oss.beachgeek.co.uk/3fx) which shares our approach to open source security together with some useful examples, data points, and supporting articles. If that was not enough, we also launched[ Open Source Cryptography](https://aws-oss.beachgeek.co.uk/3fy) that looks at some of the great open source innovations that AWS has produced, in the area of cryptography. Bookmark both of these resources and let us know what you think.
  
**Feedback**

Please please please take 1 minute to [complete this short survey](https://www.pulse.aws/promotion/10NT4XZQ). I have AWS credit codes for the first 50 as a thank you! 

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes: Haoween You, Joe Dahlquist, Chetan Patwal, Ali Alemi, Kiran Singh, Chirag Dave, Vinodkrishna Gopalan, Yoni Shalom, Sashi Varanasi, Roberto Luna Rojas, Steven Hancz, Elad Bernstein, Karthik Konaparthi, Erik Hanchett, Ashish Nanda,  Pascal Vogel,  Rakshith Rao, John Jackson, Rachel Leekin, Michael (Mike) Masaaud, Jihed Mselmi, Shreyas Subramanian, Ray Khorsandi, Hemanth Vemulapalli, Abhishek Gupta, Ruchi Mishra, Naga Gaddamu, Vadym Kazulkin, Harry at Data Smiles, Nowsath, Brendan Bouffler, Dan Fox, and Brian Krygsman.

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution. The projects mentioned here do not represent any formal recommendation or endorsement, I am just sharing for greater awareness as I think they look useful and interesting!*

#### Tools

**aws-iatk**

[aws-iatk](https://aws-oss.beachgeek.co.uk/3fc) AWS Integrated Application Test Kit (IATK), a new open-source test library that makes it easier for developers to create tests for cloud applications with increased speed and accuracy. With AWS IATK, developers can quickly write tests that exercise their code and its AWS integrations against an environment in the cloud, making it easier to catch mistakes early in the development process. IATK includes utilities to generate test events, validate event delivery and structure in Amazon EventBridge Event Bus, and assertions to validate call flow using AWS X-Ray traces. The [AWS IATK](https://aws-oss.beachgeek.co.uk/3g0) is available for Python3.8+. To help you get started, check out the supporting blog post from Dan Fox and Brian Krygsman, [Introducing the AWS Integrated Application Test Kit (IATK)](https://aws-oss.beachgeek.co.uk/3fz).

**res**

[res](https://aws-oss.beachgeek.co.uk/3f0) Research and Engineering Studio on AWS (RES) is an open source, easy-to-use web-based portal for administrators to create and manage secure cloud-based research and engineering environments. Using RES, scientists and engineers can visualise data and run interactive applications without the need for cloud expertise. With just a few clicks, scientists and engineers can create and connect to Windows and Linux virtual desktops that come with pre-installed applications, shared data, and collaboration tools they need. With RES, administrators can define permissions, set budgets, and monitor resource utilisation through a single web interface. RES virtual desktops are powered by Amazon EC2 instances and NICE DCV. RES is available at no additional charge. You pay only for the AWS resources needed to run your applications.

Dive deeper by reading [New: Research and Engineering Studio on AWS](https://aws-oss.beachgeek.co.uk/3f1), where Brendan Bouffler explains what RES is and how it works, and we’ll explain how to deploy it in your own AWS account, and get it ready for your users.

![screenshot of res in action](https://d2908q01vomqb2.cloudfront.net/e6c3dd630428fd54834172b8fd2735fed9416da4/2023/11/09/users-shot.png)

**aws-cdk-stack-builder-tool**

[aws-cdk-stack-builder-tool](https://aws-oss.beachgeek.co.uk/3g3) or AWS CDK Builder, is a browser-based tool designed to streamline bootstrapping of Infrastructure as Code (IaC) projects using the AWS Cloud Development Kit (CDK). Equipped with a dynamic visual designer and instant TypeScript code generation capabilities, the CDK Builder simplifies the construction and deployment of CDK projects. It stands as a resource for all CDK users, providing a platform to explore a broad array of CDK constructs. Very cool indeed, and you can deploy on AWS Cloud9, so that this project on my weekend to do list.

![demo screenshot of cdk stack builder](https://github.com/aws-samples/aws-cdk-stack-builder-tool/blob/main/assets/aws-cdk-builder.png?raw=true)

**terraform-aws-ecr-watch**

[terraform-aws-ecr-watch](https://aws-oss.beachgeek.co.uk/3f2) is a project out of the folks from Porsche, when they are not busy designing super fast cars, their engineers are busy creating useful open source tools for folks to use. This project is a Terraform module to configure an AWS ECR Usage Dashboard based on AWS CloudWatch log insight queries with data fetched from AWS CloudTrail.

![dashboard for terraform-aws-ecr-watch](https://raw.githubusercontent.com/porscheofficial/terraform-aws-ecr-watch/main/images/ecr-watch.png)

### Demos, Samples, Solutions and Workshops

**ragna**

[ragna](https://aws-oss.beachgeek.co.uk/3f3) this is a repo I put together to show you how you can add Amazon Bedrock models from Anthropic and Meta within the Ragna tool. I blogged last week about this [#179](https://dev.to/aws/unboxing-ragna-getting-hands-on-and-making-it-to-work-with-amazon-bedrock-7k3) but I have put together this repo that shows the actual code as I had received quite a few DMs, and as a bonus, I have also added the recently announced Llama2 13B model from Meta. To help with this, a new blog post, [Adding Amazon Bedrock Llama2 as an assistant in Ragna](https://dev.to/aws/adding-amazon-bedrock-llama2-as-an-assistant-in-ragna-pdl) will help you get this all up and running. There is also lots of useful info in the project README.

![screenshot of ragna ui with llama2](https://ricsuepublicresources.s3.eu-west-1.amazonaws.com/images/ragna_chat.png)

**aws-external-package-security**

[aws-external-package-security](https://aws-oss.beachgeek.co.uk/3g2) provides code to setup a solution that demonstrates how you can deploy AWS Code Services (e.g., AWS CodePipeline, AWS CodeBuild, Amazon CodeGuru Security, AWS CodeArtifact) to orchestrate secure access to external package repositories from an Amazon SageMaker data science environment configured with multi-layer security. The solution can also be expanded upon to account for general developer workflows, where developers use external package dependencies.

![architecture of aws external package security](https://raw.githubusercontent.com/aws-samples/aws-external-package-security/84d00d80a813794ea93166383b75a412865bf642/design/solution-overview.svg)

### AWS and Community blog posts

**Community round up**

Starting strongly in this weeks community round up we have AWS Community Builder Vadym Kazulkin who has put together a great read for those building modern Java apps and looking for ways to optimise how these work in his post, [Reducing Cold Starts on AWS Lambda with Java Runtime - Future Ideas about SnapStart, GraalVM and Co](https://aws-oss.beachgeek.co.uk/3fr). AWS Community Builder Nowsath has a quick handy post for those working with Amazon EMR, and who might be encountering the occasional error (after all, who create stuff that works first time.......yeah, exactly, no one!). Check out [Most common errors when setting up Amazon EMR](https://aws-oss.beachgeek.co.uk/3fs) the next time you are planning to work on Amazon EMR, you never know, it might help save you some time. I am also a big fan of including errors and issues in my blog posts. The amount of times that I have received messages to say they were searching for a fix, and came across my blog posts is enough validation for me. Next up we have Harry at Data Smiles with [Mastering Apache Airflow: My Essential Best Practices for Robust Data Orchestration](https://aws-oss.beachgeek.co.uk/3ft), covering good practices when working with Apache Airflow. A lot of sense in that post, so whether you are new or experienced, well worth checking out. 

To finish up, a few posts from some of my colleagues. First up we have Abhishek Gupta with [Use Amazon Bedrock and LangChain to build an application to chat with web pages](https://aws-oss.beachgeek.co.uk/3fu), who shows you how you can build and package a conversational application using AWS CDK, LangChain, and of course Go. Next up we have a longer tutorial from Hemanth Vemulapalli, [Break a Monolithic Application Into Microservices With AWS Migration Hub Refactor Spaces, AWS Copilot](https://aws-oss.beachgeek.co.uk/3fv) which walks you through the process of decomposing a monolith to micro services leveraging the strangler fig pattern using Refactor Spaces and AWS Copilot. To finish this weeks community round up, we have [How to launch Ray Clusters on AWS](https://aws-oss.beachgeek.co.uk/3fw) where Ruchi Mishra and Naga Gaddamu look at how you can get started with Ray on AWS. Ray is an open source general purpose universal library that allows you to do distributed computing and it offers you an ecosystem of native libraries to scale ML workloads.

**ezsmdeploy**

I first covered ezsmdeploy back in [#25](https://dev.to/aws/aws-open-source-news-and-updates-no-25-528b), an open source Python package to help easily deploy machine learning models and provide a variety of options such as passing one or more model files, automatic selection of instances, and autoscaling. In [Deploy Large Language Models Easily with the New ezsmdeploy Python SDK](https://aws-oss.beachgeek.co.uk/3fq), Shreyas Subramanian and Ray Khorsandi cover the new features of the ezsmdeploy 2.0 SDK, providing some code examples to demonstrate how to launch and interact with popular foundation models (FM). This is a really nice update, so make sure you check this out if you are exploring the world of generative AI and looking for open source tools to help make your life easier.
 
**Karpenter**

Karpenter is an open-source, high-performance Kubernetes cluster autoscaler that automatically provisions new nodes in response to un-schedulable pods. In the post, [Deliver Namespace as a Service multi tenancy for Amazon EKS using Karpenter](https://aws-oss.beachgeek.co.uk/3fk) Rachel Leekin, Michael (Mike) Masaaud, and Jihed Mselmi show how you can use Karpenter to provision node, scale up, and scale down the cluster per tenant without impacting other ones. [hands on]

**Apache Airflow**

For folks who have been using Managed Workflows for Apache Airflow (MWAA) for a while, you may be familiar with a long requested ask around how to deploy MWAA into more customised AWS VPC configurations. Specifying customer-managed endpoints is sometimes a requirements for customers to meet strict security policies by explicitly restricting VPC resource access to just those needed by their Amazon MWAA environments. It was great to read [Introducing shared VPC support on Amazon MWAA](https://aws-oss.beachgeek.co.uk/3fd), where John Jackson provides a hands on guide on how to automate environment creation with shared VPC support in Amazon MWAA. This gives you the ability to manage your own endpoints within your VPC, adding compatibility to shared, or otherwise restricted, VPCs.

**Observability**

Last week saw some great content covering all things related to observability, so here are my picks:

* [Extend your Amazon Managed Grafana experience with Grafana community plugins](https://aws-oss.beachgeek.co.uk/3fp) looks at a new self-service plugin management experience for Grafana community plugins, that enables you to unify data from a wider variety of data sources with visualisations tailored to analyse your unique datasets [hands on]
* [.NET Observability with OpenTelemetry – Part 1: Metrics using Amazon Managed Prometheus and Grafana](https://aws-oss.beachgeek.co.uk/3fl) is the first in a series, that looks at the implementation of OpenTelemetry in an ASP.NET website to capture application metrics [hands on]
* [Analyzing Amazon Lex conversation log data with Amazon Managed Grafana](https://aws-oss.beachgeek.co.uk/3fm) overes how to enable and use conversation logs to provide these insights and use Grafana to visualize and report on key metrics [hands on]

![dashboard for conversation analytics](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2023/11/08/Picture15.png)

* [Announcing Amazon CloudWatch Container Insights with Enhanced Observability for Amazon EKS on EC2](https://aws-oss.beachgeek.co.uk/3fn) has probably more graphs than I have ever seen in a post before, but looks at the various features introduced as part of the Amazon CloudWatch Container Insights with enhanced observability for Amazon Elastic Kubernetes Service - expect lots of graphs! [hands on]

![example graph](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2023/11/03/image7.png)

* [Monitoring MongoDB Atlas with AWS Managed Grafana and Amazon Managed Service for Prometheus](https://aws-oss.beachgeek.co.uk/3fo) describes how to use AWS Managed Service for Prometheus (AMP) and Amazon Managed Grafana (AMG) for monitoring MongoDB Atlas Clusters [hands on]

![overview of monitoring architecture for mongodb atlas](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2023/10/31/cloudops-1330_image001.png)

**Other posts and quick reads**

* [Implement Apache Flink near-online data enrichment patterns](https://aws-oss.beachgeek.co.uk/3fj) covers how you can implement data enrichment for near-online streaming events with Apache Flink and how you can optimize performance [hands on]

![overview of real time streaming flow](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2023/11/09/BDB-3563-overview-full.png)

* [Converting Apache Kafka events from Avro to JSON using EventBridge Pipes](https://aws-oss.beachgeek.co.uk/3fg) shows how to reliably consume, validate, convert, and send Avro events from Kafka to AWS and third-party services using EventBridge Pipes, allowing you to reduce custom deserialization logic in downstream services [hands on]

![architecutre of apache kafka conversion using eventbridge pipes](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2023/11/10/1968-1-1024x446.png)

* [Announcing frozen collections in Amazon Keyspaces](https://aws-oss.beachgeek.co.uk/3fe) looks at support for frozen collections in Amazon Keyspaces, and discusses various use cases for frozen collections and how to use the three different types of collections: MAP, LIST, and SET [hands on]
* [Simplifying data processing at Capitec with Amazon Redshift integration for Apache Spark](https://aws-oss.beachgeek.co.uk/3fh) is a case study on how the Capitec team successfully implemented the Apache Spark Amazon Redshift integration for Apache Spark to simplify their feature computation workflows [hands on]
* [Run Amazon EKS on RHEL Worker Nodes with IPVS Networking](https://aws-oss.beachgeek.co.uk/3ff) provides details of how to create Amazon EKS worker nodes that run on RHEL 8 and RHEL 9 Amazon EC2 instances and how to run your Amazon EKS clusters in IPVS networking mode [hands on]
* [Build trust and safety for generative AI applications with Amazon Comprehend and LangChain](https://aws-oss.beachgeek.co.uk/3fi) explores how you can use Amazon Comprehend ContentModerationChain to add trust and safety features to any LLM workflow, including Retrieval Augmented Generation (RAG) workflows implemented in LangChain [hands on]

![overview of workflow](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2023/11/07/ml-15084-image012-new.png)

### Quick updates
 
 **Amazon Linux 2023**
 
AWS Lambda now supports Amazon Linux 2023 as both a managed runtime and a container base image. This runtime has a significantly smaller deployment footprint than Amazon Linux 2 runtimes, and provides updated versions of common libraries such as glibc. The Amazon Linux 2023 runtime will also be used as the basis for future Lambda runtime releases, such as Node.js 20, Python 3.12, Java 21, and .NET 8. The Amazon Linux 2023 runtime provides an OS-only execution environment for Lambda functions. It is based on the AL2023 minimal container image release of AL2023. An OS-only Lambda environment is useful in three scenarios: when using languages which are compiled to native code, such as Go or Rust; when using third-party runtimes such as Bref for PHP; or when using custom runtimes. AWS will automatically apply updates and security patches to the managed runtime and container base image, as they become available.
 
 Rakshith Rao provides more details in the post, [Introducing the Amazon Linux 2023 runtime for AWS Lambda](https://aws-oss.beachgeek.co.uk/3fa).

 **NodeJS**
 
AWS Lambda now supports creating serverless applications using Node.js 20. Developers can use Node.js 20 as both a managed runtime and a container base image, and AWS will automatically apply updates to the managed runtime and base image as they become available. You can use Node.js 20 with Lambda@Edge, allowing you to customize low-latency content delivered through Amazon CloudFront. Powertools for AWS Lambda (TypeScript), a developer toolkit to implement serverless best practices and increase developer velocity, also supports Node.js 20.

The Lambda Node.js 20 runtime is built on the new Amazon Linux 2023 runtime, which is based on the AL2023 minimal container image. This provides a significantly smaller deployment footprint than earlier Amazon Linux 2-based runtimes, updated versions of common libraries such as glibc, and a new package manager. The Node.js 20 runtime also provides configurable certificate loading for faster cold starts, as well as supporting new Node.js 20 language features.

Read Pascal Vogel's post to find out more, [Node.js 20.x runtime now available in AWS Lambda](https://aws-oss.beachgeek.co.uk/3ez) [hands on]

**AWS Amplify**

AWS Amplify JavaScript Library v6 is now available. This includes reduced bundle sizes, richer TypeScript support, and integrations with Next.js server-side features. The AWS Amplify JavaScript Library enables frontend developers to connect their web and React Native apps to AWS cloud backends. In this release, Amplify JavaScript now offers richer TypeScript support enhancing developer productivity and reducing runtime errors. Additionally, Apps using this new release will be served with smaller bundle sizes. Amplify JavaScript v6 also introduces an integration with Next.js server-side features such as App Router, Middleware, API routes, and server functions. Developers can now build web apps leveraging improved TypeScript interfaces for a more intuitive development experience, including syntax highlighting, code completion, and type checking. We have improved app load times by reducing the bundle sizes served with Amplify JavaScript. This version also enables developers to use Amplify JavaScript in Next.js applications client-side or server-side, including in Middleware, API routes, and with the new App Router.

You might be wanting more info perhaps? Well, in which case why not dive into this post [Building fast Next.js apps using TypeScript and AWS Amplify JavaScript v6](https://aws-oss.beachgeek.co.uk/3f4), where Erik Hanchett and Ashish Nanda happily oblige.

![graph of java package improvements](https://d2908q01vomqb2.cloudfront.net/0a57cb53ba59c46fc4b692527a38a87c78d84028/2023/11/15/image-60.png)

**Redis**

Amazon ElastiCache for Redis version 7.1 is now generally available. This release contains performance improvements which enable workloads to drive higher throughput and lower operation latencies. ElastiCache customers can achieve over 1 million requests per second per node on r7g.4xlarge or larger. Amazon ElastiCache for Redis version 7.1 can achieve up to 100% more throughput and 50% lower P99 latency, compared to Elasticache for Redis version 7.0. Customers choose ElastiCache to power some of their most performance-sensitive, real-time applications, that require fast data access, fast response time and cost reduction. As they scale their applications, they have a growing need for high throughput, while keeping latency under 1ms per request. Today, customers can double the performance by upgrading from ElastiCache for Redis 7.0 to 7.1, and can scale to 500 millions of requests per second (RPS) with microsecond response time.

Also published this week on an unrelated note, was a great post to help guide you in sizing your Redis clusters using good practices. Elad Bernstein and Karthik Konaparthi are your hosts in [Best practices for sizing your Amazon ElastiCache for Redis clusters](https://aws-oss.beachgeek.co.uk/3f5).

If that was not enough, Sashi Varanasi, Roberto Luna Rojas, and Steven Hancz collaborated on [Optimize cost and boost performance of RDS for MySQL using Amazon ElastiCache for Redis](https://aws-oss.beachgeek.co.uk/3f6),  that very nicely details how you can optimise your relational database costs with in-memory caching using Amazon ElastiCache.

![overview of rds mysql and redis caching architecture](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2023/11/03/DBBLOG-3030-image003-1.png)

**MySQL**

Amazon RDS for MySQL now supports MySQL Innovation Release 8.1 in the Amazon RDS Database Preview Environment, allowing you to evaluate the latest Innovation Release on Amazon RDS for MySQL. You can deploy MySQL 8.1 in the Amazon RDS Database Preview Environment that has the benefits of a fully managed database, making it simpler to set up, operate, and monitor databases. MySQL 8.1 is the first Innovation Release from the MySQL community. MySQL Innovation releases include bug fixes, security patches, as well as new features. MySQL Innovation releases are supported by the community until the next major & minor release, whereas MySQL Long Term Support (LTS) Releases, such as MySQL 8.0, are supported by the community for up to eight years. 

**PostgreSQL**

Amazon RDS Proxy is a fully managed and a highly available database proxy for Amazon Aurora and RDS databases. RDS Proxy allows customers to gracefully scale applications by efficiently reusing database connections. For application using PostgreSQL Extended Query Protocol, RDS Proxy can now reuse database connections, resulting in efficient use of database resources.  Many applications and database drivers use PostgreSQL Extended Query Protocol for improved security and performance. Prior to this launch, when RDS Proxy encountered an extended query protocol message, it automatically “pinned” the database connection, which meant applications could not benefit from efficient database connection reuse. Now, RDS Proxy will continue to pool and share database connections when it detects an extended query protocol message, improving your database efficiency and application scalability. This functionality is available for existing as well as new RDS Proxy customers by default. 

It would be great if you could get more details right? Well, why not try [Amazon RDS Proxy multiplexing support for PostgreSQL Extended Query Protocol](https://aws-oss.beachgeek.co.uk/3f7), where Kiran Singh, Chirag Dave, Vinodkrishna Gopalan, and Yoni Shalom provide a details hands on guide on getting started with this.

![benchmark graph of using rds proxy with postgresql extended query protocol](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2023/11/09/DBBLOG-3615-image003.png)

**Apache Kafka**

Amazon Managed Streaming for Apache Kafka (Amazon MSK) Serverless now supports writes and reads from Kafka clients written in all programming languages. Administrators can simplify and standardise access control to Kafka resources using AWS Identity and Access Management (IAM). Amazon MSK’s IAM support is based on SASL/OAUTHBEARER, an open standard for authorisation and authentication. Amazon MSK Serverless is a cluster type for Amazon MSK that allows you to run Apache Kafka without having to manage and scale cluster capacity. MSK Serverless automatically provisions and scales compute and storage resources, so you can use Apache Kafka on demand. Developers can now build applications on Amazon MSK Serverless with minimal code changes using Amazon MSK’s open-sourced client helper libraries and code samples for popular languages, including Java, Python, Go, JavaScript, and .NET. Customers can also use standard IAM access controls such as temporary role-based credentials and precisely scoped permission policies more broadly with the multiple language support on Amazon MSK Serverless.

Check out [Amazon MSK Serverless now supports Kafka clients written in all programming languages](https://aws-oss.beachgeek.co.uk/3f8) where Ali Alemi provides a hands on guide to show how you can connect your applications to MSK Serverless with minimal code changes using the open-sourced client helper libraries and code samples for popular languages, including Java, Python, Go, JavaScript, and .NET. Ali also published [Amazon MSK IAM authentication now supports all programming languages](https://aws-oss.beachgeek.co.uk/3f9), so make sure you check that out too.

![apache kafka client access](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2023/11/08/bdb-3791-image001.png)

### Videos of the week

**eksctl - the CLI for EKS**

The topic for this Weaveworks Office Hours session is eksctl - The official CLI for Amazon EKS and the hosts for this session include Joe Dahlquist, VP Product Marketing, and Chetan Patwal, Senior Software Engineer.  Learn about eksctl, an open source tool that simplifies the creation and management of clusters on Amazon EKS. 

{{< youtube Cnxri7yllcU >}}

**Open Source with AWS Geospatial**

Haoween You from AWS Geospatial talks about recent open-source developments at AWS. This is a presentation during the Open Visualization Collaborator Summit 2023.

{{< youtube 7HNdIdpEuFk >}}

# Events for your diary

If you are planning any events in 2023, either virtual, in person, or hybrid, get in touch as I would love to share details of your event with readers. 

**Big Data Europe**
**21st-24th November, Online/Vilnius, Lithuania**

I will be speaking at the Big Data Europe event, talking about how you can shift left and apply modern developer approaches to manage your Apache Airflow workflows. This builds upon a lot of the other work I have done in this space, so am really looking forward to doing this talk.

Check out the[ event page ](https://labsoflatvia.com/en/events/big-data-conference-europe-2023)for registration details, as well as to check out all the other sessions - many of which feature open source projects and technologies.

**re:Invent**
**November, 27th-1st December, Las Vegas, USA**

The annual must attend conference for all AWS developers is back, and with another strong line up of open source sessions, chalk talks, builder sessions, workshops and more. There will be a super cool open source booth, with a line up of great demos - I have taken a sneak look and so make sure you check out the demo schedule on the booth.

Find out more by checking out the event page, [re:Invent 2023](https://reinvent.awsevents.com/)

The Amazon EKS team have published a post to help ensure that you do not miss the best Kubernetes related sessions. Go check it out at, [Amazon EKS and Kubernetes sessions at AWS re:Invent 2023](https://aws-oss.beachgeek.co.uk/3fb).

**Cortex**
**Every other Thursday, next one 16th February**

The Cortex community call happens every two weeks on Thursday, alternating at 1200 UTC and 1700 UTC. You can check out the GitHub project for more details, go to the [Community Meetings](https://aws-oss.beachgeek.co.uk/2h5) section. The community calls keep a rolling doc of previous meetings, so you can catch up on the previous discussions. Check the [Cortex Community Meetings Notes](https://aws-oss.beachgeek.co.uk/2h6) for more info.

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)

### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)