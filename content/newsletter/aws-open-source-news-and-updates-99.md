---

title: 'AWS open source news and updates #99'
date: '2022-02-07'
tags : [ oss-newsletter, aws open source, PostgreSQL, Apache Airflow, AWS CDK, Redis, GraphQL, Apollo GraphQL, Kubernetes, AWS EKS, Monokle, Rust,  Visual Flow, Apache Cassandra, OpenZFS, Lustre, Apache Kafka, MariaDB]

---

## Feb 7th, 2022 - Instalment #99

Newsletter #99. While Nena gave you 99 red balloons, I give you the latest version of the AWS open source news letter. This week we feature more great new open source projects including a project to help you with drift detection in your CloudFormation stacks, new Terraform modules, an open-source prometheus exporter, some AWS CDK resources and sample projects and more. This weeks AWS and Community posts cover PostgreSQL, Apache Airflow, AWS CDK, Redis, GraphQL, Apollo GraphQL, Kubernetes, AWS EKS and more. Make sure you check out the Quick Updates to stay on top of whats new in your favourite open source projects. In the videos, we feature Monokle, Rust, and a getting started with Visual Flow guide. Finally, we wrap up with Events, with a few happening later this week. As always, if you have an event/meet-up you want me to feature, just drop me a message and I will include it.

**Job of the week**

