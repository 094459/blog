---
title: 'AWS open source news and updates 92'
date: '2021-11-29'
tags : [ oss-newsletter ]
---
## November 29th, 2021 - Instalment #92

Newsletter #92. This is the re:Invent edition of the weekly newsletter, and whilst I am not there this year, I will still be covering all the announcements and topics of interest in this and next weeks newsletter. 

Outside of re:Invent, this weeks letter also brings you lots more new open source projects including something for DynamoDB fans, a serverless GraalVM project, a very nice AWS SSO project, new Grafana recipes and more. AWS and community posts this week cover Linux, Redis, Deep Java Library, Deep Graph Library, Magma, Moodle, GitHub Actions and more. We have a couple of new videos to share to round things off.

Before diving in, check out the agenda this week at re:Invent so you do not miss any of the great open source sessions.

**re:Invent 2021**

Spot put together your essential reading to prepare you for re:Invent this year in his post, [AWS attendee guide for Open Source at re:Invent 2021](https://aws-oss.beachgeek.co.uk/150).

If you are going or attending virtually, there is plenty of great open source related sessions this year. I have summarised them here for your convenience. Read Spot's post above to dive into the abstracts of these sessions if you want to know more.

* OPN201 - How Apache Lucene's community built merge-on-refresh
* OPN202 - Babelfish architecture and design (Chalk Talk)
* OPN204 - Introduction to GraphQL
* OPN205 - Construct Hub: An open-source catalog for CDK libraries (Chalk Talk)
* OPN206 - Getting started as a Bottlerocket contributor (Chalk Talk)
* OPN207 - Top 10 observability challenges and how open source can help
* OPN301 - Using Rust to minimize environmental impact
* OPN302 - Upgrade to OpenSearch (Chalk Talk)
* OPN303 - Working in the open with OpenSearch (Chalk Talk)
* OPN304 - Async Rust: Hurry up and .await! (Workshop)
* OPN305 - Securing your OpenSearch data (Builder Session)
* OPN307 - OpenSearch: Building the future of search together
* OPN308 - ML with Metaflow and Kubernetes: Prototype to production on Amazon EKS
* OPN309 - AWS SaaS Boost vNext: Enabling new patterns and extensibility
* OPN311 - Build your AWS Cloud-connected embedded Linux OS faster (Chalk Talk)
* OPN312 - Building a multi-architecture CI/CD pipeline for Kubernetes (Chalk Talk)
* OPN313 - When life hands you data, grab OpenSearch (Workshop)
* OPN314 - Dive deep into cross-SDK features on AWS (Workshop)
* OPN315 - Build a PostgreSQL database cluster with Babelfish (Builder Session)
* OPN316 - Prometheus and Grafana: Integrated metrics, logs, and traces (Builder Session)

Other sessions of note include:

* AIM409 - Accelerate deep learning with cloud custom environments
* AIM12 - Deep learning applications with TensorFlow (Chalk Talk)
* ANT204 - Dive into Amazon OpenSearch Service (Workshop)
* ANT401 - Deep dive: Accelerating Apache Spark with Amazon EMR
* ARC311 - Accelerate building media analysis workflows on AWS
* CON204 - Observability & beyond with container-based services on AWS (Workshop)
* CON210 - Kubernetes scalability and dynamic scheduling
* CON305 - Automatic node provisioning with Karpenter
* CON320 - Keeping your host operating system secure with Bottlerocket (Chalk Talk)
* COP206 - Observability the open-source way
* COP316 - Open-source observability (Chalk Talk)
* COP402 - Optimizing AWS workflows with the CDK for Terraform
* DPR203 - The AWS DeepRacer open-source robotics showcase
* IOT302 - Build intelligent IoT devices faster with AWS IoT Greengrass (Chalk Talk)
* HJS304 - Code Green! The sustainability data hackathon and workshop
* NET301 - Open-source security appliances with AWS Gateway Load Balancer (Workshop)
* QTC306 - Using Julia to program quantum computers (Chalk Talk)

If you are there in person, a few things you should check out:

* Developer Lounge - there will be open source projects being show cased as well as open source builders on hand to speak with you.
* [After Dark](https://aws-oss.beachgeek.co.uk/13n) - an open source social that the open source team is organising. 

There is still time to register and attend, so find out more by checking out the [event home page.](https://aws-oss.beachgeek.co.uk/13m)

If you attending this week, check the noticeboard to make sure you do not miss the best re:Invent party, After Dark.

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Tyler Walch, Mark Sailes, Yusuf Mayet, Nathan Harris, Dmitry Gulin, Hari Ohm Prasath, Rene Brandel,  Lauren Mullennex, Indrajit Ghosalkar, Kirit Thadaka, Roberto Luna Rojas, Siva Karuturi, Sonal Brahmane, Lucas Baker, Andrea Duque, Viet Yen Nguyen, Kamran Habib, Waleed (Will) Badr, Kevin O’Brien, Joanne Moore, Jim Weingarten, Rabi Abdel, Jim Huang, and Arun Thulasi.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest open source projects

**electrodb**

[electrodb](https://aws-oss.beachgeek.co.uk/15f) ElectroDB is an open source DynamoDB library from Tyler Walch that aims to simplify the process of modelling, enforcing data constraints, querying across entities, and formatting complex DocumentClient parameters. Detailed documentation and plenty of examples make this a project worth checking out.

**serverless-graalvm-demo**

[serverless-graalvm-demo](https://aws-oss.beachgeek.co.uk/15g) Mark Sailes has put together a Serverless GraalVM demo, that consists of an Amazon API Gateway backed by four AWS Lambda functions and an Amazon DynamoDB table for storage.

![arch](https://github.com/aws-samples/serverless-graalvm-demo/blob/main/imgs/diagram.png?raw=true)

**grafana-athena-recipes**

If you have not subscribed to Michael Hausenblas' excellent weekly newsletter [o11y](https://aws-oss.beachgeek.co.uk/99), covering o11y topics including but not limited to OpenTelemetry, Prometheus, FluentBit, and other related CNCF projects then I recommend you check it out. Michael shares a couple of new recipes from the announcement last week that Amazon Athena and Amazon Redshift are now supported as data sources from within Grafana.

First up we how to [setup Amazon Athena](https://aws-oss.beachgeek.co.uk/159), using a nice demo of how to query geo data and then visualise this. [Amazon Redshift as a data source](https://aws-oss.beachgeek.co.uk/15a) is now also possible, whether you want to use your own open source Grafana or a managed service version like AMG.

**aws-sso-extensions-for-enterprise**

[aws-sso-extensions-for-enterprise](https://aws-oss.beachgeek.co.uk/15h) this project simplifies the process to manage user access to AWS accounts with AWS SSO by extending the AWS SSO API. Instead of separately managing AWS SSO permission sets and account assignments, you can use this solution to describe permission sets with one API call per set.

![arch](https://github.com/aws-samples/aws-sso-extensions-for-enterprise/blob/main/docs/images/aws-sso-extensions-for-enterprise-overview.png?raw=true)

**mlops-template-gitlab**

[mlops-template-gitlab](https://aws-oss.beachgeek.co.uk/14w) this repo contains a MLOps template in this repo can be used to setup a SageMaker Project for model training and deployment using GitLab for SVC and GitLab Pipelines for CI/CD.  Lauren Mullennex, Indrajit Ghosalkar, and Kirit Thadaka have put together this blog post, [Build MLOps workflows with Amazon SageMaker projects, GitLab, and GitLab pipelines](https://aws-oss.beachgeek.co.uk/14x), to help you walk through the code.

![arch](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2021/11/16/ML-6664-arch-diagram-image001.png)

**aws-virtual-waiting-room**

[aws-virtual-waiting-room](https://aws-oss.beachgeek.co.uk/15i) this new project helps you to buffer incoming user requests to your website during large bursts of traffic (perfect for the fast approaching holiday season). It creates a cloud infrastructure designed to temporarily offload incoming traffic to your website, and it provides options to customise and integrate a virtual waiting room. The waiting room acts as a holding area for visitors to your website and allows traffic to pass through when there is enough capacity. There is detailed documentation here, [Absorb large bursts of traffic to your website with the AWS Virtual Waiting Room](https://aws-oss.beachgeek.co.uk/15j). Thanks to Tyler Lynch for giving me a heads up on this one.

![arch](https://d1.awsstatic.com/Solutions/Solutions%20Category%20Template%20Draft/Solution%20Architecture%20Diagrams/virtual-waiting-room-diagram.1a874d78025af5579e5444ad576487aa1b303f37.png)

**amazon-ecs-ami**

[amazon-ecs-ami](https://aws-oss.beachgeek.co.uk/15e) this repo contains Packer recipes for building the official ECS-optimized Amazon Linux AMIs.

### AWS and Community blog posts

**Linux**

Really excited about the announcement last week, of the public preview of Amazon Linux 2022 (AL2022), Amazon's new general purpose Linux for AWS, and I know a lot of folk have been working really hard on this one. Starting with AL2022, a new Amazon Linux major version will be available every two years and each version will be supported for five years. Customers will also be able to take advantage of quarterly updates via minor releases and use the latest software for their applications. Finally, AL2022 provides the ability to lock to a specific version of the Amazon Linux package repository giving customers control over how and when they absorb updates. AL2022 uses the Fedora project as its upstream to provide customers with a wide variety of the latest software, such as updated language runtimes, as part of quarterly releases. In addition, AL2022 has SELinux enabled and enforced by default.

You can read the full announcement over at, [Announcing preview of Amazon Linux 2022](https://aws-oss.beachgeek.co.uk/157) and you can take a look at the GitHub repo, [amazon-linux-2022](https://aws-oss.beachgeek.co.uk/158)

Following that, we had Joanne Moore and Jim Weingarten announce the updated Amazon Linux Ready Program, which will now validate AWS Partner software products that run on Amazon Linux 2 as well as the next-generation Amazon Linux 2022. You read the details in their post, [Amazon Linux Ready Program Updated to Include the Next-Generation Amazon Linux Operating System](https://aws-oss.beachgeek.co.uk/154)

**Redis**

In the post, [Amazon ElastiCache introduces support for Redis 6.2](https://aws-oss.beachgeek.co.uk/14y), Roberto Luna Rojas, Siva Karuturi, and Sonal Brahmane talk about support for Redis 6.2 in Amazon ElastiCache and walk you through some of the key commands you should know about.

**Deep Java Library**

Deep Java Library (DJL) is an open source Java framework for deep learning. In this guest post from Lucas Baker, Andrea Duque, and Viet Yen Nguyen of Hypefactors, they share how they integrated the predictor into one of their pipelines using, and how that change made their architecture simpler and MLOps easier. Find out more by reading their post, [Simplified MLOps with Deep Java Library](https://aws-oss.beachgeek.co.uk/14z)

![arch](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2021/11/17/ML-6501-image009.jpg)

**Deep Graph Library**

[Deep Graph Library (DGL)](https://aws-oss.beachgeek.co.uk/152) is an open source Python package for deep learning on graphs. In this post, [How Careem is detecting identity fraud using graph-based deep learning and Amazon Neptune](https://aws-oss.beachgeek.co.uk/153) Kamran Habib, Waleed (Will) Badr, and Kevin O’Brien share how Careem detects identity fraud using graph-based deep learning and Amazon Neptune.

![graph](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2021/11/12/ML-5154-image003-600.png)

**Moodle**

If you are a user of Moodle, then this post [How to scale and optimize Moodle LMS on AWS](https://aws-oss.beachgeek.co.uk/14t) from Yusuf Mayet will show you how to scale and optimise Moodle making sure the new environment caters to thousands of students and is still a cost effective solution. [hands on]

**GitHub Actions**

Whilst not specifically open source, many open source projects have chosen to live in GitHub and often use GitHub Actions as part of their software development tooling. If you are such a project, and you are looking for a nice, easy way to deploy your project into a container runtime on AWS, then check out this post, [Deploy applications in AWS App Runner with GitHub Actions](https://aws-oss.beachgeek.co.uk/14u) from Nathan Harris, Dmitry Gulin, and Hari Ohm Prasath. This post covers how you can use GitHub as a source code repository can use GitHub Actions to deploy your containerised applications on App Runner. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2021/11/22/githubactions5.jpg)

**AWS Distro for OpenTelemetry**

In the post, [Simplifying Amazon ECS monitoring set up with AWS Distro for OpenTelemetry](https://aws-oss.beachgeek.co.uk/151) Rodrigue Koffi provides a hands on guide on how to set up AWS Distro for OpenTelemetry for Amazon Elastic Container Service (Amazon ECS) with the 1-click console integration. I have this on my todo list, so check it out. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/11/22/koffir_simplify_ecs_monitoring_opentelemetry_f1-1.png)

**Magma**

[Magma](https://aws-oss.beachgeek.co.uk/15c) is an open-source software platform that gives network operators an open, flexible and extendable mobile core network solution. In the post, [Deploying Magma on AWS Cloud: In Region, On Premises, and at Edge](https://aws-oss.beachgeek.co.uk/15d), Rabi Abdel, Jim Huang, and Arun Thulasi provide instructions for deploying and configuring the Magma core network on the AWS Cloud through Magma Cloudstrapper. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/c5b76da3e608d34edb07244cd9b875ee86906328/2021/11/23/Figure-4.-Magma-AGW-in-AWS-Edge-Outposts-1.png)

**AWS Amplify**

There have been a few very nice pre:Invent announcements from the AWS Amplify team, and last week we saw yet more.

The AWS Amplify CLI is a command line toolchain that helps frontend developers create app backends in the cloud. Within this tool, Transformers enable developers to configure their backend data model using the GraphQL Schema Definition Language, and Amplify CLI automatically transforms the schema into a fully functioning GraphQL API with its underlying cloud infrastructure.

In the post, [AWS Amplify announces the new GraphQL Transformer v2. More feature-rich, flexible, and extensible](https://aws-oss.beachgeek.co.uk/14v) Rene Brandel reviews five of the new GraphQL features that are available with the GraphQL Transformer v2.

![explain](https://d2908q01vomqb2.cloudfront.net/0a57cb53ba59c46fc4b692527a38a87c78d84028/2021/11/23/key-migration-1024x591.png)

### Quick updates

**Grafana**

Amazon Managed Grafana announces new data source plugins for Amazon Athena and Amazon Redshift, enabling customers to query, visualise, and alert on their Athena and Redshift data from Amazon Managed Grafana workspaces. Amazon Managed Grafana now also supports CloudFlare, Zabbix, and Splunk Infrastructure Monitoring data sources as well as the Geomap panel visualisation and open source Grafana version 8.2.

Read the full announcement in, [Amazon Managed Grafana adds support for Amazon Athena and Amazon Redshift data sources and Geomap visualization](https://aws-oss.beachgeek.co.uk/156)

**PostgreSQL**

Amazon Relational Database Service (RDS) Proxy now supports RDS for PostgreSQL and Amazon Aurora PostgreSQL - Compatible Edition major version 12. PostgreSQL 12 includes better management of indexing, improved partitioning capabilities, JSON path queries per SQL/JSON specifications, and many other additional features. RDS Proxy is a fully managed and a highly available database proxy for Aurora and RDS databases. RDS Proxy helps improve application scalability, resiliency, and security.

**Terraform**

AWS Proton now supports the definition of infrastructure in HashiCorp Configuration Language (HCL) and the provisioning of infrastructure using Terraform Open Source through a git-based workflow. Platform teams define AWS Proton templates using Terraform modules, and AWS Proton leverages the customer-managed Terraform automation to provision or update the infrastructure. Customers can use Terraform as their infrastructure definition and provisioning tool, and AWS Proton will ensure that modules are used consistently and kept up to date. Read more in the announcement, [AWS Proton now supports Terraform Open Source for infrastructure provisioning](https://aws-oss.beachgeek.co.uk/155) and the post from my colleague Marcia Villalba, [New – AWS Proton Supports Terraform and Git Repositories to Manage Templates](https://aws-oss.beachgeek.co.uk/15b)

**Amazon Redshift**

Native support for open source SQLAlchemy (sqlalchemy-redshift) and Apache Airflow frameworks are now available for Amazon Redshift. The updated Amazon Redshift dialect for SQLAlchemy supports the Amazon Redshift open source Python driver. With this release you can use single sign-on with your Identity Provider (IdP) to connect to Redshift clusters and avoid credential management pains. You can also use new Amazon Redshift features such as using TIMESTAMPTZ and TIMETZ datatypes when you migrate to the latest Redshift dialect for SQL Alchemy and Apache Airflow. These features are available in sqlalchemy-redshift version 0.8.6 and later.

Apache Airflow has added RedshiftSQLHook and RedshiftSQLOperator that allows Airflow users to execute Amazon Redshift operations. RedshiftSQLHook leverages the Amazon Redshift open source Python driver (redshift_connector) that supports authenticating via IAM or your Identity Provider supported in SQLAlchemy. The integration of Apache Airflow with SQLAlchemy leverages the updated sqlalchemy-redshift.

### Video of the week

**Container re:Invent special**

Adam Keller and Justin Garrison from The Containers from the Couch team ran a pre:Invent special last week, taking a look at AWS container features and launches in 2021 leading up to re:Invent

{% youtube WESQKUbnmFU %}

### Events for your diary

**re:Invent 2021 | Virtual and Las Vegas**
**November 28th to Friday 3rd December**

See details above of the sessions. There is still time to register and attend, so find out more by checking out the [event home page.](https://aws-oss.beachgeek.co.uk/13m)

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)