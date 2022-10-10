---

title: 'AWS open source news and updates #130'
date: '2022-10-10'
tags : [ oss-newsletter, aws open source, Apache Flink, Apache Kafka, Spring Boot, OpenSearch, Kubeflow, Kubernetes, Porting Assistant for .NET, AWS Copilot, PostgreSQL, Karpenter, AWS CDK, MariaDB, MySQL, Amazon Corretto, Apache Hudi, NextJS, AWS IoT Greengrass]

---

## October 10th, 2022 - Instalment #130

**Welcome**

Welcome to the AWS open source newsletter, edition #130. This newsletter was featured in the Build on Open Source episode four, [which you can check out here](https://www.twitch.tv/videos/1611856476) if you missed it.

New projects for you to practice your open source four freedoms this week include "grucloud" a new infrastructure as code tool with some nice features, "stepfunctions-sdk-autocomplete" a VSCode plugin for all you AWS Step Functions fans, "AWS_Billing_Overage_Shutdown" a very new repo that has some code to help you automate shutting down resources on alerts, "aws-secrets-manager-github-action" if you are using GitHub Actions, this one is for you, "meta-aws", tools and recipes for those using and building with Yocto, "data-on-eks" a number of sample solutions to configure self managed open source data analytics tools, "cql-replicator" a tool to help you migrate from self managed Apache Cassandra to Amazon Keyspaces, "ec2-imagebuilder-ami-lifecycle" provides some new capabilities for those building AMIs, and many more.

This weeks featured blog posts cover a broad range of open source technologies and projects including Apache Flink, Apache Kafka, Spring Boot, OpenSearch, Kubeflow, Kubernetes, Porting Assistant for .NET, AWS Copilot, PostgreSQL, Karpenter, AWS CDK, MariaDB, MySQL, Amazon Corretto, Apache Hudi, NextJS, AWS IoT Greengrass.

Finally, do not miss this weeks Events section. There are so many events happening, check them out and save your spot.


**Feedback**

Please let me know how we can improve this newsletter as well as how AWS can better work with open source projects and technologies by completing [this very short survey ](https://eventbox.dev/survey/NUSZ91Z)that will take you probably less than 30 seconds to complete. Thank you so much!

**Celebrating open source contributors**

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created. 

So thank you to the following open source heroes: Lars Jacobsson, Makendran G, Ali Alemi, Sam Mokhtari, Subham Rakshit, Jignesh Suthar, Efe Karakus, Sergey Generalov, Mark Sailes, Serkat Ozal, Vadym Kazulkin, Goran Opacic, Makendran G, Tao Liu, Ran Isenberg, Vishal Pathak, Anand Prakash, and Noritaka Sekiyama.

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution.*

#### Tools

**grucloud**

[grucloud](https://aws-oss.beachgeek.co.uk/24h) is a low/no-code infrastructure as a code tool. It can generate code from live infrastructure, and deploy resources to the cloud from code. This works with AWS and other Cloud providers, and also support Kubernetes. One of the nice things I can see is that it generates graphs and diagrams. For example, you can visualise like this:

![graphviz of grucloud](https://raw.githubusercontent.com/grucloud/grucloud/main/examples/aws/EC2/ec2-vpc/artifacts/diagram-live.svg)

Of if you prefer, a mind map

![mind map example](https://raw.githubusercontent.com/grucloud/grucloud/main/examples/aws/EC2/ec2-vpc/artifacts/resources-mindmap.svg)

Looks like an interesting project.

**stepfunctions-sdk-autocomplete**

[stepfunctions-sdk-autocomplete](https://aws-oss.beachgeek.co.uk/24f) AWS Community Builder Lars Jacobsson has been back in his open source forge and minted another great open source tool. You can also grab it directly from the Visual Studio Code marketplace page, [StepFunctions SDK Integrations Autocomplete](https://aws-oss.beachgeek.co.uk/24g)

![demo of visual studio autocomplete plugin](https://github.com/ljacobsson/stepfunctions-sdk-autocomplete/raw/HEAD/images/demo.gif)

**AWS_Billing_Overage_Shutdown**

[AWS_Billing_Overage_Shutdown](https://aws-oss.beachgeek.co.uk/24c) this repo contains the starting of a tool that scripts the automatic shutting down of AWS EC2 instances based on billing alerts. You will need to do some work as what is provided is some code and documentation, but if you like this why not get involved and help shape it. Check out [the discussion on Reddit](https://aws-oss.beachgeek.co.uk/24d) to find out more and have your say.

**aws-secrets-manager-github-action**

[aws-secrets-manager-github-action](https://aws-oss.beachgeek.co.uk/24e) lets you use a secret in a GitHub job, you can use a GitHub action to retrieve secrets from AWS Secrets Manager and add them as masked Environment variables in your GitHub workflow. When you add a secret to your GitHub environment, it is available to all other steps in your GitHub job. Make sure you check out the docs to find out about how to follow best practices and hardening of your GitHub Actions.

**meta-aws**

[meta-aws](https://aws-oss.beachgeek.co.uk/24b) the meta-aws project provides recipes for building in AWS edge software capabilities to Embedded Linux built with OpenEmbedded and Yocto Project build frameworks. This repo links to a number of demos that show machine specific demonstrations (including one for the Raspberry Pi) for AWS software on Embedded Linux built by the Yocto Project build framework with the meta-aws Metadata Layer.

**data-on-eks**

[data-on-eks](https://aws-oss.beachgeek.co.uk/24i) is a tool to build, deploy and scale Data Platforms on Amazon EKS. Data on Amazon EKS(DoEKS) helps users to build AWS managed and self-managed scalable data platforms on Amazon EKS. This repo provides Infrastructure as Code(IaC) templates(e.g., Terraform, AWS CDK etc.), sample Apache Spark/ML jobs, references to AWS Data blogs, Performance Benchmark reports and Best Practices for deploying Data Solutions on Amazon EKS. It currently covers Apache Airflow, Amazon EMR, Apache Spark and Ray. If you do any work with data you should check out this repo which will help accelerate you to build your solutions.

**cql-replicator**

[cql-replicator](https://aws-oss.beachgeek.co.uk/24j) is a migration tool that helps to replicate data to Amazon Keyspaces. The project aims to help customers to migrate from the self-managed Cassandra to Amazon Keyspaces with zero downtime, for example, customers can replicate the Cassandra workload in low seconds to Amazon Keyspaces with no code changes on the client side. Moreover, customers can scale migration workload by spinning more CQLReplicator instances, where a CQLReplicator instance is a java process that responsible for a certain set of token ranges (partition keys/rows). If the CQLReplicator fails you can restart the migration process from where it was interrupted by rebooting a failed CQLReplicator instance.

**ec2-imagebuilder-ami-lifecycle**

[ec2-imagebuilder-ami-lifecycle](https://aws-oss.beachgeek.co.uk/24q) Managing the lifecycle of AMI (Amazon Machine Image)s is a common requirement for many of our customers. An AMI lifecycle can include lifecycle events such as building, verifying, testing, vulnerability scanning, certifying, approving, and patching. This guide, and accompanying source code, describes an approach to managing AMI lifecycles by extending the capabilities of EC2 Image Builder and offering several additional features. So make sure you check this project out to find out more about those new features (no spoilers!)

![architecutre of ec2 imagebuilders](https://github.com/aws-samples/ec2-imagebuilder-ami-lifecycle/blob/main/docs/assets/solution_architecture.png?raw=true)

**euc-toolkit**

[euc-toolkit](https://aws-oss.beachgeek.co.uk/24s) Administrators can reduce self-managed VDI operational overhead by using End User Computing (EUC) managed services. The EUC Toolkit was created to provide additional features for admins managing Amazon WorkSpaces and Amazon AppStream 2.0 environments. The solution can be completely customised to meet business needs. The EUC toolkit is built on PowerShell using the Windows Presentation Framework (WPF) to display a graphical user interface (GUI). In addition, the solution has been modularised to to allow for changes and customisations.

![demo of euc toolkit](https://d2908q01vomqb2.cloudfront.net/827bfc458708f0b442009c9c9836f7e4b65557fb/2022/09/22/ToolkitGUI-1024x657.png)

### Demos, Samples, Solutions and Workshops

**water-tank-digital-twin**

[water-tank-digital-twin](https://aws-oss.beachgeek.co.uk/24r) if you have been to any AWS events such as the AWS Summits or re:Invent then there is a good chance you might have seen this project. I have had some time to play with the real thing, and it is super cool. From the folks at the Prototyping team, this Water Tank demo is a fully functioning water system including a supply tank, a storage tank and pumps to exchange water between the two reservoirs. It allows the monitoring in Virtual Reality of flow rates, water volume in the reservoirs, temperature, and leaks.

![water tank digital twin demo](https://github.com/aws-samples/water-tank-digital-twin/blob/main/doc/images/watertank.png?raw=true)

**amazon-api-gateway-powered-browser-extension**

[amazon-api-gateway-powered-browser-extension](https://github.com/aws-samples/amazon-api-gateway-powered-browser-extension) provides sample code that allows you to quickly deploy a Firefox Extension that uses Serverless AWS Services as a backend. This example allows users to translate selected text on a loaded webpage. The extension sends requests to an API Gateway which forwards them to a Lambda Function. The Lambda Function then translates the text using Amazon Translate and returns it to the user's browser to be displayed on screen.

![screen shot of browser extension](https://github.com/aws-samples/amazon-api-gateway-powered-browser-extension/blob/main/demo.png?raw=true)

**amazon-cloudwatch-alarm-formatted-email**

[amazon-cloudwatch-alarm-formatted-email](https://aws-oss.beachgeek.co.uk/24p) This solution enables you to customize CloudWatch alarm email alerts using Amazon Simple Email Service (Amazon SES) and AWS Lambda. You will be able to extract the relevant bits of information that you need from the alarm message and display them in an easy-to-read HTML format.

![architecture of solution](https://github.com/aws-samples/amazon-cloudwatch-alarm-formatted-email/blob/main/CloudWatchAlarmFormattedEmail-ArchitectureDiagram.png?raw=true)

**aws-rtb-intelligence-kit**

[aws-rtb-intelligence-kit](https://aws-oss.beachgeek.co.uk/24k) provides a sample repo that you might find interesting if you work in adtech. With one CDK application, a data scientist can deploy an end-to-end pipeline with pre-configured use cases, and can adapt the kit to their particular needs. The pre-configured use case at launch is bid filtering - predicting the likelihood of a bidder to make a bid on a given bid request. The pipeline is easily adaptable to other use cases common in the industry. By launching the kit as an open source project, users can contribute back their own adaptations and implementations in this growing industry.

![architecture of adtech sample proejct](https://github.com/aws-samples/aws-rtb-intelligence-kit/blob/main/assets/traffic-filtering-server-view.png?raw=true)

### AWS and Community blog posts

**AWS CDK**

AWS Community Builder Ran Isenberg is back with a new blog post, [AWS CDK - Best Practices From The Trenches](https://aws-oss.beachgeek.co.uk/24o) where he walks you through five current good practices that he suggestions you should be reviewing. In the post he covers Project Structure and stack guidelines, Constructs guidelines, CI/CD guidelines, Resiliency & Security, and General development tips.

**OpenSearch**

A hat tip to Adrien Sales for sharing this post with me. Tao Liu writes [Launch Highlight: OpenSearch Playground](https://aws-oss.beachgeek.co.uk/24m) where he shares the announcement of the live demo environment of OpenSearch and OpenSearch Dashboards. OpenSearch Playground provides a central location for existing and evaluating users to explore features in OpenSearch and OpenSearch Dashboards without installing or downloading anything. You can access OpenSearch Playground at [playground.opensearch.org](https://aws-oss.beachgeek.co.uk/24n).

![example of playground screenshot](https://opensearch.org/assets/media/blog-images/2022-09-26-opensearch-playground/observability.png)

**Karpenter**

AWS Community Builder Makendran G dives deep in Karpenter in his post, [A Deep Dive Into Just-in-Time Worker Nodes With Karpenter](https://aws-oss.beachgeek.co.uk/24l). In this guided walk through, he shows you how easy it is to deploy and configure the autoscaling of Kubernetes nodes using this open source project. Make sure you check this post out. [hands on]

**Apache Flink**

In the post [Common streaming data enrichment patterns in Amazon Kinesis Data Analytics for Apache Flink](https://aws-oss.beachgeek.co.uk/241), Ali Alemi, Sam Mokhtari, and Subham Rakshit explore different data enrichment patterns in Kinesis Data Analytics for Apache Flink and how you can use these patterns and find the one that addresses your needs to accelerate how you can develop a stream processing application.

![Apache Flink data enrichment patterns diagram](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2022/09/27/BDB-2199-image001.png)

**Apache Hudi**

Apache Hudi is an open-source data management framework designed for data lakes. It simplifies incremental data processing by enabling ACID transactions and record-level inserts, updates, and deletes of streaming ingestion on data lakes built on top of Amazon S3. In this post, [Ingest streaming data to Apache Hudi tables using AWS Glue and Apache Hudi DeltaStreamer](https://aws-oss.beachgeek.co.uk/24w) Vishal Pathak, Anand Prakash, and Noritaka Sekiyama collaborate to show you how to run DeltaStreamer (one of the tools that is part of Apache Hudi) to read streaming data from Amazon Managed Streaming for Apache Kafka (Amazon MSK) and ingest the data into S3 data lakes. [hands on]

![apache hudi and datastreamer architecture](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2022/09/26/bdb-2298-image001.png)

**Porting Assistant for .NET**

Porting Assistant for .NET is an open source analysis tool that reduces the manual effort and guesswork involved in porting .NET Framework applications to .NET 6, helping customers move to Linux faster. In the post, [Port legacy VB.NET applications to .NET 6.0 with Porting Assistant for .NET](https://aws-oss.beachgeek.co.uk/246) Jignesh Suthar provides a quick tutorial on how to port a well known VB.NET application to .NET 6.0 [hands on]

**Other posts you might like from the past week**

* [Build an efficient development environment for AWS IoT Greengrass](https://aws-oss.beachgeek.co.uk/24y) is a great guide on how to set up a clean and efficient development environment for AWS IoT Greengrass [hands on]
* [Building a full-stack chat application with AWS and NextJS](https://aws-oss.beachgeek.co.uk/24x) walks you through how to build scalable chat applications that contain the rich set of features [hands on]
* [Stream data with Amazon DocumentDB and Amazon MSK using a Kafka connector](https://aws-oss.beachgeek.co.uk/249) shows you how to run and configure the MongoDB Kafka connector to move data between Amazon DocumentDB and Amazon MSK for sink and source use cases [hands on]

![stream data with documentdb and msk](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2022/09/21/DBBLOG-2263-image001.png)

* [Build flexible and scalable distributed training architectures using Kubeflow on AWS and Amazon SageMaker](https://aws-oss.beachgeek.co.uk/244) demonstrates how Kubeflow on AWS (an AWS-specific distribution of Kubeflow) used with AWS Deep Learning Containers and Amazon Elastic File System (Amazon EFS) simplifies collaboration and provides flexibility in training deep learning models at scale on both Amazon Elastic Kubernetes Service (Amazon EKS) and Amazon SageMaker [hands on]

![architecture of kubeflow on aws](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2022/09/23/Solution.png)

* [Integrating SpringBoot Apps on a secured Amazon OpenSearch application](https://aws-oss.beachgeek.co.uk/245) is a hands on guide on how to create a Spring Boot RESTful Web Service, allowing end-user applications to securely interact with data stored in Amazon OpenSearch service [hands on]
* [Getting visibility into your Amazon EKS Cross-AZ pod to pod network bytes](https://aws-oss.beachgeek.co.uk/24v) provides a cross-AZ, pod-to-pod network bytes visibility inside an Amazon EKS cluster using the AWS VPC CNI plugin [hands on]

![architecture of solution for visibility in your container](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2022/10/04/kobi-1.png)

* [Amazon EKS on AWS Outposts now supports local clusters](https://aws-oss.beachgeek.co.uk/247) dives deep and shows you how to run Amazon EKS on AWS Outposts [hands on]

![architecture of amazon eks on outposts](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2022/09/29/sheetal-1.png)

* [Bootstrapping multiple AWS accounts for AWS CDK using CloudFormation StackSets](https://aws-oss.beachgeek.co.uk/248) teaches you how to bootstrap many AWS accounts in an automated and consistent manner using CloudFormation StackSets [hands on]

![aws cdk and cf stacksets](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2022/10/04/cloudops_2180_1.png)

* [Migrate Oracle’s XMLDOM package functions to Amazon Aurora PostgreSQL using JSON format](https://aws-oss.beachgeek.co.uk/24a) shares a solution to migrate Oracle’s DBMS_XMLDOM package functions to Aurora PostgreSQL or Amazon RDS for PostgreSQL using the JSON data type [hands on]

**Case studies**

In [FSI Service Spotlight: Amazon Managed Streaming for Kafka (MSK)](https://aws-oss.beachgeek.co.uk/242) reviews Amazon MSK and highlights key information that can help Financial Services Industry (FSI) customers accelerate the approval of the service within these five categories: achieving compliance, data protection, isolation of compute environments, automating audits with APIs, and operational access and security. 

### Quick updates

**MariaDB**

Amazon Relational Database Service (Amazon RDS) for MariaDB now supports MariaDB minor version 10.6.10. We recommend that you upgrade to the latest minor versions to fix known security vulnerabilities in prior versions of MariaDB, and to benefit from the numerous bug fixes, performance improvements, and new functionality added by the MariaDB community.

**MySQL**

Amazon Relational Database Service (Amazon RDS) for MySQL now supports MySQL minor version 5.7.39. We recommend that you upgrade to the latest minor versions to fix known security vulnerabilities in prior versions of MySQL, and, to benefit from the numerous fixes, performance improvements, and new functionality added by the MySQL community.

### Videos of the week

**AWS Java Panel**

If you missed the event, join a stellar list of long time Java specialists such as Mark Sailes, Serkat Ozal, Vadym Kazulkin, Goran Opacic as they talk through a number of topics such as Java 17 and 19, the impact of GraalVM, Powertools for Java and much more. If you love Java, do not miss this session.

{{< youtube APT2UKRtaWI >}}


**AWS Copilot**

Find out the latest updates in AWS Copilot release v1.22 from Efe Karakus, Senior Software Engineer (@efekarakus) and Sergey Generalov, Sr. Product Manager (@genbit). For those unfamiliar with AWS Copilot, is an open source command line interface that makes it easy for developers to build, release, and operate production ready containerised applications on AWS App Runner, Amazon ECS, and AWS Fargate.

{{< youtube Pc3sG6dUl5o >}}

**Build on Open Source**

If you want to catch up with the latest episode (the fourth) where we speak with AWS Data Hero Alvaro Hernandez, [check out the video via Twitch](https://www.twitch.tv/videos/1611856476). This is a great episode and Alvaro dives deep into StackGres, showing how you can run PostgreSQL on Kubernetes like a pro.

We have put together a playlist so that you can easily access all episodes of the Build on Open Source show. For those unfamiliar with this show, it is where we go over this newsletter and then invite special guests to dive deep into their open source project. Expect plenty of code, demos and hopefully laughs.

[Build on Open Source playlist](https://aws-oss.beachgeek.co.uk/24u)

# Events for your diary

**Hacktoberfest**

Our friends at Steampipe are participating in Hacktoberfest this year, and have put together a page on how you can earn swag for contributions. Check it out for more details, [Hacktoberfest 2022: Steampipe](https://aws-oss.beachgeek.co.uk/24t)


**The Present and The Future of Infrastructure as Code**
**October 11th, 6 PM, Paris**

This promises to be a great meet-up and essential attendance if you are into infrastructure as code. AWS Hero Anton Babenko hosts this event, sponsored by Qovery.

Read more and register for this event by heading over to [their meet-up page](https://aws-oss.beachgeek.co.uk/220).

**Dev Day Workshop: Deploy, Manage and Scale Kubernetes to AWS EKS with GitLab**
**October 11th, 11:45am PT**

This four hour hands-on workshop is designed for development teams planning projects involving AWS EKS clusters. Join industry-leading experts from AWS and GitLab for a hands-on workshop that will enable you to deploy secure applications to AWS Elastic Kubernetes Service in record time. This is an in person workshop, so if you are near SJC18 2100 University Ave, East Palo Alto, CA 94303 then check this out.

Find out more and [save your spot here](https://aws-oss.beachgeek.co.uk/22w).

**Build on AWS with Quarkus Workshop**
**Saturday, Oct 15th 3 - 9 pm CET**

"Build on AWS with Quarkus Workshop", with Julio Faerman, is a 100% practical, full-day workshop to get YOUR web application started and running on AWS, using modern Java with Quarkus and other open-source technologies. We'll start from scratch and build a sample application, step by step, so do not worry if you're new to Java or Cloud Computing. All you'll need is a web browser, an AWS account and your desire to build.

Check out more details and save your place, by heading over to the [Build on AWS with Quarkus Workshop landing page](https://aws-oss.beachgeek.co.uk/23z).

**Build Flutter apps with AWS Amplify for mobile, web, and desktop platforms**
**October 17th, 11am PT**

Building cross-platform apps is becoming increasingly prominent when building products. This is due to the cost savings and operational efficiency builders get from building apps that target multiple platforms such as mobile (iOS/Android), web, and desktop (Windows, MacOS, Linux). The Amplify Libraries allow developers to connect their Flutter apps to an AWS backend for building features such as Authentication, storage, and Data interchange operations. In this session, we'll show you can quickly build a feature-rich cross-platform apps that works across mobile, web, and desktop from a single codebase that delight your customers.

You can [register for this Webinar here](https://aws-oss.beachgeek.co.uk/22v).

**AWS Community Day**
**Dresden, Germany 19th October**

Check out this all day AWS Community driven and run event that features plenty of open source technologies. From open observability, AWS CDK, GitOps using Argo, there are is something for everyone. If you are in Dresden Germany, one to check out.

Find out the full schedule and sign up by checking out the [welcome page here](https://aws-oss.beachgeek.co.uk/240).

**Accelerating Adoption of AWS Open-Source Observability Services**
**October 20th, 9am PT**

Join this online tech talk to learn how you can leverage AWS managed open-source observability solutions to monitor your containerised or serverless workloads at scale. Unlock observability functionalities in Amazon Managed Service for Prometheus, Amazon Managed Grafana, and AWS Distro for OpenTelemetry and learn how our managed solutions can help you improve MTTD and reduce MTTR, saving you time and money. We’ll demo the Amazon Elastic Kubernetes Service Observability Accelerator and also share what’s new and upcoming in AWS Open-Source Observability.

Find out more and [register via this link](https://aws-oss.beachgeek.co.uk/22u).

**Build on AWS Open Source**
**October 21st, 9am BST**

Join us for the fifth episode of the Build on AWS series, featuring a live round up of the latest projects and news as well as a special guest speaker. We have another special guest lined up, more details to follow. Follow the show on @buildonopen for more details. Check it out on https://twitch.tv/aws

**KubeCon and CloudNativeCon North America**
**October 24th-28th, Detroit USA**

Check out this blog post from Nathan Taber, [AWS at KubeCon + CloudNativeCon North America 2022](https://aws-oss.beachgeek.co.uk/243) to hear more about what you can expect from AWS at this event, including Container Day. If you are going check this post out to see how you can reserve a spot to speak with one of the AWS specialists who will be at the booth.


**What's new in Amazon Aurora MySQL version 3**
**October 25th, 9am PT**

Amazon Aurora MySQL version 3 compatible with MySQL 8.0, is the latest version of Aurora MySQL. Come learn what makes this the best version of Aurora MySQL to run your relational database workloads. You will learn about the latest innovations in Aurora MySQL version 3 and MySQL 8.0. You will also be introduced to important and breaking behavioural changes in the new version. We will discuss the new version currency adopted with Aurora MySQL version 3 and ways to upgrade from older versions. There will also be a demo of new features like Aurora Serverless v2.

[Save your place on this online event by checking out the registration page here](https://aws-oss.beachgeek.co.uk/22x).

**AWS Elastic Kubernetes Service (EKS) Workshop**
**November 10th, London 5pm**

Join us for an interactive workshop on containers, Docker, Fargate and Amazon EKS, hosted by ClearScale and AWS. This live, virtual workshop includes three hours of interactive presentation and hands-on lab work. You will take part in the setup and deployment of containers using EKS. Follow along and work directly with AWS professionals and ClearScale (an AWS Premier Tier Services Partner) in this Level 200 training session.

You can find out more about this event by [checking out the event page and signing up](https://aws-oss.beachgeek.co.uk/22y).


**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)