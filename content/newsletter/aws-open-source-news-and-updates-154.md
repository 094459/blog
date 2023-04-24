
---
title: 'AWS open source newsletter #154'
date: '2023-04-24'
tags : [ oss-newsletter, aws open source, Apache Oozie, Apache Airflow, Deep Java Library, DJL, mwaa-local-runner, MWAA, Trusted Language Extensions for PostgreSQL, Supabase, PostgreSQL, Jupyter, Grafana, Opus, Papermill, Apache Spark, HiveQL, Amazon EKS, Kubernetes, Amazon EMR, RStudio, USBGuard, Amazon Corretto, AWS Amplify, Apache Hive Metastore, LoRaWAN, gMSA, Python, OpenSearch, AWS Copilot, Marten, Flutter]

---

## April 24th, 2023 - Instalment #154

**Welcome**

Hello and welcome to the AWS open source newsletter, #154, the newsletter that just keeps on giving....in this case, keeps giving you brand new open source projects to practice your four freedoms on. We have another great selection of projects for you as always, starting off with "cfn-teleport" an essential cli tool for Cloudformation users, "aither" an interesting collaborative development tool using virtualised desktops on containers, "tabular-column-semantic-search" a tool to help you find similar types of data in your data lakes, "resource-lister" and "komiser" tools that help you manage your AWS resources, "resource-utilization" helps you track your AWS resource utilisation, "iot-network-traffic-control-and-load-testing-simulator" an interesting load and chaos testing example, and more!

Also covered in this weeks edition are posts covering a broad range of open source technologies, including Apache Oozie, Apache Airflow, Deep Java Library, DJL, mwaa-local-runner, MWAA, Trusted Language Extensions for PostgreSQL, Supabase, PostgreSQL, Jupyter, Grafana, Opus, Papermill, Apache Spark, HiveQL, Amazon EKS, Kubernetes, Amazon EMR, RStudio, USBGuard, Amazon Corretto, AWS Amplify, Apache Hive Metastore, LoRaWAN, gMSA, Python, OpenSearch, AWS Copilot, and Marten!

As always, we have a selection of great videos including a link to the AWS Container Day, and don't miss the events section as we regular add new events for your diary, and this week we have a few new ones you should be aware of.

**Feedback**

