---
title: 'AWS open source news and updates #93'
date: '2021-12-13'
tags : [ oss-newsletter ]
---
## December 13th, 2021 - Instalment #93

Newsletter #93. We took a week off last week to recover from re:Invent, so this week we have extensive coverage of the open source related news and announcements so be sure to check those out. This week we have some great new open source projects, from a project that will help you get started with data meshes, an alternative way to provide internet connectivity to those private subnets, a nice new CDK construct to quickly deploy single page applications and a cool IoT simulator solution which I know I am going to try out. On top of the re:Invent related posts, we have content covering Kubernetes, Karpenter, Flower, Grafana, Apache Spark, Greengrass v2 and more.

Finally, before diving into the newsletter, make sure you check out the post and info on the Log4J rce vulnerability.

**Log4j rce**

Last week was dominated by news of the [Apache Log4j rce vulnerability (CVE-2021-44228)](https://www.fastly.com/blog/digging-deeper-into-log4shell-0day-rce-exploit-found-in-log4j), with the project maintainers and teams who have deployed log4j working non stop to mitigate and remediate applications and systems. David Nalley wrote [Hotpatch for Apache Log4j](https://aws-oss.beachgeek.co.uk/16g) which provides guidance on what customers can do and introduces something the folks from the Amazon Coretto team spent some time building, a tool to hotpatch vulnerable log4j deployments. You can expect more announcements this week providing more updates, like this one from Kyle Davis - [Important: Update to OpenSearch 1.2.1](https://aws-oss.beachgeek.co.uk/16h) essential reading if you use OpenSearch.


**Job Alert**

A fabulous opportunity has come up to join the open source team at AWS. What are we looking for? We are looking for someone who will be responsible for defining, leading, and contributing to the open source and community engagement content strategy for the services and technology teams across AWS. You will combine your passion and enthusiasm for cloud technology and open source with your unmatched creativity to generate content and support for AWS among key open source communities, industry opinion makers, and technologists.

You will work closely with the product marketing leadership to translate the business priorities of the service teams into original content for a variety of audiences, including C-level, end users, developers, managers, and engineers.

Ideally, you are already a recognisable figure in the open source ecosystem, in demand to contribute to technical and business publications, with an exemplary presence on social media.

Here is the Job Spec, [Principal Evangelist, Open Source, Open Source Strategy & Marketing](https://aws-oss.beachgeek.co.uk/16e) where you can read more and see how to apply.

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Ryan Niksch, Sebastien Stormacq, Sean Tracey, Jeff Barr, Ajay Swamy, George Lenz, Omur Kirikci, Sascha Moellering, Virginia Chu, Manoj Shunmugam, Randy DeFauw, Channy Yun, Sama Bali, Jordan Gruber, Chris Fife, Alex Pulver, Marcia Villalba, Varadarajan Srinivasan, Jim Parker, Ramesh Jetty, Damon Cortesi, Mehul Y. Shah, and Abhishek Sinha.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest open source projects

**aws-data-mesh-utils**

[aws-data-mesh-utils](https://aws-oss.beachgeek.co.uk/16i) this new repo is the AWS Data Mesh Helper library provides automation around the most common tasks that customers need to perform to implement a data mesh architecture on AWS. A data mesh on AWS uses a central AWS Account (the mesh account) to store the metadata associated with Data Products created by data Producers. This allows other AWS Accounts to act as Consumers, and to request Subscriptions, which must be approved by Producers. Upon approval, the approved grants are provided to the Consumer and can be imported into their AWS Account.

![arch](https://github.com/aws-samples/aws-data-mesh-utils/blob/main/doc/architecture.png?raw=true)

**fck-nat**

[fck-nat](https://aws-oss.beachgeek.co.uk/16d) if you are looking for alternatives to running NAT Gateways, then this open source project from Andrew Guenther may be just what you are looking for. This project, fck-nat offers a ready-to-use ARM and x86 based AMIs built on Amazon Linux 2 which can support up to 5Gbps NAT traffic on a t4g.nano instance. This project does not currently support high availability, and Andrew suggests you do not use this for production workloads. Take a look and if this is something you will find useful, why not contribute back to this project.

**cloudquery-policies**

[cloudquery-policies](https://aws-oss.beachgeek.co.uk/16f) if you use CloudQuery (an open-source cloud asset inventory tool powered by SQL), then this repo contains their AWS security & compliance policy packs that include CIS v1.2.0 and PCI DSS v3.2.1

**cdk-spa-deploy**

[cdk-spa-deploy](https://aws-oss.beachgeek.co.uk/16c) with the CDK Construct Hub now GA, I came across this nice construct from Matt Coulter (yes, that Matt!) that makes deploying a single page website (Angular/React/Vue) to AWS S3 behind SSL/Cloudfront as easy as 5 lines of code. Plenty of examples, this one is on my todo list.

**aws-compute-decision-tree**

[aws-compute-decision-tree](https://aws-oss.beachgeek.co.uk/16b) and interesting project from Servian that provides you with a decision tree to help you decide on the right AWS compute service for your needs. You can configure/change this to suit your own needs, so check it out and see if you might find this helpful within your organisation. There is an online version you can try out so you do not need to deploy anything.

**iot-device-simulator**

[iot-device-simulator](https://aws-oss.beachgeek.co.uk/15u) this repository is the IoT Device Simulator, an open source solution that provides  a Graphical User Interface (GUI) based engine designed to enable customers to get started quickly assessing AWS IoT services without an existing pool of devices. The IoT Device Simulator helps effortlessly create and simulate thousands of connected devices that are defined by the customer. To help you get started, make sure you read [Optimize your IoT Services for Scale with IoT Device Simulator](https://aws-oss.beachgeek.co.uk/15v) from Ajay Swamy and George Lenz. Excellent walkthrough.

![arch](https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2021/12/08/Fig6.png)

### re:Invent 

There were a number of open source related announcements from re:Invent last week. I have put this slide deck together that provides a nice summary of both the announcements in the run up to re:Invent as well as what was announced last week.

This includes Amazon FSx for OpenZFS, new capabilities and features in Amazon FSx for Lustre, Karpenter, Serverless Kafka and EMR, Amazon DevOps Guru for RDS, new AWS SDKs for Kotlin, Rust and Swift, and AWS CDK.

{% speakerdeck 521dc0274b31421eb739ef3333ba8184 %}

You can download the deck from [this link](https://aws-oss.beachgeek.co.uk/15l).

We also published a number of supporting blog posts. Here are the relevant ones you should check out.

* [Best practices for discoverability of a construct library on Construct Hub](https://aws-oss.beachgeek.co.uk/15z) from Alex Pulver
* [How customer feedback shaped the AWS Cloud Development Kit version 2](https://aws-oss.beachgeek.co.uk/15m) from Chris Fife
* [Increasing development speed with CDK Watch](https://aws-oss.beachgeek.co.uk/15n) from Calvin Combs
* [AWS BugBust sets the Guinness World Record for the largest bug fixing challenge](https://aws-oss.beachgeek.co.uk/15y) from Sama Bali and Jordan Gruber
* [New – FreeRTOS Extended Maintenance Plan for Up to 10 Years](https://aws-oss.beachgeek.co.uk/160) from Channy Yun
* [Built for Builders: AWS and Open 3D Engine – Stable 21.11 Release](https://aws-oss.beachgeek.co.uk/161) from the Amazon Game Tech team
* [New – Amazon DevOps Guru for RDS to Detect, Diagnose, and Resolve Amazon Aurora-Related Issues using ML ](https://aws-oss.beachgeek.co.uk/162)from Marcia Villalba
* [Enhanced Amazon S3 Integration for Amazon FSx for Lustre](https://aws-oss.beachgeek.co.uk/163) from Sebastien Stormacq
* [New – Amazon FSx for OpenZFS](https://aws-oss.beachgeek.co.uk/164) from Jeff Barr
* [Announcing Amazon EMR Serverless (Preview): Run big data applications without managing servers](https://aws-oss.beachgeek.co.uk/166) from Damon Cortesi, Mehul Y. Shah, and Abhishek Sinha
* [Managing ROSA subscriptions at scale](https://aws-oss.beachgeek.co.uk/168) from Ryan Niksch
* [New – Securely manage your AWS IoT Greengrass edge devices using AWS Systems Manager](https://aws-oss.beachgeek.co.uk/169) from Sean Tracey

### AWS and Community blog posts

**Karpenter**

Karpenter is an open source project that helps improve your application availability and cluster efficiency by rapidly launching right-sized compute resources in response to changing application load. Channy Yun has put together this post, [Introducing Karpenter – An Open-Source High-Performance Kubernetes Cluster Autoscaler](https://aws-oss.beachgeek.co.uk/167) to show you how to get started. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/da4b9237bacccdf19c0760cab7aec4a8359010b0/2021/11/23/2021-karpenter-diagram.png)

**Grafana**

Amazon CloudWatch recently launched Metrics Insights (Preview) an SQL-based query engine that enables you to identify trends and patterns across millions of operational metrics in real-time. Omur Kirikci shows you how you can use Metrics Insights’ SQL based query engine on OpenSource Grafana to analyse and group your metrics at scale in real time, and quickly identify the operational issues to reduce mean-time to resolution in the post [Identify operational issues quickly by using Grafana and Amazon CloudWatch Metrics Insights (Preview)](https://aws-oss.beachgeek.co.uk/15o) [hands on]

**Flower**

Flower ([flwr](https://aws-oss.beachgeek.co.uk/15p)) is a framework for building federated learning systems. In this post, [Applying Federated Learning for ML at the Edge](https://aws-oss.beachgeek.co.uk/15q), Randy DeFauw walks you through a working example of federated learning in an IoT scenario using the Flower framework. Great post.

![arch](https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2021/12/08/Fig3-fed-ml.png) 

**Apache Spark**

Varadarajan Srinivasan, Jim Parker, and Ramesh Jetty have collaborated on this post, [How Acxiom reduced their model inference time from days to hours with Spark on Amazon EMR](https://aws-oss.beachgeek.co.uk/16a) where they show you how Acxiom were able to drastically reduce the model inference duration from days to hours. Great read.

![arch](https://d2908q01vomqb2.cloudfront.net/c5b76da3e608d34edb07244cd9b875ee86906328/2021/11/22/Figure-2-Acxiom%E2%80%99s-Amazon-EMR-architecture-for-model-inference-at-scale.png)

**Kubernetes and AWS Greengrass v2**

In this post, [Collecting data from edge devices using Kubernetes and AWS IoT Greengrass V2](https://aws-oss.beachgeek.co.uk/15k) my good friend Sascha Moellering combines some of my favourite things as he describes how to set up an edge device like Raspberry Pi 4 to run k3s and deploy AWS IoT Greengrass V2 into Kubernetes. I shared this code repo in a previous newsletter (#90) so you can now use this blog to try this out for yourself.

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2021/12/08/IoTGreen-3.jpg)

**Kubernetes**

Find out how to use managed node groups to upgrade Amazon Elastic Kubernetes Service (Amazon EKS) cluster nodes in parallel from 1.19 to 1.20 in the post, [Automate Amazon EKS upgrades with infrastructure as code](![https://aws-oss.beachgeek.co.uk/15r](https://aws-oss.beachgeek.co.uk/15r)) from  Virginia Chu and Manoj Shunmugam.

![flow](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/11/12/virchu_automate_eks_upgrades_f1-603x1024.png)

**Other posts worth checking out**

* [AWS Deep Learning AMIs: New framework-specific DLAMIs for production complement the original multi-framework DLAMIs](https://aws-oss.beachgeek.co.uk/15s) - check out AWS AMIs and the various ML frameworks available.
* [Secure end-to-end traffic on Amazon EKS using TLS certificate in ACM, ALB, and Istio](https://aws-oss.beachgeek.co.uk/15t) - how to implement end-to-end encryption using a TLS certificate in AWS Certificate Manager (ACM), Application Load Balancer (ALB), and Istio in an Amazon EKS environment.
* [Field Notes: Building a Data Service for Autonomous Driving Systems Development using Amazon EKS ](https://aws-oss.beachgeek.co.uk/165)- shows you how to build a data service that can dynamically compose near real-time chunked data streams at scale using Kubernetes, Apache Kafka, Redshift, and FSx for Lustre
* [How to use Application Load Balancer and Amazon Cognito to authenticate users for your Kubernetes web apps](https://aws-oss.beachgeek.co.uk/15w) - a walkthrough on how to use Amazon Cognito to authenticate users for web apps running in an Amazon Elastic Kubernetes Services (Amazon EKS) cluster.
* [Introducing Custom Domain Names for AWS AppSync APIs](https://aws-oss.beachgeek.co.uk/15x) - shows how you can now configure a single memorable domain name that works for both the GraphQL endpoint and real-time endpoint of an AppSync API.

### Quick updates

Make sure you check out all the new updates from re:Invent. In addition, we had these new releases and updates last week.

**Kubernetes**

The Amazon Elastic Block Store (EBS) Container Storage Interface (CSI) driver is now available in Amazon Elastic Kubernetes Service (Amazon EKS) add-ons in preview, enabling you to use the Amazon EKS console, CLI, and API to install and manage the add-on. This release is in addition to existing support for the Amazon VPC CNI networking plugin, CoreDNS and kube-proxy, and makes it easier to define consistent Kubernetes clusters and keep them up to date using Amazon EKS. The EBS CSI driver provides a CSI interface used by container orchestrators to manage the lifecycle of Amazon EBS volumes. Availability in EKS add-ons in preview enables a simple experience for attaching persistent storage to an EKS cluster. The EBS CSI driver can now be installed, managed, and updated directly through the EKS console, CLI, and API. You can see available add-ons and compatible versions in the EKS API, select the version of the add-on you want to run on your cluster, and configure key settings such as the IAM role used by the add-on when it runs. Using EKS add-ons you can go from cluster creation to running applications in a single command and easily keep tooling in your cluster up to date.

**AWS Toolkit for VS Code**

The AWS Toolkit for VS Code now provides developers with convenient IDE functionality to connect to Amazon ECS containers and issue commands using Amazon ECS Exec. This allows VS Code users to directly interact with containers, such as running commands in or get a shell to an ECS container running on an Amazon EC2 instance or on AWS Fargate, without leaving their IDE. ECS Exec uses the AWS Systems Manager (SSM) Session Manager under the hood to establish a connection with the running container.

**MariaDB**

Amazon Relational Database Service (Amazon RDS) for MariaDB now supports MariaDB minor versions 10.5.13, 10.4.22, 10.3.32, and 10.2.41. We recommend that you upgrade to the latest minor versions to fix known security vulnerabilities in prior versions of MariaDB, and to benefit from the numerous bug fixes, performance improvements, and new functionality added by the MariaDB community.

### Video of the week

Check out the open source sessions from re:Invent. They are [now available on-demand](https://virtual.reinvent.awsevents.com/), and you can view the deck above for info on the specific sessions.

### Events for your diary

No new events - watch this space for events in 2022. If you have an event you want me to publish here, please contact me and I will include it in this listing.

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)


