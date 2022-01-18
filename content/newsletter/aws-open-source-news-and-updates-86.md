---
title: 'AWS open source news and updates #86'
date: '2021-10-18'
tags : [ oss-newsletter , AWS Open Source]
---
## October 18th, 2021 - Instalment #86

*updated Jan 18th, to remove dead links*

Newsletter #86.

This week we have a very broad variety of topics. Starting off with some fresh open source projects such as cfn-diagram, aws-jwt-verify, damo, aws-dotnet-deploy, automated-account-configuration, BayerCLAW and more. For mains, we have new AWS and community authored posts on MySQL, OpenSearch, .NET, miniwdl, OpenMRS, Apache Hudi, Apache Spark, ROS, cdk8s, Jax, Deep Graph Library and more. Finally, for pudding we have this weeks video that provides an insight into contributing to Apache Airflow and we have some new events added so check those out and add them to your diary. 

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Ian Avilez, Tim Pavlick, Jarek Potiuk, Ash Berlin-Taylor, Norm Johanson, Trivikram Kamat, Madhavan Sriram, Diego Menin, Gabriele Cacciola, Kunal Gautam, Mike Lin, Lee Pang, Krishna Singh, Razvan Ionasec, Archis Joglekar, Sean Morgan, Eddie Zaneski, Rohin Bhargava, Gopala Krishna, Saikumar Karanam, François Bouteruche and Nik Krichko.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest open source projects

**cfn-diagram**

[cfn-diagram](https://aws-oss.beachgeek.co.uk/4r) whilst I did cover this project back in Feb, I was [notified](https://aws-oss.beachgeek.co.uk/10b) by Lars from Mathem that there was now a new capability, ascii graphics.

**aws-jwt-verify**

[aws-jwt-verify](https://aws-oss.beachgeek.co.uk/10c) this project provides a NodeJS library for verifying JWTs signed by Amazon Cognito, and any OIDC-compatible IDP that signs JWTs with RS256 (currently, only signature algorithm RS256 is supported)

**aws-appconfig-codepipeline-cdk**

[aws-appconfig-codepipeline-cdk](https://aws-oss.beachgeek.co.uk/10d) this project provides a sample application demos setup of AWS AppConfig using AWS CDK. AWS AppConfig application is set up to use AWS CodePipeline as configuration store. It also sets up AWS Lambda validator to validate the configuration.

![arch](https://github.com/aws-samples/aws-appconfig-codepipeline-cdk/blob/main/infrastructure/src/main/resources/asset/arch.png?raw=true)

**aws-cloud-map-mcs-controller-for-k8s**

[aws-cloud-map-mcs-controller-for-k8s](https://aws-oss.beachgeek.co.uk/10e) this project that snuck out late last week, AWS Cloud Map multi-cluster service discovery for Kubernetes (K8s) is a controller that implements existing multi-cluster services API that allows services to communicate across multiple clusters. The implementation relies on AWS Cloud Map for enabling cross-cluster service discovery.

**BayerCLAW**

[BayerCLAW](https://aws-oss.beachgeek.co.uk/10f) this project from the Bayer Group is a workflow orchestration system for AWS, targeted at bioinformatics pipelines. A workflow consists of a sequence of computational steps, each of which is captured in a Docker container. Some steps may parallelise work across many executions of the same container (scatter/gather pattern).

**damo**

[damo](https://aws-oss.beachgeek.co.uk/10g) this is a cool project, damo is a user space tool for [DAMON](https://aws-oss.beachgeek.co.uk/10h). Using this, you can monitor the data access patterns of your system or workloads and make data access-aware memory management optimisations.

![demo](https://github.com/awslabs/damo/blob/next/images/damo_monitor_water_nsquared.gif?raw=true)

**aws-dotnet-deploy**

[aws-dotnet-deploy](https://aws-oss.beachgeek.co.uk/b7) this repository contains the AWS .NET deployment tool for .NET CLI - the opinionated tooling that simplifies deployment of .NET applications with minimum AWS knowledge. The tool suggests the right AWS compute service to deploy your application to. It then builds and packages your application as required by the chosen compute service, generates the deployment infrastructure, deploys your application by using the Cloud Development Kit (CDK), and displays the endpoint. Norm Johanson has put together a couple of blog posts. First we have [Update on our new AWS .NET Deployment Experience](https://aws-oss.beachgeek.co.uk/102) which provides you with an update of the recent updates to this project. Following that we have [Deployment Projects with the new AWS .NET Deployment Experience](https://aws-oss.beachgeek.co.uk/zz) that walks you through a new feature of this project, deployment projects[hands on]

**automated-account-configuration**

[automated-account-configuration](https://aws-oss.beachgeek.co.uk/zy) this project is the Automated Account Configuration, a sample solution to enable operational scale for AWS customers by automating repeatable steps required before AWS accounts are used for customer workloads. Steps include setting up backups and patching for the resources within the account.

![arch](https://d1.awsstatic.com/Solutions/Solutions%20Category%20Template%20Draft/Solution%20Architecture%20Diagrams/automated-account-config-architecture.34216591b80a575a38cd215fe59608925054d50f.png)

### AWS and Community blog posts

**MySQL**

Nik Krichko has put together this post, [Comparing Graviton (ARM) Performance to Intel and AMD for MySQL](https://aws-oss.beachgeek.co.uk/10i) that takes a closer look at running MySQL against different instance types on AWS to see what the different performance characteristics are. If you are running MySQL workloads you should check this out - no spoilers, but very interesting indeed.

**headless-recorder**

Amazon CloudWatch Synthetics to create canaries, configurable scripts that run on a schedule, to monitor your endpoints and APIs. Canaries offer programmatic access to a headless Google Chrome Browser via Puppeteer or Selenium Webdriver. Amazon provides a CloudWatch Synthetics Recorder to help you create canaries more easily. The recorder is a Google Chrome extension and based on the open source project,  [Headless recorder](https://aws-oss.beachgeek.co.uk/10a). In this post, [Visual monitoring of applications with Amazon CloudWatch Synthetics](https://aws-oss.beachgeek.co.uk/109) Mahanth Jayadeva and Yesh Ravindra walk through how the visual monitoring blueprint for Amazon CloudWatch Synthetics can be utilised to monitor your applications for visual defects. [hands on]

![demo](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2021/10/04/9-1.png)

**.NET**

My colleague François Bouteruche is back with another instalment of the story of My Local Farmer, a fictional company inspired by customer interactions with AWS Solutions Architects. This episode, [Migrating our trusty ol’ .NET Framework applications to AWS, I couldn’t believe it!](https://aws-oss.beachgeek.co.uk/108) takes a look at a number of open source projects you can use to help move your .NET workloads over to AWS. Tres bien!

**cdk8s**

Perfect timing with Kubecon last week, was Eddie Zaneski in his post, [Announcing the general availability of cdk8s and support for Go](https://aws-oss.beachgeek.co.uk/106). For those who may not be familiar with cdk8s, this is a CNCF Sandbox project, an open-source software development framework for defining Kubernetes applications using general-purpose programming languages. The output of a CDK8s program is Kubernetes YAML that you can apply directly to any cluster.

**OpenSearch**

Rohin Bhargava, Gopala Krishna, and Saikumar Karanam provide a brief overview of the cross-cluster replication feature within OpenSearch, and the thought process behind the design and implementation. Read on in [Introduction to Cross-Cluster Replication](https://aws-oss.beachgeek.co.uk/107)

**Jax**

JAX is NumPy on the CPU, GPU, and TPU, with great automatic differentiation for high-performance machine learning research. In this post, [Train and deploy deep learning models using JAX with Amazon SageMaker](https://aws-oss.beachgeek.co.uk/105) Archis Joglekar and Sean Morgan show how you can utilise the Bring Your Own Container (BYOC) paradigm to train ML models on GPUs using the increasingly popular JAX library from Google. As a bonus, the post shows how to serialise trained models into the TensorFlow SavedModel format so that we can use the existing TensorFlow Serving infrastructure provided by SageMaker. [hands on]

**Deep Graph Library**

Ian Avilez and Tim Pavlick from HawkEye 360 provide some insights in how they are using the open source Deep Graph Library and Amazon Neptune to find risks for nearby ships in the post [HawkEye 360 predicts vessel risk using the Deep Graph Library and Amazon Neptune](https://aws-oss.beachgeek.co.uk/10j). The graph networks in Neptune and GNN models enable HawkEye 360 to reveal hidden relationships among vessels that would otherwise be lost in the vast sea of complexity. Read on to find out more.

![demo](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2021/09/07/image001-1.png)

**OpenMRS**

OpenMRS is a collaborative open-source project to develop software to support the delivery of health care. In the post [Deploying OpenMRS Electronic Health Record (EHR) system on AWS](https://aws-oss.beachgeek.co.uk/104), Krishna Singh and Razvan Ionasec explore how to deploy a OpenMRS EHR system on AWS so you can support hundreds of concurrent HCP users and tens of thousands of patients. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/10/05/kbs_openmrs-aws_f1.png)

**miniwdl**

The Workflow Description Language (WDL) is a way to specify data processing workflows with a human-readable and -writeable syntax. WDL makes it straightforward to define analysis tasks, chain them together in workflows, and parallelise their execution. miniwdl is a local runner and developer toolkit for the bioinformatics-focused Workflow Description Language (WDL). In the blog post, [Using miniwdl, GWFCore, and SageMaker Studio as a cloud IDE for genomics workflows](https://aws-oss.beachgeek.co.uk/103) written by Mike Lin and Lee Pang, will show you how you can combine these open source tools together with AWS to build workflows and manage ad hoc analysis runs.

![arch](https://d2908q01vomqb2.cloudfront.net/c5b76da3e608d34edb07244cd9b875ee86906328/2021/10/11/VPC-in-Cloud.png)

**Apache Hudi**

Apache Hudi is an open-source data management framework used to simplify incremental data processing and data pipeline development. In this case study from Amazon's Transportation service, they share how they enabled near-real-time event analytics at petabyte scale using Apache Hudi tables created by AWS Glue Spark jobs. For data analytics afficiondos, read on in [How Amazon Transportation Service enabled near-real-time event analytics at petabyte scale using AWS Glue with Apache Hudi](https://aws-oss.beachgeek.co.uk/101) [warning, may contain gratuitous use of graphs!]

![arch](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2021/10/01/BDB1611-image001.png)

**AWS SDKs**

Trivikram Kamat shares how they were able to reduce the publish size of v3 SDK for Javascript modular packages by ~50% in the post, [How we halved the publish size of modular AWS SDK for JavaScript clients](https://aws-oss.beachgeek.co.uk/100). A must read this week.

![demo](https://d2908q01vomqb2.cloudfront.net/0716d9708d321ffb6a00818614779e779925365c/2021/10/14/aws_sdk_client_sts_install_size_reduction_packagephobia-1024x787.png)

### Open Data

Whilst not open source, open data sets help democratise access to data by making it available to the public for analysis on AWS; develop new cloud-native techniques, formats, and tools that lower the cost of working with data; and encourage the development of communities that benefit from access to shared datasets. In the post, [Climate data, koala genomes, analysis ready radar data, and highly-queryable genomic data: The latest open data on AWS](https://aws-oss.beachgeek.co.uk/10k) Joe Flasher shares 26 new data sets released.

### Quick updates

**Apache Spark**

Amazon EMR 6.4 release version now supports Apache Spark 3.1.2 and provides runtime improvements with Amazon EMR Runtime for Apache Spark. Amazon EMR 6.4 provides Presto runtime improvements for PrestoDB 0.254, and runtime improvements for Apache Hive 3.1.2 when you use AWS Glue Data Catalog for your metastore.

Amazon EMR 6.4 supports Apache Hudi 0.8.0, Trino 359, PrestoDB 0.254, Apache HBase 2.4.4, Apache Phoenix 5.1.2, Apache Flink 1.13.1, Apache Livy 0.7.1, JupyterHub 1.4.1, Apache Zookeeper 3.5.7 and Apache MXNet 1.8.0. Please see our release guide to learn more.

**ActiveMQ**

You can now launch Apache ActiveMQ 5.16.3 brokers on Amazon MQ. This version update to ActiveMQ contains several fixes and improvements compared to the previously supported version, ActiveMQ 5.16.2.

**AWS CDK**

During September, 2021, 5 new versions of the AWS Cloud Development Kit  (CDK) for JavaScript, TypeScript, Java, Python, .NET and Go were released (v1.121.0 through v.125.0). With these releases, the CDK CLI now has support for hotswap deployments for faster inner-loop development iterations on the application code in your CDK project. Hotswap initially supports AWS Lambda handler code, but support is planned for additional resource types and a “watch” mode which continually watches for changes and deploys any updates. Additionally, users can preserve successfully provisioned resources by disabling automatic stack rollbacks, further reducing deployment and iteration time. These releases also resolve 21 issues and introduce 40 new features that span over 30 different modules across the library. Many of these changes were contributed by the developer community.

Read the full release notes for [1.121.0](https://aws-oss.beachgeek.co.uk/zt), [1.122.0](https://aws-oss.beachgeek.co.uk/zu), [1.123.0](https://aws-oss.beachgeek.co.uk/zv), [1.124.0](https://aws-oss.beachgeek.co.uk/zw), [1.125.0](https://aws-oss.beachgeek.co.uk/zx)

**ROS**

AWS RoboMaker, a service that allows customers to simulate robotics applications at cloud scale, now supports GPU based simulation jobs for compute-intensive simulation workloads such as high fidelity simulation, vision processing, and machine learning (ML). Previously, AWS RoboMaker simulation jobs ran only on central processing unit (CPU) instances; now you can choose between a CPU based or GPU based simulation job. Developers can run, scale, and automate GPU based simulations. GPU based simulations support higher frames-per-second, higher resolutions, lower sensor latencies, and faster simulation job completion times than CPU based simulation jobs. These capabilities enable improved sensing by cameras and realistic rendering needed for use cases such as ML model training, reinforcement learning, and testing use cases that require high fidelity simulations. When running a GPU based simulation job, the AWS RoboMaker GUI tool viewer now supports higher resolutions, enabling you to see simulated objects in greater detail.

Also new, AWS RoboMaker now supports expanded configuration for any robot and simulation software. Previously Robot Operating System (ROS) and Gazebo are the only supported robot and simulation software configuration in RoboMaker. This new feature enables customers to use and configure any robot and simulation software of their choice while running simulations in RoboMaker. To use this feature, you select General software suite for Robot application and Simulation runtime for Simulation Application. By choosing the Simulation Runtime configuration, RoboMaker bypasses validations for any specific robot or simulation software, and provides generic simulation features such as sourcing files to the simulation environment, logging, launching simulation tools, and streaming tool GUIs.

### Video of the week

Want to contribute to Apache Airflow? Find out more as to how this works by checking out this video, where Jarek Potiuk and Ash Berlin-Taylor, Apache Airflow maintainers walk you through why developer and contributor experience matters for Apache Community projects such as Apache Airflow and what they have done together with other members of the community to improve it.

{% youtube 7MOuUnCxmt8 %} 


### Events for your diary

**Enterprise Scale NLP with Hugging Face & SageMaker**
**October 26th 2021 - 5:00 PM (BST)**

In this workshop, [Getting Started with Amazon SageMaker: Training your first NLP Transformer model with Hugging Face](https://aws-oss.beachgeek.co.uk/10l) you will learn how to use Amazon SageMaker to train a Hugging Face Transformer model and deploy it afterwards. The workshop covers preparing and uploading  test dataset to S3, fine-tuning a script to be used with Amazon SageMaker Training jobs, launching a training job and storing the trained model into S3 and then deploying the model after successful training.

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