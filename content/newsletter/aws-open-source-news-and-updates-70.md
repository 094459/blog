---
title: 'AWS open source news and updates #70'
date: '2021-06-01'
tags : [ oss-newsletter ]
---
## 1st June, 2021 - Instalment #70

Due to it being a bank holiday in the UK, Newsletter #70 is a day later than usual.

Make sure you check out this weeks "Quick Updates" as there are some updates that I know a lot of people will be happy about, and I always share great nuggets that sometimes folk miss. More great projects this week, from iamzero which helps you simplify your identity and access management, PMapper that you will find helpful for identifying risks in your IAM configurations, an AWS CDK construct to help you deploy a VSCode server, Orkestra, a super nice project that lets you create workflows using Lambda functions a la Apache Airflow and many more. You will find blog posts from AWS and the community covering Apache Airflow, Apache Spark, Apache Zeppelin, TensorFlow, Packer, lots of containers goodies and more. Finally, do not forget the events section, which is a great seg-way into the biggest news last week...

**Open@Amazon**

Last week we announced Open@Amazon, a celebration of open source on AWS with a fabulous cast of speakers, a fantastic broad set of topics and the event will be fully live so you can get your chance to interact with the speakers and the broader open source and AWS community. Check out the blog post, [What’s up with open source at AWS? Attend Open@Amazon live on Twitch June 16](https://aws-oss.beachgeek.co.uk/jo) or just register to get a handy calendar invite [HERE](https://aws-oss.beachgeek.co.uk/jn)

**DevAx connect**

Also, later this week we have a new regular open source series by developers for developers that will be streamed live via Twitch, hosted by the awesome Heitor Lessa. The first Thursday of every month you will be able to join Heitor and invited guests as they take you through a variety of interesting open source topics, projects and more. This week we have Lars Jacobsson, and I am looking forward to it. Check out the events section for more details.

**Please help me improve this newsletter**

Thank you to those who have provided such great feedback already, I am currently reviewing and thinking how to incorporate the suggestions. I would still love to hear from more of you, and I have more AWS credit vouchers as a thank you for taking the time to complete the survey. The first 20 will get an AWS credit voucher for $25, so thank you again. It is only 5 questions, and will probably only take you a minute or two to complete.


### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Stephan Fitzpatrick, Daniel Burkhardt, Malte Luecken, Mrudhula Balasubramanyan, Imaya Kumar Jagannathan, Joerg Woehrle, Brad Kashani, Carl Youngblood, Danilo Poccia, Christian Weber, Alolita Sharma, Nizar Tyrewalla, Josiah Davis, Yin Song, Anne Hu,  Joshua McKiddy, Olivier Cruchant, Arunprasath Shankar, Mark Roy, Eli Fisher, Luke Kysow, Devarshi Shah, Horace Nelson, Brian Schiller, Mike Apted, Serhii Vasylenko, Ibrahim Cesar, Niko Virtala, Troy Ameigh and Andrew Glenn.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

**orkestra**

[orkestra](https://aws-oss.beachgeek.co.uk/kw) this new open source project from Stephan Fitzpatrick looks very promising, allowing you to create workflow tasks via Lambda functions and then orchestrate these similar to how Apache Airflow works. The documentation says "a seamless way of building observable (scheduled or event-driven) cloud-native workflows. It aims to bring a similar development experience to that of Airflow while leveraging the full power of AWS."

This is a project that is going to get some closer inspection from myself for sure.

![arch](https://raw.githubusercontent.com/knowsuchagency/orkestra/main/docs/assets/images/hello_orkestra_sfn.png)

**iamzero**

[iamzero](https://aws-oss.beachgeek.co.uk/kk) is an open source tool that helps simplify your identity and access management on AWS. IAM Zero detects identity and access management issues and automatically suggests least-privilege policies. Check out the [newly formed website](https://aws-oss.beachgeek.co.uk/km) and business that has started to help customers who want support from this tool, and you can read more about the backstory in this [post from Reddit](https://aws-oss.beachgeek.co.uk/kl). As per the Reddit post:

> The tool is in a similar space to iamlive, policy_sentry, and consoleme (all of which are worth checking out too if you're interested in making AWS security easier) but the main points of difference I see are:
> 
> * iam-zero can run transparently on any or all of your roles just by swapping your AWS SDK import to the iam-zero instrumented version or using the instrumented CLI
> 
> * iam-zero can run continuously as a service (deployed into a isolated AWS account in an organization behind an SSO proxy) and could send notifications through Slack, email etc
> 
> * iam-zero uses TLS to dispatch events and doesn't include any session tokens in the dispatched event (AWS Client Side Monitoring, which iamlive utilises, includes authentication header details in the event - however iamlive is awesome for local policy development)

**PMapper**

[PMapper](https://aws-oss.beachgeek.co.uk/kn) Principal Mapper (PMapper) is a script and library for identifying risks in the configuration of AWS Identity and Access Management (IAM) for an AWS account or an AWS organization. It models the different IAM Users and Roles in an account as a directed graph, which enables checks for privilege escalation and for alternate paths an attacker could take to gain access to a resource or action in AWS. PMapper includes a querying mechanism that uses a local simulation of AWS's authorization behavior. When running a query to determine if a principal has access to a certain action/resource, PMapper also checks if the user or role could access other users or roles that have access to that action/resource. This catches scenarios such as when a user doesn't have permission to read an S3 object, but could launch an EC2 instance that can read the S3 object.

**aurora-serverless-to-s3**

[aurora-serverless-to-s3](https://aws-oss.beachgeek.co.uk/ki) this open source project from Devetry simplifies the automation necessary to export Amazon RDS Aurora Serverless snapshots to S3 for a specific database whenever an automated snapshot is created. The project outlines how it achieves its task, provides clear examples and an AWS CDK app to help easily deploy this project. Brian Schiller has put together a short blog post, [Aurora Serverless DB Export](https://aws-oss.beachgeek.co.uk/kj) that provides some additional context. If you want to see a demo, check this short video

{% youtube lyNGeDg6EII %}

**Image-Flex**

[Image-Flex](https://aws-oss.beachgeek.co.uk/kg) is an open sourced solution from Horace Nelson that provides a robust image resizing service built on AWS Serverless technologies and used to resize, optimise, and cache images on "the edge," on the fly. If you want to know more about how you might use or deploy it, he has helpfully put together a detailed blog post, [An Open Source and Completely Serverless Image Resizing Service in AWS](https://aws-oss.beachgeek.co.uk/kh)

![arch](https://res.cloudinary.com/practicaldev/image/fetch/s--HJI5FI4v--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/8bhb9if8fn1hesm31bq2.png)

**ecs-anywhere-tutorial**

[ecs-anywhere-tutorial](https://aws-oss.beachgeek.co.uk/ke) last week one of the big announcements was the general availability of [Amazon ECS Anywhere](https://aws-oss.beachgeek.co.uk/kf), and this project/tutorial is intended to walk you through an opinionated demonstration of how ECS Anywhere works. The initial steps will show you how to deploy a (somewhat) sophisticated multi services application in an AWS region as an ECS service running on AWS Fargate. Further in the tutorial, the steps will guide you through how to deploy parts of this application on ECS Anywhere managed instances in a customer managed infrastructure outside of the AWS region. If you saw Massimo's presentation and demo, you will know how nice this was and I am looking forward to dusting off my Raspberry Pi's and trying this out for myself.

![demo](https://github.com/aws-containers/ecs-anywhere-tutorial/raw/master/images/stretched-architecture.png)

**aws-do-docker**

[aws-do-docker](https://aws-oss.beachgeek.co.uk/kd) this project provides a simple pattern for building and deployment of Docker containers to AWS. It can be used "as is" to build and run a sample container, or can be customized and used to build, test, and deploy containerized microservices, jobs, or serverless functions. Containers built using this project can be run locally or on a number of AWS compute environments by a simple change to the configuration files.

![demo](https://github.com/aws-samples/aws-do-docker/blob/main/docs/img/aws-do-docker-demo.gif?raw=true)

**serverless-rules**

[serverless-rules](https://aws-oss.beachgeek.co.uk/kv) is new project that provides a compilation of rules to validate infrastructure as code template against recommended practices. This currently provides a module for cfn-lint and a plugin for tflint. This is currently in public preview, so if you do try it out please feedback anything you find.

**cdk-vscode-fargate**

[cdk-vscode-fargate](https://aws-oss.beachgeek.co.uk/ko) this was one of my favourite projects that I came across last week, although I have not had a chance to test it out yet. cdk-vscode-fargate is a JSII construct library for AWS CDK from Mike Apted that allows you to deploy Code-server running VS Code remotely, on a AWS Fargate container. The project provides you with a quick how-to guide to get you started, so hopefully something I can try over the weekend. You can find the source code in the GitHub repository [here](https://aws-oss.beachgeek.co.uk/kp)

![arch](https://github.com/mikeapted/cdk-vscode-fargate/blob/main/diagram.png?raw=true)

**mwaa-local-runner**

[mwaa-local-runner](https://aws-oss.beachgeek.co.uk/kc) I shared this project a few weeks ago (#66) but that was for Apache Airflow 1.x, and the project has been quickly updated to align with the launch last week of Apache Airflow version 2.0.2 support in Amazon Managed Workflows for Apache Airflow (MWAA). Everything is the same, just now using the latest version.

**S3AssetDeploy**

[S3AssetDeploy](https://aws-oss.beachgeek.co.uk/kb) if you are a Ruby developer then you are going to find this open source tool from Loomly very nice indeed. The folks at Loomly use this to safely package up and deploy their web assets to Amazon S3 that are being served via Cloudfront. This gem is designed to upload and clean unneeded assets from S3 in a safe manner such that older versions or recently removed assets are kept on S3 during the rolling deploy process. It also maintains a version limit and TTL (time-to-live) on assets to avoid deleting recent and outdated versions (up to a limit) or those that have been recently removed. Nice detailed docs and clear examples too.

**amazonlinux-dind**

[amazonlinux-dind](https://aws-oss.beachgeek.co.uk/kt) this repo from Niko Virtala is an Amazon Linux 2 container image with systemd and Docker Engine, and as Niko said in his tweet:

> I built a #Docker in Docker image that meets the #ECS Agent systemd requirement, so you don't have to – you can find it from all well-stocked container registries and #GitHub
> 

### Tweet of the week

We have not had a Tweet of the week for a while, but last week there were a couple that caught my eye and worth sharing.

**Blender**

This [tweet](https://aws-oss.beachgeek.co.uk/k3) shared by John Mark, linked to an example of how the AWS open source teams are working with open source projects and foundations to strengthen upstream communities.

**AWS Copilot vs**

This [tweet](https://aws-oss.beachgeek.co.uk/k4) from Jonathan Matthews asking about using AWS Copilot vs the AWS cli started a great discussion and it was good to hear from the likes of Massimo, Romain and Efe. Massimo shared a [response](https://aws-oss.beachgeek.co.uk/k5) but make sure you check out the thread.

**AWS CDK**

Henrique Lima had [an ask](https://aws-oss.beachgeek.co.uk/k6) this week for folks who are using AWS CDK. He is specifically looking for developers interested in checking or automating compliance of infrastructure changes, to provide 30 minutes to complete a survey to help him as he works on a Change Analysis tool for his Master's thesis to do just that. 


### Community open source posts

**GraakVM**

[Converting Java Lambda functions to GraalVM native-image](https://aws-oss.beachgeek.co.uk/ks) Mark Sailes with a quick guide on how to create binary files that you can use in your Lambda functions, showing you how to configure your maven files to do this.

**OpenSearch**

Eli Fisher shared the new public roadmap for the OpenSearch project, hosted in GitHub. The roadmap shows the next several months of planned features and releases. Going forward, this roadmap will show what the maintainers and contributors of the various components of the project intend to work on and when that work aims to launch. Read more in the post, [The OpenSearch roadmap is now available on GitHub](https://aws-oss.beachgeek.co.uk/k8)

![roadmap](https://opensearch.org/assets/media/blog-images/2021-05-26-opensearch-roadmap-announcement/opensearch-roadmap.png)

**Consul Service Mesh**

[Announcing Tech Preview of Consul Service Mesh for Amazon ECS](https://aws-oss.beachgeek.co.uk/k9) Luke Kysow and Devarshi Shah wrote last week about the availability (at this stage it is a tech preview) of HashiCorp Consul service mesh for Amazon ECS, with this tech preview letting you deploy non-production versions of Consul for testing on the Fargate launch type for ECS. The post covers how it works and provides a simple Web and API example to demonstrate this further.

![arch](https://www.datocms-assets.com/2885/1622050365-consul-on-ecs.png?fit=max&fm=webp&q=80&w=2500)

**Anisible**

In the past week (and indeed this week) there have been a number of posts around how you can use open source tools as part of your CI/CD pipeline to build your applications for the Mac operating systems. In this post, [Run Ansible playbook on mac1.metal instances fleet with AWS Systems Manager](https://aws-oss.beachgeek.co.uk/ka) AWS Community Builder Serhii Vasylenko shows you how you can use Ansible in conjunction with AWS Services. 

**Reddis**

Another AWS Commuinity Builder, Ibrahim Cesar has put this post, [Redis: Exploring Redis as Serverless Database to solve idempotence in APIs](https://aws-oss.beachgeek.co.uk/kr) which is part of a series, but in this he explores what Reddis is and how to get started with it. 

### AWS and Amazon open source posts

**Assisted Log Enabler**

In my #67 newsletter I introduced you to this open source project from AWS, [assisted-log-enabler-for-aws](https://aws-oss.beachgeek.co.uk/h7) an interesting tool that helps customers manage logging for various services. Joshua McKiddy has put together this blog post, [Introducing Assisted Log Enabler for AWS](https://aws-oss.beachgeek.co.uk/k0) showing you how to use Assisted Log Enabler for AWS to ensure logging is turned on within an AWS environment. Make sure you check this out.

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/05/19/mckiddy_assisted-log-enabler-diagram.png)

**AWS Distro for OpenTelemetry**

[AWS Distro for OpenTelemetry 0.10.0 is now available with AWS Lambda layers for .Net](https://aws-oss.beachgeek.co.uk/jy) Alolita Sharma and Nizar Tyrewalla provide a quick update on the availability of version 0.10.0 of AWS Distro for OpenTelemetry (ADOT). This is now available in AWS Lambda layers for AWS X-Ray support in .Net. The latest versions of AWS Lambda layers with AWS X-Ray support are now available for the OpenTelemetry Collector, Java, Java instrumentation, JavaScript, and Python. The post also covers news of some updated sample applications as well as news that StatsD is now supported within the ADOT Collector. Read the post for the full details.

**Vim, tmux and Zsh**

As an extensive user of these tools, this post brought a huge smile to my face. In, [Enhancing data science environments with Vim, tmux, and Zsh on Amazon EC2](https://aws-oss.beachgeek.co.uk/jz) Josiah Davis, Yin Song, and Anne Hu share how you can use these tools to enable data scientists to be more productive in their day to day working environment. From providing Cloudformation templates that enable you to get this up and running yourself, to providing some great examples, this post is your must read post this week. Whether you are a data scientist or not, you can take some of the tips shared here to help you work smarter. Very nice indeed.

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/04/29/davjosia_Enhance-data-science-vim-tmux-zsh_f1.png)

**Apache Zeppelin**

Launched last week, Amazon Kinesis Data Analytics Studio uses a number of open source projects to help make it easier for customers to analyse streaming data. You can now easily launch Apache Zeppelin notebooks, and interact and work with streaming data using SQL, Python or Scala. In, [Introducing Amazon Kinesis Data Analytics Studio – Quickly Interact with Streaming Data Using SQL, Python, or Scala](https://aws-oss.beachgeek.co.uk/jw) Danilo Poccia provides you an overview of the features as well as a follow along example to help get you orientated. 

![arch](https://d2908q01vomqb2.cloudfront.net/da4b9237bacccdf19c0760cab7aec4a8359010b0/2021/05/19/KinesisAnalyticsStudio-1-1024x655.png)

My favourite part of this blog post is where Danilo writes:

> "In Kinesis Data Analytics Studio, we run the open-source versions of Apache Zeppelin and Apache Flink, and we contribute changes upstream. For example, we have contributed bug fixes for Apache Zeppelin, and we have contributed to AWS connectors for Apache Flink, such as those for Kinesis Data Streams and Kinesis Data Firehose. Also, we are working with the Apache Flink community to contribute availability improvements, including automatic classification of errors at runtime to understand whether errors are in user code or in application infrastructure."

**Apache Spark**

Bigstream is an AWS ISV Partner and pioneer in the field of hardware and software level acceleration. Brad Kashani, CEO at Bigstream, shares in this post, [Bigstream Provides Big Data Acceleration with Apache Spark and Amazon EMR](https://aws-oss.beachgeek.co.uk/ju) why acceleration has better potential than CPU scaling, the historic challenges organisations have had in implementing accelerators, and how Bigstream are able to address those for a seamless, accelerated Spark experience.

![arch](https://d2908q01vomqb2.cloudfront.net/77de68daecd823babbb58edb1c8e14d7106e83bb/2021/05/24/Bigstream-Spark-EMR-2.png)

**Packer**

Packer is an open source tool from HashiCorp for building identical machine images for multiple platforms from a single source configuration. In this post, [Building Amazon Machine Images (AMIs) for EC2 Mac instances with Packer](https://aws-oss.beachgeek.co.uk/jt) Joerg Woehrle shares best practices for building custom AMIs for EC2 Mac instances using HashiCorp Packer. Joerg covers how to create an AMI of an EC2 Mac instance, understake administrative tasks such as resizing the hard drive, resetting ec2-macos-init and installing some base software (golang) onto the image as well as demonstrating how to facilitate SSM to connect to an EC2 instance without the need to open any ports or a public IP. Read on to dive deeper...

![arch](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2021/05/24/Packer1.png)

**git**

[Use Git pre-commit hooks to avoid AWS CloudFormation errors](https://aws-oss.beachgeek.co.uk/ku) Troy Ameigh and Andrew Glenn with a post that walks you through how you can use GitHub pre-commit hooks with a number of open source tools to help address a number of common issues when using AWS Cloudformation. The post takes a look at some of those open source tools and how you can use them to help you with things like checking shell scripts, validating end of line, dealing with white space, enforcing style and much more.

![arch](https://d2908q01vomqb2.cloudfront.net/b7eb6c689c037217079766fdb77c3bac3e51cb4c/2021/03/20/customize-quick-start-example-architecture.png)

**AWS CDK**

Christian Weber provides another one of his regular monthly updates covering all things AWS CDK related, in his [CDK Corner – May 2021](https://aws-oss.beachgeek.co.uk/jx). Plenty of highlights, including updates from the recent CDK Day, news on the CDK v2 developer preview, AWS CDK for Go developer preview and a nice list of updated/new constructs you should check out. This is essential reading in my opinion, and hats off to all those listed as having their first PRs merged. Please get in touch, I have an AWS Credit voucher waiting for you..

**TensorFlow**

A couple of posts this week on TensorFlow. The first post covers how to optimise the inference latency of TensorFlow Serving in the post, [How Contentsquare reduced TensorFlow inference latency with TensorFlow Serving on Amazon SageMaker](https://aws-oss.beachgeek.co.uk/k1). Olivier Cruchant shares how one customer was able to experiment with a number of approaches to find an optimum solution for hosting their inference endpoints.

![arch](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2021/03/25/Capture-d%E2%80%99%C3%A9cran-2021-03-25-%C3%A0-13.03.31.jpg)

Following that we have the post, [Host multiple TensorFlow computer vision models using Amazon SageMaker multi-model endpoints](https://aws-oss.beachgeek.co.uk/k2), where Arunprasath Shankar and Mark Roy demonstrate how to use SageMaker multi-model endpoints to host two computer TensorFlow vision models with different model architectures and datasets for image classification. They provide the sample notebook so you can try this for yourself.

![arch](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2021/05/11/1-2888-Architecture.jpg)


**Open Problems**

Open Problems provides a framework for researchers to define formalized tasks in single-cell genomics and benchmark model performance on those tasks using AWS. In the blog post, [Driving innovation in single-cell analysis on AWS](https://aws-oss.beachgeek.co.uk/jr) Daniel Burkhardt, Malte Luecken, and Mrudhula Balasubramanyan take a look in more detail how they are running this on AWS, looking at the architecture of the platform, benchmarking computational methods for single-cell analysis and more.

![open problems](https://d2908q01vomqb2.cloudfront.net/9e6a55b6b4563e652a23be9d623ca5055c356940/2021/05/27/CHANNEL_SIM-ID_international-competition-open-problems-repository-clipped-2.jpg)

**Ethereum**

Amazon Managed Blockchain support for managed Ethereum nodes makes it possible to build your own decentralized applications (dapps) without having to worry about maintaining reliable Ethereum nodes for relaying blockchain transactions or querying the state of blockchain data. In this post, [Deploy an Ethereum node on Amazon Managed Blockchain](https://aws-oss.beachgeek.co.uk/jv) Carl Youngblood walks you through setting up and connecting to an Ethereum node with Managed Blockchain

### Quick updates

**Apache Airflow**

You can now launch Apache Airflow 2.0 environments on Amazon Managed Workflows for Apache Airflow (MWAA). Apache Airflow 2.0 is the latest version of the popular open-source tool that helps customers author, schedule, and monitor workflows.

**PostgreSQL**

AWS Database Migration Service (AWS DMS) has expanded functionality by adding support for PostgreSQL version 13 in preview mode. Using AWS DMS, you can now perform live migrations from any AWS DMS supported sources to PostgreSQL 13 databases, and from PostgreSQL 13 databases to any AWS DMS supported targets.

**Apache Kakfa**

Amazon Managed Streaming for Apache Kafka (Amazon MSK) now supports Apache Kafka version 2.7.1 for new and existing clusters. Apache Kafka 2.7.1 includes several bug fixes. For a complete list of fixes, see the Apache Kafka release notes for 2.7.1.

**Apache Cassandra**

A couple of quick updates this week.

First up is news that Amazon Keyspaces (for Apache Cassandra), a fully managed Apache Cassandra–compatible database service, is now Health Insurance Portability and Accountability Act of 1996 (HIPAA) eligible to help you run healthcare workloads more easily. AWS enables covered entities and their business associates subject to HIPAA to use the secure AWS environment to process, maintain, and store protected health information. Now, you can run Cassandra workloads that are subject to HIPAA compliance more easily by using a fully managed and serverless database service. Amazon Keyspaces helps you secure PHI through features such as encryption, audit logging via AWS CloudTrail, and access management through AWS Identity and Access Management.

Following that is news you can manage service quotas for Amazon Keyspaces (for Apache Cassandra), through the Service Quotas console. Using the Service Quotas console, you can view and manage quotas (formerly referred to as limits) easily and at scale as your AWS workloads grow. For example, you can manage Amazon Keyspaces quotas such as account-level throughput, keyspaces and tables per AWS Region, and concurrent Data Definition Language (DDL) operations. Service Quotas makes requesting quota increases easier: search for a quota, enter your desired value, and submit a quota increase request. You can manage your quotas proactively by configuring Amazon CloudWatch alarms that monitor usage and alert you to approaching quotas.

**Apache Spark 3.1.1**

Amazon EMR 6.3 release version now supports Apache Spark 3.1.1 and provides runtime performance improvements with EMR Runtime for Spark. Amazon EMR 6.3 also supports Apache Hudi 0.7.0, Flink 1.12.1, PrestoDB 0.245.1, PrestoSQL 350, Hue 4.9, JupyterHub 1.2, Oozie 5.2.1 and TensorFlow 2.4.1.

**JetBrains**

The AWS Toolkit for JetBrains now provides developers with convenient IDE functionality to create and manage deployments from their code or image repositories using AWS AppRunner. AWS App Runner that was recently announced  is a new service that makes it easy for customers without any prior containers or infrastructure experience to build, deploy, and run containerised web applications and APIs in just a few clicks.

With new App Runner features in the AWS Toolkit for JetBrains, users of any JetBrains IDE can configure and deploy web services, track deployment status (i.e. view deployment notification logs) and monitor state of deployed services (i.e., services active, running, or paused), all without leaving their IDEs.

**Lustre**

Amazon FSx for Lustre, a service that provides cost-effective, high-performance, scalable file storage for compute workloads, now supports data compression. Data compression enables you to reduce storage consumption of both your file system storage and your file system backups. The data compression feature is designed to deliver high levels of compression without adversely impacting file system performance. Once data compression is enabled, newly written files are automatically compressed by FSx for Lustre before they are written to disk and automatically uncompressed when they are read. In addition to compression, Amazon FSx for Lustre offers a range of storage options to help you reduce costs, including a variety of SSD and HDD storage options, along with an option to store data on unreplicated storage for short-term processing of data.

### Videos of the week

**Observability**

Implementing observability in applications a requirement for achieving Operational Excellence, and a well implemented observability plan allows customers to react to operational events, run workloads effectively and gain insights into their applications. In this video, Imaya Kumar Jagannathan will walk you through how to use Amazon managed open source tools for observability, how to use Amazon Managed Prometheus to monitor the performance of containerised workloads and how Amazon Managed Service for Prometheus and Amazon Managed Service for Grafana work with other AWS services

{% youtube YlupF_OAGIg %}

### Events for your diary

**DevAx**
**June 3rd, 2pm CET**

I am excited to let you know about DevAx, a new workshop series by developers for developers that will be streamed live via Twitch. The first Thursday of every month you will bel able to join our AWS experts and invited guests as they take you through a variety of interesting open source topics, projects and more.

Make sure you check out Twitch and join in on the fun! https://www.twitch.tv/aws

**Data Hack for Good 2021**
**June 5th, Belfast/Virtual**

The Allstate Data Hack for Good, is taking place virtually Saturday and Sunday 5th and 6th June 2021. It is being held in partnership with Belfast City Council and supported by the Department of Finance Open Data Innovation and Outreach Fund. This year this event is collaborating with AWS.

The hackathon is open to technologists of all experience levels and backgrounds, with the goal to use data and technology to make life better in Belfast. During the hackathon, on demand technical training will be available, including data visualisation, data manipulation, model building, and Alexa Skills. Experts will be on hand throughout the event to answer questions, troubleshoot and support a collaborative approach to using data to solve problems.


**Maintainer Week**
**week of June 7th**

Make sure you check out this week long event starting on the 7th of June, for open source maintainers to gather, share, and be celebrated. You can find details of [all the weeks sessions on their GitHub page](https://aws-oss.beachgeek.co.uk/kq), with Upstream on June 7th, Global Maintainer Summit on the 8/9th, The Changelog: Maintainer Spotlight on the 10th and FundOSS on the 11th.

**Open@Amazon**
**June 16th, 9:00am - 5:00PM EDT**

Of course I am biased, but this is a must attend event. A celebration of open source on AWS with a fabulous cast of speakers, a fantastic broad set of topics and the event will be fully live so you can get your chance to interact with the speakers and the broader open source and AWS community.

Check out the blog post, [What’s up with open source at AWS? Attend Open@Amazon live on Twitch June 16](https://aws-oss.beachgeek.co.uk/jo)

**Cloud Native Day**
**23rd September, Bern Switzerland**

What is this, an in person event returning? A stellar line up including our own Michael Hausenblas, an event looking at CNCF projects and the future of IT. 

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen).