---
title: 'AWS open source newsletter #152'
date: '2023-04-10'
tags : [ oss-newsletter, aws open source, AWS Amplify, Swift, Apache Airflow, MWAA, Kubernetes, Amazon EKS, AWS CDK, OpenSearch, AWS Controllers for Kubernetes, Redis, Prometheus, AWS SAM, Terraform, Streamlit, Steampipe, Grafana, Amazon Redshift]

---

## April 10th, 2023 - Instalment #152

**Welcome**

Hello and welcome to the AWS open source newsletter, #152 an Easter special. This week sees more great new projects including, "redshift-test-drive" a set of essential tools for Amazon Redshift users, "simple-database-archival-solution" a nice tool to help you archive your data, "attribution-gen" a Go tool to help you build open source attribution documents, "aws-glue-data-catalog-federation" a library to help you federate your Glue catalog, "subnet-utilization-monitor-for-amazon-vpc" a handy tool to keep on top of your IP address allocation, "AlexaGPT" a demo of integrating Alexa with you know what, and more!

We also have some great posts covering your favourite open source projects, which this week include Swift, Apache Airflow, Kubernetes, OpenSearch, AWS Controllers for Kubernetes, Redis, Prometheus, AWS SAM, Terraform, Streamlit, Steampipe, Grafana, and more!

**Feedback**

