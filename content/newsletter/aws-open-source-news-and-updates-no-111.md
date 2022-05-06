---

title: 'AWS open source news and updates #111'
date: '2022-05-06'
tags : [ oss-newsletter, aws open source, Kubernetes, Ray, Locust, AWS Copilot, AWS SAM, PostgreSQL, Terraform, VSCode, Smithy, AWS Distro for OpenTelemetry, Apache Livy, OpenSearch]

---

## May 6th, 2022 - Instalment #111

Newsletter #111. 

Welcome to edition #111 of the AWS open source newsletter, a bit later this week but that was so I could pack in even more great open source content. This week we have another round up of new open source projects from the AWS community that include tools to help you manage your AWS CloudFront distributions, resource providers for CloudFormation for Confluent users, managing Amazon Route53 via the command line, a nice tool for Rust developers working with AWS Lambda, a nice tool to help you find your CIDR address ranges, and many more including some great samples.

If you are looking to catch up on the latest posts, we have topics covering Kubernetes, Ray, Locust, AWS Copilot, AWS SAM, PostgreSQL, Terraform, Smithy, AWS Distro for OpenTelemetry, Apache Livy, OpenSearch, and more. This weeks video is perfect for .NET developers and looks at an open source project from AWS that helps you migrate your .NET applications to .NET Core.

Finally, we have the event section, with lots of events happening over the next few weeks. AWS Container Day is happening at the beginning of next week. Check out the details in the Events section below for more details, but this is certainly a must attend event, with great sessions spread out over a number of days. The perfect way to get ready for KubeCon.

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Steven David , Sean Lee, Jeongyeol Lee, Seungjae Lee, Wontag Han, Jonas Woo, Adam Thomas, Paavan Mistry, Matt DePietro, Sivamuthu Kumar, Sofian Hamiti, Prayag Singh, Daniel Yeo and Yiqin(Miranda) Zhu, Gilad David Maayan, John Preston, Cooper Walbrun, Mathew Duggan, Shahar Shaked, Bharat Gamini and John Benninghoff.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest open source projects

#### Community

**cloudfront-manager**

