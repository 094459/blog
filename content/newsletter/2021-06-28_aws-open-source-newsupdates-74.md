---
title: 'AWS open source news/updates #74'
date: '2021-06-28'
tags : [ oss-newsletter ]
---
## 28th June, 2021 - Instalment #74

Newsletter #74.

This week we have new open source projects that help you access your AWS EFS data without the need for a VPN, a new Red Team security tool that is in the very early stages and a number of new AWS projects to help you easily deploy open source projects such as Nextcloud or manage your own SQL Server deployments. Community and AWS posts covering Apache Airflow, Rust, Prometheus, DevOps, Apache Spark, R Studio, Grafana Loki and many more. Make sure you check out the videos as we have two great topics featured and finally keep up to date with the quick updates and the events section.

No newsletter next week as I take a week off to recharge, so expect a bumper edition on #75. 

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Nicholas Omer Chiasson, Thomas Edwards, Gavin Adams, Channy Yun, Gopi Krishnamurthy, Zachariah Elliott, Pranusha Manchala, Marco Ballerini, Kseniya Stadnik, Darryl Osborne, Nima Kaviani, Matt Asay, Rob Hilton, Sarah Watson, Paul Hargis, Jason MacKay, Raphey Holmes, Mark Roy, Chayan Panda, Michael Hsieh, Mukosi Mukwevho, Siva Ramani, Naveen Balaraman, Paul Kukiel, Antje Barth, Chris Fregley, François Bouteruche, Ankur Dahiya, Lezgin Bakircioglu, Damodar Shenvi Wagle, Sumit Mishra, Srinivas Manepalli and Tom Moore.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

**efsu**

