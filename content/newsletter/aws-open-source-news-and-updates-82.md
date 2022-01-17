---
title: 'AWS open source news and updates #82'
date: '2021-09-20'
tags : [ oss-newsletter , AWS Open Source]
---
## September 20th, 2021 - Instalment #82

Newsletter #82.

Welcome to issue #82 of this newsletter, bringing you the latests updates on open source on AWS. This weeks featured new projects include cdk-nag (helping CDK developers to shift left and check their stacks against best practices), cfn-alarms (a nice tool to automate the creation of your CloudWatch alarms), aws-lambda-adapter (a project to help accelerate your web applications to serverless), as well as some new open source solutions including aws-security-hub-automated-response-and-remediation and eks-preventative-controls.

There is another great collection of community and AWS content, covering Apache Airflow, Apache Spark, Apache Kafka, AWS CDK, Kubernetes, OpenTelemetry, OpenSearch, ROS, AWS Data Wrangler, Apache Cassandra, PostgreSQL and more. For Java developers, check out the Spring Boot post and with the announcement last week of Java 17, make sure you check out the news on Amazon Corretto 17, a great openJDK based distribution.

I have not had a video for a while, but this week is a good one, with the Containers from the couch team diving deep on EKS Anywhere. New events added this week, so make sure you check those out, especially the Secure Coding Virtual Summit with some great sessions covering open source security.

Finally, we have a couple of new events added, so check those out and put them in your diary.

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Becki Lee, Igor Soroka, Lars Jacobsson, Raviraja Ganta, Tom Milner, Gunter Rotsaert, Jayden Aung, Tomas Christ, Danilo Poccia, Jasper Wang, Deenadayaalan Thirugnanasambandam, Sri Saran Balaji, Joseph Zhang, Andrew Love, Steven Heidel, Eric Kessler, Karen Xu, Kelvin Lo, Vadim Lyakhovich, Drew Rutledge, Mark Sailes, Justin Garrison, Vivek, Sheetal Joshi, Ugur KIRA, Ping Xiang, and Min Xia.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest open source projects

**cdk-nag**

[cdk-nag](https://aws-oss.beachgeek.co.uk/wx) this was my favourite new open source project last week, and provides you with the ability to check your CDK applications for best practices using a combination of available rule packs. Inspired by cfn_nag, which does the same thing for Cloudformation. Awesome stuff.

![demo](https://github.com/cdklabs/cdk-nag/blob/main/cdk_nag.gif?raw=true)

**cfn-alarms**

[cfn-alarms](https://aws-oss.beachgeek.co.uk/x4) this is a great open source project from the team at mhlabs (the MatHem teach team), which provides the ability to create CloudWatch alarms based on the resources in a CloudFormation stack. To dive a little deeper and show how this works, Lars Jacobsson put together this post, [An approach to loosely coupled CloudWatch alarms and contextual alerts](https://aws-oss.beachgeek.co.uk/x5) which also provides a reference project that you can explore in more detail.

**MLOps-Basics**

[MLOps-Basics](https://aws-oss.beachgeek.co.uk/x1) this is a great project from Raviraja Ganta that has put together a nine week learning program to help you get started with MLOps. I have not gone through it yet, but it is certainly on my todo list. Each week has a corresponding blog post to help guide you through.

![mlops](https://github.com/graviraja/MLOps-Basics/blob/main/images/summary.png?raw=true)

**aws-lambda-adapter**

[aws-lambda-adapter](https://aws-oss.beachgeek.co.uk/x2) this is a very handy tool that helps you to run web applications on AWS Lambda without changing code. The project README walks you through how it works and how to get started, so why not give it a go.

![arch](https://github.com/aws-samples/aws-lambda-adapter/blob/main/docs/images/lambda-adapter-overview.png?raw=true)

**lambda-java17-layer**

[lambda-java17-layer](https://aws-oss.beachgeek.co.uk/wy) why not celebrate the GA announcement of Java 17 by trying out this new AWS Lambda layer from Mark Sailes to enable Java 17 support. Work in progress, so kick the tyres and let Mark know how you get on.

**aws-security-hub-automated-response-and-remediation**

[aws-security-hub-automated-response-and-remediation](https://aws-oss.beachgeek.co.uk/x3) this project is an add-on solution that works with AWS Security Hub to provide a ready-to-deploy architecture and a library of automated playbooks. The solution makes it easier for AWS Security Hub customers to resolve common security findings and to improve their security posture in AWS. Detailed documentation including how to customise and create your own playbooks.

![arch](https://github.com/awslabs/aws-security-hub-automated-response-and-remediation/raw/main/SHARR_v1.2.jpg)

**eks-preventative-controls**

[eks-preventative-controls](https://aws-oss.beachgeek.co.uk/wm) this open source project will help you setup a CI/CD pipeline, integrating Conftest and OPA Rego policies (open-source tools within CNCF Open Policy Agent suite) you can automate Kubernetes preventative controls, and help you maintain compliance in your Kubernetes environments. To help you get going, Jasper Wang and Deenadayaalan Thirugnanasambandam have put together this blog post, [How to automate Amazon EKS preventative controls in CI/CD using CDK and OPA/Conftest](https://aws-oss.beachgeek.co.uk/wn)

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2021/09/16/Solution_Overview.png)

### AWS and Community blog posts

**Amazon Corretto**

Amazon Corretto is a no-cost, multi-platform, production-ready distribution of OpenJDK. Corretto is distributed by Amazon under an open source license. Amazon Corretto 17 is now generally available. This version supports the latest Java feature release JDK 17 and is available on Linux, Windows, and macOS, on x86 and arm.

It was great to see all the launch announcements last week, and I especially liked this [tweet](https://aws-oss.beachgeek.co.uk/ww). 

**Spring Boot**

Gunter Rotsaert has put together great content over the years, and last week I came across [How to Deploy a Spring Boot App on AWS ECS Cluster](https://aws-oss.beachgeek.co.uk/x7) which provides everything you need to know to get your Spring Boot apps running on (in my view) the best container service on AWS.

**Apache Kafka**

Kafka Connect is an open-source component of Apache Kafka that provides a framework for connecting with external systems such as databases, key-value stores, search indexes, and file systems. In the post, [Introducing Amazon MSK Connect – Stream Data to and from Your Apache Kafka Clusters Using Managed Connectors](https://aws-oss.beachgeek.co.uk/wo) Danilo Poccia introduces a new capability within Amazon Managed Streaming for Apache Kafka that makes it easier to manage Kafka Connect clusters. MSK Connect allows you to configure and deploy a connector using Kafka Connect with a just few clicks. To dive deeper, check out the post. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/da4b9237bacccdf19c0760cab7aec4a8359010b0/2021/08/18/msk-connect-aurora-debezium-architecture-1-1024x243.png)

**Apache Spark**

Where you are running a self managed Apache Spark cluster or using Amazon EMR, you have a number of choices to help you optimise how you run those workloads on AWS. In the post [Reduce costs and increase resource utilization of Apache Spark jobs on Kubernetes with Amazon EMR on Amazon EKS](https://aws-oss.beachgeek.co.uk/xd), Saurabh Bhutyani takes a look at how you can use the support in Amazon EMR on EKS for Spark’s pod template feature and how to use that for resource isolation and controlling costs.

![arch](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2021/09/07/BDB-1539-image001.jpg)

**Apache Airflow**

Two great posts this week on Apache Airflow. First up we have Tomas Christ, Solution Architect at eprimo GmbH, who provides some context and then dives into the details of why and how they migrated from self managed Apache Airflow to Amazon Managed Workflows for Apache Airflow in the post, [Migrating from self-managed Apache Airflow to Amazon Managed Workflows for Apache Airflow (MWAA)](https://aws-oss.beachgeek.co.uk/wp). If you looking to do the same, make sure you read Tomas' lessons learned and he provides some code to show you how they have deployed and automated running MWAA.

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/09/14/christ_amazon_MWAA_eprimo_f3.png)

Following that we have this post from AWS Community Builder Tom Milner which I thought was very cool, and shows a creative way of how you can decouple but integrate workflows in Apache Airflow, using events. This is a must read post this week, so dive into [Decouple your DAGs with an event-driven architecture on AWS](https://aws-oss.beachgeek.co.uk/x6)

![demo](https://res.cloudinary.com/practicaldev/image/fetch/s--Cz-3HJGa--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/86o179nxa2ywdxa1umxb.png)

**Apache Cassandra**

Vadim Lyakhovich shares how you can connect to your Amazon Keyspaces (for Apache Cassandra) from your local machine using some common developer tools in the post, [Connect to Amazon Keyspaces from your desktop using IntelliJ, PyCharm, or DataGrip IDEs](https://aws-oss.beachgeek.co.uk/wu)

**PostgreSQL**

In the past I have had to run benchmarks on a number of different systems, sometimes at the application level, other times at the infrastructure level. Recently, as part of some work to understand the performance characteristics of AWS Graviton2 instances, I ran a number of benchmarks on Amazon Aurora RDS MySQl and Postgres to compare the performance. I would have loved to have had this post, [Automate benchmark tests for Amazon Aurora PostgreSQL](https://aws-oss.beachgeek.co.uk/ws) from Andrew Love. A great walk through of how to use tools like pgbench to run benchmarks, and make sure you are optimising your infrastructure for your workloads. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2021/09/03/DBBLOG-1780-arch-diag.png)

**OpenSearch**

Drew Rutledge shares how you can use OpenSearch and OpenSearch Dashboards for aggregating, monitoring, and visualising application and server health, in the post [Monitoring VMware Cloud on AWS Workloads with Amazon OpenSearch Service](https://aws-oss.beachgeek.co.uk/wv) [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/77de68daecd823babbb58edb1c8e14d7106e83bb/2021/08/24/VMware-Cloud-AWS-OpenSearch-1.png)

**Kubernetes**

If you have wanted to connect your Kubernetes clusters to AWS and visualise it in Amazon EKS via the AWS Management Console, then happy days. Sri Saran Balaji and Joseph Zhang share details on exactly how you can manage that in their post, [Connect any Kubernetes cluster to Amazon EKS](https://aws-oss.beachgeek.co.uk/wq) [hands on]

![overview](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2021/09/15/Screen-Shot-2021-09-03-at-4.28.52-PM.png)

**OpenTelemetry**

A couple of posts this week caught my eye.

First up we have [Container Insights for Amazon EKS Support AWS Distro for OpenTelemetry Collector](https://aws-oss.beachgeek.co.uk/xc), a collaboration between Ugur KIRA, Ping Xiang, and Min Xia. The post looks at the AWS Distro for OpenTelemetry (ADOT) Collector integration with Container Insights for Amazon EKS (CloudWatch Container Insights collects, aggregates, and summaries metrics from your containerized applications and microservices). They cover architecture details, key components, and installation and setup verification details.

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2021/09/14/Container-Insights_img1-1024x588.png)

Next, we have, [AWS Lambda metrics support for Amazon Managed Service for Prometheus now available in AWS Distro for OpenTelemetry](https://aws-oss.beachgeek.co.uk/wt) where intern engineers Karen Xu and Kelvin Lo describe how they added metric support to the OpenTelemetry and AWS Distro for OpenTelemetry Lambda layers, and built and tested the metric pipeline to generate, collect, and export application metrics from AWS Lambda to Amazon Managed Service for Prometheus (AMP).

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/09/02/xu-lambda-amp_f1.png)

**Quantum**

Using a great analogy of Java, Steven Heidel and Eric Kessler share details of what OpenQASM is, and how it is looking to help simplify and make more accessible writing and interacting with Quantum applications in the post [AWS joins the OpenQASM 3.0 Technical Steering Committee](https://aws-oss.beachgeek.co.uk/wr). AWS has been supporting the open source effort to develop OpenQASM 3.0 for the past year, including joining the technical steering committee.

**AWS Data Wrangler**

There is not enough written or said about the fantastic open source project that is AWS Data Wrangler. In this quick start, [An AWS Professional Service open source initiative](https://aws-oss.beachgeek.co.uk/x0), you will learn more and then try and understand how you managed without.

**AWS CDK**

A number of posts this week covering one of my favourite infrastructure as code tools, AWS CDK.

Who doesn't like a good "lessons learnt" blog post? I know I am a complete sucker for these, so was very happy to read Igor Soroka's blog post, [My lessons after moving from CloudFormation to CDK](https://aws-oss.beachgeek.co.uk/xa). It will only take you a few minutes to read, and you will be all the wiser for it.

AWS Community builder Matt Morgan has put together an essential post, [Testing the Async Cloud with AWS CDK](https://aws-oss.beachgeek.co.uk/x9) to help you navigate how you can leverage AWS CDK together with a number of tools to automate tests for your asynchronous architectures. The post also covers some related reading on the topic of testing frameworks for asynchronous processing which was new to me and I am all the better for having read them. Matt has put together and shares a sample repository with examples for doing asynchronous testing of EventBridge and Step Functions.

Finally we have Becki Lee with [Securing an AWS Cloud Development Kit (CDK) App Using Regula and Open Policy Agent (OPA)](https://aws-oss.beachgeek.co.uk/xe) which takes a look at how you can use Regula (a security and compliance tool that works with CloudFormation and Terraform which I have featured in my newsletter before) with AWS CDK. [hands on] 

**Terraform**

For folks who love and use Terraform, Jayden Aung has put together this post, [How To Automate Application Deployments Using Terraform and AWS CodeDeploy](https://aws-oss.beachgeek.co.uk/x8) he walks you through how you can use Terraform to automate the creation of AWS infrastructure, and work with AWS CodeDeploy to automate deployment of a sample application.

### Videos of the week

I mentioned this last week, but it was great to see it in the flesh. Justin Garrison, Vivek and Sheetal Joshi walk you through Amazon EKS Anywhere, and show you how to deploy your first local cluster.

{% youtube n7Qh7ha5MG0 %}


### Quick updates

**Apache Kafka**

Amazon Managed Streaming for Apache Kafka (Amazon MSK) now supports the simultaneous use of multiple authentication modes and updates to encryption-in-transit settings for Amazon MSK clusters. These features allow you to migrate your clients seamlessly from one authentication mode to another and update encryption settings to match those changes. 

With this launch, you can now activate any combination of authentication modes (mutual TLS, SASL SCRAM, or IAM Access Control) on new or existing clusters, which is useful if you are migrating to a new authentication mode or need to run multiple authentication modes simultaneously. You also have the flexibility to update TLS encryption settings for data moving between clients and brokers to ensure that your encryption settings can evolve with your requirements. Additionally, you can update the Private Security Authority recognised by the cluster that can be used to sign certificates for mutual TLS authentication.

**ROS**

AWS RoboMaker, a service that allows customers to simulate robotics applications at cloud scale, now supports container images. This feature enables customers to use the container tools that they are already familiar with to build and package their code for running simulations in RoboMaker. With container support, you can now take advantage of container features such as cross-environment execution and dependency package locking while using RoboMaker. To use this feature, you create a RoboMaker Robot Application and Simulation Application with OCI compliant images stored in Amazon ECR (Elastic Container Registry). You can then use the created applications to run simulation jobs in RoboMaker.

### Events for your diary

Coming up later this week we have...

**Data in Motion: Combining the strengths of AWS and Confluent**
**September 22nd, 11am MDT**

In this webinar, Big Compass, Confluent, and AWS will come together to explore the strengths of Confluent and AWS, and how each technology can complement one another for various use cases. The webinar covers ways to combine AWS and Confluent in a hybrid platform, how to build your serverless applications with AWS and Confluent, and a look at real-world use cases for AWS and Confluent.

To find out more and [register, click here](https://aws-oss.beachgeek.co.uk/vq).

**Cloud Native Day**
**23rd September, Bern Switzerland**

What is this, an in person event returning? A stellar line up including our own Michael Hausenblas, an event looking at CNCF projects and the future of IT. Find out more and to view prices/register, by clicking [here](https://cloudnativeday.ch/en/#speakers).

**Secure Coding Virtual Summit**
**September 29, 2021**

The Secure Coding Virtual Summit is your source for everything you need to build secure code from the ground up. There are many interesting session, but check out the sessions covering how to secure and protect yourself when using open source.

Full details, including speaker line up and [how to register, here](https://aws-oss.beachgeek.co.uk/xb).

**GraphQL API security best practices with AWS AppSync and AWS Amplify**
**14th October, 11am AEST**

As a developer, the most important parts of managing your applications should always include enhancing performance while strengthening security. In this webinar, we take you through security best practices for your GraphQL API’s with AWS AppSync and AWS Amplify, providing you with an understanding of how these can be applied to your applications. In this session, you will learn about:

* GraphQL Protocol and how to configure a schema
* Possible ways to authenticate and authorise access to GraphQL APIs
* How to configure network security for your API
* How to enable observability for your API with logging, tracing or auditing

To [register for this event, use this link](https://aws-oss.beachgeek.co.uk/ue).


**Amazon SageMaker and Open-Source Tools for ML: Better Together**
**October 7 | 11 AM PT | 2 PM ET**

Many organisations rely on open-source tools to support the Machine Learning lifecycle. Amazon SageMaker has been rapidly evolving by introducing support and compatibility for various open-source frameworks. In this session, you will learn how to build a customisable ML Infrastructure based on Amazon SageMaker and open-source components. We will discuss pros and cons, the limitations of different tools that support specific stages of the ML workflow, and best practices for MLOps, to automate these stages into repeatable pipelines.

To read more and [register for this event, click here](https://aws-oss.beachgeek.co.uk/wz).


**Flink Forwards Global 2021**
**October 26th/27th**

Flink Forward Global 2021 is a 2-day virtual conference for the Apache Flink and stream processing communities. Apache Flink is an open-source distributed engine for processing data streams that can support both streaming and batch workloads. Flink Forward has keynote presentations and talks on production Flink use cases, technical deep dive sessions, and the growth of the Flink ecosystem. You can meet core Flink committers, new and experienced users, and thought leaders who share experiences and best practices in stream processing, real-time analytics, and the management of mission-critical Flink deployments in production.

[Read more and sign up here.](https://aws-oss.beachgeek.co.uk/wh)




### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)