Please please please take 1 minute to [complete this short survey](https://pulse.buildon.aws/survey/PJRTOUMK) and bask in the warmth of having helped improve how we support open source.

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes: Daniel Schroeder, Efe Karakus, Maish Saidel-Keesing,  David Tippet, Varun Jain, Satya, Kevin Mun, Yan Cui, Sean McGrail, Vinay Kumar Khambhampati, Amol Guldagad, Sandeep Singh, Cristobal Espinosa, Matt Cline, Sai Kiran Akula, and Samiullah Mohammed

**.NET on AWS**

It was great to see [this tweet](https://aws-oss.beachgeek.co.uk/2pq) around our continued support for open source projects that help .NET developers on AWS. This month we supported the [Marten](https://aws-oss.beachgeek.co.uk/2pr) project. The Marten library provides .NET developers with the ability to use the proven PostgreSQL database engine and its fantastic JSON support as a fully fledged document database. Very cool. Make sure you follow [@dotnetonAWS](https://aws-oss.beachgeek.co.uk/2qz) to keep up on other projects we are sponsoring. 

Also hot off the press is news that the .NET open-source team announced the release of Core WCF v1.4.0-preview with Queue Transport support and RabbitMQ implementation. RabbitMQ implementation also allows developers to use Amazon MQ for RabbitMQ for dispatching and processing messages out of the box. Core WCF is an open-sourced project where we collaborate with Microsoft actively as partners. Specific AWS contributions of note include the end-to-end design of Queue Transport layer that enables multiple queue providers to be built on top of the existing transport layer; and additional Core WCF packages: CoreWCF.RabbitMQ and CoreWCF.RabbitMQ.Client that enable customers to use AmazonMQ for RabbitMQ from Core WCF and opens up a pathway for customers to use different messaging technologies on AWS and not be tied to just MSMQ on-premises. 

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution.*

#### Tools

**aws_cloudwatch_insights**

[aws_cloudwatch_insights](https://aws-oss.beachgeek.co.uk/2qy) is both a command line tool and a python API to simplify interacting with AWS Cloudwatch Insights. Check out the README for how you can use this, but it allows you to start building some nice automations. I am going to be giving this a test drive as I am a big fan of CloudWatch Insights. Make sure to check this project out.

**cfn-teleport**

[cfn-teleport](https://aws-oss.beachgeek.co.uk/2qh) is a fabulous new tool from Daniel Schroeder that provides a command-line tool which can move CloudFormation resources between stacks. Very cool indeed.

![demo of cfn-teleport](https://raw.githubusercontent.com/udondan/cfn-teleport/main/docs/demo.gif)

**aither**

[aither](https://aws-oss.beachgeek.co.uk/2qi) looks like an interesting project from the folk at Enoki, which is a containerised Linux desktop with multiplayer features, making it easy to collaborate on technical projects. 

![demo of aither ](https://github.com/enoki-inc/aither/blob/main/demo.gif?raw=true) 

**simple-database-archival-solution**

[simple-database-archival-solution ](https://aws-oss.beachgeek.co.uk/2or) is an open source solution which we featured in #152 (I know I know, I can hear you saying this is cheating and this is not new!), that provides a nice solution you can deploy in your AWS account that will help you to archive data to AWS. A new blog post has been written that dives deeper into this project and helps you get started. Check out [Announcing the Simple Database Archival Solution](https://aws-oss.beachgeek.co.uk/2q7)

![architecture of sdas](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2023/04/18/SDAS-architecture.png)

**komiser**

[komiser](https://aws-oss.beachgeek.co.uk/2qd)  is an open-source cloud-agnostic resource manager. It integrates with multiple cloud providers to build a cloud asset inventory, and helps you break down your cost at the resource level. You can check out this blog post,[ Deploy Komiser to AWS with Terraform](https://aws-oss.beachgeek.co.uk/2qe), where Mohamed Labouardy helps you get this project up and running and deployed.

![dashboard of komiser](https://uploads-ssl.webflow.com/6373a295d370a41a1a802e8c/6438febc9d95fd44eb92d166_Screenshot%202023-04-12%20at%2017.54.16.png)

**resource-utilization**

[resource-utilization](https://aws-oss.beachgeek.co.uk/2qn) This project aims to provide easy to read resource utilisation metrics across several services and resource types. With both cost optimisation and sustainability in mind. This is just the first and most simple version of an account wide resource utilisation metric & dashboard, to get overall insights on actually how much room for optimisation is available. As a baseline, initial version considers only Amazon EC2 service CPU Utilisation.

![overview of architecture for resource-utilisation project](https://github.com/aws-samples/resource-utilization/blob/main/assets/resource-utilization.drawio.png?raw=true)

**iot-network-traffic-control-and-load-testing-simulator**

[iot-network-traffic-control-and-load-testing-simulator](https://aws-oss.beachgeek.co.uk/2qo) this repo shows you how to deploy IoT Simulator with two CDK stacks that deploy a load testing tool that simulates hundreds to millions of IoT devices, and a control network traffic on your IoT application, to simulate real-world environment where network quality may vary. It also uses [Locust](https://aws-oss.beachgeek.co.uk/2qp), a modern open source load testing framework, installed on Amazon Elastic Container Service (ECS) of which workers are configured to send MQTT topic to configured AWS IoT Core endpoint.

![architecture for iot load and break simulator](https://github.com/aws-samples/iot-network-traffic-control-and-load-testing-simulator/blob/main/imgs/architecture_normal.png?raw=true)

**resource-lister**

[resource-lister](https://aws-oss.beachgeek.co.uk/2qt) is an open source, NO CODE, interactive, python-based command line utility. Resource Lister can generate list of AWS resources (for supported services) in single or multiple accounts in consumable CSV, or flatten JSON format. Resource Lister uses AWS SDK for Python(Boto3) sessions and underlying Boto3 List APIs to connect multiple configured child accounts and generate the resource list. It essentially simplifies accessing of Boto3 list APIs. Resource Lister also provides an option to send generated list to file, s3, or print on command line. Resource Lister can be configured to run from Cloud9, Cloudshell, EC2 or from your machine.

![how it works diagram](https://github.com/awslabs/resource-lister/blob/main/imgs/0_utility_interface.PNG?raw=true)

**common-io-ble**

[common-io-ble](https://aws-oss.beachgeek.co.uk/2qk) provides an abstraction layer which offer a common set of APIs to control the device, perform Generic Access Profile (GAP) and Generic Attribute (GATT) operations for FreeRTOS developers. You can read more about this over at, [Bluetooth Low Energy library](https://aws-oss.beachgeek.co.uk/2ql).

**common-io-basic**

[common-io-basic](https://aws-oss.beachgeek.co.uk/2qr)  provides a basic set of I/O libraries (HAL, Hardware Abstraction Layer) for pins and serial communications on embedded devices. Check out the [Common I/O](https://aws-oss.beachgeek.co.uk/2qs) documentation page for more info on how to use these.

### Demos, Samples, Solutions and Workshops

**ecs-trainium-examples**

[ecs-trainium-examples](https://aws-oss.beachgeek.co.uk/2qm) this repo demonstrates how to deploy Trainium instances on ECS Cluster with all mandatory requirements to run AWS Neuron SDK and ready for training a Machine Learning model.

**prompt-engineering-playground-with-sagemaker**

[prompt-engineering-playground-with-sagemaker](https://aws-oss.beachgeek.co.uk/2qq) is a utility which provides a UI to do prompt engineering within SageMaker Studio. Check out the comprehensive README that dives deeper into the topic and provides a good background in prompt engineering before walking you through the deployment of this utility.

**tabular-column-semantic-search**

[tabular-column-semantic-search](https://aws-oss.beachgeek.co.uk/2qu) Finding similar columns in a data lake has important applications in data cleaning and annotation, schema matching, data discovery, and analytics across multiple data sources. The inability to accurately find and analyse data from disparate sources represents a potential efficiency killer for everyone from data scientists, medical researchers, academics, to financial and government analysts. The code in this repo helps you to build a solution  for searching for similar columns based on column name, column content, or both. To help you bootstrap this project, you can read the detailed post,[ Build a semantic search engine for tabular columns with Transformers and Amazon OpenSearch Service](https://aws-oss.beachgeek.co.uk/2qv)

![architecture for tabular column semantic search](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2023/02/22/BDB-2789-image001-arch-diagram-1024x523.png)

### AWS and Community blog posts

**Community roundup**

We had a great selection of community authored content that caught my eye this week.

In [#144](https://dev.to/aws/aws-open-source-newsletter-144-22h) we featured [dynamodb-shell](https://aws-oss.beachgeek.co.uk/2hs), a simple CLI for DynamoDB modeled on isql, and the MySQL CLIs. Satya has put together a short post, [AWS DynamoDB Shell - ddbsh](https://aws-oss.beachgeek.co.uk/2qc), where he walks through some examples of using this. 

Next up we have Kevin Mun with his post, [I bring up my full-stack AWS application in ten minutes, here are the open-source tools you will be using](https://aws-oss.beachgeek.co.uk/2qf) shares his experience (and delight!) in using one open source tool, sst, to help make his life easier and more productive.

From sst to AWS CDK, this time AWS Hero Yan Cui with his take on the strengths and weaknesses of AWS CDK based on his own use cases and experience. Worth reading anything from Yan as you know he has put a lot of thought into it.

The final post in this round up comes from the folk behind [ZeusCloud](https://aws-oss.beachgeek.co.uk/2n1),  an open source tool to help you discover, prioritise, and remediate your risks in the cloud that we featured in [#150](https://dev.to/aws/aws-open-source-newsletter-150-352g). In [AWS Account ID: An Attacker's Perspective](https://aws-oss.beachgeek.co.uk/2qg), Varun Jain shares details about how exposing your AWS Account number is useful to potential attackers. I certainly learned a few things from reading this post.

**AWS Libcrypto for Rust**

AWS Libcrypto for Rust (aws-lc-rs) is a new open source cryptographic library for Rust software developers with FIPS cryptographic requirements. In the blog post, [Introducing AWS Libcrypto for Rust, an Open Source Cryptographic Library for Rust](https://aws-oss.beachgeek.co.uk/2pz), Sean McGrail provides a hands on introduction to this library and shows you how you can get started. [hands on]

![graph of aws-ls-rs benchmarks](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2023/04/14/libcrypto-rust-chart.png)

**Trusted Language Extensions for PostgreSQL**

One of my favorite open source related announcements at re:Invent 2022 was Trusted Language Extensions for PostgreSQL, an open source development kit that lets developers create extensions in their preferred language with built-in safety guardrails. In this post, [Supabase Makes Extensions Easier for Developers with Trusted Language Extensions for PostgreSQL](https://aws-oss.beachgeek.co.uk/2qb) we take a look at how Supabase are using Trusted Language Extensions for PostgreSQL to make the Supabase platform easier to deploy across multiple cloud providers and to make it easier for developers to add extensions in Supabase. Essential reading this week!

**Apache Airflow**

I put together a couple of blog posts last week on Apache Airflow. The first was borne out of wanting to know more about the recently launched (and hotly anticipated) feature that allows you to now specify a startup script that will launch at the start of your worker nodes. In [Exploring Shell Launch Scripts on Managed Workflows for Apache Airflow (MWAA) and mwaa-local-runner](https://aws-oss.beachgeek.co.uk/2po) I show you how you can use mwaa-local-runner to test this before you deploy to your Managed Workflows for Apache Airflow (MWAA), including how to patch a current issue I found that stopped the environment variables working within mwaa-local-runner.

![workflow diagram of how startup scripts outline](https://res.cloudinary.com/practicaldev/image/fetch/s--1VgtDTZI--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://ricsuepublicresources.s3.eu-west-1.amazonaws.com/images/airflow-variables.png)

As I was writing this, I was speaking to some developers who were looking to experiment with mwaa-local-runner but wanted to do this in their AWS Cloud9 developer environments. I put this recipe together, [Getting mwaa-local-runner up on AWS Cloud9](https://aws-oss.beachgeek.co.uk/2pp). I would welcome feedback on how to improve the setup and make it even easier to deploy mwaa-local-runner on Cloud9.

The final Apache Airflow update (this time, not written by me!), is an update to the MWAA migration documentation,  [Migrating workloads from AWS Data Pipeline to Amazon MWAA](https://aws-oss.beachgeek.co.uk/2px), where you can check this new section that has been added to help those who are using AWS Data Pipeline service migrate those pipelines to Apache Airflow.

**Apache Oozie**

[Apache Oozie](https://aws-oss.beachgeek.co.uk/2q4) is an open source workflow scheduler system to manage Apache Hadoop jobs. In the post, [Accelerate HiveQL with Oozie to Spark SQL migration on Amazon EMR](https://aws-oss.beachgeek.co.uk/2q5), Vinay Kumar Khambhampati, Amol Guldagad, and Sandeep Singh walk you through a solution that automates the migration from HiveQL to Spark SQL with Oozie workloads, and is battle tested in a real world use case. [hands on]

![overview illustration of an apache oozie job](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2023/04/03/BDB-2696-image001.png)

**Deep Java Library**

The [Deep Java Library (DJL)](https://aws-oss.beachgeek.co.uk/2q1) is a deep learning framework built from the ground up to support users of Java and JVM languages like Scala, Kotlin, and Clojure. In this case study, [How Sportradar used the Deep Java Library to build production-scale ML platforms for increased performance and efficiency,](https://aws-oss.beachgeek.co.uk/2q2) the Sportradar team discusses the challenges they encountered building production ready machine learning inference solutions, and the solutions they created to build their model inference platform using the DJL. 

![architecture overview of DJL by SportsRadar](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2023/04/06/soln_overview.png)

**Other posts and quick reads**

* [Running Jupyter notebooks as hybrid jobs with Amazon Braket](https://aws-oss.beachgeek.co.uk/2q0) looks at how users can seamlessly scale up from exploratory notebook into repeatable and reliable experiments by running Jupyter notebooks directly as Hybrid Jobs (a fully-managed, containerised environment to run experiments combining classical and quantum computations) [hands on]

![overview of hybrid jobs and papermill architecture](https://d2908q01vomqb2.cloudfront.net/5a5b0f9b7d3f8fc84c3cef8fd8efaaa6c70d75ab/2023/04/14/CleanShot-2023-04-14-at-11.15.21.png)

* [Monitoring Amazon DevOps Guru insights using Amazon Managed Grafana](https://aws-oss.beachgeek.co.uk/2pw) walks you through integrating the insights generated from DevOps Guru with Amazon Managed Grafana [hands on]
* [Neural encoding enables more-efficient recovery of lost audio packets](https://aws-oss.beachgeek.co.uk/2py) explores a new paper written by the Amazon Chime team that looks at how to tackle audio quality when you have unreliable networks, and how Amazon is contributing improvements upstream to Opus ( an open source codec for interactive speech and audio transmission over the Internet)

![diagram of lbrr ](https://assets.amazon.science/dims4/default/60ff210/2147483647/strip/true/crop/1920x1080+0+0/resize/1200x675!/format/webp/quality/90/?url=http%3A%2F%2Famazon-topics-brightspot.s3.amazonaws.com%2Fscience%2Fd4%2F91%2Fc071a4304f64b9e4b3115aa64371%2Fdred-vs.%20LBRR.png)

* [Managing edge-aware Service Mesh with Amazon EKS for AWS Local Zones](https://aws-oss.beachgeek.co.uk/2q3) looks at how Amazon EKS clusters deployed across multiple AWS Local Zones can be used with a service mesh to simplify edge aware routing
* [Connect Amazon EMR and RStudio on Amazon SageMaker](https://aws-oss.beachgeek.co.uk/2q8) provides a hands on guide on how you can connect your RStudio on SageMaker domain with an EMR cluster [hands on]

![overview of rstudio and amazon emr integration](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2023/03/22/sagemaker-emr.drawio.png)

* [Protecting Linux-based IoT devices against unintended USB access](https://aws-oss.beachgeek.co.uk/2qa)  shows how to protect Linux-based IoT devices and computers against unintended USB access with [USBGuard](https://aws-oss.beachgeek.co.uk/2q9), an open source framework for implementing USB device authorisation policies (what kind of USB devices are authorised) as well as method of use policies (how a USB device may interact with the system) [hands on]

![architecture of usbguard and iot devices](https://d2908q01vomqb2.cloudfront.net/f6e1126cedebf23e1463aee73f9df08783640400/2023/04/14/IOTB-613-architecture.png)

* [Simplify and speed up Apache Spark applications on Amazon Redshift data with Amazon Redshift integration for Apache Spark](https://aws-oss.beachgeek.co.uk/2qw) explains how you can use the Amazon Redshift integration for Apache Spark to build and deploy applications with Amazon EMR on Amazon EC2, Amazon EMR Serverless, and AWS Glue to automatically apply predicate and query pushdown to optimise the query performance for data in Amazon Redshift [hands on]


**Tutorial**

I put together a deep dive tutorial, [Automate the Provisioning of Your Apache Airflow Environments](https://aws-oss.beachgeek.co.uk/2ps), which walks you through how to setup and automate both the provisioning of your Managed Workflows for Apache Airflow (MWAA) environments, and how to automate the deployment of your workflows (DAGs) using a simple CI/CD pipeline.

![architecture of ci/cd pipeline with mwaa](https://www.buildon.aws/_next/image?url=https%3A%2F%2Fwww.buildon.aws%2Fraw-post-images%2Ftutorials%2Fautomating-mwaa-environments-and-workflows%2Fimages%2Fairflowcici-end2end.png&w=1920&q=75)

### Quick updates

**Amazon Corretto**

On April 18, 2023 Amazon announced quarterly security and critical updates for Amazon Corretto Long-Term Supported (LTS) versions of OpenJDK. Corretto 20.0.1, 17.0.7, 11.0.19, 8u372 are now available for download. Amazon Corretto is a no-cost, multi-platform, production-ready distribution of OpenJDK. With this release, we are declaring aarch64 Alpine Linux binaries of Corretto 17, 11, and 8 GA. 

**AWS Amplify**

AWS Amplify announced support for Push Notifications for Swift, Android, Flutter, and React Native applications. This means that developers can now use Amplify to set up push notifications when targeting iOS and Android platforms, providing developers and businesses with a way to engage with users and send them timely and relevant information. Developers can now set up campaigns to segment and target specific users. Personalising push notifications with AWS Amplify allows mobile and cross-platform developers to target specific users with important updates, promotions, and new features, resulting in higher engagement and increased user satisfaction.

Read the post, [AWS Amplify supports Push Notifications for Android, Swift, React Native, and Flutter apps](https://aws-oss.beachgeek.co.uk/2q6), that shows you how to add push notifications features to your Android applications with AWS Amplify, and then send targeted messages to your users.

**Flutter**

The AWS Amplify Flutter team unveiled the version 1.0.0 last week, which will help app development by adding support for both web and desktop platforms. You can now with a single codebase target 6 platforms, including iOS, Android, Web, Linux, MacOS, and Windows. Dive deeper into the post, [Amplify Flutter announces general availability for web and desktop support](https://aws-oss.beachgeek.co.uk/2qx).

![demo screenshot of amplify flutter 1.0](https://d2908q01vomqb2.cloudfront.net/0a57cb53ba59c46fc4b692527a38a87c78d84028/2023/04/14/ezgif.com-video-to-gif.gif)

**Apache Hive Metastore**

AWS Lake Formation and the Glue Data Catalog now extend data cataloging, data sharing and fine-grained access control support for customers using a self-managed Apache Hive Metastore (HMS) as their data catalog. Previously, customers had to replicate their metadata into the AWS Glue Data Catalog in order use Lake Formation permissions and data sharing capabilities. Now, customers can integrate their HMS metadata within AWS, allowing them to discover data alongside native tables in the Glue data catalog, manage permissions and sharing from Lake Formation, and query data using AWS analytics services.

To get started, customers using this feature will need to connect their HMS databases and tables as federation objects into their AWS Glue Data Catalog (check out [#153](https://dev.to/aws/aws-open-source-newsletter-152-2eo4), and the [aws-glue-data-catalog-federation](https://aws-oss.beachgeek.co.uk/2oq) project). Customers can then grant Lake Formation column, tag, and data filter permissions on tables as if they were native AWS Glue Data Catalog tables. These permissions are then applied whenever those tables are queried by Lake Formation supported AWS services, simplifying the management of unified data access controls. Finally, customers can audit access and permissions on their HMS resources using AWS CloudTrail logs generated on all data and metadata access events.

**Python**

AWS Lambda now supports Python 3.10 as both a managed runtime and a container base image. To deploy Lambda functions using Python 3.10, upload the code through the Lambda console and select the Python 3.10 runtime. You can also use the AWS CLI, AWS Serverless Application Model (AWS SAM) and AWS CloudFormation to deploy and manage serverless applications written in Python 3.10. Additionally, you can also use the AWS-provided Python 3.10 base image to build and deploy Python 3.10 functions using a container image. AWS will automatically apply updates to the Python 3.10 managed runtime and to the AWS-provided Python 3.10 base image, as they become available.

**Amazon EMR**

Amazon EMR on EC2 now provides contextual error details that makes it easier to troubleshoot cluster provisioning failures. EMR lets you provision your EMR on EC2 cluster without worrying about managing compute infrastructure or open-source application setup. However, there can be circumstances when your cluster provisioning fails, such as an insufficient EC2 instance capacity error, bootstrap action failure or a VPC-subnet misconfiguration error. With today’s launch, you will now find additional error details in the new EMR console, AWS Command Line Interface (AWS CLI), and the AWS SDK. These additional error details are automatically enabled for all EMR versions and no further action is needed.

Previously when users encountered a provisioning error, such as a bootstrap failure, they would receive an error message that the cluster failed but with no further context. Identifying whether the root cause was an invalid or conflicting bootstrap action or a misconfigured bootstrap source file location took multiple steps. With today’s launch, you will get specific error details for cluster provisioning failures along with detailed root cause, and recommendations to resolve the failure. You can find these details in the Cluster list view in the new console and via APIs.

**LoRaWAN**

AWS IoT Core for LoRaWAN announces public network support (preview) for LoRaWAN-based Internet of Things (IoT) systems. With this update, customers can now easily connect their IoT devices to the cloud using publicly available LoRaWAN networks provided by Everynet, a global LoRaWAN network operator offering carrier grade networks. Using AWS IoT Core for LoRaWAN, customers can simply register their devices to the cloud and opt for public network support in the AWS IoT console. Within minutes, they will be able to receive data from registered LoRaWAN devices in their AWS account. 

AWS IoT Core for LoRaWAN is a fully managed LoRaWAN Network Server (LNS) that enables customers to connect their LoRaWAN-enabled wireless devices, typically used for low-power, long-range wide area network connectivity, to AWS. IoT system operators now do not need to deploy and maintain their own private LoRaWAN network, resulting in development, management, and operational cost savings. It also streamlines billing processes as system operators do not need to interface with individual network provider for managing network subscription costs.

**gMSA**

Amazon Elastic Container Service (ECS) is announcing availability of ECS-optimised Amazon Linux 2023 (AL2023) AMIs and group managed service accounts (gMSA) on ECS Linux containers through credentials-fetcher integration. gMSA is a managed account that provides automatic password management, service principal name (SPN) management, and the ability to delegate management to administrators over multiple servers or instances. This integration allows applications hosted on Amazon ECS Linux containers to easily authenticate with Microsoft Active Directory (AD) to access network shared resources. This integration enables customers to continue using AD as well as get the cost, reliability, and scalability benefits of Amazon Linux on ECS. 

As you deploy your .NET applications, the applications hosted on Linux containers need to connect to network resources such as SQL Server hosts or storage blocks that are authenticated over Microsoft AD. The gMSA credentials-fetcher is now directly integrated into Amazon ECS. You can use credentials-fetcher to access AD from services hosted on Linux containers using the service account authentication model. Developers and system administrators can use the ECS agent for a managed configuration experience on the ECS platform.

To dive deeper into this, check out the excellent post [Using Windows Authentication with gMSA on Linux Containers on Amazon ECS](https://aws-oss.beachgeek.co.uk/2pt), where Cristobal Espinosa, Matt Cline, Sai Kiran Akula, and Samiullah Mohammed provide a nice detailed  walk through on how to integrate Credentials Fetcher with Amazon ECS.

![architecture overview of gMSA and ECS integration](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2023/03/24/sample-solution.png)

### Videos of the week

**AWS Container Day**

As KubeCon has just finished, what better way to celebrate than to share the recording of the AWS Container Day sessions. This is an epic seven hour video packed with lots of different sessions and speakers covering all things Kubernetes on AWS. You can check out the full agenda at [Save the date: Container Day + KubeCon](https://aws-oss.beachgeek.co.uk/zd),  


{{< youtube LGD52z0LxAA >}}


**OpenSearch**

If you missed the last OpenSearch community meeting, then you can watch the recording here where David Tippet takes the chair and goes over some updates you need to know about and then looks at a demo of the recently launched Security Analytics functionality and look at out of the box dashboards.

{{< youtube JgpuBHViJuU >}}


**AWS Copilot**

Check out this session from Efe Karakus and Maish Saidel-Keesing of the Containers from the Couch crew as they deep dive on the new features available in the 1.27 version of the AWS Copilot CLI

{{< youtube 54XAoS4vq2c >}}


**Build on Open Source**

For those unfamiliar with this show, Build on Open Source is where we go over this newsletter and then invite special guests to dive deep into their open source project. Expect plenty of code, demos and hopefully laughs. We have put together a playlist so that you can easily access all (eight) of the episodes of the Build on Open Source show. [Build on Open Source playlist](https://aws-oss.beachgeek.co.uk/episodes)

# Events for your diary

If you are planning any events in 2023, either virtual, in person, or hybrid, get in touch as I would love to share details of your event with readers. 

**FIPS Enabled Ubuntu Pro on AWS**
**Webinar, 26th April 5pm GMT**

Developing and running Linux workloads in regulated and high-security environments require a long and expensive validation process. As a result, U.S. government agencies and companies that are required to meet government standards and/or deploy to meet their RMF, ATO or FedRAMP or GOVCloud demands will typically need to make large investments, ensuring that they run on robust and secure infrastructure platforms.

Thanks to Ubuntu Pro and AWS you can have highly secure and FIPS enabled Open Source Linux instances running in no time. In this webinar, we will look at Ubuntu Pro with FIPS and additional security controls we provide at a higher level for agencies or missions to help you meet your security and compliance requirements. The session will also include a demo that shows how easy it is to start securing the Ubuntu Operating System within the AWS cloud.

Register to save your spot at[ [Webinar] FIPS Enabled Ubuntu Pro on AWS](https://aws-oss.beachgeek.co.uk/2pv)


**Reducing the costs of your openCypher applications**
**Online, May 8th, 4pm UK**

openCypher is an open-source project for creating graph applications. Neptune supports openCypher graph query language, and in this webinar you will learn more about the cost benefits for moving openCypher workloads to Neptune serverless. With Neptune serverless, customers can see up to 90% cost savings compared to provisioning for peak capacity. A demo of Neptune in action will be included in this session.

Head over to the You Tube holding page, [Reducing the costs of your openCypher applications](https://aws-oss.beachgeek.co.uk/2mp) 

**Intelligent Document Processing with AWS and Open Source with Hugging Face**
**AWS Office Zurich, May 23rd 8am - 2pm CET**

For readers who are based in Zurich, make sure you check out this event. The goal of this in-person event is to learn and share experience on how to get insights from documents, and simplify workflows using document processing and the power of open source. There is a great line up of speakers and an excellent agenda.

Find out more and reserve your space by heading over to, [Intelligent Document Processing with AWS and Open Source with Hugging Face](https://aws-oss.beachgeek.co.uk/2qj)

**Open source Table Formats with AWS Glue and Amazon EMR**
**Online, 6th June 5PM UK time**

Curious about Transactional Data Lakes? Come join our AWS experts as we take you through the most popular open source table formats, how these table formats can help you enable a modern data strategy, and how to build on these formats with Amazon EMR and AWS Glue. In this session, we'll cover some of the key differences between these different table formats, help you decide which table format may be the best fit for your workloads, and show you how to start building today.

You can [join via YouTube live here](https://aws-oss.beachgeek.co.uk/2pu)

**Cortex**
**Every other Thursday, next one 16th February**

The Cortex community call happens every two weeks on Thursday, alternating at 1200 UTC and 1700 UTC. You can check out the GitHub project for more details, go to the [Community Meetings](https://aws-oss.beachgeek.co.uk/2h5) section. The community calls keep a rolling doc of previous meetings, so you can catch up on the previous discussions. Check the [Cortex Community Meetings Notes](https://aws-oss.beachgeek.co.uk/2h6) for more info.

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)

### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)
