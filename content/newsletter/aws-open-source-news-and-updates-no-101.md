---

title: 'AWS open source news and updates #101'
date: '2022-02-21'
tags : [ oss-newsletter, aws open source, Apache Log4J, Formik, AWS CDK, QUIC, s2n-quic, Apache Airflow, AWS Amplify, Syne Tune, Apollo Server, Amazon EKS, PostgreSQL, Apache Hudi, Terraform, CloudQuery, RabbitMQ, MariaDB, GitOps, Flux ]

---

## Feb 21st, 2022 - Instalment #101

Newsletter #101. 

There is nothing basic and fundamental about edition 101 of the AWS open source newsletter, with another great round up of new open source projects including eks-creation-engine from the folks at Lightspin helping you all to stay safer with this handy tool you should check out, idp-scim-sync to help users of AWS SSO who want to synchronise with their Google Workspace Directory, typecart an analysis tool for proof evolution and many other great projects and sample code. If reading is more your thing, then catch up on the latest posts covering topics such as Apache Log4J, Formik, AWS CDK, QUIC, Apache Airflow, AWS Amplify, Syne Tune, Apollo Server, Amazon EKS, PostgreSQL, Apache Hudi, Terraform, CloudQuery, RabbitMQ, MariaDB, and many more. We have a nice video presented from the lovely folk at Weaveworks and of course, the latest events and meet ups to attend.

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Panos Kampanakis, Tim Shear, Matt Auerbach, Danilo Poccia, Olivier Cruchant, David Salinas, Andrew Guthrie, Matthias Seeger, Markus Ziller, David Boldt, Adam McQuistan, Kevin Rivera, Mark Carlson, Shruti Arora, Britney Tong, Balaji Varadarajan, Yevgeny Pats, Jonathan Rau, and Matt Badger.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest open source projects

#### Community

**idp-scim-sync**

