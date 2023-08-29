---
title: 'AWS open source newsletter #171'
date: '2023-08-29'
tags : [ oss-newsletter, aws open source, Cedar, Kubernetes, aws-iam-authenticator, LocalStack, AWS SAM, Open Data Maps, AWS CDK, PostgreSQL, OpenSearch, Memcached, MySQL, MariaDB, OpenShift, Grafana, Prometheus, Ratify]
---

## August 29th, 2023 - Instalment #171

Welcome to #171 of the AWS open source newsletter, the newsletter created for developers passionate about open source. Thanks to the wonderful August bank holiday here in the UK, we are publishing a day later than usual. If you have not read this newsletter before, we feature new projects, content from across the open source and AWS community, and share events and videos that you should check out.

This weeks new projects include ways to automate deployments within your AWS environments at scale, a tool to help you run scripts within AWS Lambda, a tool that helps you simplify setting up a CI/CD pipeline full of open source security scanning tools, a Python library for Cedar (as well as a demo app that uses this library), and more! We have content on open source projects this week that include Cedar, Kubernetes, aws-iam-authenticator, LocalStack, AWS SAM, Open Data Maps, AWS CDK, PostgreSQL, OpenSearch, Memcached, MySQL, MariaDB, OpenShift, Grafana, Prometheus, and Ratify.

As always, make sure you do not skip the video section or the events section. And as always, if you have an open source event you would like me to share with the readers, just drop me a line.

**Feedback**

Before you dive in however, I need your help!  Please please please take 1 minute to [complete this short survey](https://www.pulse.aws/promotion/10NT4XZQ) and you will forever have my gratitude! 

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes:  Sai Kiran Kshatriya, Cal Heldenbrand, Stephen Kuenzli, Jeremy Cowan, Frank Osasere Idugboe, Lionel Tcham, Allen Helton, Stephanie May, Katie Kowals, Emina Torlak, Jehu Gray, Abiola Olanrewaju, Serge Poueme, Anand Komandooru, Li Liu, Neil Potter, Vivek Shrivastava, Sai Vennam, Imaya Kumar Jagnnathan, Elamaran Shanmugam, and Mikhail Shapirov

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution. The projects mentioned here do not represent any formal recommendation or endorsement, I am just sharing for greater awareness as I think they look useful and interesting!*

#### Tools

**aws-orga-deployer**

[aws-orga-deployer](https://aws-oss.beachgeek.co.uk/36u) makes it easier to deploy and manage infrastructure-as-code at the scale of an AWS Organizations. It enables to deploy Terraform or CloudFormation templates and to execute Python scripts in multiple AWS accounts and multiple regions, making it particularly suitable for building AWS foundations (or Landing Zones). To get started, you develop modules (Terraform or CloudFormation templates or Python scripts), create a package definition file to specify which modules to deploy in which accounts and regions and using which parameters, and let AWS Orga Deployer deploy modules and manage dependencies between deployments. Check out the nice documentation, which provides an overview of the key concepts and shows you how you can get started.

**lambda_shell**

[lambda_shell](https://aws-oss.beachgeek.co.uk/36s) is a tool from Cal Heldenbrand that provides a Lambda Runtime Interface Client written in pure Bash and Curl. It allows you to quickly create a simple bash script to run in Lambda for use cases like cron jobs or tasks that you want to quickly set up and deploy. This also implements the Lambda Function URL API to to write HTTP endpoints in bash. A very detailed README provides lots of examples that should help you explore and experiment with this project. Be sure to let Cal know what you think, and check out [Cal's post on Reddit](https://www.reddit.com/r/aws/comments/15xdknr/new_project_lambda_shell/) for more details.

**simple-code-scanning-pipeline**

[simple-code-scanning-pipeline ](https://aws-oss.beachgeek.co.uk/36p)- The Simple Code Scanning Pipeline project creates a pipeline that AWS users can use to automatically scan a wide variety of code for security and syntax issues. This repo sets up a ready-to-use development environment integrated with a CI pipeline with security and DevOps best practices. Upon successful deployment, it will configure an AWS CodeCommit Git repository (you can specify an existing one if you want), and a multi-stage pipeline  that integrates a number of open source tools such as: Bandit for finding common security issues in Python code, Flake8 for ensuring well-formatted Python code, cfn_nag for CloudFormation template linting and security checks, Checkov for Terraform linting, Gitleaks for secret detection, Shellcheck for Shell script linting, SqlFluff for SQL linting, Unit testing of RDK Custom Config rules, and more. Check out the repo for the full list of tools used.

**cedar-py**

[cedar-py](https://aws-oss.beachgeek.co.uk/36q) is a Python wrapper that helps you use the (Rust) Cedar Policy library from Python. You can use cedarpy to check whether a request is authorised by the Cedar Policy engine, and validate the format of your policies. I cannot recommend this library enough, and is perfect if you are a Python developer looking to lean into the excitement around Cedar. In fact, check out the demo section below where I put this library to use in a very simple Flask demo app. Thank you Stephen, great stuff!

### Demos, Samples, Solutions and Workshops

**amazon-eks-scaling-with-keda-and-karpenter**

[amazon-eks-scaling-with-keda-and-karpenter](https://aws-oss.beachgeek.co.uk/36t) this repository contains the necessary files and instructions to deploy and configure KEDA (Kubernetes-based Event Driven Autoscaling) and Karpenter (Kubernetes Node Autoscaler) on an Amazon Elastic Kubernetes Service (EKS) cluster. KEDA enables autoscaling of Kubernetes pods based on the number of events in event sources such as Azure Service Bus, RabbitMQ, Kafka, and more. Karpenter is a Kubernetes node autoscaler that scales the number of nodes in your cluster based on resource usage. README contains plenty of good documentation as well as a video to help you get started.

![demo of eks scaling with keda and karpenter](https://raw.githubusercontent.com/aws-samples/amazon-eks-scaling-with-keda-and-karpenter/main/img/Keda.gif)

**cedar-flask-demo**

[cedar-flask-demo](https://aws-oss.beachgeek.co.uk/36r) I have been playing around with [cedar-py](https://aws-oss.beachgeek.co.uk/36q) from Stephen Kuenzli (see above) and put together a very simple Flask based demo showing how you can use it to simplify authorisations within your Flask applications. I hope you will be able to see how easy it is to use, and spark some ideas and perhaps more comprehensive demos from Python developers out there!

![screenshot of demo cedar python app](https://github.com/094459/cedar-flask-demo/blob/main/images/cedar-python-demo.png?raw=true)

### AWS and Community blog posts

**Community round up**

As usual, we begin the round up of written content by exploring the community posts. We start with [Programmatically accessing the EKS cluster API endpoint without a kubeconfig file](https://aws-oss.beachgeek.co.uk/36k), where Jeremy Cowan shares a quick recipe on how you can use the aws-iam-authenticator Go module to programmatically call the Kubernetes API without loading the Kubernetes client SDK. Sticking with Kubernetes, we have AWS Community Builder Frank Osasere Idugboe who has put together a nice introduction, [Understanding the ABCs of Kubernetes](https://aws-oss.beachgeek.co.uk/36l),  for those who are looking for a nice Kubernetes primer. Next we have another AWS Community Builder, Lionel Tchami, who looks at how you can get started with LocalStack, an open source project that helps you mock AWS services locally, in their post [LocalStack: Emulate AWS Services for Local Development & Testing](https://aws-oss.beachgeek.co.uk/36m). AWS Hero Allen Helton's post, [A Beginner's Guide to the Serverless Application Model (SAM)](https://aws-oss.beachgeek.co.uk/36n), is the perfect guide for those of you wanting to dip your toes into the world of Serverless Application Model. To close this weeks roundup I have, [Open Data Maps for AWS](https://aws-oss.beachgeek.co.uk/36o) where Stephanie May and Katie Kowals provide a super interesting read on the thinking and processes behind creating web maps exclusively from open data, and how to express different purposes as part of its design.

![overview of open data maps for aws](https://stamen.com/wp-content/uploads/2023/08/image2-1.png)

**Cedar**

Emina Torlak has put together essential reading for those of you who want to know more about Cedar, the open source project that provides a domain specific language to help you build next generation authorisation within your applications. In the post, [How we designed Cedar to be intuitive to use, fast, and safe](https://aws-oss.beachgeek.co.uk/36f), Emina shows  how Cedar’s authorisation semantics, data model, and policy syntax work together to make the Cedar language intuitive to use, fast, and safe. This weeks must read post.

![overview of cedar authorisation diagram](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2023/08/18/img1-4.png)

**AWS CDK**

If you use the AWS Cloud Development Kit (CDK) then make sure you do not miss this post from Jehu Gray, Abiola Olanrewaju, and Serge Poueme. In [How to add notifications and manual approval to an AWS CDK Pipeline](https://aws-oss.beachgeek.co.uk/36g) they provided a guided walkthrough on how to set up notifications and add a manual approval stage to your  AWS CDK Pipeline. [hands on]

![overview of aws cdk manual approval](https://d2908q01vomqb2.cloudfront.net/7719a1c782a1ba91c031a682a0a2f8658209adbf/2023/08/17/figure-1.jpg)

**PostgreSQL**

pg_partman is an extension to create and manage both time-based and serial-based table partition sets in your PostgreSQL databases. In the post, [Automate the archive and purge data process for Amazon RDS for PostgreSQL using pg_partman, Amazon S3, and AWS Glue](https://aws-oss.beachgeek.co.uk/36j) Anand Komandooru, Li Liu, Neil Potter, and Vivek Shrivastava showcase how to use AWS Glue workflows to automate the archive and restore process in RDS for PostgreSQL database table partitions using this tool and Amazon S3 as archive storage. [hands on]

![overview of pg_partman archiving on RDS PostgreSQL](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2023/08/15/BDB-3508-arch.png)

**Other posts and quick reads**

* [Measure cluster performance impact of Amazon GuardDuty EKS Agent](https://aws-oss.beachgeek.co.uk/36e) looks at how Amazon EKS Runtime Monitoring captures runtime activity from your Kubernetes workloads through an agent built using eBPF

![measuring kubernetes performance using eBPF](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2023/08/15/GuardDuty-Agent.png)

* [Serve distinct domains with TLS powered by ACM on Amazon EKS](https://aws-oss.beachgeek.co.uk/36h) looks at how you can serve multiple domains by using a single instance of an AWS Application Load Balancer using host-based routing with Server Name Indication (SNI) [hands on]

![overview of ACM and SNI support for EKS workloads](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2023/08/15/3-Dinstinct-Domains.png)

* [Try semantic search with the Amazon OpenSearch Service vector engine](https://aws-oss.beachgeek.co.uk/36d) provides details of a couple of demos give you an idea of the capabilities of vector-based semantic vs. word-based lexical search and what can be accomplished by utilising the vector engine for OpenSearch Serverless to build your search experiences

![demo of vector search in opensearch](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2023/08/17/BDB-3659-image.png)

* [Amazon OpenSearch Serverless expands support for larger workloads and collections ](https://aws-oss.beachgeek.co.uk/36i) dives deeper into the recent announcement that you can now scan and search source data sizes of up to 6 TB in your Amazon OpenSearch Serverless environments [hands on]

![graph of autoscaling for opensearch serverless](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2023/08/16/BDB-3627-image004.jpg)

* [Amazon OpenSearch Service H1 2023 in review](https://aws-oss.beachgeek.co.uk/36c) is a handy review of all the exciting features releases in OpenSearch Service in the first half of 2023

![screenshot of security analytics using opensearch](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2023/08/21/BDB-3530-image005.png)

### Quick updates

**Memcached**

Amazon ElastiCache for Memcached now makes it simpler and faster for you to get started with setting up an ElastiCache for Memcached cluster. The new console experience offers streamlined navigation and minimal settings required to configure a cluster, in just a few clicks. You can now create an ElastiCache for Memcached cluster by selecting from one of the three pre-defined configurations: Production, Dev/Test, and Demo. Each configuration includes default cluster settings based on best practices that are tailored to your use case.

**MySQL**

Amazon Aurora MySQL-Compatible Edition 3 (with MySQL 8.0 compatibility) now supports Percona Xtrabackup for completing physical migrations of your existing MySQL 8.x databases running on Amazon EC2 or outside of AWS. This capability makes it easier and faster to migrate large MySQL databases with complex schemas into Amazon Aurora MySQL. Percona XtraBackup allows you to perform consistent, non-blocking, online backups of your source MySQL database which can then be migrated to Aurora MySQL with minimal downtime. To complete a physical migration, customers need to create a physical backup using the Percona XtraBackup tool. You can then upload the backup files to Amazon S3 and restore them to the target Aurora MySQL 3.x cluster.

**PostgreSQL**

Amazon Relational Database Service (RDS) for PostgreSQL now supports the latest minor versions PostgreSQL 15.4, 14.9, 13.12, 12.16, and 11.21. We recommend that you upgrade to the latest minor versions to fix known security vulnerabilities in prior versions of PostgreSQL, and to benefit from the bug fixes, performance improvements, and new functionality added by the PostgreSQL community. Please refer to the PostgreSQL community announcement for more details about the release.

With this release, RDS for PostgreSQL adds support for a new extension h3-pg — an extension providing hexagonal, hierarchical geospatial indexing system, which allows you to perform spatial analysis to gain insights from large geospatial datasets. Support for PL/Rust and pg_tle now includes PostgreSQL 15.2-R2 and higher, 14.9 and higher, and 13.12 and higher. This release also includes updates for existing extensions: pg_tle is updated to 1.1.1 with support for custom data types, plrust is updated to 1.2.3 with crate support for aes, ctr, and rand, and HypoPG is updated to 1.4.0.

**MariaDB**

Amazon RDS for MariaDB now supports MariaDB major version 10.11, the latest long-term maintenance release from the MariaDB community. Amazon RDS for MariaDB 10.11 includes performance improvements that enable up to 40% higher transaction throughput than prior versions. You can deploy RDS for MariaDB 10.11 on RDS Optimized Read and Optimized Write enabled instance classes for additional performance gains. MariaDB 10.11 major version also includes improvements to authentication, information schema, system versioning, and the InnoDB storage engine made by the MariaDB community. You can leverage Amazon RDS Managed Blue/Green deployments to upgrade your databases to RDS for MariaDB 10.11.

Find out more by reading [Introducing Amazon RDS for MariaDB 10.11 for up to 40% higher transaction throughput](https://aws-oss.beachgeek.co.uk/36b) where Sai Kiran Kshatriya benchmarks Amazon RDS for MariaDB version 10.11 and compares it to version 10.6, and additionally looks at the latest features introduced by the community in MariaDB 10.11.

![benchmark graph of mariadb improvements](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2023/08/21/DBBLOG-3304-image001.png)

**OpenShift**

In May, Red Hat announced the preview of Red Hat OpenShift Service on AWS (ROSA) with hosted control planes (HCP), a new deployment model for ROSA clusters. Today, we are introducing an AWS account configuration workflow for ROSA with HCP on the AWS Management Console. Under the original ROSA deployment model, now called ROSA classic, all AWS infrastructure required to run the ROSA control plane is hosted on your AWS account. Now, you can create ROSA clusters with the control plane hosted and managed on a service account. During the preview, ROSA with HCP clusters will not incur ROSA service fees and should not be used for production workloads.

ROSA with HCP helps reduce the AWS infrastructure cost of running ROSA clusters, as the ROSA control planes are hosted and managed by Red Hat on AWS. The new deployment model reduces the ROSA cluster create time, and you can separately schedule OpenShift version upgrades for the control plane and the worker node machine pools. By moving control plane infrastructure out of your AWS account, ROSA with hosted control planes mitigates the risk that actions taken on your account lead to a degraded ROSA control plane.

### Videos of the week

**Kubernetes Observability Accelerated ft. Grafana, Prometheus, CloudWatch, CDK and Terraform**

Direct from the Containers from the Couch, Sai Vennam, Imaya Kumar Jagnnathan, Elamaran Shanmugam, and Mikhail Shapirov show you how to navigate the complex ecosystem of observability solutions that can be used with Kubernetes. They also provide a hands-on demo of a new open-source project to implement observability on Amazon EKS with CDK, aptly named "AWS Observability Accelerator for CDK".

{{< youtube F6V4vscvOeY >}}

**Container Image Signing with AWS Signer and Amazon EKS**

With container image signing you can deploy containers securely, ensuring only trusted images are running in your Kubernetes cluster. Ratify is an open source project that enables Kubernetes clusters to verify artefact security metadata prior to deployment, ensuring that only those that comply with a defined policy are deployed. Find out more about how these two things come together in another session from the folks from the Couch.

{{< youtube p5gqe5bNXXU >}}

**Open Source Brief**

Now featured every week in the AWS Community Radio show, grab a quick five minute recap of the weekly open source newsletter from yours truly.

{{< youtube 5sZPqUGTjKg >}}

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

**All Things Open**
**October, 15th-17th, Raleigh Convention Center, Raleigh, North Carolina**

I will be attending and speaking at All Things Open, looking at Apache Airflow as an container orchestrator. I will be there with a bunch of fellow AWS colleagues, and I hope to meet some of you there. Check us out at the AWS booth, where you will find me and the other AWS folk throughout the event. Check out the event and sessions/speakers at the official webpage for the event, [AllThingsOpen 2023](https://aws-oss.beachgeek.co.uk/31e)

**Open Source India**
**October 19-21st, NIMHANS Convention Center, Bengaluru**

> **Note!** Date Change

One of the most important open source events in the region, Open Source India will be welcoming thousands of attendees all to discuss and learn about open source technologies. Check out more details on their web page, [here](https://aws-oss.beachgeek.co.uk/31d).

**Cortex**
**Every other Thursday, next one 16th February**

The Cortex community call happens every two weeks on Thursday, alternating at 1200 UTC and 1700 UTC. You can check out the GitHub project for more details, go to the [Community Meetings](https://aws-oss.beachgeek.co.uk/2h5) section. The community calls keep a rolling doc of previous meetings, so you can catch up on the previous discussions. Check the [Cortex Community Meetings Notes](https://aws-oss.beachgeek.co.uk/2h6) for more info.

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)

### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)