[cloudfront-manager](https://aws-oss.beachgeek.co.uk/1nf) is a new open source tool from AWS Community Builder Harinder Seera that will help you to Invalidate, Enable, Disable and Delete Cloudfront distribution. Also display detail of a distribution. He has put together this blog post, [AWS Cloudfront Manager Utility - How To Guide For Windows](https://aws-oss.beachgeek.co.uk/1ng) that helps you get start with this tool.

**aws-cfn-confluentcloud-iam-serviceaccount**

[aws-cfn-confluentcloud-iam-serviceaccount](https://aws-oss.beachgeek.co.uk/1ni) is an open source 3rd party CloudFormation resource that users of Confluent should check out. It allows to create a new Service Account into an organization in Confluent Cloud via API. Nice work John!


#### Tools

**aws-ensure-route53**

[aws-ensure-route53](https://aws-oss.beachgeek.co.uk/1nj) is a new open sourced tool from nathants that enables you to easily manage route53 on multiple accounts.

**cargo-lambda**
[cargo-lambda](https://aws-oss.beachgeek.co.uk/1nk) this project provides a Cargo subcommand to help you work with AWS Lambda. The **new** subcommand creates a basic Rust package from a well defined template to help you start writing AWS Lambda functions in Rust. The **build** subcommand compiles AWS Lambda functions natively and produces artifacts which you can then upload to AWS Lambda or use with other echosystem tools, like SAM Cli or the AWS CDK. There are other commands (**watch, invoke, deploy**), so if you are a Rust developer exploring AWS Lambda, this project is for you.

**aws-cidr-finder**

[aws-cidr-finder](https://aws-oss.beachgeek.co.uk/1nl) this project from Cooper Walbrun provides a Python CLI tool for finding unused CIDR blocks in AWS VPCs and outputs them to STDOUT. It is very simple, but can be quite useful for users who manage many subnets across one or more VPCs. Read more in the post from Mathew Duggan, [Quickly find unused CIDR blocks in your AWS VPC](https://aws-oss.beachgeek.co.uk/1nm)

**ec2-spot-interrupter-cli**

[ec2-spot-interrupter-cli](https://aws-oss.beachgeek.co.uk/1nv) this is a neat tool that provides a command line interface to simulate EC2 Spot Instances interruptions using AWS Fault Injection Simulator (FIS).

**amazon-cloudwatch-retention-period-setter**

[amazon-cloudwatch-retention-period-setter](https://aws-oss.beachgeek.co.uk/1nt) By default, all the logs stored in Amazon CloudWatch log groups are kept indefinitely and their retention period is set to Never Expire which might result in excessive costs. To reduce storage costs, customers should consider changing the default retention period. Changing Amazon CloudWatch log groups retention period manually could be tedious considering that you need to track all the newly created log groups. This repo contains a solution to help you automate that, and links to a detailed walk through of how to configure this.

#### Demos, Samples and Workshops

**aws-global-pubsub-api**

[aws-global-pubsub-api](https://aws-oss.beachgeek.co.uk/1nx) This is an implementation of a multi-region PubSub real-time API based on Serverless/Functionless WebSockets where clients are subscribed to a specific channel and messages are pushed automatically to clients listening/subscribed to the channel in both regions. Connections management, scalability, fan-out and broadcasting are all automatically handled by the regional AppSync APIs.

![architecture of global pubsub](https://github.com/aws-samples/aws-global-pubsub-api/blob/main/images/globalWSAPI.png?raw=true)

**deploy-kubernetes-resources-to-amazon-eks-using-azure-devops**

[deploy-kubernetes-resources-to-amazon-eks-using-azure-devops](https://aws-oss.beachgeek.co.uk/1nu) if you are using Azure DevOps as part of your developer tooling, then this project might be of interest. This pattern aims to provide guidance on how to deploy a containerized application to Amazon EKS cluster from Azure DevOps using Helm chart. The pattern can be further extended by modifying the pipeline template shared here to use the Azure pipelines service connection for AWS in order to query and use data from AWS Cloud.

![architecture for azure devops on aws](https://github.com/aws-samples/deploy-kubernetes-resources-to-amazon-eks-using-azure-devops/blob/main/docs/img/Architecture.png?raw=true)

**observability-with-amazon-opensearch**

[observability-with-amazon-opensearch](https://aws-oss.beachgeek.co.uk/1ns) this repo contains a workshop where you will learn how to instrument, collect, and analyze metrics, traces, and log data all the way from user front ends to service backends and everything in between. Put this together with OpenSearch, AWS Distro for OpenTelemetry, FluentBit, and Data Prepper.

![architecture for workshop opensearch observability](https://github.com/aws-samples/observability-with-amazon-opensearch/blob/main/assets/arch.jpg?raw=true)

**aws-sagemaker-pipelines-skin-classification**

[aws-sagemaker-pipelines-skin-classification](https://aws-oss.beachgeek.co.uk/1nw) This repository aims at enabling the customization of a built-in SageMaker pipeline for MLOps to user-defined workflow. In this case we address a computer vision use case for skin lesion classification. This is a step-by-step guide on how to adapt an existing code to the CI/CD pipeline in AWS SageMaker Studio.

**amazon-elasticache-demo-using-aws-cdk**

[amazon-elasticache-demo-using-aws-cdk](https://aws-oss.beachgeek.co.uk/1ny) this repo contains code to deploy Amazon Elasticache for Redis using AWS Cloud Development Kit (AWS CDK). The demo configures a host for the web application using Amazon Elastic Compute Cloud (Amazon EC2). We load a large dataset into a MySQL database hosted on Amazon Relational Database Service (Amazon RDS). To cache queries we use Amazon ElastiCache for Redis. The following architecture diagram shows the solution components and how they interact.

![architecture of demo](https://github.com/aws-samples/amazon-elasticache-demo-using-aws-cdk/blob/main/images/00_architecture.png?raw=true)

### AWS and Community blog posts

**Smithy**

Smithy is an open sourced interface definition language and set of tools that allows developers to build clients and servers in multiple languages. Adam Thomas shares his excitement about the developer preview of Smithy’s server and client generators for TypeScript in his post, [Smithy Server and Client Generator for TypeScript (Developer Preview)](https://aws-oss.beachgeek.co.uk/1n4). This enables developers to write concise, type-safe code in the same model-first manner that AWS has used to develop its services. Recommended read this week. [hands on]

![architecture of smithy server](https://d2908q01vomqb2.cloudfront.net/7719a1c782a1ba91c031a682a0a2f8658209adbf/2022/04/27/Picture1-3.png)

**Apache Livy**

Apache Livy is a service that enables easy interaction with a Spark cluster over a REST interface. In [Access Apache Livy using a Network Load Balancer on a Kerberos-enabled Amazon EMR cluster](https://aws-oss.beachgeek.co.uk/1nr) Bharat Gamini and John Benninghoff discuss how to provide Kerberos ticket access to Livy for external systems like Airflow and Notebooks. [hands on]

**OpenSearch**

Shahar Shaked put together this blog post, [Introducing open-source Kubernetes Operator for OpenSearch](https://aws-oss.beachgeek.co.uk/1nn) that takes a look at the OpenSearch Operator. This is a fully open-source Kubernetes Operator, licensed as Apache 2.0, and is used for automating the deployment, provisioning, management, and orchestration of OpenSearch clusters and OpenSearch dashboards.

**Ray**

Ray is an open source (Apache 2.0 License) framework to build and scale distributed applications. In the post, [Announcing Amazon CloudWatch for Ray](https://aws-oss.beachgeek.co.uk/1ne) Daniel Yeo and Yiqin(Miranda) Zhu share how with CloudWatch for Ray, you can now deploy your Ray applications in production on Amazon EC2 and monitor their health with near real-time metrics, logs, and alarms.

**Terraform**

A great post from Andrew Wasilczuk at the Scale Factory, that shows you how you can use Terraform to automat the deployment and configuration of AWS Control Tower. If you have been looking to automate how you deploy and comnfigure AWS Control Tower, you need to read the post, [Is AWS Control Tower suitable for Terraform users?](https://aws-oss.beachgeek.co.uk/1nc)

**AWS Copilot**

In the post AWS Copilot GitHub Actions, AWS Community Builder Sivamuthu Kumar shows you how you can use AWS Copilot, an open-source command-line interface that makes it easy for developers to build, release, and operate production-ready containerised applications on AWS, together with GitHub actions. [hands on]

**AWS Amplify**

[Using Open Source AWS Amplify JS with Cognito to Secure Angular Apps](https://aws-oss.beachgeek.co.uk/1nh) is a post from Gilad David Maayan is a guided walk through of how set up the Cognito UserPools JWT authentication flow and how it will integrate with an Angular Web Application. [hands on]

**VSCode**

Code-server is a popular open source project that allows you to access VS Code via a browser. Sofian Hamiti and Prayag Singh have taken this a step further and collaborated on this post, [Hosting VS Code on SageMaker Studio](https://aws-oss.beachgeek.co.uk/1nb) where they walk you through deploying VS Code within SageMaker Studio. [hands on]

![architecutre of solution](https://miro.medium.com/max/1400/1*gN__nvpP9_ENd5nx53_0Ew.jpeg)

**Locust**

Locust is an open-source load testing tool I have featured in previous newsletters that comes with a real-time dashboard and programmable test scenarios. 

![architecture of locust solution](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2022/05/03/locust-1.jpg)

In the post, [Load testing your workload running on Amazon EKS with Locust](https://aws-oss.beachgeek.co.uk/1n5), Sean Lee, Jeongyeol Lee, Seungjae Lee, Wontag Han, and Jonas Woo walk you through the steps to build two Amazon EKS clusters, one for generating load using Locust and another for running a sample workload. You can use this as the basis for your own setup. [hands on]

![example locust dashbaord](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2022/05/03/locust-11.jpg)

**Kubernetes**

In the post [Introducing Kubernetes Resource View in Amazon EKS console](https://aws-oss.beachgeek.co.uk/1n9) is a post from Paavan Mistry and Matt DePietro that explores an update within the Amazon EKS console which will mean you are able to see all Kubernetes API resource types running in your Amazon EKS clusters, making it easier to visualise and troubleshoot your Kubernetes applications using Amazon EKS.

I also found this post from AWS Partner Weaveworks, [Weaveworks & AWS: Best Practices for Hybrid Cloud Kubernetes with EKS and Weave GitOps](https://aws-oss.beachgeek.co.uk/1nd)  which provides and overview and links to the whitepaper on currnet good practices for Hybrid Cloud Kubernetes with EKS. Absolutely essential reading if you are using Amazon EKS.

**AWS Distro for OpenTelemetry**

AWS Distro for OpenTelemetry (ADOT) is a secure, AWS-supported distribution of the OpenTelemetry project. Viji Sarathy and Imaya Kumar Jagannathan have come together to write, [Metrics and traces Collection from Amazon ECS using AWS Distro for OpenTelemetry with Dynamic Service Discovery](https://aws-oss.beachgeek.co.uk/1na) showing you how you can deploy a single instance of an ADOT Collector to an Amazon ECS cluster and collecting Prometheus metrics from workloads that were dynamically discovered by taking advantage of the integration between Amazon ECS and AWS Cloud Map. [hands on]

![architecture of solution](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2022/05/03/opentelemetry-1.png)

**Other posts worth checking out**

* [Automate interval partitioning maintenance, and monitoring in Amazon RDS for PostgreSQL and Amazon Aurora PostgreSQL](https://aws-oss.beachgeek.co.uk/1n3) demonstrates how to configure interval partitioning in an Aurora PostgreSQL database using PostgreSQL extensions such as pg_partman and pg_cron
* [AWS announces support for Android, iOS, and MacOS games with AWS GameKit for Unreal Engine](https://aws-oss.beachgeek.co.uk/1n6) is an update to share how AWS GameKit now supports Android, iOS, and MacOS games developed with Unreal Engine
* [Accelerate hybrid quantum-classical algorithms on Amazon Braket using embedded simulators from Xanadu’s PennyLane featuring NVIDIA cuQuantum](https://aws-oss.beachgeek.co.uk/1n7) explores what are Quantum embedded simulators and how you might use them

![example architecture of embedded simulators](https://d2908q01vomqb2.cloudfront.net/5a5b0f9b7d3f8fc84c3cef8fd8efaaa6c70d75ab/2022/05/05/hybrid_jobs_how_it_works.jpg)

**Case Studies**

* [Ogury Uses Open Source Technologies on AWS to Run Low-Latency Machine Learning](https://aws-oss.beachgeek.co.uk/1n8) is a great case study showcasing how Ogury, a Personified Advertising company, is using open source machine learning (ML) on AWS to deliver a planned 300,000 inferences per second under 10-ms latency

![overview of ogury architecture](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2022/03/31/ONNX1.png)

### Quick updates

**PostgreSQL**

Amazon Relational Database Service (Amazon RDS) for PostgreSQL announces support for PostgreSQL 14 with three levels of cascaded read replicas, 5 replicas per instance, supporting a maximum of up to 155 read replicas per source instance. You can now create Single-AZ or Multi-AZ cascaded read replica DB instances in same region or any one cross region from another read replica instance, enabling you to build a more robust disaster recovery architecture.

Starting with Amazon RDS for PostgreSQL 14.1 and higher, read intensive workloads such as data analytics can now benefit from up to 155 cascaded read replicas that offer up to 30 times higher read capacity versus previous versions of PostgreSQL, thereby reducing the load on source instance. You can now also pre-create read replicas for your selected disaster recovery target read replica and utilise read scaling immediately after promoting the target. The cascaded read replicas also come with the option to enable automated backup that allows for a quicker promotion of read replica to source instance since only incremental snapshot is required for the promoted read replica.

**AWS SAM**

Now you can use the AWS Serverless Application Model (AWS SAM) CLI to enable AWS X-Ray tracing in your AWS SAM templates automatically, without manually authoring your AWS SAM templates. This makes it easier to centrally manage AWS X-Ray tracing across your Lambda functions in your serverless application.

The AWS SAM CLI is a developer tool that makes it easier to initialise, build, package, test on local and cloud, and deploy serverless applications. AWS X-Ray helps you analyse and debug your distributed applications, such as those built using a microservices architecture. AWS X-Ray provides an end-to-end view of requests as they travel through your application, making it easier to monitor and troubleshoot complex serverless architectures. Enabling tracing through the AWS SAM CLI reduces the complexity of setting up tracing on each of your Lambda functions.

To enable tracing through the AWS SAM CLI, simply add --tracing flag to the sam init command invocation to activate tracing. You can enable tracing across all Lambda functions in your AWS SAM application, or for specific functions. 

### Videos of the week

**.NET Core**

Steven David helps you learn about Porting Assistant for .NET, an analysis tool that scans .NET Framework applications and generates a .NET Core compatibility assessment, helping you port your applications to cloud native services faster.

{{< youtube JDGc6-v-yPA >}}

### Events for your diary

Events coming up in the next few weeks. I will be at the AWS Summit Berlin and KubeCon so if you are also attending, let me know - would be great to meet some of you in person.

**AWS Container Day**
**May 10th-13th**

With KubeCon around the corner, a few days before AWS is holding its annual Container Day event where we share a number of great sessions covering everything you need to know about running containers on AWS. You can check out the blog post, [Save the date: AWS Containers events in May](https://aws-oss.beachgeek.co.uk/1no) that provides links and more details. Whilst you do not need to register as these will be live streamed, registration will allow you to set a reminder and calendar invite so you don't miss any of these great sessions.

If you want to check out the schedule of speakers and topics, check out [AWS Container Day with Docker](https://aws-oss.beachgeek.co.uk/1np) and [AWS Container Days @ KubeCon + CloudNativeCon Europe 2022](https://aws-oss.beachgeek.co.uk/1nq) for the full breakdown.


**AWS Berlin Summit**
**May 11th/12th**

Aside from the AWS open source sessions (including me again, talking about Apache Airflow) we will have our very own Spot and myself manning the open source booth. Really looking forward to this and would love to see you come down and share your open source projects on our booth.

[AWS Berlin Summit registration page](https://aws.amazon.com/events/summits/berlin/)

**KubeCon**
**May 16th-20th, Valencia Spain**

The Cloud Native Computing Foundation’s flagship conference gathers adopters and technologists from leading open source and cloud native communities in Valencia, Spain from 16 – 20 May 2022. I will be there with many of the open source team and other AWS colleagues, so if you are going, make sure you swing by the AWS Booth.

Find out more about the [event here](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/).

**GitOpsCon Europe**
**May 17th, Valencia Spain**

GitOpsCon Europe is designed to foster collaboration, discussion, and knowledge sharing on GitOps. This event is aimed at audiences that are new to GitOps as well as those currently using GitOps within their organisation. Get connected with others that are passionate about GitOps. Learn from practitioners about pitfalls to avoid, hurdles to jump, and how to adopt GitOps in your cloud native environment.

The event is vendor-neutral and is being organised by the CNCF GitOps Working Group. Topics include getting started with GitOps, scaling and managing GitOps, lessons learned from production deployments, technical sessions, and thought leadership.

Read more about this from the official page [here](https://events.linuxfoundation.org/gitopscon-europe/).

**CDK Day**
**May 26th - Virtual**

This is a community organised event about AWS CDK, cdktf, projen and cdk8s. This will be third year they run this event, and if the previous two are anything to go by, this will be essential viewing - live streamed via You Tube. Check out and register for the event over at their home page at [https://www.cdkday.com/](https://www.cdkday.com/)

**BOSC 2022**
**July 13-14, Madison, Wisconsin, USA**

The Bioinformatics Open Source Conference (BOSC) has been held annually since 2000, and this year AWS is proud to be a platinum sponsor for this event. BOSC covers all aspects of open source bioinformatics software and open science, including (but not limited to) these topics, Open Science and Reproducible Research, Open Biomedical Data, Citizen/Participatory Science, Standards and Interoperability, Data Science Workflows, Open Approaches to Translational Bioinformatics, Developer Tools and Libraries, Inclusion, and Outreach and Training. This is a hybrid event (in person/virtual) and you find out more by checking out the event page, [BOSC 2022](https://aws-oss.beachgeek.co.uk/1li)

**OpenSearch**
**Every Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting - Feb2022](https://aws-oss.beachgeek.co.uk/1az)

**OpenSearchCon 2022**
**Sept 21st, 2022 Seattle**

Come to the first annual OpenSearchCon!

This day-long conference will be packed with presenters who build and innovate with OpenSearch. It doesn’t matter if you’re just getting started on your OpenSearch journey, running giant clusters, or contributing tons of code; the event is for everyone. Join us to celebrate the progress and look into the future of the project. Admission is free, and registration will be open in the next few weeks. All you will need to do is sign up, and get to Seattle!

Check out the full details, including signing up and location, at the [meetup page here](https://aws-oss.beachgeek.co.uk/1n1).


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)