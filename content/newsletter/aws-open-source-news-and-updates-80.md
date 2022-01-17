---
title: 'AWS open source news and updates #80'
date: '2021-09-06'
tags : [ oss-newsletter, AWS Open Source ]
---
## September 6th, 2021 - Instalment #80

Newsletter #80.

So what delights does #80 of this newsletter offer this week? We have plenty of new open source projects, such as aws-o11y-recipes (observability recipes), dassana-io (contextual alerts), sgCheckup (security), aws-lambda-scheduler (developer tool to simplify scheduling of AWS Lambda functions), aacli (AWS cli authentication/SSO) as well as Terraform modules and AWS open source solutions covering Hugging Face, reporting on your AWS accounts and more. If you are more interesting in blog posts covering open source topics, we have posts from the AWS and community covering OpenSearch, GraphQL, Flutter, Apache Airflow, Debezium, Apache Kafka, Kubernetes, Packer, OpenTelemetry and many more. We also have a round up of posts covering last weeks GA announcement of Grafana. 


**Job of the week**

**[Principal Developer Advocate - Java Specialist](https://aws-oss.beachgeek.co.uk/ur)**

A new opening in my team has come up, for anyone in the Cambridge/Boston area in the US. As a Principal Developer Advocate in the AWS Developer Relations organisation, you will work to earn trust with Enterprise developers and the broader Java community through your technical leadership and expertise. This is a high-impact role that's well-suited to someone with domain-specific technical experience that enjoys sharing what they have learned in order to help users solve their technical issues and overcome any challenges they face. You will have the ability to influence and educate customers at every stage of their experience with technologies such as OpenJDK, Serverless, Containers, DevOps tools and more.

Check out the [job description](https://aws-oss.beachgeek.co.uk/ur) for more details, and please feel free to DM or email me with any questions you might have. 

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Oğuzhan Yılmaz, Michael Walmsley, Bhuvanesh R, Derek Bingham, Ankit Anand, Gold Fig Labs, Arkady Titenko, Oren Leung, Francesco Canessa, Eddie Pick, Dhawalkumar Patel, Kapil Shardha, Aravind Singirikonda, Juan Lamadrid, Andrew Hopp, Nicholas Knize, Pavan Kumar Sunder, Jon Slominski, Roy Kincaid, Eric Robertson, Ali Spittel, Aaron Todd, Ian Botsford, Ken Gilmer, Nicki Stone, John Woo, Gopalakrishnan Subramanian, Satheesh Kumar, Alolita Sharma, Nizar Tyrewall, Imaya Kumar Jagannathan, Michael Hausenblas, Danilo Poccia, Julia Hu, Matthieu Fuzellier, Srikanth Kodali, Yuxin Yang, Sheetal Joshi, Mike Stefaniak, Jayanth Varavani, Vimal Bagmar, Waleed Sarwari, and Santosh Vallurupalli.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest open source projects

**aws-o11y-recipes**

[aws-o11y-recipes](https://aws-oss.beachgeek.co.uk/up) this was the project I spent most time on last week, a new initiative/home to share recipes for observability (o11y) solutions at AWS. Currently this is covering six areas: **destinations** (Prometheus, Grafana, OpenSearch, CloudWatch and Jaeger), **agents** (AWS Distro for OpenTelemetry, Fluent Bit, CloudWatch agent and AWS X-Ray agent), **languages** (Java and Javascript currently, Python, .NET, Go and Rust to come), **infrastructure and databases** (Amazon RDS, DynamoDB and Managed Streaming for Apache Kafka), **compute** (AWS Batch, Amazon ECS and EKS, Amazon ElasticBeanstalk and AWS Lambda) and **compute engine** (AWS Fargate, Amazon EC2 and Amazon Lightsail). This repository will grow over time, so make sure to check it out, bookmark it and even better, why not contribute your own recipes. If you are using Python, .NET, Go or Rust, would be great to start adding those to the repo. To find out more and check out these recipes, head over to [AWS Observability Recipes](https://aws-oss.beachgeek.co.uk/uq)

**dassana-io**

[dassana-io](https://aws-oss.beachgeek.co.uk/vl) this is a new open source project from Dassana that looks interesting. From the [docs](https://aws-oss.beachgeek.co.uk/vm) 

> Dassana is on a mission to solve the alert fatigue problem. Now, more than ever before, it is easy to "scan" your environment for security issues and deploy threat detection tools. But as soon as you deploy these tools, you will find that they start generating too many alerts. Although most of the alerts are accurate, they still lack the necessary context to be of great help. For example, if you get an alert that an s3 bucket has been found public in your environment, you might drop everything and start investigating it. But what if you find that there is a website associated with the bucket? What if the bucket has a word public or static in it? Wouldn't it be great if the alert already had this context to begin with? That's what Dassana does. Dassana adds context to security alerts.

I am going to try and get this project up and running this week to find out more.

**sgCheckup**

[sgCheckup](https://aws-oss.beachgeek.co.uk/uj) another project from the folks at Gold Fig Labs, sgCheckup is a tool to scan your AWS Security Groups for a combination of open ports and attached Network Interfaces. The goal is to find anything listening on a port that you wouldn't consider safe. In addition to generating reports for security groups, sgCheckup can generate and run nmap to get specifics. Really loving the 80's demo scene logo/graphics on the README - I would love to know how you did that. More please!

![demo](https://user-images.githubusercontent.com/291215/131582460-4a581540-2f11-4c96-af54-a1e39961e69d.png)

**aws-lambda-scheduler**

[aws-lambda-scheduler](https://aws-oss.beachgeek.co.uk/vh) it would be nice if you could quickly configure any existing functions you have in AWS Lambda to work on a schedule. I know this has been something I have had to do. Whilst it is not a problem to do this, this handy open source project from 
Oğuzhan Yılmaz makes this painless. Deploy this function, and then to run your functions on a schedule, all you need to do is trigger this function with some configuration data. Example/docs will get you up and running in no time.

**aacli**

[aacli](https://aws-oss.beachgeek.co.uk/uk) Arkady Titenko has created this nice open source CLI tool allows you to programmatically authenticate into AWS accounts through IAM roles in a multi-account AWS Organizations setup, and requires MFA enabled for your account. This project was born from an effort to figure out a simple yet reasonably secure way of programmatic authentication into AWS environments with support for MFA authentication. Read more about this project in the notes, plenty of examples of how to use it.

**aws-perspective**

[aws-perspective](https://aws-oss.beachgeek.co.uk/ul) I have shared details about this project before, but [this tweet](https://twitter.com/toksvaeth/status/1431232907834765314) make me think that I should share it again incase anyone missed it the first time. AWS Perspective is a tool that quickly visualizes AWS Cloud workloads as architecture diagrams. You can use the solution to build, customize, and share detailed workload visualizations based on live data from AWS. The latest update to this project focuses heavily on cost related features that allow you to better understand your cloud billing.

![demo](https://github.com/awslabs/aws-perspective/blob/master/docs/screenshots/cost-dialog.png?raw=true)

**AWSTagsAsADatabase**

[AWSTagsAsADatabase](https://aws-oss.beachgeek.co.uk/um) Whilst I absolutely do not recommend anyone does this, this project from Oren Leung did make me smile this week. Following on from an ongoing joke of Amazon Route53 being a "database", now comes using AWS tags as a "database". Growing up in tech in the 80s and the demo scene, this kind of reminds me of the kinds of things that folks tried to do to show what was possible. Nice effort Oren.

**web-client-for-aws-transfer-family**

[web-client-for-aws-transfer-family](https://aws-oss.beachgeek.co.uk/v2) is an open source project that provides a web-based interface to consumers of your existing Transfer Family SFTP endpoints. You can read more details, including how to deploy this project, in the blog post, [Announcing the open-source release of Web Client for AWS Transfer Family](https://aws-oss.beachgeek.co.uk/v3) from Kapil Shardha, Aravind Singirikonda, and Juan Lamadrid.

![arch](https://d2908q01vomqb2.cloudfront.net/e1822db470e60d090affd0956d743cb0e7cdf113/2021/08/26/The-Web-Client-for-AWS-Transfer-Family-solution-deploys-multiple-AWS-resources-example-architecture-1-1024x600.png)

**terraform-ec2-docker-swarm**

[terraform-ec2-docker-swarm](https://aws-oss.beachgeek.co.uk/un) this project from Francesco Canessa helps you to deploy Docker Swarm terraform infrastructure on AWS.

**terraform-aws-dms**

[terraform-aws-dms](https://aws-oss.beachgeek.co.uk/vk) if you are looking for a way to provision your Database Migration Service via Infrastructure as Code using Terraform, then clowd.haus has you covered.

**amazon-sagemaker-huggingface-benchmark**

[amazon-sagemaker-huggingface-benchmark](https://aws-oss.beachgeek.co.uk/uo) this project will be of interesting if you are working on building NLP models with HuggingFace. It provides code to help you benchmark the trade-offs between cost, train time, and performance for fine-tuning HuggingFace models with distributed training on Amazon SageMaker. Detailed README to get you going.

**finetune-deploy-bert-with-amazon-sagemaker-for-hugging-face**

[finetune-deploy-bert-with-amazon-sagemaker-for-hugging-face](https://aws-oss.beachgeek.co.uk/uw) this project uses the Hugging Faces transformers and datasets library with Amazon SageMaker to fine-tune a pre-trained transformer on binary text classification. It uses the pre-trained DistilBERT model with the Amazon Reviews Polarity dataset. Eddie Pick and Dhawalkumar Patel have put together this blog post, [Fine-tune and host Hugging Face BERT models on Amazon SageMaker](https://aws-oss.beachgeek.co.uk/ux) to help walk you through the code.

![arch](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2021/08/31/ML3931-image005.png)

**greengrass-v2-sagemaker-edge-manager-python**

[greengrass-v2-sagemaker-edge-manager-python](https://aws-oss.beachgeek.co.uk/ut) this project uses two open source projects, AWS Greengrass v2 and NEO to demonstrate how to integrate them via components. At the end of the sample, you will have a Python-based component running inference at the edge with the SageMaker Edge Manager binary agent, and a YOLOv3 Darknet model. To help you get started with this project, check out the blog post [Build machine learning at the edge applications using Amazon SageMaker Edge Manager and AWS IoT Greengrass V2](https://aws-oss.beachgeek.co.uk/uu) from Pavan Kumar Sunder and Jon Slominski.

![arch](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2021/08/31/ml2780-image001.png)

### Hot topics

**Grafana**

Announced during re:Invent 2020 in preview, last week saw the general availability announcement for Amazon Managed Grafana, a fully managed service developed in collaboration with Grafana Labs that makes it easy to use the open-source and the enterprise versions of Grafana to visualize and analyze your data from multiple sources. 

We had several posts covering this, with my colleague Danilo Poccia's sharing the news in [Amazon Managed Grafana Is Now Generally Available with Many New Features](https://aws-oss.beachgeek.co.uk/v6). The GA announcement saw plenty of additional new features, and in the post, [Amazon Managed Grafana is now Generally Available](https://aws-oss.beachgeek.co.uk/v7), Imaya Kumar Jagannathan and Michael Hausenblas dive a little deeper into the launch, including the new features that have been added.

Sunil Ramachandra and Roy Rodan walk you through the steps required to integrate your identity provider with Amazon Managed Grafana, in the post [Amazon Managed Grafana supports direct SAML integration with identity providers](https://aws-oss.beachgeek.co.uk/v8). They show you how you can assign users and appropriate roles through your identity provider so that your users can seamlessly authenticate into the Amazon Managed Grafana environment to visualise and monitor your workloads and log.

Finally, we had Julia Hu, Matthieu Fuzellier, Srikanth Kodali, and Yuxin Yang collaborate on this post, [How to use InfluxDB and Grafana to visualize ML output with AWS IoT Greengrass](https://aws-oss.beachgeek.co.uk/v9) where they show how to build an end-to-end workflow using open source tools with AWS IoT Greengrass version 2 to visualise ML inference results in near real-time on an edge device. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/08/30/juliahu_influxdb-grafana-greengrass_f1.png)

### AWS and Community blog posts

**Apache Airflow**

Mikaela Pisani has put together this blog post, [How to run Airflow, Spark, & Apache Livy in AWS EKS](https://aws-oss.beachgeek.co.uk/va), where she walks you through each of these open source components and then how you can run them on Amazon EKS to address some specific results such as scalability, traceability, isolation and speed of processing. 

**Debezium / Apache Kafka**

Debezium is an open source distributed platform for change data capture. Bhuvanesh R shares his experiences (and helps you avoid the issues he came across) as he walks you through how to integrate Debezium with AWS Managed Streaming for Kafka IAM authentication, in his post [Debezium With AWS MSK IAM Authentication](https://aws-oss.beachgeek.co.uk/vb). [hands on]

![arch](https://thedataguy.in/assets/aws/Debezium%20With%20AWS%20MSK%20IAM%20Authentication.jpg)

**PostgreSQL**

Gopalakrishnan Subramanian and Satheesh Kumar explain how to combine HAProxy with a lightweight connection pool handler PgBouncer as a sidecar to load balance the connections to Aurora reader nodes in the blog post, [Set up highly available PgBouncer and HAProxy with Amazon Aurora PostgreSQL readers](https://aws-oss.beachgeek.co.uk/v5) [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2021/08/09/DBBLOG-1153-image005_v2-1024x680.png)

**Amazon ECS**

John Preston is back with more blogging goodness, this time helping you to get Traefik up and running within your Amazon ECS environments in, [Traefik Proxy in AWS with AWS ECS - Part 1](https://aws-oss.beachgeek.co.uk/vc). When I asked John what Traefik was, he pointed me to the project page but did say that this project "makes network boring" - anything that makes anything boring, also makes my life easier, so make sure you check this post out. John's post are always great to read. [hands on]

![arch](https://labs.compose-x.io/_images/TraefikPart1.png)

**Kubernetes**

The VPC Container Networking Interface (CNI) Plugin is the open source component that provides a networking plugin for pod networking in Kubernetes using Elastic Network Interfaces on AWS. In the post, [Amazon VPC CNI plugin increases pods per node limits](https://aws-oss.beachgeek.co.uk/vj), Sheetal Joshi, Mike Stefaniak, and Jayanth Varavani walk you through some recent enhancements that improve capacity and dive deep into the details of the implementation.

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2021/09/03/image-8-1.png)

**Packer**

Packer is an open-source tool developed by HashiCorp for creating identical machine images for multiple platforms from a single source configuration. In this post, [Migrating from HashiCorp Packer to EC2 Image Builder](https://aws-oss.beachgeek.co.uk/vi), Vimal Bagmar, Waleed Sarwari, and Santosh Vallurupalli walk you through how to migrate Packer template build components specifically for commonly used Packer Provisioners, such as Ansible, Chef, Shell, and Files to their corresponding EC2 Image Builder components.

![arch](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2021/09/02/Picture2.png)

**AWS Lambda Powertools** 

Michael Walmsley provides a great primer on Idempotency in hist post, [Making All Your APIs Idempotent](https://aws-oss.beachgeek.co.uk/ve). From what it is to why you should care, he also shares how you can use AWS Lambda Powertools for Python to make it easy when creating an idempotent API. [hands on]

![arch](https://miro.medium.com/max/1022/1*uw-EGaoznpKe25eaQqKYcg.jpeg)

**Flutter**

Want to know what a BLoc pattern is? I was certainly curious, and in this post, [Using the Flutter BLoC Pattern with AWS Amplify Datastore](https://aws-oss.beachgeek.co.uk/vf) my good friend Derek Bingham walks you through an example of the BLoC pattern, how you can use it to improve your use of AWS Amplify Datastore API calls, to be a lot cleaner and so easier to maintain. [hands on]

![arch](https://res.cloudinary.com/practicaldev/image/fetch/s--X02BneBS--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/pkrotfsyacotuof5uf2h.png)

**GraphQL**

One of my favourite posts in recent weeks, Ali Spittel has put together [A Complete Beginner's Guide to GraphQL](https://aws-oss.beachgeek.co.uk/uz) which will get you up and running quickly on this topic.

Now that you know more about GraphQL, Eric Robertson has put together this blog post, [Implementing caching for pipeline resolvers in AWS AppSync GraphQL APIs](https://aws-oss.beachgeek.co.uk/uy) that shows how to use caching for pipeline resolvers to unlock lower latency with less requests to backend data sources, and can help reduce costs when using pipeline resolvers in AppSync to orchestrate and connect data from multiple data sources with a single GraphQL API call. 

**OpenTelemetry**

Ankit Anand has put together this post, [Everything you need to know about OpenTelemetry Collector](https://aws-oss.beachgeek.co.uk/vg) that provides a clean and simple guide to understanding more about what OpenTelemetry is, the architecture, why you should care and then how to get started. Worth 5 minutes of your time. 

In this weeks winner of longest blog title competition, Alolita Sharma and Nizar Tyrewall share the release highlights from version 0.12 of AWS Distro for OpenTelemetry in the post, [AWS Distro for OpenTelemetry 0.12 adds metrics support for AWS Lambda, Amazon ECS on EC2 metrics, and Amazon EKS metrics in Amazon Managed Prometheus (Preview)](https://aws-oss.beachgeek.co.uk/v4). Amazon Elastic Kubernetes Service (Amazon EKS) Infrastructure metrics and trace collection, AWS Lambda layers supporting metrics collection for Amazon Managed Service for Prometheus (AMP) and Amazon Elastic Container Service (Amazon ECS) running on Amazon Elastic Cloud Compute (Amazon EC2) container metrics are the three covered, so click on the link to find out more.

**OpenSearch**

How many times have you wondered how a piece of technology or software you use works, from end to end? In this post, [A query, or There and Back Again](https://aws-oss.beachgeek.co.uk/us) Andrew Hopp and Nicholas Knize tell the story of how a query works in OpenSearch by following a query through OpenSearch

**AWS SDKs**

We had a couple of alpha release announcements this week.

Start off with this post from Aaron Todd, Ian Botsford, and Ken Gilmer, in [Announcing new AWS SDK for Kotlin alpha release](https://aws-oss.beachgeek.co.uk/v0) they cover how the AWS SDK for Kotlin makes it easy to call AWS services using idiomatic Kotlin APIs. You can use the native Kotlin language constructs you are used to, have mobile support without compromises, and target multiple platforms and execution environments in a single language.

Following that we had Nicki Stone and John Woo with [Announcing new AWS SDK for Swift alpha release](https://aws-oss.beachgeek.co.uk/v1). This helps customers developing in Swift that have asked for a native Swift SDK so they can use the language constructs they are used to, and provides an SDK that behaves similarly to SDKs they have used in other language environments. 

With post of these announcements, the SDK's are still in the early stages of development. This is a great time to influence the roadmap by sharing your thoughts on the SDK design, as well as features and services that are the most important to you. Make sure you use the links in the post to provide your ideas or feedback.

**MQTT**

We recently announced the general availability of MQTT retained messages for AWS IoT Core. This feature allows you to store a single message per a given MQTT topic for delivery to any current and future topic subscribers. In this post, [Getting started with MQTT retained messages for AWS IoT Core](https://aws-oss.beachgeek.co.uk/uv) Roy Kincaid provides an overview of this feature, share some use cases to keep in mind when designing your next IoT project, and provide a guide on how to get started. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/f6e1126cedebf23e1463aee73f9df08783640400/2021/09/01/getting-started-with-retained-messages-01.png)

**ROS**

Whilst this post, [Introduction to ROS: The Robot Operating System](https://aws-oss.beachgeek.co.uk/vd) is not AWS specific, AWS RoboMaker and Amazon have been working with this open source project/foundation for some time, and this tutorial/course is a great primer/introduction if you are interested in open source robotics. You will need to register (I did mine via LinkedIn) and the course covers the basics you need to get started. The course also links to various pieces of hardware that you will need.

### Quick updates

**MariaDB**

Amazon Relational Database Service (Amazon RDS) for MariaDB now supports MariaDB minor versions 10.5.12, 10.4.21, 10.3.31, and 10.2.40. We recommend that you upgrade to the latest minor versions to fix known security vulnerabilities in prior versions of MariaDB, and to benefit from the numerous bug fixes, performance improvements, and new functionality added by the MariaDB community.

**PostgreSQL**

Amazon Aurora PostgreSQL-Compatible Edition now supports PostgreSQL major version 13. PostgreSQL 13 includes improved functionality and performance from enhancements such as de-duplication of B-tree index entries, improved performance for queries that use partitioned tables, incremental sorting to accelerate data sorts, parallel processing of indexes with the VACUUM command, more ways to monitor activity within a PostgreSQL database, new security capabilities, and more. This release also adds support for bool_plperl, which simplifies writing Perl procedures.

With PostgreSQL 13 on Aurora PostgreSQL-Compatible Edition you can create time series data tables with improved data ingestion rates of several hundred thousands of metrics per second for use cases such as storing DevOps metrics or tracking business metrics (e.g., daily sales).

**AWS Copilot**

Version 1.10 of AWS Copilot was released with support for publish/subscribe architectures that customers can use to decouple microservices and consume events asynchronously. Customers can now use AWS Copilot to build event-driven architectures or to decouple services in order to increase performance, reliability, and scalability.

All existing AWS Copilot services and jobs can use the new publish field to broadcast events to Amazon Simple Notification Service (Amazon SNS) topics. These events can then be received via Amazon Simple Queue Service (Amazon SQS) queues with the new "Worker Service" pattern in AWS Copilot for Amazon Elastic Container Service (Amazon ECS) services running on AWS Fargate.

AWS Copilot v1.10 also adds a new field taskdef_overrides in the manifest file to allow customers to add all fields supported by Amazon ECS task definitions that are not surfaced in the manifest. This enables customers to use configurations available for Amazon ECS (such as the ulimit parameter which allows customers to change default resource limit values) for their AWS Copilot jobs and services which are not supported in AWS Copilot directly. Additionally, the alias field for request and load balanced services has been augmented to accept a list of friendly domain names instead of a single entry.

### Events for your diary

**Cloud DevSecOps with Bridgecrew and Terraform**
**8th September, 9am PST**

From scanning infrastructure as code (IaC) for security misconfigurations to implementing automated DevSecOps workflows, this workshop will provide a hands-on experience to automate your cloud security. Find out more and [register via this link](https://aws-oss.beachgeek.co.uk/ud).

**Cloud Native Day**
**23rd September, Bern Switzerland**

What is this, an in person event returning? A stellar line up including our own Michael Hausenblas, an event looking at CNCF projects and the future of IT. Find out more and to view prices/register, by clicking [here](https://cloudnativeday.ch/en/#speakers).

**GraphQL API security best practices with AWS AppSync and AWS Amplify**
**14th October, 11am AEST**

As a developer, the most important parts of managing your applications should always include enhancing performance while strengthening security. In this webinar, we take you through security best practices for your GraphQL API’s with AWS AppSync and AWS Amplify, providing you with an understanding of how these can be applied to your applications. In this session, you will learn about:

* GraphQL Protocol and how to configure a schema
* Possible ways to authenticate and authorise access to GraphQL APIs
* How to configure network security for your API
* How to enable observability for your API with logging, tracing or auditing

To [register for this event, use this link](https://aws-oss.beachgeek.co.uk/ue).

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)