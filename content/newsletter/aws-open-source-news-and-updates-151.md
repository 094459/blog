---
title: 'AWS open source newsletter #151'
date: '2023-04-03'
tags : [ oss-newsletter, aws open source,  OpenSearch, AWS Copilot, Amazon EMR, Kubernetes, Lambda Powertools for .NET, Spring Cloud AWS, Spring Boot, Apache Hudi, Bottlerocket, Red Hat Linux, AWS Parallel Cluster, Goldilocks, NGINX, AWS CDK, Terraform, etcd, PostgreSQL, Apache Airflow]

---

## April 3rd, 2023 - Instalment #151

**Welcome**

Hello and welcome to the AWS open source newsletter, #151. This week sees more great new projects, including those covered in the [latest episode of Build on Open Source](), such as "ec2-former2" a way to host this great project to reverse engineer your CloudFormation templates, "protonizer" a cli tool for those using AWS Proton, "fortuna", a library for Uncertainty Quantification, "aws-resilience-hub-tools" a set of tools and scripts for working with the AWS Resilience Hub, "jenkins-unity-build-on-aws" a nice reference solution for those needing to build Unity projects, "amazon-cognito-passwordless-auth" a nice demo of how to do authentication sans password, and more. Also featured is content from some of the best open source projects out there, including OpenSearch, AWS Copilot, Amazon EMR, Kubernetes, Lambda Powertools for .NET, Spring Cloud AWS, Spring Boot, Apache Hudi, Bottlerocket, Red Hat Linux, AWS Parallel Cluster, Goldilocks, NGINX, AWS CDK, Terraform, etcd, PostgreSQL, and Apache Airflow. Finally, don't forget to check out the video and events section for some great events coming up over the next few weeks.

**Feedback**

