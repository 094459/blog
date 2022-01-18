---
title: 'AWS open source news and updates #68'
date: '2021-05-17'
tags : [ oss-newsletter ]
---
## May 17th, 2021 - Instalment #68

Newsletter #68. 

What better way that to celebrate my 100th post on dev.to with the latest AWS open source news and updates. This week we have posts covering Rust, OpenSearch, SaaS Boost, Apache Airflow, Kubernetes, Taurus, Spring Boot, Jenkins, GraphQL, Redis and more. If you are looking for projects, make sure you check out SaaS Boost which generated a lot of buzz last week, as well as the first beta of OpenSearch, sls-test-tools, aws-assume-role-lib and more. On top of that, check out the workshops this week, covering Apache Airflow and Laravel and finally some new videos and events for your diaries.  

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Ben Kehoe, Kyle Davis, Andrew Hopp, Becki Lee, Drew Wright, James Sorling, Ernest Chiang, Sebastian Bille, Vu Dao, Jimmy Ray, Alexei Ledenev, Ajay Swamy,  George Lenz, Rotem Bar, Adrian De Luca, Mikhail Vasilyev, Brian Carlson, Claudio Sidi, Jim Gallagher, Mirus Lu, Arjan Schaaf, Benjamin Meyer, Shane Miller, James Sun, Alon Gendler, Dima Breydo, Michael Song, Rajesh Mikkilineni, Matheen Raza and Aaron Miller.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

**aws-saas-boost**

[aws-saas-boost](https://aws-oss.beachgeek.co.uk/if) announced during re:Invent 2020, AWS SaaS Boost is an open source tool that helps software developers migrate their existing solutions to a Software-as-a-Service (SaaS) delivery model, removing the complexities of building SaaS solutions with ready-to-use core software elements. Those elements include tenant management, deployment automation, analytics dashboards, billing and metering, an administrative web interface, and more.

![arch](https://github.com/awslabs/aws-saas-boost/raw/main/docs/images/gs-install-flow.png?raw=true)

Read the announcement blog post, [AWS SaaS Boost released as open source](https://aws-oss.beachgeek.co.uk/ig) from Adrian De Luca to find out more. This announcement generated a LOT of interest last week, but rather than share the links here I suggest if you are interested in this project, check out some of the other posts that the tech press has written to get some additional perspectives.

**OpenSearch**

[OpenSearch](https://aws-oss.beachgeek.co.uk/hz) big news last week from the OpenSearch team, who shared the first beta of OpenSearch and OpenSearch Dashboards. Check out the blog post, [OpenSearch Beta 1](https://aws-oss.beachgeek.co.uk/i0) from Kyle Davis and Andrew Hopp. Download links are available from that blog post, or if you prefer you can always check out the GitHub repos and the source code. Finally, keep up to date with the latest news by bookmarking the webpage, https://opensearch.org/

On a related note, the [Apache SkyWalking](https://aws-oss.beachgeek.co.uk/ic) project wrote last week, [OpenSearch, a new storage option to avoid ElasticSearch's SSPL](https://aws-oss.beachgeek.co.uk/id) sharing that they had begun work on supporting OpenSearch and that they were supporting it as a storage option for their project.

**sls-test-tools**

[sls-test-tools](https://aws-oss.beachgeek.co.uk/iw) from the same folks that brought you the amazing sls-dev-tools we have an alpha of sls-test-tools, an open source tool that provides a range of utilities, setup, teardown and assertions to make it easier to write effective and high quality integration tests for Serverless Architectures on AWS.


**aws-assume-role-lib**

[aws-assume-role-lib](https://aws-oss.beachgeek.co.uk/iu) this library from AWS Hero Ben Kehoe is something you will find useful if you work with AWS in Python and you do role assumption. As Ben [tweeted](https://twitter.com/ben11kehoe/status/1393701765749436418) yesterday:

> Yesterday I had to write a script that iterated over every account and assumed the Organizations access role in each one to do some work. The amount of thinking/remembering about the details of sts.assume_role was zero.

You can find that script over at [his Gists](https://aws-oss.beachgeek.co.uk/iv).

**dragoneye**

[dragoneye](https://aws-oss.beachgeek.co.uk/ir) dragoneye is an open source tool from Indeni written in Python that is used to collect data about your AWS environment using the cloud provider's APIs. It is intended to function as component in other tools who have the need to collect data quickly (multi-threaded), or as a command line to collect a snapshot of a cloud account.

**staticweb-open-wp**

[staticweb-open-wp](https://aws-oss.beachgeek.co.uk/i5) this is an open-source, customisable template for Static WordPress stacks on AWS that uses WP2Static to deploy HTML files to AWS S3. The generated website is served by AWS CloudFront and you can read more about this project in the blog post, [Open-Source WordPress Stack](https://aws-oss.beachgeek.co.uk/i6) that provides a generator that create the CloudFormation stack to deploy this project. If you deploy WordPress sites, make sure you take a look.

### Community open source posts

**Open Distro for Elasticsearch**

[SSRF in Open Distro for Elasticsearch](https://aws-oss.beachgeek.co.uk/ie) I enjoyed this post from Rotem Bar that dives deep into CVE-2021-31828, an issue that effects Open Distro for ElasticSearch (ODFE), versions until 1.12.0.2. The post covers the background, the time line and the remediation process, and is a fascinating read for those wanting to know more about how these kinds of vulnerabilities are managed responsibly.

**Serverless**

[Serverless Framework vs SAM vs AWS CDK](https://aws-oss.beachgeek.co.uk/i7) Sebastian Bille shares his thoughts and experiences as he compares a number of open source developer tools that developers can use when building serverless applications. Seb takes the approach of trying these different tools to build and deploy the same application, sharing his thoughts as he goes along. Nice.

**Kubernetes**

A couple of Kubernetes related community posts this week. First up we have, [AWS CDK for EKS — Kubernetes Manifest Handling](https://aws-oss.beachgeek.co.uk/i8) where Jimmy Ray follows up from a previous post on using AWS CDK to deploy a sample Java application on Amazon EKS, with this post that dives deeper into Kubernetes YAML manifests. From what these are to how to use them with AWS CDK, this is a great post to understand what your options are when managing Kubernetes manifests and the resulting Kubernetes resources that get created.

Following that we have Vu Dao with, [Add Taints To AWS EKS Cluster And Trouble Shooting](https://aws-oss.beachgeek.co.uk/i9) which takes a look at a newly released feature within AWS EKS, Kubernetes node taints (see Quick Updates below for more info), and how you can get started with these to help you with managing and troubleshooting your EKS Clusters.

**Spotinfo**

[Spotinfo — a new CLI for AWS Spot](https://aws-oss.beachgeek.co.uk/ia) a couple of weeks back I covered a great new open source tool from Alexei Ledenev called [spotinfo](https://dev.to/aws/aws-open-source-news-and-updates-66-1bhj), a command-line tool that helps you determine AWS Spot instance types with the least chance of interruption and provides the savings you get over on-demand rates. Alexei has put together this post shows you how it works and how to get started. If you like this tool like I do, then remember to check out the GitHub repo and give it some love.

**Regula**

Last week Fugue posted news that their open source tool Regula, now supported AWS CloudFormation. You can read the full post from Drew Wright, [Regula Adds Support for AWS CloudFormation Security Checks](https://aws-oss.beachgeek.co.uk/i2) and then if that piques your interest, why not take the next step and follow their clear tutorial, [Checking AWS CloudFormation IaC Security with Regula](https://aws-oss.beachgeek.co.uk/i1) that Becki Lee has put together.

**Apache Airflow**

[Working with the RedshiftToS3Transfer operator and Amazon Managed Workflows for Apache Airflow](https://aws-oss.beachgeek.co.uk/it) something I worked on last week after some discussions in the Apache Airflow community slack channel, where a community member was getting some unexpected behaviour when using the Airflow operator that lets you move data from Redshift to S3. Took me a while to get this working in a secure way, so have made this super easy for you to reproduce in this blog post now. How to work and integration Amazon Redshift with your Apache Airflow workflows.


### AWS open source posts

**Kubernetes**

[Migrating from self-managed Kubernetes to Amazon EKS? Here are some key considerations](https://aws-oss.beachgeek.co.uk/iq) Matheen Raza and Aaron Miller talk about some of the things to think about when planning your migration from your own, self managed Kubernetes clusters to Amazon EKS. They cover topics such as versions, security, networking and storage as well as some ideas on how to approach testing. If this is something you have been thinking about, this post is for you.

**Rust**

The Rust language builds on the superpowers of other languages and innovates when required to deliver big on performance, reliability, productivity, and accessibility. In this post, [Innovating with Rust](https://aws-oss.beachgeek.co.uk/im) Shane Miller takes a look at the missions and goals of Rust within AWS, how we working with the open source community, the AWS Rust team and the future.  

**Apache Airflow**

[Manage and process your big data workflows with Amazon MWAA and Amazon EMR on Amazon EKS](https://aws-oss.beachgeek.co.uk/il) James Sun, Alon Gendler, and Dima Breydo provided a great deep dive in how you can orchestrate an ETL pipeline using Amazon MWAA with EMR on EKS, using the sample Citi Bike dataset and providing you with everything you need so you can reproduce this in your own environment. That is my weekend sorted.

![arch](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2021/05/04/bdb1232-worfklows-mwaa-emr-eks-1.png)

**GraphQL**

[How Takeda uses the GraphQL API with AWS AppSync to support data scientists](https://aws-oss.beachgeek.co.uk/ip) Michael Song and Rajesh Mikkilineni from Takeda show you how you can deploy an API using JupyterHub to access data via GraphQL, and use JupyterHub to run queries to fetch the dataset using the GraphQL API. 	They have taken this approach to provide API-based access to data as the flexibility of GraphQL enables researchers to access data the way they need it. To dive deeper, read on.

**Taurus**

Taurus is an open source tool that simplifies the process of performance and functional tests with an automation-friendly convenience wrapper for a number of open source testing tools such as JMeter, Gatling, Locust.io, Grinder and Selenium WebDriver. In this post, [Ensure Optimal Application Performance with Distributed Load Testing on AWS](https://aws-oss.beachgeek.co.uk/ib) Ajay Swamy and George Lenz walk you through a new open sourced solution, Distributed Load Testing on AWS, to help you automate the performance testing of your software applications at scale.

![arch](https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2021/05/12/Fig2-2.png)

**Jenkins**

[Unify your iOS mobile app CI/CD pipeline with Amazon EC2 Mac Instances](https://aws-oss.beachgeek.co.uk/ik) Benjamin Meyer shares with you how you can use Jenkins to build a CI/CD pipeline with the new Amazon EC2 Mac instance types to build and test your iOS and macOS applications. The post also talks about Fastlane, an open-source platform aimed at simplifying Android and iOS deployment, and the walk through shows you how you can incorporate to automate the development and release workflow of mobile applications.

![arch](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2021/05/07/Fastlane9.png)

**Redis**

[Manage AWS ElastiCache for Redis access with Role-Based Access Control, AWS Secrets Manager, and IAM](https://aws-oss.beachgeek.co.uk/ii) Claudio Sidi, Jim Gallagher, and Mirus Lu collaborate on this solution to address the lack of an out-of-the-box way to grant IAM entities (roles, users, or groups) read and write access to Redis when using RBAC. The post shows you how you can associate IAM entities with ElastiCache RBAC users and ACLs, through the use of AWS Secrets Manager as a proxy for granting access to ElastiCache RBAC user credentials.

![arch](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2021/05/07/dbblog_1523__02.png)

**Spring Boot**

[Amazon DynamoDB single-table design using DynamoDBMapper and Spring Boot](https://aws-oss.beachgeek.co.uk/ij) Arjan Schaaf with a great post for Java/Spring Boot fans, taking a look at how to us a single-table design approach in conjunction with Spring Data (used by Spring Boot based application for data access) when using a nonrelational database, in this case DynamoDB. Check out the code in the GitHub repo and suggestions of how you can tailor this solution for your own needs. 


### Open Source on AWS

[Choosing a CI/CD approach: Open Source on AWS, an Iponweb story](https://aws-oss.beachgeek.co.uk/ih) Mikhail Vasilyev and Brian Carlson take a look at how one customer, Iponweb, approached choosing a continuous integration, continuous deployment (CI/CD) environment using open source tools running on AWS. 

I loved the quote from Michael Benuhis, CTO at Iponweb.

> “Iponweb was able to get the best of open-source software and public cloud services by building the continuous integration platform on Amazon Web Services. Open-source tools provided Iponweb platform agnosticism for serving our diverse customer base, while managed Amazon EKS on EC2 Spot Instances eliminated the operational burden of managing our own Kubernetes infrastructure, and with greater cost efficiency.”

### Quick updates

**Apache Ranger**

Amazon EMR integration with Apache Ranger is now available on EMR 6.3, allowing you to define, enforce, and audit fine-grained data access control. With this feature, you can define and enforce 1/ database, table, and column level authorisation policies for Apache Spark and Apache Hive users to access data through Hive Metastore, and 2/ prefix and object level authorisation policies when accessing data in Amazon S3 via the Amazon EMR File System (EMRFS), leveraging Amazon CloudWatch to capture auditing logs.

Apache Ranger is an open-source tool to enable, monitor, and manage comprehensive data security across the Hadoop platform. Previously, you can use Apache Ranger to enforce fine-grained authorisation on data in HDFS with Apache Hive using this blog post. Now this native integration enables additional capabilities. You can define three types of authorisation policies on Apache Ranger Policy Admin server. You can set table, column, and row level authorisation for Apache Hive, table and column level authorisation for Apache Spark, and prefix and object level authorisation for Amazon S3. Amazon EMR automatically installs and configures the corresponding Apache Ranger plugins on the cluster. These Ranger plugins sync up with the Policy Admin server for authorisation polices, enforce data access control, and send auditing events to Amazon CloudWatch Logs.

Check out the full announcement here, [Amazon EMR 6.3 now supports Apache Ranger for fine-grained data access control](https://aws-oss.beachgeek.co.uk/hw)

**Kubernetes**

Amazon Elastic Kubernetes Service (EKS) managed node groups now supports Kubernetes node taints, simplifying node lifecycle management for clusters with varying application resource requirements.

With managed node group support for Kubernetes node taints, you can easily section off groups of Amazon EC2 instances in your cluster as designated for only certain applications. You can apply a toleration to your pods that allows them to be scheduled onto nodes with matching taints. Taints and tolerations work together to ensure that pods are not scheduled onto inappropriate nodes.


### Workshop

**Apache Airflow**

Really good to see this new workshop, [Apache Airflow for Analytics](https://aws-oss.beachgeek.co.uk/hx).

In this workshop, you will learn how to build and orchestrate data and ML pipelines that include services such as Amazon S3, Amazon Redshift, Amazon EMR, AWS Glue, and Amazon SageMaker. You will gain familiarity and a better understanding of the hooks and operators available as part of Airflow to manage your pipelines/workflows on AWS.

**Laravel**

[laravel-on-aws-ecs-workshops](https://aws-oss.beachgeek.co.uk/i4) I somehow missed this when it surfaced a few months ago, but better late than never. If you are a PHP/Laravel developer, then this workshop from Ernest Chiang will guide you to deploying your Laravel applications onto AWS, guiding you through a number of different steps that improve your architecture and enable you to move to support production workloads.


### Video of the week


**AWS Copilot and Wordpress**

In last weeks Containers from the Couch session, Austin Ely from the Copilot team walks you through what it takes to build a highly available, containerised Wordpress site. This video includes building a network file system using Amazon EFS, and a serverless relational MySQL database using Aurora Serverless. All that is done while diving into the latest features we've added to the AWS Copilot CLI!

{% youtube nvW1i33my3o %}

**DevSecOps**

Last week I enjoyed listening to [Security Superfriends | James Sorling, Security Architect, WirelessCar](https://aws-oss.beachgeek.co.uk/i3) which talks about meeting developers where they were, in their toolchains, and in their workflows and getting them to scan their infrastructure as code (IaC) early in development. This often uses open source tools, and James (who I featured last week) is a contributor to CFN-nag and integration of that into tools like SonarQube. 

{% youtube aYwSd1Wu28Q %}


### Events for your diary

**Open Sourcing AWS DeepRacer**
**May 18th, 8:00PM CET**

Recently we expanded AWS DeepRacer’s educational capabilities to coding robotics applications with the introduction of AWS DeepRacer Open Source. Now, aspiring ROS developers can use their AWS DeepRacer device to experiment with sample projects developed by our GitHub community, and contribute their own projects for a chance to be featured. During this tech talk we’ll provide an overview of DeepRacer Open Source, how to access sample projects in the DeepRacer GitHub community, and finally we’ll show you how to program your DeepRacer to scare off unwanted critters with the DeepRacer Robocat project.

**How to Run Your First HPC Job on AWS**
**May 25th, 8:00PM CET**

In this online webinar you will learn how to set up your first HPC cluster on AWS. We'll cover everything from installing AWS ParallelCluster (and open source cluster management tool to deploy and manage HPC clusters in the AWS cloud), selecting the your Amazon EC2 instances, when to use Spot Instances to save up to 90% on compute, to launching your first MPI “hello world” job from the command line.

**Mobile and Front-End Live**
**May 25th, 9:00 - 15:00 PDT**

This is a LIVE streamed event on Twitch  focused on accelerating full-stack mobile and web development. Learn about AWS Amplify, a set of purpose-built tools and services for front-end web and mobile developers that simplify app development. Deep dive into GraphQL and AWS AppSync, a fully-managed GraphQL service that improves app performance and developer productivity.

You can read more about what you can expect in the blog post, [Mobile and Front-End Live, May 25](https://aws-oss.beachgeek.co.uk/f4)


**Cloud Native Day**
**23rd September, Bern Switzerland**

What is this, an in person event returning? A stellar line up including our own Michael Hausenblas, an event looking at CNCF projects and the future of IT. 


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen).