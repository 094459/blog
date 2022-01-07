---
title: 'AWS open source news and updates #88'
date: '2021-11-01'
tags : [ oss-newsletter ]
---
## November 1st, 2021 - Instalment #88

Newsletter #88.

Number 88 symbolises fortune and good luck in Chinese culture (I hope that is correct, so please let me know if that is not) and I hope you will feel you are all the luckier for chancing upon this weeks selection of open source projects and posts.

This week, the big news was the publishing of the Babelfish repository. Check out the launch post as well as additional content and links to this interesting open source project. We have plenty of other new open source projects such as nixtla, an open source time series forecasting library ready to roll in your AWS environment, shrimp and s3sha256sum tools that will help you work with large files over slow or unreliable connections, aws-sso-cli a project to help you configure SSO within your command line, and many more.

We have community and AWS content covering OpenSearch, PyDeequ, ConsoleMe, Apache DistCp, Apache Airflow, Delta Sharing, Apache Solr, Synchro Charts, AWS SAM, Bottlerocket and more. We also have a bumper set of videos too, this weeks topics include building Open Data Lakes, contributing to Terraform, Hugging Face and how to get started with GitHub Actions.

Before diving in, make sure you check out the Bug Bust article just below, and my team are hiring a couple of open source folks, so check out the job descriptions and feel free to DM me if you want a chat or to get any more details - could you be the one? 

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Stefan Sundin, Aaron Turner, Saul Magnusson, Sarat Vemulapalli, Robert Hafner, Tyler Lynch, Drew Mullen, Richard Boyd, Sheetal Joshi, Frank Munz, Sebastien Stormacq, Andrew Lee, Hammad Ausaf, Eric Johnson, Mahendar Gajula, Nitin Srivastava, Sean Tracey, Brian Diehr, Andrea Di Simone, Samuel Passman,  Kinnar Kumar Sen, Anjan Biswas, Ananth Raghavendra, Gary Stafford, Guilherme Sena Zuza, Suman Kumar Gangopadhyay, Sebastian Bille and Anton Rubin 

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Community noticeboard

**Bug Bust**

