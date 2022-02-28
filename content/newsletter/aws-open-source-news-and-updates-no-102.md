---

title: 'AWS open source news and updates #102'
date: '2022-02-28'
tags : [ oss-newsletter, aws open source, Rhizomer, Kubernetes, OWL, Amazon Neptune, AWS SAM, AWS Orbit Workbench, SPARQL, Spinner, Apache Airflow, Leapp, Nano, AWS Graviton2, Amazon EMR, Ploomber, ROS, Ambit ]

---

## Feb 28th, 2022 - Instalment #102

Newsletter #102. 

Welcome to edition #102 of the AWS open source news and updates newsletter, and this week we have a super collection of new open source projects that I am really excited to share. First up we have the AWS DataOps Development Kit, which uses AWS CDK under the covers, and is an open source development framework to help you build data workflows. Threatmapper is an open source cloud native security observability platform, which looks easy to use and has some good visualisations. Granted is something I think I will be using, and is a cli tool that helps you managed multiple AWS accounts and browsers. Cloudsaga is a new open source tool that helps customers to test security controls and alerts within their AWS accounts, and many more. Make sure you check the other projects out too.

We also have AWS and Community blog posts and articles covering topics including Rhizomer, Kubernetes, OWL,  AWS SAM, AWS Orbit Workbench, SPARQL, Spinner, Apache Airflow, Leapp, Nano, Ploomber, ROS, Ambit and more. I have updated the Events section with a couple of events happening later this week, so plenty of time to add those into your diary and finally, we have a couple of videos that I think you will find interesting.


### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Kris Schultz, Jeremy Wallace, Eduardo Blancas, Cal Mitchell, Sheetal Joshi, Yahav Biran, Vikesh Pandey, Ioan Catana, Michaël Hoarau, Igor Holovii, Adithya Pathipaka, Olalekan Elesin, Roberto García, Sakti Mishra, Michael Stein, Ahmed Khattab, Omer Ahmed Hussain, and Robert Djurasaj.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest open source projects

#### Community

**lambda-java17-layer**

[lambda-java17-layer](https://aws-oss.beachgeek.co.uk/1e4) this project is based on original work from Mark Sailes (lambda-java17-layer) but with some differences including support for Java 17 on architecture amd64 and arm64, based on AWS Corretto 17 build of OpenJDK, and a few more. Check out the project README.md for details.

#### Tools

**AWS DataOps Development Kit**

[aws-ddk](https://aws-oss.beachgeek.co.uk/1ea) this is a brand new open source development framework to help you build data workflows and modern data architecture on AWS. Based on the AWS CDK, it offers high-level abstractions allowing you to build pipelines that manage data flows on AWS, driven by DevOps best practices. The framework is extensible, you can add abstractions for your own data processing infrastructure or replace our best practices with your own standards. It's easy to share templates, so everyone in your organisation can concentrate on the business logic of dealing with their data, rather than boilerplate logic.

**ThreatMapper**

[ThreatMapper](https://aws-oss.beachgeek.co.uk/1e5) is an open source cloud native security observability platform. Linux, K8s, AWS Fargate and more. Deepfence ThreatMapper hunts for vulnerabilities in your production platforms, and ranks these vulnerabilities based on their risk-of-exploit. You can then prioritize the issues that present the greatest risk to the security of your applications. Check the repo for some great demos and a nice getting started guide.

![demo](https://raw.githubusercontent.com/deepfence/ThreatMapper/master/images/readme/threatmapper-topology-full.jpg)

**granted**

[granted](https://aws-oss.beachgeek.co.uk/1e9) how many times have you wanted to have multiple browser tabs open with different AWS accounts? I know I have, and there is only so many times you can use Private browser tabs and become quickly annoyed about re-entering credentials. I was therefore very interested in this project that has a potential solution. Granted is a command line interface (CLI) application which simplifies access to cloud roles and allows multiple cloud accounts to be opened in your web browser simultaneously. Check it out, I like it a lot.

![demo](https://github.com/common-fate/granted/raw/main/docs/demo.gif)

**aws-cloudsaga**

[aws-cloudsaga](https://aws-oss.beachgeek.co.uk/1e3) this new open source tool from AWS helps customers to test security controls and alerts within their Amazon Web Services (AWS) environment, using generated alerts based on security events seen by the AWS Customer Incident Response Team (CIRT). Check out the README.md for detailed examples of how you can use this.

**opensearch-oci-object-storage**

[opensearch-oci-object-storage](https://aws-oss.beachgeek.co.uk/1e6) this new plugin for OpenSearch allows the user to take snapshots into OCI Object storage from the OpenSearch cluster. The README shares some important features that make this plugin very friendly for production, so check this out.

**cdk-karpenter**

[cdk-karpenter](https://aws-oss.beachgeek.co.uk/1eb) Robert Djurasaj shared this with me last week, an AWS CDK Construct for installing Karpenter on top of an EKS cluster. Karpenter is an AWS open source project that simplifies Kubernetes infrastructure with the right nodes at the right time. It automatically launches just the right compute resources to handle your cluster's applications. It is designed to let you take full advantage of the cloud with fast and simple compute provisioning for Kubernetes clusters.

**sqlpipe**

[sqlpipe](https://aws-oss.beachgeek.co.uk/1ed) this open source project from Cal Mitchell makes it easy to move the result of one query from one database to another. Cal has helpfully put together a blog post, [How To Transfer Data From PostgreSQL To Redshift](https://aws-oss.beachgeek.co.uk/1ee) that shows you how you can use it to transfer data from PostgreSQL into Amazon Redshift. Nice.

**amazon-lookout-for-equipment-python-sdk**

[amazon-lookout-for-equipment-python-sdk](https://aws-oss.beachgeek.co.uk/1dp) this repo contains the Python SDK is an open-source library that allows you to easily build, train and deploy anomaly detection models for industrial time series data using Amazon Lookout for Equipment. Find out how you can use this by checking out the blog post, [Build, train, and deploy Amazon Lookout for Equipment models using the Python Toolbox](https://aws-oss.beachgeek.co.uk/1dq), from Vikesh Pandey, Ioan CATANA, and Michaël Hoarau. [hands on]

![demo](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2022/01/21/ML-7134-image007.jpg)

#### Demos and Samples

**aws-iot-twinmaker-samples-snowflake**

[aws-iot-twinmaker-samples-snowflake](https://aws-oss.beachgeek.co.uk/1eg) With this Snowflake module, you can extract asset information from snowflake database and store it in S3 as JSON file. This json file can then be imported into IoT TwinMaker as entities. The module allows you to extract data using your SQL query, so you can define the hierarchy of the model via the SQL query.

![arch](https://github.com/aws-samples/aws-iot-twinmaker-samples-snowflake/blob/main/snowflake_workflow.jpg?raw=true)

**aws-lakeformation-datasharing-workflow**

[aws-lakeformation-datasharing-workflow](https://aws-oss.beachgeek.co.uk/1ei) this is a really nice sample application that demonstrates how to build an approval workflow to provide a consistent experience for data consumers to request access to specific data sets from data producers.

![arch](https://github.com/aws-samples/aws-lakeformation-datasharing-workflow/blob/main/doc-images/datamesh-workflow-detailed.png?raw=true)

**aws-batch-architecture-for-alphafold**

[aws-batch-architecture-for-alphafold](https://aws-oss.beachgeek.co.uk/1ek) this repository includes the CloudFormation template, Jupyter Notebook, and supporting code to run the Alphafold v2.0 algorithm on AWS Batch. Very detailed README which includes performance indicators, cost estimates and more.

![arch](https://github.com/aws-samples/aws-batch-architecture-for-alphafold/blob/main/imgs/aws-alphafold-arch.png?raw=true)

**s3uploader-ui**

[s3uploader-ui](https://aws-oss.beachgeek.co.uk/1ef) this sample project contains an AWS Amplify demo app that demonstrate how to build a simple WebApp to users upload files to S3.

**apprunner-cdk-example-with-custom-resource**

[apprunner-cdk-example-with-custom-resource](https://aws-oss.beachgeek.co.uk/1eh) this repo contains sample CDK code of App Runner with CustomResource that you can use to cover a gap in CFN where we don't have a resource to create AppRunner AutoScalingConfiguration (AutoScalingConfigurationArn).

### AWS and Community blog posts

**Ambit**

AWS Ambit Scenario Designer for Unreal Engine 4 (Ambit) is a suite of tools to streamline content creation at scale for autonomous vehicle and robotics simulation applications, and implemented as an open source plugin for for Unreal Engine 4 (UE4). Kris Schultz introduces this new content creation tool in his blog post, [Create 3D content for simulation using Ambit](https://aws-oss.beachgeek.co.uk/1en) and takes a tour of some of the key features and how to get started.

![demo](https://d2908q01vomqb2.cloudfront.net/c5b76da3e608d34edb07244cd9b875ee86906328/2022/02/11/3D-content.jpg)

**Nanos**

[Nanos](https://aws-oss.beachgeek.co.uk/1dz) is a new kernel designed to run one and only one application in a virtualised environment. In the post, Running Nanos on AWS Graviton, the fine folks at nonovms share how to get this up and running on AWS Graviton2 instances on AWS. [hands on]

**Spinner**

The engineering team at Pintrest have shared a must read post this week, [Spinner: Pinterest’s Workflow Platform](https://aws-oss.beachgeek.co.uk/1e0) which shares how they have evolved their approach to managing the large sums of data they use as a business, and how they settled on Apache Airflow core to their solution. 

![arch](https://miro.medium.com/max/1400/0*-wDdPjVOmsqNTY3y)

**Ploomber**

[Ploomber ](https://aws-oss.beachgeek.co.uk/13a)is an open source framework that helps you build data pipelines. Eduardo Blancas has put together a short blog post on how you can use it with AWS Batch.

**Rhizomer**

[Rhizomer](https://aws-oss.beachgeek.co.uk/1dy) is a web application for interactive exploration of semantic and linked data available from SPARQL endpoints. Roberto García, Associate Professor and Deputy Vice-rector for Research & Transfer at Universitat de Lleida in Spain has put together a blog post, [Explore the semantic knowledge graphs without SPARQL using Amazon Neptune with Rhizomer](https://aws-oss.beachgeek.co.uk/1dx) that illustrates how to use the Rhizomer web application to interact with knowledge graphs available as semantic data from an Amazon Neptune instance through its SPARQL endpoint.

![arch](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2022/02/08/DBBLOG-1282-image005.png)

**Kubernetes**

In [How to route UDP traffic into Kubernetes](https://aws-oss.beachgeek.co.uk/1dt) Sheetal Joshi and Yahav Biran share how you can use Kubernetes to scale a connectionless UDP-based application behind a network load balancer to meet low-latency needs. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2022/02/10/udp-nlb-sample.jpg)

We also had Michael Stein, Ahmed Khattab, and Omer Ahmed Hussain put together [Implement a central ingress Application Load Balancer supporting private Amazon Elastic Kubernetes Service VPCs](https://aws-oss.beachgeek.co.uk/1e8). This solution will help you configure central inbound connectivity, enabling internet-sourced traffic to be routed via an Application Load Balancer to an Amazon EKS cluster using an inter-VPC communication path provided by AWS PrivateLink. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/5b384ce32d8cdef02bc3a139d4cac0a22bb029e8/2022/01/24/Internet-Ingress-ALB-1-ALB.jpg)

**.NET**

AWS Lambda now supports .NET 6 as both a managed runtime and a container base image. Developers creating serverless applications in Lambda with .NET 6 can take advantage of new features such as improved logging, simplified function definitions using top-level statements, and improved performance using source generators. Norm Johanson put together this post, [Introducing the .NET 6 runtime for AWS Lambda](https://aws-oss.beachgeek.co.uk/1dw) which dives deeper into these new features and improvements, as well as how this works with the open source Lambda runtime client. [hands on]

**Other posts worth checking out**

* [Build, train, and deploy Amazon Fraud Detector models using the open source Python SDK](https://aws-oss.beachgeek.co.uk/1ej) shows you a step-by-step guide for using the Amazon Fraud Detector's open-source Python SDK for Python
* [Model-driven graphs using OWL in Amazon Neptune](https://aws-oss.beachgeek.co.uk/1dr) learn about OWL and how to use OWL ontology to derive a data model to validate and generate RDF data in Neptune

![arch](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2022/02/11/DBBLOG-1801-image002.png)

* [Using AWS DataSync to move data from Hadoop to Amazon S3](https://aws-oss.beachgeek.co.uk/1e7) walks you through the capabilities of HDFS support provided by AWS DataSync and how you can copy data from a Hadoop cluster to Amazon S3
* [Building TypeScript projects with AWS SAM CLI](https://aws-oss.beachgeek.co.uk/1ds) see how you can use the AWS SAM cli to build projects using TypeScript

### Book of the week

**Simplify Big Data Analytics with Amazon EMR: A beginner's guide to learning and implementing Amazon EMR for building data analytics solutions**

I heard about this new book written by Sakti Mishra that provides a practical guide to Amazon EMR for building data analytics solutions in AWS. It dives deep into Amazon EMR features, advanced configurations, scaling, security, monitoring, high availability, best practices and cost optimisation techniques. It also provides guidance for on-premise Hadoop cluster migration, and explains how you can implement batch ETL, real-time streaming and interactive workloads in EMR with workflow orchestration options to build an end to end pipeline.

Find out more by checking this online: [Simplify Big Data Analytics with Amazon EMR: A beginner's guide to learning and implementing Amazon EMR for building data analytics solutions](https://aws-oss.beachgeek.co.uk/1e1)

One for your Amazon Wish list maybe, I know I put it on mine.

### Quick updates

**Leapp**

[Leapp](https://aws-oss.beachgeek.co.uk/1e2) is an open-source local development tool that I have featured before in previous newsletters, and it helps you manage and gain access to cloud accounts and resources through credentials, roles, and federated access. It was good to see that a new release was published last week, 0.9.0 with some great new features and updates. Check the link, as they are looking for builders who are interested in spreading the word. If you are interested in writing a blog, or doing a demo at an event, get in touch with the team.

**AWS CDK**

[Triggers](https://aws-oss.beachgeek.co.uk/1ec) is a new capability within AWS CDK that allows you to execute code during deployments. This can be used for a variety of use cases such as:

* Self tests: validate something after a resource/construct been provisioned
* Data priming: add initial data to resources after they are created
* Preconditions: check things such as account limits or external dependencies before deployment.

**Python**

If you are using Python on AWS, then make sure you check out this post, [Python support policy updates for AWS SDKs and Tools](https://aws-oss.beachgeek.co.uk/1du) to find out key information on end of life dates and support options and recommendations.

**route53-cli**

A new update to this project from Isan-Rivkin, [release v0.3.2](https://aws-oss.beachgeek.co.uk/1dv) that now prints Route 53 Hosted zone Web URLs

### Videos of the week

**AWS Orbit Workbench**

AWS Orbit Workbench is an open source framework that provides a single, unified experience for your data, analytics and machine learning projects. You can collaborate with your team in a secure environment, using a wide range of AWS and partner services to experiment, develop, test and deploy your workloads onto Kubernetes Clusters in production. Watch this video to see Igor Holovii, Adithya Pathipaka, Olalekan Elesin, walking you through this project, presented by Chris Fregly and Antje Barth. 

{{< youtube jSfeAXHLGYo >}}


**ROS**

In this video, Jeremy Wallace introduces a new way to use the cloud for managing and running ROS applications on production robot fleets using AWS IoT Greengrass 2.0, an open-source edge run-time for building, managing and deploying device software. When combined with the industry-grade tools, libraries, and capabilities of the Robot Operating System 2 (ROS2), developers can use this approach to bring new cloud-enhanced robot features to market, and reduce the time and effort required to build failure resilient over-the-air (OTA) deployment infrastructure.

{{< vimeo 649647971 >}}

### Events for your diary

If you have an event you want me to publish here, please contact me and I will include it in this listing. 

**Confluent + AWS Immersion Day - Digital Native**
**2nd March 2022 at 11:00 CET**

Learn how Confluent has rearchitected Apache Kafka for digital native companies to unlock new value. This event is LIVE and includes an interactive workshop session. To find out more about what you will be covering, check out the [sign up and registration page here](https://aws-oss.beachgeek.co.uk/1em).

**Unifying data pipelines and ML with Delta Lake and Amazon SageMaker**
**March 8th, 9:00 AM PT**

Join this live workshop event to learn about the best practices for enterprises to use with powerful open source technologies to simplify and scale your data and ML efforts. We’ll discuss how to leverage Apache Spark™ — the de facto data processing and analytics engine for data preparation that unifies data at a massive scale across various sources — and Delta Lake so you can make your data lake ML-ready.

Find out more and [register here](https://aws-oss.beachgeek.co.uk/1el).
 
**OpenSearch**
**Every Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting - Feb2022](https://aws-oss.beachgeek.co.uk/1az)

**GitOpsCon Europe**
**May 17th, Valencia Spain**

GitOpsCon Europe is designed to foster collaboration, discussion, and knowledge sharing on GitOps. This event is aimed at audiences that are new to GitOps as well as those currently using GitOps within their organisation. Get connected with others that are passionate about GitOps. Learn from practitioners about pitfalls to avoid, hurdles to jump, and how to adopt GitOps in your cloud native environment.

The event is vendor-neutral and is being organised by the CNCF GitOps Working Group. Topics include getting started with GitOps, scaling and managing GitOps, lessons learned from production deployments, technical sessions, and thought leadership.

Read more about this from the official page [here](https://events.linuxfoundation.org/gitopscon-europe/).


### CFP

**Apache Airflow**
**CFP closes March, 14th**

A heads up to folks who are interested in all things Apache Airflow. Apache Airflow Summit 2022 has been announced and the call for papers (cfp) is now open. The bar for sessions is always very high, so looking forward to this event already.

If you have an idea for a talk, why not submit one via the cfp process. Check out the event, [Apache Airflow Summit 2022](https://aws-oss.beachgeek.co.uk/19e)

If you maybe have wanted to do a session, then I am very happy to help with feedback or coaching to help you feel more comfortable in creating and/or delivering your session. If this something that has been on your mind, but you just needed a little support, PLEASE get in touch.

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)