Please please please take 1 minute to [complete this short survey](https://pulse.buildon.aws/survey/PJRTOUMK) and bask in the warmth of having helped improve how we support open source.

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes:  Milind Shyani, Dhrubo Saha, Nina Mishra, Fanit Kolchina,  Alex Pulver, Stavros Macrakis, Aruna Govindaraju, Victor Gu, Peter Dalbhanjan, Michael Gasch, Maciej Walkowiak, Elad Ben-Israel, Shai Ber, Amir Khairalomoum, Henrique Graca, David Tippett,Brian Hammons, Alex Lines, Vara Bonthu, Vikram Venkataraman, Aaron Miller, Geeta Gharpure, George John, Saurav Pathak, Devansh Bawari, and Ian Mckay


### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution.*

#### Tools

**protonizer**

[protonizer](https://aws-oss.beachgeek.co.uk/2ns) is a CLI tool for working with IaC in [AWS Proton](https://aws-oss.beachgeek.co.uk/2nt). Protonizer allows you take your existing IaC (infrastructure as code) templates and modules and bring them into AWS Proton to scale them out across your organisation. Note that this is an experimental project and currently only supports generating Proton templates based on Terraform and CodeBuild provisioning. The tool also currently only supports primitive HCL data types such as strings, numbers, bools, and lists of primitive types. This is currently aligned with the Proton schema types that are supported by the Proton console.

**ec2-former2**

[ec2-former2](https://aws-oss.beachgeek.co.uk/2nu) this repo helps you to deploy an EC2 instance running Former2, an open source project from AWS Hero Ian Mckay that we have featured in this newsletter and on the Build on Open Source show. Former2 is a website that allows you to generate IaC (Infrastructure as Code) templates (such as CloudFormation, CDK, Terraform, etc) from existing AWS resources. Some users have security concerns around entering their AWS credentials on an external website and prefer a private web instance. However, Former2 requires browser helper extension that only works with websites that has domain names 127.0.0.1, localhost, former2.com and www.former2.com. This repo provides CloudFormation templates that provision an EC2 instance hosting former2, so that users can remote in from their browsers to generate IaC templates and download them.

![screenshot of former2 running on ec2](https://github.com/aws-samples/ec2-former2/blob/main/images/ec2.png?raw=true)

**fortuna**

[fortuna](https://aws-oss.beachgeek.co.uk/2nj)  is a library for Uncertainty Quantification. Proper estimation of predictive uncertainty is fundamental in applications that involve critical decisions. Uncertainty can be used to assess reliability of model predictions, trigger human intervention, or decide whether a model can be safely deployed in the wild. Fortuna is a library for uncertainty quantification that makes it easy for users to run benchmarks and bring uncertainty to production systems. 

![flow diagram of fortuna in action](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2022/12/14/ml-12418-image001.jpg)

Dive deeper by checking out the blog post, [Introducing Fortuna: A library for uncertainty quantification](https://aws-oss.beachgeek.co.uk/2nk) [hands on]

**aws-resilience-hub-tools**

[aws-resilience-hub-tools](https://aws-oss.beachgeek.co.uk/2nc) This repository includes a collection of solutions and tools for AWS Resilience Hub. What is that I can hear you all ask. AWS Resilience Hub offers a single place to define, validate, and track the resiliency of applications on AWS. You can integrate AWS Resilience Hub into your software development lifecycle. This repo contains a number of tools that you can use as is or customise them to enhance how you use AWS Resilience Hub.

**amazon-security-lake**

[amazon-security-lake](https://aws-oss.beachgeek.co.uk/2ne) this tool can be used to ensure that user provided parquet data properly maps to the various schema definitions specified within the Open Cyber Schema Framework (OCSF). The Open Cybersecurity Schema Framework is an open-source project, delivering an extensible framework for developing schemas, along with a vendor-agnostic core security schema. 

**jenkins-unity-build-on-aws**

[jenkins-unity-build-on-aws](https://aws-oss.beachgeek.co.uk/2ng) this repo provides a starter kit for Unity build pipeline with Jenkins and EC2 Linux/Mac instances on AWS. Packaged up as a CDK app to make it easy to deploy, check out the README for more info on how to configure and use.

![overview of jenkins and unity build on aws architecture](https://raw.githubusercontent.com/aws-samples/jenkins-unity-build-on-aws/78d8eb4f0535583ee641f32d9db02978f9065e9d/docs/imgs/architecture.svg)

**inventory-management-for-amazon-ec2**

[inventory-management-for-amazon-ec2](https://aws-oss.beachgeek.co.uk/2ni) this repo helps do EC2 instance management with AWS Services. One of the suggested use cases is to help DevSecOps and Security Engineers who want check OS Level system metric, CCE, and CVEs automatically. cover EC2 instance management with AWS Services.It will be helpful for DevSecOps and Security Engineers who want check OS Level system metric, CCE, and CVEs automatically. The code provides a demo of one way you can achieve this.

![overview of dashboards from project](https://github.com/aws-samples/inventory-management-for-amazon-ec2/blob/main/static/images/demo/ssm-instances-performance.png?raw=true)

### Demos, Samples, Solutions and Workshops

**amazon-cognito-passwordless-auth**

[amazon-cognito-passwordless-auth](https://aws-oss.beachgeek.co.uk/2nh)  this repo provides code to help you implement Passwordless authenticaton with Amazon Cognito. Passwordless authentication improves security, reduces friction and provides better user experience for end-users of customer facing applications. Amazon Cognito provides features to implement custom authentication flows, which can be used to expand authentication factors for your application. This solution demonstrates several patterns to support passwordless authentication and provides reference implementations for a number of methods including "FIDO2" aka WebAuthn, i.e. sign with Face, Touch, YubiKey, "Magic Link Sign In" to sign in with a one-time-use secret link that's emailed to you (and works across browsers), and "SMS based Step-Up auth"  let an already signed-in user verify their identity again with a SMS One-Time-Password (OTP) without requiring them to type in their password.

![architecture for passwordless auth using magic links](https://github.com/aws-samples/amazon-cognito-passwordless-auth/blob/main/drawings/magic-link.png?raw=true)


**aws-amplify-cloud-assistant-app**

[aws-amplify-cloud-assistant-app](https://aws-oss.beachgeek.co.uk/2nd) this repo helps you build an application that demonstrates how AWS Amplify can be used to build and deploy an automated AWS account management web application powered by a conversational AI built with Amazon Lex (Figure 1). This application (hereinafter referred to as the cloud assistant) provides users with a conversational interface leveraging Natural Language Understanding (NLU) to interact with various AWS services and automates/performs all sorts of simple or advanced operations on behalf of users. It allows users to manage their AWS accounts using natural language thus reducing time spent navigating the AWS console or figuring out the proper CLI commands. You can use this sample application as an example of how Amplify in combination with other AWS services can be used to build any other kind of assistant-powered web application. 

![architecture of aws cloud assistant on amplify](https://github.com/aws-samples/aws-amplify-cloud-assistant-app/blob/main/static/images/architecture.png?raw=true)

**barcode-qr-decoder-lambda**

[barcode-qr-decoder-lambda](https://aws-oss.beachgeek.co.uk/2nf) this project provides everything you need so you can decode barcodes and QR codes. With this Lambda Function you will be able to add decoding features to your applications at scale! If you have been looking for a solution that does this, make sure you check this out.

![example lambda log showing qr code scanning execution](https://github.com/aws-samples/barcode-qr-decoder-lambda/blob/main/src/img/step-6.png?raw=true)


### AWS and Community blog posts

**Data on EKS**

Data on EKS (DoEKS), a new open-source project aimed at streamlining and accelerating the process of building, deploying, and scaling data workloads on Amazon Elastic Kubernetes Service (Amazon EKS). I am a big fan, and have previous shared my experience of using this project in my blog post, [Self managed Apache Airflow with Data on EKS](https://aws-oss.beachgeek.co.uk/2mu). In this post, [Introducing Data on EKS – Modernize Data Workloads on Amazon EKS](https://aws-oss.beachgeek.co.uk/2nm) authors Brian Hammons, Alex Lines, and Vara Bonthu dive deeper into what this project is, some of the open source technologies it will help you deploy, and how you can get involved. This weeks essential reading.

![overview of data on eks](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2023/03/22/Data-on-EKS.png)

**Kubernetes**

Plenty of nice posts this week.

First up we have, [Managing etcd database size on Amazon EKS clusters](https://aws-oss.beachgeek.co.uk/2no), where Geeta Gharpure and George John show you the importance of monitoring the etcd database within your Kubernetes clusters, why monitoring the etcd database size is important, and what you can do when you approach or exceed the database size limit. [hands on]

![dashboard for Managing etcd database size on Amazon EKS clusters](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2023/03/24/multiple-update.png)

Following that is [Right-size your Kubernetes Applications Using Open Source Goldilocks for Cost Optimization](https://aws-oss.beachgeek.co.uk/2nq) where Vikram Venkataraman and Aaron Miller share guidance on how to optimise resource allocation and right-size applications in Kubernetes environments using the open source project Goldilocks. Goldilocks is an open source project from Fairwinds that is designed to help organisations get their Kubernetes application resource requests “just right”.  Dive in to find out more and try this out for yourself. [hands on]

![architecture for goldilocks on eks](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2023/03/24/vertical-pod-autoscaler-diagram.png)

AWS Controllers for Kubernetes (ACK) lets you define and use AWS service resources directly from Kubernetes, using the Kubernetes Resource Model (KRM). In this collaboration from Victor Gu, Peter Dalbhanjan, and Michael Gasch, [Build event-driven data pipelines using AWS Controllers for Kubernetes and Amazon EMR on EKS](https://aws-oss.beachgeek.co.uk/2nz), they provide a detailed, hands on guide on how to build an event-driven data pipeline using AWS Controllers for Kubernetes (ACK) and EMR on EKS. [hands on]
 
![architecture of ack orchestration](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2023/03/22/pic1.jpg)

**OpenSearch**

We had a flurry of posts for OpenSearch fans this week, starting off with [Expanding k-NN with Lucene approximate nearest neighbor search](https://aws-oss.beachgeek.co.uk/2o1) where Stavros Macrakis provides a short post on the variety of options you have for implementing exact and approximate k-NN search

Following that we had Milind Shyani, Dhrubo Saha, Nina Mishra, and Fanit Kolchina come together to write [The ABCs of semantic search in OpenSearch: Architectures, benchmarks, and combination strategies](https://aws-oss.beachgeek.co.uk/2o2). This builds on previous blog posts (linked in the post) and dives deeper in the different ways of building a semantic search engine in OpenSearch.

Finally, in the post [Perform accent-insensitive search using OpenSearch](https://aws-oss.beachgeek.co.uk/2nx), Aruna Govindaraju shows you how to perform accent-insensitive search using OpenSearch to handle diacritics. What is "diacritics" I can hear you all ask. From the blog post itself:

> Accent-insensitive search, also called diacritics-agnostic search, is where search results are the same for queries that may or may not contain Latin characters such as à, è, Ê, ñ, and ç. Diacritics are English letters with an accent to mark a difference in pronunciation. In recent years, words with diacritics have trickled into the mainstream English language, such as café or protégé.

**AWS CDK**

In the post, [Recommended AWS CDK Project Structure for Monolithic Python Applications](https://aws-oss.beachgeek.co.uk/2o3) Alex Pulver looks at some of the recommended ways you can set out your CDK projects, and specifically  looks at the recommended project structure for monolithic applications.

![overview of cdk project structure](https://softwhat.com/images/recommended-aws-cdk-project-structure-for-monolithic-python-applications-2.png)

**Other posts and quick reads**

* [Elastic visualization queues with NICE DCV in AWS ParallelCluster ](https://aws-oss.beachgeek.co.uk/2nl) shows you how to leverage AWS ParallelCluster and the Slurm scheduler to create on-demand graphical sessions for your users using NICE DCV [hands on]

![architecture of nice dcv and aws parallellcluster ](https://d2908q01vomqb2.cloudfront.net/e6c3dd630428fd54834172b8fd2735fed9416da4/2023/03/10/CleanShot-2023-03-10-at-11.33.06.png)

* [Automate the deployment of an NGINX web service using Amazon ECS with TLS offload in CloudHSM](https://aws-oss.beachgeek.co.uk/2np) is a very nice guide on how to set up a NGINX web server on Fargate in a secure, private subnet that offloads the TLS termination to a FIPS 140-2 Level 3 HSM environment that uses the CloudHSM OpenSSL Dynamic Engine [hands on]

![architecture for secure, FIPs compliant NGINX](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2023/03/15/img1-2.png)

* [Amazon Aurora PostgreSQL database authorization using role-based access control](https://aws-oss.beachgeek.co.uk/2ny) presents a database authorisation solution using role-based access control (RBAC) [hands on]

![overview of postgresql database authorisation implementation](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2023/03/21/BLOG-2442-1.jpg)

**Technical Paper**

[Run Apache Hudi at scale on AWS](https://aws-oss.beachgeek.co.uk/2n9)

This technical guide provides guidance on getting started with Apache Hudi on different AWS services, as well as best practices and recommendations for running Apache Hudi on AWS at scale while optimising cost and performance.

### Quick updates

**PostgreSQL**

Amazon DevOps Guru for RDS is a Machine Learning (ML) powered capability for Amazon RDS that automatically detects and diagnoses database performance and operational issues. DevOps Guru for RDS is a feature of DevOps Guru, which detects operational and performance related issues for Amazon RDS engines and dozens of other resource types. DevOps Guru for RDS expands upon the existing capabilities of DevOps Guru to detect, diagnose, and provide remediation recommendations for a wide variety of database-related performance issues, such as resource over-utilisation and misbehaviour of SQL queries. Announced last week, Amazon DevOps Guru for Amazon RDS now supports Amazon RDS for PostgreSQL.

**Terraform**

Support for AWS Secrets Manager managed master passwords for RDS and Aurora instances and clusters is now in the AWS provider for Terraform (v4.61.0). See the [full release notes here](https://aws-oss.beachgeek.co.uk/2nv), as well as reading the announcement back in December for this feature [here](https://aws-oss.beachgeek.co.uk/2nw). Hats off to OSS community member Mark Ferguson for his wonderful contribution. Thanks Tyler Lynch for bringing this to my attention.

**Amazon EMR on EKS**

A couple of important updates this week.

First up we had news that you can now define where a Jupyter Enterprise Gateway (JEG) pod can be deployed when running interactive Spark workloads using managed endpoints. Amazon EMR on EKS enables customers to run open-source big data frameworks such as Apache Spark on Amazon EKS. Amazon EMR on EKS customers setup and use a managed endpoint (available in preview) to run interactive workloads using integrated development environments (IDEs) such as EMR Studio. Until now, customers running Jupyter notebooks via managed endpoints had no control over the instance type to deploy their managed endpoint on. If a managed endpoint is deployed on a spot instance, it could run into a situation where access to Jupyter notebooks is lost via the managed managed endpoint, creating an issue customers have to work around. With this feature, customers now have full control on where the JEG pod will be deployed, including the ability to specify an on-demand instance via a managed or self-managed node group.

The second update is support for EKS clusters with both managed and self-managed node groups when using interactive Spark workloads via managed managed endpoints. Amazon EMR on EKS enables  customers to run open-source big data frameworks such as Apache Spark on Amazon EKS. Amazon EMR on EKS customers setup and use a managed endpoint (available in preview) to run interactive workloads using integrated development environments (IDEs) such as EMR Studio. Until now, customers who had EKS clusters configured with self-managed node groups were unable to use EMR Studio with EMR on EKS. With this feature, customers using managed endpoints can now specify EKS clusters with managed or self-managed node groups to run their interactive workloads, with the added flexibility of defining aspects such as on-demand or spot instance types, and specify a custom AMI, among others.

**OpenSearch**

Last week we launched new observability features including log patterns, metrics analytics and support for Jaeger traces with OpenSearch 2.5 in Amazon OpenSearch Service. Log patterns provide automated grouping of log data, which can be used to provide new insights into large volumes of log data. These groupings help to detect outliers in large volumes of data, which helps improve your signal to noise ratio and allows you to identify uninteresting logs to optimise storage costs. With the new metrics analytics interface, you can now visualise multiple log-generated metrics like throughput, errors and response times in a single interface and correlate these metrics. The newly added support for popular open source Jaeger format allows you to use the capabilities of OpenSearch to analyse the trace data stored in this format. This expands on the existing support for OTEL format trace data.

The new observability capabilities and log monitoring features are available on the Amazon OpenSearch Service domains running OpenSearch version 2.5 or higher in the AWS Regions where Amazon OpenSearch Service is available.

*Request for Comment (RFC)*

The OpenSearch team are looking for feedback on a new proposal on how to update GeoIPs. The proposal is to provide a way to update a GeoIP database in GeoIP processor automatically. Read and comment on the RFC, [GeoIP database auto update to provide the latest IP to geo location mapping in GeoIP processor](https://aws-oss.beachgeek.co.uk/2nr)

*OpenSearch release 2.6.0*

OpenSearch 2.6.0 was released recently, and if you have not taken a look at the release yet, check out the highlights from this short video from OpenSearch developer advocate, David Tippett.

{{< youtube EcdYhaII-iQ >}}


**AWS Copilot**

Version 1.27 of AWS Copilot that was announced last week enables customers to fully customise AWS Cloud Formation templates, which AWS Copilot uses to provision the service, environment, pipeline, and job resources. Customers can now use AWS Cloud Development Kit (CDK) or YAML patches to change any property of those AWS resources. AWS Copilot is a command-line interface (CLI) that makes it easier for customers to build, deploy, and operate containerised applications on AWS by providing common application architecture and infrastructure patterns, user-friendly operational workflows, and configuring deployment pipelines.

With the new AWS Copilot release (1.27) users can now run copilot svc override, copilot env override, or copilot job override to enable overrides of any property of a service, environment, or job . Users can choose between two options --tool cdk or --tool yamlpatch overrides. With CDK overrides, AWS Copilot bootstraps a new CDK application inside a copilot/<resource name>/overrides/ directory of the user’s project and provides instructions inside stack.ts file on how to use the CDK. Customers can start by editing stack.ts and modify any properties of AWS Cloud Formation resources generated by AWS Copilot before a deployment. Customers who choose to use YAML patch overrides can override the AWS Cloud Formation template via .yaml patch files that adhere to the JSON patch syntax. Both options give customers full control over AWS resources and their properties that AWS Copilot deploys. The feature is available in all regions when using AWS Copilot 1.27 release.

**AWS SAM**

The AWS Toolkits enables easier development faster by supporting AWS SAM Accelerate in the IDEs letting you edit, deploy, and test your code iteratively. This update is supported in Visual Studio Code or JetBrains IDEs like IntelliJ IDEA, Rider, WebStorm, PyCharm, CLion, RubyMine, GoLand and PhpStorm. Customers can quickly deploy and run code changes by selecting the ‘Sync AWS SAM Application’ option from their IDE and run the local changes in the AWS cloud without initiating an AWS CloudFormation deployment. For example, changes to AWS Lambda functions, Lambda Layer resources, AWS StepFunction templates and Amazon APIGateway documents are deployed quickly without an infrastructure deployment. With the ability to rapidly deploy to the AWS Cloud during development, you can iteratively identify issues with your application that are challenging to detect in your local environment.

**Bottlerocket**

Bottlerocket, a Linux-based operating system that is purpose built to host container workloads, now supports FireLens. Customers using Bottlerocket with Amazon Elastic Container Services (Amazon ECS) can now benefit from a simpler way to collect logs from Bottlerocket nodes.

FireLens is a container log router for Amazon ECS that allows you to send logs to multiple destinations and that gives you extensibility to use the breadth of services at AWS or partner solutions for log analytics and storage. Please refer to the detailed guide on how to configure a custom log routing using FireLens.

This feature is available on Bottlerocket versions starting from 1.13.0.

**Red Hat Linux**

NICE DCV is a high-performance remote display protocol that is designed to help customers securely access remote desktop or application sessions, including 3D graphics applications hosted on servers with high-performance GPUs. NICE DCV version 2023.0 introduces multiple enhancements and features, such as support for Red Hat Enterprise Linux 9 and monitor selection for a full-screen remote session on Linux and macOS clients. Check out the full announcement,[ NICE DCV releases version 2023.0 with support for Red Hat Enterprise Linux 9](https://aws-oss.beachgeek.co.uk/2nb), for more details about the features and improvements.

**Kubernetes**

Amazon Elastic Kubernetes Service (EKS) announces domainless Group Managed Service Account (gMSA) support for Windows containers. This helps customers to easily authenticate applications hosted on Amazon EKS with Microsoft Active Directory (AD) using a portable user identity and a plug-in mechanism to retrieve the gMSA credentials for their Windows containers. Now, customers can run containers that require AD authentication without joining the EKS nodes to the domain, even in case of autoscaling events.

Group Managed Service Account (gMSA) is a managed domain account that provides automatic password management, service principal name (SPN) management, and the ability to delegate the management to other administrators over multiple servers/instances. This allows multiple containers or resources to share an AD account without having to authenticate each container or resource individually, or without having access to network-shared resources such as SQL Server hosts, or file-shares. Since the launch of EKS version 1.14, customers can run EKS Windows containers with gMSA by joining underlying nodes to a target AD domain. Now customers can also use a built-in plugin on the latest EKS-Optimized Windows AMIs (versions 1.22 and above) that enables non-domain-joined Windows nodes to retrieve gMSA credentials with a portable user identity instead of a host computer account.

[Domainless Windows Authentication for Amazon EKS Windows pods](https://aws-oss.beachgeek.co.uk/2nn) provides a hands on end-to-end guide on how to get started.

![architecture for Domainless Windows Authentication for Amazon EKS Windows pods](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2023/03/24/gMSA-plugin.png)

*

Also announced last week was the general availability of the AWS Controllers for Kubernetes (ACK) for EventBridge and Pipes. This launch allows you to manage EventBridge resources, such as event buses, rules, and pipes, using the Kubernetes API and resource model (custom resource definitions). Amazon EventBridge event buses and pipes are serverless event router and point-to-point integrations that enable you to create scalable event-driven applications by routing events between your own applications, third-party SaaS applications, and other AWS services. You can set up routing rules to determine where to send your events, allowing for application architectures to react to changes in your systems as they occur. The EventBridge and Pipes ACK controllers join the 20+ generally available ACK controllers and enable you to create even complex event-driven architectures on Kubernetes by connecting resources from other available ACK controllers, such as S3, SQS, Lambda, and DynamoDB, with a consistent user experience. In the initial release, the two new EventBridge ACK controllers allow you to manage EventBridge event buses, rules, archives, global endpoints, and pipes as Kubernetes resources, with more resources planned in future releases.

*

The final quick update for Kubernetes is news of the general availability of Amazon GuardDuty EKS Runtime Monitoring to detect runtime threats from over 30 security findings to protect your EKS clusters. You can read the full post from my colleague Channy, [Amazon GuardDuty Now Supports Amazon EKS Runtime Monitoring](https://aws-oss.beachgeek.co.uk/2o0)

### Videos of the week

**The Golden Path to SpringOne: What’s New in Spring Cloud AWS 3.0**

In the past year, Spring Cloud AWS has gone through a major refactoring, in many places even a complete rewrite: integration with modern AWS SDK v2 for Java, massive enhancements in S3 integration, including integration with high-throughput Transfer Manager, persistence with DynamoDB, over 10x faster SQS integration, local testing with Localstack, reduced startup time, and much more. 

Maciej Walkowiak walks you through new additions, improvements, and deprecations, as well as the motivation behind them. You’ll learn how simple it is to integrate Spring Boot applications with AWS services using Spring Cloud AWS 3.0.

{{< youtube VgfNCrIVll8 >}}


**Sessions with SAM & Friends - All about Wing**

Wing is a new open source project from Monada, which provides a new paradigm for building applications in the Cloud - in effect, a completely new programming language fit for the Cloud era. In this episode co-founders Elad Ben-Israel and Shai Ber join host Eric as they look at how to build serverless applications with Wing and talk about what the future holds for this new language.

{{< youtube GD_Ffmawm8Y >}}


**Lambda Powertools for .NET | Serverless Office Hours**

Powertools for .NET is an open source tool that provides a suite of utilities that helps with implementing observability best practices without needing to write additional custom code. Powertools for .NET simplifies your code and allows you to focus more time on the business logic. In this video, you will hear from Amir Khairalomoum and Henrique Graca  as they join regular host Julian Wood to learn about all the recently released utilities which form part of Powertools for .NET. 

{{< youtube nxzr7mr58G4 >}}


**Build on Open Source**

I hope some of you were able to catch the fourth episode of Build on Open Source, where we had special guests  Saurav & Devansh to learn more about their open source e-commerce project, Bagisto. You can catch [the replay here ](https://www.twitch.tv/videos/1780597466).

For those unfamiliar with this show, Build on Open Source is where we go over this newsletter and then invite special guests to dive deep into their open source project. Expect plenty of code, demos and hopefully laughs. We have put together a playlist so that you can easily access all (eight) of the episodes of the Build on Open Source show. [Build on Open Source playlist](https://aws-oss.beachgeek.co.uk/24u)

# Events for your diary

If you are planning any events in 2023, either virtual, in person, or hybrid, get in touch as I would love to share details of your event with readers. 

**FOSSASIA**
**April 13th-15th, Singapore**

FOSSASIA Summit 2023 returns as an in-person and online event, taking place from Thursday 13th April to Saturday 15th April at the Lifelong Learning Institute in Singapore. 

If you are interested in attending in person, or virtually, find out more about the event at the [FOSSASIA Summit 2023 page](https://aws-oss.beachgeek.co.uk/2iq).

**AWS at KubeCon + CloudNativeCon Europe 2023**
**April 18th live on twitch.tv/aws**

AWS Container Day ft. Kubernetes at KubeCon + CloudNativeCon Europe 2023 is a day-long virtual event dedicated to helping Kubernetes practitioners optimise their workloads and reduce their Ops burden. AWS and guest speakers will dive deep into the latest trends, techniques, and best practices for deploying, managing, securing, and scaling with Kubernetes. The day will feature new solution demos and interactive challenges designed to provide hands-on experience and practical insights. Attendees will walk away with new tools, mental models, and resources to innovate, optimise, and scale their applications.

Check out the amazing schedule that has been published on the event page, [AWS at KubeCon + CloudNativeCon Europe 2023](https://aws-oss.beachgeek.co.uk/2na) and register to set yourself a reminder.

**AWS Community Nordics**
**April, 20th Helsinki**

The AWS Community Day Nordics is a free full day event for AWS users to come together to network, learn from each other and get inspired. The event is organised by the community - for the community. The cfp is currently open, so if you are in the area and want to talk then here is your chance. Check out the full event details and save your space here, [AWS Community Nordics registration page](https://aws-oss.beachgeek.co.uk/2l5)

**Reducing the costs of your openCypher applications**
**May 8th, 4pm UK - online**

openCypher is an open-source project for creating graph applications. Neptune supports openCypher graph query language, and in this webinar you will learn more about the cost benefits for moving openCypher workloads to Neptune serverless. With Neptune serverless, customers can see up to 90% cost savings compared to provisioning for peak capacity. A demo of Neptune in action will be included in this session.

Head over to the You Tube holding page, [Reducing the costs of your openCypher applications](https://aws-oss.beachgeek.co.uk/2mp) 

**Cortex**
**Every other Thursday, next one 16th February**

The Cortex community call happens every two weeks on Thursday, alternating at 1200 UTC and 1700 UTC. You can check out the GitHub project for more details, go to the [Community Meetings](https://aws-oss.beachgeek.co.uk/2h5) section. The community calls keep a rolling doc of previous meetings, so you can catch up on the previous discussions. Check the [Cortex Community Meetings Notes](https://aws-oss.beachgeek.co.uk/2h6) for more info.

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)

### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)