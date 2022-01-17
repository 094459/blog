---
title: 'AWS open source news and updates #61'
date: '2021-03-22'
tags : [ oss-newsletter ]
---
## March 22nd, 2021 - Instalment #61

Newsletter #61. 

This week we have a lot of love for Apache projects, covering Apache Lucene, Parquet, Airflow, Cassandra and HBase, with a couple of must read posts. On top of that, we have more new open source projects, including a couple of curated lists of essential resources as well as some new open source tools from AWS. Finally, the usual round up of open source posts from the community and AWS, as well as a couple of videos and short updates. But before you dive in, make sure you check out these two posts if you are using Amazon Linux or Ruby...

**Amazon Linux AMI End of Life**

First up an important reminder from Vibhav Agarwal and Cameron Sparr in the post, [Amazon ECS-optimized Amazon Linux AMI End-of-Life](https://aws-oss.beachgeek.co.uk/ba), and on April 15, 2021, the Amazon ECS-optimised Amazon Linux AMI will be ending its standard support phase and will enter a maintenance support phase. The post provides further details as well as guidance on how you can plan remediation actions.

**Ruby**

And on a similar note, a post came out late last week that you should familiarise yourself with if you are a Ruby developer. In this post, [Announcing the end of support for Ruby runtimes 1.9, 2.0, 2.1 and 2.2 for the AWS SDK For Ruby](https://aws-oss.beachgeek.co.uk/br), Matt Muller provides a reminder about the end of life for a number of Ruby version SDKs

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Michael McCandless, Jimmy Ray, Abhishek Khanna, Peng Zhang, Stephen Wu, Zach York, Rodrigue Koffi, Rafael Pereyra, John Jackson, Arun Km, Mazen Ali, Shiladitya Mandal, Norm Johanson and Philip Pittle, Sandy Millar, Dhiraj Thakur, Vibhav Agarwal, Cameron Sparr, Nathan Peck, Jena Ken, Ivan Iliev, Ali Khajeh-Hosseini, Itai Admi, Zach Scholl, Danny Steenman, Jeremy Cowan, Tod Golding and Matt Muller.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

**sacc**

[sacc](https://aws-oss.beachgeek.co.uk/bh) this open source tool from Ivan Iliev is just what you need if you are looking for a way to get new AWS session tokens. The tool will use your AWS access key and secret to request new session token from the AWS Security Token Service (AWS STS). This blog post, [SACC - Smart AWS Cli Config](https://aws-oss.beachgeek.co.uk/bi) provides more details and how to get started.

![demo](https://blog.ivnilv.com/images/sacc.svg)

**awesome-chalice**

[awesome-chalice](https://aws-oss.beachgeek.co.uk/bd) AWS Chalice is an open source framework for writing serverless Python applications based on AWS Lambda. This project is a curated list of everything you need to know to get started and go deep. Projects, labs, example code, demos and much more. If you know of stuff that is missing, why not do a PR and add it.

**aws-toolbox**

[aws-toolbox](https://aws-oss.beachgeek.co.uk/be) on a similar vibe to the curated AWS Chalice content we have a collection of DevOps tools from Danny Steenman that include shell & python scripts that automate the the stuff you need automating in AWS.

**document-processing-pipeline-for-regulated-industries**

[document-processing-pipeline-for-regulated-industries](https://aws-oss.beachgeek.co.uk/bn) - Document Processing Pipeline For Regulated Industries is a brand new open sourced solution that customers can use that implements an ML-integrated document processing pipeline using a number of AI services. The project outlines some of the potential use cases where you might find this project useful.

![arch](https://raw.githubusercontent.com/aws-samples/document-processing-pipeline-for-regulated-industries/main/images/pipeline.png)

**aws-dotnet-deploy**

[aws-dotnet-deploy](https://aws-oss.beachgeek.co.uk/b7) this shiny new open source tool is the AWS .NET deployment tool for .NET CLI, an opinionated tool that simplifies deployment of .NET applications with minimum AWS knowledge. In [Reimagining the AWS .NET deployment experience](https://aws-oss.beachgeek.co.uk/b6) Norm Johanson and Philip Pittle kick the tyres and show you how to get started with it. Nice stuff, and but make sure you are aware that the tool is currently in developer preview.

**ssm-agent-daemonset-installer**

[ssm-agent-daemonset-installer](https://aws-oss.beachgeek.co.uk/bo) this open source tool helps you to install the SSM agent onto EKS worker nodes using a Kubernetes DaemonSet. This method for configuring the nodes can be used to customize workers in an EKS Managed Node Group (MNG) after they've been deployed, at least until launch templates are supported. In the post, [Introducing the aws-ssm-agent-installer](https://aws-oss.beachgeek.co.uk/bp), Jeremy Cowan provides some background as to why this project was created and then gets you started.

**amazon-keyspaces-examples**

[amazon-keyspaces-examples](https://aws-oss.beachgeek.co.uk/bs) fresh out last week is this collection of sample code for Amazon Keyspaces (for Apache Cassandra), covering .NET, Python, Ruby and Java. These examples demonstrate various common service implementations, or infrastructure patterns that could be useful in your use of Amazon Keyspaces when building your own infrastructure. If you love Apache Cassandra, make sure you check out the blog post below.

**amazon-mwaa-examples**

[amazon-mwaa-examples](https://aws-oss.beachgeek.co.uk/bf) not wanting to be left out, some more examples but this time for Amazon Managed Workflows for Apache Airflow. Check out this new repo that hosts sample DAG's and how to's to accelerate your workflow development.

**verify environment**

[verify environment](https://aws-oss.beachgeek.co.uk/bg) another essential resources for those working with are even just looking at Amazon Managed Workflows for Apache Airflow. This script will help you check your MWAA environments are healthy, and reduce the time it takes to troubleshoot MWAA environment issues you may encounter.

### Community open source posts

**Apache Lucene**

[Open-source collaboration, or how we finally added merge-on-refresh to Apache Lucene](https://aws-oss.beachgeek.co.uk/bu) this post from Michael McCandless, PMC member and committer for the Apache Lucene project, is another must read post this week. Apache Lucene is one of the first open source projects I remember getting to know back in the early days of open source, using it to power search for a number of applications I was involved with. Nowadays, you will find it powering other projects such as Elasticsearch, and so it remains as relevant and important as ever. Michael sets the stage and provides a background of Apache Lucene, and some of the work that the project has done over the years and gives you a great insight in what it is like to collaborate in a project such as this.

**Terraform**

[Infracost diff - "git diff" but for cloud costs](https://aws-oss.beachgeek.co.uk/bj) I shared with you Infracost in #57, a project for those using Terraform that shows cloud cost estimates for Terraform projects. It helps you to quickly see the cost breakdown and compare different options upfront. In this post, Ali Khajeh-Hosseini shares more details on how you might use this project.

**lakeFS**

[Power Amazon EMR Applications with Git-like Operations Using lakeFS](https://aws-oss.beachgeek.co.uk/bk) Itai Admi writes a detailed post that will show you how to use lakeFS with Amazon EMR. lakeFS is an open source project I covered back in #40 that delivers resilience and manageability to object-storage based data lakes. With lakeFS you can build repeatable, atomic and versioned data lake operations - from complex ETL jobs to data science and analytics. In this post, Itai guides you through how configure Spark on EMR to work with lakeFS.

**CloudQuery**

[Running CloudQuery in AWS Lambda](https://aws-oss.beachgeek.co.uk/bl) CloudQuery is an open source tool that allows you to interact with your cloud infrastructure via queryable SQL or Graphs for easy monitoring, governance and security. In this post, Zach Scholl shows you how to go serverless with CloudQuery, using some of the scheduling capabilities of AWS Lambda to help you run it when you need and using other serverless services such as Amazon Aurora. Nice post.

**AWS CDK**

[AWS CDK — Where Imperative Meets Declarative](https://aws-oss.beachgeek.co.uk/bt) Jimmy Ray with a great post for java developers who want to delve into the world of infrastructure as code on AWS using the AWS Cloud Development Kit. As regular readers will know, I am a big fan of AWS CDK (check events out and put the CDK Day on your diary) and find that most of the examples and walkthroughs cover typescript. I tend to use Python, and there is not as much content out there, so it is great when other languages get the AWS CDK coverage they deserve - this time it is Java. 

### AWS open source posts

**Prometheus**

[Setting up cross-account ingestion into Amazon Managed Service for Prometheus](https://aws-oss.beachgeek.co.uk/b2) Rodrigue Koffi and Rafael Pereyra follow up from previous posts and show you how to set up central monitoring visibility for cross-account applications with Amazon Managed Service for Prometheus (AMP). This is a sit down with a cup of tea type post, so enjoy.

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/03/08/koffir_Cross-Account-Prometheus_f1.jpg)

**Apache HBase**

[Amazon EMR 6.2.0 adds persistent HFile tracking to improve performance with HBase on Amazon S3](https://aws-oss.beachgeek.co.uk/b1) in Amazon EMR 5.2.0, you can enable HBase data files (HFiles) on Amazon Simple Storage Service (Amazon S3), that provide benefits such as the ability to scale storage and compute requirements separately. Abhishek Khanna, Peng Zhang, Stephen Wu, and Zach York share how you can use persistent HFile tracking to improve your performance with the improvements available in Amazon EMR 6.2.0 (HBase 2.2.6). The post covers the benefits that can be achieved, as well as operational considerations for utilising persistent HFile tracking within Amazon EMR.

**Microsoft SQL Server on Linux**

[Deploying a highly available Microsoft SQL Server on Linux on AWS](https://aws-oss.beachgeek.co.uk/b8) Sandy Millar with probably my post of the week, where he walks you through how to successfully design and build a highly available Microsoft SQL Server on Linux. This post provides high-level insight into the components necessary to create this solution, including Microsoft SQL on Linux, ClusterLabs Pacemaker (Pacemaker) open source clustering software, leading Linux distributions, and AWS.

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/02/25/millar_clusterlabs_f1_white.png)

**Apache Cassandra**

[Build an Amazon Keyspaces (for Apache Cassandra) data model using NoSQL Workbench](https://aws-oss.beachgeek.co.uk/b9) Dhiraj Thakur shows you how to build an end-to-end data model for an internet data consumption application, using the NoSQL Workbench tool to build, design, create, query, and manage Amazon Keyspaces tables. You can also use NoSQL Workbench to convert the existing relational database management service application and build an Amazon Keyspaces model.

**Apache Parquet**

[Export and analyze Amazon DynamoDB data in an Amazon S3 data lake in Apache Parquet format](https://aws-oss.beachgeek.co.uk/b5) Mazen Ali and Shiladitya Mandal show how to use the DynamoDB-to-Amazon S3 data export feature, and convert the exported data into Apache Parquet. Apache Parquet is a very popular, high-performant columnar data format—translates into faster queries and cost savings.

![arch](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2021/03/17/Screen-Shot-2021-03-17-at-12.26.57.png)

**Apache Airflow**

[Move your Apache Airflow connections and variables to AWS Secrets Manager](https://aws-oss.beachgeek.co.uk/b3) John Jackson with a great post that shows you how you can managed your configuration details and variables in a secure way when developing your DAGs in Apache Airflow. John dives in and shows you how to easily move from storing these (variables/connections) in each environment to storing centrally using an alternate secrets backend, specifically AWS Secrets Manager. Given the nature of your workflows will most likely need to connect to external systems, make sure you check out this post out.

![flow](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/03/08/jacnjoh_apache_airflow_f1.png)

**Lustre**

[Optimizing storage management with Amazon FSx for Lustre storage quotas](https://aws-oss.beachgeek.co.uk/b4) Arun Km writes up about the Amazon FSx for Lustre storage quota feature, enabling customers to limit the amount of disk space and the number of files that a user or a group can use. It can set quotas on both users, and groups consuming several files and disk space resources.

**AWS Copilot**

[Connecting to an interactive shell on your containers running in AWS Fargate using AWS Copilot](https://aws-oss.beachgeek.co.uk/bb) Nathan Peck takes a look at an exciting new feature that was announced last week, ECS exec and how AWS Copilot makes ECS exec easy to use. AWS Copilot is an open source tool that guides developers through the process of building, releasing, and operating their containerised application, and ECS exec is the ability for users to securely establish a connection and control a remote machine (think of it as docker exec - read more in Massimo's excellent post, [NEW – Using Amazon ECS Exec to access your containers on AWS Fargate and Amazon EC2](https://aws-oss.beachgeek.co.uk/bq)). Nathan walks you through how you can leverage these capabilities in the latest version of AWS Copilot.

![demo](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2021/03/12/ezgif-5-5fd075e0dd85.gif)


### Open Data

[Open data helps recovery in the aftermath of devastating weather events](https://aws-oss.beachgeek.co.uk/bc) in this great post, Jena Ken, communications/engagement and co-technical lead from NOAA’s Big Data Program, shares how AWS and open data is helping with disaster response by providing access to aerial data and imagery through open data initiatives.

![image](https://d2908q01vomqb2.cloudfront.net/9e6a55b6b4563e652a23be9d623ca5055c356940/2021/03/15/Hurricane-imagery-acquired-by-NOAA-RSD.jpg)

### Quick updates

**Kubernetes**

Amazon Elastic Kubernetes Service (EKS) has reduced new cluster creation time by 40%, enabling you to create an EKS cluster in 9 minutes or less, on average.  Reduced cluster creation time means you can now quickly test new features and iterate on your application infrastructure faster than before. This is especially useful if you have adopted continuous integration and continuous deployment mechanisms that require frequent cluster creation thus improving agility for your teams.

**MySQL**

Amazon RDS for MySQL now supports rollback protection for database major version upgrades. For Amazon RDS for MySQL customers upgrading from MySQL 5.7 to MySQL 8.0, Amazon RDS introduced prechecks that identify potential issues before the upgrade begins, including both prechecks from MySQL and prechecks developed by the Amazon RDS team. Rollback protection extends the reliability of major version upgrades for RDS for MySQL instances beyond prechecks, and automatically reverts instances to a running state on MySQL 5.7 when upgrades to MySQL 8.0 cannot be completed. This automatic rollback process helps ensure minimal downtime in the case when upgrade issues occur, and is automatically enabled for all RDS MySQL customers.

**Amazon Corretto 16**

Amazon Corretto 16 is now generally available. This version supports the latest Java feature release JDK 16 and is available on Linux, Windows, and macOS. You can download Corretto 16 from our [GitHub Releases](https://aws-oss.beachgeek.co.uk/b0).

**AWS Copilot**

AWS Copilot launches v1.4 which now provides more operational capabilities for applications hosted on Amazon Elastic Container Service (Amazon ECS). This allows you to directly access a container to troubleshoot and run commands with ECS exec. AWS Copilot also added the ability to deploy applications from a Bitbucket repository and attach Amazon Elastic File Service (EFS) volumes.

You can now access your containers directly from your command-line shell using AWS Copilot’s exec command powered by the ECS exec feature. This lets you safely debug your applications while they’re running in the cloud. AWS Copilot also supports adding a deployment pipeline to safely deploy resources from Bitbucket repositories, in addition to the existing GitHub and AWS CodeCommit options. You may also quickly connect your application to an existing EFS file system using the new 'storage' field in your application's AWS Copilot manifest.


### Videos of the week

**Autoscaling Amazon ECS with Custom Prometheus Metrics**

Viji Sarathy joins the Containers from the couch team as he walks through a recently blog post I shared in a previous newsletter, a solution for autoscaling micro services deployed to an Amazon ECS cluster based on service metrics collected with CloudWatch SDK and CloudWatch Container Insights for Prometheus.

{% youtube JMS95gY5lp4 %}

**AWS SaaS Boost: An Open-Source Tool for Accelerating SaaS Migration**

In this video, Tod Golding will walk you through AWS SaaS Boost, a new tool that streamlines your ability to move a monolith into a SaaS delivery model.

{% youtube ekK5xA7FIZc %} 

### Events for your diary

**CDK Day**
**April 30th**

Announced this week was the second [CDK Day](https://sessionize.com/cdkday/), which will be on April 30th. Check out [the web page](https://sessionize.com/cdkday/) to find out more about the first CDK Day, which was incredible. This second event promises to be even better. The CFP is open until the 19th of March. Check out this supporting blog post, [CDK Day CFP Is Open!!!!](https://aws-oss.beachgeek.co.uk/4v) from Matt as to what to expect and what they are looking for when it comes to sessions.

**Cloud Native Rust Day**
**May 3rd**

Rust is a language empowering everyone to build secure, reliable, and efficient software. Rust is becoming more widely used in cloud native, powering everything from lightning-fast service meshes and powerful developer tools to internet-scale distributed databases.

Come explore what makes Rust a fantastic choice for new cloud native development, and learn about how the community uses Rust today. Find out [more and register here](https://aws-oss.beachgeek.co.uk/5y).

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen).