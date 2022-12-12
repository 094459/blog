---

title: 'AWS open source news and updates #138'
date: '2022-12-12'
tags : [ oss-newsletter, aws open source, Rez, Terraform, PostgreSQL, Apache Hudi, Apache Iceberg, Delta Lake, Amazon EMR, Apache Iceberg, Apache Spark, OpenZFS, Ray, MySQL, Kubernetes, Apache Kafka, Open Invention Network, AWS IoT Greengrass, Ray, Modin, Amazon Corretto, Firecracker, DeeQu, Open Cybersecurity Schema Framework, ocsf, AWS SDK for pandas, Amazon Braket, Yocto, Log4shell, MQTT, Redis, AWS CDK, AWS Amplify,]

---

## December 12th, 2022 - Instalment #138

**Welcome**

Welcome to the AWS open source newsletter, edition #138. After a week off due to re:Invent, this edition is packed with content on many of the open source related announcements. As always, we have a great line up of new projects for you to practice your four freedoms on. In no particular order, we have projects like "eks-node-viewer", a nice visualisation tool for your Amazon EKS clusters, "pg_tle" a great new project to make your PostgreSQL environments safer, "dyna53" a fun project that finally turns Amazon Route 53 into a database, "dynamodb-mass-migrations" a tool to help you migrate to Amazon DynamoDB, "visual-asset-management-system" a very nice digital asset management tool, "fast-differential-privacy" implement differential privacy in your PyTorch models, "migration-hadoop-to-emr-tco-simulator" a handy total cost of ownership calculator for Amazon EMR, "realtime-toxicity-detection" a tool to help you stay on top of your online communities, "functionclarity" a very cool tool to check the integrity of your serverless functions before executing, and many more.

We also feature this week content on a broad array of open source technologies, such as Rez, Terraform, PostgreSQL, Apache Hudi, Apache Iceberg, Delta Lake, Amazon EMR, Apache Iceberg, Apache Spark, OpenZFS, Ray, MySQL, Kubernetes, Apache Kafka, Open Invention Network, AWS IoT Greengrass, Ray, Modin, Amazon Corretto, Firecracker, DeeQu, AWS SDK for pandas, Amazon Braket, Yocto, Log4shell, MQTT, Redis, and many more. Finally, make sure you check out the Video section, where I share what i think are the best videos from re:Invent on open source.


**Amazon Joins the Open Invention Network**

