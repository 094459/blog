---

title: 'AWS open source news and updates #128'
date: '2022-09-23'
tags : [ oss-newsletter, aws open source, Prometheus, Kubernetes, Amazon EMR, Kyverno, Cosign, MariaDB, AWS CDK, Amazon Corretto, GitOps, AWS SDK for pandas, Guardian, AWS SAM, Terragrunt, Open Policy Agent, Apache Airflow, Kubecost, OpenCost]

---

## September 23rd, 2022 - Instalment #128

**Welcome**

Welcome to the AWS open source newsletter, edition #128. I hope some of you were able to catch Derek and myself sharing a peek at this edition, and enjoyed our special guest, Gethin Webster as he walked us through the open source Cloudscape project. If you want to catch up on that event, [check out the video here](https://www.twitch.tv/videos/1598818260).

This weeks opens new open source projects include "Guardian", a command line tool that produces nice reports on your AWS environments, "cdk-scheduler", a new construct that helps you schedule your CDK deployments, "terraform-iam-policy-validator" a script that helps you validate your Terraform scripts, "aws-cdk-golden-ami-pipeline" an example of how to build an automated pipeline to build Amazon Machine Images (AMI's), and many more. Make sure you check them out and practice your four freedoms on them.

Content wise this week we feature posts from AWS and the community on Prometheus, Kyverno, Cosign, MariaDB, Amazon Corretto, AWS SDK for pandas, Guardian, AWS SAM, Terragrunt, Open Policy Agent, Apache Airflow, OpenCost and many more. This weeks video features GitOps and to finish off we have some new events for you to review and sign up for.

**Feedback**

If you enjoy reading this newsletter, please let me know how we can improve it as well as how AWS can better work with open source projects and technologies by completing [this very short survey ](https://eventbox.dev/survey/NUSZ91Z)that will take you probably less than 30 seconds to complete. Thank you so much!

**Celebrating open source contributors**

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created. 

So thank you to the following open source heroes: Guillaume Égée, Imtranur Rahman, Lotfi Mouhib, Ajeeb Peter, Shane Corbett, Kurt Roekle, Pekka Malmirae, Aravind V, Éloi Alain, Borislav Hadzhiev, Chouaieb Nemri, Leo Murillo, Zohaib Khawaja, Linh Lam, Mike George and Abhi Khanna.

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution.*

#### Tools

**Guardian**

[Guardian](https://aws-oss.beachgeek.co.uk/22g) is an open source tool that provides a command line tool you can run that produces a detailed report of the improvements you can make to your AWS architecture. In the post, [Guardian 1.0.0 available now! Your Free Open Source audit tool for AWS architectures!](https://aws-oss.beachgeek.co.uk/22h), Éloi Alain shows you how you can install and configure this and walks you through creating a report and showing you how you can integrate this into your CI pipeline.

![demo of project Guardian](https://res.cloudinary.com/practicaldev/image/fetch/s--f6xLX_BL--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_66%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/l3i0inddqzv6z3z04j5o.gif)

**kong-aws-request-signing**

[kong-aws-request-signing](https://aws-oss.beachgeek.co.uk/22q) This plugin will sign a request with AWS SIGV4 and temporary credentials from sts.amazonaws.com requested using an OAuth token. It enables the secure use of AWS Lambdas as upstreams in Kong using Lambda URLs.

**cdk-scheduler**

[cdk-scheduler](https://aws-oss.beachgeek.co.uk/22r) this construct from Guillaume Égée enables you to trigger an event at a given time on a serverless architecture. You should use cdk-scheduler if you need to trigger an event at a precise time (down to the second) on your AWS application.

**terraform-iam-policy-validator**

[terraform-iam-policy-validator](https://aws-oss.beachgeek.co.uk/22o) this is a super useful tool that provides a command line tool that validates AWS IAM Policies in a Terraform template against AWS IAM best practices.

**zone-aware-controllers-for-k8s**

[zone-aware-controllers-for-k8s](https://aws-oss.beachgeek.co.uk/22l) this project provides Kubernetes controllers for AWS availability zone (AZ) aware rollouts and disruptions. The ZoneAwareUpdate (ZAU) controller enables faster deployments for a StatefulSet whose pods are deployed across multiple availability zones. At each control loop, it applies zone-aware logic to check for pods in an old revision and deletes them so that they can be updated to a new revision. Want to know more, then check out the docs of this project.

**sqlservertools**

[sqlservertools](https://aws-oss.beachgeek.co.uk/22p) this tool, the RDS Discovery Tool, is a lightweight ,it provides a capability to scan a fleet of on-prem SQl Servers and does automated checks for 20+features , validates supportability of the enabled features on RDS, and generates a report which provides recommendation to migrate to RDS, RDS Custom or EC2 compatible.

### Demos, Samples, Solutions and Workshops

**aws-cdk-golden-ami-pipeline**

[aws-cdk-golden-ami-pipeline](https://aws-oss.beachgeek.co.uk/22m) this repo (Golden Amazon Machine Image  pipeline) enables creation, distribution, verification, launch-compliance of the AMI and creates a continuous and repeatable process for the consumers to generate the golden AMI. 

![architecture of cdk golden ami pipeline](https://github.com/aws-samples/aws-cdk-golden-ami-pipeline/blob/main/images/Golden_AMI_v2.png?raw=true)

**amazon-eks-argo-rollouts**

[amazon-eks-argo-rollouts](https://aws-oss.beachgeek.co.uk/22k) this repo contains all the code and sample you need to set up an Amazon EKS cluster and Argo to enable progressive delivery of your code. It uses Terraform to provision everything, so if you are looking to explore this why not start here.

**ai-powered-text-insights**

[ai-powered-text-insights](https://aws-oss.beachgeek.co.uk/22n) this repo contains code that enables you to build a prototype to help you gain insights on how your customers interact with your brand in social media. By combining zero-shot text classification, sentiment analysis, and keyword extraction we are able to obtain real time insights from posts on Twitter and present them in a dashboard.

![architecture for AI powered insights](https://github.com/aws-samples/ai-powered-text-insights/blob/main/architecture.png?raw=true)

### AWS and Community blog posts

**AWS SDK for pandas**

In the post [ML on AWS : Read from your favorite AWS Data Sources to a Pandas DataFrame using AWS Data Wrangler](https://aws-oss.beachgeek.co.uk/22j), Chouaieb Nemri provides a nice primer into this open source project (that was recently renamed from AWS DataWrangler) and shows you how you can install this project and then get started with some simple examples.

**AWS CDK**

Borislav Hadzhiev has put together a really great post for those wanting to scratch beneath the AWS CDK surface and find out more about Identifiers in AWS CDK. Read his post, [What is an identifier (id) in AWS CDK - Complete Guide](https://aws-oss.beachgeek.co.uk/22i) and explore what these are, how they are assigned and more. Great stuff.

**Kyverno and Cosign**

Supply chain security is a very hot topic, and so I was delighted to read this post from Imtranur Rahman. In this weeks must read post, [Supply Chain Security on Amazon Elastic Kubernetes Service (Amazon EKS) using AWS Key Management Service (AWS KMS), Kyverno, and Cosign](https://aws-oss.beachgeek.co.uk/224), Imtranur demonstrate how you can implement supply chain security using open source tools on Amazon Elastic Kubernetes Service (Amazon EKS) with AWS Key Management Service (AWS KMS) and Cosign with Kyverno.

![architecture overview for kyverno and cosign](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2022/09/16/architecture-diagram-Kyverno-1024x610.png)

**Open Policy Agent (OPA)**

Open Policy Agent (OPA, pronounced “oh-pa”) is an open source, general-purpose policy engine that unifies policy enforcement across your stack. OPA provides a high-level declarative language that lets you specify policy as code and simple APIs to offload policy decision-making from your software. You can use OPA to enforce policies in micro-services, Kubernetes, CI/CD pipelines, API gateways, and more.

In the blog post, [Unified authorization for AWS with Styra Declarative Authorization Service: EKS Edition](https://aws-oss.beachgeek.co.uk/229), Kurt Roekle (a Solutions Architect at Styra) shows you how to enforce EKS guardrails using OPA and also outlines how to enable true and consistent authorisation at scale across your AWS deployments. [hands on]

![architecture overview of opa post](https://d2908q01vomqb2.cloudfront.net/761f22b2c1593d0bb87e0b606f990ba4974706de/2022/09/15/Styra1.png)

**Kubecost**

Kubecost is based on the open source project, OpenCost. It is a vendor-neutral open source project for measuring and allocating infrastructure and container costs in real time. In the post [Integrating Kubecost with Amazon Managed Service for Prometheus](https://aws-oss.beachgeek.co.uk/22t) Linh Lam, Mike George and Abhi Khanna that shows you how you can deploy this within your Amazon EKS clusters, integrating with Prometheus. [hands on]

![dashboard of kubecost](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2022/09/21/couldops_1085_3.png)

**Prometheus**

Great post from Shane Corbett, which hooked me with its opening line. In Kubernetes, when you are setting up a Pod, you can optionally specify how much of each resource a container needs. The most common resources to specify are CPU and memory (RAM) and these are defined as limits. In [Using Prometheus to Avoid Disasters with Kubernetes CPU Limits](https://aws-oss.beachgeek.co.uk/228) explores how limits work. The post then looks at how you can figure out how to set the right values, and know which metrics for troubleshooting throttles, and turning these into Prometheus metrics. [hands on]

![illustration of prometheus limit](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2022/09/21/avoid-12.jpg)

**Apache Airflow**

It is always interesting to hear from and learn how companies are using and implementing Apache Airflow. In the post, [How ZS created a multi-tenant self-service data orchestration platform using Amazon MWAA](https://aws-oss.beachgeek.co.uk/22a), learn how ZS (a management consulting and technology firm) created a multi-tenant self-service data orchestration platform using Amazon Managed Workflows for Apache Airflow (MWAA).

![screen shot of data hub solution](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2022/08/24/BDB-2517-image006.png)

**Amazon EMR**

In the post, [Design considerations for Amazon EMR on EKS in a multi-tenant Amazon EKS environment](https://aws-oss.beachgeek.co.uk/226), Lotfi Mouhib and Ajeeb Peter show how to configure and run EMR on EKS in a multi-tenant EKS cluster that can used by your various teams. They tackle multi-tenancy through four topics: network, resource management, cost management, and security. [hands on]

![illustration of multi tenancy for Amazon EMR ](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2022/09/15/Diagram-%E2%80%93-4.png)

**Other posts you might like from the past week**

* [Amazon SageMaker Autopilot is up to eight times faster with new ensemble training mode powered by AutoGluon](https://aws-oss.beachgeek.co.uk/227) looks at optimising model training when using AutoGluon-Tabular (AGT), a popular open-source AutoML framework that trains highly accurate ML models on tabular datasets [hands on]
* [Deploy your Amazon EKS Clusters Locally on AWS Outposts](https://aws-oss.beachgeek.co.uk/22b) dives deeper into the announcement this week of Amazon EKS local clusters [hands on]

### AWS Community Builders

This week we feature some great content form the AWS Community, specifically from the AWS Community Builders.

**AWS SAM**

AWS Community Builder Aravind V has been putting together a series of posts on using AWS CDK (make sure you check them out). I managed to read a couple of the most recent. First up we have,  [AWS CDK 101 - 🦋 SAM local to test and debug lambda function](https://aws-oss.beachgeek.co.uk/22c) where he shows you setting up local integration testing of the AWS Lambda functions using AWS SAM.

![architecture of solution for SAM Local testing](https://res.cloudinary.com/practicaldev/image/fetch/s--iedv-ung--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/msrbf94oefdrnu29a5db.jpeg)

Following that he put together, [AWS CDK 101 - 💫 Dynamodb Local setup and integrating with sam invoke](https://aws-oss.beachgeek.co.uk/22d), that uses Dynamodb local together with AWS SAM invoke, to include testing of Amazon DynamoDB.

**Terragrunt**

[Terragrunt](https://aws-oss.beachgeek.co.uk/22e) is a thin wrapper for Terraform that provides extra tools for working with multiple Terraform modules. AWS Community Builder Pekka Malmirae has put together this post, [Mastering AWS deployments with Terragrunt](https://aws-oss.beachgeek.co.uk/22f) where he shares more details about what Terragrunt is and how you can use it to up your Terraform game. As someone still coming up to speed with Terraform, I found this post super valuable.

![overview of terragrunt](https://res.cloudinary.com/practicaldev/image/fetch/s--3DM0GHCB--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/7b6eypdt23ekffbiop1m.jpg)

### Quick updates

**Amazon Corretto**

Amazon Corretto 19 is now generally available. This version supports the latest OpenJDK feature release and is available on Linux, Windows, and macOS. 

Highlights of OpenJDK 19 include previews of Record Patterns, a new Foreign Function & Memory API, and Virtual Threads. Developers will get improved data navigation using Record Pattern Matching, which offers more sophisticated, composable data queries. Also in preview in this release is a Foreign Function & Memory API, which will allow you to more easily interoperate with native code outside the JVM, and Virtual Threading, which will improve the developer experience when writing, maintaining and observing high-throughput concurrent applications.

There is a new incubating feature for Structured Concurrency. Plus, you will get updates to the Pattern Matching for switch statements preview feature and to the incubating Vector API. Structured Concurrency will streamline error handling and cancellation, improve reliability, and enhance observability by treating multiple tasks running in different threads as a single unit of work.

Read more about this, including links to the download page and more detailed highlights at [Amazon Corretto 19 is now generally available](https://aws-oss.beachgeek.co.uk/225) 

**AWS CDK**

The latest update to AWS CDK 2.42.0 is now generally available. Check out some highlights from the [release notes](https://aws-oss.beachgeek.co.uk/222):

* cfnspec: cloudformation spec v88.0.0
* cognito: add SAML user pool identity provider
* lambda-event-sources: add filters to SQS, DynamoDB, and Kinesis event sources
* redshift-alpha: directly add parameters to a parameter group or indirectly through a cluster
* ssm: reference existing SSM list parameters

And these new alpha modules

* neptune: add engine version 1.2.0.0 
* neptune: introduce cluster grant method for granular actions

**Kubernetes**

Announced this week was the general availability of local clusters for Amazon Elastic Kubernetes Service (EKS) on Outposts, which enable you to run highly available Kubernetes clusters in on-premises environments.

Local clusters enable you to run the entire Amazon EKS cluster locally on Outposts, so you can mitigate the risk of application downtime that can result from temporary network disconnects to the cloud, such as those caused by fibre cuts or weather events. Because the entire Kubernetes cluster runs locally on Outposts, applications remain available, and you can perform cluster operations during network disconnects to the cloud. When connected to the cloud, Amazon EKS manages the availability of the Kubernetes control plane on Outposts, so you can simplify your Kubernetes operations. Local clusters run the same Kubernetes as Amazon EKS in the cloud, and automatically deploy the latest security patches to make it easier for you to maintain an up-to-date, secure cluster. You can use the same tooling you use with Amazon EKS in the cloud for a consistent experience across on-premises and cloud environments.

**Amazon EMR**

Also announced this week was that Amazon EMR on EKS release 6.7.0 and onwards includes the ability to run Apache Spark SQL scripts through the StartJobRun API. Spark SQL is a Spark module for structured data processing. Unlike the Spark DataFrame API, Spark SQL interfaces provide Spark with more information about the structure of both the data and computation being performed. Internally, Spark SQL uses this extra information to perform additional optimisations. With this release, you can run Spark SQL queries and Spark SQL-based ETL pipelines directly through Amazon EMR on EKS’ StartJobRun API.

Amazon EMR on EKS users rely on the StartJobRun API to kick-off Spark jobs. Previously, to run Spark SQL scripts, users had to embed their SQL scripts in interfaces such as PySpark, which required user modifications to existing Spark SQL scripts. As part of this release, a new Spark SQL job driver is added to the Amazon EMR on EKS’ base image that users use to run their Spark jobs. Users will now be able to supply SQL entry-point files to run Spark SQL queries on Amazon EMR on EKS using the StartJobRun API directly, without any modifications to existing Spark SQL scripts.

**MariaDB**

Amazon Relational Database Service (Amazon RDS) for MariaDB now supports MariaDB minor versions 10.5.17, 10.4.26 and 10.3.36. We recommend that you upgrade to the latest minor versions to fix known security vulnerabilities in prior versions of MariaDB, and to benefit from the numerous bug fixes, performance improvements, and new functionality added by the MariaDB community.

### Videos of the week

**GitOps**

Leo Murillo, Principal Solutions Architect at Weaveworks, and Zohaib Khawaja, Solutions Architect at AWS, demonstrate why GitOps is a standardised workflow to deploy, configure, monitor, update and manage Kubernetes, its components and all the applications that run on it.

{{< youtube F1SABYVoBuU >}}


**Build on Open Source**

If you missed us live last Friday, you can catch up as we take a look at the latest open source news and talk to this weeks special guest, AWS Hero Ian Mckay.

{{< youtube _ZtJuhiS7p4 >}}


### Events for your diary

**AWS Java Panel**
**September 27th, 4:30pm**

If you love Java and AWS, then make sure you check out this free, online event. A stellar line up includes Mark Sailes from AWS, Serkan Ozal Thundra (AWS Hero), Vadym Kazulkin from ip.labs (AWS Community Builder), and Goran Opacic Esteh (AWS Hero).

They are going to cover topics such as Java 17 and 19, developer experiences, GraalVM, PowerTools for Java and much more.

Check out the [registration page](https://aws-oss.beachgeek.co.uk/22s) and save your place.

**ApacheCon North America 2022**
**October 3-6, New Orleans**

ApacheCon is the official open source software convention of the Apache Software Foundation (ASF), focused on the software projects hosted at the ASF. With over 160 sessions covering all your favourite Apache open source projects and more, 

[Check out the ApacheCon registration page](https://aws-oss.beachgeek.co.uk/221) for more details, including the sessions and keynotes.

**Jumpstart your Java applications with AWS Lambda and Micronaut**
**October 5th**

Don't miss the opportunity to attend this event if you are in or around London. Combining lectures, live coding demonstrations, AWS interaction, and hands-on exercises, you will learn:

* How AWS Lambda functions written with the Micronaut framework can be triggered with AWS Events (such as an S3 or DynamoDB event)
* How integrating Amazon API Gateway and AWS Lambda enables you to write your applications as you would with a Netty runtime (i.e., write your applications as you usually do; run them in AWS Lambda)
* How to deploy a Micronaut application as a GraalVM native image to AWS Lambda Java runtime or to a custom runtime
* How leveraging certain characteristics of Micronaut applications, including fast startup, low memory consumption, and GraalVM integration, can help you work around cold startups in AWS Lambda.

Check out and register while there are places available [at the link here](https://aws-oss.beachgeek.co.uk/223).


**Build on AWS Open Source**
**October 7th, 9am BST**

Join us for the third episode of the Build on AWS series, featuring a live round up of the latest projects and news as well as a special guest speaker. This week, we are delighted to have AWS Data Hero Alvaro Hernandez who will be talking about all things database on containers. Do not miss this!

**The Present and The Future of Infrastructure as Code**
**Paris, France**
**Oct 11, 6 PM**

This promises to be a great meet-up and essential attendance if you are into infrastructure as code. AWS Hero Anton Babenko hosts this event, sponsored by Qovery.

Read more and register for this event by heading over to [their meet-up page](https://aws-oss.beachgeek.co.uk/220).


**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)

