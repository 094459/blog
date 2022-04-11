---

title: 'AWS open source news and updates #103'
date: '2022-03-07'
tags : [ oss-newsletter, aws open source, Apache Spark, Apache Kafka, Amazon Athena Federated Queries, XEN, Apache Cassandra, MySQL, OpenZFS, PostgreSQL, Kubeflow, Apache Airflow, ROS, Kubernetes, Amazon EMR, Grafana, Prometheus, Karpenter, Apache Flink, Apache Hudi, Babelfish for Aurora PostgreSQL, AutoGluon]

---

## March 7th, 2022 - Instalment #103

Newsletter #103. 

Welcome to edition #103 of the AWS open source news and updates. This weeks featured new open source projects include botocove (a decorator that helps you run your functions across your AWS accounts easily), functionless (a TypeScript plugin that transforms TypeScript code into Service-to-Service integrations), replibyte (a tool to replicate your PostgreSQL data), aws-security-bulletin-alert (notifies you of new AWS Security Bulletins) and sends out E-Mail notifications via Amazon SES), and many more. This weeks round up of articles and blogs across the AWS and Community include another broad variety of topics, including Apache Spark, Apache Kakfa,  OpenZFS, PostgreSQL, Kubeflow, Apache Airflow, ROS, Kubernetes, Grafana, Prometheus, Karpenter, Apache Flink, Apache Hudi, Babelfish for Aurora PostgreSQL, AutoGluon and more. This week we feature a new white paper, Patterns for Ingesting SaaS Data into AWS Data Lakes, so don't miss that. To finish this weeks edition we have a number of great videos on Open 3D engine, XEN and Terraform, as well as a list of open source related events you should check out.

As always, if you are working on anything interesting you would like me to include in this weekly round up, please drop me a line at ricsue@amazon.com.


### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Dave Connell, Sam Goodwin, Mattia Berlusconi, Paola Lorusso, Jose Alfredo de Castro Nunes, Krithivasan Balasubramaniyan, Rumeshkrishnan Mohan, Naseer Ahmed, Igor Alekseev, Ramesh Mathikumar, Gabriel Soto, Vara Bonthu, Raja Ganesan, Aldred Halim, Ryan Shevchik, Neil Ashton, Ali Alemi, Jenna Pederson, J. Cole Morrison, Ivan Cui, Jonas Mueller, and Wenming Ye.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest open source projects

#### Community

**botocove**

