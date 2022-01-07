---
title: 'AWS open source news and updates #53'
date: '2021-01-25'
tags : [ oss-newsletter ]
---
## January 25th, 2021 - Instalment #53

Newsletter #53

This weeks newsletter has another great variety of posts and projects for you to check out. First up though, and probably the most important news from last week was the announcement around how AWS is looking to keep Elasticsearch and Kibana open source (read the post below). In addition to that news, we have some interesting projects for builders interested in infrastructure as code, a couple of great benchmarking posts, including another great AWS Graviton2 story and my new favourite open source project, Apache Airflow.

Without further ado, lets get going.

### Elasticsearch

[Stepping up for a truly open source Elasticsearch](https://aws-oss.beachgeek.co.uk/2x) Carl Meadows, Jules Graybill, Kyle Davis, and Mehul Shah shared an important announcement for customers and developers working with Elasticsearch. With the recent licensing changes that will, in effect moved Elasticsearch to become a proprietary code base, (SSPL is **not** open source) then this left customers and many in the open source communities with some difficult decisions to make. This post shares how AWS is creating a fork of Elasticsearch and Kibana so that both projects can remain open source, under the Apache 2.0 license. This is a really important post and I urge you to read it. 

If you have any questions or follow up, please do not hesitate to contact me - you can find my contact details in my bio but alternatively leave a comment and I will get back to you.

**Open Data**

We very recently announced eighteen new or updated datasets from Illumina, the University of Alaska Fairbanks, IntelinAir, and others. Whilst not open source, these open data sets are very useful and are available for you to build on for research, education, and product development. Many of the listings for the datasets include applications, demos, tutorials, and publication references showing how you can use the data on AWS.

To find out more details about these new data sets, read the [announcement here](https://aws-oss.beachgeek.co.uk/2m). 

**CloudFormation Guard - RFC**

CloudFormation Guard is a tool that checks #CloudFormation templates for compliance using a simple declarative language. We are asking for feedback on upcoming changes to the rule language through this RFC. Be part of the conversation by submitting your feedback in our open pull request, which you can check out [here](https://aws-oss.beachgeek.co.uk/2s).


### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following superstars: Julia Evans, Joseph So, Ned McClain, GenUI, Lezgin Bakircioglu, Anubhav Sharma, Tod Golding, Denis Gladkikh, Stephane Jourdan, Anubhav Mishra, Jobin Augustine, Sergey Kuzmichev, Srinivas Manepall, Qing Lan, Carol McDonald, Kong Zhao,  Leo Meyerovich, Dave Bechberger, Taylor Riggan, Carl Meadows, Jules Graybill, Kyle Davis, Mehul Shah, James Saryerwinnie, Mikhail Shapirov, Curtis Rissi, Benjamin Smith, Re Alvarez-Parmar, Chaithanya Maisagoni,  Vishal Pathak,  Shantanu Kotambkar, Al MS and Peter Gvozdjak, Stanislav Kirdey,, Lu Huang, Lai Wei, and Qing Lan.


Make sure you find and follow these builders and keep up to date with their open source projects and contributions.


### Latest from open source projects

**driftctl**

[driftctl](https://aws-oss.beachgeek.co.uk/2p) is an open source project that helps you to measure infrastructure as code coverage, and tracks infrastructure drift. Stephane Jourdan blogs about this project and the problem it is looking to address in, [Announcing Driftctl because drift matters](https://aws-oss.beachgeek.co.uk/2q).

**dwcflint**

[dwcflint](https://github.com/dwtechnologies/dwcflint) is an open source Python module that provides a runnable module and wrapper around Amazons cfn-lint tool for Cloudformation file linting that adds a few extra rules. It is written in Python 3, lightweight (only a single dependency) and fast. This tool emerged from trying to solve the problem around how they could easily bundle custom rules for the corner cases they had discovered, and distribute those among the development teams.

You can read more about this from Lezgin Bakircioglu's post, [DWCFLint - The tool supporting our cost control & improves our security roles](https://aws-oss.beachgeek.co.uk/2k)

**s3p**

[s3p](https://aws-oss.beachgeek.co.uk/39) S3P is an open source tool from GenUI that provides a radically faster way to copy, list, sync and do other bulk operations over large AWS S3 buckets. You can use it as a command-line tool for common operations, or you can use it as a library. The project readme shares how it is able to be so quick, as well as sharing a blog post they wrote earlier last year. Worth checking out if you are looking to improve/tune performance of your file copies.

**aws-saas-factory-ref-solution-metrics-analytics**

[aws-saas-factory-ref-solution-metrics-analytics](https://aws-oss.beachgeek.co.uk/2i) is an open source reference implementation of a metrics & analytics solution, which can be used to visualize the usage and consumption across various tenants, and tenant tiers, within your SaaS application. These metrics can then be used for various purposes, such as optimizing tenant experience and ultimately calculating cost per tenant. These metrics will also eventually have a direct impact on the pricing and tiering strategy of your SaaS application.

![arch](https://d2908q01vomqb2.cloudfront.net/77de68daecd823babbb58edb1c8e14d7106e83bb/2021/01/22/SaaS-Multi-Tenant-Metrics-2.jpg)

You can read more about how this solution works in the blog post, [Capturing and Visualizing Multi-Tenant Metrics Inside a SaaS Application on AWS](https://aws-oss.beachgeek.co.uk/2j) by Anubhav Sharma and Tod Golding.

**wdio-aws-device-farm-service**

[wdio-aws-device-farm-service](https://aws-oss.beachgeek.co.uk/2n) Cross-browser e2e tests have never been simpler with the release of this new open source project that provides AWS Device Farm drivers for WebdriverIO. [WebdriverIO](https://aws-oss.beachgeek.co.uk/2o) is a test automation framework that allows you to run tests based on the Webdriver protocol and Appium automation technology. It provides support for your favorite BDD/TDD test framework and will run your tests locally or in the cloud using Sauce Labs, BrowserStack, TestingBot or LambdaTest. 

### Videos of the week

**Agones**

Great video from the Containers from the Couch team, this time talking about how Agones, which is an open source game server orchestrator for Kubernetes, can leverage AWS Spot instances reliably. If you are running any kind of gaming infrastructure, Agones or just interested in GameTech, then check this video.

{% youtube RvBjgKME21U %}

**etcd**

From the beginning of the year, the team get together to talk about the graduation of etcd within CNCF and talk to Gyuhuo Lee about the work he has done within that project.

{% youtube RTSbyr1Rjxg %}

### Blog posts from the community and customers

**Firecracker**

Have you heard or read about [Firecracker](https://aws-oss.beachgeek.co.uk/3e), the open source virtualisation technology that helps you create secure, fast, multi-tenant container solutions but didn't know where to start? Well this post from Julia Evans, [Firecracker: start a VM in less than a second](https://aws-oss.beachgeek.co.uk/3f) is just what you need. From a quick overview of the main problems Firecracker is looking to address to then providing a number of examples of how you can get it up and running, look no further than this post for your weekly dose of Firecracker goodness. 

**GraphQL**

[Testing AppSync GraphQL with Altair](https://aws-oss.beachgeek.co.uk/3c) this post from Joseph So shows you how you can use the [open source GraphQL client IDE Altair](https://aws-oss.beachgeek.co.uk/3d) to test your AWS AppSync GraphQL API's. Joseph walks you through a quick example so you can understand how this works and then apply this to your own projects.

**PostgreSQL**

[PostgREST on Fargate](https://aws-oss.beachgeek.co.uk/3a) Ned McClain walks you through how you can deploy PostgREST on AWS Fargate. [PostgREST](https://aws-oss.beachgeek.co.uk/3b) is an open source project that serves a fully RESTful API from any existing PostgreSQL database. Ned shows you how you can get this running on AWS Fargate, with a detailed walkthrough and instructions.

**AWS Amplify**

[Scheduled AWS Amplify Builds](https://aws-oss.beachgeek.co.uk/2l) Denis Gladkikh gives you a very quick post sharing a tip around how to trigger Hugo blog posts builds using the buidFuture option. Read on to find out more.


### AWS open source posts

**Deep Java Library**

[How Netflix uses Deep Java Library (DJL) for distributed deep learning inference in real-time](https://aws-oss.beachgeek.co.uk/35) Stanislav Kirdey from Netflix and  Lu Huang, Lai Wei, and Qing Lan from AWS share with you how the observability team at Netflix uses Deep Java Library (DJL), an open source, deep learning toolkit for Java, to deploy transfer learning models in production to perform real-time clustering and analysis of applications’ log data. 

One of the ways Netflix is able to sustain a high-quality customer experience is by employing deep learning models in the observability and monitoring space, specifically in observability of system and application logs (not user data) to help improve the customer experience. The Netflix observability team uses deep learning to automatically analyse and cluster gigabytes of log lines coming from various microservices in real-time.

The post provides sample code to help you reproduce the post.

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2020/12/22/qingla_Netflix-DGL_f1.png)

**Apache Airflow**

[Running Airflow on AWS Fargate](https://aws-oss.beachgeek.co.uk/31) Re Alvarez-Parmar and Chaithanya Maisagoni show you how you can get Apache Airflow up and running on AWS Fargate. A few weeks ago I posted how one of our customers, Affirm has already undertaken this journey and the benefits they have seen. This post takes that one step further and takes a look at the technical and architectural considerations you will need to think about.

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2021/01/20/img_0416.png)

**Apache Spark**

This week we have a couple of posts on Apache Spark. Kicking this off we have Qing Lan, Carol McDonald, and Kong Zhao collaborating on this tutorial, [Leverage deep learning in Scala with GPU on Spark 3.0](https://aws-oss.beachgeek.co.uk/2u). This post demonstrate how to create a cluster of GPU machines and use Apache Spark with Deep Java Library (DJL) on Amazon EMR to leverage large-scale image classification in Scala. DJL now provides a GPU-based Deep Learning Java package that is designed to work smoothly in Spark.

Following that we have [Run Apache Spark 3.0 workloads 1.7 times faster with Amazon EMR runtime for Apache Spark](https://aws-oss.beachgeek.co.uk/34). Al MS and Peter Gvozdjak have put together an interesting benchmarking post to help you understand how you can improve the performance of your Apache Spark workloads. They use the [TPC-DS benchmark](https://aws-oss.beachgeek.co.uk/36) to do this, and as with all benchmarking posts, no spoilers - it is a short post, so check the results out for yourself.

**Apache Hudi**

[Writing to Apache Hudi tables using AWS Glue Custom Connector](https://aws-oss.beachgeek.co.uk/32) Vishal Pathak follows up from a previous post (which you can find [here](https://aws-oss.beachgeek.co.uk/38)) taking a look at the volume (or "big") aspect of big data, and how you can use Apache Hudi tables created within the AWS Glue service to process millions of records (in this post they show an example of updating 70 million out of 200 million records). If you like your data big, this post is for you.

**DevSecOps**

[Building end-to-end AWS DevSecOps CI/CD pipeline with open source SCA, SAST and DAST tools](https://aws-oss.beachgeek.co.uk/2v) Srinivas Manepall shows how you can use a number of open source tools such as OWASP Dependency Check, SonarQube, PHPStan and OWASP Zap as part of your automated deployment pipelines to provide security capabilities such as detecting publicly available vulnerabilities in the code, static code analysis, finding common application vulnerabilities and more. This post uses a number of AWS services to help you incorporate these tools, so check it out.

This is a complete solution and the source code is available in the GitHub repository here, at [devsecops-cicd](https://aws-oss.beachgeek.co.uk/37)

![arch](https://d2908q01vomqb2.cloudfront.net/7719a1c782a1ba91c031a682a0a2f8658209adbf/2021/01/21/pipeline-architecture.png)

**Amazon Neptune and graph-app-kit**

[Enabling low code graph data apps with Amazon Neptune and Graphistry](https://aws-oss.beachgeek.co.uk/2w) Leo Meyerovich CEO of Graphistry and Dave Bechberger and Taylor Riggan from AWS take a look at a new open-source tool, graph-app-kit, which aims to provide  a low code way to create powerful data applications for your Amazon Neptune managed graph database. 

![demo](https://aws-database-blog.s3.amazonaws.com/artifacts/DBBLOG-1352-neptune-graphistry/graph_app_kit_gremlin.gif)

This post provides everything you need to get going to create stunning looking visualisations from your data with modest effort.

**AWS Chalice**

[AWS Chalice adds support for the AWS CDK](https://aws-oss.beachgeek.co.uk/2y) James Saryerwinnie follows up with another post on AWS Chalice and support in AWS CDK, this time sharing how the AWS CDK construct (cdk-chalice) has now been integrated into the AWS Chalice framework from version 1.22.0. In this post, James walks you through creating a sample application that shows how this integration works.

**Bottlerocket, Calico and eBPF**

[Turbocharging EKS networking with Bottlerocket, Calico, and eBPF](https://aws-oss.beachgeek.co.uk/2z) Mikhail Shapirov and Curtis Rissi from AWS team up with Alex Pollitt, Co-founder and CTO at Tigera take a closer look at the support within Amazon EKS for running Bottlerocket, and what this means to managing the networking requirements you might have. Bottlerocket is an open source Linux distribution built by Amazon to run containers focused on security, operations, and manageability at scale. In this post you will read how Calico can build on top of this foundation to enhance the base networking for EKS beyond just adding network policy support . The benefits of this approach include accelerating network performance, removing the need to run kube-proxy, and preserving client source IP addresses when accessing Kubernetes Services from outside the cluster.

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2021/01/21/calico-ebpf-node-port.png)

**PHP**

[Building PHP Lambda functions with Docker container images](https://aws-oss.beachgeek.co.uk/30) Benjamin Smith is back with more PHP goodness, this time following up from the re:Invent announcement of AWS Lambda supporting Open Container Initiative (OCI) Spec v1.0 onwards) as a packaging format for your functions and how this can benefit folk who are running custom container runtimes such as the PHP one. This is a great post and game changing if you are running serverless PHP. 

**AWS SDK's**

[AWS SDK for Go Version 2 – General Availability](https://aws-oss.beachgeek.co.uk/33) Shantanu Kotambkar posts about the general availability of the AWS SDK for Go, v2. This new SDK requires Go version 1.15 or higher, and offers better functionality and performance. Read the post for more details.


### AWS Partner

**PostgreSQL on AWS Graviton2**

[PostgreSQL on ARM-based AWS EC2 Instances: Is It Any Good?](https://aws-oss.beachgeek.co.uk/2t) Jobin Augustine and Sergey Kuzmichev at Percona have put together a post to understand and compare the differences between running PostgreSQL on x86 and arm against a number of different workloads. As for all benchmarking posts, no spoilers - read the post. Warning, gratuitous use of graphs!

![graph](https://www.percona.com/blog/wp-content/uploads/2021/01/saturation_IO.png)

**CDK for Terraform**

[Announcing CDK for Terraform 0.1](https://aws-oss.beachgeek.co.uk/2r) Anubhav Mishra writes about the release of CDK for Terraform 0.1, covering the enhancements that have been added since the launch last July and outlining how this project is moving closer to beta status.If you are using AWS CDK, HashiCorp's Terraform or just interested in IaC, check this post.

### Quick updates

**OpenTelemetry**

With Amazon CloudWatch agent, you can now use OpenTelemetry APIs and SDKs to send application telemetry data to CloudWatch and AWS X-Ray. This update enables the agent to receive OpenTelemetry metrics and traces from applications and services running on Amazon Elastic Compute Cloud (Amazon EC2) and is intended for existing CloudWatch agent users who want to begin monitoring applications with OpenTelemetry without installing or configuring multiple agents.

As a project of the Cloud Native Computing Foundation, OpenTelemetry provides open source APIs and libraries to collect distributed traces and metrics for application monitoring. Instrumenting your applications using the OpenTelemetry SDKs allows you to correlate performance data with underlying infrastructure data, reducing the mean time to problem resolution. CloudWatch agent allows you to collect metrics and traces and send them to CloudWatch and X-Ray. CloudWatch and X-ray provide tools you can use to view, filter, and gain insights into data to monitor your applications, identify issues, and improve performance.

**PostgreSQL**

Amazon RDS for PostgreSQL Supports pg_cron Extension for Scheduling Database Jobs. pg_cron allows you to use cron syntax to schedule PostgreSQL commands directly within your database. You can use pg_cron to schedule tasks such as periodically rolling up data for analytic reports, refreshing materialised views, and scheduling vacuum jobs to reclaim storage. pg_cron includes an AWS open source contribution that adds an audit table so that you can query the outcome of each scheduled job. Amazon RDS supports pg_cron in PostgreSQL versions 12.5 and higher.  

**Apache Kafka**

You can now scale your Amazon Managed Streaming for Apache Kafka (MSK) clusters on demand by changing the size or family of your brokers without reassigning Apache Kafka partitions. Changing the size or family of your brokers gives you the flexibility to adjust your MSK cluster’s compute capacity based on changes in your workloads, without interrupting your cluster I/O. In just a few clicks, you can scale up or scale down your Amazon MSK clusters’ compute capacity that includes CPU, memory, network throughput and I/O capacity. You will be charged for the chosen broker size or family per Amazon MSK standard pricing.

**Apache Cassandra**

Amazon Keyspaces (for Apache Cassandra), a scalable, highly available, and fully managed Cassandra-compatible database service, now supports JavaScript Object Notation (JSON) syntax to help you read and write data from other systems more easily. 

JSON is a popular data format used for configuration files, storing the state of applications, and exchanging data between systems. Now, Amazon Keyspaces helps you read and write JSON documents more easily by supporting JSON syntax for INSERT and SELECT operations. When you read and write JSON data, Keyspaces maps the attributes within a JSON document automatically to a target table’s schema. Using the built-in JSON syntax support in Keyspaces helps you ensure proper formatting of JSON data by validating the structure of JSON documents against a table’s schema. Storing JSON documents in Keyspaces also helps you query for data across multiple JSON documents efficiently by using Cassandra Query Language (CQL). 

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen).

### Your feedback matters!

I have put together a short feedback survey, which I would ask you to take - it will take no more than 2 minutes. You can access [here](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn). Many thanks!

[Take the survey](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn