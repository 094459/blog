---

title: 'AWS open source news and updates #96'
date: '2022-01-17'
tags : [ oss-newsletter, aws open source, kubernetes, Babelfish, Redis, Smithy, Lambda Powertools, Amazon EMR, TorcheServe, Deep Graph Library, ParallelCluster, Galaxy, Apache Flink, OpenSearch]

---

## Jan 17th, 2022 - Instalment #96

Newsletter #96. 

Welcome to another great round up of open source projects, news and great content. This week, we have new open source projects such as Event Catalog (that helps you to discover, explore and document your Event Driven Architectures), AWS Powertools for Lambda TypeScript edition, flowdog (an application/framework for inspection and manipulation of network traffic in AWS VPCs), ai-doorbell (a serverless AI enabled door bell) and many more. For your reading pleasure we have content on the following topics, Kubernetes, Babelfish, Redis, Smithy, Amazon EMR, TorcheServe, Deep Graph Library, ParallelCluster, Galaxy, Apache Flink, OpenSearch and more. Make sure you check out the new SaaS workshop, we have a new video that I think you will enjoy and we have a couple of new events, one of which you can catch later today.

Before diving in though, make sure you check out the AWS Community Builder application (below) and if you missed it, news about a great book which should be on your reading list. With that....

**CDK Book**

If you are looking for something to read, then I have a recommendation for you. Towards the end of 2021, [The CDK Book](https://aws-oss.beachgeek.co.uk/195) came out, written by Matthew Bonig, Thorsten Höger, Sathyajith Bhat and Matt Coulter. This is a must read interesting in automation and writing infrastructure as code, this book has been written by DevOps engineers for DevOps engineers. With a foreword from Elad Ben-Israel, this provides a hands on (plenty of examples and code, across more than just TypeScript) guide, as well as sharing current good practices as well as how you might use this in more enterprise use cases. 

**AWS Community Builders**

The application form to join AWS Community Builders will be open until January 24th, and I would love to see more of the great open source builders sign up for this great program. Application form is [here](https://aws-oss.beachgeek.co.uk/18a) If you want more info, check out this great write up from an existing AWS Community Builder, Stephen Sennett, [How to become an AWS Community Builder](https://aws-oss.beachgeek.co.uk/18b)  

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Matt Lewis, Matt Morgan, Aidan Steele, Lars Jacobsson, Cameron Senese, Yehor Shytikov, David Boyne, Damon Cortesi, Matt Muller, Asher Yermiyahu, Viji Sarathy, Kishore Dhamodaran, Jared Keating, Neha Gupta, Ramesh Kumar Venkatraman, Sheetal Joshi, Apurup Chevuru, Mike Stefaniak, Carlos Manzanedo Rueda, Brandon Wagner, Karthik Basavaraj, Suman Debnath, Hubert Asamer and Jan Metzner.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest open source projects

**eventcatalog**

[eventcatalog](https://aws-oss.beachgeek.co.uk/18d) another fantastic project from David Boyne. Event Catalog helps you to discover, explore and document your Event Driven Architectures powered by Markdown. EventCatalog as a website generator that allows you to document your event architectures with markdown files. As with all David's projects, next level documentation and there are example/demo output so you can see what you are likely to get if you were to run it yourself. Awesome stuff. If you do find it useful, make sure you do not skip the Sponsor link...

![demo](https://raw.githubusercontent.com/boyney123/eventcatalog/master/website/static/img/eventcatalog-screen1.png)

**cloud-map-mcs-controller**

[cloud-map-mcs-controller](https://aws-oss.beachgeek.co.uk/18c) is an open source project that implements the upstream multi-cluster services API (mcs-api) specification. The repository also provides a detailed work instruction and associated artefacts required for the end-end implementation of the AWS Cloud Map MCS Controller across multiple EKS clusters in support of seamless, multi-cluster workload deployments. This blog post, Kubernetes Multi-cluster Service Discovery using the AWS Cloud Map MCS Controller, from Cameron Senese will help you learn all about the mcs-api, and how to deploy the AWS MCS Controller in support of seamless, multi-cluster workload deployments on Amazon EKS.

![arch](https://blog.bytequalia.com/content/images/2022/01/solution-overview-v0.01.png)

**aws-lambda-powertools-typescript**

[aws-lambda-powertools-typescript](https://aws-oss.beachgeek.co.uk/18e) this generated a lot of excitement a few weeks back when it was announced. TypeScript developers no longer need to feel left out. AWS Lambda Powertools TypeScript provides a suite of utilities for AWS Lambda functions running on the Node.js runtime, to ease the adoption of best practices such as tracing, structured logging, custom metrics, and more. AWS Lambda Powertools for TypeScript is currently released as a beta developer preview and is intended strictly for feedback purposes only. Check out the blog section for a couple of great, early reviews of this project.

**cdk-lambda-powertools-python-layer**

[cdk-lambda-powertools-python-layer](https://aws-oss.beachgeek.co.uk/18f) Have you checked out the CDK Constructs Hub yet? Whilst browsing last week, I found this community developed construct that will create AWS Lambda Layer with AWS Powertools for Python library. With this construct you don't have to care about packaging and dependency management, just create a construct and add it to your function. Nice!

**flink-industrial-anomaly-detector**

[flink-industrial-anomaly-detector](https://aws-oss.beachgeek.co.uk/18z) this ready to go open sourced solution provides a solid foundation for some advanced streaming analytics projects you might have. In this particular case, the streaming data is coming from an industrial use case. Sensor data, such as pressure and temperature, is ingested with a local edge gateway and streamed to the cloud runing in-stream analytics using Apache Flink. 
Hubert Asamer and Jan Metzner have put this detailed blog post [Detect Real-Time Anomalies and Failures in Industrial Processes Using Apache Flink](https://aws-oss.beachgeek.co.uk/18y)

![arch](https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2022/01/07/Figure-2-Detailed-system-architecture.png)

**flowdog**

[flowdog](https://aws-oss.beachgeek.co.uk/190) this the first of two projects from Aidan Steele. Flowdog is an application/framework for inspection and manipulation of network traffic in AWS VPCs. Packets routed to or from the Internet, between VPCs, between subnets can all be programmatically inspected or modified in great detail. What can you do with this? Aidan provides some examples, which demonstrate that anything is possible in the world of software-defined networking. From the docs, I really enjoyed the "Rickrolling" example. As Aidan says..

> AWS Workspaces is managed computers in the cloud for employees. Sometimes they want to watch YouTube. But here's a script that means they can only watch The One Video.
> ![example](https://pbs.twimg.com/media/FI5eZihaAAEpFK5?format=jpg&name=medium)
> Or maybe you want a more subtle rickroll. There's another sample that intercepts requests to the STS API and returns a friendly commitment in the response payload.
> ![example](https://pbs.twimg.com/media/FI5ejaAaIAIOyrk?format=jpg&name=medium)

**ipv6-ghost-ship**

[ipv6-ghost-ship](https://aws-oss.beachgeek.co.uk/191) what might you do if IP addresses were (almost) infinite? Well how about this fun/silly project from Aidan Steele, which changes the prefix of your instance ever 30 seconds. Make sure you read the Twitter thread...(I don't want to spoil it, but you really must)

**eks-gitops-crossplane-flux**

[eks-gitops-crossplane-flux](https://aws-oss.beachgeek.co.uk/18p) this repository contains software artifacts to deploy Crossplane server and Flux to an existing Amazon EKS cluster and then leverage the GitOps workflow to manage both provisioning a remote EKS cluster with Crossplane and subsequently manage application deployments to it using Flux. Viji Sarathy has put together a supporting blog post, [GitOps model for provisioning and bootstrapping Amazon EKS clusters using Crossplane and Flux](https://aws-oss.beachgeek.co.uk/18q) to help you get started.

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2022/01/06/GitOpsEKS.jpg)

**ai-doorbell**

[ai-doorbell](https://aws-oss.beachgeek.co.uk/198) nice new project from AWS Community Builder Lars Jacobsson, that will help you build a serverless, smart AI enabled door bell. To walk you through the build, Lars has put together this blog post, [The serverless architecture of a talking doorbell](https://aws-oss.beachgeek.co.uk/199) as well as rather funny demo video of the finished thing.

{% youtube DYGVGh5M-wg %}
{{< youtube DYGVGh5M-wg >}}

### Workshop

**Amazon EKS SaaS Workshop**

Check out the new Amazon EKS SaaS Workshop. Amazon EKS introduces a range of constructs that you can use to realise multi-tenancy in your SaaS solution. In this workshop, dig into the code and architecture of a working Amazon EKS SaaS application, exploring the various strategies to apply when building a SaaS application with Amazon EKS. Identity, tenant isolation, routing, data partitioning, and onboarding are among the SaaS constructs you create in this workshop. This workshop provides a hands-on view into all the moving parts of a real Amazon EKS SaaS solution that addresses specific considerations associated with bringing it to life on AWS.

![arch](https://static.us-east-1.prod.workshops.aws/public/596a58f6-65df-49e9-bce8-94bf5e3cf488/static/30/arch-overview.png)

You can find the code for this workshop in the GitHub repository, [aws-saas-factory-eks-reference-architecture](https://aws-oss.beachgeek.co.uk/192)

### AWS and Community blog posts

**AWS Lambda Powertools**

We had a couple of posts last week from AWS Community Builders/Heroes on the recently announced AWS Lambda Powertools for TypeScript. (in fact, it is a tale of two Matt's or Matt^2!)

First up is AWS Community Builder Matt Morgan, kicks the tyres of this project and walks you through his evaluation in his post, [First Look at Lambda Powertools TypeScript](https://aws-oss.beachgeek.co.uk/196). Following that is AWS Data Hero Matt Lewis, with his post [Test Drive AWS Lambda Powertools for Typescript](https://aws-oss.beachgeek.co.uk/197) where he takes his turn in kicking the AWS Lambda Powertools for TypeScript tyres. Make sure you check out both posts, including some of the comments in the first.

**OpenSearch**

AWS Data Hero Matt Lewis' second post this week (see above) on how to quickly get up and running with OpenSearch in [Streaming Data to OpenSearch](https://aws-oss.beachgeek.co.uk/19a). This post shows you how to configure Cognito to protect OpenSearch Dashboards, and set up a custom CloudWatch Metrics dashboard for monitoring the HTTP Status Codes that are returned.

**Smithy**

Smithy is an open sourced interface definition language and set of tools that allows developers to build clients and servers in multiple languages. Smithy models define a service as a collection of resources, operations, and shapes. A Smithy model enables API providers to generate clients and servers in various programming languages, API documentation, test automation, and example code. In this post, [Developer Preview: Ruby SDK code generation using Smithy](https://aws-oss.beachgeek.co.uk/18n) Matt Muller shares news of the developer preview of smithy-ruby, a toolchain that can be used to code generate a “white label” Ruby SDK for your service API using Smithy modelling. This is a really interesting project that deserves more attention, so make sure you read this - especially if you are planning/building your own APIs.

![demo](https://d2908q01vomqb2.cloudfront.net/0716d9708d321ffb6a00818614779e779925365c/2022/01/07/Screen-Shot-2021-05-17-at-1.26.28-PM.png)

**Babelfish**

In the post, [Get started with Babelfish for Aurora PostgreSQL](https://aws-oss.beachgeek.co.uk/18t), Neha Gupta and Ramesh Kumar Venkatraman show you the steps involved in creating Babelfish for Aurora PostgreSQL and how to connect to the Babelfish database to query the server properties and its version information using different clients like sqlcmd and the SSMS Query Editor. [hands on]

![babelfish](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2021/12/20/DBBLOG-1915-image031.jpg)

**Redis**

A couple of posts this week. First off we have Asher Yermiyahu with the first in a series of posts related to AWS contributions to open source Redis clients. In the first one, [New cluster-mode support in redis-py](https://aws-oss.beachgeek.co.uk/18r) learn about how AWS has teamed up with the open-source community that supports redis-py to add cluster-mode support to this popular client. [hands on]

Following that we have Kishore Dhamodaran and Jared Keating who have written about the recently announced support for auto scaling your Amazon ElastiCache for Redis clusters in the post, [Scale your Amazon ElastiCache for Redis clusters with Auto Scaling](https://aws-oss.beachgeek.co.uk/18s) [hands on]

![graph](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2021/12/27/DBBLOG-1960-image025.jpg)

**Kubernetes**

There were a bunch of interesting posts related to Kubernetes. We had Sheetal Joshi, Apurup Chevuru, and Mike Stefaniak put together this, [Amazon EKS launches IPv6 support](https://aws-oss.beachgeek.co.uk/18v) where you will learn how to create an IPv6 EKS cluster within a dual-stack Amazon Virtual Private Cloud (VPC). As part of this walkthrough you will deploy a sample IPv6-only service and understand IPv4 and IPv6 ingress and egress functionality. Nice [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2022/01/03/ipv6-pod-networking.png)

Next up was, [Efficiently Scaling kOps clusters with Amazon EC2 Spot Instances](https://aws-oss.beachgeek.co.uk/18w) from Carlos Manzanedo Rueda and Brandon Wagner where they show you how you can leverage recently released tools to optimise your usage of Amazon EC2 Spot Instances on Kubernetes Operations (kOps) clusters. [hands on]

Finally, if you were looking for guidance on how to mount Amazon EFS file systems cross-account using Amazon EKS, then Karthik Basavaraj and Suman Debnath have you covered in their post [Mount Amazon EFS file systems cross-account from Amazon EKS](https://aws-oss.beachgeek.co.uk/18x).

Also, another plug for the new [EKS News](https://aws-oss.beachgeek.co.uk/185) which brings you all the latest updates, news and service announcements, notable blogs and stuff you really need to know about. Make sure you sign up for it.

**Other posts worth checking out**

Last week, these posts also caught my eye.

* [Custom AMIs with ParallelCluster 3](https://aws-oss.beachgeek.co.uk/18j) looks at how you can use features of ParallelCluster 3 (an AWS open sourced cluster management tool) for building on your existing AMIs when creating your clusters [hands on]
* [How to set up Galaxy for research on AWS using Amazon Lightsail](https://aws-oss.beachgeek.co.uk/18k) will help you to deploy the open-source Galaxy Project (a well-known toolkit for researchers to complete tasks and common tooling on public and private datasets) on AWS [hands on]
* [Optimize your inference jobs using dynamic batch inference with TorchServe on Amazon SageMaker](https://aws-oss.beachgeek.co.uk/18l) shows you a number of options for running your model inferencing using the open source project, TorchServe [hands on]
* [Graph-based recommendation system with Neptune ML: An illustration on social network link prediction challenges](https://aws-oss.beachgeek.co.uk/18m) shows you how you can use Neptune ML (powered by the Deep Graph Library an open-source, high-performance, and scalable Python package for DL on graphs) and GNNs to help you make recommendations on graph data [hands on]

![example](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2022/01/04/ML-6681-image002.png)

* [Introducing server-side caching item eviction for AWS AppSync](https://aws-oss.beachgeek.co.uk/18o) look at how developers can leverage a new capability to evict specific entries from AppSync’s server-side cache [hands on]
* [Automating SAP installation with open-source tools](https://aws-oss.beachgeek.co.uk/18u) walks you how you can use open-source common tools like Jenkins and Ansible to automate your SAP installation. [hands on]

### Quick updates

**MySQL**

Following the announcement of updates in MySQL database versions 5.7 and 8.0, we have updated Amazon Relational Database Service (Amazon RDS) for MySQL to support MySQL minor versions 5.7.36, and 8.0.27. We recommend that you upgrade to the latest minor versions to fix known security vulnerabilities in prior versions of MySQL, and to benefit from the numerous bug fixes, performance improvements, and new functionality added by the MySQL community. 

**Magento**

If you deploy Magento on AWS, then you will be interested in this update which I received from Yehor Shytikov. He let me know of a number of updates to some open source projects ([TerraformMagentoCloud](https://aws-oss.beachgeek.co.uk/18g) and [Magento-AWS-Linux-2-Installation](https://aws-oss.beachgeek.co.uk/18h)) that help set up Magento on AWS infrastructure with auto-scaling using AWS Cloud and Terraform. A new minimal branch helps you to deploy in a minimal infrastructure without redundant complexity like Varnish cache server.

**Redis**

You can now publish the Redis engine log from your Amazon ElastiCache for Redis clusters to Amazon CloudWatch Logs and Amazon Kinesis Data Firehose. The Redis engine log provides visibility into the internal operations of the Redis engine, giving additional insight into Redis operations and helping you troubleshoot Redis issues. You can choose to send these logs in either JSON or text format to Amazon CloudWatch Logs and Amazon Kinesis Data Firehose. This feature is available for Amazon ElastiCache clusters with Redis version 6.2 and is supported in all commercial Amazon Web Services Regions. 

**SQL Explorer**

Amazon EMR Studio is an integrated development environment (IDE) that makes it easy for data scientists and data engineers to develop, visualise, and debug big data and analytics applications written in R, Python, Scala, and PySpark. SQL Explorer is a new feature in your EMR Studio Workspace that allows you to browse the data catalog and run SQL queries on EMR clusters from EMR Studio. This release of SQL Explorer in EMR Studio supports running SQL queries on Amazon EMR on EC2 clusters running Presto version 0.254.1 or higher. 

Presto is a fast SQL query engine designed for interactive analytic queries over large datasets from multiple sources. In SQL explorer, you can connect to Amazon EMR on EC2 clusters with Presto installed to view and browse the data catalog. Supported data catalogs include AWS Glue Data Catalog and self-hosted Hive Metastore version 3.1.2 or higher. SQL Explorer also provides you an Editor to run SQL queries, view the query results in a table, and download query results in a csv format. You also have the ability to run multiple SQL statements via different Editor tabs. SQL explorer is supported for Amazon EMR versions 6.4.0+.

**AWS Toolkit for JetBrains**

The AWS Toolkit for JetBrains now provides developers with convenient IDE functionality to connect to Amazon ECS containers and issue commands using Amazon ECS Exec. This allows developers to directly interact with containers, such as running commands in or get a shell to an ECS container running on an Amazon EC2 instance or on AWS Fargate, without leaving their IDE. ECS Exec uses the AWS Systems Manager (SSM) Session Manager under the hood to establish a connection with the running container.

### Videos of the week

**Amazon EMR Studio - Real-time Collaboration**

Real-time collaboration is a new feature in EMR Studio that allows multiple users to share a single notebook workspace. This makes it easy for data scientists and data engineers to collaborate in real-time across teams using EMR Studio as they develop, visualise, and debug big data and analytics applications written in R, Python, Scala, and PySpark. In this video, Damon Cortesi shows you how you can both use the same workspace to collaborate on the same notebook. You can follow along in the session using the code in the GitHub repo, [emr-studio-samples](https://aws-oss.beachgeek.co.uk/18i)

{{< youtube Q6NNDoLEUpo >}}

### Events for your diary

If you have an event you want me to publish here, please contact me and I will include it in this listing.

**Lakehouse Automation w/ Redshift+Apache Airflow & New AWS ML services**
**January 17th, 9:00am PST**

During this meetup, join hosts Chris Fregly and Antje Barth and speaker Gary Stafford, who do a presentation and brief demonstration, based on his recent video demonstration, AWS Lakehouse Automation: Loading and unloading data from Amazon Redshift using Apache Airflow, we will learn how to use Amazon Managed Workflows for Apache Airflow (Amazon MWAA) to programmatically load, unload, test, catalog, query, and monitor data using DevOps-like DataOps practices.

Find out more about this and [register here](https://www.meetup.com/data-science-on-aws/events/282788878/?_xtd=gqFyqTI2NzgyNDA2OaFwo2FwaQ&from=ref).
 
**AWS Startup Showcase Season**
**January 26th, 10:00am PDT**

Join AWS and theCUBE as eight innovative companies within the AWS Partner ecosystem highlight their latest developments in the open source community.

[Register via this link](https://aws-oss.beachgeek.co.uk/194)

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)