As re:Invent fast approaches, it was interesting to read about the AWS BugBust re:Invent Challenge at this year’s AWS re:Invent conference. It will be an attempt to create a new World Record for “Largest Bug Fixing Competition” as recognised by Guinness World Records. As part of this, AWS will be including a myriad of open source projects that developers will be able to patch and contribute to throughout the event. Bugs can range from security issues, to duplicate code, to resource leaks and more. To find out more, and how you might be able to register interest for your open source projects, read on in [Help Make BugBusting History at AWS re:Invent 2021](https://aws-oss.beachgeek.co.uk/11c)

**Jobs**

A couple of openings have come up in the open source team, so if you are looking for a change, and want to work with a really awesome bunch of people, then check these out. Feel free to ping me directly if you want to discuss in more details or ask any other question about the role, the team or working at AWS in general.

**Principal Evangelist, Open Source, Open Source Strategy & Marketing**

The OSS Technical Evangelist will be responsible for defining, leading and contributing to the open source and community engagement strategy for service teams across AWS. You will combine your passion and enthusiasm for cloud technology and open source with your unmatched creativity to generate grass-roots attention and support for AWS among key open source communities, industry opinion makers and technologists. You will work closely with the product marketing leadership to translate the business priorities of the service teams into solid engagements with key open source communities, foundations and open source technology partners. You will also be the voice of the community, building a feedback loop to teams across Amazon to help them understand the dynamics and needs of the open source community and build mechanisms to measure impact of our open source engagements. [Read more here](https://aws-oss.beachgeek.co.uk/11h).

**Sr. Open Source Program Mgr, Open Source Strategy & Marketing**

AWS Open Source is seeking an experienced Program Manager to join the team. The successful candidate will be a key member of the Open Source Strategy and Marketing team, which is responsible for driving high-visibility, strategic programs that directly impact customer experience and perception. The ideal candidate will have a software development background as well as Program management experience and will own and execute complex projects and drive key operational process improvement activities. You will be comfortable in a fast-paced multi-tasked environment, with the ability to drive the program’s strategy and roadmap, collaborate with business and development teams across the company to analyse the cost/benefit of project selection, and manage all aspects of the project execution. [Read more here](https://aws-oss.beachgeek.co.uk/11i).

### Latest open source projects

**Babelfish**

[Babelfish](https://aws-oss.beachgeek.co.uk/115) last week saw the availability of the [Babelfish for PostgreSQL](https://aws-oss.beachgeek.co.uk/114) open source project. As a reminder, Babelfish for PostgreSQL is an open source project available under the Apache 2.0 and PostgreSQL licenses that provide the capability for PostgreSQL to understand queries from applications written for Microsoft SQL Server. You can get started by reading my colleague Sebastian Stormacq post, [Goodbye Microsoft SQL Server, Hello Babelfish](https://aws-oss.beachgeek.co.uk/117). We also had Chandra sekhar Pathivada and Yogi Barot share this post, [Modify SSIS packages from SQL Server to Babelfish for Aurora PostgreSQL](https://aws-oss.beachgeek.co.uk/11r) showing you how to modify your existing Microsoft SSIS package connection from SQL Server to Babelfish.

![arch](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2021/10/14/DBBLOG-1862-image001.png)

**nixtla**

[nixtla](https://aws-oss.beachgeek.co.uk/11u) this open source library from Nixtla looks interesting. An open source time series forecasting library. You can use the service that Nixtla provide, or use the documentation within the README to host yourself on AWS. Either way, if you are exploring your choices for a time series forecasting library, you should add this to your list.

![arch](https://raw.githubusercontent.com/Nixtla/nixtla/main/.github/images/Architecture.png)

Stefan Sundin has been busy, putting together a couple of open source projects and a blog post to show you how to use them, [Introducing shrimp and s3sha256sum](https://aws-oss.beachgeek.co.uk/11v)

**shrimp**

[shrimp](https://aws-oss.beachgeek.co.uk/11x) this open source tool helps you upload large files to Amazon S3 over slow connections. Shrimp is optimised for this use case.

**s3sha256sum**

[s3sha256sum](https://aws-oss.beachgeek.co.uk/11w) this open source tool is a small program that calculates SHA256 checksums of objects stored on Amazon S3. Use it to verify the integrity of your objects. Perfect for checking those files have copied successfully (large files that you may have copied using Shrimp perhaps!)

Nice work Stefan!

**aws-sso-cli**

[aws-sso-cli](https://aws-oss.beachgeek.co.uk/11s) this open source, GPL 3 project from Aaron Turner is a secure replacement for using the aws configure sso wizard with a focus on security and ease of use for organisations with many AWS Accounts and/or users with many IAM Roles to assume. Detailed docs and examples, worth checking out.

{% asciinema 445604 %}

**aws-cdk-go-example-static-site**

[aws-cdk-go-example-static-site](https://aws-oss.beachgeek.co.uk/11t) if you are looking for an example of how to deploy statics sites via AWS CDK, then check out this project from Saul Magnusson. This example launches a secure static site hosted in an S3 bucket, distributed by CloudFront, protected by an ACM certificate, and with URIs automatically rewritten by a CloudFront Function

**ds-dashboard**

[ds-dashboard](https://aws-oss.beachgeek.co.uk/11g) Andrea Di Simone and Samuel Passman have put together this project that helps you to deploy and operate a simple data collection and distribution mechanism for your data science projects, which can be used for use cases such as generating dashboards. For a detailed walk through, check out the blog post, [Implementing a hub and spoke dashboard for multi-account data science projects](https://aws-oss.beachgeek.co.uk/11f)

**amazon-opensearch-service-monitor**

[amazon-opensearch-service-monitor](https://aws-oss.beachgeek.co.uk/11o) if you are using OpenSearch, then check out this repository that contains step by step demonstration to setup monitoring Stack for Amazon OpenSearch Service domains across all specified regions. This example uses AWS CDK and Python.

![arch](https://github.com/aws-samples/amazon-opensearch-service-monitor/blob/main/images/amazon_opensearch_service_monitor_framework.png?raw=true)

### AWS and Community blog posts

**Consoleme**

In the post [Achieving least-privilege at FollowAnalytics with Repokid, Aardvark and ConsoleMe](https://aws-oss.beachgeek.co.uk/11k), Guilherme Sena Zuza shares how he used a number of open source tools to help get closer to the principle of least privilege, and how he deployed these tools at FollowAnalytics. [hands on]

![arch](https://miro.medium.com/max/2000/0*QER4A3rd92n12alI)

**OpenSearch**

A couple of OpenSearch related posts this week.

First up we have Anton Rubin from Eliatra, who explains some of the core concepts of OpenSearch security in the post, [Partner Highlight: Eliatra presents OpenSearch Security Concepts](https://aws-oss.beachgeek.co.uk/11n). The post links to other, deeper dives if you want to gain even more understanding.

![auth](https://opensearch.org/assets/media/blog-images/2021-10-11-opensearch-security-concepts/auth_auth_sequence.png)

Following that we have the post [Moving from open source Elasticsearch to OpenSearch](https://aws-oss.beachgeek.co.uk/11q), where Sarat Vemulapalli shares how an overview of how to move from open source Elasticsearch to OpenSearch.

**Apache Airflow**

I missed this the first time around, but caught it last week. Suman Kumar Gangopadhyay provides a step by step guide to help setup a pipeline which can automate running spark jobs from an edge node to a spark cluster, in the blog post[Airflow, Spark & S3, stitching it all together](https://aws-oss.beachgeek.co.uk/11l) [hands on]

**Apache DistCp**

In the post, [Copy large datasets from Google Cloud Storage to Amazon S3 using Amazon EMR](https://aws-oss.beachgeek.co.uk/11a) Andrew Lee and Hammad Ausaf demonstrates how to configure an EMR cluster to use open source tools such as Apache DistCp and S3DistCP, and compares the performance of doing large file copies. [hands on]

**Delta Sharing**

Delta Sharing is a Linux Foundation open source framework that uses an open protocol to secure the real-time exchange of large datasets and enables secure data sharing across products for the first time. It was great therefore,  to read [Delta Sharing on AWS](https://aws-oss.beachgeek.co.uk/118) from former colleague Frank Munz, who is now a Developer Advocate at Databricks. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/09/29/ialek_databricks_delta-sharing_f4.png)

**Apache Solr**

Apache Solr is an open source enterprise search platform built on Apache Lucene. Kinnar Kumar Sen, Anjan Biswas, and Ananth Raghavendra have collaborated on this post, [Deploying and scaling Apache Solr on Kubernetes](https://aws-oss.beachgeek.co.uk/11j) that shows you how to deploy a highly available, scalable, and fault-tolerant enterprise-grade search platform with Apache Solr using Amazon Elastic Kubernetes Service (Amazon EKS). [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/10/13/anjanavb_apache-solr-kubernetes_f3.png)

**PyDeequ**

PyDeequ is an open-source Python wrapper over Deequ (an open-source tool developed and used at Amazon, to help data scientists and engineers with data quality and testing capabilities from Python and PySpark). In the post, [Accelerate large-scale data migration validation using PyDeequ](https://aws-oss.beachgeek.co.uk/11b) Mahendar Gajula and Nitin Srivastava, show you how you can use this and walk through a step-by-step process to validate large datasets. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2021/10/04/BDB1530-image001.png)

**Synchro Charts**

Synchro Charts, is a new open source project that is a front-end component library that provides a collection of components to visualise time-series data for application developers with a focus on monitoring, root cause analysis, and analytics. In the post, [Visualizing time series data with the open source Synchro Charts](https://aws-oss.beachgeek.co.uk/11d) Brian Diehr walks you through some of the features which you can check out at [synchrocharts.com](https://aws-oss.beachgeek.co.uk/11e) 

**Bottlerocket**

[Amazon EKS adds native support for Bottlerocket in Managed Node Groups](https://aws-oss.beachgeek.co.uk/116) from Sheetal Joshi takes a look at how to set up an Amazon EKS cluster and launch a Bottlerocket managed node group. Bottlerocket is a Linux-based open-source operating system that is purpose-built by Amazon. It focuses on security and maintainability, and provides a reliable, consistent, and safe platform for container-based workloads. Dive deeper into what this means by checking out this post. [hands on]

**Serverless Framework**

AWS Community Builder Sebastian Bille takes a look at two open source projects and how you get combine these when developing and deploying your serverless application in the blog post, [Combining Serverless Framework & AWS CDK](https://aws-oss.beachgeek.co.uk/11m) [hands on]

**AWS SAM**

Eric Johnson shares with you a new capability of AWS SAM, that aims to increase infrastructure accuracy for testing with sam sync, incremental builds, and aggregated feedback for developers. AWS SAM Accelerate brings the developer to the cloud and not the cloud to the developer. In the post, [Accelerating serverless development with AWS SAM Accelerate](https://aws-oss.beachgeek.co.uk/119) he shows you how to bypass most local emulation by testing serverless applications in the cloud against production services using AWS SAM Accelerate. When I saw a demo of this, this was one of the most exciting things I have seen in a while. If you are a serverless developer, you should definitely check this out. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2021/10/26/main-1.png)

**GitHub Actions**

If you are looking to use GitHub Actions to build your open source projects and need to integrate with AWS, then the recent release of the of Github Actions OpenID Connect will be good news for you. In this blog post, [Using Github Actions OpenID Connector to push to AWS ECR without Credentials](https://aws-oss.beachgeek.co.uk/11p)  Robert Hafner walks you through setting this up, using an example of using Terraform to push images to Amazon ECR. Also, check out the videos where we have Richard Boyd walking you through how you can set this up.

### Quick updates

**Bottlerocket**

Amazon Elastic Kubernetes Service (EKS) now adds native support for Bottlerocket in EKS managed node groups in all commercial AWS regions. Most EKS customers today deploy their applications on worker nodes backed by operating systems that are designed for a variety of use cases. AWS launched Bottlerocket, a minimal, Linux-based open source operating system that is purpose built and optimised to run containers. When combined, EKS managed node groups and Bottlerocket give customers a simple way to provision and manage compute capacity using the latest best practices for running containers in production. Bottlerocket is now included as a built-in AMI choice for managed node groups, enabling customers to provision container optimised worker nodes with a single click.

EKS customers can easily migrate their applications to run on Bottlerocket based worker nodes and benefit from an improved node security posture. By moving to worker nodes that include only the minimal set of packages needed to run containers, customers benefit from a reduced attack surface, decreased node provisioning time and improved efficiency as more node resources are allocated to applications. This improves cluster utilisation and scale. Managed node groups provides notifications when newer EKS Bottlerocket AMIs are available, enabling customers to more easily update nodes to the latest versions of the software.

**PostgreSQL**

A couple of quick updates this week:

Following the announcement of updates to the PostgreSQL database by the open source community, we have updated Amazon Aurora PostgreSQL-Compatible Edition to support PostgreSQL 13.4, 12.8, 11.13, and 10.18. These releases contain bug fixes and improvements by the PostgreSQL community. As a reminder, Amazon Aurora PostgreSQL 9.6 will reach end of life on January 31, 2022.

Following that, we saw news that Amazon Aurora PostgreSQL-Compatible Edition now supports PostGIS major version 3.1. This new version of PostGIS is available on PostgreSQL versions 13.4, 12.8, 11.13, 10.18, and higher. PostGIS allows you to store, query and analyze geospatial data within a PostgreSQL database. PostGIS 3.1 significantly improves performance such as spatial joins, which now run up to [N]X faster on PostgreSQL 13. As an example, you could use a spatial join to count the number of people living in an area defined by the reception of mobile phones from radio towers. PostGIS 3.1 is the new default version on PostgreSQL 10 and higher starting with the new minor versions. However, you can still create older versions of PostGIS in your PostgreSQL database, e.g., if you require version stability.

### Video of the week

We have a bumper selection this week, all great and well worth watching.

**Building Open Data Lakes**

From blog posts to You Tube, there is no place where Gary Stafford will not go in order to share his knowledge and expertise on this topic. In this video (grab a cup of your favourite hot beverage) he shows you how you can build a simple open data lake on AWS using a combination of open-source software, including Debezium for change data capture (CDC), Apache Kafka, Kafka Connect, Apache Hive, Apache Spark, and Apache Hudi and Hudi's DeltaStreamer.

{% youtube E1N0RuK1PLc %}

**Terraform**

Fresh from the AWS Summit in DC, we have Tyler Lynch and Drew Mullen talking about the process of contributing upstream to the AWS provider for Terraform. Dive deep on overcoming imposter syndrome, understanding the process, validating the need, working on the code, acceptance tests, and making a pull request.

{% youtube GuLymRU42jQ %}


**Deploying to AWS with GitHub Actions**

This talk from one of my colleagues Richard Boyd, will walk you through how you can use a recently announced new capabilities (new OIDC provider as well as some new AWS developed custom GitHub actions) to show you how to deploy a serverless application using AWS SAM.

{% youtube NwGZWUgaaac %}

**Hugging Face**

This is Julien from HuggingFace...it was great to see former colleague in this great video showing you NLP models: from the Hugging Face hub to Amazon SageMaker... and back! 

{% youtube aiJaAWFGL7k %}


### Events for your diary

**Databricks | AWS Lakehouse Dev Day Live Workshop**
**November 16th 9:00 AM PT**

Delta Lake is an open source storage layer that provides ACID transactions, scalable metadata handling, and unifies streaming and batch data processing. You can use Delta Lake on top of your existing data lake. During this workshop you will learn how to:

* Make your existing Amazon S3 data lakes into a lakehouse with Delta Lake.  
* Provide an easy-to-use platform for analysts to directly query data on your data lake using SQL Analytics
* Simplify and automate data pipelines for streaming and batch data to lower costs and boost productivity for your data teams

[Read more and sign up here](https://aws-oss.beachgeek.co.uk/zs).

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)