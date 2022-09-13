---

title: 'AWS open source news and updates #126'
date: '2022-09-09'
tags : [ oss-newsletter, aws open source, AWS SAM, AWS Copilot, Kubernetes, Prometheus, Grafana, dotNET Core, NodeJS, PyTorch, PostgreSQL, AWS Toolkit for VS Code, Mosquitto, mqtt, Babelfish for PostgreSQL, ECS Anywhere, Moodle, Event Ruler, Terraform ]

---

## September 9th, 2022 - Instalment #126

**Welcome**

Welcome to the AWS open source newsletter, edition #126. Exciting news this week includes the second episode of the Build on AWS open source show, and the release of a new AWS open source project, event-ruler (more in a bit).

As always, this weeks newsletter includes more great new open source projects from AWS and the AWS Community. We have "aws-integration-for-apache-guacamole" that provides a guide of how you can deploy this open source project, "xcodeinstall" a tool to help you heedlessly install Xcode, "soci-snapshotter" a very cool project for Container lovers, "credentials-fetcher" a new Linux demon for those wanting to integrate with Windows environments, "imds-credential-server" a very nice tool to help you vend AWS credentials, "automated-data-analytics-on-aws" a new data tool that will help you accelerate time to insights, and "event-ruler" a very cool new project allowing you to match Rules to Events, and many other projects for you to check out.

This week we also feature content that covers open source technologies such as Prometheus, Grafana, dotNET Core, NodeJS, PyTorch, PostgreSQL, AWS Toolkit for VS Code, Mosquitto, mqtt, Babelfish for PostgreSQL, and more. Check out this weeks videos that cover AWS SAM, AWS Copilot, as well as the first episode of the Build on Open Source show. We wrap up as always with events that you need to know about.

**Feedback**

If you enjoy reading this newsletter, please let me know how we can improve it as well as how AWS can better work with open source projects and technologies by completing [this very short survey ](https://eventbox.dev/survey/NUSZ91Z)that will take you probably less than 30 seconds to complete. Thank you so much!

**Celebrating open source contributors**

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created. 

So thank you to the following open source heroes:  Donnie Prakoso, Michael Vinci, Rishi Baldawa, Tim Bray, Kyle Fox, Pavankumar Kasani, Prasad Rao, Imran Younus, Alex Iankoulski, Justin Keye, John Mille, Nathan Peck, Paul Bradley, Mukesh Murugan, Vladyslav Budichenko, Ben Kehoe,

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution.*

#### Tools

**event-ruler**

[event-ruler](https://aws-oss.beachgeek.co.uk/20c) is a new open source Java library that allows matching Rules to Events. An event is a list of fields, which may be given as name/value pairs or as a JSON object. A rule associates event field names with lists of possible values. There are two reasons to use Ruler: 1/ it's fast; the time it takes to match Events doesn't depend on the number of Rules, and 2/ customers like the JSON "query language" for expressing rules.

To find out more, check out the blog post from Rishi Baldawa, [Open Sourcing Event Ruler](https://aws-oss.beachgeek.co.uk/20d) which dives deeper into the internals of this project. You should also check out this post, [Hello Ruler](https://aws-oss.beachgeek.co.uk/20e) from Tim Bray, who contributed to this project and  that provides some additional flavour.

**xcodeinstall**

[xcodeinstall](https://aws-oss.beachgeek.co.uk/20a) this project from colleague Sébastien Stormacq is for macOS, iOS, iPadOS  developers using Mac machines for CI/CD, like EC2 Mac instances. This command line tool allows to list, download, and install Xcode and its Command Line Tools from a SSH session.  No GUI required. No web-based download from Apple Developer Portal. It is integrated with AWS Secrets Manager to store the apple session cookies, only the initial authentication requires a human interaction. It supports MFA and may store your apple developer portal credentials in AWS Secrets Manager.  The README has the details of the minimum IAM permissions required to do so.

This is an early stage project, and Sebastien is interested in your feedback. He knows it works on his machine and on EC2 Mac instances, and is curious about other configuration / environments. Please file issues on GitHub.

**soci-snapshotter**

[soci-snapshotter](https://aws-oss.beachgeek.co.uk/20n) is a super interesting new project and something to check out if you are using Containers. SOCI Snapshotter is a containerd snapshotter plugin. It enables standard OCI images to be lazily loaded without requiring a build-time conversion step. "SOCI" is short for "Seekable OCI", and is pronounced "so-CHEE". The standard method for launching containers starts with a setup phase during which the container image data is completely downloaded from a remote registry and a filesystem is assembled. The application is not launched until this process is complete. Using a representative suite of images, Harter et al FAST '16 found that image download accounts for 76% of container startup time, but on average only 6.4% of the fetched data is actually needed for the container to start doing useful work.

Definitely worth reading the README for this project.

**credentials-fetcher**

[credentials-fetcher](https://aws-oss.beachgeek.co.uk/20o) is a Linux daemon that retrieves group managed service account (gMSA) credentials from Active Directory over LDAP. It creates and refreshes kerberos tickets from gMSA credentials, and those Kerberos tickets can be used by containers to run apps/services that authenticate using Active Directory.

**aws-gamekit-unity**

[aws-gamekit-unity](https://aws-oss.beachgeek.co.uk/20p) this repository contains modifiable source code for the AWS GameKit package for Unity in the form of an Embedded Package. If you don’t need to modify the AWS GameKit package, you can download the latest tarball .tgz file from the releases page and add it to a Unity project using the Unity Package Manager. To modify this package we recommend cloning this repo and opening it as a blank Unity project. After making your changes, follow the Packaging steps below to generate a custom plugin package, which you can then add to your Unity projects.

**AWSCreds**

[AWSCreds](https://aws-oss.beachgeek.co.uk/214) this project from Michael Vinci might be useful for Mac owners as it provides a MacOS menubar app to help switch AWS Profiles.

![demo of tool](https://github.com/michaeldvinci/AWSCreds/blob/main/res/AWSCreds.gif?raw=true)

**imds-credential-server**

[imds-credential-server](https://aws-oss.beachgeek.co.uk/20y) is a very nice tool from AWS Serverless Hero Ben Kehoe that runs a server compliant with the EC2 IMDSv2 interface in order to vend AWS credentials, primarily to export credentials into locally-run containers. This is better than mounting your ~/.aws directory into a container as a) it allows for mechanisms that only work on the host, e.g., custom credential processes and b) it only vends one set of (refreshable) credentials to the container rather than providing access to all your credentials. I have a few ideas of how I am going to use this, so hopefully I will have some time to play about with this project and share in a future newsletter.

### Demos, Samples, Solutions and Workshops

**automated-data-analytics-on-aws**

[automated-data-analytics-on-aws](https://aws-oss.beachgeek.co.uk/20g) is a new open source solution that provides an end-to-end data platform for ingesting, transforming, managing and querying datasets. This helps analysts and business users manage and gain insights from data without deep technical experience using Amazon Web Services (AWS). It has an open-sourced architecture with connectors to commonly used AWS services, along with third-party data sources and services. This solution also provides a user interface (UI) to search, share, manage, and query datasets using standard SQL commands.

![architecture for solution](https://github.com/aws-solutions/automated-data-analytics-on-aws/blob/main/source/images/solution_architecture_diagram.png?raw=true)

The Automated Data Analytics on AWS solution automates the building of data pipelines that are optimized for the size, frequency of update, and type of data. These data pipelines handle the data ingestion, transformations, and queries. 

I found out about this project from the video that the team did at the AWS Summit ANZ 2022 (session was Reducing time to insight with Data Manifold). Check out the video here, where Kyle Fox introduces this project and does a quick demo of it.

{{< youtube NZ-uQacqJ_I >}}


**aws-integration-for-apache-guacamole**

[aws-integration-for-apache-guacamole](https://aws-oss.beachgeek.co.uk/20q) Apache Guacamole is an open source tool that provides a client-less remote desktop gateway, supporting standard protocols like VNC, RDP, and SSH. This repository is a walk through of scripts that were made to quickly set up an automated VDI - Virtual Desktop Infrastructure - using the Apache Guacamole using Amazon EC2 Spot Instances. This sample is an AWS automation to integrate with Apache Guacamole using Eventbridge Rules and Lambda Functions to detect EC2 events in the VPC and create or remove connections in Guacamole. Very cool indeed.

![architecture of apache guacamole reference solution](https://github.com/aws-samples/aws-integration-for-apache-guacamole/blob/main/images/EAD-FireTV-blogpost.png?raw=true)

**aws-lambda-unit-test-example**

[aws-lambda-unit-test-example](https://aws-oss.beachgeek.co.uk/211) this repo contains sample code to demonstrate unit testing approaches using Python when using AWS services such as Amazon API Gateway, an AWS Lambda function, a DynamoDB Table, and an S3 bucket.

![architecture of lambda unit test](https://github.com/aws-samples/aws-lambda-unit-test-example/blob/main/doc/architecture.png?raw=true)

An API Gatway path [1] triggers an AWS Lambda function [2] that retrieves a data from a DynamoDB [3] table and writes data to a object on Amazon S3 [4]. The API path contains a Document Type and a Customer ID. The Lambda function retrieves both the Document Type data and Customer ID data and combines them, writing the data to S3 and returning the object key [1]. The DynamoDB table name and the S3 bucket name are provided to the Lambda function via environment variables. The DynamoDB table schema is comprised of a Partition Key (PK) for looking up a given item, and a “data” field containing string contents. Document Type Items are prefixed with D#, and Customer items have a PK prefixed with C#.

**observability-driven-development**

[observability-driven-development](https://aws-oss.beachgeek.co.uk/210) this repo contains all the code from the Observability Driven Development workshop that promotes observability as a primary concern in the development process. Observability Driven Development elevates application and infrastructure observability to primary concerns in the development lifecycle. Operational health, security, compliance and business impact are instrumented early in the life cycle to provide comprehensive observability before, during, and after application deployments. Observability Driven Development aligns with development models like Test Driven Development and Behaviour Driven Development.

### AWS and Community blog posts

**NodeJS**

Great post from Nathan Peck for those who are NodeJS developers wanting to explore how to run their applications on Containers. In his post, [Your first Node.js container on AWS](https://aws-oss.beachgeek.co.uk/20r), Nathan gently guides you through everything you need to know to be able to confidently run your Node applications on Containers. Essential reading this week. [hands on]

**PyTorch**

In the post, [Distributed training with Amazon EKS and Torch Distributed Elastic](https://aws-oss.beachgeek.co.uk/20k),  Imran Younus and Alex Iankoulski detail the steps needed for running PyTorch distributed data parallel model training on EKS clusters. This post shows how you can use the [AWS DevOps for EKS](https://aws-oss.beachgeek.co.uk/20l) project created by the ML Frameworks team at AWS provides all the necessary scripts and tools to simplify the process and make distributed model training easily accessible.[hands on]

![architecture of solution for running pytorch on eks](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2022/08/24/ML-9589-image002.png)

**ASP.NET Core**

A couple of posts this weeks for Microsoft dot Net Core fans.

Many customers are looking to modernise their .NET applications via open source, and so in this first post [Accelerate containerization and migration of ASP.NET Core applications to AWS using AWS App2Container](https://aws-oss.beachgeek.co.uk/20h), Pavankumar Kasani and Prasad Rao provide a tutorial on how you can containerise your ASP.NET Core applications to Linux containers and migrate to AWS using AWS App2Container (A2C). AWS App2Container is a command-line tool for modernising .NET and Java applications into containerised applications. [hands on]

Following that we have Mukesh Murugan who has put together this post, [Hosting ASP.NET Core Web API with AWS Lambda – Truly Serverless REST APIs](https://aws-oss.beachgeek.co.uk/20w), provides a hands on post that will help you understand more about hosting ASP.NET Core Web API with AWS Lambda. [hands on]

**Babelfish for PostgreSQL**

In the post, [Provisioning an AWS PostgreSQL Aurora RDS Cluster with Babelfish using Terraform](https://aws-oss.beachgeek.co.uk/20v), Paul Bradley provides a nice introduction into Babelfish and then shows you how you can use Terraform and infrastructure as code to automate the configuration and deployment of this. 

**Terraform**

Vladyslav Budichenko shares how you can quickly use Terraform to deploy a static website on AWS in hist post, [Deploy a static website on AWS with terraform](https://aws-oss.beachgeek.co.uk/20x) [hands on]

**ECS compose-x**

[ECS compose-x](https://aws-oss.beachgeek.co.uk/20s) is an open source tool from AWS Community Builder John Mille that simplifies how you can deploy your infrastructure and applications on Amazon ECS, leveraging existing docker compose files and providing modularity via plugins. He has put together a couple of blog posts on a couple of solutions for [MQTT persistence with AWS IOT core bridge with Mosquitto](https://aws-oss.beachgeek.co.uk/20u) and [Prometheus proxy to AWS Managed Prometheus](https://aws-oss.beachgeek.co.uk/20t).

The first post hows to build a solution where all local MQTT transactions are synchronised on AWS for persistence and future-proofing. 

![solution architecture for mosquitto](https://labs.compose-x.io/_images/mosquitto-on-edge.jpg)

The second post (Running Prometheus with proxy to AWS Managed Prometheus) shows you how you can collect metrics with no requirement for local storage. AWS ECS Anywhere along with ECS Compose-X, makes it super easy. 

![architecture of solution for ecs compose-x](https://labs.compose-x.io/_images/prometheus-proxy-to-aps.jpg)

**Other posts you might like from the past week**

* [Modernize Moodle LMS with AWS serverless containers](https://aws-oss.beachgeek.co.uk/212) shares how you can deploy Moodle LMS using serverless containers technology on AWS to help remove the undifferentiated heavy-lifting in managing the servers

![architecture of modern serverless moodle](https://d2908q01vomqb2.cloudfront.net/9e6a55b6b4563e652a23be9d623ca5055c356940/2022/09/06/moodle-lms-with-aws-serverless-containers-figure-5-architecture-diagram.png)

* [Understanding and Cost Optimizing Amazon EKS Control Plane Logs](https://aws.amazon.com/blogs/containers/understanding-and-cost-optimizing-amazon-eks-control-plane-logs/) provides an overview of each type of Amazon EKS control plane log type, and explores ways to obtain insights from these logs while optimising on cost

![architecture for eks control plane logs cost optimising](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2022/08/18/EKS-GuardDuty-Blog-Arch.png)

* [Introducing vended logs for Amazon Managed Service for Prometheus](https://aws-oss.beachgeek.co.uk/213) provides a solution to demonstrate just how you can use logs with Amazon Managed Service for Prometheus to troubleshoot alert manager configuration issues
* [Monitoring Windows desktops on Amazon Workspaces using Amazon Managed Service for Prometheus and Amazon Managed Grafana](https://aws-oss.beachgeek.co.uk/20i) shows you how you can set up Amazon Managed Service for Prometheus, Amazon Managed Grafana, and a Prometheus server on Amazon Elastic Compute Cloud (Amazon EC2) to provide a monitoring solution for Amazon Workspaces [hands on]

![architecture of grafana and prometheus monitoring solution](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2022/08/31/prometheus-8-31-22.drawio.png)

* [Create an audit trail for an Amazon Aurora PostgreSQL table](https://aws-oss.beachgeek.co.uk/20j) covers how to create an audit log for a table in an Amazon Aurora PostgreSQL [hands on]

![overview of solution for postgres audit log](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2022/08/24/Aurora-Postgres-Audit-Trail-3-1024x398.png)

### Quick updates

**AWS Toolkit for VS Code**

Covering improvements in the "Connect to AWS" experience of the AWS Toolkit for VS Code (something I am very happy about as a regular user), in the post [Improvements to the connection experience in the AWS Toolkit for VS Code](https://aws-oss.beachgeek.co.uk/20m), Justin Keye dives deeper into what some of those improvements are.

**Kubernetes**

An additional 5 AWS Controllers for Kubernetes (ACK) service controllers have graduated to generally available status. Customers can now provision and manage AWS resources using ACK controllers for Amazon Relational Database Service (RDS), AWS Lambda, AWS Step Functions, Amazon Managed Service for Prometheus (AMP), and AWS Key Management Service (KMS).

ACK lets you define and use AWS service resources directly from Kubernetes clusters. With ACK, you can take advantage of AWS managed services for your Kubernetes applications without needing to define resources outside of the cluster or run services that provide supporting capabilities like databases or message queues within the cluster. [ACK now supports 12 AWS service controllers as generally available with an additional 13 in preview.](https://aws-oss.beachgeek.co.uk/20b)

**Prometheus**

Amazon Managed Service for Prometheus now provides Alert Manager & Ruler logs to help customers troubleshoot their alerting pipeline and configuration in Amazon CloudWatch Logs. Amazon Managed Service for Prometheus is a fully managed Prometheus-compatible monitoring service that makes it easy to monitor and alarm on operational metrics at scale. Prometheus is a popular Cloud Native Computing Foundation open source project for monitoring and alerting that is optimised for container environments. The Alert Manager allows customers to group, route, deduplicate, and silence alarms before routing them to end users via Amazon Simple Notification Service (Amazon SNS). The Ruler allows customers to define recording and alerting rules, which are queries that are evaluated at regular intervals. With Alert Manager and Ruler logs, customers can troubleshoot issues in their alerting pipelines including missing Amazon SNS topic permissions, misconfigured alert manager routes, and rules that fail to execute.

### Videos of the week

Donnie Prakoso

**Build on AWS open source**

Catch episode one of our new fortnight show, where Derek Bingham and myself talk with open source builders about their projects and we review the latest open source news and projects from this very newsletter.

{{< youtube yvaOErf6hcA >}}


**AWS Copilot**

In this video from the AWS Summit ASEAN, my colleague Donnie Prakoso shares how to deploy your containerised applications into Amazon ECS and AWS Fargate and build a release pipeline using an open source tool, AWS Copilot. Discover how to extend your applications with AWS CDK and integrate with AWS Copilot applications. From dev to deploy, this session is fully packed with demos.

{{< youtube FsccXOePwxQ >}}


**AWS SAM**

In another session from the AWS Summit ASEAN, Panyapol Cheunwatanakul explore AWS Serverless Application Model (SAM), an open-source framework for building serverless applications. During this video he walks you through building a fully serverless python HTTP API complete with an automated CI/CD pipeline using AWS SAM, and sharestips and tricks to get you started on your Serverless journey.


{{< youtube W6UK9ilNLws >}}


### Events for your diary

**Build on AWS Open Source**
**September 23rd, 9am BST**

The third episode of a new show where Derek Bingham and myself walk you through the latest AWS open source news, show you code and demos of some of the interesting projects we think you should know about and we invite guests to share their open source projects via the medium of demo.

This episode (S01E03) we are very lucky to have the AWS Cloudscape team who will be talking more about this open source project and then diving into the code. Should be great!

https://twitch.tv/aws

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)

**OpenSearchCon 2022**
**Sept 21st, 2022 Seattle**

Come to the first annual OpenSearchCon!

This day-long conference will be packed with presenters who build and innovate with OpenSearch. It doesn’t matter if you’re just getting started on your OpenSearch journey, running giant clusters, or contributing tons of code; the event is for everyone. Join us to celebrate the progress and look into the future of the project. Admission is free, and registration will be open in the next few weeks. All you will need to do is sign up, and get to Seattle!

Check out the full details, including signing up and location, at the [meetup page here](https://aws-oss.beachgeek.co.uk/1n1).


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)

