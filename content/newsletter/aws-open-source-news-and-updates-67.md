---
title: 'AWS open source news and updates #67'
date: '2021-05-10'
tags : [ oss-newsletter ]
---
## May 10th, 2021 - Instalment #67

Newsletter #67. 

This week more great open source projects for you to get stuck into. The big news last week was the release in alpha of the new Rust SDK for AWS, so make sure you check that out if you are exploring the world of Rust. We also have a couple of interesting new projects on awslabs, always a great place to explore if you have the time, awsclii a nice little tool that generates groovy ascii graphics as well as some significant updates to some projects I have covered in earlier newsletters. As always AWS and Community blog posts covering Apache Airflow, Apache Kafka, Pixie, Kubernetes, cdk8s and CDK and many more. If you missed out on AWS Container Day at Kubecon, check out the links to the sessions. To finish off we have the usual events and an interesting video on open source documentation.

Before you dive in, a few short notices you should read.

**Python 2.7 in AWS Chalice**

On July 15, 2021, AWS will publish a minor version update for AWS Chalice that will require Python 3.6 or greater, formally ending our support for Python 2.7. You can read more in the post from James Saryerwinnie,
[Announcing the end of support for Python 2.7 in AWS Chalice](https://aws-oss.beachgeek.co.uk/hd) which provides more details as well as some options for what you can do.

**Do you want to write a blog on the AWS open source blog?**

I am always looking our for new content that we can share with readers of the AWS open source blog, so if you have some great content you would love to share, please get in touch. It has been really good over the past year to see many builders share their open source stories/projects/knowledge, and we can help you through the process, so don't worry if you have never done this before.

**Give your project some love**

Check out [this tweet from David Boyne](https://aws-oss.beachgeek.co.uk/gz) if you have an open source project that you might want to benefit from this tool David is developing. From the short video, it looks really nice and one of the best ways to help raise awareness and get interest in your project is having clear documentation. This could be a great way to help with that.

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: iliana etaoin, Jesse Butler, Matt Hansen, David Boyne, Jilles van Gurp, Matthew Lau, Heitor Lessa, Joshua McKiddy, Valter Silva, Brent Langston, Adam Keller, Stéphane Maarek, Manabu McCloskey, Nima Kaviani, Rob Hilton, Jeremy Schiefer, Fabio Nonato de Paula, Mahadevan Balasubramaniam, James Saryerwinnie, Colin Bookman, Mark Carter, Srihari Prabaharan, Rucha Deshpande, Jason Nichols, Ron Xing, Yudho Ahmad Diponegoro, Dirk Boekee, Matt Coulter, Anna Geller, Vu Dao and Nočnica Fee.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

**aws-sdk-rust**

[aws-sdk-rust](https://aws-oss.beachgeek.co.uk/hs) last week we released the alpha of the new AWS SDK for Rust developers. During the alpha, you can install the SDK via a Git dependency and this will be published to crates.io when the SDK is Generally Available. You can read more about this from the launch blog post from iliana etaoin, [A New AWS SDK for Rust – Alpha Launch](https://aws-oss.beachgeek.co.uk/ht)

**awscii-cli**

[awscii-cli](https://aws-oss.beachgeek.co.uk/h5) folks that know me understand how much I love retro/ascii art/graphics, so when I saw the latest project from the lovely folks at the MatHem tech team I got super excited. This is an open source tool that renders ASCII-art graphs from AWS resource metrics. The purpose of this tool is to give cloud engineers instant access to their resources' graphs without context switching into the AWS console. Check out this little animated gif demo to see more, then head over and check out the project.

![demo](https://raw.githubusercontent.com/mhlabs/awscii-cli/main/images/demo.gif)

**node-go-live**

[node-go-live](https://aws-oss.beachgeek.co.uk/hu) the folks at Eyevinn Technology released this node package that provides the functionality to build an API layer on top of AWS Media Services to automate and simplify setting up a media pipeline for live using RTMP as the video signal contribution protocol. If you work with AWS Media Services, this is going to come in real handy.

**aws-auto-inventory**

[aws-auto-inventory](https://aws-oss.beachgeek.co.uk/h6) this very handy new tool, AWS Auto Inventory, allows you to quickly and easily generate inventory reports of your AWS resources. Check out the repo to take a look at what those reports look like and how configurable this tool is. I think a lot of folks are going to find this tool very useful.

![demo](https://github.com/aws-samples/aws-auto-inventory/blob/master/clencli/terminalizer/run.gif?raw=true)

**assisted-log-enabler-for-aws**

[assisted-log-enabler-for-aws](https://aws-oss.beachgeek.co.uk/h7) this is an interesting tool that is for customers who do not have logging turned on for various services, and lack knowledge of best practices and/or how to turn them on. Check out the README to find out more details as to which AWS service logs it can enable, and more about the typical use cases where this might be useful.

![arch](https://github.com/awslabs/assisted-log-enabler-for-aws/blob/main/diagrams/assisted_log_enabler.png?raw=true)

**aws-react-elasticsearch-terraform**

[aws-react-elasticsearch-terraform](https://aws-oss.beachgeek.co.uk/h3) The right to study/modify/use that open source gives you is what this project is all about, and is a complete sample project/architecture from Matthew Lau that uses a number of open source technologies to build a sample todo application that is perhaps a little over-engineered but you can re-purpose potentially for your own needs. It uses Terraform to deploy, and this is on my todo list for the weekend..see what I did there :-)

![arch](https://github.com/MatthewCYLau/aws-react-elasticsearch-terraform/blob/master/img/aws-elasticsearch.JPG?raw=true)

Also, if you are a fan of Terraform then you should check out AWS Hero Anton Babenko's weekly Terraform newsletter which you can [sign up for here](https://aws-oss.beachgeek.co.uk/hq). The [latest edition, #40](https://aws-oss.beachgeek.co.uk/hr) is jam packed with great Terrform resources and whilst not all the content covers AWS, there is plenty of relevant AWS content on a regular basis.

**tool-compare**
* [tool-compare](https://github.com/iacsecurity/tool-compare) a nice simple tool helps you compare various infrastructure as code (IaC) open source security tools. This allows you to see what the tool can do, and how it compares, before even installing it. Currently supporting Checkov, Indeni Cloudrail,Kics,	Snyk, Terrascan and Tfsec.

**AWSsert**

[AWSsert](https://aws-oss.beachgeek.co.uk/hv) this Python library popped up on my radar over the weekend, and is a library providing declarative assertions about AWS resources to your tests. Installing the package will make AWSserts extra assertions available to all of your tests. Assertions are attached directly to boto3 resource objects, allowing you to write clean and declarative tests. Whilst only a subset of AWS Services is currently supported, one to watch.

**other open source project updates**

* [es-kotlin-client](https://aws-oss.beachgeek.co.uk/h0) - es-kotlin-client is an open source tool from Jilles van Gurp that provides a friendly Kotlin API on top of the official Elastic Java client, that adds kotlin DSLs, support for co-routines, and more to the official Java client.

* [aws-graviton-getting-started](https://aws-oss.beachgeek.co.uk/h1) - updated last week, this project  helps new users start using the Arm-based AWS Graviton and Graviton2 processors and has been updated to include .NET/.NET Core 

* [aws-lambda-powertools-python](https://aws-oss.beachgeek.co.uk/h4) big release last week from one of the most loved projects that I know about, Lambda powertools. This release has three major goodies: 1/ Idempotency utility is now GA, 2/ New API Gateway and ALB event handler, and 3/ MANY enhancements to Logger. As AWS Community Builder Luc van Donkersgoed tweeted last week "Check out this new feature in Lambda Powertools for Python: fully managed event handling for ALB, REST and HTTP API Gateways. Just decorate your handler function with a route and boom, it works."

Finally, if you are a Terraform user and interested in using that to automate Amazon Lightsail deployments, then [check out this thread](https://aws-oss.beachgeek.co.uk/h2) and think about supporting (up voting) some of these. 

### Community open source posts

**Magpie**

[Magpie](https://aws-oss.beachgeek.co.uk/hg) is a free, open-source framework and a collection of community developed plugins that can be used to build complete end-to-end security tools such as a Cloud Security Posture Manager (CSPM). In this blog post, [Magpie RFC - Security Rules and Policies](https://aws-oss.beachgeek.co.uk/hf) Jason Nichols describes the planned approach for how the open source Magpie framework will also be able to apply policies against the persisted discovery data from discovered information of your AWS resources that are persisted. To find out more about this project, check out their other blog posts including the origin story [here](https://aws-oss.beachgeek.co.uk/hh).

**Apache Airflow**

[How I Built CI/CD For Data Pipelines in Apache Airflow on AWS](https://aws-oss.beachgeek.co.uk/hm) one of my favourite posts this week, Anna Geller puts together this detailed walkthrough of how you can create a CI/CD pipeline for your Apache Airflow environment, using Buddy as your CI/CD tool. Really nice.

**AWS CDK**

With CDK Day still fresh in my mind, it was amazing to see Matt Coulter put together this post, [CDK Day In Review](https://aws-oss.beachgeek.co.uk/hn). Consider this your essential companion when revisiting or checking out for the first time the sessions that ran over the two tracks. Great stuff.

**CDK8s**

On a related note, Vu Dao put together this post, [CDK8S Example](https://aws-oss.beachgeek.co.uk/ho), that uses the CDK8s tool to generate Kubernetes YAML from code you write to describe your application using the same constructs approach that you will be familiar with in AWS CDK. This is a great primer into how this works, walking you through a sample application.

### AWS open source posts

**Pixie**

[Gathering insights on Kubernetes applications, services, and network traffic with Pixie](https://aws-oss.beachgeek.co.uk/he) Colin Bookman and Mark Carter share a great post on Pixie, an Extended Berkeley Packet Filter (eBPF) powered, open source, observability platform for Kubernetes that makes observability easily accessible to developers. The post provides more info on Pixie, how AWS is partnering with New Relic to contribute to this project and the announcement last week of AWS joining Pixies board to collaborate with New Relic on this open source project. The post provides some great links to getting started and tutorials so you should be able to try this out for yourself very quickly indeed.

![pixie](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/04/28/bookman_f1_1000.png)

You can also check out the post from Nočnica Fee at New Relic over on dev.to, [Pixie is now open source](https://aws-oss.beachgeek.co.uk/hp)

**Open Policy Agent**

[Open Policy Agent](https://aws-oss.beachgeek.co.uk/hj) (OPA) is an open source, general-purpose policy engine, which decouples policy decision-making from policy enforcement, which allows you to release, analyse, and review policies (which security and compliance teams love) without sacrificing availability or performance. In this post, [Creating a custom Lambda authorizer using Open Policy Agent](https://aws-oss.beachgeek.co.uk/hi) Srihari Prabaharan and Rucha Deshpande demonstrate how you can create a custom Lambda authoriser to offload authorisation decisions by leveraging the OPA policy engine, showing how authorisation can be as straightforward as passing request headers to OPA to return a decision.

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/04/28/srihap_custom_lambda_f1_500.png)

**TiDB**

[Achieve Better Price to Performance for TiDB on Amazon EKS with Graviton2 Processors](https://aws-oss.beachgeek.co.uk/hk) Ron Xing from PingCAP, and Yudho Ahmad Diponegoro from AWS collaborate on a post that combines two of my favourite things: open source technology and AWS Graviton2 processors. In this post you will hear how TiDB benchmarking was undertaken using a number of different benchmarks to provide a much better price/performance result. I always recommend that customers look to use these kinds of posts as helpful illustrations only and that you should look to benchmark your own workloads, leveraging the how-to and other nuggets provided to help you with that effort.

![benchmark](https://d2908q01vomqb2.cloudfront.net/cb4e5208b4cd87268b208e49452ed6e89a68e0b8/2021/05/05/Pingcap-TIDB-Cluster-on-EKS-1.png)

**Spinnaker Keel**

[How to deploy Spinnaker Keel on Amazon EKS](https://aws-oss.beachgeek.co.uk/ha) Manabu McCloskey, Nima Kaviani, and Rob Hilton look at the process of deploying Spinnaker core micro services and Keel to a Kubernetes cluster and then deploying a sample Kubernetes application using Keel. Spinnaker is a continuous delivery platform for releasing software changes rapidly and reliably that was open sourced by Netflix, and Keel is an optional micro service of Spinnaker that enables the GitOps experience. To find out more, read on...

**PyTorch**

[Achieve 12x higher throughput and lowest latency for PyTorch Natural Language Processing applications out-of-the-box on AWS Inferentia](https://aws-oss.beachgeek.co.uk/hb) winner of this weeks longest blog post title, we have Fabio Nonato de Paula and Mahadevan Balasubramaniam who show you how to optimise running a NLP-based solution using HuggingFace Transformers pretrained BERT base models, with no modifications to the model and one-line code change at the PyTorch framework level that achieves 12 times higher throughput at 70% lower cost. This is done using AWS Inferentia instance types, leveraging the open source [Neuron SDK's](https://aws-oss.beachgeek.co.uk/hc) capabilities for PyTorch.

![graph](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2021/04/29/topPicture.png)

**ROS**

[AWS RoboMaker now supports ROS2 Foxy Fitzroy featuring Navigation2](https://aws-oss.beachgeek.co.uk/gu) Matt Hansen provides an update on the latest ROS2 release,  Foxy Fitzroy, and how you can now use this when using AWS RoboMaker. In this post, Matt takes a look at Navigation2 (Nav2) which is the second generation of the ROS Navigation software stack, enabling robots to move autonomously from point A to B. He covers the main features and architecture as well as getting you started with Nav2 in AWS RoboMaker. 

![arch](https://d2908q01vomqb2.cloudfront.net/a9334987ece78b6fe8bf130ef00b74847c1d3da6/2021/05/03/figure-d.png)

**Kubernetes**

[Planning Kubernetes Upgrades with Amazon EKS](https://aws-oss.beachgeek.co.uk/gv) Jesse Butler kicks off what will be a new series of blog posts on the Containers blog covering new features as well as calling out specific changes that you should make note of when planning your cluster upgrades. Jesse kicks this series off with this post taking a look at Kubernetes version 1.19, and shares a broader perspective on versions and observations of running this version of Kubernetes. If you do containers, this is a must read this week.

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2021/05/01/EKS-Lifecycle-Management.png)

**SimpleSAMLphp**

[Enabling Federation with SimpleSAMLphp and Amazon AppStream 2.0](https://aws-oss.beachgeek.co.uk/h9) Jeremy Schiefer writes about an old favourite project of mine that I have used many times in the past, SimpleSAMLphp. This is an open-source project written in native PHP that deals with authentication for SAML 2.0 as a Service Provider and as an Identity Provider. In this post, Jeremy explains how to configure federated user access for Amazon AppStream 2.0 for customers already using SimpleSAMLphp.

**SRT**

Secure Reliable Transport (SRT) is an open source video transport protocol that optimises video streaming performance, and in this post, [Getting started with SRT inputs in AWS Elemental Live](https://aws-oss.beachgeek.co.uk/hl), Dirk Boekee dives deeper into SRT and then shows you how you can integrate this with AWS Elemental Live.

![arch](https://d2908q01vomqb2.cloudfront.net/fb644351560d8296fe6da332236b1f8d61b2828a/2021/05/05/Picture1-1.png)

**Apache Kafka**

[Securing Apache Kafka is easy and familiar with IAM Access Control for Amazon MSK](https://aws-oss.beachgeek.co.uk/h8) this guest post from AWS Data Hero Stéphane Maarek takes a look at how easy it is to secure an Amazon MSK cluster and Apache Kafka with IAM Access Control, showing you how to configure access from your developer tooling. 

![arch](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2021/05/06/bdb1447-access-control-msk-1.jpg) 

### Quick updates

**Prometheus**

If you missed this last week, then this will be good news as we announced reducing the price of metric samples ingested by up to 84% for Amazon Managed Service for Prometheus (AMP). Amazon Managed Service for Prometheus (AMP) is a fully managed Prometheus-compatible monitoring service that makes it easy to monitor containerised applications at scale. With AMP, you can use the open source Prometheus Query Language (PromQL) to monitor the performance of containerised workloads on AWS or on-premises. AMP automatically scales the ingestion, storage, and querying of operational metrics (from, for example, your Amazon Kubernetes Service (Amazon EKS) clusters) as workloads grow or shrink, and is integrated with AWS security services such as AWS Identity and Access Management (IAM), AWS PrivateLink, and AWS CloudTrail to enable fast and secure access to data.

Find out more by reading the post, [AWS announces a price reduction for Amazon Managed Service for Prometheus (AMP)](https://aws-oss.beachgeek.co.uk/gx)

**Elasticsearch**

Amazon Elasticsearch Service now offers instances from the AWS Graviton2 instance family. Instance types include general purpose (M6g), compute optimized (C6g), and memory optimized (R6g, R6gd). Customers can enjoy up to 38% improvement in indexing throughput, 50% reduction in indexing latency, and 30% improvement in query performance when compared to the corresponding x86-based instances from the current generation (M5, C5, R5). 

Amazon Elasticsearch Service Graviton2 instances support Elasticsearch version 7.9 and above. The instances also include support for all recently launched features like encryption at rest and in-flight, role-based access control, cross-cluster search, Auto-Tune, Trace Analytics, Kibana Reporting, and UltraWarm.

Amazon Elasticsearch Service Graviton2 instances provide up to 44% price/performance improvement over previous generation instances. Further savings are available via reserved instance (RI) pricing for these instances.

**Porting Assistant for .NET**

In case you missed this last week, Porting Assistant for .NET is now available as a Visual Studio IDE extension. With this release, developers can access Porting Assistant for .NET directly from the Visual Studio IDE to assess incompatibilities and be more productive with an integrated experience for porting their .NET applications. Along with rich source code editing features provided by the IDE, this extension provides developers with feedback on lines of code that need to be modified to make the source code compatible with .NET Core. Developers can now run automated porting and take advantage of continuous assessment of incompatibilities as they make updates to the code.

Porting Assistant for .NET is an open source analysis tool that scans .NET Framework applications and generates a .NET Core or .NET 5 compatibility assessment, helping you port your applications to Linux faster. Porting .NET Framework applications to .NET Core or .NET 5 helps customers take advantage of the performance, cost savings, and the robust Linux ecosystem.

The new Porting Assistant for .NET extension is available for download through the Visual Studio marketplace [here](https://aws-oss.beachgeek.co.uk/gw).

**FreeRTOS**

FreeRTOS version 202104.00 includes a new managed over-the-air update (OTA) library, coreMQTT-Agent library and the AWS IoT Device Defender custom metrics feature as generally available. Developers can use these libraries to update firmware, manage IoT device fleets, design multi-threaded applications, and monitor fleet metrics for their IoT devices.

The OTA library makes it easier to download and perform cryptographic verification of firmware updates. You can use the OTA library with your preferred MQTT library, HTTP library, and underlying operating system (e.g. FreeRTOS, Linux). The coreMQTT-Agent library manages the MQTT connection by serializing the access to the coreMQTT library and reducing implementation overhead (e.g., the need for repeated calls to the process loop from the application). This allows your multi-threaded applications to share the same MQTT connection, and enables you to design an embedded application without having to worry about thread safety. See coreMQTT-Agent demo that uses OTA, Device Shadow, and Device Defender in multiple threads. The Device Defender library enables you to send device metrics to the AWS IoT Device Defender service. This library also supports custom metrics, a feature that helps you monitor operational health metrics that are unique to your fleet or use case. For example, you can define a new metric to monitor the memory usage or CPU load on your devices. These libraries have been optimized for modularity and memory usage for constrained microcontrollers, and have undergone code quality checks (e.g. MISRA-C compliance, Coverity static analysis), and memory safety validation with the C Bounded Model Checker (CBMC) automated reasoning tool.

You can read more in the announcement, [FreeRTOS 202104.00 includes new managed OTA and MQTT capabilities for IoT applications](https://aws-oss.beachgeek.co.uk/gy)

### AWS Container Day at KubeCon

If you missed it last week, then don't worry. You can now sit back and take in over the next eight hours all the content you need about Amazon EKS and Kubernetes at AWS, hosted by Brent Langston and Adam Keller of Containers from the Couch

{% youtube MZ-4HzOC_ac %}

### Video of the week

**Benefits of Open-sourcing Content with Andrew Etter of Amazon Web Services**

Andrew Etter, the Senior Technical Writer at Amazon Web Services, shares his journey in the field of technical writing in this video, looking at the documentation process at Amazon Web Services and how it is necessary to make the content accessible to users.

{% youtube pcz6qGrLrn4 %}

### Events for your diary

**Building And Maintaining Your Own Secure Container OS**
**May 13th 9am PST**

Curtis Rissi, a Principal Partner SA at AWS will walk attendees through the Bottlerocket (an open-source Linux-based operating system meant for hosting containers) build process, and provide some key use cases for customisation: how to add new configuration options; how to add new packages; how to configure your own update repositories; how to add security policy; and other common customisations. 

**ROS 2 Industrial Training (Europe)**
**May 18th - 21st**

If you were looking to increase your knowledge of open source robotics, then this training event might be of interest. Being held over 4 days, this is an industry focused event, that teaches the basics of ROS 2
and how to use ROS 2 for manipulation and for navigation. The class is completed by a session of best
practices, with the goal of the training is to get you started in developing with ROS.

**Mobile and Front-End Live**
**May 25th, 9:00 - 15:00 PDT**

This is a LIVE streamed event on Twitch  focused on accelerating full-stack mobile and web development. Learn about AWS Amplify, a set of purpose-built tools and services for front-end web and mobile developers that simplify app development. Deep dive into GraphQL and AWS AppSync, a fully-managed GraphQL service that improves app performance and developer productivity.

You can read more about what you can expect in the blog post.


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen).