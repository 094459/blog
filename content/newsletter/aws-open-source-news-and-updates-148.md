---
title: 'AWS open source newsletter #148'
date: '2023-03-12'
tags : [ oss-newsletter, aws open source, Kubernetes, OpenSearch, AWS SAM, MySQL, MariaDB, PostgreSQL,  Apache Kafka, Apache Iceberg, Grafana, AWS Copilot, Crossplane, Flux,RabbitMQ, Apache TinkerPop, PyTorch, Apache Hudi, Apache Iceberg, Delta Lake ]

---

## March 13th, 2023 - Instalment #148

**Welcome**

Hello and a warm welcome to edition #148 of the AWS open source newsletter, the only newsletter on the planet that serves you up a weekly dose of the freshest, latest open source projects on AWS. This week we have projects such as  "iam-ape" a tool to help you grapple with your IAM policies, "amazon-emr-cli" a nice command line tool to package and deploy your Spark jobs on Amazon EMR, "duckdb-athena-extension" that helps you import data from Amazon Athena into DuckDB, "terraform-aws-email-files-dropped-in-s3" a helpful tool to easily email you attachments automatically, "cloud-queue-for-quantum-devices" a tool to help Quantum researchers across the world, "aws-private-ca-matter-infrastructure" a sample reference architecture for setting up a secure, private certificate authority, "aws-sam-cli-java-examples" will help you deploy your Java apps via AWS SAM, "mpartman" a PostgreSQL partition manager, "aws-do-pcluster" simplifying how to run AWS ParallelCluster, "staticwebsite-cli" a very nice too to help you easily deploy static web sites, and more!

If that was not enough, we also feature content on some of your favourite open source technologies. This week we have content covering Kubernetes, OpenSearch, AWS SAM, MySQL, MariaDB, PostgreSQL,  Apache Kafka, Apache Iceberg, Grafana, AWS Copilot, Crossplane, Flux, RabbitMQ, Apache TinkerPop, PyTorch, Apache Hudi, Apache Iceberg, and Delta Lake.

Before diving into the newsletter, make sure you read the next segment if you are using Kubernetes in any way.

**ACTION: Important news for Builders who use Kubernetes**

If you are using Kubernetes, then please make sure you check out this information post, [k8s-registry-deprecation](https://aws-oss.beachgeek.co.uk/2lm) about the imminent freezing of the k8s.gcr.io image registry. The Kubernetes project runs a community-owned image registry called registry.k8s.io to host its container images. On the 3rd of April 2023, the old registry k8s.gcr.io will be frozen and no further images for Kubernetes and related subprojects will be pushed to the old registry. This registry registry.k8s.io replaced the old one and has been generally available for several months.  Read more in the post, [k8s.gcr.io Image Registry Will Be Frozen From the 3rd of April 2023](https://aws-oss.beachgeek.co.uk/2ln)

**Do you have a .NET on AWS open source project?**

The .NET on AWS team is committed to supporting a healthy and thriving .NET OSS ecosystem.  They have put together a GitHub repo,  [https://github.com/aws/dotnet-foss](https://aws-oss.beachgeek.co.uk/2lo) that shows one of the ways we are supporting open source for .NET Builders. If this is you, make sure you check this out.

**Feedback**

Please please please take 1 minute to [complete this short survey](https://pulse.buildon.aws/survey/PJRTOUMK) and get some exclusive content as a thank you.

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes: Cristian Măgherușan-Stanciu, Damon Cortesi, Mehmet Nuri Deveci, Steven Cook, Maximilian Schellhorn, Stephen Mallette,  Arabinda Pani, Abhinav Sarin, Josh Hart, Flora Wu, Daniel Li, Stephen Heverin, Kalyan Janaki, Ankit Mishra, Louis Muller,  Yota Hamaoka, Hailong Cui, Binlong Gao, Zhou Su, Xuesong Luo, Viktor Farcic and Whitney Lee.

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution.*

#### Tools

**staticwebsite-cli**

[staticwebsite-cli](https://aws-oss.beachgeek.co.uk/2lw) this Rust CLI tool makes it easy to deploy a static website to AWS. It builds and hosts the website, sets up a CDN and DNS, and provisions an SSL certificate. In order to manage DNS, the tool needs to be able to configure endpoints in your DNS zone. You must have an existing Route53 zone corresponding to the --domain-zone specified. 

**iam-ape**

[iam-ape](https://aws-oss.beachgeek.co.uk/2lz) or AWS Policy Evaluator (APE) is a new project from Orca that takes all of your AWS IAM policies attached to a User, Group, or Role object, and presents you with a single policy, summarising all of their actual permissions. To get a better idea of how this tool works, Tohar Braun has put together a blog post, [Meet IAM APE: An Open Source Tool to Simplify AWS IAM Policy Management](https://aws-oss.beachgeek.co.uk/2m0) that provides more details on what you can do with it.

![overview of iam-ape tool](https://lh3.googleusercontent.com/4aT0XT4zImrnEJWI7D6jqQJWACDYNIyJKPI8RyDsLvrM2Ckac565E4Dn33v8ZTusFUgZ23c38QFYn-4NrRiakPKlia4L_7gO0vBvIeLu3JhaJxSJnmCZEUtO4Z2HUFkphxEeyuNRauaN4AlnFeQweIk)

**duckdb-athena-extension**

[duckdb-athena-extension](https://aws-oss.beachgeek.co.uk/2lj) is a new project (very much alpha stage) from all round good egg Damon Cortesi (the first of two contributions this week) that provides an experimental extension for DuckDB, allowing you to import data by scanning an Athena table. Check the docs for the constraints and how to use this project.

**amazon-emr-cli**

[amazon-emr-cli](https://aws-oss.beachgeek.co.uk/2ly) this is Damon's second project, and this tool helps you package and deploy your Amazon EMR Spark jobs. This is still very fresh, and under active development. Give it a go and provide your feedback to Damon and let him know what you think.

**terraform-aws-email-files-dropped-in-s3**

[terraform-aws-email-files-dropped-in-s3](https://aws-oss.beachgeek.co.uk/2li) a new project from Cristian Măgherușan-Stanciu, who is on a crusade to create a new open source project every week. This weeks project sends an email when a file is dropped into an S3 bucket, including the file as an attachment.  As Cristian said in a post about the project:

> "The idea came from the AWS Reddit, where someone asked about this.
>
> Then I realized I'd also love to have something like this so I started building it.
>
> My use case is to save time reading the daily CSV reports from the AWS Marketplace, "conveniently" - for sure only for the AWS Marketplace team 😀 - dropped in an S3 bucket, one of the many usability papercuts of the AWS Marketplace seller user experience.

**cloud-queue-for-quantum-devices**

[cloud-queue-for-quantum-devices](https://aws-oss.beachgeek.co.uk/2le) is an open source, cloud-based application which allows quantum researchers to easily and securely submit and manage workloads destined for quantum devices, from anywhere in the world. This too will help you  collaborate with researchers around the world. You can read more about this by checking out the supporting blog post, [New open source tool expands access to lab-based quantum prototypes: Cloud Queue for Quantum Devices](https://aws-oss.beachgeek.co.uk/2ld).

![architecture for quantum device queue](https://d2908q01vomqb2.cloudfront.net/5a5b0f9b7d3f8fc84c3cef8fd8efaaa6c70d75ab/2023/03/06/architecture-1024x613.png)

**mpartman**

[mpartman](https://aws-oss.beachgeek.co.uk/2lr) is a PostgreSQL partition management package. You can use Mpartman to manage partitions and subpartitions in PostgreSQL versions 11 – 15. With Mpartman, you can create RANGE and LIST partitions, merge, split, detach, and drop partitions. In addition to this, Mpartman supports partition retention fucntion and includes the set of partition information functions and views. The documentation covers typical use cases, installation, usage, and how it works under the cover.

**aws-do-pcluster**

[aws-do-pcluster](https://aws-oss.beachgeek.co.uk/2ls) the [Do Framework](https://aws-oss.beachgeek.co.uk/2lt) is a DevOps framework focused on simplicity, intuitiveness, and productivity. It helps you get more done.  This project aims to make it easy to use AWS Parallel Cluster, by leveraging these principals. This project builds a container which contains all prerequisites, tools that are useful when working with Parallel Cluster, and the latest version of the pcluster cli. It comes with useful scripts to configure, create, and delete parallel cluster infrastructure.

![screenshot of parallel cluster ui](https://github.com/aws-samples/aws-do-pcluster/blob/main/aws-pcluster-ui-1024.png?raw=true)

### Demos, Samples, Solutions and Workshops

**template-for-closed-network-system-workloads-on-aws**

[template-for-closed-network-system-workloads-on-aws](https://aws-oss.beachgeek.co.uk/2lu) if you are operating in highly restrictive environments, then this repo will be of interest. It provides an example architecture that you can provision via CDK, that deploys a closed network infrastructure. The README provide an example use case:

> In local government systems that require a high level security and network restrictions, we need to configure our architecture with characteristics from on-premise, like "Closed area networks" and "Allow NW access routes from AWS to on-premise network". 

![architecture of closed networks for workloads ](https://github.com/aws-samples/template-for-closed-network-system-workloads-on-aws/blob/main/docs/images/template_architecture_en.png?raw=true)

**amazon-msk-topic-resource**

[amazon-msk-topic-resource](https://aws-oss.beachgeek.co.uk/2lv) is a custom CloudFormation resource that can be used to create and manage Kafka topics in MSK clusters. With this repo, you can deploy and manage Kafka topics in the same way you manage other application infrastructure.

![how it works](https://github.com/aws-samples/amazon-msk-topic-resource/blob/main/assets/flow.jpg?raw=true)

**aws-private-ca-matter-infrastructure**

[aws-private-ca-matter-infrastructure](https://aws-oss.beachgeek.co.uk/2lp) this repo demonstrates the use of AWS CDK to set up Public Key Infrastructure (PKI) infrastructure using AWS Private CA to help you meet the requirements of the Matter PKI Certificate Policy (CP) approved on October 26, 2022. Matter is a new standard for smart home security and device interoperability. Matter uses X.509 digital certificates to identify devices. Matter certificates can be issued only by CAs that comply with the Matter PKI Certificate Policy (CP).

**rosa-install-codepipeline**

[rosa-install-codepipeline](https://aws-oss.beachgeek.co.uk/2ll) This repository provides AWS CloudFormation templates, a Dockerfile, Bash scripts to deploy a PrivateLink Red Hat OpenShift on AWS (ROSA) cluster using a AWS CodePipeline. Includes security best practices such as use of Secrets Manager, KMS, immutable ECR repository, closed security groups with temporary internet access during installation and routing egress traffic through a separate Egress VPC connected through a Transit Gateway, storage of all installation parameters and logs in CodeBuild etc. This setup creates 3 private VPCs and subnets for deploying a PrivateLink ROSA cluster following AWS best practices. This is an end-to-end setup resulting in a functional ROSA cluster where a Kubernetes application can be readily deployed

**aws-codecommit-s3-backups-with-terraform**

[aws-codecommit-s3-backups-with-terraform](https://aws-oss.beachgeek.co.uk/2lk) is a Terraform pattern to help you backup your AWS CodeCommit repositories to Amazon S3.

![architecture of codecommit backup](https://github.com/aws-samples/aws-codecommit-s3-backups-with-terraform/blob/main/img/architecture.png?raw=true)

**aws-sam-cli-java-examples**

[aws-sam-cli-java-examples](https://aws-oss.beachgeek.co.uk/2lq)  provide examples of the different methods that are available to build java applications using AWS SAM. You can follow along in the blog post, [Building serverless Java applications with the AWS SAM CLI](https://aws-oss.beachgeek.co.uk/2l3) where Mehmet Nuri Deveci, Steven Cook, and Maximilian Schellhorn provide an overview of the common ways to build Java applications for Lambda with the AWS SAM CLI .

![overview of using sam to deploy java applications](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2023/02/28/sam6.png)


### AWS and Community blog posts

**Open Source Data Lakes**

In the post, [An Introduction to Modern Data Lake Storage Layers](https://aws-oss.beachgeek.co.uk/2lx) colleague Damon Cortesi dives hands on into Apache Hudi, Apache Iceberg, and Delta Lake taking a look at each of these engines and providing insights into how they function under the hood and his thoughts of the differences in each. If you find yourself wanting to know more about these different projects that on the surface do similar things, then I recommend you dive right in. [hands on]

**Apache TinkerPop**

Apache TinkerPop™ is an open source graph computing framework for both graph databases (OLTP) and graph analytic systems (OLAP). Stephen Mallette takes a look at some of the new features you can find in his post, [Exploring new features of Apache TinkerPop 3.6.x in Amazon Neptune](https://aws-oss.beachgeek.co.uk/2l6). There are plenty of new features to get excited about, so whether you are just starting out in graph databases and analytics, or a seasoned pro, dive in and catch up on the new capabilities. [hands on

**PostgreSQL**

If you are a regular reader of this newsletter, you may know that I love posts that cover collecting and analysing performance metrics. I really enjoyed reading this post, [Monitor Amazon RDS for PostgreSQL and Amazon Aurora PostgreSQL performance using PGSnapper](https://aws-oss.beachgeek.co.uk/2l7) where Arabinda Pani and Abhinav Sarin look at how you can set up and use PGSnapper to periodically collect PostgreSQL database metrics and run customised queries to identify performance bottlenecks. [hands on]

![architecture of pgsnapper metrics collection](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2023/03/03/DBBLOG-2076-image001-cropped.png)

We had more great posts on PostgreSQL last week, and Josh Hart and Maximilian Schellhorn put together this post, [Choose the right PostgreSQL data access pattern for your SaaS application](https://aws-oss.beachgeek.co.uk/2lf) where they explore the different access patterns for PostgreSQL in a multi-tenant environment. It explores how factors such as AWS IAM Auth, compute isolation model and the database isolation model influence your implementation strategy. Well worth a read. [hands on]

**Apache Iceberg**

Apache Iceberg is an open table format for very large analytic datasets, which captures metadata information on the state of datasets as they evolve and change over time. In the post, [Use Apache Iceberg in a data lake to support incremental data processing](https://aws-oss.beachgeek.co.uk/2l8) Flora Wu and Daniel Li look at how the Apache Iceberg framework helps resolve some of the challenges of modern data lakes, and walk you though a solution to process incremental data as well as how to tweak performance. [hands on]

![apache iceberg on aws](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2023/02/22/Iceberg_architecture.png)

**Grafana**

Grafana is an open source analytics and interactive visualisation web application. You can use it to visualise any kind of data, and in this post, [Visualize database privileges on Amazon Redshift using Grafana](https://aws-oss.beachgeek.co.uk/2l9)  Yota Hamaoka shows how you can use some predefined Grafana dashboards to visualisation database privileges of Amazon Redshift.  Database administrators can use these dashboards to quickly navigate through identities, objects, and privileges without writing SQL. [hands on]

![example dashboard for redshift and grafana](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2023/02/17/BDB-2424-8.png)

**Other posts and quick reads**

* [Implementing a pub/sub architecture with AWS Copilot](https://aws-oss.beachgeek.co.uk/2lh) walks you through how you can use AWS Copilot CLI to easily implement a publisher service and subscriber worker services on Amazon ECS and AWS Fargate [hands on]

* [Deploying self-managed MariaDB high availability using Amazon EBS Multi-Attach](https://aws-oss.beachgeek.co.uk/2la) is a hands on guide on how to set up a self-managed MariaDB with improved availability using the Amazon EBS Multi-Attach feature [hands on]

![architecture of self managed MariaDB high availability using EBS](https://d2908q01vomqb2.cloudfront.net/e1822db470e60d090affd0956d743cb0e7cdf113/2023/02/28/Screenshot-2023-02-28-at-11.08.17-AM.png)

*  [Deploy an Amazon RDS for PostgreSQL and MySQL Multi-AZ DB cluster using Terraform modules](https://aws-oss.beachgeek.co.uk/2lb) shows you how you can implement deployment strategies using Terraform modules to drive consistency with repeatable deployments and ensure best practices are implemented at every stage of continuous delivery and deployment pipelines [hands on]

![using terraform to automate RDS postgres and mysql deployments](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2023/02/11/Picture2.jpg)

* [Hosting YOLOv8 PyTorch models on Amazon SageMaker Endpoints](https://aws-oss.beachgeek.co.uk/2lc)  explains how to host a pre-trained YOLOv8 (a popular object detection model) PyTorchModel on a SageMaker endpoint and test the inference results by invoking the endpoint [hands on]

![architecture of hosting a pytorch model on sagemaker](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2023/02/28/ML13353_AWSArchitecture-1024x605.png)

### Quick updates

**OpenSearch**

Hailong Cui, Binlong Gao, Zhou Su, Xuesong Luo provided a quick update on OpenSearch improvements on indexing in their post, [Index Management UI enhancements](https://aws-oss.beachgeek.co.uk/2l2). In the post they look at some of the new features added to the UI that help you better manage your indices. 

![example opensearch ui index management screenshot](https://opensearch.org/assets/media/blog-images/2023-02-28-admin-panels-for-index-operations/index-mapping-editor.png)

**RabbitMQ**

Amazon MQ is a managed message broker service for Apache ActiveMQ and RabbitMQ that makes it easier to set up and operate message brokers on AWS.  Amazon MQ now provides support for RabbitMQ version 3.10.17, which includes several important fixes and performance optimisations to the previously supported version, RabbitMQ 3.10.10. 

**MariaDB**

Amazon Relational Database Service (Amazon RDS) for MariaDB now supports Amazon RDS Optimized Writes enabling up to 2x higher write throughput at no additional cost. This is especially useful for RDS for MariaDB customers with write-intensive database workloads, commonly found in applications such as digital payments, financial trading, and online gaming.

In RDS for MariaDB, you are protected from data loss due to unexpected events, such as a power failure, using a built-in feature called the “doublewrite buffer”. But this method of writing takes up to twice as long, consumes twice as much I/O bandwidth, and reduces the throughput and performance of your database. Starting today, Amazon RDS Optimized Writes provides you with up to 2x improvement in write transaction throughput on RDS for MariaDB by writing only once while protecting you from data loss and at no additional cost. Optimized Writes uses Torn Write Prevention, a feature of the AWS Nitro System, to reliably and durably write to table storage in one step.

Amazon RDS Optimized Writes is available as a default option from RDS for MariaDB version 10.6.10 and higher on db.r6i, db.r6g, db.r5b, db.x2iedn and db.x2idn database instances. 

**MySQL**

Amazon Aurora MySQL-Compatible Edition now supports authentication of database users using Microsoft Active Directory. You can use Active Directory to authenticate with Amazon Aurora using AWS Directory Service for Microsoft Active Directory or with your on-premise Active Directory by establishing a trusted domain relationship.

With support for Active Directory authentication in Amazon Aurora MySQL-Compatible Edition, you have access to single sign-on and centralised authentication of database users. Single sign-on reduces the operational overhead of database user management across multiple authentication approaches and credentials. Moreover, a centralised authentication approach enables customers to leverage native Active Directory credential management capabilities to manage password complexities and rotation. This allows you to effectively keep pace with the myriad of compliance and security requirements across the globe and improve the security posture of your critical business assets.

Active Directory authentication is supported for Aurora MySQL version 3.03 (compatible with MySQL 8.0.26) and higher.

**PostgreSQL**

Amazon Relational Database Service (Amazon RDS) for PostgreSQL now supports the latest minor versions PostgreSQL 14.7, 13.10, 12.14, and 11.19. 

**Apache Kafka**

Amazon Managed Streaming for Apache Kafka (Amazon MSK) now supports Apache Kafka version 3.3.2 for new and existing clusters. Apache Kafka 3.3.2 includes several bug fixes and new features that improve performance. Some of the key features include enhancements to fetch from the closest replica and metrics. Amazon MSK will continue to use and manage Zookeeper for quorum management in this release. 

For a complete list of improvements and bug fixes, see the Apache Kafka [release notes for 3.3.2](https://aws-oss.beachgeek.co.uk/2l4).

### Videos of the week

**Building Internal Developer Platforms (IDPs) with Crossplane and Flux**

Join the Containers from the Couch crew and Viktor Farcic and Whitney Lee as they  look at popular GitOps concepts and tooling like Crossplane and Flux, and demo Crossplane.

{{< youtube jIVMJ0NbqtE >}}

**Apache Kafka**

Join Stephen Heverin, Kalyan Janaki, Ankit Mishra, and Louis Muller as they uncover Amazon MSK Operational Best Practices. Expect plenty of good info and live demos.

{{< youtube -B_dFO8iqwg >}}


**Build on Open Source**

For those unfamiliar with this show, Build on Open Source is where we go over this newsletter and then invite special guests to dive deep into their open source project. Expect plenty of code, demos and hopefully laughs. We have put together a playlist so that you can easily access all (eight) of the episodes of the Build on Open Source show. [Build on Open Source playlist](https://aws-oss.beachgeek.co.uk/24u)

# Events for your diary

If you are planning any events in 2023, either virtual, in person, or hybrid, get in touch as I would love to share details of your event with readers. 

**Build on Open Source**
**March 17th, twitch.tv/aws**

The third episode of Build on Open Source features special guest AWS Community Builder John Preston who will be showing us ecs-compose-x, an open source tool to help simplify how you configure and deploy applications on AWS. This project got a name check from the Containers from the Couch crew last week, giving it the big thumbs up so make sure you tune in and find out more about this project. Really looking forward to this one as John is a super star open source developer.

See you there on [twitch.tv/aws](https://twitch.tv/aws), Friday 17th at 9am GMT, 10am CET.

**Power Up your Kubernetes**
**March 15th, AWS Office Zurich, Switzerland**

If you want to improve architecture, scaling and monitoring of your applications that run on AWS Elastic Kubernetes Service, this event is for you. During this event you will learn to scale Kubernetes applications with Karpenter, monitor your workloads, and build SaaS architectures for Kubernetes. 

Find out more and save your place by heading over to the registration page, [Power up your Kubernetes on AWS](https://aws-oss.beachgeek.co.uk/2jd)

**Everything Open**
**March14-15th Melbourne, Australia**

A new event for the fine folks in Australia. Everything Open is running for the first time, and the organisers (Linux Australia) have decided to run this event to provide a space for a cross-section of the open technologies communities to come together in person. Check out the [event details here](https://aws-oss.beachgeek.co.uk/2ds). The CFP us currently open, so why not take a look and submit something if you can.

**FOSSASIA**
**April 13th-15th, Singapore**

FOSSASIA Summit 2023 returns as an in-person and online event, taking place from Thursday 13th April to Saturday 15th April at the Lifelong Learning Institute in Singapore. 

If you are interested in attending in person, or virtually, find out more about the event at the [FOSSASIA Summit 2023 page](https://aws-oss.beachgeek.co.uk/2iq).

**AWS Community Nordics**
**April, 20th Helsinki**

The AWS Community Day Nordics is a free full day event for AWS users to come together to network, learn from each other and get inspired. The event is organised by the community - for the community. The cfp is currently open, so if you are in the area and want to talk then here is your chance. Check out the full event details and save your space here, [AWS Community Nordics registration page](https://aws-oss.beachgeek.co.uk/2l5)

**Cortex**
**Every other Thursday, next one 16th February**

The Cortex community call happens every two weeks on Thursday, alternating at 1200 UTC and 1700 UTC. You can check out the GitHub project for more details, go to the [Community Meetings](https://aws-oss.beachgeek.co.uk/2h5) section. The community calls keep a rolling doc of previous meetings, so you can catch up on the previous discussions. Check the [Cortex Community Meetings Notes](https://aws-oss.beachgeek.co.uk/2h6) for more info.

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)

### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)

