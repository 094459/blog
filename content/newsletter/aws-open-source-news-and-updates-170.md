---
title: 'AWS open source newsletter #170'
date: '2023-08-21'
tags : [ oss-newsletter, aws open source, AWS-LC, Threat Composer, AWS CDK, AWS SAM, AWS SDK for Java, GitLab, GraphQL, AWS AppSync,AWS Distro for OpenTelemetry (ADOT), PostgreSQL, Apache Airflow, SBOM, Syft, Apache Hudi, Apache Iceberg, Apache Spark, collectd, Grafana, O3DE, ROS, Next.js, PostgreSQL, OpenZFS, MWAA, Cedar, Powertools for Lambda]

---

## August 21st, 2023 - Instalment #170

Welcome to edition #170 of the AWS open source newsletter, an oasis of open source goodness that features the latest new projects, essential reading, and must view videos to quench the thirst of every open source developer. This weeks edition we have new projects that help you get on top of your IAM actions, a handy tool for knowing what your current AWS account service limits are from the command line, a tool to help you do database migrations, and some interesting and very detailed reference solutions for gaming, live streaming, and managing/exporting of your Amazon Cognito profiles.

This weeks community and AWS content round up includes content from open source technologies including AWS-LC, Threat Composer, GraphQL, AWS Distro for OpenTelemetry (ADOT), PostgreSQL, Apache Airflow, Syft, Apache Hudi, Apache Iceberg, Apache Spark, collectd, Grafana, O3DE,  Next.js, OpenZFS, Cedar, Powertools for Lambda and more. As always, don't skip the events section as there are plenty of events happening in August/September which you should check out.


**Feedback**

Before you dive in however, I need your help!  Please please please take 1 minute to [complete this short survey](https://www.pulse.aws/promotion/10NT4XZQ). For the first 20 submissions I have some AWS Credits as a thank you.

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes:  Darren Boyd, Jessie Wei, Andrew Hopkins, Greg Foster, Chris Farris, Stephen Jones, Rotem Tamir, Ivica Kolenkaš, Heitor Lessa, Daniel Aniszkiewicz, Yasunori Kirimoto, Kaxil Naik, Virgil Ennes, Samuel Baruffi, Emmanuel Saliu, Rishi Gera, Hernan Garcia, Parnab Basak, Shubham Mehta, Kevin Schwarz, Eoin Shanaghy, and Luciano Mammino

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution. The projects mentioned here do not represent any formal recommendation or endorsement, I am just sharing for greater awareness as I think they look useful and interesting!*

#### Tools

**sensitive_iam_actions**

[sensitive_iam_actions](https://aws-oss.beachgeek.co.uk/361) is a crowdsourced list of sensitive IAM Actions. There exists no definitive list of Sensitive IAM Actions that can lead to credential or data access, privilege escalation, or making resources public. This repo contains a list of IAM Actions that fall into one of four risk categories: Credential Exposure, Data Access, Privilege Escalation, and Resource Exposure. Make sure you read the project README in full, as there is lots of additional information. Also, Chris Farris put together this blog post [Defining the Sensitive IAM Actions](https://aws-oss.beachgeek.co.uk/362) provides more background on the reason Chris put this repo together.

**aws-service-limits**

[aws-service-limits](https://aws-oss.beachgeek.co.uk/363) is a tool from AWS Community Builder Stephen Jones that fetches and displays service quotas for AWS services. It uses the GetAWSDefaultServiceQuota API to retrieve information about the current setting and utilises the UsageMetric information to get the actual usage via CloudWatch.

![demo of aws-service-limits](https://github.com/sjramblings/aws-service-limits/blob/main/images/basic.gif?raw=true)

**atlas**

[atlas](https://aws-oss.beachgeek.co.uk/364)  is a language-agnostic tool for managing and migrating database schemas using modern DevOps principles. It offers two workflows: Declarative - Similar to Terraform, Atlas compares the current state of the database to the desired state, as defined in an HCL, SQL, or ORM schema. Based on this comparison, it generates and executes a migration plan to transition the database to its desired state, and Versioned - Unlike other tools, Atlas automatically plans schema migrations for you. Users can describe their desired database schema in HCL, SQL, or their chosen ORM, and by utilising Atlas, they can plan, lint, and apply the necessary migrations to the database.

Rotem Tamir has put together a blog post, [Passwordless Schema Migrations on RDS with Atlas](https://aws-oss.beachgeek.co.uk/365) that shows how you can use this tool with AWS IAM authentication, which enables you to perform passwordless schema migrations on your Amazon RDS databases.

### Demos, Samples, Solutions and Workshops

**Extended CDK Workshop**

You can now try out a new CDK workshop, the [Extended CDK Workshop](https://aws-oss.beachgeek.co.uk/366). This workshop is aimed at folk who are already familiar with CDK and will cover how you can use CDK Pipeline for application deployment, importing existing CloudFormation resources and their use inside CDK, and how to transform your CDK stack to other languages supported by CDK. Make sure you check out the pre-req's.

**live-streaming-on-aws**

[live-streaming-on-aws](https://aws-oss.beachgeek.co.uk/367) this open source solution is a reference deployment that demonstrates how to deliver highly available live streaming video through an integrated workflow between Elemental Cloud and AWS. The solution is deployed using a CloudFormation template with a lambda backed custom resource, available in both NodeJS and Python. The README also provides a link to documentation that will help you get this up and running.

![overview of solution architecture for livestreaming](https://github.com/aws-solutions/live-streaming-on-aws/blob/main/architecture.png?raw=true)

**cognito-user-profiles-export-reference-architecture**

[cognito-user-profiles-export-reference-architecture](https://aws-oss.beachgeek.co.uk/368) is an open source reference architecture for exporting user profiles, group details, and group memberships from an Amazon Cognito User Pool to an Amazon DynamoDB global table using AWS Step Functions and AWS Lambda. This solution uses an AWS Step Functions workflow (ExportWorkflow) to periodically export user profiles, groups, and group membership details from your user pool to an Amazon DynamoDB global table with automatic, asynchronous replication to a backup Region for added resiliency. This solution is designed to provide a framework for exporting user profile and group information from your user pool, allowing you to focus on extending the solution’s functionality rather than managing the underlying infrastructure operation.

![architecture for cognito user profile exporter](https://github.com/aws-solutions/cognito-user-profiles-export-reference-architecture/blob/main/architecture-diagram.png?raw=true)

**guidance-for-custom-game-backend-hosting-on-aws**

[guidance-for-custom-game-backend-hosting-on-aws](https://aws-oss.beachgeek.co.uk/369) the AWS Game Backend Framework allows you to integrate your game clients with AWS backend services, with secure scalable identity management and authentication, and integrations to commonly used game platform identity providers and game engines. The framework consists of three key components: Custom identity component, that can be deployed with AWS Cloud Development Kit. Supports guest identities, Steam, Sign in with Apple, Google Play, and Facebook, lightweight game engine SDK:s for Unreal Engine 5, Unity 2021 (and up), and Godot 4; and a sample backend component templates to get started with backend feature development. I am been meaning to play around with Godot for a while, so maybe this is the excuse I need to get started.

![overview of game backend hosting](https://github.com/aws-solutions-library-samples/guidance-for-custom-game-backend-hosting-on-aws/blob/main/highlevelarchitecture.png?raw=true)

### AWS and Community blog posts

**Community round up**

Every week I am amazed at how many great posts I come across from the community, and this week is no different. Great stuff, please keep them coming.

This week I want to start with[ Manage Airflow connections with Terraform and AWS SecretsManager ](https://aws-oss.beachgeek.co.uk/35w)from AWS Community Builder Ivica Kolenkaš, which is a must read post for anyone working with Apache Airflow who wants to improve how they manage Airflow Connections. I was speaking with Heitor (Powertools for Lambda guru) who mentioned that this uses Powertools for Lambda under the hood, which is super awesome. From Apache Airflow to Cedar, and this time it is AWS Community Builder Daniel Aniszkiewicz who has written [Authorization and Amazon Verified Permissions - A New Way to Manage Permissions Part X: AVP-CLI](https://aws-oss.beachgeek.co.uk/35x) and shares details of his open source tool [avp-cli](https://aws-oss.beachgeek.co.uk/35y) that helps you work with AWS Verified Permissions (AVP) via the command line. Make sure you check Daniel's other posts on both AVP and Cedar. Something a little different next, with AWS Hero Yasunori Kirimoto writing [Use 3D map library with API key function of Amazon Location Service](https://aws-oss.beachgeek.co.uk/35z) which shows you how you can integrate open source mapping libraries with the Amazon Location Service. To wrap up this section this week we have Greg Foster from Graphite who has put together, [How an AWS Aurora feature cut our DB costs by 90%](https://aws-oss.beachgeek.co.uk/360). If you are using PostgreSQL then make sure you read this one.

![graph from graphite blog](https://www.datocms-assets.com/85246/1691689997-untitled.png?fm=webp)

**Apache Airflow**

I have written in the [past](https://dev.to/aws/getting-mwaa-local-runner-up-on-aws-cloud9-1nhd) about setting up developer environments and tools to work with Apache Airflow. Last week I took a look at a new project from Kaxil Naik, director of engineering at Astronomer and all round Apache Airflow good guy. Kaxil has put together airflowctl, a command-line tool for managing Apache Airflow projects, and making it super easy to get up and running. What does it do? Well, it helps you install and use different versions of Apache Airflow, work with Variables and Connections, provide live logs, and more. Read more about how you can get started by reading my post, [A look at airflowctl, a tool to help developers manage Apache Airflow projects](https://aws-oss.beachgeek.co.uk/36a) where I get you up and running using AWS Cloud9 as my cloud based developer IDE.

![image of airflow ui for airflowctl](https://res.cloudinary.com/practicaldev/image/fetch/s--rwBEEWZh--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://ricsuepublicresources.s3.eu-west-1.amazonaws.com/images/blog/airflowctl.png)

> **Note** As of writing, the version of airflowctl is now 0.2.6 so make sure you grab the latest version and check the README for updates.

**OpenZFS**

OpenZFS is an open source file system for high-performance applications. In the post, [Sharing data on Amazon FSx for OpenZFS across Linux and Windows clients](https://aws-oss.beachgeek.co.uk/35o) Virgil Ennes show how to use Network File System (NFS) protocol version 3 and different authentication methods available to concurrently share data stored on FSx for OpenZFS data for your Linux and Windows clients. [hands on]

**SBOM**

An Software Bill of Materials (SBOM) is a formal, machine-readable record of all the libraries, modules, and dependencies used in building a software product and the relationships between these components. In this post, [Using SBOM to find vulnerable container images running on Amazon EKS clusters](https://aws-oss.beachgeek.co.uk/35p) Samuel Baruffi, Emmanuel Saliu, and Rishi Gera present an approach of using SBOM to find container images running in your Amazon EKS cluster that have vulnerable software component inside. The solution components address some of the key considerations in using SBOM, like automatic generation of SBOM for container images, centralized storage for SBOM inventory, and the ability to search through the inventory quickly when you need to. This is a must read this week folks. [hands on]

![overview of SBOM architecture for EKS workloads](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2023/07/26/diagram.png)

**Big Data roundup**

We had a few posts last week on some of your favourite open source data projects.

* [Use a reusable ETL framework in your AWS lake house architecture](https://aws-oss.beachgeek.co.uk/35s) explores some of the challenges building out your lake house architecture and integrating it into your source systems [Apache Hudi, Apache Airflow]

![overview of etl framework architecture](https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2023/08/04/Fig2-reusable-etl2.png)

* [Optimizing performance of Apache Spark workloads on Amazon S3](https://aws-oss.beachgeek.co.uk/35t) outlines the step-by-step process to optimize Apache Spark jobs on Amazon EKS and Amazon S3 [Apache Spark]
* [Implement a serverless CDC process with Apache Iceberg using Amazon DynamoDB and Amazon Athena](https://aws-oss.beachgeek.co.uk/35u) provides a solution to handle incoming semi-structured datasets from source systems and effectively determine changed records and load them into Iceberg tables [Apache Iceberg]

**Other posts and quick reads**

* [Getting Started with CloudWatch agent and collectd](https://aws-oss.beachgeek.co.uk/35j) looks at how to do a basic setup of collectd, an open source daemon for data collection, and the Amazon CloudWatch agent on an Amazon EC2 Linux instance, sharinf some examples of what you can do with this data on CloudWatch dashboards and alarms [hands on]

![example dashboard for collectd data](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2023/08/14/dashboard-in-alarm-masked-2.png)

* [Centralized AWS Observability with Grafana Cloud for Monitoring, Analytics, and Optimization](https://aws-oss.beachgeek.co.uk/35k) shows you how you can easily integrate AWS services with the Grafana Cloud, now supporting over 60 AWS services [hands on]
* [Running high-fidelity O3DE simulations in AWS RoboMaker](https://aws-oss.beachgeek.co.uk/35n) provides a tutorial on how to create a Docker image from an O3DE sample application (Robot Vacuum Sample) and deploy it as a simulation job in AWS RoboMaker [hands on]

![example image of robomaker and o3de](https://d2908q01vomqb2.cloudfront.net/a9334987ece78b6fe8bf130ef00b74847c1d3da6/2023/08/07/running-controlling-robot-vacuum.png)

* [Manage case-insensitive data in PostgreSQL](https://aws-oss.beachgeek.co.uk/35q) discusses different options to deal with the case-insensitive data in PostgreSQL and their use cases, pros, and cons [hands on]
* [SSG vs SSR in Next.js Web Applications: Choosing the Right Rendering Approach](https://aws-oss.beachgeek.co.uk/35r) explains the key differences between Server-Side Rendering (SSR) and Static Site Generation (SSG), when to choose one over the other, and how to deploy either approach using AWS Amplify [hands on]

### Quick updates

**Apache Airflow**

Amazon Managed Workflows for Apache Airflow (MWAA) is a managed orchestration service for Apache Airflow that makes it easier to set up and operate end-to-end data pipelines in the cloud. Apache Airflow version 2.6 introduces important security updates and bug fixes that enhance the security and reliability of your workflows. This update also brings improvements such as better handling of stuck tasks, ability to add notifications to DAGs with notifiers, and an improved user interface featuring a graph tab in the grid view.

Hernan Garcia, Parnab Basak, and Shubham Mehta have put together a must read post on this update, [Introducing Apache Airflow version 2.6.3 support on Amazon MWAA](https://aws-oss.beachgeek.co.uk/35i) that provides more details on the new features you can start using, as well as sharing info about the in place upgrade.

![screenshot of mwaa new features](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2023/08/09/BDB-3651-IMG1.jpg)

**PostgreSQL**

Amazon Relational Database Service (Amazon RDS) for PostgreSQL 16 Beta 3 is now available in the Amazon RDS Database Preview Environment, allowing you to evaluate the pre-release of PostgreSQL 16 on Amazon RDS for PostgreSQL. You can deploy PostgreSQL 16 Beta 3 in the Preview Environment that has the benefits of a fully managed database, making it simpler to set up, operate, and monitor databases. PostgreSQL 16 Beta 3 in Preview Environment also includes support for logical decoding on read replicas, AWS libcrypto (AWS-LC), and over 80 PostgreSQL extensions. 

The PostgreSQL community released PostgreSQL 16 Beta 3 on August 10, 2023 that enables logical replication from standbys and includes numerous performance improvements. PostgreSQL 16 also adds support for SQL/JSON constructors and identity functions, more query types that can use parallelism, introduction of using SIMD CPU acceleration, and the ‘pg_stat_io’ view that provides statistics on I/O usage. 

The Amazon RDS Database Preview Environment supports the latest generation of instance classes that are retained for a maximum period of 60 days and are automatically deleted after the retention period. Amazon RDS database snapshots that are created in the preview environment can only be used to create or restore database instances within the preview environment. You can use the PostgreSQL dump and load functionality to import or export your databases from the preview environment. 

**AWS Distro for OpenTelemetry (ADOT)**

Last week saw the general availability of the Kubernetes attributes processor in the AWS Distro for OpenTelemetry (ADOT) collector. ADOT is a secure, production-ready, AWS supported distribution of the OpenTelemetry project. With this release, customers can use the ADOT collector to enable filtering and correlation use cases with Kubernetes-specific metadata such as a namespace or pod.

Customers can now use the Kubernetes attributes processor in the ADOT collector. At collection time, when using receivers such as the StatsD receiver, X-Ray receiver, or the OpenTelemetry Protocol (OTLP) receiver, you can configure the Kubernetes attributes processor in the pipeline to enrich the telemetry signals with Kubernetes-specific metadata. You can then, at analysis time, use this metadata to enable the filtering of traces and metrics from Kubernetes workloads. For example, in Amazon Managed Grafana, you can filter traces and metrics by Kubernetes namespace or pod. Further, the Kubernetes-specific metadata can be used to aid correlation in observability destinations including Amazon Managed Service for Prometheus, Amazon CloudWatch, AWS X-Ray, and Amazon OpenSearch.

You can configure and deploy the latest version of the ADOT collector by using AWS CloudFormation templates, the AWS Command Line Interface, kubectl commands, or the ADOT EKS add-on.

**GraphQL**

AWS AppSync is a managed service that makes it easier to build scalable APIs that connect applications to data. With AppSync, API developers can write resolvers to define the business logic that connects their AppSync GraphQL and Pub/Sub APIs to data. Now, developers can use JavaScript to write their unit resolvers, pipeline resolvers, and AppSync functions that are executed on the AppSync JavaScript (APPSYNC_JS) runtime.

With JavaScript support for unit resolvers, developers can now handle single data source access patterns in JavaScript with a single resolver. Developers can continue to handle complex access patterns and mix Velocity Template Language (VTL) functions along with JavaScript functions in a pipeline resolver. AppSync provides two NPM libraries to simplify local development: @aws-appsync/eslint-plugin, to catch and fix problems quickly during development; and @aws-appsync/utils to provide type validation (e.g.: when using TypeScript) and autocompletion in code editors. To test their business logic, developers can use AppSync’s evaluate-code API command.

Dive deeper by checking out this post from Brice Pelle, [AWS AppSync now supports JavaScript for all resolvers in GraphQL APIs](https://aws-oss.beachgeek.co.uk/35h) who shows you how to get started.

![screenshot of new options of javascript and vtl](https://d2908q01vomqb2.cloudfront.net/0a57cb53ba59c46fc4b692527a38a87c78d84028/2023/08/12/js-unit-resolvers-3.png)

**AWS SAM**

On a related note was new that AWS Serverless Application Model (AWS SAM) now supports building serverless GraphQL APIs with AWS AppSync. You try this out for yourself by checking out the post from Kevin Schwarz, [AWS SAM now supports GraphQL Applications with AWS AppSync](https://aws-oss.beachgeek.co.uk/35l).

![overview of AWS SAM and AWS AppSync](https://d2908q01vomqb2.cloudfront.net/0a57cb53ba59c46fc4b692527a38a87c78d84028/2023/08/10/SAM_appsync_API.png)

**AWS SDK for Java**

AWS SDK for Java team announced last week the latest addition to the AWS SDK for Java 2.x: the Amazon Simple Storage Service (Amazon S3) Cross-Region Client feature. With this new feature, you can effortlessly access Amazon S3 buckets in different AWS Regions by using a single client configured for cross-region access. Join us as we explore the possibilities and convenience offered by this exciting enhancement. Read more by checking out this post from John Vegas, [Introducing S3 cross-region support in the AWS SDK for Java 2.x](https://aws-oss.beachgeek.co.uk/35m)

**GitLab**

You can now use your GitLab.com source repository to build, test, and deploy code changes using AWS CodePipeline. Connect your GitLab.com account using AWS CodeStar Connections, and use the connection in your pipeline to automatically start a pipeline execution on changes in your repository.

### Videos of the week

**CDK Patterns - The Good, The Bad and The Ugly**

Eoin Shanaghy and Luciano Mammino from AWS Bites dive into the world of CDK Patterns , building blocks that can transform how you build and deploy your cloud applications. They walk you through what CDK Patterns are, where to find them, and why you'll want to use them!

{{< youtube rCJOBcjxjao >}}

**Threat Composer**

Back in episode [#155](https://dev.to/aws/aws-open-source-newsletter-155-42kj) I featured a project called Threat Composer (also shown on [Build on Open Source S206](https://www.youtube.com/watch?v=aHfdAb51y0c)). The tools was featured in this talk at re:Inforce, and will help you look at what might go wrong as you build your threat models. The tool aims to help you brainstorm and consistently compose useful examples with the time you have available.

{{< youtube CaYCsmjuiHg >}}

**AWS-LC: FIPS certification journey and how it’s used on AWS**

AWS-LC is an open-source cryptographic library from AWS. AWS-LC is integrated into foundational components to make it easier for organisations to use FIPS-validated cryptography in their applications. Learn how AWS is planning to deploy AWS-LC FIPS to AWS, and discover the benefits of the migration. Designed for developers and security experts, this video provides the knowledge and skills you need to use AWS-LC in your own applications. 

{{< youtube WKNGnCkZiQE >}}

**Open Source Brief**

Now featured every week in the AWS Community Radio show, grab a quick five minute recap of the weekly open source newsletter from yours truly.

{{< youtube KO61NJWxKBw >}}

Check out the [playlist here](https://aws-oss.beachgeek.co.uk/359).

**Build on Open Source**

For those unfamiliar with this show, Build on Open Source is where we go over this newsletter and then invite special guests to dive deep into their open source project. Expect plenty of code, demos and hopefully laughs. We have put together a playlist so that you can easily access all (sixteen) of the episodes of the Build on Open Source show. [Build on Open Source playlist](https://aws-oss.beachgeek.co.uk/episodes).

We are currently planning the third series - if you have an open source project you want to talk about, get in touch and we might be able to feature your project in future episodes of Build on Open Source.

# Events for your diary

If you are planning any events in 2023, either virtual, in person, or hybrid, get in touch as I would love to share details of your event with readers. 

**Developer eXperience and serverless**
**Sigma Technology Cloud, Malmö, Sweden, August 29th 5:30pm**

The AWS Skåne Meetup features a great line up as always, but of interest to open source developers will be the session on Powertools for AWS Lambda that none other than Heitor Lessa will be delivering, and our good friend and AWS Community Builder Lars Jacobsson who will be demonstrating his tool [samp-cli](https://aws-oss.beachgeek.co.uk/34c). If you are in the area, make sure you reserve your spot. You can find more on the meetup page for [Developer eXperience and serverless](https://aws-oss.beachgeek.co.uk/34b)

**RADIUSS AWS Tutorials: Learn how to use a modern HPC software stack**
**Online, throughout August 2023**

Check out this series of online tutorials happening throughout August demonstrating how to use several GPU-ready projects in the cloud and on premises. Follow along on your own EC2 instance (provided). No previous experience necessary. Lots of open source technologies are covered in this series, so if you are looking to get started in this space, check out the details on the information page, [Learn how to use a modern HPC software stack](https://aws-oss.beachgeek.co.uk/31h). Brenden Bouffler has also put together a great blog post, [Call for participation: RADIUSS Tutorial Series 2023](https://aws-oss.beachgeek.co.uk/31i) that dives deeper into some of these topics and provides further information.

**Developer Webinar Series, Open Source At AWS**
**Online, 7th September 11am - 2pm AEST**

As part of the Developer Webinar series, we are delighted to showcase three sessions that look at open source on AWS. We have Aish Gunasekar who will be talking about "Leveraging OpenSearch for Security Analytics". I will be doing a talk on Cedar, in my session "Next generation Authz with Cedar", and to wrap things up we have Keita Watanabe who will be looking at "Scaling LLM/GenAI deployment with NVIDIA Triton on Amazon EKS". The sessions are technical deep dives, and there will be Q&A as well.

Jump over to the [registration page and sign up](https://aws-oss.beachgeek.co.uk/34j), and hope to see many of you there.

**Building ML capabilities with PostgreSQL and pgvector extension**
**YouTube, 14th September 4pm UK time**

Generative AI and Large Language Models (LLMs) are powerful technologies for building applications with richer and more personalized user experiences. Application developers who use Amazon Aurora for PostgreSQL or Amazon RDS for PostgreSQL can use pgvector, an open-source extension for PostgreSQL, to harness the power of generative AI and LLMs for driving richer user experiences. Register now to learn more about this powerful technology.

Watch it [live on YouTube](https://aws-oss.beachgeek.co.uk/325).

**Build ML into your apps with PostgreSQL and the pgvector extension**
**YouTube, 21st September 4pm UK time**

This office hours session is a follow up for those who attended the fireside chat titled "Building ML capabilities into your apps with PostgreSQL and the open-source pgvector extension". Others are also welcome. Office hours attendees can ask questions related to this topic. Application developers who use Amazon Aurora for PostgreSQL or Amazon RDS for PostgreSQL can use pgvector, an open-source extension for PostgreSQL, to harness the power of generative AI and LLMs for driving richer user experiences. Join us to ask your questions and hear the answers to the most frequently asked questions about the pgvector extension for PostgreSQL.

Watch it [live on YouTube](https://aws-oss.beachgeek.co.uk/326).

**Open Source Summit, Europe**
**September 19th-21st, Bilboa Spain**

"Open Source Summit is the premier event for open source developers, technologists, and community leaders to collaborate, share information, solve problems, and gain knowledge, furthering open source innovation and ensuring a sustainable open source ecosystem. It is the gathering place for open-source code and community contributors." You will find AWS as well as myself at Open Source Summit this year, so come by the AWS booth and say hello - from the glimpses I have seen so far, it is going to be awesome! Find out more at the official site, [Open Source Summit Europe 2023](https://aws-oss.beachgeek.co.uk/31f).

**OpenSearchCon**
**Seattle, September 27-29, 2023**

Registration is now open source OpenSearchCon. Check out this post from Daryll Swager, [Registration for OpenSearchCon 2023 is now open!](https://aws-oss.beachgeek.co.uk/2zk) that provides you with what you can expect, and resources you need to help plan your trip.

**CDK Day, 2023**
**Online, 29th September 2023**

Back for the fourth instalment, this Community led event is a must attend for anyone working with infrastructure as code using the AWS Cloud Development Kit (CDK). It is intended to provide learning opportunities for all users of the CDK and related libraries. The event will be live streamed on YouTube, and you check more at the website, [CDK Day](https://aws-oss.beachgeek.co.uk/fr) 

**Open Source India**
**October 12-13th, NIMHANS Convention Center, Bengaluru**

One of the most important open source events in the region, Open Source India will be welcoming thousands of attendees all to discuss and learn about open source technologies. I will be there too, doing a talk so I would love to meet with any of you who are also planning on attending. Check out more details on their web page, [here](https://aws-oss.beachgeek.co.uk/31d).

**All Things Open**
**October, 15th-17th, Raleigh Convention Center, Raleigh, North Carolina**

I will be attending and speaking at All Things Open, looking at Apache Airflow as an container orchestrator. I will be there with a bunch of fellow AWS colleagues, and I hope to meet some of you there. Check us out at the AWS booth, where you will find me and the other AWS folk throughout the event. Check out the event and sessions/speakers at the official webpage for the event, [AllThingsOpen 2023](https://aws-oss.beachgeek.co.uk/31e)
 
**Cortex**
**Every other Thursday, next one 16th February**

The Cortex community call happens every two weeks on Thursday, alternating at 1200 UTC and 1700 UTC. You can check out the GitHub project for more details, go to the [Community Meetings](https://aws-oss.beachgeek.co.uk/2h5) section. The community calls keep a rolling doc of previous meetings, so you can catch up on the previous discussions. Check the [Cortex Community Meetings Notes](https://aws-oss.beachgeek.co.uk/2h6) for more info.

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)

### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)

