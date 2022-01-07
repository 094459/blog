---
title: 'AWS open source news and updates #62'
date: '2021-03-29'
tags : [ oss-newsletter ]
---
## March 29th, 2021 - Instalment #62

Newsletter #62. 

This week we have some really interesting new projects for you to take a look at, including someones first. We have cli tools to make it easier to work with the recently announced ECS Exec, to a serverless security tool, a very nice project that incorporates AWS CDK as part of an ArchOps project and more. We also have some great reads for you this week - check out the back story of Jupyter from Matt, a few posts on how AWS and Hugging Face are working together, some nice posts for you DevOps enthusiasts and more. With the usual round up of other stuff, there is a lot this week to keep you busy.

Before diving in, make sure you check out these two end of life announcements if you use Python or .NET Core.

**Python 2.7 and Lambda**

[Announcing end of support for Python 2.7 in AWS Lambda](https://aws-oss.beachgeek.co.uk/c5) Jonathan Tuliani shares something that everyone should be aware of. On July 15, 2021, AWS Lambda will deprecate Python 2.7 as a supported runtime, formally ending our Python 2.7 support. The post provides details of this announcement as well as providing you with answers to the most common questions and providing some things you should be thinking about. Essential reading if you think you might have any Python 2.7 code out there.

**.NET Core**

[.NET Standard 1.3 is no longer supported in AWS SDK for .NET version 3.7](https://aws-oss.beachgeek.co.uk/cb) Alex Shovlin provides a quick update on this announcement for old, non supported versions of .NET Core 1.0 to 1.3 and the corresponding AWS SDK for .NET. A reminder of what to do with recommendations so check this out.

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Sven Lito, Anton Babenko, RKVS Raman, Jake Hendy, Michael Cade, Ed Smith, 3CORESec, Garret Sweetwood, Justin Garrison, Yury Tsarev, Arturo Velasco, Katreena Mullican, Ryan Niksch, John Trollinger, Vigya Sharma, Joydeep Sinha, Balaji Kannan, Karthik Mohanasundaram, Paul White, Eduardo Rabelo, Jonathan Tuliani, César Prieto Ballester, Julien Simon, Matt Asay, Viji Sarathy, Imaya Kumar Jagannathan, Eric Kessler, Phillip Ninan, Krithivasan Balasubramaniyan, Yuxin Yang and Ryan Vanderwerf

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

**ecsgo**

[ecsgo](https://aws-oss.beachgeek.co.uk/ck) a first open source project is to be treasured, so I loved this from Ed Smith, creator of ecsgo, around the motivation for this project he wrote:
> Off the back of the recently announced ECS Exec, I realised I'd be using this a lot as it significantly improves troubleshooting and will make re-platforming to FARGATE a lot easier.
>
>I decided to make (yet another) CLI tool which makes selecting a task/container to connect to a little bit easier. The idea was very much inspired by gossm which I also use extensively, and have contributed to.
>
> The reason I didn't want to add this functionality to gossm was to keep a separation of concerns. gossm is great for interacting with EC2 instances in a variety of ways. This is purely for ECS (even though under the hood it still uses SSM for connectivity).
> 

![demo](https://user-images.githubusercontent.com/25430401/112647724-b7584a80-8e40-11eb-9928-d6a39f42d862.gif)

**Trapdoor**

[Trapdoor](https://aws-oss.beachgeek.co.uk/cj) this project from 3CORESec is an AWS Serverless Application meant to create and alert on [honeyTokens](https://aws-oss.beachgeek.co.uk/cl). They have helpfully created a blog post so you can find out more, [Trapdoor - The serverless HTTP honeypot](https://aws-oss.beachgeek.co.uk/cm) and the documentation and examples provided are very clear and you should be able to get this up and running in no time.

**aws-workbench**

[aws-workbench](https://aws-oss.beachgeek.co.uk/ci) this looks like a super interesting project from RKVS Raman, that introduced a new term I had not heard of before - ArchOps. I guess those Architects were feeling left out of the Ops party, and this tool, which leverages a number of open source tools such as Eclipse, AWS CDK and others, provides a visual editor that allows you to think about how you design and deploy AWS Services. Great documentation, this is a project that deserves a proper sit down and exploration with a cup of your favourite beverage.

![arch](https://aws-workbench.github.io/images/getting-started-images/workflow.png)

**terraform-aws-eventbridge**

[terraform-aws-eventbridge](https://aws-oss.beachgeek.co.uk/ch) if you are using Terraform, this new module is something you will like from Sven Lito and Anton Babenko. This Terraform module adds capability to create EventBridge resources. The module currently supports Cloudwatch Event Archive, Cloudwatch Event Bus, Cloudwatch Event Permission, Cloudwatch Event Rule and Cloudwatch Event Target.

**aws-devops-monitoring-dashboard**

[aws-devops-monitoring-dashboard](https://aws-oss.beachgeek.co.uk/cg) this is a new open sourced AWS solution that automates the process of ingesting, analysing, and visualising continuous integration/continuous delivery (CI/CD) metrics. These metrics are displayed in Amazon QuickSight dashboards to help DevOps leaders measure the impact of their DevOps initiatives and make data-driven decisions to drive continuous improvement in their development teams.

![arch](https://d1.awsstatic.com/Solutions/Solutions%20Category%20Template%20Draft/Solution%20Architecture%20Diagrams/aws-devops-monitoring-dashboard-architecture-diagram.d6d4eaebd6bb2fa199ab8444067018c088f9950a.png)

### Community open source posts

**Bottlerocket**

[Kubernetes, How To - AWS Bottlerocket + AWS EKS](https://aws-oss.beachgeek.co.uk/cn) this post from Michael Cade takes a look at Bottlerocket and getting started using it with Amazon EKS. 

**AWS CDK**

A couple of posts this week, apt with CDK Day rapidly approaching, so you should expect a flurry of great content. 

Starting off this week we have Phillip Ninan with [5 Reasons to Use AWS CDK!](https://aws-oss.beachgeek.co.uk/cd) - what only 5 :-) It is a short post, so why not check out these five reasons and see if they are enough to get you started.

Following that we have [CD-Okay that's how you do custom resources](https://aws-oss.beachgeek.co.uk/co) from Jake Hendy who takes a look at AWS CDK custom resources. If you are familiar with custom resources from AWS CloudFormation, then Jakes shows you how these are different before diving deep and showing you how you can look to get even more value from custom resources. 

**Machine Learning**

This blog post, [AWS ML Community showcase: March 2021 edition](https://aws-oss.beachgeek.co.uk/cp) from Cameron Peron has a number of great projects from the AWS ML community that you can try out for yourself, including the really incredible and inspirational project around helping your toddlers to soar like a bird. Several of these projects provide source code so you can try and get these up and running for yourself. Pretty amazing stuff from the AWS ML Community.

![bird](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2021/03/26/Header.jpg)

### AWS open source posts

**FluxCD**

If you are interested in GitOps, then César Prieto Ballester has a post that you will want to check out. [CI/CD on Amazon EKS using AWS CodeCommit, AWS CodePipeline, AWS CodeBuild, and FluxCD](https://aws-oss.beachgeek.co.uk/c6) will help you to speed up the development of your Kubernetes infrastructure by using a continuous integration (CI) pipeline to build your Docker images and automatically deploy them to Amazon Elastic Kubernetes Service (Amazon EKS) cluster using FluxCD and the GitOps philosophy. Flux is an open source tool that automatically ensures that the state of a cluster matches the config in git. It uses an operator in the cluster to trigger deployments inside Kubernetes, which means you don't need a separate CD tool.

Cesar takes a look at how you can deploy the infrastructure needed using AWS CDK, and it is good to see Python being used. Full source code is available so you can build your own GitOps CI/CD pipeline and then tell all your friends about it!

![arch](https://d2908q01vomqb2.cloudfront.net/7719a1c782a1ba91c031a682a0a2f8658209adbf/2021/03/09/diagram.png)

**Jenkins via Terraform**

[Building a serverless Jenkins environment on AWS Fargate](https://aws-oss.beachgeek.co.uk/ce) this post from Krithivasan Balasubramaniyan is walk you through how to set up a completely serverless Jenkins environment on AWS Fargate using Terraform. Jenkins is a popular open-source automation server that enables developers around the world to reliably build, test, and deploy their software, and Terraform is an open-source infrastructure as code software tool from HashiCorp. Using Terraform to build a Jenkins environment via serverless technology sounds like a great combination, so to find out more, read on.

![arch](https://d2908q01vomqb2.cloudfront.net/7719a1c782a1ba91c031a682a0a2f8658209adbf/2021/03/24/Jenkins.jpg)

**AWS Greengrass/Amazon SageMaker Neo**

Yuxin Yang and Ryan Vanderwerf have collaborated on a new blog post, [Using AWS IoT Greengrass Version 2 with Amazon SageMaker Neo and NVIDIA DeepStream Applications](https://aws-oss.beachgeek.co.uk/cf) that shows you a couple of ways you can use AWS Greengrass v2 (an Internet of Things open source edge runtime and cloud service that helps you build, deploy, and manage device software) to build on the NVIDIA Jetson devices. The post also uses another open source project, Amazon SageMaker NEO, that helps you to optimise your machine learning models for edge devices.

![arch](https://d2908q01vomqb2.cloudfront.net/f6e1126cedebf23e1463aee73f9df08783640400/2021/03/26/architecture-integration-between-aws-iot-greengrass-v2-and-nvidia-jetson-modules.png)

Source code and project walkthrough provided in the post.

**Jupyter**

[How and why AWS contributes to Jupyter](https://aws-oss.beachgeek.co.uk/c9) Matt Asay with a great post on the story of Jupyter, the open source project widely used in data science, machine learning, and scientific computing. There is so much more to this project though, and whether you use Jupyter or not, dip your toes into this post and enjoy the ride. These posts are useful for helping you understand the different journeys that open source projects take, and some of the themes talked about might resonate with you.

**Hugging Face**

I posted a few weeks ago the great open source backstory to Hugging Face. This week we had a couple of blog posts that added to that story. First up we have [Hugging Face and AWS partner to bring over 7,000 NLP models to Amazon SageMaker with accelerated inference and distributed training](https://aws-oss.beachgeek.co.uk/c7), with the announcement of Hugging Face has selected AWS as its preferred cloud provider. Hugging Face recently introduced AutoNLP and the Accelerated Inference API, new hosted services built on AWS using Amazon SageMaker, that makes it easy to quickly build, train, and deploy ML models in the cloud and at the edge.

Following that we have Julien Simon diving deep in [AWS and Hugging Face Collaborate to Simplify and Accelerate Adoption of Natural Language Processing Models](https://aws-oss.beachgeek.co.uk/c8) where Julien walks you through how to get started with Hugging Face models using Amazon SageMaker. If that was not enough, Julien also created a video on his channel (make sure you subscribe, he always has plenty of great open source projects he uses and talks about).

{% youtube leyrCgLAGjM %}

**Prometheus**

[Metrics collection from Amazon ECS using Amazon Managed Service for Prometheus](https://aws-oss.beachgeek.co.uk/ca) Viji Sarathy and Imaya Kumar Jagannathan present a blog post and ready to roll solution that will enable customers to deploy Prometheus server on an Amazon ECS cluster, dynamically discover the set of services to collect metrics from, and send the metrics to AMP for subsequent query and visualisation as well as long-term storage.

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/03/12/ijaganna_Prometheus-Metrics_f2.png)

This is a really nice post, so make sure you check it out.

**GraphiQL**

[Explore AWS AppSync APIs with GraphiQL from your local machine](https://aws-oss.beachgeek.co.uk/c4) is a great post from Eduardo Rabelo, where he shows you how you can inspect from your local browser a GraphQL schema and prototype queries from your local machine using a local GraphiQL instance. Eduardo shows you how you can use this to improve your local developer setup.

![demo](https://d2908q01vomqb2.cloudfront.net/0a57cb53ba59c46fc4b692527a38a87c78d84028/2021/03/23/GraphiQL4.png)

**PennyLane**

[Working with PennyLane for variational quantum algorithms and quantum machine learning](https://aws-oss.beachgeek.co.uk/cc) Eric Kessler with a quick update on the work we are doing with the open source team at PennyLane to support the goal of building better tools for developers and researchers by combining ideas from ML and quantum computing.

**OpenSCAP**

[How to automate SCAP testing with AWS Systems Manager and Security Hub](https://aws-oss.beachgeek.co.uk/c1) John Trollinger takes a look at how to automate OpenSCAP to improve your view of your IT systems’ compliance status. OpenSCAP is an open-source NIST-certified security and compliance tool and uses the Security Content Automation Protocol (SCAP) to automate continuous monitoring, vulnerability management, and reporting of security policy compliance data.

![arch](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2021/03/19/Automate-SCAP-testing-2021-1-1.png)

**Elasticsearch**

[Introducing Auto-Tune in Amazon ES](https://aws-oss.beachgeek.co.uk/c3) Vigya Sharma, Joydeep Sinha, Balaji Kannan, Karthik Mohanasundaram, and Paul White talk about a new innovation available to customers of Amazon Elasticsearch Service that is powered by the Open Distro for Elasticsearch Performance Analyser plugin, which provides fine-grained metrics from OS, JVM, and the Elasticsearch cluster. In this post, you will learn how this new capability can helps to automatically optimise resources in Elasticsearch clusters to improve its performance and availability. 

![memory](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2021/03/23/bdb1335-auto-tune-es-6.jpg)

**OBS**

[Streaming video to AWS Elemental MediaConnect using Zixi SDK](https://aws-oss.beachgeek.co.uk/by) don't miss this three part series from Arturo Velasco and Katreena Mullican that show you how you can integrate some cool open source projects (ffmpeg and [OBS - Open Broadcast Software](https://aws-oss.beachgeek.co.uk/bz)) with Zixi and AWS services such as AWS Elemental using the Zixi SDK for AWS Elemental MediaConnect. This series will help you install and configure OBS Studio and Zixi-MediaConnect on a local system, create an encrypted MediaConnect flow, and then stream a local VOD asset to Zixi Player on end user mobile devices.

**VS Code**

The AWS Toolkit for Visual Studio Code is an open source plug-in for the Visual Studio Code that makes it easier to create, debug, and deploy applications on Amazon Web Services. The toolkit provides an integrated experience for navigating AWS resources (e.g., S3, CloudWatch Logs), developing serverless applications, including assistance for getting started, step-through debugging, and deploying from the IDE. 

A new release of the AWS Toolkit for VS Code means customers can use federated credentials, MFA and AWS Single Sign-On (AWS SSO) to connect Visual Studio Code to AWS. Using AWS SSO, users can sign in to their organization’s Active Directory, a built-in AWS SSO directory, or another external identity provider (IdP) connected to AWS SSO. Regardless of which IdP you use, AWS SSO abstracts those distinctions away, and they all work with the AWS Toolkit, as explained in this short blog post from Garret Sweetwood, [Introducing AWS SSO support in the AWS Toolkit for VS Code](https://aws-oss.beachgeek.co.uk/bv) will help you get started.

### Quick updates

**Kubernetes**

A couple of new things to be aware about this week, especially useful to know if you are planning or already running machine learning workloads on Kubernetes.

First up is news that Amazon Elastic Kubernetes Service (EKS) now supports adding Amazon EC2 P4d instances as worker nodes to clusters in regions where P4d is available. Amazon EC2 P4d instances are the next generation of GPU-based instances that provide the best performance for machine learning (ML) training and high performance computing (HPC) in the cloud for applications such as natural language processing, object detection and classification, seismic analysis, and genomics research.

Following that we have news that Amazon EKS now supports Elastic Fabric Adapter (EFA), enabling applications to achieve the performance of an on-premises machine learning training cluster, with the scalability, flexibility, and elasticity provided by Kubernetes clusters managed by EKS. Kubernetes has become a leading platform for distributed machine learning applications, as it makes it easy to scale clusters to a large number of nodes with powerful GPU based instances. At scale, network bandwidth can become a bottleneck for distributed workloads. Elastic Fabric Adapter (EFA) is a network interface for Amazon EC2 instances that enables you to run applications requiring high levels of inter-node communications at scale on AWS. You can now easily integrate EFA into distributed training applications on Kubernetes by leveraging the newly released EFA device plugin, which automatically discovers and mounts EFA devices into pods that request them. This allows you to add bandwidth as ML training jobs scale horizontally to accommodate ever increasing model sizes. You can now take full advantage of the latest EC2 GPU powered instance types such as P4d that include multiple EFA devices for even greater improvements with model training time.

**Redis**

Amazon ElastiCache for Redis now supports running clusters with high availability across multiple AWS Local Zones. AWS Local Zones are an extension of an AWS Region where you can run your latency-sensitive applications using AWS services in geographic proximity to end-users. Previously, Amazon ElastiCache for Redis only supported launching a cluster in a single AWS Local Zone. Support for launching your Amazon ElastiCache for Redis cluster across multiple AWS Local Zones enables you to configure your cluster with high availability. In the unlikely event of a specific AWS Local Zone outage, Amazon ElastiCache will failover and promote a read-replica node in other AWS Local Zones to continue serving traffic for your applications.

**Apache Flink**

Amazon Kinesis Data Analytics for Apache Flink now supports streaming applications built using Python version 3.7. This enables you to write streaming applications in the Python language and run them using Apache Flink v1.11 on Amazon Kinesis Data Analytics. Apache Flink v1.11 offers support for Python through the Table API, which is a unified, relational API for data processing.

**Red Hat OpenShift**

Containers have proven popular with AWS and Red Hat customers because they increase developer velocity, improve application portability, and enable faster application development. Currently, AWS offers a broad range of containers technology in the cloud, including Amazon Elastic Containers Service (ECS), Amazon Elastic Kubernetes Service (EKS), Amazon ECS and Amazon EKS with AWS Fargate. Now customers have an additional option with the launch of Red Hat OpenShift Service on AWS (ROSA), which provides a new managed service that makes it easier for Red Hat OpenShift customers to build, scale, and manage containerised applications on AWS.

With ROSA, customers can quickly and easily create Kubernetes clusters using familiar Red Hat OpenShift APIs and tooling, and seamlessly access to the full breadth and depth of AWS services, all from within the AWS console. Furthermore, ROSA maintains key compliance validations customers rely on with OpenShift Container Platform, including SOC-2, ISO-27001 and PCI.

For more details, including a look at the ROSA cli and how to get started, check out this blog post from Ryan Niksch, [What’s new with Red Hat OpenShift Service on AWS](https://aws-oss.beachgeek.co.uk/c0).

**OpenTelemetry**

AWS Distro for OpenTelemetry (ADOT) 0.8.0 is now available with StatsD support in the Collector and stable Java 1.0 support with an auto-instrumentation agent for observing your Java applications. Alolita Sharma and Nizar Tyrewalla share more details in the post, [AWS Distro for OpenTelemetry adds StatsD and Java support](https://aws-oss.beachgeek.co.uk/c2) 

### Videos of the week

**k8gb - creating global load balancers for your Kubernetes applications**

This week, another great session from the Containers from the Couch team, this time Justin Garrison and Yury Tsarev show you how you can create hlobal Kubernetes load balancer with the open source project, [k8gb](https://aws-oss.beachgeek.co.uk/bx).

{% youtube 5pe3ezSnVI8 %} 

### Events for your diary

**CDK Day**
**April 30th**

Announced this week was the second [CDK Day](https://sessionize.com/cdkday/), which will be on April 30th. Check out [the web page](https://sessionize.com/cdkday/) to find out more about the first CDK Day, which was incredible. This second event promises to be even better. The CFP is open until the 19th of March. Check out this supporting blog post, [CDK Day CFP Is Open!!!!](https://aws-oss.beachgeek.co.uk/4v) from Matt as to what to expect and what they are looking for when it comes to sessions.

**Cloud Native Rust Day**
**May 3rd**

Rust is a language empowering everyone to build secure, reliable, and efficient software. Rust is becoming more widely used in cloud native, powering everything from lightning-fast service meshes and powerful developer tools to internet-scale distributed databases.

Come explore what makes Rust a fantastic choice for new cloud native development, and learn about how the community uses Rust today. Find out [more and register here](https://aws-oss.beachgeek.co.uk/5y).

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen).