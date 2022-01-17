---
title: 'AWS open source news and updates No.41'
date: '2020-10-26'
tags : [ oss-newsletter ]
---
## October 26th - Instalment #41

Episode No.41 - As we approach Halloween this week, there is nothing scary or frightening in this episode, just a shockingly good amount of new open source projects, blog posts, case studies and events to add to your diary. Last week was dominated by the Open Distro for Telemetry preview announcement (read all about that in a minute) but there is also great stuff such as the unboxing of HashiCorp's Waypoint by the Containers from the Couch team, something for Java folk and another Graviton2 post.

Without further ado, over to the main talk of last week...


### Open Distro for Telemetry

> "Observability is a study of the system in motion" and "Debugging is about the system at rest" [Charity Majors](https://twitter.com/mipsytipsy)

[Public Preview – AWS Distro for OpenTelemetry](https://aws.amazon.com/blogs/aws/public-preview-aws-distro-open-telemetry/) Jeff Barr introduces the preview of AWS Distro for OpenTelemetry. We are part of the Cloud Native Computing Foundation (CNCF)’s OpenTelemetry community, working to define an open standard for the collection of distributed traces and metrics. AWS Distro for OpenTelemetry is a secure and supported distribution of the APIs, libraries, agents, and collectors defined in the OpenTelemetry Specification.

![opentel](https://media.amazonwebservices.com/blog/2020/obs_map_4.png)

Jeff concludes that this is an open source project and welcome your pull requests! We will be tracking the upstream repository and plan to release a fresh version of the toolkit quarterly.

Following Jeff's post, Alolita Sharma and Nizar Tyrewalla followed up with [AWS Distro for OpenTelemetry now available for public preview](https://aws.amazon.com/blogs/opensource/aws-distro-for-opentelemetry-now-available-for-public-preview/) which provides some more details, the core components and how you can get started.
 
We also had follow on posts from AWS Partners who are integrating as back end providers for Open Distro for Telemetry. Partners such as:

* **Grafana** [AWS Distro for OpenTelemetry, Grafana, Prometheus, Loki, OpenMetrics, and beyond: How Open Standards continue to shape modern observability](https://grafana.com/blog/2020/10/21/grafana-modernizing-observability-with-aws-opentelemetry-openmetrics-and-beyond/)
* **New Relic** [New Relic, AWS, and OpenTelemetry: Cloud Observability, Simplified](https://blog.newrelic.com/product-news/aws-distro-for-opentelemetry/)
* **Splunk** [Splunk and AWS: Partnering to Accelerate Production-Ready OpenTelemetry](https://www.splunk.com/en_us/blog/devops/splunk-and-aws-partnering-to-accelerate-production-ready-opentelemetry.html)
* **AppDynamics** [What is OpenTelemetry and Why Should You Care?](https://www.appdynamics.com/blog/product/what-is-opentelemetry/)
* **Datadog** A[WS Distro for OpenTelemetry will send metrics and traces to Datadog](https://www.datadoghq.com/blog/aws-opentelemetry/)

### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to Brian Demers, Steve Roberts, Ahmed Bham, Marcelo Boeira, Annie Ku, Andrea Cavagna, Yann Hamon, Brian McCann, Jimmy Dahlqvist, Takuji Kawata, Tatsuya Arai, Alolita Sharma, Nizar Tyrewalla, Walkley He, Jiaxin Shan,  Henner Dierks, Anthony Antonuccio, Rob Hilton, Kevin Tuil, Kyle Galbraith, Reza Ramezanpour, Yegor Shytikov, Ken Winner, Lars Jacobsson, Justin Garrison, Lezgin Bakircioglu, Michael Redlich and Dhruvesh Patel.


Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

**aws-oidc**

[aws-oidc](https://github.com/chanzuckerberg/aws-oidc) is an open source command-line utility tool for generating temporary AWS STS credentials. The current project contains sample configurations and currently requires Okta as the identity provider. Annie Ku has put together a post to help you get started, in [Federated AWS Access](https://medium.com/czi-technology/federated-aws-access-e5705faca7db)

![arch](https://miro.medium.com/max/1400/1*hPZ6mh2GpGPPoBJdK_u_Zw.png)

Annie notes in a conversation over in LinkedIn that whilst this overlaps with AWS SSO, one of the key drivers for creating this project was the Terraform support they needed.

**leapp**

[leapp](https://github.com/Noovolari/leapp) Andrea Cavagna go in touch this week to talk with me about a new open source project that he is involved in that helps customers more easily connect with AWS EC2 instances via Session Manager. It provides a nice GUI that allows you to manage your various profiles and AWS accounts and then quickly access them via SSH. This project is still early days and Andrea is looking for more people to get involved, test the tool and provide feedback. You can also check out the project home page [here](https://www.leapp.cloud/).

**kube-secret-syncer**

[kube-secret-syncer](https://github.com/contentful-labs/kube-secret-syncer) is an open source project that provides a Kubernetes operator to sync secrets from AWS Secrets Manager. View the README to find out why this might work better for you if you are already using something like Kubernetes external Secrets or AWS secret operator. Yann Hamon over at Contentful has helpfully put together an intro post [Open-sourcing kube-secret-syncer: A Kubernetes operator to sync secrets from AWS Secrets Manager](https://www.contentful.com/blog/2020/10/20/open-source-kube-secret-syncer/) which you should also check out.

**determined-ai**

[determined](https://github.com/determined-ai/determined) is an open-source deep learning training platform that makes building models fast and easy. This project provides a CloudFormation template to bootstrap you into AWS and then has a number of tutorials covering how to manage your data, train and then deploy inference endpoints. If you are looking to explore more open source machine learning projects, then check this one out.

**booster**

[booster](https://github.com/boostercloud/booster) Booster is a high-level framework for TypeScript to build Serverless applications with built-in business-logic-level abstractions. Booster is highly opinionated and still under heavy development so be aware of that as you explore this project. I had a look a the [documentation](https://github.com/boostercloud/booster/tree/master/docs/), and it is very detailed and comprehensive. This could be a project to watch.

**Lambda-Extension-Secrets-Wrapper-Python**

[Lambda-Extension-Secrets-Wrapper-Python](https://github.com/JimmyDqv/Lambda-Extension-Secrets-Wrapper-Python) Jimmy Dahlqvist shares this open source project that read all parameters for an application and environment from Amazon Parameter Store and presents them as environment variables.

**AWS SDK for Javascript**

[aws-sdk-js-v3](https://github.com/aws/aws-sdk-js-v3) the AWS SDK for JavaScript v3 RC is a rewrite of V2 with some great new features. Read this post to find out more, [Modular AWS SDK for JavaScript – Release Candidate](https://aws.amazon.com/blogs/developer/modular-aws-sdk-for-javascript-release-candidate/).

**aws-robomaker-sample-application-meirorunner**

[aws-robomaker-sample-application-meirorunner](https://github.com/aws-samples/aws-robomaker-sample-application-meirorunner) this is a cool open source sample application that you can run on AWS RoboMaker and demonstrate reinforcement learning machine learning for robotics. The folks have also written a supporting blog post, [Escape from the maze by training a Reinforcement Learning model on AWS RoboMaker](https://aws.amazon.com/blogs/robotics/reinforcement-learning-robotics/) Takuji Kawata and Tatsuya Arai provide additional information to help you run this yourself. 

**aws-auto-cleanup**

[aws-auto-cleanup](https://github.com/servian/aws-auto-cleanup) an open source application from Servian to programmatically clean your AWS resources based on a whitelist and time to live (TTL) settings. Auto Cleanup is comprised of three modules, APP, API, and WEB. Click through to learn more and follow the steps to deploy the modules to your environment.

**cfn-diagram**

[cfn-diagram](https://github.com/mhlabs/cfn-diagram) how many times have you wished you could take your CloudFormation YAML or JSON and then visualise it? When this open source tool provides a CLI as well as integration into tools like VSCode that help visualise CloudFormation templates as draw.io diagrams. Very nice Lars Jacobsson and the MatHem tech team. There is also the experimental [cfn-diagram-ci](https://github.com/mhlabs/) which you can have a look at as well.

**axis-aws-rekognition**

[axis-aws-rekognition](https://github.com/dwtechnologies/axis-aws-rekognition) Lezgin Bakircioglu got in touch this week to tell me about this project and how they are integrating AI services such as AWS Rekognition into the Axis range of cameras in order to do OCR. He has put together this blog post, [Boosting the assembly process with AWS serverless & Axis camera](https://medium.com/daniel-wellington-tech-stories/boosting-the-assembly-process-with-aws-serverless-axis-camera-cc094b1543f4) to help you understand how this all fits together. This is still experimental, so get in touch with Lezgin if you think this is something you would like to contribute to. 


### AWS open source posts

**AWS CDK**

[AWS CDK User Study on safe CI/CD](https://8599119.hubspotpagebuilder.com/aws-cdk-cicd-study) Master's Student Henrique Melo Lima is joining the CDK team to investigate mechanisms for staying safe while deploying infrastructure via CI/CD. To make sure we are building the right things for you, our users, we are looking for guinea pigs volunteers who meet the following criteria:

* Are currently deploying, or have experience deploying, infrastructure-as-code via Continuous Deployment, preferably using CDK.
* Have a good sense of what they would need to feel safe pulling updates from the internet and deploying those right away, and are willing to spend time talking to Henrique about it.
* Are willing to participate in an evaluation session at the end of the project.

Check out the link above to read more about what sort of commitment this might mean and how to sign up.

**Metaflow**

[Getting started with the open source data science tool Metaflow on AWS](https://aws.amazon.com/blogs/opensource/getting-started-with-the-open-source-data-science-tool-metaflow-on-aws/) Rob Hilton explains how to use Metaflow and AWS to make data science pipelines not only portable to the cloud, but also seamlessly scalable and inspectable. Netflix open-sourced Metaflow, a tool to help simplify the life of data scientists and ensuring consistency and repeatability between their local and scaled experiments. Metaflow’s promise is allowing those oft-repeated and fragmented pieces of a machine-learning project to be streamlined and executed in a human-friendly way.

![model](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2020/10/02/robhilt_MetaFlow_f2.png)

**Kubernetes machine learning**

[Virtual GPU device plugin for inference workloads in Kubernetes](https://aws.amazon.com/blogs/opensource/virtual-gpu-device-plugin-for-inference-workload-in-kubernetes/) Walkley He and Jiaxin Shan introduce an open source solution to schedule virtual GPU resource on Amazon Elastic Kubernetes Service (Amazon EKS). Efficiently running machine learning inference workload on GPU with Kubernetes is not easy and this posts demonstrated a solution to use a Kubernetes device plugin and Nvidia MPS to run inference jobs on GPU, which can significantly improve the GPU resource utilisation and reduce cost. 

![diagram](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2020/09/25/guilihe-shjiaxin_GPU-Device_f1.png)

The post explores GPU device plugin to address how to set fractional number of GPU resource for each pod by implementing the Kubernetes device plugin and Nvidia MPS. This project has been open sourced on [GitHub](https://github.com/awslabs/aws-virtual-gpu-device-plugin).  

**Kubernetes**

Two Kubernetes related posts this week. First up, we have [Field Notes: Migrating a Self-managed Kubernetes Cluster on Amazon EC2 to Amazon EKS](https://aws.amazon.com/blogs/architecture/field-notes-migrating-a-self-managed-kubernetes-cluster-on-ec2-to-amazon-eks/) where Ahmed Bham and Marcelo Boeira share how to migrate your live-traffic serving self-hosted Kubernetes Cluster to Amazon EKS. AWS customers from startups to enterprises have been successfully running Kubernetes clusters on Amazon EC2 instances since 2015, well before Amazon Elastic Kubernetes Service (Amazon EKS), was launched in 2018. Since Amazon EKS is upstream Kubernetes compliant, you can migrate existing self-managed Kubernetes workloads to Amazon EKS, with multiple options to minimize or avoid service disruption.

![arch](https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2020/10/15/mydomain.com_-1024x694.png)

Following that, Justin Garrison's post [Introducing the AWS Load Balancer Controller](https://aws.amazon.com/blogs/containers/introducing-aws-load-balancer-controller/) talks about the AWS ALB ingress controller, something Kubernetes users have been using it in production for years to expose Kubernetes services in AWS. This post explores recently added new features. No spoilers, so check out the post and make sure you follow Justin on Twitter to keep up to date with everything container related on AWS.

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2020/10/15/image-72.png)

**.NET Core**

[Open sourcing the Porting Assistant for .NET](https://aws.amazon.com/blogs/opensource/open-sourcing-the-porting-assistant-for-net/) Steve Roberts announces the open sourcing of the tool we launched a few months ago, the Porting Assistant for .NET, a tool for analyzing the compatibility of .NET Framework applications and estimating the effort required to port them to .NET Core. Steve goes on to talk about what was open sourced during the original launch, the data sets used to determine compatibility and then share the new about open sourcing the source code and compatibility analysis components of the assistant.

There has never been a better time to explore using this tool and to start thinking about how you might use this to modernise your .NET applications. Read Steve's post to diver deeper into how we are working with the community and collaborating with them for future releases.

**HPC**

[Fire Dynamics Simulation CFD workflow using AWS ParallelCluster, Elastic Fabric Adapter, Amazon FSx for Lustre and NICE DCV](https://aws.amazon.com/blogs/compute/fire-dynamics-simulation-cfd-workflow-using-aws-parallelcluster-elastic-fabric-adapter-amazon-fsx-for-lustre-and-nice-dcv/) Kevin Tuil (winning this weeks longest blog title) takes a look at the open-source code: Fire Dynamics Simulation (FDS) developed by National Institute of Standards and Technology (NIST) which is a popular tool used when looking to model fires across many industries, from the design of new buildings, defining evacuation procedures for trains, planes and ships, and even the spread of wildfires.

AWS High Performance Computing (HPC) resources many of which are themselves open source, allow FDS users to scale up beyond a single workstation to hundreds of cores to achieve simulation times of hours rather than days or weeks. Kevin looks at the architecture and provides everything you need to reproduce this setup.

![arch](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2020/10/16/update-to-diagram-.png)

**AWS Amplify**

Have you checked out Amplify with Friends? Check out episode four, Shared Dev Environment and then flick through the back catalog. This video features Community Builders Michael Liendo and Horacio Herrera who regulars join Matt Auerbach and Shawn Wang.

{% youtube VNe89WXtHHw %}

### Deep Dive of the Week

**Linux Kernel**

[Colm MacCárthaigh](https://twitter.com/colmmacc) over on Twitter shared this [tweet](https://twitter.com/colmmacc/status/1318217139766005760?s=11):

>Do you maintain a user-space RNG, e.g. Cryptography libraries, JVMs, and other run-times? We started a thread on LKML about adding vmgenid support to Linux, so that cloning a VM clone can be notified to user-space. Influence your preferred mechanism!
>

You can check out the thread over at lkml.org [here](https://lkml.org/lkml/2020/10/16/629).

### Partner

**HashiCorp's Waypoint**

Unboxing Waypoint, a great session from the crew of Containers from the Couch (Eddie, Adam and Brent) where they introduce the new open source project from HashiCorp, Waypoint. I watched this and then kicked the tyres myself and loved it. I also ended up following a number of different paths to learn some new stuff around buildpacks and the tooling around that. If you only watch one thing today, then make sure it is this.

{% youtube IDTWgg1qD3Y %}

Following on from that is this blog post, [How to Deploy a Next.Js App to AWS ECS with HashiCorp Waypoint](https://blog.kylegalbraith.com/2020/10/20/how-to-deploy-a-nextjs-app-to-aws-ecs-with-hashicorp-waypoint/) from Kyle Galbraith will help you take your new found understanding of Waypoint and use it to deploy a sample application effortlessly to Amazon ECS.

### Case Studies and Industries

**Research**

[Managing compute environments for researchers with Service Workbench on AWS](https://aws.amazon.com/blogs/opensource/managing-compute-environments-for-researchers-with-service-workbench-on-aws/) I have talked about this solution before so it great to see Henner Dierks and Anthony Antonuccio dive deep and walk you through this open source project called Service Workbench on AWS. This project provides a web frontend that abstracts the complexity of the cloud away from end users (researchers) who want to focus on research work rather than understanding the cloud. Additionally, it helps improve collaboration and cost management, which are both essential in a research setting on a fixed budget and in cross-organisational projects.

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2020/10/15/hennerd_service-workbench_f1.png)

Service Workbench on AWS also makes research IT staff’s work easier as they can focus on creating templates for research workspace types rather than having to provision every single workspace in the environment.

### Latest blog posts

**Spring Boot on Lambda**

[Java Developers, It’s Time To Give AWS Lambda a Try](https://medium.com/@bmccann36/java-developers-its-time-to-give-aws-lambda-a-try-c265215603a1) Brian McCann kicks off the first in what promises to be a great series of posts on the topic of modernising applications and how you might approach this using the examples of well know java frameworks such as Spring Boot. If you are new to this space and are wondering how Java and java frameworks might fit into modern approaches such as serverless, then read Brian's post and catch his follow ups.

**Bottlerocket**

[EKS, Bottlerocket, and Calico eBPF](https://www.projectcalico.org/eks-bottlerocket-and-calico-ebpf/) Reza Ramezanpour gets you hands on with Bottlerocket and Amazon EKS as you deploy Calico eBPF. What is Calico eBPF? From the post:

> it allows you to write mini programs that can be attached to various low-level hooks in the Linux kernel, for a wide variety of uses including networking, security, and tracing.

**AWS Graviton2**

[AWS Graviton 2 ARM C6g is the Magento Cloud Killer instance](https://yegorshytikov.medium.com/aws-graviton-2-arm-c6g-magento-cloud-killer-instances-magento-2-php-fpm-performance-2aba9ab9b4f1) straight talking Yegor Shytikov is back with another benchmark post, this time looking at the performance of running Magento on different AWS instance types. I do not want to spoil the conclusion and you should read this post. Yet more evidence as to why the AWS Graviton2 instance types are really making an impact when it comes to optimising both cost and performance of your workloads.

[How to Utilize Java Benchmarks With Arm Processors](https://dzone.com/articles/how-to-utilize-java-benchmarks-with-arm-processors) Brian Demers shares the first benchmark study that I have seen that compares Amazon Corretto running the Phoronix Test suite against a number of AWS instance types. As always, I hate spoiling the surprise so dip into this post from Brian and read what he found out.

**Amazon Corretto**

[Heapothesys - an Open-Source GC Latency Benchmark by Amazon Corretto](https://www.infoq.com/news/2020/09/introducing-heapothesys/) I missed this post from Michael Redlich a few weeks ago, but in it Michael introduces for those who are unfamiliar what this open source project that the Amazon Corretto team released is, and then walks through an example. If you are looking to understand the behaviour of your java applications and want to model how it will behave under different gc (garbage collection) configurations, this post is for you.

![bench](https://res.infoq.com/news/2020/09/introducing-heapothesys/en/resources/1infoq-overlay-plot-1600966318873.png)

**Deep Java Library**

[DJL - Deep Java Library](https://dev.to/dhruvesh_patel/djl-deep-java-library-2o40) Dhruvesh Patel shares a quick post and walkthrough of how to use the Deep Java Library to do some object detection. Whilst many posts focus on Python when it comes to machine learning, Deep Java Library provides a rich set of capabilities to enable Java developers to deploy deep learning using a number of different frameworks.

![object](https://res.cloudinary.com/practicaldev/image/fetch/s--9n98Pyji--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/h4tvh26sqrtv00yha10o.JPG)

**AWS AppSync and projen**

[Using projen to deploy AWS AppSync with AWS CDK](https://kennethwinner.com/2020/10/23/projen-appsync-project/) Ken Winner shares a very brief post on how you can use projen, a tool I mentioned a few issues ago from Elad Ben-Israel, to scaffold out everything you need when setting up your projects. In this case Ken has created [cdk-appsync-project](https://github.com/kcwinner/cdk-appsync-project) to demonstrate how you would do this for a sample AWS AppSync application integrated with AWS Cognito. As Ken points out, projen helps you address some of the things that AWS CDK does not. This is a two minute read, so head over and check this out.

### Quick updates

**Active MQ**

You can now launch Apache ActiveMQ 5.15.13 brokers on Amazon MQ. This patch update to ActiveMQ contains several fixes and new features compared to the previously supported version, ActiveMQ 5.15.12. Amazon MQ is a managed message broker service for Apache ActiveMQ that makes it easy to set up and operate message brokers on Amazon Web Services (AWS). Message brokers allow different software systems, often using different programming languages, to communicate and exchange information. With Amazon MQ, you can use industry standard APIs and protocols for messaging, including JMS, NMS, AMQP, STOMP, MQTT, and WebSocket. You can easily move from any message broker that uses these standards to Amazon MQ because you don’t have to rewrite any messaging code in your applications.

**Apache Kafka**

Amazon Managed Streaming for Apache Kafka (Amazon MSK) now supports Apache Kafka version 2.6.0 for new and existing clusters. Apache Kafka 2.6.0 includes several bug fixes and new features that improve performance. Some key features include native APIs to manage client quotas (KIP-546) and explicit rebalance triggering to enable advanced consumer usecases (KIP-568). For a complete list of improvements and bug fixes, see the Apache Kafka release notes for 2.6.0.

**Infrastructure as Code**

If you go out into the (Berlin) woods today....you might bump into my colleague Darkos talking about everything that is to do with Infrastructure as Code. In this short video he covers Amazon CloudFormation, and mentions a number os useful open source tools to make your life much easier. Tools such as cfn-link, cfn-nag, taskcat, cfn-guard and there are many more.

{% youtube 8Zo_om-liTg %}


### Events for your diary

Check out these events this week.

**cdk8s**
**October 27, 2020, 11:00 AM (PT) | 2:00 PM (ET)**

The new CDK for Kubernetes (cdk8s) is an open-source project that lets you define Kubernetes applications and reusable components using familiar programming languages. In this tech talk, learn how csk8s works locally on your machine and generates standard Kubernetes YAML data, so you can use it with any Kubernetes cluster running anywhere, including on-premises and the cloud.

Sign up [here](https://pages.awscloud.com/AWS-Online-Tech-Talks_October-2020.html?webinar=2020_1020-CON).

**What’s New with Amazon ElastiCache for Redis**
**October 30, 2020, 9:00 AM (PT) | 12:00 PM (ET**

Amazon ElastiCache for Redis is a blazing fast in-memory data structure store. Customers use ElastiCache for Redis to accelerate and store data for all manner of distributed applications. In Redis 6.0, customers can make their Redis applications more secure by applying Resource Based Access Control (RBAC) to data structures and commands. Furthermore, customers can now use client-side caching to further improve performance. In this tech talk, we will explain and demonstrate these new capabilities.

Register [here](https://pages.awscloud.com/AWS-Online-Tech-Talks_October-2020.html?webinar=2020_1028-DAT)

And put these on your diary for November.

**Amazon Corretto**
**Reducing latencies with Micronaut and Amazon Corretto**
**OCTOBER 30, 2020 10:00 a.m. CDT**

When a millisecond delay can mean all the difference, the right tools are critical. Join 2GM (Groovy, Grails, and Micronaut) team member, Álvaro Sánchez-Mariscal, and Amazon Software Development Manager, Azeem Jiva, for a live tutorial demonstrating the most effective ways to reduce latencies with Micronaut and Amazon Corretto. 

Reserve your spot [here](https://objectcomputing.com/products/micronaut/resources/reduce-latencies-with-micronaut-and-amazon-corretto). 


**OpenShift on AWS**
**Nov 10, 2020 6:00 PM - 7:00 PM GMT**

Mayur Shetty will discuss the benefits of Red Hat OpenShift 4.5 and all the consumption options available to customers on AWS.

Register [here](https://register.gotowebinar.com/register/7154011299129383181?source=Socialhttps://attendee.gotowebinar.com/register/7154011299129383181?source=Social).

**AWS Container Day: Kubernetes Edition**
**November 17th, 10:00am to 6:00pm EST

Join us for AWS Container Day, a fully live, virtual day of sessions all about Amazon EKS and Kubernetes at AWS, hosted by Containers from the Couch. At this Day Zero KubeCon event, the AWS Kubernetes team will be discussing new launches, demoing products and features, covering best practices, and answering your question live on Twitch.

Register [here](https://awscontainerdayk8s.splashthat.com/#rsvp).

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen).

### Your feedback matters!

I have put together a short feedback survey, which I would ask you to take - it will take no more than 2 minutes. You can access [here](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn). Many thanks!

[Take the survey](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn)
26th