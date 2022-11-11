---

title: 'AWS open source news and updates #135'
date: '2022-11-11'
tags : [ oss-newsletter, aws open source, Redis, Amazon EMR, AWS Copilot, Ansible, O3DE, Dagger, Apache Hudi, Apache Flink, AWS Amplify, AWS AppSync, PostgreSQL, Spring Boot, AWS SAM, Micronaut, Apache Iceberg, Dagger,]

---

## November 11th, 2022 - Instalment #135

**Welcome**

Welcome to the AWS open source newsletter, edition #135. 

What do we have in store for you in this weeks instalment? I am happy to report that we have yet more great new projects this week. These include "sovereign-keys" and "nitrogen" are new projects to help you secure and get started working with enclaves, "aws-serverless-scheduler" helps you schedule your events, "aws-resource-explorer-cli" provides a command line tool for this new capability, "workload-discovery-on-aws" helps you stay on top of your AWS workloads, ""image-content-moderation" provide a sample project for image moderation you can integrate into your workflows, "cloudenv" is a proof of concept that explores managing secrets and prameters, "cdk-schema-watcher" is a tool to help you stay notified of schema changes in your event driven applications, and several other projects to check out.

We also feature content on Redis, Amazon EMR, AWS Copilot, Ansible, O3DE, Dagger, Apache Hudi, Apache Flink, AWS Amplify, AWS AppSync, PostgreSQL, Spring Boot, AWS SAM, Micronaut, Apache Iceberg and more. Finally, don't forget the quick updates, video round up and events section. We have the seventh episode of Build on Open Source this Friday, 18th and we are super excited to have as a special guest, Vinoth Chandar, creator of the Apache Hudi project.

**Feedback**

Please let me know how we can improve this newsletter as well as how AWS can better work with open source projects and technologies by completing [this very short survey ](https://eventbox.dev/survey/NUSZ91Z)that will take you probably less than 30 seconds to complete. Thank you so much!

**Celebrating open source contributors**

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created. 

So thank you to the following open source heroes: Lars Jacobsson, David Boyne, Agus Marchi, Hardik Singh Behl, Allan Chua, Diego Gomes, Bill Pereira, Lee Hung Nguyen, Jérémie Rondon, Kyle Lee, Mark Sailes, Heather Jeong, Jimmy Kang, Jimmy Tam, Aidan Steele, Shaun Scovil, and Samrose Ahmed.

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution.*

#### Tools

**workload-discovery-on-aws**

[workload-discovery-on-aws](https://aws-oss.beachgeek.co.uk/292) is a solution to visualize AWS Cloud workloads. With it you can build, customize, and share architecture diagrams of your workloads based on live data from AWS. The solution maintains an inventory of the AWS resources across your accounts and regions, mapping their relationships and displaying them in the user interface.

![architecture of solution for workload discovery](https://github.com/awslabs/workload-discovery-on-aws/blob/main/docs/modules/ROOT/images/arch-diagram.png?raw=true)

You can view more details by checking out the implementation guide over at, [Workload Discovery on AWS](https://aws-oss.beachgeek.co.uk/293)

**aws-resource-explorer-cli**

[aws-resource-explorer-cli](https://aws-oss.beachgeek.co.uk/290) is the latest project from AWS Community Builder Lars Jacobsson, and provide a cli for the recently announced Resource Explorer feature (read more about that in the blog post, [Introducing AWS Resource Explorer – Quickly Find Resources in Your AWS Account](https://aws-oss.beachgeek.co.uk/291) from my colleague Danilo Poccia). The cli tool allows you to quickly find what you are looking for in the console before launching the web browser in the right place.

![demo of resource explorer cli](https://github.com/ljacobsson/aws-resource-explorer-cli/blob/main/images/demo.gif?raw=true)

**cdk-schema-watcher**

[cdk-schema-watcher](https://aws-oss.beachgeek.co.uk/28y) Serverless Developer Advocate and all round open source good guy David Boyne has been hard at the open source forge again, this time with his latest creation, SchemaWatcher. SchemaWatcher is a CDK construct that can help you scale your event-driven architecture by allowing event consumers to subscribe to schema changes. SchemaWatcher was designed to help developers manage their event-driven architecture. Notifying consumers of any changes to event structures can help catch issues before you see them in production. In David's words:

> Over time our Event Driven Architectures (EDA) grow and it can become difficult to understand the impact of changes to downstream consumers. Producers can easily change their event schemas without consumers being aware. SchemaWatcher was built to help you setup notifications for your downstream consumers when using EventBridge. Never let a breaking schema scare you again!

David's projects have one common trait - amazing documentation, and SchemaWatcher is no different. You can view the documentation at [cdk-schema-watcher.vercel.app](https://aws-oss.beachgeek.co.uk/28z)

**aws-serverless-scheduler**

[aws-serverless-scheduler](https://github.com/agusmdev/aws-serverless-scheduler) this repo from Agus Marchi is a fork of a similar project (aws-scheduler) but with a narrower focus, scheduling webhook-related tasks. How does it work? The docs have you covered, but to schedule a trigger you have to publish an event (format spec is provided in the docs). There are some limitations to check out, but if you are looking for a way to schedule large amounts of point in time events with a great time precision, and they are webhook related, then this is a project for you my friend.

![architecture of aws-serverless-scheduler ](https://github.com/agusmdev/aws-serverless-scheduler/blob/main/architecture.png?raw=true)

**cloudenv**

[cloudenv](https://aws-oss.beachgeek.co.uk/28o) is an open source proof of concept from Aidan Steele that allows your AWS Lambda functions to be configured to use secrets stored in AWS Parameter Store and AWS Secrets Manager in the same way that AWS ECS task definitions can be. Aidan has put together a detailed blog post, [Configuration in the cloud](https://aws-oss.beachgeek.co.uk/28p), that goes into more details. Take a look and get back to Aidan with your feedback.

![example of cloudenv](https://awsteele.com/assets/2022-10-20-tada.png)

**nitrogen**

[nitrogen](https://aws-oss.beachgeek.co.uk/28v) is my vote for coolest project name this week, and is an open source tool for deploying web services to AWS Nitro Enclaves. Given a dockerfile and an ssh key, Nitrogen will spin up an EC2, configure the network, and build and deploy your web service. You get back a hostname that’s ready to go. Nitrogen is fully open source and it comes with pre-built scripts for deploying popular services like Nginx, Redis, and MongoDB. This sounds pretty amazing to me, so this is going straight to the top of the todo list.

Make sure you check out the documentation, which really does help explain and show how you might use enclave technology, as well as seeing the other demos from Cape Privacy, which you can find here [demos.capeprivacy.com](https://aws-oss.beachgeek.co.uk/28w)

**sovereign-keys**

[sovereign-keys](https://aws-oss.beachgeek.co.uk/289) Sovereignty has become a concern for some companies as they plan and move to Cloud computing. This project is designed around the hypothesis that your Cloud provider is not actively seeking to steal your data for its own gain, but rather that it can be forced by the law to surrender your data to a (foreign) government. Sovereign Keys gives you additional data protection guarantees and also provides an excuse that Cloud providers can use to argue they cannot comply with legally issued requests to access your data (e.g. requests issued under the CLOUD Act). 

![architecture overview of the sovereign-keys](https://github.com/d2si/sovereign-keys/blob/main/images/demo-architecture-overview.png?raw=true)

There is a lot of stuff to go through in this project, and the examples and documentation is very detailed. Jérémie Rondon has also put together this video to walk you through it too. Grab your favourite beverage and strap yourself in, this is a great deep dive session into how this works.

{{< youtube NUYR3tqgCyY >}}

### Demos, Samples, Solutions and Workshops

**soap-to-serverless-modern-infrastructure-for-mature-apis**

[soap-to-serverless-modern-infrastructure-for-mature-apis](https://aws-oss.beachgeek.co.uk/28s) this project provides a SOAP Service written in NodeJS that communicates with API Gateway which transforms the information payload using VTL to Lambda. Lambda responds back to API Gateway to maintain backward to SOAP and in JSON to REST calls. The repo provides a sample use case as to why this project might be helpful. A company has a legacy application communicating between layers using SOAP Services. The team that is in charge of the business logic wants to start migrating part of the code to Serverless but have backward compatibility with the front-end layer. So communication between the front-end and backend has to remain in SOAP contract but with business logic in serverless solution. This example show how to do that.

![architecture for supporting SOAP to serverless](https://github.com/aws-samples/soap-to-serverless-modern-infrastructure-for-mature-apis/blob/main/docs/images/architecture.png?raw=true)

**react_aws_static_hosting**

[react_aws_static_hosting](https://aws-oss.beachgeek.co.uk/28t) is a demo repository from Allan Chua for hosting static React websites using AWS, CloudFront, WAF & CloudFront Origin Policies.

![architecture of sample static react app](https://github.com/allanchua101/react_aws_static_hosting/blob/main/assets/waf_s3_cf_cf-origins.jpg?raw=true)

**image-content-moderation**

[image-content-moderation](https://aws-oss.beachgeek.co.uk/28u) is a proof of concept from Hardik Singh Behl, that exposes a single REST API endpoint to set/update user's current profile picture. Amazon Rekognition has been integrated in the service layer to detect any inappropriate, suggestive, unwanted or offensive content in the image being uploaded, If any ModerationLabels are detected the API returns HttpStatus.NOT_ACCEPTABLE. On successful content moderation evaluation, HttpStatus.OK is returned by the endpoint. Check the README for a short video of how this works.

**sagemaker-datawrangler**

[sagemaker-datawrangler](https://aws-oss.beachgeek.co.uk/286) this repo contains example flows that demonstrate how to aggregate and prepare data for Machine Learning using Amazon SageMaker Data Wrangler. Isha Dua has put together a blog post, [Use Github Samples with Amazon SageMaker Data Wrangler](https://aws-oss.beachgeek.co.uk/287) to help get you started.

![example screen shot of sagemaker datawrangler examples](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2022/10/20/image012-2.jpg)

### AWS and Community blog posts

**Terraform CDK**

Shaun Scovil has put together this post, [Using Terraform CDK with LocalStack (Python)](https://aws-oss.beachgeek.co.uk/28q) (with a nice illustration courtesy of Midjourney) that is intended for anyone who is trying to get Terraform CDK to work with LocalStack. For those who may be unfamiliar, LocalStack is an open source tool that enables you to run cloud service emulator in a single container on your laptop or in your CI environment. Very nice idea and post, so well worth five minutes of your time this week. [hands on]

**Apache Iceberg**

Matano is an open source security lake platform for AWS, which I have featured in previous editions of this newsletter. Samrose Ahmed peeks under the covers as he writes, [Automated Iceberg table maintenance](https://aws-oss.beachgeek.co.uk/28r) and how table maintenance works and how they are able to run completely serverless Iceberg table maintenance on AWS.

![architecture of apache iceberg on matano](https://www.matano.dev/assets/images/diag-2e2f41b5e35e05b3ea86ef0448b96ba6.png)

**Micronaut**

In a collaboration between Mark Sailes, Heather Jeong, Jimmy Kang, and Jimmy Tam, they have got together to write [Improving Developer Productivity at Disney with Serverless and Open Source](https://aws-oss.beachgeek.co.uk/28k) where they share how they are combining serverless and open source technologies to improve their ability to deliver business value safely and reliably.  

![cold start graph](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2022/11/07/Java-cold-start-native-image-chart.png)

**Apache Flink**

Apache Flink is an open-source framework and engine for stateful processing of data streams. It’s highly available and scalable, delivering high throughput and low latency for the most demanding stream-processing applications. In [Learn more about Apache Flink and Amazon Kinesis Data Analytics with three new videos](https://aws-oss.beachgeek.co.uk/28i), there are three new videos for you to learn more about Apache Flink and Kinesis Data Analytics, including open-source contributions to Apache Flink, our learnings from running thousands of Flink jobs on a managed service, and how we use Kinesis Data Analytics and Apache Flink to enable machine learning (ML) in Alexa.

{{< youtube F5yKSznkls8 >}}

**AWS Amplify**

This week we had a number of great posts for Web and Mobile developers. 

In this first of a two part post, [Building Offline first applications with AWS Amplify DataStore – Part 1](https://aws-oss.beachgeek.co.uk/28g), Diego Gomes shows how [AWS Amplify DataStore](https://aws-oss.beachgeek.co.uk/28f) addresses some of the challenges of building Offline first applications. [hands on]

![architecture overview of amplify datastore](https://d2908q01vomqb2.cloudfront.net/0a57cb53ba59c46fc4b692527a38a87c78d84028/2022/11/03/mobile_1962_2.png)

Following that we had Kyle Lee write, [Getting Started with AWS Amplify on macOS](https://aws-oss.beachgeek.co.uk/28h) who shows you how to use Amplify Auth sign in with web UI to authenticate a user across both macOS and iOS. Get into XCode and off you go...! [hands on]

**Other posts and quick reads**

* [Using Async/Await with AWS Amplify Libraries for Swift](https://aws-oss.beachgeek.co.uk/28n) shows you how to use async/await with the Amplify Libraries for Swift and demonstrates how efficiently you can write asynchronous code with this new release [hands on]
* [Transfer learning for TensorFlow text classification models in Amazon SageMaker](https://aws-oss.beachgeek.co.uk/288) looks at the announcement last week that SageMaker provides a new built-in algorithm for text classification using TensorFlow [hands on] 
* [Secure AWS AppSync with Amazon Cognito using the AWS CDK](https://aws-oss.beachgeek.co.uk/28j) provides an overview of AWS IAM permissions as they relate to Cognito identity pools, showing how to configure IAM permissions in the CDK [hands on]
* [Secure AWS AppSync with API Keys using the AWS CDK](https://aws-oss.beachgeek.co.uk/28m) is a walkthrough on how access can be enabled for guest users–that is, users that need access to our data, but do not have a mechanism for logging in [hands on]
* [Support JSON data using Amazon RDS for PostgreSQL or Amazon Aurora PostgreSQL and Java Spring Boot on AWS](https://aws-oss.beachgeek.co.uk/28l) shows you how to support business data captured in JSON format in microservices developed in the Spring Boot Java framework, Amazon RDS for PostgreSQL, or Aurora PostgreSQL [hands on]

**Case Studies**

* [How Hudl built a cost-optimized AWS Glue pipeline with Apache Hudi datasets](https://aws-oss.beachgeek.co.uk/28e) in this case study, Hudl (Hudl Agile Sports Technologies, a company that provides tools for coaches and athletes to review game footage and improve individual and team play) share how Apache Hudi enabled them to dramatically improve performance of their data pipeline.

![hudl apache hudi data pipeline architecture](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2022/10/25/NewDesign.png)

### Quick updates

**Redis**

Amazon ElastiCache for Redis now supports Redis 7. This release brings several new features to Amazon ElastiCache for Redis:

* Redis Functions: ElastiCache for Redis 7 adds support for Redis Functions, and provides a managed experience enabling developers to execute LUA scripts with application logic stored on the ElastiCache cluster, without requiring clients to re-send the scripts to the server with every connection.
* ACL improvements: ElastiCache for Redis 7 adds support for the next version of Redis Access Control Lists (ACLs). With ElastiCache for Redis 7, clients can now specify multiple sets of permissions on specific keys or keyspaces in Redis.
* Sharded Pub/Sub: Amazon ElastiCache for Redis 7 now gives you the ability to run Redis’ Pub/Sub functionality in a sharded way when running ElastiCache in Cluster Mode Enabled (CME). Redis’ Pub/Sub capabilities enable publishers to issue messages to any number of subscribers on a channel. With Amazon ElastiCache for Redis 7, channels are bound to a shard in the ElastiCache cluster, eliminating the need to propagate channel information across shards resulting in improved scalability. 

**Amazon EMR**

Announced earlier this week was the general availability of job templates in Amazon EMR on EKS. Job templates allow you to create and store templates to configure Spark applications parameters. This helps you ensure consistent settings across applications by reusing and enforcing configuration overrides in data pipelines.

EMR on EKS applies default Spark settings to optimise an application’s performance when customers use the StartJobRun API to run Spark-based applications and data pipelines. With job templates, data engineers can now define reusable templates to apply additional customisations, configuring executor and driver compute capacity, setting security and governance properties such as IAM roles, and customised docker image to use across multiple applications and data pipelines. Additionally, customers can also enforce specific configuration values, preventing overrides when calling the StartJobRun API using the template. Job templates can be optionally encrypted with customer-managed master keys stored in AWS Key Management Service.

**AWS Copilot**

AWS announced the general availability of AWS Copilot version 1.23 with support for AWS App Runner private services. App Runner makes it easier for developers to quickly deploy containerised web applications and APIs to the cloud, at scale, and without having to manage infrastructure. By default, App Runner services are accessible publicly over the internet. Now, with private services you can restrict network access to your internal websites, APIs, and applications to originate from within your Amazon VPC.

With AWS Copilot, you can quickly get started and deploy to Amazon ECS or AWS App Runner with a single command and a Dockerfile. Copilot provides a developer-focused interface and workflows, where users can focus on application architecture by choosing common application and services patterns. Copilot provisions and keeps up to date the necessary AWS infrastructure in your account, using the best-practices and infrastructure-as-code artefacts. Now, you have the option of toggling the request-driven Copilot services, powered by App Runner, to be private. Simply specify http.private: true in the Copilot service manifest and run copilot deploy command. Copilot will take care of configuring AWS App Runner services to accept traffic only from within Amazon VPC provisioned for your Copilot environment.

### Videos of the week

**Ansible**

Bill Pereira shows you how you can use Ansible to transfer data. between #zOS and #AWS, using the #ibm_zos_core modules to backup and restore, and the #AMAZON #AWS modules to put and get data from the #S3 buckets.

{{< youtube pBIJozFx-4o >}}

**O3DE**

In 2022, there are so many 3D engines that exist that you can barely keep a count on it. With multiple experiences, comes complex design problems to solve on a day to day basis. This is where design systems come in. There's no need to reinvent the wheel; when we can all just align on the most expected and common design patterns for users to experience. The BlueJay Design System is the official design system for Open 3D Engine. Lee Hung Nguyen is your speaker as he outlines what is involved in planning and building the best open source design system for the 3D engine. 

{{< youtube oF1JyMGsHAI >}}

**Dagger**

[Dagger](https://aws-oss.beachgeek.co.uk/28c) is an open source programmable CI/CD engine that runs your pipelines in containers. You can follow along with the Containers on the Couch crew via [Twitch](https://aws-oss.beachgeek.co.uk/28b) or [LinkedIn](https://aws-oss.beachgeek.co.uk/28a) as they introduce this project and then walk you through a demo.

**AWS Container Day**

If you missed the AWS sessions at KubeCon NA a few weeks back, the team has your back. They have put together a [play list on YouTube](https://aws-oss.beachgeek.co.uk/28d) with all the sessions.

**Build on Open Source**

For those unfamiliar with this show, Build on Open Source is where we go over this newsletter and then invite special guests to dive deep into their open source project. Expect plenty of code, demos and hopefully laughs.

We have put together a playlist so that you can easily access all the other episodes of the Build on Open Source show. [Build on Open Source playlist](https://aws-oss.beachgeek.co.uk/24u)

# Events for your diary

**OpenSearch - Development Backlog & Triage Meeting Security**
**14th November - 12pm PT**

The OpenSearch engineering team working on the Security repo have opened up their Backlog & Triage meetings to the public. This is a great opportunity to find out more about the inner workings of open source projects such as OpenSearch. Don't worry if you cannot make this meeting as they are currently scheduled from the 7th of November out through Dec 19th.

Check out the entire [list here](https://aws-oss.beachgeek.co.uk/285).

**Running Open Source Transcoding Server on Amazon EKS**
**Friday, 18th, 19:00 WIB**

Join Beny Ibrani and the AWS User Group Indonesia for this session (local language I believe) where Beny will show you how you can use open source transcoding software running on Amazon EKS.

This session will be streamed on YouTube, so [check it out here](https://aws-oss.beachgeek.co.uk/27j)

**Build on AWS Open Source**
**November 18th, 9am BST**

Join us for the sixth episode of the Build on AWS series, featuring a live round up of the latest projects and news as well as a special guest speaker. We have another special guest lined up, and we are super happy to speak with Vinoth Chandar, Onehouse CEO/Founder and creator of the Apache Hudi project. Follow the show on @buildonopen for more details. Check it out on https://twitch.tv/aws

**AWS Elastic Kubernetes Service (EKS) Workshop**
**November 10th, London 5pm**

Join us for an interactive workshop on containers, Docker, Fargate and Amazon EKS, hosted by ClearScale and AWS. This live, virtual workshop includes three hours of interactive presentation and hands-on lab work. You will take part in the setup and deployment of containers using EKS. Follow along and work directly with AWS professionals and ClearScale (an AWS Premier Tier Services Partner) in this Level 200 training session.

You can find out more about this event by [checking out the event page and signing up](https://aws-oss.beachgeek.co.uk/22y).

**re:Invent**
**November 28th - December 3rd, Las Vegas**

re:Invent is only a few weeks away so I want to share a few things that will hopefully be of interest.

First up, we will be running the Build On Live stream throughout re:Invent and we would love to feature you! If either yourself, or perhaps you know a community member going to re:Invent and think they will absolutely love to attend the livestream, we want to hear from you. Please nominate a community member you want to hear from during Build On Live [using this survey](https://eventbox.dev/survey/6B0ED1J).

Second, check out this handy way to look at all the amazing open source sessions, then check out this [dashboard](https://aws-oss.beachgeek.co.uk/252) [sign up required]. I would love to hear which ones you are excited about so please let me know in the comments or via Twitter. If you want to hear what my top three, must watch sessions, then this is what I would attend (sadly, as an AWS employee I am not allowed to attend sessions)

1. OPN306 AWS Lambda Powertools: Lessons from the road to 10 million downloads - Heitor Lessa is going to deliver an amazing session on the journey from idea to one of the most loved and used open source tools for AWS Lambda users
2. BOA204 When security, safety, and urgency all matter: Handling Log4Shell - Cannot wait for this session from Abbey Fuller who will walk us through how we managed this incident
3. OPN202 Maintaining the AWS Amplify Framework in the open - Matt Auerbach and Ashish Nanda are going to share details on how Amplify engineering managers work with the OSS community to build open-source software

There are many other great open source sessions, and hopefully I will try and put together a more comprehensive list as approach re:Invent.

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)