[botocove](https://aws-oss.beachgeek.co.uk/1fi) this project from Dave Connell provides a simple decorator for functions to run them against all AWS accounts in an organisation. You can run a function against a selection of AWS accounts, Organisational Units (OUs) or all AWS accounts in an organisation, concurrently with thread safety. Run in one or multiple regions.

**functionless**

[functionless](https://aws-oss.beachgeek.co.uk/1fb) this new project from Sam Goodwin is a TypeScript plugin that transforms TypeScript code into Service-to-Service (aka. "functionless") integrations, such as AWS AppSync Resolvers and Velocity Templates, or (coming soon) Amazon States Language for AWS Step Functions. To find out more, with plenty of examples, dive into this repo.

**replibyte**

[replibyte](https://aws-oss.beachgeek.co.uk/1fa) current in alpha state, this new open source tool from the lovely folks at Qovery is a standalone application to replicate your cloud databases from one place to the other. The repo provides some background as to the motivation for the tool, and gives some example of how you can use this to synchronise PostgreSQL databases on AWS. One to watch.

![arch](https://raw.githubusercontent.com/Qovery/replibyte/672ee1def6ef87e292236f42aef057f260556e0b/assets/diagram.svg)

#### Tools

**eks-anywhere-packages**

[eks-anywhere-packages](https://aws-oss.beachgeek.co.uk/1f9) EKS Anywhere curated packages is a framework to manage installation, configuration and maintenance of components that provide general operational capabilities for Kubernetes applications.

**api-gateway-dynamic-publish**

[api-gateway-dynamic-publish](https://aws-oss.beachgeek.co.uk/1fd) this is a nice open sourced resources that uses AWS CDK and leverages an OpenAPI definition to define, document and create an Amazon API Gateway deployment. At deploy time, a CloudFormation Custom Resource is leveraged to dynamically substitute the Lambda integration function ARNs into the OpenAPI definition file as well as publishing the updated file to an S3 bucket for documentation viewing. This is a must check out project this week.

![arch](https://github.com/aws-samples/api-gateway-dynamic-publish/blob/main/docs/assets/solution-architecture.png?raw=true)

**aws-security-bulletin-alert**

[aws-security-bulletin-alert](https://aws-oss.beachgeek.co.uk/1fe)

If you are looking for a way to be proactively notified of new security bulletins, then this project will be of interest. This CDK project deploys an AWS Lambda Function which is scheduled for every full hour. It checks the https://aws.amazon.com/security/security-bulletins for new AWS Security Bulletins and sends out E-Mail notifications via Amazon SES.

![arch](https://github.com/aws-samples/aws-security-bulletin-alert/blob/main/img/diagram.png?raw=true)

#### Demos and Samples

**aws-proton-tutorial**

[aws-proton-tutorial](https://aws-oss.beachgeek.co.uk/1fg) Proton is a fully managed AWS service that helps engineering platform teams build developer portals to streamline the SDLC (software development lifecycle). Proton has two main goals: increase developers' productivity and agility while allowing organisations to maintain the right level of control and governance. This workshop/tutorial from Massimo Re Ferrè is for those of a curious nature that want to understand more.

**eks-multi-environment-cdk-pipeline**

[eks-multi-environment-cdk-pipeline](https://aws-oss.beachgeek.co.uk/1ff) This project shows how AWS CDK can be used to provision and manage EKS cluster deployed in multiple environments. This project uses cdk-pipelines construct to create pipeline between the different Amazon EKS clusters that deployed in multiple environments. This project follows EKS Best practices guide, and deploy relevant add-ons like Cluster-Autoscaler, AWS Load Balancer Controller, and SSM Agent. It also deploys Weave Flux V2 for GitOps delivery. The reason that the Cluster add-ons are deployed using CDK and not using Flux, is because these add-ons require configurations both on the AWS and on the EKS/K8s (IAM roles and policies on AWS, and add-on deployment on K8s). All other application deployments will be deployed using Weave Flux V2.

![arch](https://github.com/aws-samples/eks-multi-environment-cdk-pipeline/blob/main/images/eks-multi-environment-cdk-pipeline.png?raw=true)

**serverless-java-frameworks-samples**

[serverless-java-frameworks-samples](https://aws-oss.beachgeek.co.uk/1fc) this repo provides a simple serverless application built in Java using popular frameworks, Micronaut, Quarkus, and Spring Boot

![arch](https://github.com/aws-samples/serverless-java-frameworks-samples/blob/main/imgs/diagram.jpg?raw=true)

**mediatailor-vod-upload**

[mediatailor-vod-upload](https://aws-oss.beachgeek.co.uk/1f7) this is a sample project and demo workflow that automates adding video on demand (VOD) sources to AWS MediaTailor Channel Assembly. To learn about AWS MediaTailor Channel Assembly, [this workshop](https://aws-oss.beachgeek.co.uk/1f8) walks through defining sources, creating a channel and programs along with test source content.

![arch](https://github.com/aws-samples/mediatailor-vod-upload/blob/main/AWS_Services.png?raw=true)

### AWS and Community blog posts

**Apache Kafka, Apache Flink, and Apache Hudi**

Ali Alemi  is a Streaming Specialist Solutions Architect at AWS, and shares some of his wisdom in this post, 
[Create a low-latency source-to-data lake pipeline using Amazon MSK Connect, Apache Flink, and Apache Hudi](https://aws-oss.beachgeek.co.uk/1f4). The post helps you understand the different ways of working with streaming data with minimum coding, and demonstrate how to build fully scalable pipelines using SQL language without prior knowledge of Flink or Hudi. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2022/02/10/BDB-1970-image001.png)

**Apache Airflow**

In my continuing quest for more knowledge on Apache Airflow, I came across this post [Orchestrating Databricks Workloads on AWS With Managed Workflows for Apache Airflow](https://aws-oss.beachgeek.co.uk/1et) from the lovely Naseer Ahmed and Igor Alekseev of Databricks. The posts dives into how to leverage Databricks’ jobs API with Amazon Managed Apache Airflow (MWAA), integrating with AWS Cloudwatch to monitor Directed Acyclic Graphs (DAG) with Databricks-based tasks. [hands on]

![architecture](https://databricks.com/wp-content/uploads/2022/01/orchestrating-databricks-workloads-with-managed-workflows-blog-1.jpg)

**Karpenter**

Karpenter is a dynamic, high performance cluster auto scaling solution for the Kubernetes platform introduced at re:Invent 2021. In the post, [Using Amazon EC2 Spot Instances with Karpenter](https://aws-oss.beachgeek.co.uk/1ex) Raja Ganesan and Aldred Halim look at how to use Karpenter with EC2 Spot Instances and handle Spot Instance interruptions. [hands on]

![graph diagram](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2022/02/25/spot-instances.jpg)

**Kubeflow**

I hope you enjoy this post, [Building a multi-tenant Kubeflow environment on Amazon EKS using Amazon Cognito and ADFS](https://aws-oss.beachgeek.co.uk/1es) from Jose Alfredo de Castro Nunes, Krithivasan Balasubramaniyan, and Rumeshkrishnan Mohan, which I enjoyed testing. This detailed walk through will help you understand the key components of how to deploy Kubeflow on Amazon Elastic Kubernetes Service (Amazon EKS) and how to achieve multi-user isolation using Amazon Cognito and ADFS. One up and running, you will be able to log in via your federated identity, and access your own tenant Kubeflow environment. [hands on]

![demo](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2022/02/14/Kubeflow-1.png)

**Observability**

Ramesh Mathikumar, Gabriel Soto, and Vara Bonthu have collaborated on this post, [Monitoring Amazon EMR on EKS with Amazon Managed Prometheus and Amazon Managed Grafana](https://aws-oss.beachgeek.co.uk/1ew) where you will  build (via Terraform) an end-to-end observability solution for EMR on EKS Spark workloads by leveraging Amazon Managed Service for Prometheus to collect and store the metrics generated by Spark Applications. You will then use Amazon Managed Grafana to build dashboards for monitoring use cases. Source code provided. [hands on]

![arch solution](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2022/02/14/fig1zuc.png)

**PostgreSQL**

Financial services industry (FSI) customers and other highly regulated industries often need to audit every action made by each database user and administrator as well as identify each person logged in to their databases, usually using their identity provider (IdP). Mattia Berlusconi and Paola Lorusso have written, [Auditing for highly regulated industries using Amazon Aurora PostgreSQL](https://aws-oss.beachgeek.co.uk/1er), to share how a proactive solution to a common security challenge for highly regulated industries and describe how to incorporate security best practices for auditing and monitoring users’ actions on data stored in Amazon Aurora PostgreSQL-Compatible Edition. [hands on]

![solution architecture diagram](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2022/02/28/Bpost20220217-1.png)

**OpenFOAM**

OpenFOAM is a widely used open source Computational Fluid Dynamics (CFD) suite of software tools. In the post, [Getting the best OpenFOAM Performance on AWS](https://aws-oss.beachgeek.co.uk/1f1), Neil Ashton helps you explore six practical things you can do as an OpenFOAM user to run your simulations faster and more cost effectively on AWS.

![graphs](https://d2908q01vomqb2.cloudfront.net/e6c3dd630428fd54834172b8fd2735fed9416da4/2022/02/25/hpcblog-14-fig3.png)

**AutoGluon**

AutoGluon is an open-source library for AutoML for text, image, and tabular data, allowing you to produce highly accurate models from raw data with just one line of code. In the post, [Build a cold start time series forecasting engine using AutoGluon](https://aws-oss.beachgeek.co.uk/1fh) Ivan Cui, Jonas Mueller, and Wenming Ye collaborate on how to build a cold start forecasting engine. Cold start forecasting, is where you build forecasts for a time series that has little or no existing historical data, such as a new product that just entered the market in the retail industry. [hands on]

![graph of timeseries](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2022/02/18/ML-7552-image001.png) 

**Other posts worth checking out**

* [Preparing ROS application and simulation containers for AWS RoboMaker](https://aws-oss.beachgeek.co.uk/1eu)  shows you how to use containers to build and package Robot Operating System (ROS) applications to run in AWS RoboMaker
*  [Three things to consider when implementing Mutual TLS with AWS App Mesh](https://aws-oss.beachgeek.co.uk/1f2) helps you understand which questions you should ask before implementing mutual TLS with AWS App Mesh for containerised workloads
*  [Migrate On-Premises Multi-Tenant Systems to Amazon Elastic Kubernetes Service](https://aws-oss.beachgeek.co.uk/1ev) explores how you can use Amazon EKS to enable multi-tenant systems using containers to simplify their operation, optimise cost, improve segmentation, security, and increase availability/scalability

![arch](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2022/02/23/fig7wc.jpg)

* [New Amazon RDS for MySQL & PostgreSQL Multi-AZ Deployment Option: Improved Write Performance & Faster Failover](https://aws-oss.beachgeek.co.uk/1ey) looks at the new Amazon RDS Multi-AZ deployment option with up to 2x faster transaction commit latency that can automate fail overs typically to under 35 seconds
* [Automate PostgreSQL log exports to Amazon S3 using extensions](https://aws-oss.beachgeek.co.uk/1ez) provides examples of how you can use the PostgreSQL extensions and automate the export of PostgreSQL logs directly to Amazon S3
* [Migrate from Amazon RDS for Oracle to Aurora PostgreSQL or Amazon RDS for PostgreSQL using this self-service guide](https://aws-oss.beachgeek.co.uk/1f3) should be on your reading list if you are looking to migrate onto PostgreSQL
* [Migrate from SQL Server to Aurora PostgreSQL using SSIS and Babelfish](https://aws-oss.beachgeek.co.uk/1f6) shares how to migrate a large SQL Server database to Aurora PostgreSQL using SSIS and Babelfish
* [How Panasonic Avionics used Amazon Aurora MySQL to modernize their environment](https://aws-oss.beachgeek.co.uk/1f5) is a good case study and technical overview of how this customer were able to improve the scalability and resiliency of their applications

### Whitepapers

[Patterns for Ingesting SaaS Data into AWS Data Lakes](https://aws-oss.beachgeek.co.uk/1eo) is a new white paper that outlines different patterns using Amazon Web Services (AWS) services to ingest SaaS data into a data lake on AWS. It covers a number of different patterns, including how you can use Apache Spark, Apache Kakfa, and Amazon Athena Federated Queries.


### Quick updates

**MySQL**

The AWS JDBC Driver for MySQL is an open-source project that uses the General Public License v2 and is now generally available for use with your Amazon RDS or Amazon Aurora MySQL-compatible edition database clusters. This database driver minimises failover time by monitoring database cluster status and caching the cluster’s topology. The cache is then used to improve DNS name resolution speed if a node fails, reducing failover time from minutes to seconds. The MySQL JDBC driver is based on the MySQL Connector/J and supports MySQL deployments. It is drop-in compatible with the community MySQL driver and is installed with Maven, Gradle, or by .jar file. After installing the required file, your client requires simple changes to the connection string to use the new driver.

You can dive deeper in the blog post, [Improve application availability with the AWS JDBC Driver for Amazon Aurora MySQL](https://aws-oss.beachgeek.co.uk/1f0) where Ryan Shevchik demonstrate how to use the AWS JDBC Driver for MySQL, and how your application can take advantage of the features of clustered MySQL databases.

**PostgreSQL**

Following the announcement of updates to the PostgreSQL database by the open source community, AWS has updated Amazon Aurora PostgreSQL-Compatible Edition to support PostgreSQL versions 13.5, 12.9, 11.14, and 10.19 in commercial and AWS GovCloud (US) Regions. These releases contain bug fixes and improvements by the PostgreSQL community. 

**Apache Cassandra**

Amazon Keyspaces (for Apache Cassandra) is a fully managed Apache Cassandra compatible database service now helps you automate resource management by using the AWS SDK. Amazon Keyspaces helps you to run Apache Cassandra workloads more easily at scale by using a fully managed and serverless database service. Amazon Keyspaces works with your existing Cassandra drivers and Cassandra Query Language (CQL) API code. In addition, Amazon Keyspaces is integrated with AWS CloudFormation to help you automate provisioning and management of Amazon Keyspaces resources, such as keyspaces and tables. You also can use CloudFormation to manage encryption and point-in-time recovery (PITR) settings. Now, you also can create and manage Amazon Keyspaces resources by using the AWS SDK. AWS SDK support also allows you to use third-party automation tools that depend on the AWS SDK to manage your AWS resources.

**Apache Kafka**

You can now use AWS CloudFormation to manage Amazon Managed Streaming for Apache Kafka (MSK) cluster configurations and SASL/SCRAM secrets. 

**OpenZFS**

With the introduction of LZ4 data compression, you can now choose from two different compression options on Amazon FSx for OpenZFS file systems. LZ4 provides another highly popular performance-optimised compression option (in addition to Z-Standard) to help you optimise storage efficiency and performance based on the needs of your individual workloads.

Amazon FSx for OpenZFS provides fully managed, cost-effective, shared file storage powered by the popular OpenZFS file system. It offers powerful storage efficiency capabilities like data compression, enabling you to reduce storage consumption of the data in both your file system and your file system backups. Until today, FSx for OpenZFS file systems only supported Z-Standard compression, which is optimised for the highest levels of storage efficiency and is well-suited for a broad set of general purpose workloads. Now, you can also choose LZ4 data compression, which is optimised for delivering higher levels of write throughput for your performance-intensive write-heavy workloads.

Starting today, you can enable data compression and choose LZ4 as the compression algorithm using the AWS Console, AWS CLI, or FSx API.

### Videos of the week

**Terraform**

Check out the second of a series of "Learning Live with AWS & HashiCorp" videos featuring our own Jenna Pederson and J. Cole Morrison from HashiCorp. In this episode they'll create their first micro service. I highly recommend this series, you get to learn more than just how to use Terraform to build AWS infrastructure - this week, I learned about "ClickOps"!

{{< youtube imppNTvnM18 >}}

**O3DE**

Open 3D Engine (O3DE) is a modular, open-source, cross-platform 3D engine built to power anything from AAA games to cinema-quality 3D worlds to high-fidelity simulations. Join Amar Mehta who provides an overview of O3DE and explores more about why this project matters to our developers, customers and partners.

{{< youtube _FbEJU8b8s8 >}}

**Amazon EC2: Nitro System Support for Previous Generation Instances**

Principal Hypervisor Engineer speaker, Paul Durrant, dives into the Nitro System; reviewing it's design & architecture, exploring new innovations to the platform, and demonstrating how it's implementation has made the seemingly impossible, possible and how we are enabling workloads that depend on Xen interfaces to run on the Nitro system.

{{< youtube PoenOPLX3ic >}}

### Events for your diary

If you have an event you want me to publish here, please contact me and I will include it in this listing. 

**FIPS Enabled Ubuntu Pro on AWS**
**March 8th, 5PM GMT**

This webinar looks at Ubuntu Pro with FIPS and additional security controls to provide at a higher level for agencies or missions to help you meet your security and compliance requirements. The session will also include a demo that shows how easy it is to start securing the Ubuntu Operating System within the AWS cloud.

[Review the full details and sign up here](https://aws-oss.beachgeek.co.uk/1eq).


**Unifying data pipelines and ML with Delta Lake and Amazon SageMaker**
**March 8th, 9am PT**

Join this live workshop event to learn about the best practices for enterprises to use with powerful open source technologies to simplify and scale your data and ML efforts. We’ll discuss how to leverage Apache Spark™ — the de facto data processing and analytics engine for data preparation that unifies data at a massive scale across various sources — and Delta Lake so you can make your data lake ML-ready.

Find out more and [register here](https://aws-oss.beachgeek.co.uk/1el).

**Building an Open Data Lakehouse with Presto, Hudi, and AWS S3**
**March 29th, 10am PT**

In this 90 minute hands on-virtual lab that will walk you through how to build an Open Data Lakehouse stack with Presto, Apache Hudi, and AWS S3.

If you want to learn more about these open source projects, this looks like the perfect opportunity. Check it out and [register on their registration page](https://aws-oss.beachgeek.co.uk/1ep).

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