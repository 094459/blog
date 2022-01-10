---

title: 'AWS open source news and updates #95'
date: '2022-01-10'
tags : [ oss-newsletter, Terraform, Amazon EMR, Consul, PostgreSQL, Flagger, Observability, AWS DeepRacer, Apache Lucene, Apache Log4j, AWS CDK, Babelfish, Apache Hudi, Apache Spark, Debezium]

---

## Jan 10th, 2022 - Instalment #95

Newsletter #95. 

Feliz Ano and a very happy new year to you all in this first newsletter in 2022. In this weeks update I reflect on some of the interesting stuff I learnt running this newsletter in 2021, before diving into the usual round up of new open source projects, AWS and community blog posts, videos and events. This weeks projects include tfdevops, a tool for Terraform uses to integrate with DevOps Guru, a tool to validate your custom container images on Amazon EMR, a Python wrapper for DynamoDB local and more. Topics covered in the post include PostgreSQL, Babelfish, Apache Lucene, Apache Hudi, Apache Spark, Debezium, Terraform, Amazon EMR, Consul, Flagger, AWS DeepRacer and more. Make sure you check out the videos too, I missed a few of these during re:Invent and they are worth checking out (especially the Apache Lucene one).

**2021 in review**

Before diving into the first newsletter of 2022, I just wanted to share a few data points that might be of interest to regular readers. I am very grateful for all the amazing feedback I have received from readers, I hope that this newsletter will continue to be of value in 2022 and beyond.

Over 100K of you viewed the 45 newsletters, with the top 5 countries of origin being the US, India, UK, Australia, and Germany. From a demographic perspective, 80% of readers identified as male, 19.1% female, with over 53% being within the 25-34 age range, 30% being 35-44 and 15% 45-54.

Over those 45 posts, we had over 800 unique contributors. In 2021 it became clear that it was the actual code projects you were mostly interested in, so you can expect a few tweaks in this newsletter to share more of those projects and be more frugal on your time/attention with the other stuff.

The top three most view posts where not surprisingly, open source repositories. The most viewed was **[Querypal](https://aws-oss.beachgeek.co.uk/x)** is a web-based, query execution tool which leverages Amazon Athena to make authoring queries and retrieving results simple for users. Following that was **[cfn-diagram](https://aws-oss.beachgeek.co.uk/4r)** from the MatHem tech team, which a super nice CLI tool to visualise CloudFormation/SAM/CDK stacks as visjs networks, draw.io or ascii-art diagrams. Lastly, we have **[censor-shell](https://aws-oss.beachgeek.co.uk/admin/index.php?search=&search_in=all&sort_by=timestamp&sort_order=desc&perpage=2000&click_filter=more&click_limit=&date_filter=before&date_first=&date_second=#:~:text=295-,fb,-GitHub%20%2D%20iann0036/censor)** from AWS Hero Ian Mckay, a great tool if you are doing demos or presentations, as it hides shell / Bash / console output based on defined patterns - great for hiding secrets in demos!

The technical posts I have been writing on Apache Airflow have also been very well received, so please let me know what pain points or additional stuff you would like me to cover in that area too. Outside of Apache Airflow, the highest viewed post of 2021 was my detailed walkthrough of how to take a simple Spring Boot app, and deploy it on any thing, any where - a good example of combing open source technologies to allow customers the most flexibility on where they run their workloads. Over 30K of you read that.

What would you like to see me cover more of in 2022 in this newsletter? I would love to know, so feel free to use the comments, email or contact me via one of the many social channels you will find me on. I look forward to reading your suggestions.

**Apache Log4j rce update**

If you missed it in the last newsletter that I published before the Christmas holidays, then here is a summary of important info. Some of the posts have been updated since the last time I shared these, so it is well worth re-reading them if this is something you are still working on.

* [Hotpatch for Apache Log4j](https://aws-oss.beachgeek.co.uk/16g)- this is a blog post published that provides some general information as well as access to some tooling that can help customers identify and patch systems that may be vulnerable. For customers who are using Amazon Linux 2, you can now install this quickly (https://twitter.com/stewartsmith/status/1471150310718468097) via “yum install log4j-cve-2021-44228-hotpatch” as it has been added to the package repositories.
* [Open source hotpatch for Apache Log4j vulnerability](https://aws-oss.beachgeek.co.uk/16l) - AWS CISO Steve Schmidt summarised our efforts/position on this, pointing to the same resource above. 
* [hotpatch-for-apache-log4j2](https://aws-oss.beachgeek.co.uk/16m) - This is a tool which injects a Java agent into a running JVM process. The agent will attempt to patch the lookup() method of all loaded org.apache.logging.log4j.core.lookup.JndiLookup instances to unconditionally return the string "Patched JndiLookup::lookup()".
* [kubernetes-log4j-cve-2021-44228-node-agent](https://aws-oss.beachgeek.co.uk/16n) - The Apache Log4j2 CVE-2021-44228 node agent is an open source project built by the Kubernetes team at AWS. It is designed to run as a DaemonSet and mitigate the impact of Log4j2 CVE-2021-44228
* [Using AWS security services to protect against, detect, and respond to the Log4j vulnerability](https://aws-oss.beachgeek.co.uk/16j) - a guide on how to use AWS security services to help you manage this incident.
* [Advice on mitigating the Apache log4j security issue for EKS, ECS, and Fargate customers](https://aws-oss.beachgeek.co.uk/175)- this post  shows you how Amazon Elastic Container Service (Amazon ECS) and Amazon Elastic Kubernetes Service (Amazon EKS) customers using Amazon EC2 and AWS Fargate to run their containerized applications can identify and mitigate CVE-2021-44228 and CVE-2021-45046 (the “log4j2 issue”).
* [Container scanning updates in Amazon ECR private registries using Amazon Inspector](https://aws-oss.beachgeek.co.uk/176) - if you create/build/use container images, then check out how you can scan those to help identify vulnerabilities such as CVE-2021-44228 and CVE-2021-45046. 
* [AWS resources to address Apache Log4j vulnerabilities](https://aws.amazon.com/blogs/publicsector/aws-resources-to-address-apache-log4j-vulnerabilities/) Mukhtar Kabir provides his own summary of resources you can use to help manage this incident.

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: David Krohn, Kapil Thangavelu, Harish Vaswani, Rafael Ramos,  Welly Siauw, Parag Bhingre, Sanjeev Ganjihal, Aaron Miller, Mike Revitt, Woongbin Kang, Jonathan Rau, Chris Miller, Michael Sokolov, Michael Froh, Sébastien Stormacq, Matt Morgan, Gary Stafford, Michael Hausenblas, Udit Mehrotra and Gagan Brahmi.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest open source projects

**tfdevops**

[tfdevops](https://aws-oss.beachgeek.co.uk/17j) this project from Staklet provides support for terraform users by automatically converting terraform state to an imported CloudFormation stack and optionally enabling it with DevOps guru. To help you get started with this project, checkout the blog post from Kapil Thangavelu, Harish Vaswani and Rafael Ramo, [Monitor AWS resources created by Terraform in Amazon DevOps Guru using tfdevops](https://aws-oss.beachgeek.co.uk/17k) which demonstrates how to enable DevOps Guru to monitor your AWS resources created by Terraform

**data-compare-tool**

[data-compare-tool](https://aws-oss.beachgeek.co.uk/189) this tool might be helpful for those currently thinking about, planning or in the process of migrating from Oracle or SQL Server databases. The data compare tool helps in validating your data from one database to another, with the source being either Oracle or SQL Server and target is PostgreSQL. The tool fetch the data from the table(s) (depending on the optional filter given) in chunks and each column in the row of the chunk will get concatenated and generates hash. The generated hash will be compared and produces the result row wise.

**amazon-emr-on-eks-custom-image-cli**

[amazon-emr-on-eks-custom-image-cli](https://aws-oss.beachgeek.co.uk/17i) - Amazon EMR on Amazon EKS provides support for Custom Images, a capability that enables you to customise the Docker container images used for running Apache Spark applications on Amazon EMR on EKS. Custom images enables you to install and configure packages specific to your workload that are not available in the public distribution of EMR’s Spark runtime into a single immutable container.  This open source tool enables you to validate the image’s file structure. The utility will examine basic required arguments and ensure that the modifications work as expected and prevent job failures due to common misconfigurations.

**aws-firewall-factory**

[aws-firewall-factory](https://aws-oss.beachgeek.co.uk/183) this open source solution from David Krohn helps you deploy, update, and stage your Web Application Firewalls while managing them centrally via AWS Firewall Manager. David has put together a blog post, [Introducing the AWS Firewall Factory](https://aws-oss.beachgeek.co.uk/184) to help get you started.

![arch](https://github.com/globaldatanet/aws-firewall-factory/blob/master/static/AWSFIREWALLMANAGER.png?raw=true)

**serverless-kotlin-demo**
[serverless-kotlin-demo](https://aws-oss.beachgeek.co.uk/181) incase you missed the announcement, the AWS SDK for Kotlin was made at re:Invent, so why not check this simple serverless application built in Kotlin using the AWS SDK for Kotlin. It consists of an Amazon API Gateway backed by four AWS Lambda functions and an Amazon DynamoDB table for storage.

![arch](https://github.com/aws-samples/serverless-kotlin-demo/blob/main/imgs/diagram.png?raw=true)

**ddb_local**

[ddb_local](https://aws-oss.beachgeek.co.uk/17r) this project from Woongbin Kang provides a convenient Python wrapper for DynamoDB Local, and he has put together this blog post to help you get started: [ddb-local - Python wrapper for DynamoDBLocal](https://aws-oss.beachgeek.co.uk/17s)

**remote-monitoring-of-iot-devices**

[remote-monitoring-of-iot-devices](https://aws-oss.beachgeek.co.uk/187) IoT devices tend to have intermittent connectivity to the cloud. Furthermore, many devices are battery powered and can stop sending data to the cloud when they run out of charge. It is imperative to monitor these devices for data transmission, and data validity. Remotely monitoring assets is necessary to generate outcome-oriented insights from IoT solutions, whether it's based on telemetry data generated by a few devices in a smart home setting, or sensor-based data streaming off thousands of industrial devices. This solution ingests real-time device data from IoT devices to assess the state of each IoT device and send you notifications if there are data transmission /validity issues.

The solution provides a framework for collecting diagnostic information for deriving outcome- oriented insights into the health of your assets. The solution utilises a managed service to collect, analyse and detect faults and/or sub-optimal performance to generate events in real-time. These events are then used to invoke automatic alerts and actions to automate diagnostics and initiate maintenance requests for that device.

![arch](https://github.com/awslabs/remote-monitoring-of-iot-devices/blob/main/images/architecture.png?raw=true)

**aws-react-spa-with-cognito-auth**

[aws-react-spa-with-cognito-auth](https://aws-oss.beachgeek.co.uk/186) this sample shows how to make a React SPA application with serverless backend by AWS Cloud Development Kit (CDK).

![arch](https://github.com/aws-samples/aws-react-spa-with-cognito-auth/blob/main/imgs/architecture.png?raw=true)

### AWS and Community blog posts

**Babelfish**

Babelfish for Aurora PostgreSQL is a capability for Amazon Aurora PostgreSQL-Compatible Edition developed using the PostgreSQL extension framework that enables Aurora to understand commands from applications written for Microsoft SQL Server. Rajib Sadhu has put together this post, [Run SQL Server Reporting Services reports against Babelfish for Aurora PostgreSQL](https://aws-oss.beachgeek.co.uk/17y) that examines a use case in which you’re migrating your Microsoft SQL Server database to Babelfish for Aurora PostgreSQL and you have SSRS reports using the application databases as source. We show you how to modify your SSRS reports to work with your databases after they have been migrated to Babelfish for Aurora PostgreSQL.

![arch](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2021/12/16/DBBLOG-1861-image001.png)

**Open Data Lakes**

In the post, [The Art of Building Open Data Lakes with Apache Hudi, Kafka, Hive, and Debezium](https://aws-oss.beachgeek.co.uk/17v) Gary Stafford shares how to build a data lake on AWS using a combination of open-source software (OSS), including Red Hat’s Debezium, Apache Kafka, Kafka Connect, Apache Hive, Apache Spark, Apache Hudi, and Hudi DeltaStreamer. 

![arch](https://miro.medium.com/max/1400/1*IqYbm7LMotC5oNLrACIa8A.png)

**PostgreSQL**

The Oracle Foreign Data Wrapper (oracle_fdw) has been available as a production-ready extension to the community version of PostgreSQL since April 8, 2014. This extension allows a PostgreSQL database to connect directly with an Oracle database—much like database links do in Oracle databases. In the post, [Connect to Oracle from Amazon RDS for PostgreSQL using the oracle_fdw](https://aws-oss.beachgeek.co.uk/17m) Mike Revitt shows you how to configure and utilize oracle_fdw in Amazon RDS for PostgreSQL to allow you to progressively migrate your Oracle databases into PostgreSQL on AWS regardless of whether or not they’re using Oracle database links. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2021/12/14/DBBLOG-1397-image001.png)

**Consul**

Consul is an open source project that helps you to automate network configurations, discover services, and enable secure connectivity across any cloud or runtime. In the post, [Getting started with Consul service mesh on Amazon ECS](https://aws-oss.beachgeek.co.uk/17l) Welly Siauw and Parag Bhingre show you how to integrate Consul service mesh on Amazon ECS using AWS CDK. [hands on]

**Flagger**

Flagger is an open source progressive delivery tool that automates the release process for applications running on Kubernetes. It reduces the risk of introducing a new software version in production by gradually shifting traffic to the new version while measuring metrics and running conformance tests. Sanjeev Ganjihal and Aaron Miller
 show you how you can leverage AWS App Mesh and Flagger to implement progressive delivery (automated metrics-based canary deployment)in the blog post, [Progressive Delivery using AWS App Mesh and Flagger](https://aws-oss.beachgeek.co.uk/17n) [hands on]
 
![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2021/12/16/AppMesh2.jpg)

**AWS CDK**

Published on Christmas Day, this nice post from Matt Morgan, [AWS CDK v2 Tutorial – How to Create a Three-Tier Serverless Application](https://aws-oss.beachgeek.co.uk/17u), does what it says on the tin - namely provide you with a simple walk through on how you can create a CDK application (in Typescript) to configure a typical three tier application. All source code is provided via a linked GitHub repo. Nice!

**Observability**

It was great to read this, [On The State Of Continuous Profiling](https://aws-oss.beachgeek.co.uk/17t), from Michael Hausenblas who takes a look at what continuous profiling is, and where are we with it at the end of 2021.

{{< tweet 1462047847776407556 >}}

**Other posts worth checking out**

* In [Optimizing SAS Grid on AWS with Amazon FSx for Lustre](https://aws-oss.beachgeek.co.uk/17o) find out more about the best practices for migrating SAS Grid to AWS, Amazon FSx for Lustre and how its’ data compression feature can help you lower your costs
* [How Belcorp decreased cost and improved reliability in its big data processing framework using Amazon EMR managed scaling](https://aws-oss.beachgeek.co.uk/17p) is a great case study where Belcorp share how they were able to undertake a series of continuous improvements in order to reduce the number of platform incidents, optimise SLAs required by the business, and be more cost-efficient when using Amazon EMR, resulting in up to 30% savings for the company.
* [How Twilio modernized its billing platform on Amazon Aurora MySQL](https://aws-oss.beachgeek.co.uk/17q) talks about how Twilio modernized their billing platform with Amazon Aurora MySQL-Compatible Edition to support their growth
* [Tips & Tricks: Debugging your C# CDK project in Visual Studio](https://aws-oss.beachgeek.co.uk/17w) is a rare but good to see a C# CDK post
* [Modernize and containerize a legacy MVC .NET application with Entity Framework to .NET Core with Entity Framework Core: Part 3](https://aws-oss.beachgeek.co.uk/17z) the third instalment and shows the steps to modernise a legacy SQL Server database to Amazon Aurora PostgreSQL-Compatible Edition using Babelfish. Parts 1 and 2 have been covered in previous newsletters

![arch](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2021/12/14/DBBLOG-1484-image001.png)

### Amazon EKS Newsletter

Brand new for 2022, a new newsletter from the Amazon EKS developer advocates that you really should sign up for if you are interested in all things Kubernetes and Cloud Native. [EKS News](https://aws-oss.beachgeek.co.uk/185) brings you all the latest updates, news and service announcements, notable blogs and stuff you really need to know about. Make sure you sign up for it so you do not miss a thing.

### Quick updates

**AWS SAM Cli**

Last week we announced the general availability of AWS Serverless Application Model CLI (AWS SAM CLI) support for local testing of AWS Cloud Development Kit applications. AWS SAM and AWS CDK are both open-source frameworks for building applications using infrastructure as code (IaC). AWS SAM is made up of the SAM template, which is a way to describe infrastructure in an application using JSON or YAML, and SAM CLI, which is a tool to build, package, test and deploy AWS SAM applications. AWS CDK is a development framework to define your cloud application resources using familiar programming languages such as Python or Node.js.

Before this announcement, you could use the AWS SAM CLI to build, test, and package serverless applications defined using AWS CloudFormation or AWS SAM templates. With this release, you can use AWS SAM CLI to run local testing on Lambda functions and REST APIs on API Gateway defined using the AWS CDK.

**NodeJS**

AWS Lambda functions using the Node.js 14 runtime now support code packaged as ECMAScript modules, allowing Lambda customers to consume a wider range of JavaScript packages in their Lambda functions. In addition, Lambda customers can now take advantage of ‘top-level await’, a Node.js 14 language feature. When used with Provisioned Concurrency, this improves cold-start performance for functions with asynchronous initialisation tasks. For more information, see the blog post Using Node.JS ES Modules and Top-Level Await in AWS Lambda.

ECMAScript (ES) modules are a packaging format for JavaScript code, used to publish JavaScript code libraries so they can be imported and re-used in other applications. Until now, Lambda’s Node.js runtimes only supported code using the earlier CommonJS packaging format. With this release, customers can use the ES module format for both their function handler and any code they import.

With this release, customers can also use ‘top-level await’, a Node.js 14 language feature, to wait for asynchronous initialisation tasks to complete during the function initialisation phase. This capability is especially useful for functions configured with Provisioned Concurrency, which creates runtime environments ahead of time. This is designed to reduce cold start latency, resulting in more responsive applications.

Customers can use ES modules and top-level await with all Lambda functions using the Node.js 14 runtime (and subsequent releases of newer Node.js runtimes). 


**Apache Kafka**

Amazon Managed Streaming for Apache Kafka (Amazon MSK) now supports Apache Kafka versions 2.6.3 and 2.7.2 for new and existing clusters. These new Apache Kafka releases includes security improvements and bug fixes.  

**Apache Hudi**

Apache Hudi is an open-source transactional data lake framework that greatly simplifies incremental data processing and data pipeline development by providing record-level insert, update, and delete capabilities. This record-level capability is helpful if you’re building your data lakes on Amazon Simple Storage Service (Amazon S3) or Hadoop Distributed File System (HDFS). In this post, [New features from Apache Hudi 0.7.0 and 0.8.0 available on Amazon EMR](https://aws-oss.beachgeek.co.uk/17x) Udit Mehrotra and Gagan Brahmi share a summary of some of the key new features and capabilities included since Apache Hudi release versions 0.7.0 and 0.8.0. 

![illustration](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2021/12/08/BDB-1699-image015.jpg)

**Amazon EMR on EKS**

Amazon EMR on EKS enables customers to easily run open-source big data frameworks such as Apache Spark on Amazon EKS. Amazon EMR on EKS customers setup and use a managed endpoint (available in preview) to run interactive workloads using integrated development environments (IDE) such as EMR Studio.

Data scientists and data analysts may need to use libraries in their code that are not available in the public distribution of Amazon EMR on EKS Spark runtime. Customers use custom images functionality to create Spark driver and executor images that contain their application dependencies. Until now, customers who used Amazon EMR on EKS’ managed endpoints to run interactive workloads were unable to use custom images. With this release, you can now build a custom image with your application dependencies and use the image in your interactive jobs run using managed endpoints.

You can also use the Custom Images feature to customise container images for AWS Graviton-based instances. Customers often have applications with different compute architecture requirements. For example, customers may want to run machine learning workloads on AWS Graviton ARM-based instances that offer compelling price-performance benefits, while running daily data transformation jobs on non-Graviton-based instances. Previously, Amazon EMR on EKS users could only customise container images of non-Graviton-based EC2 instances. With this release, users can customise images for both Graviton-based and non-Graviton-based EC2 instances. Building, deploying, and using container images for different architectures from the same image repository in Amazon EMR on EKS is now more simple.

**Kubernetes**

Amazon Elastic Kubernetes Service (EKS) now supports IPv6, enabling customers to scale containerised applications on Kubernetes far beyond limits of private IPv4 address space, while achieving high network bandwidth with minimal complexity.

Kubernetes uses a flat networking model that requires each pod to receive an IP address. This simplified approach enables low-friction porting of applications from virtual machines to containers, but requires a significant amount of IP addresses that many private IPv4 networks are not equipped to handle. Further, clusters running in IPv4 based networks require complex network routing configuration to enable pod communication with internet services.

With EKS support for IPv6, pods are assigned only a globally routable IPv6 address, and you easily scale applications in your cluster without consuming limited private IPv4 address space. This globally routable IPv6 address can be used to directly communicate with any IPv6 endpoint in your Amazon VPC, on-premises network, or the public internet. IPv6 support is enabled through the Amazon VPC CNI plugin, which directly integrates with the EC2 networking stack to deliver high performance and reliability. With native VPC integration, you can secure your applications using standard components including egress-only internet gateways, security groups, and network access control lists (ACL). EKS configures networking so that pods can still communicate with IPv4 based endpoints outside the cluster, enabling you to adopt the benefits of IPv6 and Kubernetes without requiring that all dependent services deployed across your organisation are first migrated to IPv6.

Read more in the post from Sébastien Stormacq, [Amazon Elastic Kubernetes Service Adds IPv6 Networking](https://aws-oss.beachgeek.co.uk/17h)


### Videos of the week

**ElectricEye**

I missed this session from Jonathan Rao due to over reaching myself, so happy that I was able to check it out on YouTube. With continual increase of adoption of public cloud workloads, and the expansion of services therein, security and developer teams have a hard time keeping up with best practices of configurations. While the cloud service providers and commercial partners have helped bridge the gap with Cloud Security Posture Management (CSPM) teams are still left in the dark with not-often-used or newly launched services. Adopting Open Source Security tools can help bridge these gaps, extend current coverage, and further empower developer and security teams to detect issues before they become security incidents. Watch this YT video to see Jonathan do a demo of ElectricEye, and open-source AWS CSPM tool with over 320 available checks and 80 support services, which can help with extending your CSPM.

{{< youtube dfRw4QaikQg >}}

**AWS DeepRacer**

Chris Miller shows you how you can learn to code, create, and collaborate with a global AWS DeepRacer GitHub community on AWS DeepRacer using open-source software. Check out this video from re:Invent to see top AWS DeepRacer community members showcase their latest projects and use cases to inspire endless possibilities for programming your AWS DeepRacer device.

{{< youtube tKQeUti_HEQ >}}

**Apache Lucene**

Another video from re:Invent, this time Michael Sokolov and Michael Froh take a look at the inner workings of modern open-source development by following a significant, complex change from inception to release. In 2020, Amazon completed a multiyear migration of its customer-facing product search engine onto a new service based on Apache Lucene, supported by many AWS services. In production, Amazon observed Lucene’s segmented nature influencing query latency and had an idea to reduce its segment count. The idea seemed simple, but its realisation, through close collaboration with the Lucene developer community, took nearly a year! This session dives deep into this journey.

{{< youtube UwclHSeE_B8 >}}

### Events for your diary

If you have an event you want me to publish here, please contact me and I will include it in this listing.

**Rust Foundation Ask Me Anything – January 2022**
**January 11th, 3PM Eastern Time (US)**

The first Rust Foundation AMA of the new year will be on January 11th at 12pm PT/3pm ET. The new Executive Director and CEO Bec Rumbul will share the latest updates, discuss the Foundation's plans for 2022, and answer any questions you have for her. Bec will be joined by Rust Foundation Board Director Nell Shamrell-Harrington, and the conversation will be moderated by Sage Griffin. Read more and [register, here](https://aws-oss.beachgeek.co.uk/180)

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)