[Open Invention Network (OIN)](https://aws-oss.beachgeek.co.uk/2bl) is a company that acquires patents and licenses them royalty-free to its community members who, in turn, agree not to assert their own patents against Linux and Linux-related systems and applications. Announced last week, David Nalley wrote about Amazon joining OIN, and what this means to us. Nithya Ruff also added:

>“By joining OIN, we are continuing to strengthen open source communities and helping to ensure technologies like Linux remain thriving and accessible to everyone.”


**Feedback**

Please let me know how we can improve this newsletter as well as how AWS can better work with open source projects and technologies by completing [this very short survey ](https://eventbox.dev/survey/NUSZ91Z)that will take you probably less than 30 seconds to complete. Thank you so much!

**Celebrating open source contributors**

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created. 

So thank you to the following open source heroes: Donnie Prakoso, Todd Neal, Tyler Lynch, Thomas Roos, Darko Mesaros, Curtis Evans, Ariel Shuper, Channy Yun, Jeff Barr, Álvaro Hernández, Heitor Lessa, Abbey Fuller, Noritaka Sekiyama, Gonzalo Herreros, Mohit Saxena, Abdel Jaidi, Anton Kukushkin, Lucas Hanson, Leon Luttenberger, Zach Mitchell, Ishan Gaur, Kinshuk Pahare, Derek Liu, Pathik Shah and Raj Devnath

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution.*

#### Tools

**pg_tle**

[pg_tle](https://aws-oss.beachgeek.co.uk/2cf) Trusted Language Extensions (TLE) for PostgreSQL (pg_tle) is an open source project that lets developers extend and deploy new PostgreSQL functionality with lower administrative and technical overhead. Developers can use Trusted Language Extensions for PostgreSQL to create and install extensions on restricted filesystems and work with PostgreSQL internals through a SQL API. You can learn more about Trusted Language Extensions in the AWS News blog post, [New – Trusted Language Extensions for PostgreSQL on Amazon Aurora and Amazon RDS](https://aws-oss.beachgeek.co.uk/2bh) where Channy Yun provides a hands on guide to getting started with this project.

**eks-node-viewer**

[eks-node-viewer](https://aws-oss.beachgeek.co.uk/2cq) is a tool developed by Todd Neal for visualising dynamic node usage within a cluster. It was originally developed as an internal tool at AWS for demonstrating consolidation with Karpenter. Check out [this short video](https://aws-oss.beachgeek.co.uk/2cr) from Justin Garrison that looks at this tool running. Hat tip to Tyler Lynch for sharing this with me.

![demo screenshot of eks-node-viewer](https://github.com/awslabs/eks-node-viewer/blob/main/.static/screenshot.png?raw=true)

**functionclarity**

[functionclarity](https://aws-oss.beachgeek.co.uk/2co) is a code integrity solution for serverless functions. It allows users to sign their serverless functions and verify their integrity prior to their execution in their cloud environments. FunctionClarity includes a CLI tool, complemented by a "verification" function deployed in the target cloud account. The solution is designed for CI/CD insertion, where the serverless function code/images can be signed and uploaded before the function is created in the cloud repository.

![architecture for functionclarity](https://user-images.githubusercontent.com/110329574/197707276-10cd650e-a84d-4a9f-a83a-ee60dc2cbf28.png)

Check out this blog post [A New Open-Source Tool that Fills a Critical Serverless Security Gap](https://aws-oss.beachgeek.co.uk/2cp), where Ariel Shuper looks at this in more detail including how you can get started.

**dyna53**

[dyna53](https://aws-oss.beachgeek.co.uk/2br) a fun project from AWS Hero, Álvaro Hernández, dyna53 is a database (with limited functionality). It is in reality a frontend to another database. The frontend is DynamoDB API compatible. That is, it implements (a limited subset of) the same API that DynamoDB exposes. Therefore it is (should be) compatible with DynamoDB clients and tools. The main goal is to support very basic operations (create table, put item, basic querying capabilities). The backend is AWS Route 53, a DNS service. This is where data is stored and queried from. As Alvaro notes in the README

> Using DNS "as a database" is not a novel idea, but the concept of running a database on top of Route 53 has not been explored deep enough. 
> 

What do you think? Get in touch with Alvaro if you try this out, and let him know what you think.

**dynamodb-mass-migrations**

[dynamodb-mass-migrations](https://aws-oss.beachgeek.co.uk/2cl) this repo provides a tool using AWS Step Functions Distributed Map to run massively parallel DynamoDB migrations in AWS CDK. Thanks to recent accouncement of Step Functions Distributed Map, we can now run 10,000 of parallel executions in Step Functions. This is especially useful for transforming/migrating big datasets in DynamoDB.

![architecture of dynamodb migration](https://github.com/Dynobase/dynamodb-mass-migrations/blob/main/stepfunctions_graph.png?raw=true)

**aws-kms-xksproxy-api-spec**

[aws-kms-xksproxy-api-spec](https://aws-oss.beachgeek.co.uk/2cg) if you missed the [announcement](https://aws-oss.beachgeek.co.uk/2ch) at re:Invent, AWS Key Management Service (AWS KMS) introduces the External Key Store (XKS), a new feature for customers who want to protect their data with encryption keys stored in an external key management system under their control. This capability brings new flexibility for customers to encrypt or decrypt data with cryptographic keys, independent authorisation, and audit in an external key management system outside of AWS. This repo contains the specification, an example XKS client and some test clients. There is also a link to the launch blog post to help get you started.

**visual-asset-management-system**

[visual-asset-management-system](https://aws-oss.beachgeek.co.uk/2bo) VAMS for short, is a purpose-built, AWS native solution for the management and distribution of specialised visual assets used in spatial computing. VAMS offers a simplified solution for organisations to ingest, store, and manage visual assets in the cloud, which empowers any user with a web browser to upload, manage, visualise, transform, and retrieve visual assets. Existing workflows that leverage both custom code and pre-built or third-party applications can also be migrated to VAMS and ran in the AWS cloud, as opposed to being limited by the on-premise capacity available. VAMS is customisable and expandable with option of being further tailored to specific use-cases by development teams.

![architecture of VAMS](https://d2908q01vomqb2.cloudfront.net/a17554a0d2b15a664c0e73900184544f19e70227/2022/12/01/VAMS-Architecture.jpg)

**aws-cloud9-auto-root-volume-resize**

[aws-cloud9-auto-root-volume-resize](https://aws-oss.beachgeek.co.uk/2ca) this is a project that I think a lot of folk (including myself, who comes up against this every time I provision a new environment) will find useful. Cloud9 provides a consistent environment for development teams that allows for ease of development by easily integrating with AWS. However, when launching a Cloud9 instance environment, no options are provided that will allow for adjusting the size of the root volume and the environment will launch using the default size of 10 GiB. This limited size can prove cumbersome if teams start development work in the Cloud9 instance environment without realising this storage space is limited without intervention. This solution allows for a near-seamless integration with the existing Cloud9 instance environment launch process but utilising an optional tag ("cloud9:root_volume_size") to indicate the desired root volume size in GiB.

**fast-differential-privacy**

[fast-differential-privacy](https://aws-oss.beachgeek.co.uk/2cc) is a library that allows differentially private optimisation of PyTorch models, with a few additional lines of code. It supports all PyTorch optimisers, popular models in TIMM, torchvision, HuggingFace (up to supported modules), multiple privacy accountants, and multiple clipping functions. The library has provably little overhead in terms of training time and memory cost, compared with the standard non-private optimisation.

**aws-organizations-alternate-contacts-management-via-csv**

[aws-organizations-alternate-contacts-management-via-csv](https://aws-oss.beachgeek.co.uk/2ce) Nowadays, customers have several linked accounts in their AWS Organizations. These linked accounts might require different alternate contacts for many reasons and keeping such contacts updated is fundamental. Unfortunately, populating such contacts might be a complex and time-consuming activity. Customers would like to fill in their AWS linked accounts alternate contacts in a simple and quick way, closer to their daily way of working, like exporting to a CSV file, modifying it keeping the original formatting, and importing the updated contacts from the management account. This is what the script does. The script leverages on AWS CLI 2.0 and AWS CloudShell to enable the AWS Organizations management account to easily export all the linked accounts alternate contacts to a regular CSV file. Then, the file can be integrated or updated, and uploaded again.

**migration-hadoop-to-emr-tco-simulator**

[migration-hadoop-to-emr-tco-simulator](https://aws-oss.beachgeek.co.uk/2cj) this repo provides you with help if you are looking to move off self managed Hadoop, and migrate onto a managed service like Amazon EMR. This tool may be useful when examining and estimating the cost of migration, so well worth checking out.

![dashboard for tco calculator](https://github.com/awslabs/migration-hadoop-to-emr-tco-simulator/blob/main/imgs/tco_simulation.png?raw=true)

**aws-medialive-channel-orchestrator**

[aws-medialive-channel-orchestrator](https://aws-oss.beachgeek.co.uk/2cm) this repository contains sample code to deploy a web app that can be used to simplify the management of AWS MediaLive Channels. Supported functionality includes starting/stopping channels, input switching, motion graphic overlays, and much more. If you use AWS MediaLive Channels, then this repo is something you should check out.

![architecture of aws-medialive-channel-orchestrator](https://github.com/aws-samples/aws-medialive-channel-orchestrator/blob/main/docs/architecture.jpg?raw=true)

**amazon-gamelift-testing-toolkit**

[amazon-gamelift-testing-toolkit](https://aws-oss.beachgeek.co.uk/2cn) this repo provides a test harness and visualisation tool for Amazon GameLift and Amazon GameLift FlexMatch. The toolkit lets you visualise your GameLift infrastructure, launch virtual players, and iterate upon your FlexMatch rule sets with the FlexMatch simulator. Detailed docs show you how to deploy and use this project.

![architecture of gamelift testing toolkit](https://aws-samples.github.io/amazon-gamelift-testing-toolkit/img/amazon_gamelift_testing_toolkit.png)

### Demos, Samples, Solutions and Workshops

**aws-music-genre-classification**

[aws-music-genre-classification](https://aws-oss.beachgeek.co.uk/2cd) is a Jupyter Notebook that connects to the Registry of Open Data on AWS to show music genre classification. You can run this locally or use AWS SageMaker Studio Lab (this does not require an AWS account)

**realtime-toxicity-detection**

[realtime-toxicity-detection](https://aws-oss.beachgeek.co.uk/2ci) this repository contains a complete solution for detecting toxicity across voice and text chats, cost efficiently and at scale, in near real time. It makes use of a number of AWS services, including Amazon SageMaker, Amazon Cognito, AWS Lambda, AWS Amplify, and Amazon Transcribe.

![architecture for toxicity solution](https://github.com/aws-samples/realtime-toxicity-detection/blob/main/images/high-level-architecture.png?raw=true)


**msk-powered-financial-data-feed**

[msk-powered-financial-data-feed](https://aws-oss.beachgeek.co.uk/2cb) this sample application demonstrates how to publish a real-time financial data feed as a service on AWS. It contains the code for a data provider to send streaming data to its clients via an Amazon MSK cluster. Clients can consume the data using a Kafka client SDK. Detailed instructions on how to get this setup are provided in the README, as well as plenty of examples in the EXAMPLES folder.

**aws-to-azure-bgp-vpn**

[aws-to-azure-bgp-vpn](https://aws-oss.beachgeek.co.uk/2bn) this Terraform module allows you to configure a BGP VPN Gateway between AWS and Microsoft Azure. Check the docs for requirements and constraints, but if you are looking to build networking across Clouds, this is going to be of interest.

**terraform-eksblueprints-tetrate-istio-addon**

[terraform-eksblueprints-tetrate-istio-addon](https://aws-oss.beachgeek.co.uk/2bj) provides sample code on how you can deploy Istio and Envoy into your Amazon EKS environments. To help you along the way, check out [Automate Istio-Enabled Amazon EKS Cluster Deployment with Tetrate’s EKS Blueprints Add-On](https://aws-oss.beachgeek.co.uk/2bk)

![example dashboard from using itsio tetrate](https://d2908q01vomqb2.cloudfront.net/77de68daecd823babbb58edb1c8e14d7106e83bb/2022/11/21/Tetrate-EKS-Blueprints-Add-On-3.png)


### AWS and Community blog posts

**Apache Spark**

Cloud Shuffle Storage Plugin for Apache Spark, is a new open source project under the Apache 2.0 license that allows you to independently scale storage in your Spark jobs without adding additional workers. With this plugin, you can expect jobs processing terabytes of data to run much more reliably. You can download the binaries and run them on any Spark environment. The new plugin is open-cloud, comes with out-of-the box support for Amazon S3, and can be easily configured to use other forms of cloud storage such as Google Cloud Storage and Microsoft Azure Blob Storage.

To find out more, check out this must read post, [Introducing the Cloud Shuffle Storage Plugin for Apache Spark](https://aws-oss.beachgeek.co.uk/2bt) where Noritaka Sekiyama, Gonzalo Herreros, and Mohit Saxena help get you started. [hands on]

![illustration of architecture for cloud shuffle](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2022/11/22/bdb2484-chopper_diagram.jpg)

**DeeQu**

A hot topic over the past 12 months that I have been hearing in various data communities is that around data quality. [Deequ](https://aws-oss.beachgeek.co.uk/2bu) is an open source library built on top of Apache Spark for defining "unit tests for data". Built on top of the open-source DeeQu framework, [AWS Glue Data Quality](https://aws-oss.beachgeek.co.uk/2bv) provides a managed, serverless experience to help you evaluate and monitor the quality of your data when you use AWS Glue 3.0. To find out more on how to get started, check out Jeff Barr's excellent post on the topic, [Join the Preview – AWS Glue Data Quality](https://aws-oss.beachgeek.co.uk/2bw) [hands on]

![example output of using tool](https://d2908q01vomqb2.cloudfront.net/da4b9237bacccdf19c0760cab7aec4a8359010b0/2022/11/22/dq_eval_out_1.png)

**AWS Lambda Snapstart**

One of the biggest announcements during re:Invent was that of AWS Lambda SnapStart, a new performance optimisation developed by AWS that can significantly improve the startup time for applications. This feature delivers up to 10x faster function startup times for latency-sensitive Java applications. SnapStart is made possible by several pieces of open-source work, including Firecracker, Linux, CraC, OpenSSL and more. It is always interesting to see how these open source building blocks are combined to create great innovations like this. Dive deeper by reading the post, [Starting up faster with AWS Lambda SnapStart](https://aws-oss.beachgeek.co.uk/2by) on what those open source projects are and how they combine to make this all work. [deep dive]

![overview of snapshot lifecycle](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2022/11/25/Screen-Shot-2022-11-25-at-10.48.12-AM.png) 

**Amazon Security Lake**

Launched earlier this year, the [Open Cybersecurity Schema Framework](https://aws-oss.beachgeek.co.uk/2c1) is an open-source project, delivering an extensible framework for developing schemas, along with a vendor-agnostic core security schema. Amazon Security Lake is a purpose-built service that supports data in this format, and automatically centralises an organisation’s security data from cloud and on-premises sources into a purpose-built data lake stored in your account. To find out more, check out [Preview: Amazon Security Lake – A Purpose-Built Customer-Owned Data Lake Service](https://aws-oss.beachgeek.co.uk/2c2) where Channy Yun looks closer at OCSF and Amazon Security Lake. [hands on]

![dashboard example of amazon security lake](https://d2908q01vomqb2.cloudfront.net/da4b9237bacccdf19c0760cab7aec4a8359010b0/2022/11/21/2022-security-lake-7.jpg)

**AWS SDK for pandas**

AWS SDK for pandas is an open-source library that extends the popular Python pandas library, enabling you to connect to AWS data and analytics services using pandas data frames. I love this project, and use it frequently in my demos. At re:Invent, it was announced that AWS SDK for pandas now supports Ray and Modin, enabling you to scale your pandas workflows from a single machine to a multi-node environment, with no code changes. Check out the blog post, [Scale AWS SDK for pandas workloads with AWS Glue for Ray](https://aws-oss.beachgeek.co.uk/2c4) where Abdel Jaidi, Anton Kukushkin, Lucas Hanson, and Leon Luttenberger walk you through this update [hands on]

![overview of how this works](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2022/11/25/BDB-2793-image003.png)

**Ray**

Ray is an open-source unified compute framework that makes it simple to scale AI and Python workloads. In this post, [Introducing AWS Glue for Ray: Scaling your data integration workloads using Python](https://aws-oss.beachgeek.co.uk/2c5) Zach Mitchell, Ishan Gaur, Kinshuk Pahare, and Derek Liu provide an introduction to AWS Glue for Ray and shows you how to start using Ray to distribute your Python workloads. [hands on]

![AWS Glue for Ray overview](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2022/11/25/BDB-2761-image003.jpg)

**Other posts and quick reads**

* [Managing Docker container lifecycle with AWS IoT Greengrass](https://aws-oss.beachgeek.co.uk/2bf) an interesting way on how to use AWS IoT Greengrass to control a Docker container’s lifecycle, using the AWS IoT Core MQTT topic and uses the message contents to execute commands against the Docker daemon with the Docker SDK for Python [hands on]

![overview of greeengrassv2 and docker](https://d2908q01vomqb2.cloudfront.net/f6e1126cedebf23e1463aee73f9df08783640400/2022/11/09/solution-diagram.png)

* [Gain visibility into your Amazon MSK cluster by deploying the Conduktor Platform](https://aws-oss.beachgeek.co.uk/2bg) looks at how you can use Conduktor to help you solve Apache Kafka issues end to end with solutions for testing, monitoring, data quality, governance, and security [hands on]
* [Managing Pod Security on Amazon EKS with Kyverno](https://aws-oss.beachgeek.co.uk/2c8) shows you how you can augment the Kubernetes Pod Security Admission (PSA) and  Pod Security Standards(PSS) configurations with Kyverno [hands on]
* [Managing access to Amazon Elastic Kubernetes Service clusters with X.509 certificates](https://aws-oss.beachgeek.co.uk/2bp) is walk through on how to use X.509 certificates as the root of trust for obtaining temporary AWS credentials to access resources in the Amazon EKS Cluster [hands on]

![architecture of x509 on eks](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2022/11/28/anuj-1.jpg)

* [AWS Thinkbox Deadline adds support for Rez](https://aws-oss.beachgeek.co.uk/2bq) looks at Rez, an open source, cross-platform package manager, and how the deep integration into AWS Thinkbox Deadline allows customers to build dynamically resolved pipelines that can be executed in an identical way on their render farm, whether that be on-premises or in the cloud

![example of what REZ does](https://d2908q01vomqb2.cloudfront.net/fb644351560d8296fe6da332236b1f8d61b2828a/2022/12/03/Image-1-1.png)

* [New for Amazon Redshift – General Availability of Streaming Ingestion for Kinesis Data Streams and Managed Streaming for Apache Kafka](https://aws-oss.beachgeek.co.uk/2bz) looks at how you can now natively ingest hundreds of megabytes of data per second from Apache Kafka (Amazon MSK) into an Amazon Redshift materialised view and query it in seconds [hands on]
* [Simplify managing access to Amazon ElastiCache for Redis clusters with IAM](https://aws-oss.beachgeek.co.uk/2c0) shows you how to use your IAM identity to authenticate and access an ElastiCache for Redis cluster [hands on]

![architecture overview of redis and iam](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2022/11/28/DBBLOG-2711_img1-1024x454.png)

* [Introducing the Amazon Braket Algorithm Library](https://aws-oss.beachgeek.co.uk/2c3) walks you through this  open-source, GitHub repository providing researchers ready-to-use Python implementations for a set of quantum algorithms on Amazon Braket

![example dashboard of algo library](https://d2908q01vomqb2.cloudfront.net/5a5b0f9b7d3f8fc84c3cef8fd8efaaa6c70d75ab/2022/11/28/Screen-Shot-2022-11-28-at-6.18.35-PM.png)

* [Introducing new MQTTv5 features for AWS IoT Core to help build flexible architecture patterns](https://aws-oss.beachgeek.co.uk/2c7) looks at how AWS IoT Core support of MQTTv5 features help enhance communications of large-scale device deployments and innovate device messaging patterns [hands on]

![overview of mqttv5 support in iotcore](https://d2908q01vomqb2.cloudfront.net/f6e1126cedebf23e1463aee73f9df08783640400/2022/11/26/AWS-iot-mqttv5-diagram.png)

* [Use AWS CDK v2 with the AWS Amplify CLI extensibility features (Preview)](https://aws-oss.beachgeek.co.uk/2c9) shows you how with v11.0.0-beta of the Amplify CLI, you can now use AWS CDK v2 to extend or modify your Amplify backend stack [hands on]


### Quick updates

**terraform-provider-aws**

This popular Terraform module now enables you to configure and deploy AWS Neptune Global clusters. You can view the [release notes here](https://aws-oss.beachgeek.co.uk/2bm).

**Apache Hudi, Apache Iceberg, Delta Lake**

AWS Glue for Apache Spark now supports three open source data lake storage frameworks: Apache Hudi, Apache Iceberg, and Linux Foundation Delta Lake. These frameworks allow you to read and write data in Amazon Simple Storage Service (Amazon S3) in a transactionally consistent manner. AWS Glue is a serverless, scalable data integration service that makes it easier to discover, prepare, move, and integrate data from multiple sources. This feature removes the need to install a separate connector and reduces the configuration steps required to use these frameworks in AWS Glue for Apache Spark jobs.

These open source data lake frameworks simplify incremental data processing in data lakes built on Amazon S3. They enable capabilities including time travel queries, ACID (Atomicity, Consistency, Isolation, Durability) transactions, streaming ingestion, change data capture (CDC), upserts, and deletes.

**Amazon EMR**

With Amazon EMR release 6.8, you can now use Amazon Elastic Compute Cloud (Amazon EC2) instances such as C6i, M6i, I4i, R6i, and R6id, which use the third-generation Intel Xeon scalable processors. Using these new instances with Amazon EMR improves cost-performance by an additional 5–33% over previous generation instances. To dive deeper into this, check out the blog post, [Amazon EMR launches support for Amazon EC2 C6i, M6i, I4i, R6i and R6id instances to improve cost performance for Spark workloads by 6–33%](https://aws-oss.beachgeek.co.uk/2bi)

**Apache Iceberg**

Amazon SageMaker Feature Store now supports the ability to create feature groups in the offline store in Apache Iceberg table format. The offline store contains historical ML features, organised into logical feature groups, and is used for model training and batch inference. Apache Iceberg is an open table format for very large analytic datasets such as the offline store. It manages large collections of files as tables and supports modern analytical data lake operations optimised for usage on Amazon S3.

Ingesting data, especially when streaming, can result in a large number of small files which can negatively impact query performance due the higher number of file operations required. With Iceberg you can compact the small data files into fewer large files in the partition, resulting in significantly faster queries. This compaction operation is concurrent and does not affect ongoing read and write operations on the feature group. If you chose the Iceberg option when creating new feature groups, SageMaker Feature Store will create the Iceberg tables using Parquet file format, and register the tables with the AWS Glue Data Catalog.

**Apache Spark**

Amazon Athena now supports Apache Spark, a popular open-source distributed processing system that is optimised for fast analytics workloads against data of any size. Athena is an interactive query service that helps you query petabytes of data wherever it lives, such as in data lakes, databases, or other data stores. With Amazon Athena for Apache Spark, you get the streamlined, interactive, serverless experience of Athena with Spark, in addition to SQL. You can build interactive Apache PySpark applications using a simplified notebook experience in the Athena console or through Athena APIs. With Athena, interactive Spark applications start in under a second and run faster with our optimised Spark runtime, so you spend more time on insights, not waiting for results. As Athena takes care of managing the infrastructure and configuring Spark settings, you can focus on your business applications.

Dive deeper into this launch by reading the post, [Explore your data lake using Amazon Athena for Apache Spark](https://aws-oss.beachgeek.co.uk/2bs) where Pathik Shah and Raj Devnath show how you can use Athena for Apache Spark to explore and derive insights from your data lake hosted on Amazon Simple Storage Service (Amazon S3). 

![graph from blog post of Apache Spark on Athena](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2022/11/14/bdb-2718-image023.jpg)

My fellow Developer Advocate Donnie Prakoso also put something together, so check out his post, [New — Amazon Athena for Apache Spark](https://aws-oss.beachgeek.co.uk/2bx) where he shows you how you can get started.

![demo of athena for apache spark](https://d2908q01vomqb2.cloudfront.net/da4b9237bacccdf19c0760cab7aec4a8359010b0/2022/10/03/Kepler-0.gif)

Amazon EMR announces Amazon Redshift integration with Apache Spark. This integration helps data engineers build and run Spark applications that can consume and write data from an Amazon Redshift cluster. Starting with Amazon EMR 6.9, this integration is available across all three deployment models for EMR - EC2, EKS, and Serverless. You can use this integration to build applications that directly write to Redshift tables as a part of your ETL workflows or to combine data in Redshift with data in other source. Developers can load data from Redshift tables to Spark data frames or write data to Redshift tables. Developers don’t have to worry about downloading open source connectors to connect to Redshift.

**OpenZFS**

Amazon FSx for OpenZFS now offers a new generation of file systems that doubles the maximum throughput and IOPS performance of the existing generation and includes a high-speed NVMe cache.

Amazon FSx for OpenZFS provides fully managed, cost-effective, shared file storage powered by the popular OpenZFS file system. The new generation of FSx for OpenZFS file systems provides two performance improvements over the existing generation. First, new-generation file systems deliver up to 350,000 IOPS and 10 GB/s throughput for both reads and writes to persistent SSD storage. Second, they include up to 2.5 TB of high-speed NVMe storage that automatically caches your most recently-accessed data, making that data accessible at over a million of IOPS and with latencies of a few hundred microseconds. With these new-generation file systems, you can power an even broader range of high-performance workloads like media processing/rendering, financial analytics, and machine learning with simple, highly-performant NFS-accessible storage.

**Ray**

AWS Glue for Ray is a new engine option on AWS Glue. Data engineers can use AWS Glue for Ray to process large datasets with Python and popular Python libraries. AWS Glue is a serverless, scalable data integration service used to discover, prepare, move, and integrate data from multiple sources. AWS Glue for Ray combines that serverless option for data integration with Ray (ray.io), a popular new open-source compute framework that helps you scale Python workloads.

You pay only for the resources that you use while running code, and you don’t need to configure or tune any resources. AWS Glue for Ray facilitates the distributed processing of your Python code over multi-node clusters. You can create and run Ray jobs anywhere that you run AWS Glue ETL (extract, transform, and load) jobs. This includes existing AWS Glue jobs, command line interfaces (CLIs), and APIs. You can select the Ray engine through notebooks on AWS Glue Studio, Amazon SageMaker Studio Notebook, or locally. When the Ray job is ready, you can run it on demand or on a schedule.

**MySQL**

A couple of updates for MySQL users, that should make you happy. Improvements on both READ and WRITES of data.

Amazon Relational Database Service (Amazon RDS) for MySQL now supports Amazon RDS Optimized Reads for up to 50% faster query processing compared to previous generation instances. Optimized Read-enabled instances achieve faster query processing by placing temporary tables generated by MySQL on the local NVMe-based SSD block-level storage that’s physically connected to the host server. Complex queries that utilize temporary tables, such as queries involving sorts, hash aggregations, high-load joins, and Common Table Expressions (CTEs) can now execute up to 50% faster with Optimized Reads on RDS for MySQL. 

Amazon RDS Optimized Reads is available by default on RDS for MySQL versions 8.0.28 and higher on Intel-based M5d and R5d instances and AWS Graviton2-based M6gd and R6gd database (DB) instances. R5d and M5d DB instances provide up to 3,600 GiB of NVMe SSD-based instance storage for low latency, high random I/O and sequential read throughput. M6gd and R6gd DB instances are built on the AWS Nitro System, and provide up to 3,800 GiB of NVMe-based SSD storage and up to 25 Gbps of network bandwidth. Amazon RDS Optimized Reads for Amazon RDS for MySQL is available today on M5d, R5d, M6gd, and R6gd instances in the same AWS Regions where these instances are available.

Amazon Relational Database Service (Amazon RDS) for MySQL now supports Amazon RDS Optimized Writes. With Optimized Writes you can improve write throughput by up to 2x at no additional cost. This is especially useful for RDS for MySQL customers with write-intensive database workloads, commonly found in applications such as digital payments, financial trading, and online gaming.

In MySQL, you are protected from data loss due to unexpected events, such as a power failure, using a built-in feature called the “doublewrite buffer”. But this method of writing takes up to twice as long, consumes twice as much I/O bandwidth, and reduces the throughput and performance of your database. Starting today, Amazon RDS Optimized Writes provide you with up to 2x improvement in write transaction throughput on RDS for MySQL by writing only once while protecting you from data loss and at no additional cost. Optimized Writes uses the AWS Nitro System, to reliably and durably write to table storage in one step. Amazon RDS Optimized Writes is available as a default option from RDS for MySQL version 8.0.30 and above and on db.r6i and db.r5b database instances.

You can dive deeper by checking out Jeff Barr's post, [New – Amazon RDS Optimized Reads and Optimized Writes](https://aws-oss.beachgeek.co.uk/2c6)

### Videos of the week

**AWS Lambda Powertools**

Heitor Lessa provided one of the best and most eagerly anticipated sessions at re:Invent, AWS Lambda Powertools: Lessons from the road to 10 million downloads. In this session, Heitor talked about the current state of Lambda Powertools, how this growth was supported, key lessons learned in the past two years, and what’s next on the horizon.

{{< youtube dH2GP6Lydj8 >}}


**Log4Shell**

This was my top recommendation for re:Invent attendees, and I am super happy that the video is already available for everyone to watch. Abbey Fuller is your speaker, and you will learn about the response to Log4Shell, from initial notification to hot patch, fleet scanning, and customer communications.

{{< youtube pkPkm7W6rGg >}}
{% youtube pkPkm7W6rGg %}

**Open Source tools on AWS**

Darko Mesaros and Curtis Evans have a look at open-source tools that can help make your AWS adventure easier. See something for security and permissions, something for cost management, and a few more things for building in the cloud—tools like Infracost, IAMLive, and more.

{{< youtube bEg-mIFZEmc >}}


**Yocto**

BitBake is a make-like build tool with the special focus of distributions and packages for embedded Linux cross compilation. Manually upgrading bitbake recipes often and testing them is time-consuming. Thomas Roos talks  about our approach to automate the Yocto layer maintenance of meta-aws with cloud managed services technologies. Maintenance means upgrading software versions, testing, committing bitbake recipes and back porting of changes from master to release branches. You can also call it CI/CD for Yocto layers.

{{< youtube CNCjtQj74VI >}}


**Build on Open Source**

For those unfamiliar with this show, Build on Open Source is where we go over this newsletter and then invite special guests to dive deep into their open source project. Expect plenty of code, demos and hopefully laughs. We have put together a playlist so that you can easily access all (seven) of the other episodes of the Build on Open Source show. [Build on Open Source playlist](https://aws-oss.beachgeek.co.uk/24u)

# Events for your diary

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)