[efsu](https://aws-oss.beachgeek.co.uk/oe) efsu is for accessing AWS EFS from your machine without a VPN. It achieves this by deploying a Lambda function and shuttling data between your machine and EFS via that function.

**scour**

[scour](https://aws-oss.beachgeek.co.uk/of) this project, still at the very early "experimental" stages, so tread carefully as there may be bugs and unexpected things, provides a modern module based AWS exploitation framework written in golang, designed for red team testing and blue team analysis. Scour contains modern techniques that can be used to attack environments or build detections for defence.

![demo](https://github.com/grines/scour/blob/main/scour-demo.gif?raw=true)

**ssm-automation-deploy-sql-developer**

[ssm-automation-deploy-sql-developer](https://aws-oss.beachgeek.co.uk/on) is an open source deployment tool for SQL Server Developer that overcomes the challenge of how to manage and create consistent SQL Server deployments. Tom Moore has put together this blog post, [Automating SQL Server Developer deployments](https://aws-oss.beachgeek.co.uk/oo), to help you walk through how you can use this project.

**ecs-windows-ci-cd-blue-green**

[ecs-windows-ci-cd-blue-green](https://aws-oss.beachgeek.co.uk/og) this project sets up a Windows based ECS Cluster using capacity provider auto-scaling with fully automated Blue/Green deployment powered by AWS Code Deploy. All you need to pass is your ECR repo name where the image resides in cdk.json via imageRepository property.

**aws-serverless-nextcloud**

[aws-serverless-nextcloud](https://aws-oss.beachgeek.co.uk/oh) Nextcloud is a popular open source file sync and share software, and this repo provides AWS CloudFormation templates to deploy NextCloud on AWS completely in a 100% serverless way which means you have no need to manage servers or manually react to monitoring events with adding capacity manually. If you are looking at or even running this today, this project is worth checking out.

![arch](https://github.com/aws-samples/aws-serverless-nextcloud/raw/main/docs/aws-nextcloud.png)

**Zendesk**

[zendesk-translation-via-aws-eventbridge-apigateway-webhook](https://aws-oss.beachgeek.co.uk/oi) this open source project from Lezgin Bakircioglu at Daniel Wellington, helps to use the Zendesk APIs in conjunction with AWS services to respond to customers in their local language. The project documents how this project differs from others, and you can read more detail about this project in the blog post, [How Daniel Wellington’s customer service department saved 99% on translation costs with Amazon Translate](https://aws-oss.beachgeek.co.uk/oj)

![arch](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2021/06/09/3451-Architecture.jpg)

### Community open source posts

**Rust**

[Beginner's Guide to Running Rust on AWS Lambda](https://aws-oss.beachgeek.co.uk/op) Nicholas Omer Chiasson has lovingly crafted this post on how to get your Rust running within a function on AWS Lambda, pitched very much at those of you how are curious enough you want to take a closer look at this increasingly popular programming language.

**Prometheus**

This popped up this week, [Basic ECS Configuration for AMP](https://aws-oss.beachgeek.co.uk/od) (other guides exist) which provides a quick start in enabling Prometheus collection for your ECS clusters (either on EC2 or Fargate). This short guide will get you up and running in minutes.

**AWS CDK**

Last week I introduced a new narrative around a fictional company, I Love My Local Farmer, which is an online marketplace that lets people buy and sell locally grown fruit and vegetables. In the latest instalment, [Writing your CDK in Java](https://aws-oss.beachgeek.co.uk/ob) François Bouteruche put himself in the shoes of this company to understand the thinking why infrastructure as code (IaC) and how this company might approach this. It is good to see Java being used, we need more Java AWS CDK example applications.

**Apache Airflow**

In the post, [Fastest way to deploy Airflow to AWS](https://aws-oss.beachgeek.co.uk/oc), Ankur Dahiya, Co-Founder and CEO of RunX, introduces you to an open source project called Opta that will help you quickly deploy Apache Airflow on Kubernetes. What is interesting about this project is that it focuses on leveraging external services for running the Metastore database for example, rather than managing/running that within the pod. I have not had a chance to try this yet, but it is on my todo list. Nice.

![arch](https://miro.medium.com/max/700/1*6GtWbj9TEWuH0EVj0VuGQA.png)

**Data Wrangler**

AWS Data Wrangler is an open-source Python library that makes it easy to work with your data in AWS on Python. The project page has a number of tutorials, and last week a new one, [S3 Select](https://aws-oss.beachgeek.co.uk/ok) was added. AWS Data Wrangler supports Amazon S3 Select, enabling applications to use SQL statements in order to query and filter the contents of a single S3 object. It works on objects stored in CSV, JSON or Apache Parquet, including compressed and large files of several TBs.

### AWS and Amazon open source posts

**Grafana Loki**

Grafana Loki was introduced in 2018 as a lightweight and cost-effective log aggregation system inspired by Prometheus. In the post, [Managing Grafana and Loki in a regulated multitenant environment](https://aws-oss.beachgeek.co.uk/o2), Marco Ballerini and Kseniya Stadnik show you how you can deploy both Grafana Loki and Grafana so that you can multiple development teams that can consume the same monitoring stack, maintaining logical storage separation, and regulating which set of data each user of the platform can query from the Grafana interface.

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/06/09/Ballerini-Grafana_F1.png)

**Continuous Delivery Foundation (CDF)**

The Continuous Delivery Foundation (CDF) serves as the vendor-neutral home of many of the fastest-growing projects for continuous integration/continuous delivery (CI/CD). Nima Kaviani, Matt Asay, Rob Hilton and Sarah Watson, were happy to announce in the post, [AWS is doubling down on improving the open source continuous delivery experience for our customers](https://aws-oss.beachgeek.co.uk/o4) that AWS is joining the CDF as a Premier member. Find out more about what this is and what it means, including how this means we will be taking our Spinnaker contributions farther and are teaming up with Netflix to help build the next generation of Spinnaker.

**Terraform**

[Continuous Compliance Workflow for Infrastructure as Code: Part 2](https://aws-oss.beachgeek.co.uk/ol) in the second of a series of posts, Damodar Shenvi Wagle and Sumit Mishra look at the technical implementation of the continuous compliance workflow. We demonstrate how to use AWS Developer Tools to create a CI/CD pipeline that releases guardrails for Terraform application workloads. The framework uses a number of open source tools as part of the solution.

![arch](https://d2908q01vomqb2.cloudfront.net/7719a1c782a1ba91c031a682a0a2f8658209adbf/2021/06/13/design.png)

A similar post, but this time taking a look at how you can build a DevSecOps software factory implementation, Srinivas Manepalli focus' on application vulnerability scanning using a number of open source tools such as git-secrets, Sysdiag Falco, Snyk and more. Great post, so make sure you read [Building an end-to-end Kubernetes-based DevSecOps software factory on AWS](https://aws-oss.beachgeek.co.uk/om)

![arch](https://d2908q01vomqb2.cloudfront.net/7719a1c782a1ba91c031a682a0a2f8658209adbf/2021/06/25/containers-pipeline-architecture-blog-v2-1.png)

**.NET Core and cdk8s**

In the post, [Build and Deploy .Net Core WebAPI Container to Amazon EKS using CDK & cdk8s](https://aws-oss.beachgeek.co.uk/o7), Siva Ramani and Naveen Balaraman provide a walkthrough of how you can use cdk8s, an open-source software development framework for defining Kubernetes applications, to deploy the sample .NET Core application on Amazon EKS. All source code is provided, and you can use this to experiment with your own .NET workloads.

![arch](https://d2908q01vomqb2.cloudfront.net/0716d9708d321ffb6a00818614779e779925365c/2020/09/01/architecture-960x1024.png)

**AWS CDK**

Paul Kukiel wrote last week, [Deploy an SPA with personalized subdomains using AWS CDK](https://aws-oss.beachgeek.co.uk/o8) showing you how you can automate the deployment of a simple single page application using AWS CDK. Full source code is provided (TypeScript) so you can take a look and use this as the base for your own projects.

**Apache Spark**

A couple of Apache Spark posts this week.

Starting off with [Customize and Package Dependencies With Your Apache Spark Applications on Amazon EMR on Amazon EKS](https://aws-oss.beachgeek.co.uk/nz), Channy Yun shared last week that you can now use customisable image support for Amazon EMR on EKS that allows you to modify the Docker runtime image that runs your analytics application using Apache Spark on your EKS cluster. What this means is you can create a container that contains both your application and its dependencies, based on the performance-optimised EMR Spark runtime, using your own continuous integration (CI) pipeline.

![arch](https://d2908q01vomqb2.cloudfront.net/da4b9237bacccdf19c0760cab7aec4a8359010b0/2021/06/22/2021-emr-on-eks-custom-image-2.png)

Following that we had a joint team of GoDaddy and AWS architects (Paul Hargis, Jason MacKay, Raphey Holmes, and Mark Roy) write, [Build accurate ML training datasets using point-in-time queries with Amazon SageMaker Feature Store and Apache Spark](https://aws-oss.beachgeek.co.uk/o5) where they explain how you can use Amazon SageMaker Feature Store and the processing power of Apache Spark to create accurate training datasets using point-in-time queries against reusable feature groups in a scalable fashion.

![arch](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2021/06/15/1-3177-Diagram.jpg)

**RStudio and Shiny**

It has been a while since I have worked with R, but when I did, it was using the open source RStudio tool, as well as Shiny, which is an open source project to simplify how you build interactive web applications in R. I was very happy to see this blog post, [Field Notes: Accelerating Data Science with RStudio and Shiny Server on AWS Fargate](https://aws-oss.beachgeek.co.uk/o6) written by Chayan Panda, Michael Hsieh and Mukosi Mukwevho, where they describe and show you how you can set up the infrastructure to run a secure, scalable and highly available RStudio and Shiny Server installation on AWS. A must read for anyone interested in R.

![arch](https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2021/06/22/rstudio_deployment_image-resized-1.png)

**Lustre**

In the post, [Spend less while increasing performance with Amazon FSx for Lustre data compression](https://aws-oss.beachgeek.co.uk/o3) Darryl Osborne dives deep and walks you through the new Amazon FSx for Lustre data compression features, sharing some simple benchmarking tests that you can use as a starting point for you to review and test your own workloads. As Darryl writes, "Enabling data compression will help you spend less while increasing performance with your FSx for Lustre file systems."

![arch](https://d2908q01vomqb2.cloudfront.net/e1822db470e60d090affd0956d743cb0e7cdf113/2021/06/23/Figure-1-performance-components-of-an-Amazon-FSx-for-Lustre-file-system-1.png)

**AWS SAM**

AWS SAM is an open source framework for building serverless applications. During the deployment process, this transforms and expands the AWS SAM syntax into AWS CloudFormation syntax, enabling you to build serverless applications faster. In this post, [Using GitHub Actions to deploy serverless applications](https://aws-oss.beachgeek.co.uk/o0) Gopi Krishnamurthy how you can take this to the next level by using GitHub Actions to build, and deploy the application in your AWS account.

**AWS Greengrass**

AWS IoT Greengrass is an open source edge runtime and cloud service that helps you build, deploy, and manage device software at the edge. In this post, [Implementing Local Client Devices with AWS IoT Greengrass](https://aws-oss.beachgeek.co.uk/ny) Gavin Adams describe use cases for client devices using a local AWS IoT Greengrass Core for connectivity, messaging, and interaction with other components via the Interprocess communication feature (IPC). What's more, he uses my favourite open source project (Node Red) as part of the walk through. Very cool indeed.

![arch](https://d2908q01vomqb2.cloudfront.net/f6e1126cedebf23e1463aee73f9df08783640400/2021/06/24/MQTT-Device-Architecture.png)

**Elasticsearch**

Many customers are moving workloads to AWS Graviton2, ARM based instance types. In the post, [Increase Amazon Elasticsearch Service performance by upgrading to Graviton2](https://aws-oss.beachgeek.co.uk/o1) Zachariah Elliott and Pranusha Manchala review prerequisites and considerations to upgrade your existing Amazon ES instances to Graviton2 with minimal downtime, as well as looking at some of the things you need to think about.

### Video of the week

A couple of videos this week.

First up we have the Data Science on AWS meet up, where colleagues Antje Barth and Chris Fregley show you  AWS Orbit Workbench, an open source framework that provides a single, unified experience for your data, analytics and machine learning projects. If you have not already grabbed a copy, check out [their amazing book, Data Science on AWS](https://aws-oss.beachgeek.co.uk/oa) - a must read.

{% youtube 3Fc3F2zd9bk %}

Following that we have a video on SRT, which is an open source video transport protocol and technology stack that optimises video streaming performance across unpredictable networks. The Streaming Video Alliance is a global technical association addressing critical challenges in streaming video, and last week on their channel on Vimeo, Thomas Edwards from Amazon demonstrated how to utilise the SRT contribution protocol to ingest content into AWS. 

You can view the original video link [on Vimeo here](https://vimeo.com/561977522).


### Quick updates

**Apache Cassandra**

Amazon Keyspaces (for Apache Cassandra), a fully managed Apache Cassandra–compatible database service, now helps you monitor and improve application read/write performance and throughput by using new Amazon CloudWatch metrics. Keyspaces integrates with CloudWatch to give you deep observability into your Cassandra workload performance. Now, Keyspaces publishes new CloudWatch metrics to help you optimize your application data models for better read/write performance by detecting unbalanced workload traffic across your partitions. In addition, the new metrics help you detect when you need to increase the number of client connections to support greater read/write throughput.

**MariaDB**

The MariaDB audit plug-in is now available for Amazon Relational Database Service (Amazon RDS) for MySQL instances using MySQL major version 8.0. The MariaDB audit plug-in is also available for instances using MySQL major versions 5.6 and 5.7, and provides event logging for database activity to help customers meet compliance and audit requirements, and troubleshoot application issues. Some of the key details for implementing the plugin are:

* Enabling and disabling the audit plug-in – Users can enable audit plug-in by creating an option group, adding MARIADB_AUDIT_PLUGIN option to the group, and attaching the option group to an RDS instance. Audit logging can be disabled by removing the option group from the instance.

* SERVER_AUDIT_EVENTS variables – These variables allow users to specify the events they want to include in the logs (CONNECTION: users connecting and disconnecting, QUERY: queries and their result, and TABLE: which tables are affected by the queries).

* SERVER_AUDIT_EXCL_USERS and SERVER_AUDIT_INCL_USERS variables – These variables specify which users' activity should be excluded from or included in the audit. SERVER_AUDIT_INCL_USERS has higher priority and all users' activity is recorded by default.


### Events for your diary

**OpenSearch community meeting**
**29th June, 9:00am PDT**

If you want to know more about what is going on in the OpenSearch project, then join the regular monthly community meetings. Read more about the agenda and how to join by [reading here](https://aws-oss.beachgeek.co.uk/o9).

**Cloud Native Day**
**23rd September, Bern Switzerland**

What is this, an in person event returning? A stellar line up including our own Michael Hausenblas, an event looking at CNCF projects and the future of IT. Find out more and to view prices/register, by clicking [here](https://cloudnativeday.ch/en/#speakers).


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen