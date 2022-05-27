---

title: 'AWS open source news and updates #114'
date: '2022-05-27'
tags : [ oss-newsletter, aws open source, Redis, DAMON, Magento, WireGuard, Amazon Linux 2, AWS Lambda Powertools, AWS Distro for OpenTelemetry, Grafana, Prometheus, Lustre, Open 3D Engine, cdk-nag, Flutter, AWS Amplify, Steampipe, OpenSearch ]

---

## May 27th, 2022 - Instalment #114

Welcome to the AWS open source newsletter #114. This weeks new open source projects feature a variety of community related projects such as "instance-scheduler" a tool to help you schedule AWS resources, "libaws" an opinionated tool that helps you simplify creation and deletion of some AWS resources, "elasticspot" a nice tool to help you reassign elastic IPs, and "auto-close-aws-accounts" that allows you to close AWS accounts if you are using AWS Organisations. We have plenty of other projects such as "amazon-ec2-spot-interrupter" a nice tool that provides a command line tool to trigger spot interruption notifications, and others that help you work with AWS Glue, simplify deployments of SageMaker notebooks, and others. 

Also featured are blog posts covering topics such as Redis, DAMON, Magento, WireGuard, Amazon Linux 2, AWS Distro for OpenTelemetry, Grafana, Prometheus, Lustre, Open 3D Engine, cdk-nag, Flutter, AWS Amplify, Steampipe, and OpenSearch. This weeks featured videos covers a super nice deep dive on AWS Lambda Powertools and a look at Kuma. Don't know what Kuma is? Well head down to the Videos and check it out.

Before diving in, check out this important notice about the end of support for the Node.js 12.x release in the AWS SDK.

**Announcing the end of support for Node.js 12.x in the AWS SDK for JavaScript (v3)**

