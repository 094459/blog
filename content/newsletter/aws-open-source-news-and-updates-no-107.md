---

title: 'AWS open source news and updates #107'
date: '2022-04-04'
tags : [ oss-newsletter, aws open source, Kubernetes, PostgreSQL, Magma, Apache Airflow, MWAA, Apache Flink, Apache Kafka, Apache Hive, OpenZFS, AWS CDK, Karpenter, Replibyte, Apache Hadoop, Medusa, cdk8s, OpenSearch, Projen, Spline, Blazor, ]

---

## April 4th, 2022 - Instalment #107

Newsletter #107. 

Welcome to edition #107 of the AWS open source newsletter, and we have a bumper edition this week packed with more great new open source projects and content for you to consume. Topics featured this week include optimising open source big data tools, developer tooling, case studies and we even some some great open source content for .NET core developers.

This weeks projects include a really nice handy browser plugin called "aws-search-extension", that lets you search and find developer information from the AWS docs, a tool that will help you detect whether you have configured or using dockershim in your Kubernetes clusters, a library to help you integrate Amazon Cognito in your Laravel PHP applications, and plenty more developer tools and sample projects.

If reading is more your thing, check out the content featuring Kubernetes, PostgreSQL, Magma, Apache Airflow, Apache Flink, Apache Hive, OpenZFS, Karpenter, Apache Hadoop, Medusa, cdk8s, OpenSearch, Projen, Spline, and more. This weeks video feature a quick walk through of using RepliByte and looking at your options of using Blazor on AWS.



**Do you have an interesting open source project you want to share?**

As always, if you are working on anything interesting you would like me to include in this weekly round up, please drop me a line at ricsue@amazon.com.


### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Ualter Otoni Pereira, Noam Dahan, Martin Andreev, Carlos Padilla, Romaric Philogène, Michael Brewer, Pit, Julio Faerman, Jens-Uwe Walther, Jesse Butler, David Pérez Caparrós, Alexander Hobmeier, Benjamin Maier-Fuchs, Rabi Abdel, Praveen Kumar, Avnish Jain, Praveen Panati, Suthan Phillips, Aditya Shah, Syed Shameerur Rahman, Gowtham S, Abhishek Nanda, Anurag Gupta, Philip M. Gollucci, Khoa Nguyen, Krithivasan Balasubramaniyan, Francois Bouteruche, and Rahul Shaurya.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest open source projects

#### Community

**awsbe-site**