Please please please take 1 minute to [complete this short survey](https://pulse.buildon.aws/survey/PJRTOUMK) and bask in the warmth of having helped improve how we support open source.

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes: Isaac Levin, Sebastien Stormacq, Elamaran Shanmugam, Aaron Stuyvenberg, Sheetal Joshi, Liwen Wu, Alejandro Molina, Anandhi Bumstead, Nicholas Knize, Bill Beckler, Kris Freedain, Daniel (dB.) Doubrovkine, Shubham Shah, Marcin Sodkiewicz, Emre Yılmaz, and  Mukesh Murugan.

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution.*

#### Tools

**simple-database-archival-solution**

[simple-database-archival-solution](https://aws-oss.beachgeek.co.uk/2or) s an open source solution, which you can deploy in your AWS account to archive data to AWS. SDAS will connect to your database which can be on premises or in the cloud, map the schema, perform validation, and finally transfer data to AWS for storage in Amazon S3. This is accomplished by primarily leveraging AWS Step Functions and AWS Glue. The main purpose of SDAS is to provide an out-of-the-box solution that easily allows customers to archive data in the cloud coming from on premises or cloud-hosted databases.

![architecture for solution simple database archival solution](https://github.com/awslabs/simple-database-archival-solution/blob/main/images/architecture.png?raw=true)

**redshift-test-drive**

[redshift-test-drive](https://aws-oss.beachgeek.co.uk/2ot) is an amalgamation of a number of useful Redshift tools. These consists of Workload Replicator, Replay Analysis, External Object Replicator, and Node Config. Customers are always trying to reproduce issues or workloads from clusters or to do what-if scenarios. A customer can easily clone a production cluster, but replicating the workload is more complicated. Workload Replicator was created to bridge that gap, working together with Replay Analysis. External Object Replicator replicates COPY commands objects, Copy manifest objects, and Spectrum objects in source cluster to the target s3 location. Finally, Node Configuration Comparison utility answers a very common question on which instance type and number of nodes should we choose for your workload on Amazon Redshift. Each tool has a separate and detailed README to help you get started. 

![architecture review of node compare](https://github.com/aws-samples/amazon-redshift-config-compare/blob/main/serverless-v2/images/architecure-serverless.png?raw=true)

**attribution-gen**

[attribution-gen](https://aws-oss.beachgeek.co.uk/2os) is a useful tool for Go developers, and helps you generate license attributions files. Currently it only works with Go projects using modules. As the README states:

> We hope you find this tool useful; please verify the accuracy of the detected third party code and licenses.


**aws-glue-data-catalog-federation**

[aws-glue-data-catalog-federation](https://aws-oss.beachgeek.co.uk/2oq)  enables you to link your external metastores to AWS Glue Data Catalog. This eliminates the need to migrate your metastore into the AWS Glue Data Catalog in order to leverage other AWS services, such as AWS Lake Formation, Amazon Athena, Amazon Redshift & Amazon EMR. These are open-source base implementations of federation connectors. These connectors provide the necessary translation layer between AWS Glue Data Catalog and your external metastore. Currently, the only support external federation to the Apache Hive Metastore.

**subnet-utilization-monitor-for-amazon-vpc**

[subnet-utilization-monitor-for-amazon-vpc](https://aws-oss.beachgeek.co.uk/2ol) This sample deploys a Lambda function that monitors IPv4 utilisation for Amazon VPC Subnets and published the metrics to CloudWatch as custom metrics. It provides metrics around the number of available IPv4 IPs, Total IPs, Used IPs and IP utilisation. Check out the README for more info. The tool is easily deployed via a CloudFormation template.

**AlexaGPT**

[AlexaGPT](https://aws-oss.beachgeek.co.uk/2ok) is a project for those of you who like to dabble and experiment making skills for your Alexa. Aaron Stuyvenberg has come up with this project that makes your smart speaker actually smart. This serverless function plumbs ChatGPT API into Alexa using AWS Lambda.

![screenshot of alexa skills screen](https://github.com/astuyve/AlexaGPT/blob/main/skill_builder_query.png?raw=true)

**aws-application-networking-k8s**

[aws-application-networking-k8s](https://aws-oss.beachgeek.co.uk/2oh) is an implementation of the Kubernetes Gateway API. This project is designed to run in a Kubernetes cluster and orchestrates AWS VPC Lattice resources using Kubernetes Custom Resource Definitions like Gateway and HTTPRoute. You can find out more about this, and how to set it up by reading the supporting blog post, [Introducing AWS Gateway API controller for Amazon VPC Lattice, an implementation of Kubernetes Gateway API](https://aws-oss.beachgeek.co.uk/2oi) where Sheetal Joshi and Liwen Wu demonstrate how to install Gateway API controller and configure a sample Amazon VPC Lattice service network using Gateway class implemented by the controller.

![overview of architecture of aws gateway api](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2023/03/31/Lattice.png)

**mv-simple-lambda-api-router**

[mv-simple-lambda-api-router](https://aws-oss.beachgeek.co.uk/2oj) is a simple and lightweight lambda api router from Alejandro Molina. The repo provides detailed guidance on how you can use it, some example apps, as well as warnings about making sure you are using it for the right use case. The project is also pretty nifty, an Alejandro is very proud of his micro optimisation as we can see from the project readme:

> This router is capable of managing 50K in less than 100 ms

### Demos, Samples, Solutions and Workshops

**aws-iot-greengrass-component-kvs-webrtc**

[aws-iot-greengrass-component-kvs-webrtc](https://aws-oss.beachgeek.co.uk/2op) this repo helps you buildU an AWS IoT Greengrass V2 (GGv2) Component that will acquire video from a Video for Linux (v4l) device, open an Amazon Kinesis Video Streams (KVS) with WebRTC signaling channel as 'Master', and when a 'Viewer' connects to that signaling channel, publish the acquired video. This project uses GStreamer to acquire, process, and encode video. The 'pipeline' and source can easily be changed or customized to suit different video sources, processing, or formats.

![architecture of iot greengrassv2 kvs webrtc gstreamer sample](https://github.com/awslabs/aws-iot-greengrass-component-kvs-webrtc/blob/main/images/arch.png?raw=true)

**websocket-sessions-management**

[websocket-sessions-management](https://aws-oss.beachgeek.co.uk/2on) This project creates a sample app for demonstrating how to keep anonymous user context when using WebSocket APIs. The goal is to demonstrate how to handle reconnects without losing user context. To help you get started, you can read the supporting blog post from Alexey Paramonov, [Managing sessions of anonymous users in WebSocket API-based applications](https://aws-oss.beachgeek.co.uk/2oo).

![architecture for websocket sessions management](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2023/03/09/websocket1-919x1024.png)

### AWS and Community blog posts

**Finch**

Finch is an open-source container runtime client for MacOS that has been published by AWS and has an Open Source license. Finch's command-line syntax is not 100% compatible with that of docker but is quite close. In this issue raised in the CDK repo ([#23680, Optionally use Finch to build container images](https://aws-oss.beachgeek.co.uk/2ou)) Michael S. Fischer suggests how CDK should support Finch for building and publishing container images. If you have views, jump into the discussion and let them know.

**OpenSearch**

We had another great selection of new content for OpenSearch fans last week.

Starting off with news that you can now join a dedicated OpenSearch slack channel, Anandhi Bumstead, Nicholas Knize, Bill Beckler, and Kris Freedain co-created this post, [Meet your new OpenSearch Project Slack workspace](https://aws-oss.beachgeek.co.uk/2o9) that looks at how to join and review the code of conduct and principals that will ensure a welcoming and vibrant place to collaborate.

Next we had Daniel (dB.) Doubrovkine who wrote, [Technical roadmap: OpenSearch extensibility](https://aws-oss.beachgeek.co.uk/2oa) looks at an exciting new proposal around how to improve the current plugins model with a look at the concept of extensions. Essential reading for folks familiar with or working with OpenSearch.

Finally, we had Shubham Shah who put together this deep dive post [KNN Search with OpenSearch and OpenAI Embeddings: An In-Depth Guide](https://aws-oss.beachgeek.co.uk/2ob) that will help  you gain familiarity with KNN, and then building a full functional backend and search UI. The post will walk you through using OpenSearch for the search engine, OpenAI for vector embeddings and ReactiveSearch for cloud hosting of the backend and the search UI components. [hands on]

![overview of knn search graph](https://cdn.hashnode.com/res/hashnode/image/upload/v1679920183365/979801f9-8d2c-4998-ba19-0ddcdc6f094f.png?auto=compress,format&format=webp)

**OpenTelemetry**

Marcin Sodkiewicz has put together this post, [AWS & OpenTelemetry](https://aws-oss.beachgeek.co.uk/2oc) where he show you how to setup OpenTelemetry collector on AWS in Gateway mode, how and why to centralise your OTEL configuration. [hands on]

![architecture overview of otel solution](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*XHvAygcvGE5gN8XbxHeyeA.png)

**Streamlit**

[Streamlit](https://aws-oss.beachgeek.co.uk/2od) is an open source framework for creating data applications in Python. In this post, [Deploy Streamlit app to AWS with Elastic Beanstalk](https://aws-oss.beachgeek.co.uk/2oe) Emre Yılmaz shows you how you can deploy your Streamlit apps onto Amazon Elastic Beanstalk

**Steampipe**

I love solutions that help provide clarity to users, and I think this one fits into that category.  The wonderful folks at Steampipe have put together this blog post, [Visualizing AWS with Relationship Graphs](https://aws-oss.beachgeek.co.uk/2of), at how you can use Steampipe to generate a number of different visualisations and graphs to help you better understand your AWS environments. 

![example steampipe visualisation](https://steampipe.io/_next/image?url=%2Fimages%2Fblog%2F2023-03-aws-relationship-graphs%2FRole.png&w=3840&q=75)

**dotNET Core**

dotNET developer Mukesh Murugan has put together a step by step tutorial to help fellow dotNET developers deploy their dotNET Core applications onto AWS. In [Hosting ASP.NET Core WebAPI on Amazon EC2: Step-by-Step Guide ](https://aws-oss.beachgeek.co.uk/2om) he takes a ASP.NET Core WebAPI demo application (using .NET 7), and deploys this onto AWS using EC2 and Docker.

**Grafana**

In the post, [Using Open Source Grafana Operator on your Kubernetes cluster to manage Amazon Managed Grafana](https://aws-oss.beachgeek.co.uk/2o8) Elamaran Shanmugam provides a hands on guide on how to use Grafana Operator from your Kubernetes cluster to add Amazon Managed Service for Prometheus as a data source and create dashboards in Amazon Managed Grafana in a Kubernetes native way. [hands on]

![overview of sample dashboard created in grafana](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2023/04/03/Image-4-1024x506.png)

**Apache Airflow**

I was busy over the weekend putting together a blog post that I hope will be of use to those starting out with Apache Airflow and Amazon Redshift. In [Working with Managed Workflows for Apache Airflow (MWAA) and Amazon Redshift](https://aws-oss.beachgeek.co.uk/2ow) I share some of the ways you can orchestrate your Redshift tasks using Airflow, and provide code that helps you get everything up and running. Whilst this is intended for those just beginning, there is plenty of details and information that maybe more experienced folk might have missed. As always, please let me know how I can improve these kinds of posts.

![screenshot of mwaa and redshift post](https://ricsuepublicresources.s3.eu-west-1.amazonaws.com/images/airflow-redshift-import-data.png)

**Other posts and quick reads**

* [Behind the Scenes on AWS Contributions to Cloud Native Open Source Projects](https://aws-oss.beachgeek.co.uk/2o6) is a fantastic write up of some of the contributions being made by AWS to CNCF projects, and a must read this week
* [Announcing the Amazon Braket Challenge winners of the QHack 2023 Hackathon](https://aws-oss.beachgeek.co.uk/2o7) looks at some of the winners of this recent Hackathon, including sharing source code of some of the projects
* [New – Self-Service Provisioning of Terraform Open-Source Configurations with AWS Service Catalog](https://aws-oss.beachgeek.co.uk/2og) explores the new capability within AWS Service Catalog that enables you to define and provision your Service Catalog resources using Terraform [hands on]

### Quick updates

**Apache Airflow**

This announcement is going to make a lot of folk happy, as it was something that came up frequently in conversations with developers. Amazon Managed Workflows for Apache Airflow (MWAA) now supports shell launch scripts for environments version 2.x and later. Amazon MWAA now adds the ability to customise the Apache Airflow environment by launching a customer-specified shell launch script at start-up to work better with existing integration, infrastructure, and compliance needs. Customers can use shell launch script to install custom runtimes, set environment variables, and update configuration files. Expect a blog post showing you how to use this some time soon.

**Swift**

Announced last week was the general availability of macOS support for AWS Amplify for Swift (v2.7.1)! This launch allows developers to build cloud-connected apps for iOS and macOS apps. Developers can now leverage the power of the AWS Amplify across iOS and macOS platforms for production workloads. We will be announcing support for watchOS and tvOS in future releases of the library. Developers can now use Amplify Library for Swift via the Swift Package Manager to build apps for iOS and macOS platforms with Auth, Storage, Geo and more features. Developers will continue to have access to the same Amplify Command Line Interface (CLI) tools to configure and manage their cloud resources. With the Amplify Library for Swift, developers will also have direct access to the underlying AWS SDK for Swift through the escape hatch to unlock additional capabilities from AWS services.

**AWS CDK**

AWS Cloud Development Kit (CDK) now enables developers to validate Infrastructure as Code (IaC) templates against policy-as-code tools during the development lifecycle. Developers can now receive fast and actionable feedback about security or configuration issues, as defined by organisational policies, during CDK application development cycles. By verifying compliance with organisational policies at the early stages of development, the teams can enhance the success rate of the deployment phase for their CDK applications.

On release, AWS CDK will include support for AWS CloudFormation Guard with CfnGuardValidator - A policy validation plugin which enables the use of AWS CloudFormation Guard for policy validations. A pre-defined set of AWS Control Tower proactive controls are included with the plugin. 

With plugin enabled, once your CDK application has finished synthesising the template, the plugin is triggered automatically to validate generated CloudFormation templates against your policies. The plugin will execute policies validations, interpret the results, and provide a final report. The report presents a summary of the validation outcome (allow/deny), along with details about any detected misconfigurations. If non-compliance is found with respect to a specific policy, a root-cause analysis is provided, along with suggestions for mitigation. Customers can utilise this feature with other tools, including but not limited to KICS, Open Policy Agent (OPA), and Checkov. Developers can create validation plugins for these tools based on their organisation's specific requirements and preferences.

**Kubernetes**

AWS Controllers for Kubernetes (ACK) lets you define and use AWS service resources directly from Kubernetes.  The AWS Controllers for Kubernetes (ACK) service controller for Amazon MemoryDB for Redis is now generally available. Customers can provision and manage MemoryDB resources using the ACK service controller. ACK service controller for MemoryDB aims to simplify provisioning and managing your database by enabling you to define and use MemoryDB resources directly from your Kubernetes cluster. This lets you take advantage of MemoryDB to support your Kubernetes applications without needing to define MemoryDB resources outside of the cluster or run and manage in-memory database capabilities within the cluster.

**Redis**

Amazon ElastiCache for Redis now makes it simpler and faster for you to get started with setting up an ElastiCache for Redis cluster. The new console experience offers streamlined navigation and minimal settings required to configure a cluster, in just a few clicks. You can now create an ElastiCache for Redis Cluster by selecting from one of the three pre-defined configurations: Production, Dev/Test, and Demo. Each configuration includes default cluster settings based on best practices that are tailored to your use case. 

**Prometheus**

Amazon Managed Service for Prometheus is a fully managed Prometheus-compatible service that monitors and provides alerts on containerised applications and infrastructure at scale. Prometheus is a Cloud Native Computing Foundation open source project for monitoring and alerting that is optimised for container environments such as Amazon EKS and Amazon ECS. With this release, customers can send up to 500M active metrics to a single workspace after filing a service limit increase request, and can create many workspaces per account, enabling the storage and analysis of billions of Prometheus metrics.


### Videos of the week

**AWS SAM for .NET Developers**

Are you a .NET developer and you want to run some code as efficiently as possible in the cloud? Have you heard of serverless and wanted to get started building serverless applications as quickly as possible? If so, you should take a look at the AWS Serverless Application Model, or SAM. In this video, my fellow developer advocate Isaac Levin walks you through the concepts introduced with SAM and how we can use it to build awesome .NET serverless applications in the cloud.

{{< youtube Dvn4x-sf29Y >}}

**Swift**

My colleague Sebastien Stormacq also used AWS SAM in his talk at the recent /dev/world/2023 event, where he showed you how you can deploy  your server-side Swift applications on AWS Lambda. He looks at how you can start with a traditional Vapor app running unmodified in the cloud, and then deploying a native Swift Lambda function using the open source Lambda Swift runtime and a deployer SPM plugin.

{{< youtube vdJ9GHdQ-XU >}}

**Build on Open Source**

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