[Principal Developer Advocate, Containers](https://aws-oss.beachgeek.co.uk/1b7)

Amazon Web Services (AWS) is looking for a talented leader to lead the Bottlerocket and Amazon Linux Developer Advocacy program, part of Container services. Find out more, and apply via [this link](https://aws-oss.beachgeek.co.uk/1b7). If you want to have a chat about what it is like, feel free to drop me a mail.

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Bhavani Ravi, Matthieu Napoli, Luc van Donkersgoed, Anouar Zaaber, Cem Altuner, Julien Grinsztajn, Amine El Mallem, Mohamed-Ali ELOUAER, Armando Segnini, Takahiro Ishii,  HariKrishna Boorgadda, Rajesh Madiwale, Swanand Kshirsagar, Florian Chazal, Severin Gassauer-Fleissner, Zahi Ben Shabat, Nicolas Moutschen, Dmitri Pavlov, Gunnar Grosch and Zachariah Dzielinski.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest open source projects

#### Community

**bitesizedserverless**

[bitesizedserverless](https://aws-oss.beachgeek.co.uk/1bv) AWS Hero and Community Builder Luc van Donkersgoed has created a new repo to centralise all the various projects he has been working on. Worth a check to see if you might find something useful.

**cfn-drift-remediation**

[cfn-drift-remediation](https://aws-oss.beachgeek.co.uk/1bp) Cloudar have created this tool that uses the Cloud Control API to remediate drift that was detected on a CloudFormation stack. If you want to remind yourself, [AWS Cloud Control API](https://aws-oss.beachgeek.co.uk/1bq) a set of common application programming interfaces (APIs) that are designed to make it easy for developers to manage their AWS and third-party services.

**ssm-provisioner**

[ssm-provisioner](https://aws-oss.beachgeek.co.uk/1br) this tool from Zachariah Dzielinski provides the ability to provision AWS instances via SSM using Terraform. The project provides examples of how to get started and a short reason on why Zachariah created this project. 

**coroot-aws-agent**

[coroot-aws-agent](https://aws-oss.beachgeek.co.uk/1bs) is an open-source prometheus exporter that gathers metrics from AWS services.

**aws-default-vpc-deleter**

[aws-default-vpc-deleter](https://aws-oss.beachgeek.co.uk/1bo) if you are looking for a script to automate the deletion of an AWS VPC, then look no further as Cem Altuner has put together something that does exactly this. Use with caution of course, as it will delete stuff.

#### Tools

**TransactionChainsDataGenerator**

[TransactionChainsDataGenerator](https://aws-oss.beachgeek.co.uk/1bi) is a random data generation program to simulate a record of bank transactions between individuals. It first generates a configurable number of parties, some of which are marked as "suspicious", and then a configurable number of transactions between them. Each transaction's "originator party" and "beneficiary party" are selected entirely randomly from the pool, and the transaction amount is also random. The program outputs RDF files in Turtle syntax. To see how you can use this, check out the post from Severin Gassauer-Fleissner and Zahi Ben Shabat, [Financial Crime Discovery using Amazon EKS and Graph Databases](https://aws-oss.beachgeek.co.uk/1bj)

![arch](https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2022/01/28/Figure2-archFinCrime.png)

**single-ec2-cdk**

[single-ec2-cdk](https://aws-oss.beachgeek.co.uk/1bt) This is a simple CDK project that creates a single EC2 instance and copies a common set of tools needed for doing cloud development. This script handles the undifferentiated heavy lifting of creating a development environment, including a bunch of typical tools you might need. Make sure you read the doc, which covers some nice use cases I think this project is a good fit for.

**amazon-emr-with-delta-lake**

[amazon-emr-with-delta-lake](https://aws-oss.beachgeek.co.uk/1c0) this project contains code that show how to read from and write to Delta tables with Amazon EMR and help you quickly explore the main features of Delta Lake.

**aws-appflow-custom-connector-python**

[aws-appflow-custom-connector-python](https://aws-oss.beachgeek.co.uk/1bu) Amazon AppFlow is a fully managed integration service that enables you to securely transfer data between Software-as-a-Service (SaaS) applications like Salesforce, SAP, Zendesk, Slack, and ServiceNow, and AWS services like Amazon S3 and Amazon Redshift. This project enables customers and third party developers to build custom source and/or destination connectors for the AppFlow service. If you are not a Python developer, but prefer Java, then you are in luck as you can use [aws-appflow-custom-connector-java](https://aws-oss.beachgeek.co.uk/1bz).

#### Demos and Samples

**cdk-amazon-mwaa-cicd**

[cdk-amazon-mwaa-cicd](https://aws-oss.beachgeek.co.uk/1bc) a nice open sourced solution to automate the deployment and configuration of Managed Apache Airflow (MWAA) environments to programmatically author, schedule and monitor workflows. This repository demonstrates how one customer, ENGIE, were able to deploy a CI/CD pipeline for an Amazon MWAA project to automate the ingestion process from Salesforce using Airflow with an example. Anouar Zaaber, Julien Grinsztajn, Amine El Mallem, Mohamed-Ali ELOUAER, and Armando Segnini have collaborated in a detailed walkthrough blog post, [How ENGIE scales their data ingestion pipelines using Amazon MWAA](https://aws-oss.beachgeek.co.uk/1bd)

![arch](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2022/01/19/bdb-1772-image001.png)

### AWS and Community blog posts


**Apache Airflow**

In [Merging Python Modules](https://aws-oss.beachgeek.co.uk/1by) Bhavani Ravi shares lessons learned in her quest to automate the task of merging multiple Python modules into a single one for Apache Airflow, and the solution she created. [hands on]

**Apollo GraphQL**

Apollo Federation is an architecture and specification used to build and connect multiple distributed backend GraphQL (micro)services, exposing a single endpoint and GraphQL schema to API clients and consumers. In [Apollo GraphQL Federation with AWS AppSync](https://aws-oss.beachgeek.co.uk/1bh), Florian Chazal explains how to setup an Apollo Federation Gateway connected to GraphQL subgraphs powered by AWS AppSync/ [hands on]

![illustration](https://d2908q01vomqb2.cloudfront.net/0a57cb53ba59c46fc4b692527a38a87c78d84028/2022/01/26/Apollo-AppSync-Federation1.png)

**PostgreSQL**

In a two part post, HariKrishna Boorgadda, Rajesh Madiwale, and Swanand Kshirsagar discuss two ways to audit your PostgreSQL databases using the pgAudit extension. Check out the first post, [Part 1: Audit Aurora PostgreSQL databases using Database Activity Streams and pgAudit](https://aws-oss.beachgeek.co.uk/1bg) and follow the link to part two in the article. [hands on]

![design](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2022/01/14/DBBLOG-1592-image039.png)

**Redis**

Takahiro Ishii takes a look how Amazon MemoryDB for Redis is a great candidate for gaming  leaderboard backends in the post, [Rethinking Game Leaderboards with Amazon MemoryDB for Redis](https://aws-oss.beachgeek.co.uk/1bf)

**Serverless Framework**

Matthieu Napoli provides a nice summary of what to expect with [Serverless v3](https://aws-oss.beachgeek.co.uk/1bx) in his post, [Serverless Framework V3 Is Live!](https://aws-oss.beachgeek.co.uk/1bw)

**Other posts worth checking out**

Last week, these posts also caught my eye.

* [How to mount Linux volume and keep mount point consistency](https://aws-oss.beachgeek.co.uk/1c1) explains how to mount Linux volumes and keep mount points preserved when the instance type is changed or the instance is rebooted.
* [Continuous Delivery of Amazon EKS Clusters Using AWS CDK and CDK Pipelines](https://aws-oss.beachgeek.co.uk/1bk) shows the use of AWS CDK and CDK Pipelines to deploy Amazon EKS clusters. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2022/01/27/Containers-blue-green-cdk-1024x529.png)

* [Evolving REST APIs with GraphQL using AWS AppSync Direct Lambda Resolvers](https://aws-oss.beachgeek.co.uk/1be) learn how to use resources from an existing REST API built with AWS Serverless Application Model SAM, AWS API Gateaway, and AWS Lambda to work as AWS AppSync Direct Lambda Resolvers. [hands on]
* [Use AWS Systems Manager custom Inventory to locate Log4j files on managed nodes](https://aws-oss.beachgeek.co.uk/1bl) will show you how to use AWS System Manager's custom inventory data type to locate Log4j JAR files on Windows and Amazon Linux EC2 instances and hybrid managed nodes. [hands on]
* [Migrate SQL Server to Amazon Aurora PostgreSQL using best practices and lessons learned from the field](https://aws-oss.beachgeek.co.uk/1bm) find out everything you need to successfully re-architect and migrate SQL Server to Aurora PostgreSQL.

### Quick updates

**Apache Cassandra**

Amazon Keyspaces (for Apache Cassandra) a fully managed Cassandra compatible database service, is now is in scope for FedRAMP Moderate compliance to help you run highly regulated Cassandra workloads more easily. Federal Risk and Authorisation Management Program (FedRAMP) is a US government-wide program that delivers a standard approach to the security assessment, authorisation, and continuous monitoring for cloud products and services. Now, you can run Cassandra workloads that are subject to FedRAMP Moderate compliance more easily by using Amazon Keyspaces, a fully managed and serverless database service.

**OpenZFS**

Amazon FSx for OpenZFS now supports full-copy volumes to make it easier to clone and experiment with your data, enabling you to quickly capture the results of your cloning-based testing for long-term use.

**Lustre**

Amazon FSx for Lustre is now authorized as FedRAMP Moderate in US East (N. Virginia), US East (Ohio), US West (N. California), US West (Oregon) and as FedRAMP High in AWS GovCloud (US-West) and AWS GovCloud (US-East). Amazon FSx for Lustre is also approved as Department of Defense Cloud Computing Security Requirements Guide Impact Level 2 (DoD SRG IL-2) in these regions.

**MariaDB**

Amazon RDS for MariaDB now supports MariaDB version 10.6. This release introduces multiple MariaDB features to enhance the performance, scalability, reliability and manageability of your workloads, including MyRocks storage engine, IAM integration, Flexible Upgrades, Delayed replication, Oracle PL/SQL compatibility, Atomic DDL and more. Read more details in the announcement, [Amazon RDS for MariaDB now supports MariaDB 10.6](https://aws-oss.beachgeek.co.uk/1bb)

**Apache Kafka**

Amazon Managed Streaming for Apache Kafka (Amazon MSK) now offers an option to provision storage throughput for Amazon MSK, enabling customers with high throughput workloads to seamlessly scale I/O without having to provision additional brokers. By provisioning up to 1000 MiB/s of throughput to Amazon MSK storage volumes, you can scale I/O requirements past 250 MiB/s without having to provision additional brokers. When configured, you pay a low rate for the amount of storage throughput provisioned in the clusters.

### Videos of the week

**Visual Flow**

Visual Flow, powered by Apache Spark, is a cloud-native open source ETL tool based on the Apache Spark unified analytics engine with a Graphical User Interface. Join Dmitri Pavlov as he shows you how to install this project on AWS.

{{< youtube lITIK-p77EE >}}

**Rust on AWS**

A must watch video this week comes from my colleague Gunnar Grosch, who is joined by Nicolas Moutschen for a look at using Rust on AWS!

{{< youtube 1oa3UKfGw6Y >}}

**Monokle**

This week, the Containers from the Couch team look at Monokle from Kubeshop for managing full lifecycle of your manifests. [Monokle](https://aws-oss.beachgeek.co.uk/1bn) is an open source project for creating, validating, debugging and managing manifests! 🚀

{{< youtube lsMTOVJJ84o >}}


### Events for your diary

If you have an event you want me to publish here, please contact me and I will include it in this listing. 

**Melbourne AWS Programming and Tools Meetup**
**AWS Lambda Powertools for Python**
**Wednesday, 9 February 9th, 6:00 pm AEDT**

Michael Walmsley, a Serverless Architect from MyWizard AiOps at Accenture, will present a workshop introducing the AWS Lambda Powertools for Python. The workshop will cover the core utilities provided by the Powertools open source library and showcase the improved developer experience and cleaner code when using it to create your lambda projects!

Read more and [sign up here](https://aws-oss.beachgeek.co.uk/1ba).

**AWS HPC Speeds and Feeds**
**February 9, 2022 | 8:30AM - 10:00AM PST**

Over the past year, AWS HPC has introduced a host of new HPC products and services (many of them using open source technologies and project) to help today's scientists, engineers and researchers to run their workloads at scale for less cost and faster. Join us to hear directly from the engineers to learn more about the latest and greatest innovations from AWS HPC. To find out more about the talks, read the blog post [Join us for our HPC “Speeds n’ Feeds”](https://aws-oss.beachgeek.co.uk/1b0) to find out more, and use [this link to register](https://aws-oss.beachgeek.co.uk/1b1).

**Cloud DevSecOps with Bridgecrew and Terraform**
**Thursday, February 10th at 2pm GMT**

From scanning infrastructure as code (IaC) for security misconfigurations to implementing automated DevSecOps workflows, this workshop will provide a hands-on experience to automate your cloud security.

Read more and register, [AWS Dev Day Cloud DevSecOps with Bridgecrew and Terraform](https://aws-oss.beachgeek.co.uk/1ay)

**HashiTalks 2022**
**Thursday, Feb 17th**

The 24-hour HashiTalks is back for its fourth edition on Thursday, February 17. Tune-in to hear from and learn with fellow practitioners.

Find your local chapter, find more details and [register here](https://aws-oss.beachgeek.co.uk/1b3).


**OpenSearch**
**Every Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting - Feb2022](https://aws-oss.beachgeek.co.uk/1az)

**GitOpsCon Europe**
**May 17th, Valencia Spain**

GitOpsCon Europe is designed to foster collaboration, discussion, and knowledge sharing on GitOps. This event is aimed at audiences that are new to GitOps as well as those currently using GitOps within their organisation. Get connected with others that are passionate about GitOps. Learn from practitioners about pitfalls to avoid, hurdles to jump, and how to adopt GitOps in your cloud native environment.

The event is vendor-neutral and is being organised by the CNCF GitOps Working Group. Topics include getting started with GitOps, scaling and managing GitOps, lessons learned from production deployments, technical sessions, and thought leadership.

Read more about this from the official page [here](https://events.linuxfoundation.org/gitopscon-europe/).


### CFP

**GitOpsCon**
**CFP closes Feb, 14th**

GitOpsCon Europe (#GitOpsCon) is designed to foster collaboration, discussion, and knowledge sharing on GitOps. This event is aimed at audiences that are new to GitOps as well as those currently using GitOps within their organization. Get connected with others that are passionate about GitOps. Learn from practitioners about pitfalls to avoid, hurdles to jump, and how to adopt GitOps in your cloud native environment.

The CFP is now open, and you can read more about, and [submit your own session here](https://aws-oss.beachgeek.co.uk/1b2).

**Apache Airflow**
**CFP closes March, 14th**
A heads up to folks who are interested in all things Apache Airflow. Apache Airflow Summit 2022 has been announced and the call for papers (cfp) is now open. The bar for sessions is always very high, so looking forward to this event already.

If you have an idea for a talk, why not submit one via the cfp process. Check out the event, [Apache Airflow Summit 2022](https://aws-oss.beachgeek.co.uk/19e)

If you maybe have wanted to do a session, then I am very happy to help with feedback or coaching to help you feel more comfortable in creating and/or delivering your session. If this something that has been on your mind, but you just needed a little support, PLEASE get in touch.

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)