[awsbe-site](https://aws-oss.beachgeek.co.uk/1k0) AWS Community Builder Ualter Otoni Pereira has created this tool written in Go, to help handle AWS Session connections on terminals. It uses your configured AWS Shared Config and Credentials files, and manages Roles to Assume, MFA Token requests, AWS SSO Sign-in, AWS SSO Tokens and the expiration of opened sessions.

![demo of awsbe-site tool](https://github.com/ualter/awsbe-site/blob/master/docs/img/gif_04.gif?raw=true)

**aws-lambda-events**

[aws-lambda-events](https://aws-oss.beachgeek.co.uk/1it) this open source tool from AWS Community Builder Michael Brewer, provides a collection of resources and tools on the different input and outputs that AWS Lambda expects. You can use this tool to publish your locally defined test events to the Lambda Console, and the project has 100s of different examples and [cli tools with examples](https://aws-oss.beachgeek.co.uk/1iu) to help get you started.

**task-tree**

[task-tree](https://aws-oss.beachgeek.co.uk/1iv) this new tool from my friend and former colleague Julio Faerman, looks to help you automate complex maintenance and troubleshooting tasks in cloud computing. One of the things this tool can help you with is to cleanup AWS resources based on a naming prefix. Julio warmly welcomes any contributions and has provided a wish list of things he wants to add to this project.

**aws-search-extension**

[aws-search-extension](https://aws-oss.beachgeek.co.uk/1is) so I missed this project from Pit, but thanks to the AWS Community Builders who shared this project in our Slack channel. This is a browser plugin that provides a search-extension, providing quick, fuzzy-search results for AWS developers. Includes AWS API, AWS CLI and AWS CloudFormation references, and opens the official AWS documentation page when you select an item. Looks like it is compatible with most browsers (but I only tried with Chrome/Firefox). Once you have it installed, from the tab just type in "ase" and then space, and you will see a new search bar appear. Very nice.

![demo of plugin](https://github.com/pitkley/aws-search-extension/blob/main/docs/demo.gif?raw=true)

#### Tools

**kubectl-detector-for-docker-socket**

[kubectl-detector-for-docker-socket](https://aws-oss.beachgeek.co.uk/1jx) this tool will help you detect whether you are using the dockershim that is being removed from Kubernetes 1.24. It is a kubectl plugin to detect if active Kubernetes workloads are mounting the docker socket (docker.sock) volume.

![demo of kubectl detector tool](https://github.com/aws-containers/kubectl-detector-for-docker-socket/blob/main/img/dds-demo.gif?raw=true)

**nestjs-s3**

[nestjs-s3](https://aws-oss.beachgeek.co.uk/1jr) NestJS is an AWS S3 library allows you to use the AWS SDK v3 in a more friendly and familiar way by providing injectable services for managing things like buckets and objects. There is a great write up from Martin Andreev on the backstory for this project, so make sure you read [NestJS AWS S3 – From an idea to reality](https://aws-oss.beachgeek.co.uk/1js).

**Slyther**

[Slyther](https://aws-oss.beachgeek.co.uk/1jt) this open source tool from Avantika is AWS Security tool to check read/write/delete access for S3 buckets.

**aws-cognito**

[aws-cognito](https://aws-oss.beachgeek.co.uk/1ji) this package provides a simple way to use AWS Cognito authentication in Laravel 7.x for Web and API Auth Drivers. Check out the demo application and nice examples and documentation of how to use it within your PHP/Laravel projects.

#### Demos and Samples

**aws-do-pm**

[aws-do-pm](https://aws-oss.beachgeek.co.uk/1jm) this sample repository is an all-in-one template for building a predictive modelling application, built on the Do framework (a prescriptive project structure and a set of simple management scripts for building and running your application). The example walks you through modeling Electric Vehicles (EVs) and covers the process of building, running, and scaling a demo application step by step, starting from a fresh clone of the aws-do-pm repository to building and automatically deploying continuously updating predictive models for a fleet of Electric Vehicles using Artificial Neural Networks, trained by PyTorch.

![demo of predictive model for e](https://github.com/aws-samples/aws-do-pm/blob/main/docs/img/aws-do-pm-graph-slideshow.gif?raw=true)

**amazon-mwaa-extract-metadata**

[amazon-mwaa-extract-metadata](https://aws-oss.beachgeek.co.uk/1jn) This repository contains sample code for persisting and analyzing metadata in a transient Amazon MWAA environment. Storing this metadata in your data lake enables you to better perform pipeline monitoring and analysis. You can dive deeper into this by reading the blog post below on how you can use this project.

![architecture for mwaa extraction of metadata](https://github.com/aws-samples/amazon-mwaa-extract-metadata/blob/main/images/solution-architecture.png?raw=true)

**aws-apprunner-netcore**

[aws-apprunner-netcore](https://aws-oss.beachgeek.co.uk/1jz) this project and detailed walk through will show you how you can build a Microsoft.NET Web API application with Amazon Aurora Database using AWS App Runner. This is the architecture you will build.

![architecture of dotnet on App Runner](https://raw.githubusercontent.com/aws-samples/aws-apprunner-netcore/main/aws-apprunner-net-core-rds.png)

**s3-bucketkey-poc**

[s3-bucketkey-poc](https://aws-oss.beachgeek.co.uk/1jp) this is an intriguing project. S3 Bucket Key Proof of concept (POC) will demonstrate how request traffic decreases (up to 99%) from Amazon S3 to AWS KMS when you enable the S3 Bucket Key. Amazon S3 Bucket Keys reduce the cost of Amazon S3 server-side encryption using AWS Key Management Service (SSE-KMS). This new bucket-level key for SSE can reduce AWS KMS request costs by up to 99 percent by decreasing the request traffic from Amazon S3 to AWS KMS.


**sigv4a-signing-examples**

[sigv4a-signing-examples](https://aws-oss.beachgeek.co.uk/1jl) AWS is rolling out an extension to SigV4 called Signature Version 4A (SigV4A). This extension enables signatures that are valid in more than one AWS Region. This is required for signing multi-Region API requests, for example with Amazon S3 Multi-Region Access Points. This repository servers to provide examples how to sign requests with SigV4A to make Rest API requests to AWS services. Currently there are samples for Python, Node and Java, with more coming.

**cloudfront-signed-cookie-example**

[cloudfront-signed-cookie-example](https://aws-oss.beachgeek.co.uk/1jk) this is a sample project that provisions a serverless web app protecting cached assets in CloudFront by using signed cookie.

![architecture for signed cookie sample](https://github.com/aws-samples/cloudfront-signed-cookie-example/blob/main/docs/images/architecture.png?raw=true)

**aws-elastic-beanstalk-hardened-security-cdk-sample**

[aws-elastic-beanstalk-hardened-security-cdk-sample](https://aws-oss.beachgeek.co.uk/1jo) if you use AWS Elastic Beanstalk then this project is for you. The repo contains a CDK script which deploys an AWS Elastic Beanstalk application with a hardened security configuration.

![architecture of hardened elastic beanstalk ](https://github.com/aws-samples/aws-elastic-beanstalk-hardened-security-cdk-sample/blob/main/pictures/architecture_diagram.png?raw=true)

**amazon-ivs-fitness-web-demo**

[amazon-ivs-fitness-web-demo](https://aws-oss.beachgeek.co.uk/1jq) I am not sure if this project is going to shake my personal fitness regime up a level, but who knows. This demo showcases how customers can use Amazon Interactive Video Service (IVS) to create live interactive fitness experiences, with a leaderboard and basic user interactions. You can check out some of the other IVS code samples and live demos incase you just want to see how they look first.

![demo of fitness app](https://github.com/aws-samples/amazon-ivs-fitness-web-demo/blob/main/fitness-demo.png?raw=true)

### AWS and Community blog posts

**Access Undenied**

In [#106](https://dev.to/aws/aws-open-source-news-and-updates-106-849) I shared a new open source tool called 
access-undenied-aws. This project from Ermetic received a lot of attention the tool parses your logs for AWS AccessDenied CloudTrail events, and then explains the reasons for them, and offers actionable remediation steps. I missed this blog post, [Access Undenied on AWS](https://aws-oss.beachgeek.co.uk/1ju) from Noam Dahan that provides a guided tour and shows you how you can use this tool. 

**RepliByte**

I introduced this project in [#103](https://dev.to/aws/aws-open-source-news-and-updates-103-2h73) which is a very nice open-source tool written in Rust to synchronise cloud databases and hide sensitive data. CEO of Qovery Romaric Philogène has put together this blog post, [How to seed your dev Postgres DB with your prod DB with RepliByte](https://aws-oss.beachgeek.co.uk/1jb) that shows you exactly how you can get started and use it, taking a quick look at some of the features with examples. Very nice project, so check this out. [hands on]

**Projen**

[projen](https://aws-oss.beachgeek.co.uk/1jh) is a very cool open source tool for developers to help them define and maintain complex project configuration through code. So I was very interested to read this post from AWS Community Builder Philip M. Gollucci , [Projen - External Project Types](https://aws-oss.beachgeek.co.uk/1jj) provides you with a very nice example use case and walk through of how you can use this project. Very nice and essential reading this week! [hands on]

**cdk8s**

AWS Community Builder Vu Dao has put together another great blog post for you, this time on cdk8s. Similar to AWS CDK in how it works, cdk8s is an open-source software development framework for defining Kubernetes applications and reusable abstractions using familiar programming languages. cdk8s apps synthesise into standard Kubernetes manifests which can be applied to any Kubernetes cluster. AWS Controllers for Kubernetes (ACK) is a tool that lets you directly manage AWS services from Kubernetes. Putting these two things together, Vu's post, [Use CDK8S To Create AWS Controllers for Kubernetes Custom Resources](https://aws-oss.beachgeek.co.uk/1je) shows you how you generate Kubernetes manifest of ACK using cdk8s typescript. [hands on]

**OpenSearch**

A couple of posts this weeks on OpenSearch.

The first came courtesy of the "only other newsletter you need in your life" :), [o11y.news](https://aws-oss.beachgeek.co.uk/1jf) (so hat tip to Michael!). In the post, Getting started with Fluent Bit and OpenSearch, Anurag Gupta provides a getting started guide on the OpenSearch plugin for Fluent Bit, and you will soon know how you can send logs to OpenSearch immediately from your Windows, Linux, Container, Mac, or Kubernetes environments. [hands on]

Following that we had the post, [Dejavu: The missing web UI for OpenSearch](https://aws-oss.beachgeek.co.uk/1jg) which takes a look at this popular data browser for Elasticsearch, and how with the latest 3.6.0 release, they have added first-class data browser support for OpenSearch as well. 

![demo screen of connecting to opensearch](https://cdn.hashnode.com/res/hashnode/image/upload/v1648477126056/pZhsufkak.png?auto=compress,format&format=webp)

**Medusa**

[Medusa](https://aws-oss.beachgeek.co.uk/1jc) is an open-source headless commerce engine that enables developers to create digital commerce experiences (think Shopify alternative). Carlos Padilla has put together this blog post, [Set up Open source Ecommerce in the cloud](https://aws-oss.beachgeek.co.uk/1jd), on how you can deploy this on AWS Elastic Beanstalk. Very nice walk through! [hands on]

**Karpenter**

Karpenter is a high-performance open source Kubernetes cluster autoscaler that can help you autoscale your groupless nodes by letting you schedule layered constraints using the Provisioner API. Karpenter also makes node upgrades easy through the node expiry TTL value ttlSecondsUntilExpired. In the post, [Managing Pod Scheduling Constraints and Groupless Node Upgrades with Karpenter in Amazon EKS](https://aws-oss.beachgeek.co.uk/1j8) , Gowtham S and Abhishek Nanda provide a walk through on how you can set this up. [hands on]

**Spline**

[Spline](https://aws-oss.beachgeek.co.uk/1jv) is a free and open-source tool for automated tracking data lineage and data pipeline structure in your organisation. The Spline agent for Apache Spark is a complementary module to the Spline project that captures runtime lineage information from the Apache Spark jobs. In the post, [Build data lineage for data lakes using AWS Glue, Amazon Neptune, and Spline](https://aws-oss.beachgeek.co.uk/1jw), Khoa Nguyen, Krithivasan Balasubramaniyan, and Rahul Shaurya walk you through three steps in building an end-to-end automated data lineage solution for data lakes: lineage capturing, modelling and storage and finally visualisation. [hands on]

![architecture of spline data lineage solution](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2022/03/10/BDB-1683-solution-architecture.jpg)

**Apache Airflow**

Praveen Kumar and Avnish Jain have collaborated on this great new blog post, [Persist and analyze metadata in a transient Amazon MWAA environment](https://aws-oss.beachgeek.co.uk/1iz). They provide a solution that will help you understand how to export, persist and analyse Airflow metadata in Amazon S3 enabling you to run and perform pipeline monitoring and analysis. There are several uses cases, including so you can spin down Airflow instances without losing operational metadata. [hands on]

![architecture of solution](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2022/03/28/BDB-1261-image033.jpg)

**Apache Flink**

In the post, [Use Amazon CodeGuru Profiler to monitor and optimize performance in Amazon Kinesis Data Analytics applications for Apache Flink](https://aws-oss.beachgeek.co.uk/1j1), Praveen Panati shares how you can set up and use CodeGuru Profiler to monitor an application’s health and capture important metrics to optimise the performance of Kinesis Data Analytics for Apache Flink applications. [hands on]

![flame graph of Apache Flink app](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2022/03/22/BDB-1746-image019.jpg)

**Apache Hive**

Apache Hive is a data warehouse software project built on top of Apache Hadoop for providing data query and analysis. In their collaboration, [Up to 15 times improvement in Hive write performance with the Amazon EMR Hive zero-rename feature](https://aws-oss.beachgeek.co.uk/1j6) Suthan Phillips, Aditya Shah, and Syed Shameerur Rahman explore how the Hive EMRFS S3-optimized committer improves write performance compared to the default Hive commit logic, using the TPCx-BB performance benchmark as a guide.

![graph of performance improvements in Apache Hive](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2022/03/17/SpeedUpVsDataSize.png)

**Magma**

Magma is an open-source, flexible, and extendable mobile core network solution. In a previous newsletter, I shared the post that showed you how you can setup and install this project on AWS. If you want to know how you can fully automate the deployment and lifecycle management of Magma on the AWS Cloud, then you are in luck! David Pérez Caparrós, Alexander Hobmeier, Benjamin Maier-Fuchs, and Rabi Abdel have huddled together to put together this post, [Fully automated CI/CD pipelines for deploying and managing Magma on AWS](https://aws-oss.beachgeek.co.uk/1j0). [hands on]

![architecture of CI/CD for Magma](https://d2908q01vomqb2.cloudfront.net/c5b76da3e608d34edb07244cd9b875ee86906328/2022/03/29/Figure-3.-Magma-automation-pipelines.png)

**Other posts worth checking out**

* [Enabling Amazon Simple Storage Service (Amazon S3) Access Points in Apache Hadoop S3A](https://aws-oss.beachgeek.co.uk/1j9) announce and show you how you can use Amazon S3 Access Points in Apache Hadoop 3.3.2 and any framework consuming the S3A connector or relying on the Hadoop Distributed File System (such as Apache Spark, Apache Hive, Apache Pig, and Apache Flink)
* [How to integrate AWS IoT Core with Amazon MSK](https://aws-oss.beachgeek.co.uk/1j2) will show you how you can set up AWS IoT Core to stream events to Amazon MSK [hands on]

![architecture of IoT streaming into Apache Kafka](https://d2908q01vomqb2.cloudfront.net/f6e1126cedebf23e1463aee73f9df08783640400/2022/03/23/iot-msk-diagram-e1648021578179-1024x461.png)

* [Deploy bastion hosts into private subnets with AWS CDK](https://aws-oss.beachgeek.co.uk/1j3) explains how to provision scalable and extendable secure bastion hosts in private subnets using AWS CDK [hands on]
* [Optimizing AWS Lambda function performance for Java](https://aws-oss.beachgeek.co.uk/1j4) shows how to optimise the performance of AWS Lambda functions written in Java, without altering any of the function code. [hands on]
* [Synchronize your Oracle databases quickly and easily with Amazon FSx for OpenZFS](https://aws-oss.beachgeek.co.uk/1j5) provides an overview of how you can use Amazon FSx for OpenZFS with Oracle Database running on Amazon EC2 to accelerate and optimise your database cloning process
* [Integrating with GitHub Actions – CI/CD pipeline to deploy a Web App to Amazon EC2](https://aws-oss.beachgeek.co.uk/1j7) shows you how you can setup GitHub Actions to create a CI/CD workflow and AWS CodeDeploy to deploy a sample Java SpringBoot application

**Case Studies**

* [How governments can use open source solutions for faster transformation and more](https://aws-oss.beachgeek.co.uk/1ja) looks at some of the ways open source is being used to drive transformation within the Government sector
* [Data Science workflows at insitro: using redun on AWS Batch](https://aws-oss.beachgeek.co.uk/1jy) interesting look at a new data science tool called redun from insitro, that helps data scientists to define complex scientific workflows that scale

### Quick updates

**Kubernetes**

Amazon Elastic Kubernetes Service (Amazon EKS) now supports using the Amazon EKS console, AWS Command Line Interface (CLI), and EKS API to install and manage the the Amazon Elastic Block Store (EBS) Container Storage Interface (CSI) driver. This launch enables a simple experience for attaching persistent storage to an EKS cluster. The EBS CSI driver provides a CSI interface used by container orchestrators to manage the lifecycle of Amazon EBS volumes. Since announcing preview, EKS add-ons support now includes Windows compatibility, dynamic snapshotting and resizing of EBS volumes via the Kubernetes API, and backwards compatibility with the in-tree EBS driver. The EBS CSI driver can be installed, managed, and updated directly through the EKS console, CLI, and API. You can see available add-ons and compatible versions in the EKS API, select the version of the add-on you want to run on your cluster, and configure key settings such as the IAM role used by the add-on when it runs. Using EKS add-ons you can go from cluster creation to running applications in a single command and easily keep tooling in your cluster up to date.

Jens-Uwe Walther and Jesse Butler have put together this blog post, [Amazon EBS CSI driver is now generally available in Amazon EKS add-ons](https://aws-oss.beachgeek.co.uk/1ix) dives deeper into this announcement, together with some of the historical and background of the project before demonstrating how to create an Amazon EBS CSI EKS add-on, using it in the context of a Kubernetes workload. [hands on]

**PostgreSQL**

Following the announcement of updates to the PostgreSQL database by the open source community, we have updated Amazon Aurora PostgreSQL-Compatible Edition to support PostgreSQL 13.6, 12.10, 11.15, and 10.20. These releases contain bug fixes and improvements by the PostgreSQL community. Refer to the Aurora version policy to help you to decide how often to upgrade and how to plan your upgrade process. In addition, Babelfish for Aurora PostgreSQL version 1.2.0 has been released for PostgreSQL 13.6, providing improvements in support for GRANT, REVOKE , ROWVERSION , JSON_QUERY and more.

Read more in the full announcement, [Amazon Aurora supports PostgreSQL 13.6, 12.10, 11.15, 10.20 and Babelfish for Aurora PostgreSQL 1.2.0](https://aws-oss.beachgeek.co.uk/1iw)

Also new last week was news that Amazon Aurora PostgreSQL-Compatible Edition now supports a foreign data wrapper that can connect to databases that use the Tabular Data Stream (TDS) protocol, such as Sybase databases and Microsoft SQL server. You can use this foreign data wrapper to connect to data sources in other databases eliminating the need to replicate or copy data.

**AWS CDK**

Checkout the latest release notes for [AWS CDK v2.18.0](https://aws-oss.beachgeek.co.uk/1iy) with support for AWS SSO cli, and features including Amazon Cognito, autoscaling, EC2, AWS CloudWatch and more. 

### Videos of the week

**Blazor**

Blazor is a free and open-source web framework that enables developers to create web apps using C# and HTML. Building a SPA fully in .NET 6 with Blazor WebAssembly has become a hot topic in the last few months. AWS offers you several hosting options for your Blazor WASM apps. However, if you want to interact with AWS Services, there are a few things you need to know. Check out this YT video of my colleague Francois Bouteruche as he demonstrates the different hosting options you have on AWS. Then I will discuss what you need to know to interact with AWS Services from your Blazor WASM app.

{{< youtube hyJVWM36dP0 >}}

**RepliByte**

The project was featured in a previous newsletter, and you can read more about this by checking out the blog post above from CEO of Qovery Romaric Philogène. If you prefer video as a medium, this short video will help you understand what it does and why developers are already using this tool.

{{< youtube IKeLnZvECQw >}}

### Events for your diary

> If you have an event you want me to publish here, please contact me and I will include it in this listing. 

**GitOpsCon Europe**
**May 17th, Valencia Spain**

GitOpsCon Europe is designed to foster collaboration, discussion, and knowledge sharing on GitOps. This event is aimed at audiences that are new to GitOps as well as those currently using GitOps within their organisation. Get connected with others that are passionate about GitOps. Learn from practitioners about pitfalls to avoid, hurdles to jump, and how to adopt GitOps in your cloud native environment.

The event is vendor-neutral and is being organised by the CNCF GitOps Working Group. Topics include getting started with GitOps, scaling and managing GitOps, lessons learned from production deployments, technical sessions, and thought leadership.

Read more about this from the official page [here](https://events.linuxfoundation.org/gitopscon-europe/).

**CDK Day**
**May 26th - Virtual**

This is a community organised event about AWS CDK, cdktf, projen and cdk8s. This will be third year they run this event, and if the previous two are anything to go by, this will be essential viewing - live streamed via You Tube. Check out and register for the event over at their home page at [https://www.cdkday.com/](https://www.cdkday.com/)

**OpenSearch**
**Every Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting - Feb2022](https://aws-oss.beachgeek.co.uk/1az)


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)