Starting November 1, 2022, AWS SDK For JavaScript (v3) will no longer support Node.js 12.x which was EOL on April 30, 2022. If you use Node, make sure you check out the post [Announcing the end of support for Node.js 12.x in the AWS SDK for JavaScript (v3)](https://aws-oss.beachgeek.co.uk/1qk) for more details together. 

![roadmap of support for nodejs](https://d2908q01vomqb2.cloudfront.net/0716d9708d321ffb6a00818614779e779925365c/2022/05/25/nodejs-schedule-apr-2022.png)

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Nick Figgins, Allen Samuels, Joe Travaglini, Joe Hu, SeongJae Park, Abhishek Gupta, Kat Morgan, Oleksiy Volkov, Arun Donti, Abdallah Shaban, Ashish Nanda, Raajhesh Kannaa Chidambaram, Marcia Villalba, Sara Gerion, Charlotte Henkle, Nicholas Knize, James McIntyre, Mohammad Qureshi, and Sean Zheng.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest open source projects

#### Community

**instance-scheduler**

[instance-scheduler](https://aws-oss.beachgeek.co.uk/1qp) really nice tool created by AWS Community Builder Mohamed Radwan that allows you to easily schedule stopping and starting your Amazon EC2 and RDS instances. He has put together this blog post, [Create Instance Scheduler on Serverless by using Lambda, DynamoDB, API Gateway, Cognito,S3 and CloudFront](https://aws-oss.beachgeek.co.uk/1qq) to get you started.

![demo of app](https://raw.githubusercontent.com/maradwan/instance-scheduler/main/html/img/instance-view.png)

**libaws**

[libaws](https://aws-oss.beachgeek.co.uk/1qa) an interesting new tool from nathants that simplifies the provisioning and setting up of a number of AWS services. Defining what you need in YAML, you can then use the cli to build and deploy easily. Written in Go, check this out and see if this helps simplify how you create and delete infrastructure. 

**elasticspot**

[elasticspot](https://aws-oss.beachgeek.co.uk/1qb) this tool from Nick Figgins will help you simplify how to reassign Elastic IPs to new Spot instances with AWS Lambda and CloudWatch Events.

**auto-close-aws-accounts**

[auto-close-aws-accounts](https://aws-oss.beachgeek.co.uk/1qc) this tool from Raajhesh Kannaa Chidambaram leverages the recently available API to close AWS accounts to enable you to automatically close AWS Accounts when moved to a specific Organizational Unit, such as SuspendedOU or ToBeDeletedOU or BlackHole.

![demo of auto-close tool](https://github.com/raajheshkannaa/auto-close-aws-accounts/blob/master/AutoCloseAccounts.gif?raw=true)

#### Tools

**amazon-ec2-spot-interrupter**

[amazon-ec2-spot-interrupter](https://aws-oss.beachgeek.co.uk/1q9) is a simple CLI tool that triggers Amazon EC2 Spot Interruption Notifications and Rebalance Recommendations. Detailed usage guide on how this tool works, this is a tool that you should add to your toolkit.

**aws-glue-streaming-libs**

[aws-glue-streaming-libs](https://aws-oss.beachgeek.co.uk/1q6) this repo contains additions and enhancements to Spark Structured Streaming for ETL operations. This repository contains **awsglue**, a Python libary you can use to author AWS Glue Streaming ETL job that extends Apache Spark with additional data types and operations for Streaming ETL workflows, and **bin** a number of executables that allow you to run the Python library locally or open up a PySpark shell to run Glue Spark code interactively.

**audit-plugin-for-mysql**

[audit-plugin-for-mysql](https://aws-oss.beachgeek.co.uk/1q1) this Audit Plugin for MySQL Server is used by Amazon RDS for MySQL to enable logging of server activity, typically for security and compliance purposes. Make sure you read the README about contributions and roadmap for this repo.

**aws-lambda-powershell-runtime**

[aws-lambda-powershell-runtime](https://aws-oss.beachgeek.co.uk/1pz) provides the source code for the new PowerShell custom runtime for AWS Lambda that makes it even easier to run Lambda functions written in PowerShell to process events. Your code runs in an Amazon Linux environment that includes AWS credentials from an AWS Identity and Access Management (IAM) role that you manage. Julian Wood has put together a blog post, [Introducing the PowerShell custom runtime for AWS Lambda](https://aws-oss.beachgeek.co.uk/1q0) to provide a more detailed overview and a getting started guide.

**automate-vending-sagemaker-notebooks-with-eventbridge-and-lambda**

[automate-vending-sagemaker-notebooks-with-eventbridge-and-lambda](https://aws-oss.beachgeek.co.uk/1q5) this is a super nice project that helps you automate how you can provision of SageMaker notebooks to your data scientists. 

### Demos, Samples and Workshops

**amazon-chime-sdk-pstn-audio-workshop**

[amazon-chime-sdk-pstn-audio-workshop](https://aws-oss.beachgeek.co.uk/1q7) if you ever wanted to learn how to build telephony applications, then why not take a look at this workshop. This repo contains all the source code and workshop materials to help you do things like call recordings, call me back, call bridging, building a voice chat bot, call transcription and more. You can start your journey [here](https://aws-oss.beachgeek.co.uk/1q8).

**gitlab-for-eks**

[gitlab-for-eks](https://aws-oss.beachgeek.co.uk/1q2) this repo contains a workshop that focuses specifically on using the GitLab Kubernetes Agent to accomplish integration of a GitLab Instance (including GitLab.com SaaS) with an EKS cluster for managing cluster applications that are built and tested by GitLab. Previous to the availability of the GitLab Kubernetes Agent, GitLab cluster integration was done via an SSL connection to the Kubernetes Control API endpoint for a cluster. All cluster deployment happened as a matter of CI pushes to the cluster API endpoint.

**landing-zone-accelerator-on-aws**

[landing-zone-accelerator-on-aws](https://aws-oss.beachgeek.co.uk/1q3) this repo contains the Landing Zone Accelerator on AWS solution helps you quickly deploy a secure, resilient, scalable, and fully automated cloud foundation that accelerates your readiness for your cloud compliance program. A landing zone is a cloud environment that offers a recommended starting point, including default accounts, account structure, network and security layouts, and so forth. From a landing zone, you can deploy workloads that utilize your solutions and applications.

**go-redis-apprunner**

[go-redis-apprunner](https://aws-oss.beachgeek.co.uk/1pu) this repo contains code using AWS CDK to package and deploy a sample app (along with infrastructure), and run it as an AWS App Runner service that integrates with MemoryDB for Redis. My colleague Abhishek Gupta has put together an accompanying guide to walk you through how this works, in the post [Build Cloud-Native apps with AWS App Runner, Redis and AWS CDK](https://aws-oss.beachgeek.co.uk/1pv)

![architecture of sample project](https://miro.medium.com/max/1400/0*Krz2-2iDXdXwX8Ee.png)

**aws-graviton-ml-inference-armnn-example**

[aws-graviton-ml-inference-armnn-example](https://aws-oss.beachgeek.co.uk/1q4) provides sample code and steps you need to deploy ArmNN on AWS Lambda by building and loading a container image. The Lambda function will be used to efficiently perform ML inference (on Arm architecture) using an example image classification ML model in ONNX format (ResNet 50).

### AWS and Community blog posts

**OpenSearch**

Great news for folks interested in OpenSearch as v2 officially launched earlier this week. Charlotte Henkle, Nicholas Knize, James McIntyre, Mohammad Qureshi, and Sean Zheng share more details in the post, [OpenSearch 2.0 is now available!](https://aws-oss.beachgeek.co.uk/1qs).

![demo of opensearch2](https://opensearch.org/assets/media/blog-images/2022-05-26-opensearch-2-0-is-now-available/docLevelMonitor.gif)

**Steampipe**

Following up from a previous post, Bob Tordella follows that up by showing you how you can now run a security audit from within AWS CloudShell in his post, [How to perform a security audit of your AWS account in AWS CloudShell](https://aws-oss.beachgeek.co.uk/1qo) [hands on]

**DAMON**

I featured a project back in [#86](https://dev.to/aws/aws-open-source-news-and-updates-86-2hpa) called damo, a user space tool for DAMON (a data access monitoring framework subsystem for the Linux kernel). Using this, you can monitor the data access patterns of your system or workloads and make data access-aware memory management optimisations. I recently found out that this project was created by someone here at Amazon, SeongJae Park. You can catch up with the recent updates by checking out, [DAMON: Data Access Monitor](https://aws-oss.beachgeek.co.uk/10h)

![diagram of damon running](https://sjp38.github.io/img/damo_monitor_water_nsquared.gif)

**Redis**

Announced earlier this week, Redis application developers now have native support for JavaScript Object Notation (JSON) within ElastiCache and MemoryDB. In the post, [Unlocking JSON workloads with ElastiCache and MemoryDB](https://aws-oss.beachgeek.co.uk/1py) Allen Samuels, Joe Travaglini, and Joe Hu cover how JSON support works at a more technical level and provide examples of how you can write JSON documents, efficiently fetch or set portions of a JSON document in Redis. [hands on]

**Inverting Proxy**

[Inverting Proxy](https://aws-oss.beachgeek.co.uk/1qm) is an open-source reverse proxy that inverts the direction of traffic between the proxy and the backend servers. In the post, [Implementing lightweight on-premises API connectivity using inverting traffic proxy](https://aws-oss.beachgeek.co.uk/1ql) Oleksiy Volkov explores the use of lightweight application inversion proxy as a solution for multi-point hybrid or multi-cloud, API-level connectivity for cases where AWS Direct Connect or VPN may not be practical. This is super interesting, and I am wondering how else I might be able to use this tool. Essential reading this week! [hands on]

![architecture of inverted proxy](https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2022/05/19/Figure-1-1.png)

**cdk-nag**

cdk-nag (inspired by cfn_nag) validates that the state of constructs within a given scope comply with a given set of rules. Rule sets (NagPacks) includes things such as HIPAA Security, NIST 800-53 rev 4, NIST 800-53 rev 5, and PCI DSS 3.2.1. In the post, [Manage application security and compliance with the AWS Cloud Development Kit and cdk-nag](https://aws-oss.beachgeek.co.uk/1qe) Arun Donti demonstrates how to integrate cdk-nag into an AWS CDK application to provide continual feedback and help align your applications with best practices. [hands on]

**AWS Amplify and Flutter**

The AWS Amplify Flutter Authenticator is a drop in UI library that allows Flutter developers to add a customisable authentication and registration quickly. Abdallah Shaban and Ashish Nanda have collaborated on this blog post, [Setup sign-up and sign-in flows for your Flutter app in minutes with AWS Amplify](https://aws-oss.beachgeek.co.uk/1qi) which provides a hands on guide together with supporting source code. [hands on]

![demo of flutter and amplify app](https://d2908q01vomqb2.cloudfront.net/0a57cb53ba59c46fc4b692527a38a87c78d84028/2022/05/20/theme.gif)

**Other posts you might like from the past week**

* [How to Set Up WireGuard VPN on Amazon Linux 2](https://aws-oss.beachgeek.co.uk/1pw) does exactly what the titles says, and provide a walk through on how to set this up
* [Containerizing our Magento stack on AWS](https://aws-oss.beachgeek.co.uk/1px) nice post on how to deploy this popular open source eCommerce system on AWS ECS Fargate

![architecture of magento solution](https://miro.medium.com/max/1400/1*IaCUiohVt0CaPtyhduJZ6w.jpeg)

* [Prepare for Babelfish migration with the AWS SCT assessment report](https://aws-oss.beachgeek.co.uk/1qf) demonstrates how to use the AWS Schema Conversion Tool (AWS SCT) assessment report to identify where Babelfish doesn’t support specific SQL Server language features
* [Viewing collectd statistics with Amazon Managed Service for Prometheus and Amazon Managed Service for Grafana](https://aws-oss.beachgeek.co.uk/1qh) walks you through how to view metrics from a running instance of collectd on a Linux-based Amazon Elastic Compute Cloud (Amazon EC2) instance [hands on]
* [Viewing custom metrics from statsd with Amazon Managed Service for Prometheus and Amazon Managed Grafana](https://aws-oss.beachgeek.co.uk/1qg) shows you how you can view metrics from a running instance of statsd, on a Linux or Windows based Amazon Elastic Compute Cloud (Amazon EC2) instance, with Amazon Managed Service for Prometheus and Amazon Managed Grafana [hands on]
* [Deploying PyTorch Model as a Serverless Service](https://aws-oss.beachgeek.co.uk/1qr) shows you a way you can deploy a PyTorch model as a Serverless API leveraging Lambda, ECR and Serverless framework [hands on]

![architecture example of demo](https://assets-global.website-files.com/60acbb950c4d66d0ab3e2007/62862edb05637b5e40831089_6286263c5f5cc3031129a384_oS5QcXag6U4bTXjEmO_hoAl8T_9EraG7hDbEaTy2sGLDRW-kORucVFGpONrxpJBNGtZoQ7qLG-rEf9hySn3SWt4S1NUTCNCyhqVStHm05GgCCIfr1M54UOW7ZaPj5WtQiLZq-rEYAGKj-olUhg.gif)

### Case studies

* [Nurturing Continued Growth of Our Oak CT Log](https://aws-oss.beachgeek.co.uk/1qn) fascinating blog post from Lets Encrypt that walks you through the Lets Encrypt Certificate Transparency (CT) log, built using open source components running on Amazon RDS

### Quick updates

**Open 3D Engine**

Earlier this week saw the release of 22.05.0 of Open 3D Engine (O3DE) an Apache 2.0-licensed open source project. O3DE is an engine for real-time 3D development that provides developers with a modular foundation for building games and 3D simulations across a variety of applications like robotics, digital twins, automotive, healthcare, and more. In our ongoing support of O3DE, the AWS Game Engine and Developer Services team contributed numerous features to version 22.05.0 including:

Read more about this release in the announcement, [AWS for Games latest contribution to the Open 3D Engine (O3DE)](https://aws-oss.beachgeek.co.uk/1qj)

**Amazon FSx for Lustre**

Amazon FSx for Lustre, a service that provides cost-effective, high-performance, and scalable file storage for compute workloads, now supports root squash. This administrative feature adds an additional layer of file access control on top of the current network-based access control and POSIX file permissions that FSx for Lustre provides. Using the root squash feature, you can restrict root level file system access from clients that access an FSx for Lustre file system as root.

IT administrators often give users root access on their compute instances to perform privileged operations such as changing system configurations or installing and removing software. However, for instances attached to a Linux based file system, such as FSx for Lustre, a user who is granted root access also gets full access to files on the file system, which may not be desirable for certain scenarios. With root squash enabled, you can continue to give users root access to instances attached to an FSx for Lustre file system, while limiting file system permissions to those of a less-privileged user and group.

**Redis**

Amazon ElastiCache for Redis and Amazon MemoryDB for Redis now support natively storing and accessing data in the JavaScript Object Notation (JSON) format. With this launch, application developers can effortlessly store, fetch, and update their JSON data inside Redis without needing to manage custom code for serialisation and deserialisation. Using ElastiCache and MemoryDB, you can now efficiently retrieve and update specific portions of a JSON document without needing to manipulate the entire object, which can help improve performance and help reduce cost. You can also search your JSON document contents using the JSONPath query syntax. JSON support is available for Redis version 6.2 and above for ElastiCache and MemoryDB in all available regions, at no additional cost.

**Grafana**

Amazon Managed Grafana now supports a new API for creating Grafana API tokens, as well as support for new plugins, Grafana version 8.4, and workspace tags. With CreateWorkspaceApiKey, customers can create Grafana API tokens without having to log into the Grafana workspace console, enabling users to programmatically create, delete, and manage Grafana resources such as dashboards, alerts, and data sources. Amazon Managed Grafana adds support for Github, Moogsoft, Pixie, and Windrose plugins, enabling customers to connect, query, and visualize data from additional data sources. Existing and new Amazon Managed Grafana workspaces now support Grafana version 8.4, with no action required from users. Customers can now tag Amazon Managed Grafana workspaces to help simplify organisation and cost management of workspaces. Tags are labels in the form of key-value pairs that may be attached to Amazon Managed Grafana workspaces to search, filter, or allocate costs.

**AWS Distro for OpenTelemetry**

Earlier in the week was the announcement of the general availability of AWS Distro for OpenTelemetry (ADOT) for metrics, a secure, production-ready, AWS-supported distribution of the OpenTelemetry project. With this launch, customers can use OpenTelemetry APIs and SDKs in Java, .Net, and JavaScript to collect and send metrics to Amazon CloudWatch, Amazon Managed Service for Prometheus, and other monitoring destinations supported by the OpenTelemetry Protocol (OTLP). Part of the Cloud Native Computing Foundation (CNCF), OpenTelemetry provides open source APIs, libraries, and agents to collect distributed traces and metrics for application and infrastructure monitoring. With ADOT, you can instrument your applications just once to send metrics and traces to multiple monitoring solutions and use auto-instrumentation agents to collect traces and metrics without changing your code. Use AWS Distro for OpenTelemetry to instrument your applications running on Amazon Elastic Compute Cloud (EC2), Amazon Elastic Container Service (ECS), and Amazon Elastic Kubernetes Service (EKS).

For your observability needs, you can choose Amazon CloudWatch, Amazon Managed Service for Prometheus, or one of the AWS partner destinations. You can configure and deploy the latest version of the AWS Distro for OpenTelemetry for container services and Amazon EC2 by using AWS CloudFormation templates, the AWS Command Line Interface, Kubectl commands, or the ADOT EKS add-on. Developers can use the several supported receivers such as Prometheus as well as OpenTelemetry SDKs to collect or instrument their applications for collecting correlated metrics and traces.

### Videos of the week

**AWS Lambda Powertools**

AWS Lambda Powertools is a suite of TypeScript utilities for AWS Lambda functions to ease adopting best practices such as tracing, structured logging, custom metrics, and more. Join Marcia Villalba and Sara Gerion as they dive deep into this project, getting hands on and showing you more about this tool. Extra bonus points as Sara uses Terraform throughout.

{{< youtube KsVQMaZDU20 >}}


**Kuma**

Kuma is an open source service mesh that can run on every cloud, in a single or multi-zone capacity, across both Kubernetes and VMs. In this video, Kat Morgan walks you through how to install and run Kuma on AWS ECS

{{< youtube TL4Lw9Pgjlo >}}


### Events for your diary


**BOSC 2022**
**July 13-14, Madison, Wisconsin, USA**

The Bioinformatics Open Source Conference (BOSC) has been held annually since 2000, and this year AWS is proud to be a platinum sponsor for this event. BOSC covers all aspects of open source bioinformatics software and open science, including (but not limited to) these topics, Open Science and Reproducible Research, Open Biomedical Data, Citizen/Participatory Science, Standards and Interoperability, Data Science Workflows, Open Approaches to Translational Bioinformatics, Developer Tools and Libraries, Inclusion, and Outreach and Training. This is a hybrid event (in person/virtual) and you find out more by checking out the event page, [BOSC 2022](https://aws-oss.beachgeek.co.uk/1li)

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)

**OpenSearchCon 2022**
**Sept 21st, 2022 Seattle**

Come to the first annual OpenSearchCon!

This day-long conference will be packed with presenters who build and innovate with OpenSearch. It doesn’t matter if you’re just getting started on your OpenSearch journey, running giant clusters, or contributing tons of code; the event is for everyone. Join us to celebrate the progress and look into the future of the project. Admission is free, and registration will be open in the next few weeks. All you will need to do is sign up, and get to Seattle!

Check out the full details, including signing up and location, at the [meetup page here](https://aws-oss.beachgeek.co.uk/1n1).


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)