[idp-scim-sync](https://aws-oss.beachgeek.co.uk/1df) this open source tool from SlashDevOps will help you keep your AWS Single Sign-On (SSO) groups and users in sync with your Google Workspace directory.

![arch](https://raw.githubusercontent.com/slashdevops/idp-scim-sync/main/docs/images/diagrams/ipd-scim-sync.drawio.png)

**eks-creation-engine**

[eks-creation-engine](https://aws-oss.beachgeek.co.uk/1dc) The Amazon Elastic Kubernetes Service (EKS) Creation Engine (ECE) is a Python command-line program created by the Lightspin Office of the CISO to facilitate the creation and enablement of secure EKS Clusters. Jonathan Rau has put together this post, [Why Create an EKS Creation Tool?](https://aws-oss.beachgeek.co.uk/1dd) that provides a great outline of not just the rational and motivation for putting this tool together, but also provides some good examples of how to use the tool and shares what the future holds. As Jonathan likes to say, "Stay Dangerous"...reading this post is your first step!

**terraform-aws-ecr-public**

[terraform-aws-ecr-public](https://aws-oss.beachgeek.co.uk/1dg) this is a Terraform Module to manage Public Docker Container Registries on AWS ECR

#### Tools

**typecart**

[typecart](https://aws-oss.beachgeek.co.uk/1dn) typeCart is an analysis tool for proof evolution to facilitate proof maintenance for continuously integrated software. typeCart is constructed in F# and it reads two Dafny files into Dafny AST, analyses the ASTs to identify syntactically equivalent types between them, and
generates mapping functions between equivalent types. (Dafny is a programming language with built-in specification constructs, and the Dafny static program verifier can be used to verify the functional correctness of programs). If you are interested in reading more about formal reasoning and how it is used within AWS, may I be bold enough to suggest this great paper from Byron Cook, [Formal reasoning about the security of Amazon Web Services](https://aws-oss.beachgeek.co.uk/1do)

**aws-cloudwatch-monitoring**

[aws-cloudwatch-monitoring](https://aws-oss.beachgeek.co.uk/1dh) this repository provides a time-series monitoring and visualisation for PrivateLink connections using CloudWatch Contributor Insights automation. The provided CloudFormation templates sets up custom Amazon CloudWatch dashboards, Amazon CloudWatch metrics, and Amazon CloudWatch alarms based on Contributor Insights rules. These rules monitor several aspects of PrivateLink connections such as bytes transferred by source and destination IP address, traffic by source address and action or top sources for rejected TCP connections. You can modify the solution to add additional/custom rules.

![arch](https://raw.githubusercontent.com/aws-samples/aws-cloudwatch-monitoring/main/images/vpcprivatelink.PNG)

**amazon-chime-sdk-meetings-load-test**

[amazon-chime-sdk-meetings-load-test](https://aws-oss.beachgeek.co.uk/1dj) this open source project will be handy for customers using Amazon Chime. This tool simulates real attendees by launching Amazon Chime SDK for Javascript (Amazon Chime SDK for JS) clients and enabling them to join meetings and control the features of the meeting. The tool can be helpful if you wish to simulate attendees in a meeting and/or test multiple scenarios to see how the app built on Amazon Chime SDK for JS behaves for larger loads.

**green-boost**

[green-boost](https://aws-oss.beachgeek.co.uk/1dl) Build Full Stack Serverless Web Apps on AWS quickly with this repo. Green Boost is a framework for boosting development of greenfield web apps on AWS, and you can view the detailed docs [here](https://aws-oss.beachgeek.co.uk/1dm).

#### Demos and Samples

**react-formik-on-aws**

[react-formik-on-aws](https://aws-oss.beachgeek.co.uk/1d2) Formik is a popular open source form library for React and React Native, and this repo will show you how you can deploy this on AWS using AWS CDK. To help you get going, read the post [Deploying Sample UI Forms using React, Formik, and AWS CDK](https://aws-oss.beachgeek.co.uk/1d3) from Kevin Rivera, Mark Carlson, Shruti Arora, and Britney Tong

![arch](https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2022/02/15/Figure2-DownloadFileX.png)

**aws-legal-entity-extraction**

[aws-legal-entity-extraction](https://aws-oss.beachgeek.co.uk/1di) this repository is used to demonstrate how users can use AWS Comprehend to automate processing of Insurance Claims Legal Letters.

![arch](https://github.com/aws-samples/aws-legal-entity-extraction/blob/main/architecture.png?raw=true)

**scanned-documents-to-speech**

[scanned-documents-to-speech](https://aws-oss.beachgeek.co.uk/1dk) This project provides an end-to-end solution that converts scanned documents/images to speech, and reads back to user.

![arch](https://github.com/aws-samples/scanned-documents-to-speech/blob/main/architecture.png?raw=true)

### AWS and Community blog posts

**CloudQuery**

CloudQuery is an open source project that enables you to extract, transform, and load your cloud assets into normalised PostgreSQL tables. With this you can then assess, audit, and monitor the configurations of your cloud assets. In his post, [Our Open-Source Journey Building CloudQuery](https://aws-oss.beachgeek.co.uk/1db) Yevgeny Pats shares why they started CloudQuery as an open-source cloud asset inventory, and then takes a look at some of their products and they technical decisions they made along the way.

**QUIC**

QUIC is an encrypted transport protocol designed for performance and is the foundation of HTTP/3. In the post
[Introducing s2n-quic, a new open-source QUIC protocol implementation in Rust](https://aws-oss.beachgeek.co.uk/1cw), Panos Kampanakis announces the availability of s2n-quic, an open-source Rust implementation of the QUIC protocol added to our set of AWS encryption open-source libraries. Make sure you check it out, this weeks must read post.

**Apache Log4J**

In his post New for [Amazon CodeGuru Reviewer – Detector Library and Security Detectors for Log-Injection Flaws](https://aws-oss.beachgeek.co.uk/1d4), Danilo Poccia shares some nice new capabilities within Amazon CodeGuru that allows you to set up detectors that can help you detect if you’re logging anything that is not sanitised and possibly executable. These detectors work with Java and Python code and, for Java, are not limited to the Log4j library. Nice post and a must read this week.

![demo](https://d2908q01vomqb2.cloudfront.net/da4b9237bacccdf19c0760cab7aec4a8359010b0/2022/01/24/codeguru-detector-log-injection-1024x917.png)

**Apache Airflow**

This is a really nice post from Tim Shear, that takes a look at how you can migrate from mainframe CA7 job schedules to Apache Airflow. CA7 is a job scheduling and workflow automation solution that is popular in this space. The post covers everything you need to think about if this is a use case that fits your situation. Find out more by reading the full post, [Migrate from mainframe CA7 job schedules to Apache Airflow in AWS](https://aws-oss.beachgeek.co.uk/1d0)

![arch](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2022/02/16/scheduler0216.png)

**Terraform**

We had another Apache Airflow related post, this time from Matt Badger who shares how they use the Snowflake Terraform provider to automate the process of creating S3 bucket notifications, and Snowflake stages, pipes and tables for automatically loading data into Snowflake, orchestrated via Apache Airflow. Find out more by reading his post, [Terraforming Snowpipe](https://aws-oss.beachgeek.co.uk/1de)

**Apache Hudi**

Really loved this post, [Fresher Data Lake on AWS S3](https://aws-oss.beachgeek.co.uk/1da) from Balaji Varadarajan over in the Robinhood engineering team. In this post he shares their journey in building a Change Data Capture solution using various open source tools to reduce the data freshness latency for our core datasets from one day to under 15 minutes. Another must read post this week.

![arch](https://miro.medium.com/max/1400/0*fjZvRqENVxE_vvkI)

**PostgreSQL**

Adam McQuistan explores some of the advantages you might see building observability into your AWS Aurora PostgreSQL environments in his post, [Aurora PostgreSQL Slow Query Logging and CloudWatch Alarms via AWS CDK](https://aws-oss.beachgeek.co.uk/1d9). Adam provides source code in his repo so you can follow along. [hands on]

![arch](https://thecodinginterface-images.s3.amazonaws.com/blogposts/aurora-postgres-slow-queries/aurora-postgres-slow-query-log.jpg)

**Syne Tune**

Syne Tune is a parameter search and optimisation library that I shared news about this project a few weeks ago, and we now have a nice blog post that dives deeper into how you can use this project in [Learn Amazon Simple Storage Service transfer configuration with Syne Tune](https://aws-oss.beachgeek.co.uk/1d5). Olivier Cruchant, David Salinas, Andrew Guthrie, and Matthias Seeger provide an example of how you can use this open source library to (in this example) search and learn a configuration for S3 Transfer that is optimised for a specific use case. [hands on]

**Apollo Server**

Markus Ziller and David Boldt share how you can use Apollo Server on AWS Lambda in an event-driven architecture in their blost post, [Using Apollo Server on AWS Lambda with Amazon EventBridge for real-time, event-driven streaming](https://aws-oss.beachgeek.co.uk/1d8) [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2022/02/07/apollo-lambda-blog1.jpg)

**AWS Amplify**

The AWS Amplify have been focused on making it easier to contribute to their open source project. Earlier this year, theu launched the Amplify Contributor Bash, an initiative to drive more awareness to Amplify’s open source program. Find out more by reading Matt Auerbach's post [Amplify Bash: Get Started Contributing to AWS Amplify Open Source](https://aws-oss.beachgeek.co.uk/1cz)

**Other posts worth checking out**

* [NEW in AWS Amplify Flutter version 0.4.0](https://aws-oss.beachgeek.co.uk/1cv) provides a high level breakdown of the features we are announcing with Amplify Flutter version 0.4.0
* [Introducing Amazon CloudWatch Container Insights for Amazon EKS Fargate using AWS Distro for OpenTelemetry](https://aws-oss.beachgeek.co.uk/1cx) looks at the design of components in an ADOT Collector pipeline that enables the collection of Container Insights metrics from EKS Fargate workloads

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2022/01/31/ADOT-Blog-1.png)

* [Running WDL workflows at scale with Amazon Genomics CLI and MiniWDL](https://aws-oss.beachgeek.co.uk/1cy) announces the addition of miniWDL as a workflow engine in Amazon Genomics CLI, an open source tool that makes it easier to run genomics workflows at-scale by automating the deployment of workflow engines and compute clusters

![arch](https://d2908q01vomqb2.cloudfront.net/c5b76da3e608d34edb07244cd9b875ee86906328/2021/11/01/CLI-miniWDL-pic-2.jpg)

* [Migration options for MySQL to Amazon RDS for MySQL or Amazon Aurora MySQL](https://aws-oss.beachgeek.co.uk/1d1) helps you understand the different options to migrate data from a self-managed MySQL database to AWS-managed Amazon RDS for MySQL or Aurora MySQL
* [How To Expose Multiple Applications on Amazon EKS Using a Single Application Load Balancer](https://aws-oss.beachgeek.co.uk/1d7) shows the different ways to approach a microservices architecture within AWS, demonstrating hands on how to implement using Amazon EKS with a single Application Load Balancer

### Quick updates

**AWS SDKs**

The default configuration in the AWS SDK for Java v2 just got smarter! We are pleased to announce a new SDK feature —⁠ smart configuration defaults in the AWS SDK for Java v2 (version 2.17.102 or later), which vends a set of predefined sensible default values tailored to common usage patterns. With this new opt-in feature, you will get an optimized SDK client out-of-box with configuration already tuned to adhere to AWS SDK best practices. This feature is also available in the AWS SDK for .NET, JavaScript v3, Ruby v3, Go v2 , Python and PHP. In this post, we will explain the feature and show you how to leverage it in the AWS SDK for Java v2. Read more in the detailed post, [Introducing Smart Configuration Defaults in the AWS SDK for Java v2](https://aws-oss.beachgeek.co.uk/1d6)

**MariaDB**

Amazon Relational Database Service (Amazon RDS) for MariaDB now supports delayed replication, allowing you to set a configurable time period by which a read replica lags behind the source database. In a standard MariaDB replication configuration, there is minimal replication delay between the source and the replica. With delayed replication, you can introduce an intentional delay as a strategy for disaster recovery.

A delay can be helpful when you want to recover from a manual error. For example, if someone accidentally drops a table from your primary database, you can stop the replication just before the point at which the table was dropped and promote the replica to become a standalone instance. To assist with this process, Amazon RDS for MariaDB now includes a stored procedure that will stop replication once a specified point in the binary log is reached.

**RabbitMQ**

Amazon MQ now provides support for RabbitMQ version 3.9.13. This update to RabbitMQ contains several fixes and enhancements compared to the previously supported version, RabbitMQ 3.8.26.

### Videos of the week

**GitOps with Amazon EKS Anywhere + Flux**

Amazon EKS Anywhere is an open-source tool which helps you create and manage Kubernetes clusters on-premises. EKS Anywhere allows you to manage your Kubernetes clusters in a scalable and declarative manner with the help of GitOps, powered under-the-hood with CNCF Flux. Introduced by Stacey Potter, Community Manager at Weaveworks,  Dan Budris shares how EKS Anywhere integrates with Flux and uses GitOps workflows to manage the cluster lifecycle.


{{< youtube U2n3oYuIIfc >}}

### Events for your diary

If you have an event you want me to publish here, please contact me and I will include it in this listing. 


**AWS | Databricks ML Dev Day Workshop**
**24 February, 9am – 11:30am GMT**

In this workshop you will get to learn about the current good practices for enterprises to use with powerful open source technologies to simplify and scale your data and ML efforts. Covering Delta Lake, Apache Spark, TensorFlow, XGBoost, scikit-learn and MLFlow, a lot of stuff is going to be covered so read the full details and register at [AWS | Databricks ML Dev Day Workshop](https://databricks.com/p/webinar/feb-2022-emea-aws-databricks-ml-dev-day-workshop)

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