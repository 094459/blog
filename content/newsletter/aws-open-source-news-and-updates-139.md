---

title: 'AWS open source news and updates #139'
date: '2022-12-18'
tags : [ oss-newsletter, aws open source, Prowler, Terraform, AWS IoT Greengrass v2, Karpenter, PostgreSQL, MySQL, AWS Amplify, Apache Skywalking, Micronaut, Kubernetes, Grafana, Porting Assistant for .NET, Bottlerocket, Amazon EMR, AWS CDK, Apache Ranger]

---

## December 18th, 2022 - Instalment #139

**Welcome**

Welcome to the last AWS open source newsletter of 2022, edition #139. I am planning on take a few weeks off to recharge, and wish readers of this newsletter a fabulous Christmas and New Year. Over 100K of you have read this newsletter, so I want to thank you all for your continued support. This newsletter is only possible because of the passion and enthusiasm of open source Builders, and I look forward to seeing what 2023 will bring.

I hope some of you managed to catch the last episode of Build on Open Source for 2022. After a quick look back at the best of 2022, we had another awesome guest, AWS Community Builder Ran Isenberg. If you missed the session, don't worry, you can catch up by checking out the Video section below. 

This week we feature more great projects, including "jupyter-scheduler", a JupyterLab extension for running notebook jobs ,"aiac" chatGPT but for creating Terraform code, "hardeneks" a tool to help you baseline your Amazon EKS environments, "aws-lambda-snapstart-java-rules" make sure your Java based lambda functions will work with SnapStart, "aws-tf-prowler-fargate" probably the easiest way to run Prowler on your AWS environments, "aws-iot-greengrass-v2-painless-installer" a great way to simplify how to install AWS IoT Greengrass v2, and many more. If reading is more your thing, then why not check out the tutorials, blog posts, hands on deep dives covering many of your favourite open source projects, including this week Terraform, AWS IoT Greengrass v2, Karpenter, PostgreSQL, MySQL, AWS Amplify, Apache Skywalking, Micronaut, Kubernetes, Grafana, Porting Assistant for .NET, Bottlerocket, Amazon EMR, AWS CDK, and Apache Ranger. 

Make sure you don't skip the Videos section as we have some top notch videos this week, and we wrap up with some events to check out for early 2023, including the State of Open Con 23 - the CFP is open and closes this Sunday so get busy and submit a talk for this event if you can.

**Build on Open Source season two**

Finally, before I leave you I want to share that we are currently planning the second season of Build on Open Source and we are looking for open source Builders, Maintainers, and enthusiasts to come on as guests and talk about their favourite projects or walk us through what they are currently working on. Could that be you? Please get in touch, either via [email](mailto:ricsue@amazon.com?subject=Build%20on%20Open%20Source), commenting below, or contact Derek or myself via social media. 

**Celebrating open source contributors**

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created. 

So thank you to the following open source heroes: Jerome Van Der Linden, Laurence Geng, Medha Shree, Ayush Kumar, Swaminathan Jayaraman, Andreas Wittig, Sebastian Bille, Sai Vennam, Isaac Levin, Marcio Morales, Bruno Gabriel da Silva, Robert Northard, Elamaran Shanmugam, Premal Tailor, Salman Sali, Vadym Kazulkin, Yue Guo, Jimmy Ray and Sriram Ranganathan.

### A look back at the most popular projects of 2022

As this is the last newsletter of 2022, I thought I would share what have been the most popular projects this year (measured by folks that have clicked on the links). These are just too good to miss, so check this list out and let me know what you think. What were your favourite projects of 2022? What is missing that you are surprised about?

**2022 most popular projects**

