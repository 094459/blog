---
title: 'AWS open source news and updates #64'
date: '2021-04-19'
tags : [ oss-newsletter ]
---
## April, 19th, 2021 - Instalment #64

Newsletter #64. 

Another great selection of posts this week, starting off with the announcement last week of OpenSearch and OpenSearch Dashboards, the name of the community driven open source fork of Elasticsearch and Kibana. We have a great selection of community posts covering topics such as Apache Zeppelin, Rust, OpenJDK as well as an exciting new project called Lift to watch out for. Some great new open source projects including how to run Haskell on AWS Lambda, a nice project to make it easy to run EKS Distro on your desktop, so make sure you check those out. Finally we have some new events to put in your diary and then the usual round up of AWS open source related posts, a great podcast from Stelligent on the open source project mutato, and a video from the Seattle Java User Group taking a look at "A Journey into Latency Reduction" with Amazon Corretto. Plenty to keep you busy, but first, let's take a look at OpenSearch.

**OpenSearch**

The big news of last week was the post announcing OpenSearch and OpenSearch Dashboards, the name of the community-driven, open source fork of Elasticsearch and Kibana. In the post [Introducing OpenSearch](https://aws-oss.beachgeek.co.uk/e5), Carl Meadows, Jules Graybill, Kyle Davis, and Mehul Shah share details of this announcement, how we are working with the community and how the project is progressing.

> Our goal with the OpenSearch project is to make it easy for as many people and organizations as possible to use OpenSearch in their business, their products, and their projects.

Many business are supporting OpenSearch, and are as diverse as Red Hat, SAP, Capital One, and Logz.io. In the post, [logit.io's response to the Elasticsearch B.V SSPL Licensing Change](https://aws-oss.beachgeek.co.uk/eg) from Lee Smith explains how they are looking to incorporate OpenSearch and Open Search Dashboards as part of their Stack offering, just one of many business' that are looking to adopt OpenSearch.

Essential reading this week.

**Open Source Job of the week**

[Sr. Software Development Engineer - rust-vmm](https://aws-oss.beachgeek.co.uk/ec)

In this role, you will work on rust-vmm [1]. Rust-vmm is an open-source project that empowers the community to build custom Virtual Machine Monitors (VMMs) and hypervisors. It provides a set of virtualisation components that any project can use to quickly develop virtualisation solutions while focusing on the key differentiators of their product rather than re-implementing common components like KVM wrappers, virtio devices and other VMM libraries.The rust-vmm project is organised as a shared effort, shared ownership open-source project that includes (so far) contributors from Alibaba, AWS, Cloud Base, Crowdstrike, Intel, Google, Red Hat as well as individual contributors. It's components are already used in several projects such as Firecracker [2] and Cloud Hypervisor, [3] with more integrations under way.

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Shrirang Moghe, Brandon Leach, Chabane Refes, Chanwit Kaewkasi, Adrian Hornsby, Matthieu Napoli, Alolita Sharma, Imaya Kumar Jagannathan, Eitan Sela, Pahud Hsieh, Nima Kaviani, Vikrant Kahlir, Gaurav Dhamija, Sameer Kumar, Gopalakrishnan Subramanian, Shane Miller, Carl Meadows, Jules Graybill, Kyle Davis, Mehul Shah, Colm MacCárthaigh, Curtis Rissi, Mike Salvatore, Lee Smith, Abdullah T, Shane Miller, Wilhelm Wonigkeit, Andy Blackledge, Shubham Muneshwar, Paul Singman, Yishai Galatzer, Kelvin Nilsen, Toshal Dudhwala, Imaya Kumar Jagannathan, Carlos Perea and Luca Mazzaferro.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Book to watch out for

**Running Serverless Realtime GraphQL applications with AppSync**

Make sure you sign up to be notified when this new book from a collection of AWS Heroes, Aleksandar Simovic, Slobodan Stojanovic and Gojko Adzic. The book will cover  how to build and operate responsive, collaborative applications at scale with AWS AppSync and GraphQL.

The book will be available in Q3 2021, so [click on this link](https://aws-oss.beachgeek.co.uk/er) to keep notified when it has been launched.

### Latest from open source projects

**ekz**

[ekz](https://aws-oss.beachgeek.co.uk/et) Chanwit Kaewkasi's project is an opinionated Kubernetes distribution built using binaries from the AWS EKS Distro (EKS-D) and aims to be the easiest way to run EKS clusters on desktop (Linux/Mac and Windows).

**wai-handler-hal**

[wai-handler-hal](https://aws-oss.beachgeek.co.uk/eu) from the Technology team at Bellroy lets you run Haskell (wai) Applications on AWS Lambda. WAI is the Haskell version of WSGI (Python) or Rack (Ruby): the ecosystem's standard library that describes the interface between web servers and web applications.

**ssh-restricted**

[ssh-restricted](https://aws-oss.beachgeek.co.uk/es) from my colleague Adrian comes this handy AWS Config rule you can use that will check to see if any public ssh with a wide scope (i.e. 0.0.0.0/0) and then trigger a lambda function to remediate.

![arch](https://raw.githubusercontent.com/adhorn/ssh-restricted/master/arch.png)
 
**open-distro-for-elasticsearch-grafana-datasource**

[open-distro-for-elasticsearch-grafana-datasource](https://aws-oss.beachgeek.co.uk/eq) with the Open Distro for Elasticsearch plugin, you can run many types of simple or complex Elasticsearch queries to visualise logs or metrics stored in Elasticsearch. You can also annotate your graphs with log events stored in Elasticsearch. The Open Distro for Elasticsearch plugin is similar to the built-in Elasticsearch plugin, but with added support for AWS Sigv4 authentication and Piped Processing Language (PPL).

**cdk-cloudfront-plus**

[cdk-cloudfront-plus](https://aws-oss.beachgeek.co.uk/e1) Caught this [tweet](https://twitter.com/pahudnet/status/1381277549154639888) from my colleague Pahud Hsieh, which was a great collaboration between a number of AWS Community Builders to build some new AWS CDK constructs covering Lambda@Edge. This is a great effort, and the constructs cover everything from security, logging and the usual suspects when it comes to working with AWS CloudFront.

**eks-operators-airflow**

This is not ready yet, but a new issue was raised in the Apache Airflow project around creating a new operator to interact with Amazon EKS. You can view the current thinking in the issue, [Create EKS operators #8544](https://aws-oss.beachgeek.co.uk/e9) and the aim of this is to create a new Airflow operator that will:

> The proposed solution is a collection of Operators, and their underlying Hooks, which will be added to the Amazon AWS provider package. These Operators will handle creating and deleting clusters, as well as executing tasks using EKS Managed Node Groups.

**monkey**

[monkey](https://aws-oss.beachgeek.co.uk/ee) "The Infection Monkey" is an open source security tool for testing a your resiliency to perimeter breaches and internal server infection. It is not a new open source project, but the new update last week (version 1.10.0) provides a new zero trust assessment capabilities so you can conduct zero trust assessments of your AWS environments to help identify the potential gaps in an organisation’s AWS security posture that can put data at risk. Read more on this by checking out this blog post,[The Infection Monkey 1.10.0 — Go Bananas with New AWS Zero Trust Assessments](https://aws-oss.beachgeek.co.uk/ef) from Mike Salvatore.

![report](https://raw.githubusercontent.com/guardicore/monkey/develop/.github/zero-trust-report.png)

**aws-htc-grid**

[aws-htc-grid](https://aws-oss.beachgeek.co.uk/el) is an open source project that povides a reference architecture that can be used to build and adapt a modern High throughput compute solution using underlying AWS services, allowing users to submit high volumes of short and long running tasks and scaling environments dynamically. The project covers some suggested use cases and also where this may not be the best application. Check out the [documentation](https://aws-oss.beachgeek.co.uk/em) which provides clear guidance on how to set this up, the architecture and more.

 ![arch](https://raw.githubusercontent.com/awslabs/aws-htc-grid/main/docs/images/high_level_architecture.png)
 ![key](https://raw.githubusercontent.com/awslabs/aws-htc-grid/main/docs/images/job_submission_steps.png)

**tui**

[tui](https://aws-oss.beachgeek.co.uk/e7) this is a very new open source tool from Teem Ops that provides a nice gui tool that allows you to create generate aws cli commands to launch cloudformation templates that will build what you define. At the moment the support is  limited to EC2 and Autoscaling, but it is very early days for this project. Take a look and why not provide the project some feedback.

![demo](https://raw.githubusercontent.com/teemops/assets/master/teemops-scg-gif.mp4.gif)

### Community open source posts

**ArgoCD**

[Configuring ArgoCD on Amazon EKS](https://aws-oss.beachgeek.co.uk/ev) this post from Chabane Refes shows you how you can install, configure and manage ArgoCD on Amazon EKS. What is ArgoCD? [ArgoCD](https://argoproj.github.io/argo-cd/) is a declarative, GitOps continuous delivery tool for Kubernetes.

**Lift**

A new post from Matthieu Napoli, taking a look at Lift, a new open source project that simplifies deploying serverless applications. [Static websites on AWS — Designing Lift](https://aws-oss.beachgeek.co.uk/en). This new project is expected to have its first public beta around May time, and is intended to further simplify the deploying of serverless applications on AWS. The post outlines the options you have today, and how Lift is looking to simplify the deployment of static sites. Make sure you check out the GitHub repo and track it by watching it.

**OpenJDK**

[Java, Scala, Kotlin and TLS1.0 / TLS1.1](https://aws-oss.beachgeek.co.uk/ea) Colm MacCárthaigh shares news that you should pay attention to if you are using OpenJDK. From April 20th the open source OpenJDK project will be releasing new versions of JDK11, JDK8, and JDK7 that remove TLS1.0 and TLS1.1 from the default list of supported TLS/SSL protocols. Colm shares for customers using Amazon Corretto that "we’re going to keep TLS1.0 and TLS1.1 in the default set for a while longer, to avoid the breaking change". This post dives deep into the issues as to why these protocols are being removed, so if you have not already planned for this, read this and be ready. As the post adds:

> The OpenJDK change has been sign-posted in the OpenJDK crypto roadmap for quite a while, but breaking changes like this are still a big deal.

**s2n**

[Improving security in s2n](https://aws-oss.beachgeek.co.uk/eb) I missed this post from Colm MacCárthaigh's blog, shuffle sharding dot com, at the tail end of last year. The post goes into details as to the approach to reviewing security for this open source project, including the use of automation and techniques such as provable security, but crucially also the use of peer review and manual reviews. As a result, the project identified three low level issues which the posts goes on to detail.

**Rust**

As part of a series of posts from the Rust Foundation aimed at getting to know the board members, last week they published, [Introducing Shane Miller](https://aws-oss.beachgeek.co.uk/e4) where Shane introduces and shares her Rust story.

**CloudEvents**

CloudEvents is a vendor-neutral specification for defining the format of event data in a common format that is now a CNCF incubating project. In this post from Wilhelm Wonigkeit, [Direktiv: Transforming AWS EventBridge to CNCF CloudEvents](https://aws-oss.beachgeek.co.uk/ei) he shows you how you can use an open source project from vorteil.io called Direktiv, in combination with AWS services such as AWS Lambda to convert the AWS events from EventBridge into compatible CloudEvents.

![arch](https://miro.medium.com/max/2000/1*HCFDijNusuw5_jxGF2vGQQ.png)

This is a super interesting project, and if you are looking at event driven architectures then you need to check this post out.

**PartiQL**
 
PartiQL is an open sourced query language that provides SQL-compatible query access across multiple data stores containing structured data, semi-structured data, and nested data. It is widely used within Amazon and now available as part of many AWS services. In this post, [Using PartiQL to query AWS DynamoDb in Javascript](https://aws-oss.beachgeek.co.uk/eh) Abdullah T shares how this is now enabled in AWS DynamoDB to provide a SQL compatible query language to work with data in Amazon DynamoDB. This means you can write my queries in a more familiar way of SQL-like queries.

**Stackoscope**

[Introducing Stackoscope](https://aws-oss.beachgeek.co.uk/e6) this post from Lumigo announced a new capability from their open source tool (lumigo-cli) that allows you to analyse your serverless applications against a set of best practices, and produce a report which you can then review/action. The tool currently offers a number of recommendations (15) across a number of AWS services, so why not give this a try out on your dev or test environment to see what insights you might get?

![report](https://res.cloudinary.com/lumigo-production/w_477,c_fit/fl_lossy,f_auto/wp-website/2021/03/stackoscope-report.png)

**AWS Toolkit for VS Code**

[Easier Step Functions with the AWS Toolkit for VS Code](https://aws-oss.beachgeek.co.uk/ej) this post from Andy Blackledge takes a look at how this open source plugin for VS Code can really make developing AWS Step Functions much simpler. Andy walks you through an example and provides source code so you can try it for yourself.

**Apache Zeppelin**

[Setting Up Dev Endpoint Using Apache Zeppelin With AWS Glue](https://aws-oss.beachgeek.co.uk/ek)  Shubham Muneshwar shows you how you can configure Apache Zeppelin to interactively, run, debug and test ETL code before deploying as Glue job or scheduling the ETL process. Apache Zeppelin is an open source project that provides a web-based notebook that enables data-driven, interactive data analytics and collaborative documents with a large number of languages, such as SQL, Spark, Scala and more.

**Data Lakes**

[3 Data Lake Anti-Patterns to Avoid](https://aws-oss.beachgeek.co.uk/eo) Paul Singman shares three anti-patterns with you from a post a few weeks back that I missed. It would be rude of me to tell you what those were without you dipping into this post, so read on and find out more about these anti-patterns. Paul offers some helpful suggestions as to alternatives if you find yourself recognising some of these patterns.

### Podcast of the week

**DevOps on AWS Radio: Mutato and Open Source at Stelligent**

Check out this podcast in which Michael Neil talks about Stelligent’s newest open source project, Mutato, and how you can use it to automate your container deployments and help people who are new to AWS to make their deployments easier.

{% soundcloud https://soundcloud.com/stelligent/episode-27-mutato-and-open-source-at-stelligent %}

### AWS open source posts

**Prometheus**

[Prometheus 2.26.0 adds AWS Signature Version 4 support](https://aws-oss.beachgeek.co.uk/dz) Alolita Sharma and Imaya Kumar Jagannathan share that the latest release of Prometheus (v2.26.0), an open source systems monitoring and alerting toolkit, has rolled out native AWS Signature Version 4 authentication support. With this new feature, the Prometheus server is able to directly make remote-write API calls to send metrics to the Amazon Managed Service for Prometheus (AMP) without having to rely on a proxy sidecar container, such as the AWS SigV4 container. To find out more, read on.

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/04/14/alolitas_prometheus_226_f1.png)

**Grafana**

[Amazon Managed Service for Grafana (AMG) preview updated with new capabilities](https://aws-oss.beachgeek.co.uk/ew) Toshal Dudhwala and Imaya Kumar Jagannathan announce the wide availability of the AMG public preview and cover some of the new features and plugins that are available in Grafana 7.5. There is a webinar later this week, so if you want to know more make sure you sign up for it too.

![grafana](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2021/04/15/image002.gif)

**PostgreSQL**

[Amazon Aurora PostgreSQL parameters, Part 1: Memory and query plan management](https://aws-oss.beachgeek.co.uk/e3) Sameer Kumar and Gopalakrishnan Subramanian ask you to sit down, grab a cup of your favourite beverage in which to enjoy this four part blog post that covers a broad range of topics. In Part 1 they cover parameters that can be useful to tune the memory utilisation of Aurora PostgreSQL, Part 2 it is all about parameters related to replication, security, and logging. From there Part 3 looks at performance of queries and wrapping up with the final part, Part 4 explores how you can align Aurora PostgreSQL closer to American National Standards Institute (ANSI) standards and reduce the migration effort when migrating from commercial engines.

**TensorFlow**

[Implement checkpointing with TensorFlow for Amazon SageMaker Managed Spot Training](https://aws-oss.beachgeek.co.uk/e0) Eitan Sela shows you how you can train TensorFlow models (in this instance, an image classification model) using SageMaker Managed Spot Training. He shares how using checkpoints locally in the container and loaded checkpoints to resume training can help you save over 70% when training your deep-learning models.

![checkpoint](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2021/03/23/5-spot-estimator.jpg)

**Spinnaker**

[Enhancing Spinnaker deployment experience of AWS Lambda functions with the Lambda plugin](https://aws-oss.beachgeek.co.uk/e2) Nima Kaviani, Vikrant Kahlir and Gaurav Dhamija from AWS and from Autodesk, Shrirang Moghe and Brandon Leach come together to share the collaborative efforts between Autodesk, various AWS teams, and Armory.io to drive the implementation and release of the Lambda plugin for Spinnaker. Spinnaker is an open source continuous delivery platform that allows for fast-paced, reliable, and repeatable deployment of software to the cloud used by many AWS customers. The posts looks at the design choices made in building the Lambda plugin and walks you through a sample scenario of deploying a Lambda function using the plugin.

![spinnaker](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/03/31/nkaviani_Enhancing-Spinnaker-Deployment-Experience_f12.jpg)

**Terraform**

[Build infrastructure continuous integration for Terraform code leveraging AWS Developer Tools and Terratest](https://aws-oss.beachgeek.co.uk/ex) Carlos Perea and Luca Mazzaferro share this solution on how to integrate Terraform with AWS Cloud* tools to build a CI pipeline that uses Terraform and Terratest.

![arch](https://d2908q01vomqb2.cloudfront.net/0716d9708d321ffb6a00818614779e779925365c/2021/02/17/CI4Terraform.png)

### Quick updates

**PostgreSQL**

Amazon RDS for PostgreSQL now support PostgreSQL minor versions 13.2, 12.6, 11.11, 10.16, 9.6.21, and 9.5.25. This release closes security vulnerabilities in PostgreSQL and contains bug fixes and improvements done by the PostgreSQL community. This also includes the final release of PostgreSQL 9.5.

This release adds support for aws_lambda and pg_bigm. aws_lambda allows you to invoke AWS Lambda functions from an Amazon RDS for PostgreSQL DB instance. pg_bigm adds faster full text search to PostgreSQL using a bigram index.

Characters that comprise text are represented as numbers to computers. Languages such as English, French, Russian, and Hebrew use character sets of fewer than 256 characters that can be encoded in a single byte. Languages with many characters (e.g., Japanese) require more numbers, which are represented by multi-byte encoding. pg_bigm allows you to create a 2-gram (bigram) index for faster full text search of text encoded with multi-byte characters.

**Elasticsearch**

Amazon Elasticsearch Service now supports integrating with Microsoft Power BI, a business analytics service that delivers insights to enable fast, informed decisions. Powered by the Open Distro for Elasticsearch ODBC Driver you can now integrate your Microsoft Power BI environment with you Amazon Elasticsearch Service domains using the Open Distro for Elasticsearch SQL Engine.

The Open Distro for Elasticsearch SQL Engine uses Structured Query Language (SQL) to manifest search results in a tabular format. One of the key features of this engine is the Open Database Connectivity (ODBC) driver which enables you to integrate various business intelligence (BI) and analytics applications with Elasticsearch. You can now connect Amazon Elasticsearch Service with Microsoft PowerBI to create sophisticated and intelligent data visualisations on top of the search results obtained from Amazon ES by leveraging the Amazon ES- PowerBI Integration, to provide deep data insights.  

**Open Data**

Twenty eight new or updated datasets from the US Geological Survey, the Swiss Institute of Bioinformatics, iNaturalist.org, National Oceanic and Atmospheric Agency (NOAA), and others are available in the Registry of Open Data on Amazon Web Services (AWS) in the following categories: COVID-19, Agriculture, Astronomy, Climate and Weather, Geospatial, Life Sciences, Machine Learning and Statistical and regulatory. Check out the full list on the announcement page, [New datasets available in the Registry of Open Data on AWS from United States Geological Survey (USGS), the Swiss Institute of Bioinformatics, iNaturalist.org, and others](https://aws-oss.beachgeek.co.uk/e8)

You can also read more on this from the blog post, [SARS-CoV-2 viral genomes, storm surge forecasts, cloud-free satellite imagery: The latest open data on AWS](https://aws-oss.beachgeek.co.uk/ep) from Joe Flasher.

![image](https://d2908q01vomqb2.cloudfront.net/9e6a55b6b4563e652a23be9d623ca5055c356940/2021/04/16/Open-data-on-AWS-Q2.jpg)

### Video of the week

**Amazon Corretto**

This video, "Amazon Corretto, A Journey into Latency Reduction" was from the Seattle Java User group a few weeks back. Yishai Galatzer and Kelvin Nilsen talks about the Amazon Corretto project, it’s principals, and walk through examples that drove performance gains, latency reduction, and cost reduction in some of the biggest services in AWS.

{% youtube S4IrAZ5wT3c %}

### Events for your diary

Watch out for these events happening later this week and next.

**Cloud City Meetup: The Cloud Meets Open Source -- A Conversation with Matt Asay**
**21st April**

Join us for a conversation about the complements and conflicts between the cloud and open source. We’ll talk about the past, present and future of open source in a cloud world, the evolution of business models and licenses, and the best models going forward for startups based on open source projects.

To sign up for this event, [click here](https://aws-oss.beachgeek.co.uk/dy).

**CDK Day**
**April 30th**

Announced this week was the second [CDK Day](https://sessionize.com/cdkday/), which will be on April 30th. Check out [the web page](https://sessionize.com/cdkday/) to find out more about the first CDK Day, which was incredible. This second event promises to be even better. The CFP is open until the 19th of March. Check out this supporting blog post, [CDK Day CFP Is Open!!!!](https://aws-oss.beachgeek.co.uk/4v) from Matt as to what to expect and what they are looking for when it comes to sessions.

**Cloud Native Rust Day**
**May 3rd**

Rust is a language empowering everyone to build secure, reliable, and efficient software. Rust is becoming more widely used in cloud native, powering everything from lightning-fast service meshes and powerful developer tools to internet-scale distributed databases.

Come explore what makes Rust a fantastic choice for new cloud native development, and learn about how the community uses Rust today. Find out [more and register here](https://aws-oss.beachgeek.co.uk/5y).

**Container Day**
**May 4, 2021 | 10:00AM - 6:00PM CEST**

Container Day x KubeCon is a fully live, virtual day of sessions all about Amazon EKS and Kubernetes at AWS, hosted by Brent Langston and Adam Keller of Containers from the Couch. At this Day Zero KubeCon event, the AWS Kubernetes team will be revealing new launches, demoing products and features, covering best practices, and answering your questions live on Twitch! If you have a question before the event, you can email the team at awscontainerday@amazon.com and maybe get them answered.

Find out more and to register, [click here](https://aws-oss.beachgeek.co.uk/cr).

**An Introduction to Amazon Managed Blockchain**
**5th May**

Amazon Managed Blockchain (AMB) is a fully managed service that makes it easier to build scalable blockchain networks using popular open source frameworks, including Hyperledger Fabric and Ethereum. AMB includes several features and enhancements beyond those provided by the open-source projects on which it is based. It supports public and private blockchain options, each of which favors different use cases. We review reference architectures outlining example applications on both Hyperledger Fabric and Ethereum. In this lecture, you will also hear several customer success stories building solutions on Amazon Managed Blockchain.

Find out more and register [via this link](https://aws-oss.beachgeek.co.uk/dx).

**Building And Maintaining Your Own Secure Container OS**
**May 13th 9am PST**

Curtis Rissi, a Principal Partner SA at AWS will walk attendees through the Bottlerocket (an open-source Linux-based operating system meant for hosting containers) build process, and provide some key use cases for customisation: how to add new configuration options; how to add new packages; how to configure your own update repositories; how to add security policy; and other common customisations. 

Find out more and to register, click [here](https://aws-oss.beachgeek.co.uk/ed)

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen).