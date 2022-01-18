---
title: 'AWS open source news and updates #87'
date: '2021-10-25'
tags : [ oss-newsletter , AWS Open Source]
---
## October 25th, 2021 - Instalment #87

Newsletter #87.

As we approach Halloween (or Dia de los Muertos/All Saints as I remember it), rest assured there is nothing scary in this weeks round up of all things open source on AWS. This weeks projects include a project that helps you implement a GitOps workflow that includes Crossplane and Argo CD, and a static analysis tool for CloudFormation templates. We have some great blog posts this week, featured topics include Apache Kafka, StackGres, Spinnaker, OpenShift, Envoy, Porting Assistant for .NET, Grafana, Qovery, Robotics and much more. We have some events later this week, so make sure you see those as there is still time to sign up for them.

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Hendra Gunadi, Matt Hansen, Romaric Philogène, Álvaro Hernández, Ryan Niksch, Mehdi Salehi, Boris Jelic, Viji Sarathy, Manabu McCloskey, Gaurav Dhamija, Nima Kaviani, Siddhi Shah, Kevin Kidd, Brandon Leach, Shrirang Moghe, Brad Bonn, Jon Slominski, Arturo Hinojosa, Kevin Nguyen, Matt Dalida, Sohil Gogri, Prasad Rao, Pavankumar Kasani, Elamaran Shanmugam, Munish Dabra, Aaron Sempf, Florian Seidel, Nathan Arnold and Praseeda Sathaye.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Community noticeboard

Álvaro Hernández shared last week the GA of StackGres 1.0.0 GA. StackGres is an Open Source Postgres-as-a-Service that runs on any Kubernetes environment, and supports over 120 extensions. Read more in his post, [StackGres 1.0.0: Open Source Postgres-aaS with 120+ Extensions](https://aws-oss.beachgeek.co.uk/10n)

![demo](https://stackgres.io/img/blog/SG_blog-StackGres_1-0-0.jpg)

### Latest open source projects

**cfsec**

[cfsec](https://aws-oss.beachgeek.co.uk/112) is an open source tool from the lovely folk at Aqua security that helps you with static analysis for CloudFormation templates to identify common misconfigurations. cfsec is early release status, so why not help this project by trying it out and if you run into any problems, please raise issues and be patient.

**eks-gitops-crossplane-argocd**

[eks-gitops-crossplane-argocd](https://aws-oss.beachgeek.co.uk/10q) this repository provides you with artefacts that will help you to deploy Crossplane server and Argo CD to an existing Amazon EKS cluster and then leverage the GitOps workflow to manage both provisioning a remote EKS cluster with Crossplane and subsequently manage application deployments to it using Argo CD. To help you get started, you can follow along in the write up from Viji Sarathy, [GitOps model for provisioning and bootstrapping Amazon EKS clusters using Crossplane and Argo CD](https://aws-oss.beachgeek.co.uk/10r)

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2021/10/14/GitOpsEKS-1.jpg)

### AWS and Community blog posts

**Apache Kafka**

Hendra Gunadi has put together a nice bench mark blog post that takes a look at the performance of Apache Kafka running on AWS Graviton2 instances using Amazon Corretto, including the Amazon Corretto Cryptographic Provider (ACCP) which can improve performance of your cryptographic operations. No spoilers, if you want to find out how well this runs, read on in [Benchmarking AWS Graviton2 and gp3 Support for Apache Kafka](https://aws-oss.beachgeek.co.uk/111)

![flame](https://dz2cdn1.dzone.com/storage/temp/15271836-1634312934225.png)

**Spinnaker**

[Enhancing Spinnaker deployment for dynamic AWS account registration](https://aws-oss.beachgeek.co.uk/10s) is a collaboration between Manabu McCloskey, Gaurav Dhamija, Nima Kaviani, Siddhi Shah, Kevin Kidd, Brandon Leach, and Shrirang Moghe, where they share how they designed and built a new interface and open source plugin for Spinnaker to dynamically manage a large number of AWS accounts.

**OpenShift**

This week we have a couple of OpenShift posts.

AWS PrivateLink allows customers to deploy workloads without the need to expose systems to the internet, and in this post, [Red Hat OpenShift Service on AWS: private clusters with AWS PrivateLink](https://aws-oss.beachgeek.co.uk/10o), Ryan Niksch takes a look at some architectures that allow you to do this with your OpenShift clusters and applications.

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2021/10/13/ROSAPrivateLink_-17.jpg)

Following that we have [How to Use Webhooks to Automate Red Hat OpenShift App Rebuilds from AWS CodeCommit](https://aws-oss.beachgeek.co.uk/10p) from Mehdi Salehi from AWS and Boris Jelic from IBM, where they show you  how you can automate their OpenShift builds when a change is pushed into their code repositories on AWS CodeCommit. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/77de68daecd823babbb58edb1c8e14d7106e83bb/2021/10/14/Automate-Red-Hat-OpenShift-AWS-CodeCommit-9s.png)

**Envoy**

Nathan Arnold and Praseeda Sathaye take a look at how to secure communications between micro services running across different Amazon EKS clusters in different AWS account, in the post [Enabling mTLS in AWS App Mesh using SPIFFE/SPIRE in a multi-account Amazon EKS environment](https://aws-oss.beachgeek.co.uk/10z). This is the third post of the series, so if you missed the others, you can find them lined here. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2021/07/21/multi-account-spire.png)

**Porting Assistant for .NET**

Porting Assistant for .NET is an open source analysis tool that reduces the manual effort and guesswork involved in porting .NET Framework applications to .NET Core or .NET 5. Prasad Rao and Pavankumar Kasani have come together to write [Modernizing legacy WCF applications to CoreWCF using Porting Assistant for .NET](https://aws-oss.beachgeek.co.uk/10w) which walks you through the process of porting legacy WCF application to CoreWCF using Porting Assistant for .NET as a standalone tool. [hands on]

![screen](https://d2908q01vomqb2.cloudfront.net/8effee409c625e1a2d8f5033631840e6ce1dcb64/2021/10/15/WCFSolutionPath.png)

**Grafana**

Elamaran Shanmugam and Munish Dabra walk you through how to set up Amazon Managed Grafana to retrieve metrics from Amazon Managed Service for Prometheus and Amazon CloudWatch from different AWS accounts running container workloads using customer managed IAM roles, in the blog post [Setting up Amazon Managed Grafana cross-account data source using customer managed IAM roles](https://aws-oss.beachgeek.co.uk/10x) [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/10/18/1000xelamaras_setup_amg-cross-account_f1_v2.png)

**Qovery**

Last week I had the chance to speak to Romaric Philogène about his blog post, [How to Build a Cloud Version of Your Open Source Software: Part 1](https://aws-oss.beachgeek.co.uk/10y) which is the first in a series of posts where he will share with you one approach in creating a multi-tenant versions of some popular open source projects, deployed via Qovery onto AWS. Make sure you do not miss this series.

**Apache Cassandra**

Arturo Hinojosa takes a look at a widely used feature of Apache Cassandra, Time to Live (TTL). This helps developers manage storage costs and simplify application logic, and the post explains how the serverless nature of Amazon Keyspaces (for Apache Cassandra) address' the challenges of using TTL in Cassandra workloads by offering a fully managed version of TTL that doesn’t impact application performance or introduce availability risks for applications. Read more in [Announcing Amazon Keyspaces Time to Live (TTL) general availability](https://aws-oss.beachgeek.co.uk/10u)

**Amazon Kinesis Data Streams**

Education technology (EdTech) company GoGuardian announces the availability of a Go Client library for Amazon Kinesis Data Streams via open source, and Kevin Nguyen, Matt Dalida, and Sohil Gogri share more details in the blog post [GoGuardian releases Go code library via open source for Amazon Kinesis Data Streams](https://aws-oss.beachgeek.co.uk/10v)

**Location Services**

In this blog post [Simulated location data with Amazon Location Service](https://aws-oss.beachgeek.co.uk/10m) from Aaron Sempf and Florian Seidel, you will find out how you use an open-source project and open-source data to generate simulated trips, as well as how to play those trips back to the Amazon Location Service Tracker. [hands on]

![map](https://d2908q01vomqb2.cloudfront.net/7719a1c782a1ba91c031a682a0a2f8658209adbf/2021/09/29/location-service-console.jpg)

**AWS Greengrass**

AWS IoT Greengrass 2.0 is an open-source edge runtime, and in this post [How Boston Dynamics and AWS use mobility and computer vision for dynamic sensing](https://aws-oss.beachgeek.co.uk/10t), Brad Bonn from Boston Dynamics and Jon Slominski from AWS share how AWS IoT Greengrass enables Spot (Boston Dynamics'  quadruped robot) to send data back to the cloud with flexibility for varied use-cases. 

![robot](https://d2908q01vomqb2.cloudfront.net/a9334987ece78b6fe8bf130ef00b74847c1d3da6/2021/10/18/Enterprise_Industrial-.jpg)

**Robotics**

CARLA is an open-source simulator for autonomous driving research. It has been developed from the ground up to support development, training, and validation of autonomous driving systems. In the post, [Run any high-fidelity simulation in AWS RoboMaker with GPU and container support](https://aws-oss.beachgeek.co.uk/110) Matt Hansen takes a look at how you can now run a CARLA autonomous driving simulator in AWS RoboMaker, thanks to the new features that make it possible to use any robot simulator and robot software to run high fidelity GPU based simulation jobs.

![demo](https://d2908q01vomqb2.cloudfront.net/a9334987ece78b6fe8bf130ef00b74847c1d3da6/2021/10/22/driving_demo2.gif)

### Quick updates

**Porting Assistant for .NET**

Porting Assistant for .NET is an open source analysis tool that reduces the manual effort and guesswork involved in porting .NET Framework applications to .NET Core or .NET 5, helping customers move to Linux faster. It identifies incompatibilities with .NET Core or .NET 5, generates an assessment report with known replacement suggestions, and assists with porting.

Porting Assistant for .NET now supports assessment and porting of Windows Communication Foundation (WCF), Open Web Interface for .NET (OWIN), and ASP.NET System.Web.Mvc namespaces to .NET Core 3.1 or .NET 5. Following the GA release of Core WCF project in February 2021, Porting Assistant can now assess and provide recommendations to port WCF applications to Core WCF. It also supports assessment and porting of OWIN and System.Web.Mvc namespace configurations to .NET Core 3.1 or .NET 5. Developers can use the existing Porting Assistant for .NET tool or Porting Assistant for .NET Visual Studio IDE extension to get started. 

**Amazon Corretto**

Amazon Corretto 11.0.13 and 8.312 are now available for download. Amazon Corretto 17 updates will be available shortly after the release is tagged in the OpenJDK 17 repository. Amazon Corretto is a no-cost, multi-platform, production-ready distribution of OpenJDK.

**AWS Amplify**

AWS Amplify for JavaScript now supports pause, resume and cancel actions on file uploads to Simple Storage Service (Amazon S3) via the Amplify Storage category. Amplify provides a set of use-case oriented UI components, libraries and command-line tools to make it easy for frontend web and mobile developer to build AWS cloud backends for their apps. With this release, developers can create experiences where end-users can reliably upload very large files, including raw video and large productivity documents. Being able to resume uploads is particularly useful for handling scenarios where a user experiences network interruption during an upload.

The Amplify JS library will now automatically segment large files into 5Mb chunks, and upload them using the Amazon S3 Multipart upload process. This method allows chunks to be uploaded in any order, and individual chunks can be re-transmitted if their upload fails or times out. Developers are able to provide callback logic to control how and when re-transmits should be attempted.

**MySQL**

Amazon RDS Proxy now supports Amazon RDS for MySQL major version 8.0. MySQL 8.0 is the latest Community Edition major version, and offers better performance, reliability, security, and manageability. 

We have updated Amazon Relational Database Service (Amazon RDS) for MySQL on Outposts to support MySQL minor versions 8.0.23, and 8.0.25. We recommend that customers upgrade to the latest minor versions to fix known security vulnerabilities in prior versions of MySQL, and to benefit from the numerous bug fixes, performance improvements, and new functionality added by the MySQL community.

**FreeRTOS**

FreeRTOS adds symmetric multiprocessing (SMP) support in the kernel, enabling developers designing FreeRTOS-based applications to utilize the SMP capabilities of multi-core microcontrollers. Multi-core microcontrollers, in which two or more identical processor cores share the same memory, allow the operating system to distribute tasks between cores to balance processor load as desired by the application. This allows applications to optimize the resource utilization of multi-core microcontrollers.

The FreeRTOS SMP kernel has a consistent set of configuration options, APIs and behaviors for systems with multiple compute cores, so developers will be able to transition between multi-core and single-core systems with minimal effort. There are reference implementations on the xcore platform from XMOS and Raspberry Pi Pico, but for more details on the FreeRTOS SMP kernel and how to port to other platforms, see Porting to FreeRTOS SMP Kernel.


### Video of the week

This week, we do not have a video rather a playlist for you. Taken from the recent O3DCon event, this playlist will show you how you can use the Open 3D Engine to build and deploy your game. Esteban Papp covers different options the engine can be configured with. He will also go over different workflows available to build the game.

Check out the [playlist here](https://aws-oss.beachgeek.co.uk/113).

{% youtube p7zNjS6-87o %}

### Events for your diary

**Enterprise Scale NLP with Hugging Face & SageMaker**
**October 26th 2021 - 5:00 PM (BST)**

In this workshop, [Getting Started with Amazon SageMaker: Training your first NLP Transformer model with Hugging Face](https://aws-oss.beachgeek.co.uk/10l) you will learn how to use Amazon SageMaker to train a Hugging Face Transformer model and deploy it afterwards. The workshop covers preparing and uploading  test dataset to S3, fine-tuning a script to be used with Amazon SageMaker Training jobs, launching a training job and storing the trained model into S3 and then deploying the model after successful training.

Everything you need will be provided, so [read more and register using this link](https://aws-oss.beachgeek.co.uk/10l).

**Flink Forwards Global 2021**
**October 26th/27th**

Flink Forward Global 2021 is a 2-day virtual conference for the Apache Flink and stream processing communities. Apache Flink is an open-source distributed engine for processing data streams that can support both streaming and batch workloads. Flink Forward has keynote presentations and talks on production Flink use cases, technical deep dive sessions, and the growth of the Flink ecosystem. You can meet core Flink committers, new and experienced users, and thought leaders who share experiences and best practices in stream processing, real-time analytics, and the management of mission-critical Flink deployments in production.

**Databricks | AWS Lakehouse Dev Day Live Workshop**
**November 16th 9:00 AM PT**

Delta Lake is an open source storage layer that provides ACID transactions, scalable metadata handling, and unifies streaming and batch data processing. You can use Delta Lake on top of your existing data lake. During this workshop you will learn how to:

* Make your existing Amazon S3 data lakes into a lakehouse with Delta Lake.  
* Provide an easy-to-use platform for analysts to directly query data on your data lake using SQL Analytics
* Simplify and automate data pipelines for streaming and batch data to lower costs and boost productivity for your data teams


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)