*	[querypal](https://aws-oss.beachgeek.co.uk/x) the most viewed project, provides a nice WebUI for Amazon Athena
*	[cfn-diagram](https://aws-oss.beachgeek.co.uk/4r) is CLI tool to visualise CloudFormation/SAM/CDK stacks as visjs networks, draw.io or ascii-art diagrams
*	[driftctl](https://aws-oss.beachgeek.co.uk/2p) helps you detect, track and alert on infrastructure drift
* [infracost](https://aws-oss.beachgeek.co.uk/7l) shows cloud cost estimates for Terraform
* [aws-sdk-client-mock](https://aws-oss.beachgeek.co.uk/ll) provides AWS JavaScript SDK v3 mocks for easy unit testing
* [cfn_nag](https://aws-oss.beachgeek.co.uk/ng) is a linting tool for CloudFormation templates
* [steampipe](https://aws-oss.beachgeek.co.uk/dl) ise SQL to instantly query AWS resources across regions and accounts
* [keycloak](https://aws-oss.beachgeek.co.uk/lf) is an open source Identity and Access Management solution
* [gnuradio](https://aws-oss.beachgeek.co.uk/1au) is a free & open-source software development toolkit that provides signal processing blocks to implement software radios
* [eventcatalog](https://aws-oss.beachgeek.co.uk/18d) helps you discover, explore and document your Event Driven Architectures powered by Markdown.
* [ddb_local](https://aws-oss.beachgeek.co.uk/17r) provides a Python wrapper for DynamoDB Local
* [cloudquery-policies/aws](https://aws-oss.beachgeek.co.uk/16f) is an open-source cloud asset inventory powered by SQL
* [kronicle](https://aws-oss.beachgeek.co.uk/1ik) is an open source tool and dashboard for documenting and visualising a tech stack
* [memq](https://aws-oss.beachgeek.co.uk/1cs) is an efficient, scalable cloud native PubSub system from Pintrest

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution.*

#### Tools

**hardeneks**

[hardeneks](https://aws-oss.beachgeek.co.uk/2d3) this tool tuns checks to see if an Amazon EKS cluster follows EKS Best Practices.

![demo of tool running](https://raw.githubusercontent.com/aws-samples/hardeneks/main/docs/hardeneks.gif)

**aws-lambda-snapstart-java-rules**

[aws-lambda-snapstart-java-rules](https://aws-oss.beachgeek.co.uk/2cx) introduced during re:Invent, you can use AWS Lambda SnapStart environments to make big improvements in your cold start times. There are some things as a developer you need to be aware of (check the docs) but this tool, the SnapStart Bug Scanner is the [SpotBugs](https://aws-oss.beachgeek.co.uk/2cy) (an open source static analysis tool to look for bugs in Java code) plugin for helping AWS Lambda customers inspect their functions against potential bugs unique to AWS Lambda SnapStart environment. Using it will help you determine whether your code can run in AWS Lambda SnapStart environments. 

**aiac**

[aiac](https://aws-oss.beachgeek.co.uk/2df) is a command line tool to generate IaC (Infrastructure as Code) templates via OpenAI's API. The CLI allows you to ask the model to generate templates for different scenarios (e.g. "get terraform for AWS EC2"). It will make the request, and store the resulting code to a file, or simply print it to standard output. With the excitement around chatGPT, this project looks super interesting. I have already tried (and been impressed) with asking chatGPT to write basic code, so lets see how this does.

![demo of aiac tool](https://github.com/gofireflyio/aiac/blob/main/demo.gif?raw=true)

**jupyter-scheduler**

[jupyter-scheduler](https://aws-oss.beachgeek.co.uk/2dr) is a JupyterLab extension for running notebook jobs. This extension is composed of a Python package named jupyter_scheduler for the server extension and a NPM package named @jupyterlab/scheduler for the frontend extension. Installation of this extension provides a REST API to run, query, stop and delete notebook jobs; the UI provides an interface to create, list and view job details. Read the post Introducing Jupyter Scheduler, where Jason Weill introduces the project and how you can get started.

![screenshot integration of jupyter scheduler](https://miro.medium.com/max/1400/1*nUcvmd-_anAtX4rT5MGPfA.webp)

**aws-tf-prowler-fargate**

[aws-tf-prowler-fargate](https://aws-oss.beachgeek.co.uk/2cv) is a Terraform module helps you assess your multi-account environment in AWS Organizations using the open source Prowler security assessment tool deployed on AWS Fargate. It assesses all accounts using a time-based schedule expression in Amazon CloudWatch, creates assessment reports in CSV format, and stores them in an Amazon Simple Storage Service (S3) bucket.

![architecture of prowler terraform solution](https://github.com/aws-samples/aws-tf-prowler-fargate/blob/main/images/Prowler-ECS-Architecture.png?raw=true)

**aws-iot-greengrass-v2-painless-installer**

[aws-iot-greengrass-v2-painless-installer](https://aws-oss.beachgeek.co.uk/2cw) this solution allows installing Greengrass V2 on an edge gateway without requiring access to the AWS account where the device will connect. The User supervising the installation only needs to be able to authenticate with Amazon Cognito in order to initiate the installation process. No specific knowledge of the AWS Cloud nor Greengrass is necessary. The solution can be further customised for instance to federate user authentication to your enterprise identity management system (e.g. Active Directory).

![architecture overview of iot greengrass installer](https://github.com/aws-samples/aws-iot-greengrass-v2-painless-installer/blob/main/doc/ArchitectureDiagrams-OverallArchitecture.png?raw=true)

**anti-malware-scanning**

[anti-malware-scanning](https://aws-oss.beachgeek.co.uk/2dp) Hardik Singh Behl has put together this reference solution together on how you can us the open source anti virus tool ClamAV, and use event driven capabilities of Amazon S3 to execute a Lambda function that scans the file for bad things. Very nice.

![architecture of malware scanning](https://user-images.githubusercontent.com/69693621/207793461-9d9f0195-58d8-4d99-93c7-8496880662bb.png)

**cdk-s3-upload-presignedurl-api**

[cdk-s3-upload-presignedurl-api](https://aws-oss.beachgeek.co.uk/2dq) Jerome Van Der Linden has created this new AWS CDK construct to make your lives easier. If you want your users to be able to #upload a specific object to an Amazon S3 bucket, but you don't want them to have AWS security credentials or permissions, you can use pre-signed URLs. It's a common pattern but before Jerome created this construct, there was no IaC component that you could leverage directly. Great stuff Jerome.

### Demos, Samples, Solutions and Workshops

**Lucene.Net-AWS-Lambda-EFS**

[Lucene.Net-AWS-Lambda-EFS](https://aws-oss.beachgeek.co.uk/2dg) this project from Salman Sali enables you to implement a Serverless Search for .Net hosted on AWS Lambda with Amazon EFS Storage.

**amazon-keyspaces-with-apache-kafka**

[amazon-keyspaces-with-apache-kafka](https://aws-oss.beachgeek.co.uk/2d1) this repository contains hands on content how to build a data pipeline to ingest real time data using managed open-source compatible services such as Amazon Elastic Kubernetes Service (EKS), Amazon Managed Streaming for Apache Kafka (MSK), and Amazon Keyspaces (for Apache Cassandra). Apache Kafka and Cassandra share distributed core capabilities like high availability, scalability, and throughput that makes them a good solution for large scale processing applications like IoT data, user metadata, trade monitoring, and route optimisation. This data pipeline can consume a sample stream from Twitter API which streams 1% of all the tweets in realtime as a data source, parse the tweets, metadata, and publish the parsed data to a Kafka topic. Kafka works as a distributed queue as well as a buffer layer to transport messages. MSK Connect consumes these messages from Kafka topic and writes them to Amazon Keyspaces tables.

The solution uses EKS to deploy containerised Twitter Event source application, the containerised application consumes, and a stream of tweets from Twitter API, parse the tweets (discards tweets that don’t have a hashtag), extract tweet metadata (created at, lang etc.), publishes these messages to Kafka topic twitter_input with desired fields using Kafka producer API. You will use the MSK Connect to ingest data from the twitter_input topic to Amazon Keyspaces.

![architecture of solution.](https://github.com/aws-samples/amazon-keyspaces-with-apache-kafka/blob/main/static/architecture.png?raw=true)

**iot-analytics-athena-ddb**

[iot-analytics-athena-ddb](https://aws-oss.beachgeek.co.uk/2cu) provides a solution for a reference architecture to analyse electricity data from smart meters, for maintenance purposes of a hypothetical Energy company, and for self-service analysis of customers, to understand how much electricity they consume.

![architecture of iot electricity solution](https://github.com/aws-samples/iot-analytics-athena-ddb/blob/main/assets/images/iot-analytics-solution-git-cover.png?raw=true)

**amazon-sagemaker-clip-search**

[amazon-sagemaker-clip-search](https://aws-oss.beachgeek.co.uk/2cz) this repository aims at building a machine learning (ML) powered search engine prototype to retrieve and recommend products based on text or image queries. This is a step-by-step guide on how to create SageMaker Models with Contrastive Language-Image Pre-Training (CLIP), use the models to encode images and text into embeddings, ingest embeddings into Amazon OpenSearch Service index, and query the index using OpenSearch Service k-nearest neighbors (KNN) functionality.

![architecture for sagemaker clip search](https://github.com/aws-samples/amazon-sagemaker-clip-search/blob/main/pictures/blog.drawio.png?raw=true)

**ack-rds-gitops-workshop**

[ack-rds-gitops-workshop](https://aws-oss.beachgeek.co.uk/2d0) roll your sleeves up for this great workshop, where you will learn to deploy a continuous integration and delivery (CI/CD) workflow using GitOps and the AWS Controllers for Kubernetes (ACK) service controller for Amazon RDS on Amazon EKS to create and manage Amazon Aurora Serverless v2 databases effectively. GitOps relies on Git as the single source of truth for declaratively managing containerised infrastructure and application components. With Git at the centre of CI/CD pipelines, developers can automate and simplify application deployments and operations to Kubernetes. 

###2022 most popular posts

As this is the last newsletter of 2022, I wanted to highlight the most viewed blog posts of 2022 just in case some of you missed these. These are the top ten, so am hoping that some of these will be new to you.

* [Presto® on Apache Kafka® At Uber Scale](https://aws-oss.beachgeek.co.uk/1ls)
* [Dashboards as Code with HCL + SQL](https://aws-oss.beachgeek.co.uk/1hk)
* [The Art of Building Open Data Lakes with Apache Hudi, Kafka, Hive, and Debezium](https://aws-oss.beachgeek.co.uk/17v)
* [Monitor AWS resources created by Terraform in Amazon DevOps Guru using tfdevops](https://aws-oss.beachgeek.co.uk/17k)
* [Progressive Delivery using AWS App Mesh and Flagger](https://aws-oss.beachgeek.co.uk/17n)
* [Parallel CDK stack deployments with GitHub Actions](https://aws-oss.beachgeek.co.uk/1lu)
* [Use CDK8S To Create AWS Controllers for Kubernetes Custom Resources](https://aws-oss.beachgeek.co.uk/1je)
* [How Prime Video updates its app for more than 8,000 device types](https://aws-oss.beachgeek.co.uk/1b9)
* [First Look at Lambda Powertools TypeScript](https://aws-oss.beachgeek.co.uk/196)
* [AWS CDK v2 Tutorial – How to Create a Three-Tier Serverless Application](https://aws-oss.beachgeek.co.uk/17u)

Congratulations to the writers of these posts, you have obviously put together something of interest to the broader open source and AWS community.

### AWS and Community blog posts

From a retrospective look to the latest blog posts for you to enjoy.

**Karpenter**

Ran Tao, Cloud architect @Jina AI shares a detailed guide on how to lower the cost of using GPUs by using time-slicing, and how you can achieve that using Karpenter. In the post, [Time-Slicing GPUs with Karpenter](https://aws-oss.beachgeek.co.uk/2d7) find out more about how you can use Karpenter and NVIDIA’s k8s plugin to achieve time-slicing on GPUs that will allow users to share GPUs between pods, and hence save on costs.

![architecture of karpenter time slicing gpu](https://res.cloudinary.com/practicaldev/image/fetch/s--uqeSDJOU--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://miro.medium.com/max/1400/1%2A9fXBwPJii317MA5OPouEdg.png)

**Micronaut**

AWS Community Builder Vadym Kazulkin has written his latest blog post, a two part series on Measuring Java 11 Lambda cold starts with SnapStart. In the first, [Measuring Java 11 Lambda cold starts with SnapStart - Part 1 First Impressions](https://aws-oss.beachgeek.co.uk/2db) he provides a quick introduction and overview of this new capability within AWS Lambda, and in the follow up post, [Measuring Java 11 Lambda cold starts with SnapStart - Part 2 Using Micronaut Framework](https://aws-oss.beachgeek.co.uk/2d5) revisits the first post but this time comparing what happens when using the Micronaut framework.

**Apache Skywalking**

Apache SkyWalking is an open source Application Performance Monitoring (APM) tool for monitoring and troubleshooting distributed systems, especially designed for micro services, cloud native and container-based (Docker, Kubernetes, Mesos) architectures. My colleague Yue Guo has put together a blog post, [How to run Apache SkyWalking on AWS EKS and RDS/Aurora](https://aws-oss.beachgeek.co.uk/2d4) on how to quickly set up Apache SkyWalking on AWS EKS and RDS/Aurora, as well as a couple of sample services, monitoring services to observe SkyWalking itself.

![example dashboard for apache skywalker](https://res.cloudinary.com/practicaldev/image/fetch/s--Md575NF4--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ek4lmsvf78f0wdkbndii.png)

**Apache Ranger**

Apache Ranger™ is a framework to enable, monitor and manage comprehensive data security across the Hadoop platform. Amazon EMR enables fine-grained access control with Apache Ranger through a number of [components](https://aws-oss.beachgeek.co.uk/2do) (a Secret Agent and EMR record server). In the tutorial [Apache Ranger and AWS EMR Automated Installation and Integration Series (4): OpenLDAP + Open-Source Ranger](https://aws-oss.beachgeek.co.uk/2dn), Laurence Geng shows you how to use OpenLDAP as the authentication provider, and user accounts data store on it, and Ranger plays the authorisation controller. [hands on]

![architecture overview of ranger on amazon emr and openldap](https://dz2cdn1.dzone.com/storage/temp/16532375-ranger-opensource-arch.png)

**Kubernetes**

A few posts this week, starting off with [Blue/Green Kubernetes upgrades for Amazon EKS Anywhere using Flux](https://aws-oss.beachgeek.co.uk/2d9), where Robert Northard, Elamaran Shanmugam, and Premal Tailor detail a solution on how you can achieve blue/green Kubernetes platform deployments on Amazon EKS-A deployed on vSphere. [hands on]

![decision flow chart diagram](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2022/12/13/Blue-Green_Architecture_Diagram.png)

Following that Marcio Morales and Bruno Gabriel da Silva have written [Windows Authentication on Amazon EKS Windows pods](https://aws-oss.beachgeek.co.uk/2da), an end-to-end guide on how to configure an Amazon EKS cluster to exchange Kerberos tickets with an Active Directory Domain, allowing Windows pods to use Windows Authentication. [hands on]

Jimmy Ray and Sriram Ranganathan shared an overview of newly released Amazon EKS add-ons advanced configurations support in their post, [Amazon EKS add-ons: Advanced configuration](https://aws-oss.beachgeek.co.uk/2dh). Advanced configuration support for Amazon EKS add-ons allows you to set your configuration directly through the Amazon EKS add-ons API, to install and configure their operational software during cluster creation in a single step.[hands on]

At re:Invent we announced the availability of AWS Marketplace add-ons for Amazon EKS. This feature extends the add-ons experience to include operational software for security, storage, observability, and networking available in AWS Marketplace. Swaminathan Jayaraman and Sai Vennam walk you through this in the post, [Deploy third-party software add-ons from AWS Marketplace to Amazon EKS clusters.](https://aws-oss.beachgeek.co.uk/2di) [hands on] 

![architecture of aws marketplace deployments for eks](https://d2908q01vomqb2.cloudfront.net/761f22b2c1593d0bb87e0b606f990ba4974706de/2022/12/13/arch_diagram.png)

Finally we have the post [Expose Amazon EKS pods through cross-account load balancer](https://aws-oss.beachgeek.co.uk/2dl) from Medha Shree and Ayush Kumar who show you how to expose Amazon EKS pods through cross-account load balancing. [hands on]

**Other posts and quick reads**

* [Deploy a Next.js 13 app with authentication to AWS Amplify](https://aws-oss.beachgeek.co.uk/2dm) explains how to create and deploy a Next.js 13 app with user authentication to Amplify Hosting in five steps [hands on]
* [Cloud Brigade Accelerates Full-Stack App Development with AWS Amplify](https://aws-oss.beachgeek.co.uk/2d8) is a case study from Cloud Brigade and how they leverage AWS Amplify to accelerate development of solutions for their customers

![architecture of cloud bridge sample solution](https://d2908q01vomqb2.cloudfront.net/0a57cb53ba59c46fc4b692527a38a87c78d84028/2022/12/08/Screen-Shot-2022-12-07-at-4.59.43-PM-1024x647.png)

* [Partition existing tables using native commands in Amazon RDS for PostgreSQL and Amazon Aurora PostgreSQL](https://aws-oss.beachgeek.co.uk/2dk) shares how to use PostgreSQL native SQL commands to convert an existing non-partitioned table to a partitioned one [hands on]
* [Datavail: Migrating and modernizing commercial databases to open-source database engines on AWS](https://aws-oss.beachgeek.co.uk/2dj) an interview with Datavail on how they are helping to migrate customers to open source databases

![overview of datavail process](https://d2908q01vomqb2.cloudfront.net/8effee409c625e1a2d8f5033631840e6ce1dcb64/2022/12/14/datavail_process.jpg)

### Quick updates

**AWS CDK**

[V2.55 release of AWS CDK](https://aws-oss.beachgeek.co.uk/2de) was released, containing the usual new featurs, bug fixes and changes, which include:

* autoscaling: support default instance warmup for Auto Scaling groups 
* cfnspec: cloudformation spec v101.0.0
* cognito: add new AdvancedSecurityMode property 
* core: add volumes-from option to docker run command for bundling 
* s3: update runtime of notifications-handler to python3.9 
* s3-deployment: add additional sources with addSource 

**Amazon EMR**

Amazon EMR on EKS now supports accelerated computing over graphics processing unit (GPU) instance types using Nvidia RAPIDS Accelerator for Apache Spark. The growing adoption of artificial intelligence (AI) and machine learning (ML) in analytics has increased the need for processing data quickly and cost efficiently with GPUs. Nvidia RAPIDS Accelerator for Apache Spark helps customers leverage the benefit of GPU performance while saving infrastructure costs. With this release, EMR on EKS customer can use the RAPIDS accelerator by simply specifying the Spark-RAPIDS release label when calling EMR on EKS API.

Until now, EMR on EKS customers had to create a custom image to use Nvidia RAPIDS Accelerator. This requires engineering and test effort. In addition, with every new Nvidia RAPIDS release, bug fixes or security updates, customers had to rebuild the custom image and go through the testing again. Starting with EMR 6.9, EMR on EKS is introducing a new Nvidia RAPIDS Accelerator for Spark image. Customers can use the same StartJobRun API to run their Spark jobs, and simply specify a new Spark-RAPIDS release label to leverage RAPIDS Accelerator on an EKS cluster with GPU supported instance type. 

**Prowler**

[Prowler](https://aws-oss.beachgeek.co.uk/2ct), the handy cloud security tool, new version 3.0 has been fully rewritten in Python and can scan your AWS account in minutes across all regions and covering more than 250 checks for the most popular AWS services. Prowler v3 also comes with a new check architecture, better compliance support and consolidated reporting formats.

**PostgreSQL**

Amazon Relational Database Service (RDS) Proxy now supports Amazon Aurora with PostgreSQL-compatibilie edition and Amazon RDS for PostgreSQL running major version 14. PostgreSQL 14 consists of performance improvements for parallel queries, heavily-concurrent workloads, partitioned tables, logical replication, and vacuuming. PostgreSQL 14 also improves functionality with new capabilities. For example, you can cancel long-running queries if a client disconnects and you can close idle sessions if they time out. With this launch, you can enforce SCRAM (Salted Challenge Response Authentication Mechanism) password-based authentication for proxy, making connections from your applications more secure.

**Grafana**

Amazon Managed Grafana now supports AWS CloudFormation. You can use AWS CloudFormation templates to create, update, and delete your Amazon Managed Grafana workspaces, as well as manage or update workspace SAML authentication settings.

**AWS Amplify**

A couple of quick updates for AWS Amplify users.

Last week was the announcement of the general availability of v2.0 Amplify Library for Android. Amplify Library for Android allows developers building apps for the Android platform to easily include features like authentication, storage, maps, and more. This version of the library has been re-written to improve Android developers’ experience when using Auth and Storage features.

Also announced was the release of version 5 of the JavaScript library, which includes highly requested features for Web and React Native developers. This release also introduces a new Notifications channel, In-App Messaging, that developers can use to display contextual messages to their users based on their behaviour. The Amplify JavaScript library has also received improvements to reduce the overall bundle size and installation size. With this release, JavaScript developers can build media and file storage experiences with more granular pagination controls. Developers can now retrieve and filter nested models with Datastore lazy loading, such as retrieving all comments on a blog post. Amplify also provides UI components to make it easier to display In-App messages for React and React Native apps. Lastly, Apps that use GraphQL or PubSub subscriptions by default automatically re-connect when the user’s internet disconnects, providing a seamless experience for end users in poor connectivity scenarios.

**MySQL and PostgreSQL**

Amazon DevOps Guru for RDS now detects if your Amazon Aurora database is receiving a significantly larger number of SQL queries and if those queries are reading more data than usual. This new functionality will help you to discover, in the event of degraded database performance, if an application traffic change is the likely cause of the performance degradation. Amazon DevOps Guru for RDS currently supports Amazon Aurora MySQL-Compatible Edition and Amazon Aurora PostgreSQL-Compatible Edition

### Videos of the week

**IAM Legend**

Join Andreas Wittig as he speaks with Sebastian Bille, who shows us an open source project he created called IAM Legend. IAM Legend is an extension for Visual Studio Code. When editing IAM policies, the tool provides auto-completion and documentation for IAM actions. IAM Legend speeds up the process of writing IAM policies following the least-privilege principle.

{{< youtube 20E_bKm4jVs >}}


**Bottlerocket**

Securing EKS Clusters Using Bottlerocket gives viewers an overview of Bottlerocket, current security challenges and related features, and a live demo showing how easy it is to set up. 

{{< youtube KVFZ4mHFXII >}}


**Karpenter**

Karpenter is a compute provisioning and management solution, which also acts as a cluster autoscaler. In this video, Sai Vennam shows you how open-source Karpenter works, and how it differs from Kubernetes Cluster Autoscaler.

{{< youtube FIBc8GkjFU0 >}}


**Porting Assistant for .NET**

Are you a .NET developer and you are still maintaining a few .NET Framework apps? Are you hearing about the latest in .NET and want to look into modernising? If so, there is an open source tool you should look into. The Porting Assistant for .NET from AWS is an Open Source tool that you can use today to help you in your journey to the latest versions of .NET. My colleauge Isaac Levin is your host as he walks you through the Porting Assistant and see how you can start using it today!  

{{< youtube a3PI3klFtk8 >}}


**Build on Open Source**

This newsletter was reviewed in the latest Build on Open Source show, S01E08. If you missed the show, you can [still watch it over on YouTube](https://www.youtube.com/watch?v=VN_FiwJ45fE)

{{< youtube VN_FiwJ45fE >}}

For those unfamiliar with this show, Build on Open Source is where we go over this newsletter and then invite special guests to dive deep into their open source project. Expect plenty of code, demos and hopefully laughs. We have put together a playlist so that you can easily access all (seven) of the other episodes of the Build on Open Source show. [Build on Open Source playlist](https://aws-oss.beachgeek.co.uk/24u)

# Events for your diary

If you are planning any events in 2023, either virtual, in person, or hybrid, get in touch as I would love to share details of your event with readers. 

**FOSSDEM**
**Feb 4-5th, 2023 in Brussles**

FOSDEM is a free event for software developers to meet, share ideas and collaborate. Every year, thousands of developers of free and open source software from all over the world gather at the event in Brussels. 4 & 5 February 2023. A must attend event for all open source fans, check out and [register via this link](https://aws-oss.beachgeek.co.uk/2dc).

**State of Open Con 23**
**Feb 7-8th, 2023 in London**

OpenUK will be hosting a 1000 person plus two day conference in Central London, “State of Open Con 23”  in association with IEEE, the headline sponsor. Check out more info and [sign up here](https://aws-oss.beachgeek.co.uk/2dd).

**Everything Open**
**March14-15th Melbourne, Australia**

A new event for the fine folks in Australia. Everything Open is running for the first time, and the organisers (Linux Australia) have decided to run this event to provide a space for a cross-section of the open technologies communities to come together in person. Check out the [event details here](https://aws-oss.beachgeek.co.uk/2ds). The CFP us currently open, so why not take a look and submit something if you can.

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)