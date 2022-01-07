---
title: 'AWS open source news and updates No. 37'
date: '2020-09-28'
tags : [ oss-newsletter ]
---
## September 28th - Instalment #37

Week No.37 and plenty of open source goodness to sink your teeth into this week. We have the usual projects round up, including projects to help you work with your AWS Secrets via the CLI or quickly spin up AWS infrastructure, we have posts covering topics such as Spring Boot, tagging of AWS resources and a must read post on Kubernetes and then finally we have the usual round up of AWS open source goodies and case studies.


### Your feedback matters!

I have put together a short feedback survey, which I would ask you to take - it will take no more than 2 minutes. You can access [here](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn). Many thanks!

[Take the survey](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn)

### Events for your diary

Have you signed up for these events? Make sure you check them out before they go...

**CDK Day**
**September 30th, 3PM BST**

Now this is an event you should put in your diaries, an event that has been put together by the AWS CDK community (and a lot of familiar faces from posts I have shared in this weekly newsletter), has a fantastic line up of speakers and promises to be an unmissable event if you are thinking of or looking at AWS CDK. Find more details, including speaker line up and registration, [at the link](https://www.cdkday.com/) -> https://www.cdkday.com/


**ICYMI: Container Day EU**

In case you missed it, on August 17th, at the first ever virtual KubeCon, AWS held our day zero event, Container Day. The day covered technical deep dives, product demos, and launches all on how Amazon EKS makes it easy to deploy, manage, and scale containerized applications using Kubernetes on AWS. Click [here to get links](https://aws.amazon.com/blogs/containers/icymi-container-day-eu/) to the recordings and slides.

**AWS Controllers for Kubernetes**

If you missed this event last week, then the video has been uploaded and you can check out Jay Pipe's session on AWS Controllers for Kubernetes or (ACK). Using ACK you can use the Kubernetes API to describe not just your Kubernetes objects but also resources on which your applications. For example, describe that RDS database instance using a Kubernetes manifest and let it manage its lifecycle or maybe you need to ensure that an S3 Bucket exists for your application to store objects in? ACK can handle that for you as well, all you need to do is describe the S3 bucket in a Kubernetes manifest.

https://www.youtube.com/watch?v=ruQI5sHm39k

{% youtube ruQI5sHm39k %}

### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to Jay Yeras, Raj Bagwe, Cunjun Wang, Eric Hsueh, Sang Jin Lee,Juan Manuel Gomez, Adeleke Coker, Geoff Blake, Janakarajan Natarajan, Nader Dabit, Nicolas Malaval, Olaf Conijn, Ozioma Uzoegwu, Greg Sterin,  Ryan Niksch, Michael Hausenblas,  James Saryerwinnie, Anna Anisienia, Björn Wilmsmann, Karl Hughes, Philip Riecks, Tom Hombergs, David Cockerill, Daniel Hogan, Gerard Sans, Robert Boscacci, Jérémy Levy, Kevin Glasson, Andrew May, Jobin George, Michael Coughlin and Joseph Morais.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.


### Latest from open source projects

Here is the latest open source tools, libraries and demos from the last week.

**goss**

[goss](https://github.com/kevinglasson/goss) is an open source tool from Kevin Glasson for managing AWS SSM parameters from the CLI. It was mainly developed to manage batches of secrets / parameters stored in local env files for application and infrastructure deployment. It has really nice documentation and you should be able to get up and running with this very quickly. In the Reddit thread Kevin provided some additional background as to why he needed to create goss, which you can [check out here ](https://www.reddit.com/r/aws/comments/iwylqu/tool_for_managing_parameters_in_aws_ssm_parameter/?utm_source=share&utm_medium=ios_app&utm_name=iossmf)if you are interested. 

**scaffold**

[scaffold-cli](https://github.com/scaffold-sh/cli) is an new open source project from Jérémy Levy that allows you to create AWS infrastructure quickly via a simple command line syntax. This project has detailed documentation on how to install and get started, which you can find [here](https://scaffold.sh/docs). The project uses the catalog concept to create re-usable patterns for you to use, with the static website being the only current one. I really like how this is shown, so look forward to seeing how this catalog grows over time. Nice work Jeremy.

**Takomo**

[Takomo](https://github.com/takomo-io/takomo) is an open source project from Takomo.io that makes it easy to organise, parameterise and deploy your AWS CloudFormation stacks across multiple regions and accounts. In addition to stacks, you can also manage accounts, organisational units and service control policies that belong to your AWS organisation. The documentation is great and this project comes with plenty of examples to get you going which you can find [here](https://takomo.io/docs/examples/about).

**stackmanager**

[stackmanager](https://github.com/LeadingEDJE/stackmanager) this project from Andrew May is another AWS CloudFormation tool to help you manage CloudFormation stacks based upon templates (either local or stored in your Amazon S3 buckets) and a YAML configuration file. You can then perform a number of actions (deploy, status, delete, etc) against the CloudFormation stacks in your configuration files. If you are using Azure DevOps, this tool also change its behaviour automatically - nice.

**nab3**

[nab3](https://github.com/WillNye/nab3) is an open source project whose name made me smile - Not Another Boto3. This project is WillNye's at tackling some of the things annoyed him about boto3. nab3 provides an easy to use interface for searching and inspecting a service and its related resources within AWS. It also creates useful relationships that aren't returned within boto3. An example of this is returning the Security Groups for an ASG or an ECS Cluster (outlined in the README). The documentation and examples provided are super clear, and so if you have been using boto3 then you should take a look at this project to see if it can make your life easier. The author of this project concludes: "More AWS services still need to be added so any contributors are welcome. There is a dedicated doc on contributing because as you may imagine trying to normalize boto3 can get hairy."

**Amazon Interactive Video Service**

[Enhance your Android ecommerce app with Amazon Interactive Video Service](https://aws.amazon.com/blogs/media/enhance-your-android-ecommerce-app-with-amazon-interactive-video-service/) from Sang Jin Lee walks you through this open source project which you can build upon that uses the Amazon Interactive Video Service to create a cool interactive video experience. Sang Jin provides all the code in the [GitHub repo](https://github.com/aws-samples/amazon-ivs-ecommerce-android-demo) and this project will let you create a sample application that showcases a live video stream, and a carousel that gives shoppers the opportunity to purchase the products shown on stream.

### Fresh blog posts for your reading pleasure

**Kubernetes**

[10 things you didn't know about Kubernetes](https://dev.to/aws/10-things-you-didn-t-know-about-kubernetes-24n8) Michael Hausenblas shares ten things you might not know about Kubernetes. I have to say, they were ALL new to me, so I feel like I learn something from this post. To be fair, anything that mentions Raspberry Pi's is a winner in my book. Make sure you check the others in the series too (the terminal one is particular interesting).

[Serverless Kubernetes Cluster on AWS with EKS on Fargate](https://t.co/dn0A8tqVyg?amp=1) When Massimo recommends a post, you know it is going to be great, and this post from Anna Anisienia provides a deep dive on running serverless Kubernetes clusters on AWS, looking at the various options you have, use cases and strengths of different approaches. Anna also provides a quick demo so you can see this all for yourself.

**AWS SAM**

[Ditching the AWS GUI Console](https://towardsdatascience.com/ditching-the-aws-gui-console-ac77f46a05fa) - "Every good work of software starts by scratching a developer's personal itch." so wrote Eric Raymond in The Cathedral and the Bazaar, and in this post from Robert Boscacci, the scratch he was trying to itch was how to make sure that his lunchtime spot would be open for him to enjoy. So enjoy Robert's journey of automation and you can snack on his [provided source code](https://github.com/boscacci/isTheBryantParkLawnOpen.com) if you want to try this little morsel out. Bon appetite.

**SpaceNet 7**

[Deploying the SpaceNet 7 Baseline on AWS](https://medium.com/the-downlinq/deploying-the-spacenet-7-baseline-on-aws-df756a4d9695)
this blog post from Daniel Hogan will help you get up and running with [SpaceNet 7 Challenge](https://medium.com/the-downlinq/announcing-spacenet-7-the-multi-temporal-urban-development-challenge-53f68e24b9fa), where participants are challenged to identify and track building footprints in provided time series aerial imagery. The challenge ends on October 27th, and so with that date in mind, Daniel has put together a walkthrough on how you deploy everything you need on AWS. 

He has released an Amazon Machine Image with everything necessary to get started including a step-by-step instructions to undertake the deep learning process in the cloud. 

![image](https://miro.medium.com/max/700/1*JBfNNUj7neVW6RDnfxIoaw.png)

**Tagging AWS resources**

[Maintain AWS Tags When You Fall Behind - Part 3](https://www.cloudforecast.io/blog/maintain-aws-tags-when-you-fall-behind-part-3/) in this excellent write up from Karl Hughes, he covers how you can use a number of open source tools (many of which I have covered in earlier editions of this newsletter) to ensure you are properly tagging your AWS resources. Tagging resources is such an important way in which you can help increase visibility and govern your AWS environments, so this is well worth checking out. Make sure you read the [first part](https://www.cloudforecast.io/blog/aws-tagging-best-practices/), which talks about creating your tagging strategy.



### Books

**Spring Boot on AWS**

Hot off the press, Björn Wilmsmann got in touch to share with me his new book, [**Stratospheric** From Zero to Production with Spring Boot and AWS](https://www.stratospheric.dev/) which he authored with Philip Riecks and Tom Hombergs, that covers everything you need to know about running Spring Boot on AWS. From getting started and managing difference environments to using AWS CloudFormation and AWS CDK, end user registration with AWS Cognito and integration with other AWS services, there is so much packed into this book.

As part of a demo and presentation on Amazon Corretto I was looking for some sample java apps to test, and having been away from the Java world for (what I thought was a short time) it was clear that there is some really cool stuff being done by the Spring boot development communities. If you join the mailing list you can benefit from a 50% discount, and you cannot say fairer than that.

![book](https://stratospheric.dev/assets/images/book-mockup.png)


### AWS open source posts

**Prometheus and Thanos**

[Improving HA and long-term storage for Prometheus using Thanos on EKS with S3](https://aws.amazon.com/blogs/opensource/improving-ha-and-long-term-storage-for-prometheus-using-thanos-on-eks-with-s3/) by Raj Bagwe talks about Prometheus (open source systems monitoring and alerting toolkit that is widely adopted as a standard monitoring tool) and Thanos (an open source project that provides components that can allow you to scale up your Prometheus capacity) and how to implement Thanos for HA and long-term storage for Prometheus metrics using Amazon S3 on an Amazon Elastic Kubernetes Service (Amazon EKS) platform.

![deploy](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2020/09/09/rbagwe_Thanos_f2.png)

Raj concludes with some details around costs of implementing this architecture, with some suggestions on how you can approach optimisation.

[AWS adds a C++ Prometheus Exporter to OpenTelemetry](https://aws.amazon.com/blogs/opensource/aws-adds-a-c-prometheus-exporter-to-opentelemetry/) Cunjun Wang and Eric Hsueh—describe their first engineering contributions to the popular open source observability project OpenTelemetry. OpenTelemetry aims to develop an open standard and provides implementation in multiple programming languages for collecting telemetry data, including metrics, tracing, and logs. The interns contributed the C++ Prometheus Exporter to the OpenTelemetry project. This exporter takes collected metrics from OpenTelemetry and exports to Prometheus, a popular open source alerting and monitoring application. 

This post explains how the Prometheus exporter works, potential use cases and concludes with what they learned along the way. 

**FreeRADIUS MFA**

[Integrating FreeRADIUS MFA with Amazon WorkSpaces](https://aws.amazon.com/blogs/desktop-and-application-streaming/integrating-freeradius-mfa-with-amazon-workspaces/) from Juan Manuel Gomez and Adeleke Coker shows you how to configure the open source FreeRADIUS and LinOTP for multi-factor authentication (MFA) to Amazon WorkSpaces to provide that second factor of authentication and increase your security posture. FreeRADIUS is the most popular open source RADIUS server and the most widely deployed RADIUS server in the world and is used by educational institutions, internet service providers and for enterprise networks. MFA adds an extra layer of protection to a user name and password (the first “factor”). With MFA, you must enter an authentication code (the second factor), which is provided by your MFA solution.

![solution](https://d2908q01vomqb2.cloudfront.net/827bfc458708f0b442009c9c9836f7e4b65557fb/2020/09/23/Picture1-11.png)

**AWS Perspective**

[AWS Perspective](https://aws.amazon.com/solutions/implementations/aws-perspective/) is a new AWS Solution that is open source that is visualisation tool that quickly generates architecture diagrams of your AWS Cloud workloads. You can use the solution to build, customise, and share detailed workload visualisations based on live data from AWS environments. This solution works by maintaining an inventory of the AWS resources across your accounts and Regions, mapping relationships between them, and displaying them in a web user interface (web UI). When making changes to a resource, AWS Perspective saves you time by providing a link to the resource in the AWS Management Console.

![arch](https://d1.awsstatic.com/Solutions/Solutions%20Category%20Template%20Draft/Solution%20Architecture%20Diagrams/aws-perspective-architecture-diagram.f67026185e4f02d2d623289fa714d69d2c1f7af6.png)

Really excited about this project, and I am planning to set this up in my own environment next week so watch out for a potential video or blog post on what I learnt.

**AWS Graviton2**

[Getting started with Travis-CI.com on AWS Graviton2](https://aws.amazon.com/blogs/opensource/getting-started-with-travis-ci-com-on-aws-graviton2/) this post from Geoff Blake and Janakarajan Natarajan covers probably my most favourite technology (well at least at the moment) which is the AWS Graviton2 instance types. One of the reasons I really like this technology is that it is a perfect marriage with open source projects, where those projects can be compiled and optimised against these Arm based architectures to help deliver performance and cost savings for customers using those open source projects. Geoff and Janakarajan how Travis-CI.com now supports AWS Graviton2 instances to enable easy and efficient build, test, and deployment of code-artifacts for Arm64-based systems. This post is a walkthrough of how to do this, and you will soon be able to compile your own projects onto this new exciting processor architecture.


**AWS Organizations**

Managing AWS Organizations using the open source org-formation tool - this is a three part post, [Part one](https://aws.amazon.com/blogs/opensource/managing-aws-organizations-using-the-open-source-org-formation-tool-part-1/), [Part two](https://aws.amazon.com/blogs/opensource/managing-aws-organizations-using-the-open-source-org-formation-tool-part-2/) and [Part three](https://aws.amazon.com/blogs/opensource/managing-aws-organizations-using-the-open-source-org-formation-tool-part-3/) from Olaf Conijn. Many may remember Olaf from the series of the Open Source Builders videos (check it out [here](https://www.youtube.com/watch?v=bc-zRJtL5Bo) for the back story) where he talked about the drivers for building this open source project, **org-formation**. **org-formation** is an open source and community-supported tool that allows users to manage different aspects of their AWS Organizations through Infrastructure as Code (IaC). For those unfamiliar with AWS Organisations, it provides a way for customers to manage accounts centrally, allowing them to set and apply policies, set controls, and manage billing and cost management across accounts. The three part series helps introduce org-formation and explain how you can get started.


**AWS Amplify, AppSync and AWS CDK**

A couple of posts this week you need to check out, both of which focus on how you can use AWS CDK to develop your infrastructure as code to host your applications. First up, we have;

[Deploying a Static Website with AWS Amplify and CDK](https://aws.amazon.com/blogs/mobile/deploying-a-static-website-with-aws-amplify-and-cdk/) post from Ozioma Uzoegwu, uses AWS CDK bto uild a sample React application that will be hosted on AWS Amplify. Rather than deploying this via the Amplify console, Ozioma walks you through doing this via AWS CDK.

![arch](https://d2908q01vomqb2.cloudfront.net/0a57cb53ba59c46fc4b692527a38a87c78d84028/2020/09/16/Picture1_updated.png)

Having recently started learning AWS CDK, it has quickly become my default way of configuring the infrastructure I need. This post is an invaluable resource to help you get started.

[Building Scalable GraphQL APIs on AWS with CDK, TypeScript, AWS AppSync, Amazon DynamoDB, and AWS Lambda](https://aws.amazon.com/blogs/mobile/building-scalable-graphql-apis-on-aws-with-cdk-and-aws-appsync/) Nader Dabit walks you through building an AWS AppSync API from scratch using CDK, and how to use CDK to deploy AppSync APIs that leverage a variety of AWS services including Amazon DynamoDB and AWS Lambda. AWS AppSync is a managed serverless GraphQL service that simplifies application development by letting you create a flexible API to securely access, manipulate, and combine data from one or more data sources with a single network call and API endpoint. With AppSync, developers can build scalable applications on a range of data sources, including Amazon DynamoDB NoSQL tables, Amazon Aurora Serverless relational databases, Amazon Elasticsearch clusters, HTTP APIs, and serverless functions powered by AWS Lambda.

Nadar provides[ code for the post](https://github.com/dabit3/cdk-graphql-backend) so you build upon his example as a base for your own projects.

**AWS Amplify, Vue and GraphQL**

[Create a cloud-enabled GraphQL API with AWS Amplify and Vue](https://dev.to/aws/create-a-cloud-enabled-graphql-api-with-aws-amplify-and-vue-271o) hot on the heels of his post last week, Gerard Sans puts together this tutorial, that will help you to understand how to build a GraphQL data-driven serverless app using Vue, AWS Amplify and AWS AppSync. Code provided via [this](https://github.com/gsans/fullstack-serverless-amplify-ui-vue) GitHub repository, and he provides a video walkthrough if that works best for you.


**AWS Chalice and Lambda Powertools**

[Following serverless best practices with AWS Chalice and Lambda Powertools](https://aws.amazon.com/blogs/developer/following-serverless-best-practices-with-aws-chalice-and-lambda-powertools/) another post from James 'Chalice' Saryerwinnie, this time combining AWS Chalice (a framework that lets you quickly create serverless applications in Python) and Lambda Powertools (a suite of utilities for AWS Lambda Functions that makes tracing with AWS X-Ray, structured logging and creating custom metrics asynchronously easier). I have mentioned both projects extensively in previous episodes, and in this post James shows you how to incorporate Lambda Powertools in your AWS Chalice applications. If you are using AWS Chalice this is a must read post.

![arch](https://d2908q01vomqb2.cloudfront.net/0716d9708d321ffb6a00818614779e779925365c/2020/09/22/xray-trace-segments.png)

**Squid**

[How to add DNS filtering to your NAT instance with Squid](https://aws.amazon.com/blogs/security/how-to-add-dns-filtering-to-your-nat-instance-with-squid/) this post by Nicolas Malaval made me reminisce back to the early days of the web, back to the late 90's when I was using Squid as a caching proxy server for customer infrastructures. It was a very nice, robust and powerful open source proxy product. In this post, Nicolas looks at how you can use Squid to implement a “transparent proxy” that can restrict both HTTP and HTTPS outbound traffic to a given set of Internet domains, while being fully transparent for instances in the private subnet. Why? Well, for security and compliance purposes, you might have to filter requests initiated instances (also known as “egress filtering”). With iptables rules, you can restrict outbound traffic with your NAT instance based on a predefined destination port or IP address. However, you might need to enforce more complex security policies, such as allowing requests to AWS endpoints only, or blocking fraudulent websites, which you can’t easily achieve by using iptables rules. So, Squid to the rescue and this post will show you how you can configure this.

![arch](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2019/08/28/fig2-add-DNS_filtering_NAT_instance_with_Squid.png)

Nicolas provides a CloudFormation tempalte to make it even easier for you to get this up and running.

As a footnote, loved [this comment](https://www.linkedin.com/posts/activity-6715456168946475008-YTE5) from Jonathan Rau:

>Big fan of open source security solutions like this. You can partner it with Suricata (H/NIDPS), Wazuh (EDR), and other AWS tooling for some sweet defense-in-depth.


**OpenShift**

[Architecture Patterns for Red Hat OpenShift on AWS](https://aws.amazon.com/blogs/architecture/architecture-patterns-for-red-hat-openshift-on-aws/) this post from Ryan Niksch, he explores what is OpenShift. He starts off with "Red Hat OpenShift is an application platform that provides customers with turnkey application platform that is much more than a simple Kubernetes orchestration." and this post then follows through and shows you it's building blocks, terminology, how to deploy, operating at scale and how you can use it in a hybrid context.

So if you are looking for a post to understand more about what OpenShift is, what is can enable for your business and how to get the most out of it on AWS, then this is the perfect post for you.

### AWS Partner Network

**Securing open source with snyk**

[Simplify Snyk and AWS integration with our latest AWS Quick Start](https://snyk.io/blog/snyk-integration-with-aws-ecr-and-lambda/) this AWS Quick Start solution from Jay Yeras that provides a hassle free way to help you get Snyk working with Amazon Elastic Container Registry (ECR) and AWS Lambda. Snyk is an open source security platform designed to provide developer security tooling that can help you find and address security vulnerabilities as well as help with open source license compliance in your open source projects you use.

![solution](https://lh5.googleusercontent.com/QVwbZpvavV9fGkPwnb1fY3X93ZmYtpC4-cErdrK_YYgiHn6dMGHmkMpAfxYDVyIge9HlBmTr4UhXqHLDkDisVJwrurgkAY1cJrmJzaQZZZCfLrp7GM-NfhQXG9U-AXiwzjAbZpDg)

**Kafka**

[Accelerate Data Warehousing by Streaming Data from Confluent Cloud into Amazon Redshift](https://aws.amazon.com/blogs/apn/accelerate-data-warehousing-by-streaming-data-from-confluent-cloud-into-amazon-redshift/) this collaboration with Jobin George from AWS and Michael Coughlin and Joseph Morais from Confluent introduces the [Kafka Connect Amazon Redshift Sink Connector](https://docs.confluent.io/current/connect/kafka-connect-aws-redshift/index.html) from Confluent Cloud that allows you to export Avro, JSON Schema, or Protobuf data from Apache Kafka topics into your Amazon Redshift services. Confluent Cloud provides a serverless way to help you build event-driven applications that ingest real- or near real-time data into cloud data warehouses and this post provides an overview of Confluent Cloud, and step-by-step instructions to stream data from Confluent Cloud Kafka into an Amazon Redshift table.

![arch](https://d2908q01vomqb2.cloudfront.net/77de68daecd823babbb58edb1c8e14d7106e83bb/2020/09/21/Confluent_Redshift_DataWarehousing_Fig3_HowDataStreamed.jpg)

### Case Studies

**Apache Airflow**

[How Affirm uses AWS Fargate and Apache Airflow to manage batch jobs](https://aws.amazon.com/blogs/containers/how-affirm-uses-aws-fargate-and-apache-airflow-to-manage-batch-jobs/) is a guest post from Greg Sterin, Senior Staff Software Engineer, Affirm. Affirm’s mission is to deliver honest financial products that improve lives, and they reinventing credit to make it more honest and friendly, giving consumers the flexibility to buy now and pay later without any hidden fees or compounding interest. In this post, Greg talks about how the Affirm’s Platform Engineering team has built a developer friendly batch infrastructure framework that enables engineers to easily implement, test, deploy, scale and monitor compute and storage intensive pipelines with very low effort. As part of that solution, they are using Apache Airflow and this posts looks at this solution in more depth and shares the learnings and end result.

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2020/09/22/Screen-Shot-2020-09-22-at-10.19.25-AM.png)

**Public Sector**

[How nonprofit civic organizations use the cloud to meet registration demand and modernize voter education](https://aws.amazon.com/blogs/publicsector/how-nonprofit-civic-organizations-use-cloud-registration-demand-modernize-voter-education/) in this post from AWS Public Sector folks, you can learn more about how nonprofit civic organisations use digital platforms, powered by Amazon Web Services (AWS) and open source software, to register voters online, mobilise volunteers, and educate citizens. The posts talks about the open source platform [Rock the Vote](https://www.rockthevote.com/), a voter registration platform 
that makes voter registration easier for voters and partner organisations across the country.

Remember folks, exercise your right to vote. It is **such** an important privilege. Make sure you help shape your future.

**HarpberDB Studio**

[How we Build and Deploy our Serverless HarperDB Studio Backend Application](https://dev.to/harperdb/how-we-build-and-deploy-our-serverless-harperdb-studio-backend-application-52cg) David Cockerill from HarperDB shows you in this post how they use the open source AWS Serverless Application Model (SAM) to build, test, debug and deploy serverless applications for their HarperDB Management Studio backend. You might find this useful if you are looking for inspiration on how to setup your own environments for serverless development with AWS SAM.

### Quick updates

**Copilot 0.4**

Check out this [Tweet stream](https://twitter.com/efekarakus/status/1308150968073121792?s=11) from Efe Karakus as to the new features in the 0.4 release of Copilot. You can also check the full [release log here](https://github.com/aws/copilot-cli/releases/tag/v0.4.0).

**PostgreSQL**

Starting today, Amazon Aurora PostgreSQL supports the pglogical extension. pglogical is an open source PostgreSQL extension that helps customers replicate data between independent Aurora PostgreSQL databases while maintaining consistent read-write access and a mix of private and common data in each database. Amazon Aurora pglogical uses logical replication to copy data changes between independent Aurora PostgreSQL databases, optionally resolving conflicts based on standard algorithms. Customers can enable pglogical from within their Aurora PostgreSQL instances, and pay only for the additional clusters and cross-region traffic needed, with no upfront costs or software purchases required. Fully integrated, pglogical requires no triggers or external programs. This alternative to physical replication is a highly efficient method of replicating data using a publish/subscribe model for selective replication.

**Amazon Elasticsearch**

Amazon Elasticsearch Service now offers the latest T3 (general-purpose) instances which offer superior performance and larger storage capacity compared to the previous generations. The T3 instances also support our recently launched features like encryption at rest and in-flight, role based access control, HTTP compression, custom dictionary, SQL, alerting, anomaly detection, and cross-cluster search. Read the full announcement [here](https://aws.amazon.com/about-aws/whats-new/2020/09/amazon-elasticsearch-service-offers-t3-instances/).

**Amazon Corretto 15**

Amazon Corretto 15 is now generally available. This version supports the latest Java feature release JDK 15 and is available on Linux, Windows, and macOS. You can download Corretto 15 [here](https://github.com/corretto/corretto-jdk/releases/).

**Amazon Redshfit Spectrum query support for Apache Hudi and Delta Lake**

You can now use Amazon Redshift to run read queries against tables in your Amazon S3 data lake with open source Apache Hudi or Delta Lake. Amazon Redshift Spectrum, a feature of Amazon Redshift, enables you to query your S3 data lake directly from your Redshift cluster without first loading the data into it, minimizing time to insight. Redshift Spectrum powers the lake house architecture which allows you to query your data across Redshift, lake house, and operational databases without any need for ETL or loading data. Redshift Spectrum supports open data formats, such as Parquet, ORC, JSON, and CSV. Redshift Spectrum also supports querying nested data with complex data types such as struct, array, or map.

Redshift Spectrum allows you to read the latest snapshot of Apache Hudi version 0.5.2 Copy-on-Write (CoW) tables and you can read the latest Delta Lake version 0.5.0 tables via the manifest files.

**Amazon RDS Mysql and PostgreSQL AWS Graviton2 preview**

AWS Graviton2-based database instances in preview for Amazon Relational Database Service (RDS) now support more database versions. Graviton2 M6g and R6g database instances deliver better price performance over comparable current generation x86-based database instances. You can launch these database instances when using Amazon RDS for MySQL and Amazon RDS for PostgreSQL. With this launch, Graviton2 is now supported on RDS MySQL versions 8.0.17, 8.0.19, and 8.0.20 and RDS PostgreSQL 12.3, and 12.4. Support for Amazon Aurora and Amazon RDS for MariaDB is coming soon.

You can launch new instances in the Amazon RDS Management Console or using the AWS CLI. Upgrading a database instance to Graviton2 requires a simple instance type modification, using the same steps as any other instance modification. If you are currently on a relevant major version that is supported by Graviton2, such as RDS for MySQL 8.0.17, then you can move to Graviton2 by stopping the existing instance and changing the instance type to R6g or M6g instance using the AWS Management Console or AWS CLI. Your applications will continue to work as normal as you will not have to port any application code. For more details, refer to the documentation.  

**Amazon MSK**

Amazon Managed Streaming for Apache Kafka (Amazon MSK) can now authenticate Apache Kafka clients using usernames and passwords for new clusters, secured by AWS Secrets Manager. Username and password authentication uses SASL/SCRAM (Simple Authentication and Security Layer/Salted Challenge Response Authentication Mechanism), a popular authentication mechanism supported by Apache Kafka. By storing credentials in AWS Secrets Manager, you can reduce the overhead of maintaining a traditional Apache Kafka authentication system, including: auditing, updating, and rotating client credentials. You can also centrally and securely manage credentials for multiple clusters directly from the AWS Management console. SASL/SCRAM authentication can be used in all AWS regions where MSK is available.

**JetBrains IDE now support AWS SSO**

With this new release of the [AWS Toolkit for JetBrains](https://docs.aws.amazon.com/toolkit-for-jetbrains/latest/userguide/welcome.html), customers can use federated credentials, MFA and AWS Single Sign-On (AWS SSO) to connect their IDEs to AWS. Using AWS SSO, your organization's users can sign in to Active Directory, a built-in AWS SSO directory, or another external identity provider (IdP) connected to AWS SSO and get mapped to an AWS Identity and Access Management (IAM) role. Regardless of which IdP you use, AWS SSO abstracts those distinctions away, and they all work with the AWS Toolkit. The AWS Toolkit for JetBrains is an open-source plugin that lets you leverage the integrated development environment (IDE) for the creation, debugging, and deployment of software applications on Amazon Web Services, without leaving your code-authoring context. Check out the Setting AWS credentials for the AWS Toolkit for JetBrains section in the developer guide to get started. Install the AWS Toolkit and share your feedback using the feedback tool in the IDE plugin or submit feature requests and issues on [GitHub](https://github.com/aws/aws-toolkit-jetbrains/issues).

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen).