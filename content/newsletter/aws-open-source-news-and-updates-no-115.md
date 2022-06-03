---

title: 'AWS open source news and updates #115'
date: '2022-06-03'
tags : [ oss-newsletter, aws open source, Kubernetes, Amazon EMR, Apache Kylin, Blazor, SUSE Linux, Dart, AWS Amplify, Amazon Genomics CLI, AWS CDK, Go, TensorFlow, Hugging Face, Apache Cassandra, Dicoogle, MariaDB, Spack, Ubuntu, Quarkus, Realm, OpenZFS]

---

## June 3rd, 2022 - Instalment #115

Welcome to regular and new readers alike, to the AWS open source newsletter episode #115.

This week we have another great selection of brand new open source projects for you to explore, including "firec" a Rust client library for interacting with Firecracker, "sfn-cli" a tool that helps you quickly build StepFunctions definitions, "ssm-cloner" a tool to help you replicate across AWS regions your AWS System Manager documents, "amazon-lambda-compute-tuning" an AWS Lambda function benchmarking tool, "aws-iam-root-user-activity-monitor" a sample project to help you keep track of your root user, "hpc-cost-simulator" a tool to help estimate costs running your HPC workloads on AWS, and many more.

We also have blog posts and longer form technical articles covering Kubernetes, Amazon EMR, SUSE Linux, Dart, AWS Amplify, Amazon Genomics CLI, OpenZFS, AWS CDK, Go, TensorFlow, Hugging Face, Apache Cassandra, Dicoogle, MariaDB, Spack, Quarkus (don't miss this one), and more this week. This weeks featured videos cover Apache Kylin and  Blazor and I finish up events happening that you should watch out for.


**AWS CDK**

The AWS Cloud Development Kit (AWS CDK) version 1 (v1) for JavaScript, TypeScript, Java, Python, .NET and Go is now in maintenance mode. In this post, [Version 1 of the AWS Cloud Development Kit (AWS CDK) is now in maintenance mode](https://aws-oss.beachgeek.co.uk/1qz) you find out more about what this means as well as learn resources on how you can begin your migration to v2.

**MariaDB**

If you are looking to upgrade your MariaDB database from 10.2 (which is End of Life, October 2022) then you should check out this post, [Upgrading from Amazon RDS for MariaDB version 10.2](https://aws-oss.beachgeek.co.uk/1r9) put together by Vijay Karumajji. In it he covers the Amazon RDS for MariaDB 10.2 end-of-life timeline, your available upgrade choices and then shares some current good practices to follow during the upgrade process.

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created. 

So thank you to the following open source heroes: Robert Oberhofer, Hamzabouissi Bazmahou, Forrest Sun, Gena Gizzi, Noor Fairoza, Michael Raney, Noah Gift, Gary Stafford, Oliver Perks, Vijay Karumajji, Daniel Leu, Ben Smith and Lars Jacobsson.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution.*

#### Tools

**firec**

[firec](https://aws-oss.beachgeek.co.uk/1rf) (pronounced "fyrek") is an open source Rust client library to interact with Firecracker. It allows you to create, manipulate, query and stop VMMs. Very nice indeed.

**sfn-cli**

[sfn-cli](https://aws-oss.beachgeek.co.uk/1qu) the latest open source project from the lovely folk at MatHem lets you quickly build StepFunctions definitions with a handy SDK integration lookup and snippet generation of all 10K+ API actions. A bit like a dressed down Workflow Studio, but at your fingertips. **Note** that this is an early stage preview and some functionality will be missing. (A big thanks to AWS Community Builder Lars Jacobsson for sending this through)

**ssm-cloner**

[ssm-cloner](https://aws-oss.beachgeek.co.uk/1rj) this repository is used to simplify the process of cloning the SSM documents across the AWS regions. You can use this module and pass on the parameters and it will clone the documents for you. You can also use it to unclone or create new version for your documents. Sound super useful.

**function-stencil**

[function-stencil](https://aws-oss.beachgeek.co.uk/1re) very nice tool from our own Ben Smith that is a quickstart AWS Lambda function code generator. Downloads a template function code file, test harness file, sample SAM definition and appropriate file structure. Check it out on npm too, [function-stencil](https://aws-oss.beachgeek.co.uk/1rg) 

**fissaa**

[fissaa](https://aws-oss.beachgeek.co.uk/1ri) is a CLI that Hamzabouissi Bazmahou created to help him simplify the deployment of applications to AWS ECS, including things like setting-up domain registration, TLS Certification, Load Balancing, Rolling Back and budget monitoring. I love it when there is a story or meaning behind a project name, and in this case Fissaa is a Tunisian word that means speed-up.

**amazon-braket-strawberryfields-plugin-python**

[amazon-braket-strawberryfields-plugin-python](https://aws-oss.beachgeek.co.uk/1rm) This plugin provides a BraketEngine class for running photonic quantum circuits created in Strawberry Fields on the Amazon Braket service. The Amazon Braket Python SDK is an open source library that provides a framework to interact with quantum computing hardware devices and simulators through Amazon Braket. Strawberry Fields is an open source library for writing and running programs for photonic quantum computers.

**amazon-lambda-compute-tuning**

[amazon-lambda-compute-tuning](https://aws-oss.beachgeek.co.uk/1rq) when trying to optimise your AWS Lambda functions, many people use my colleague Alex Casalboni's project, [AWS Lambda Power Tuning](https://aws-oss.beachgeek.co.uk/1rp). This project takes a slightly different slant, allowing you to try and benchmark the cost and performance differences against x86 and Arm and different memory options. All you need to do is supply the arn's of your AWS Lambda functions in the AWS Amplify front end, and away you go.

![demo of amplify power tuning app](https://github.com/aws-samples/amazon-lambda-compute-tuning/blob/main/screens/tuningFormInputWithResults.png?raw=true)

**aws-iam-root-user-activity-monitor**

[aws-iam-root-user-activity-monitor](https://aws-oss.beachgeek.co.uk/1ro) this project contains a sample of how you can monitor root user activity within your AWS accounts, using Terraform. This implementation is event-driven and relies on Amazon EventBridge to communicate AWS IAM root user activity events from member accounts to a central EventBridge custom event bus deployed in a given account.

![architecture of root user monitoring](https://github.com/aws-samples/aws-iam-root-user-activity-monitor/blob/main/RootActivityMonitor.png?raw=true)

**aws-tf-kms**

[aws-tf-kms](https://aws-oss.beachgeek.co.uk/1rt) this repo contains a set of Terraform modules and examples. It provisions AWS KMS keys that are usable for the supported AWS services. Optionally, it supports managing key resource policy for cross-account access by AWS services and principals. An additional module is included that supports creating multi-region replica keys in another region.

![architecture of aws-tf-kms](https://github.com/aws-samples/aws-tf-kms/blob/main/images/aws-tf-kms-Scenario-3.png?raw=true)

**hpc-cost-simulator**

[hpc-cost-simulator](https://aws-oss.beachgeek.co.uk/1ru) This package contains scripts to parse scheduler logs and analyze them. It analyzes scheduler accounting log files to simulate the cost of running the same jobs on AWS. This tool can simulate the use of spot instances for short jobs and help guide the choice of savings plans by breaking the data to hourly consumption. Initially supports LSF and Slurm. Altair Accelerator support to be added soon.

### Demos, Samples and Workshops

**dotnet-nativeaot-labs**

[dotnet-nativeaot-labs](https://aws-oss.beachgeek.co.uk/1rk) this repo provides a place to learn about and experiment with .NET NativeAOT on AWS. At a high level, NativeAOT for .NET is a way to compile your .NET projects directly to machine code, eliminating the Intermediate Language and Just-In-Time compilation. AOT stands for "Ahead of Time", as opposed to "Just in Time". According to this [tweet](https://aws-oss.beachgeek.co.uk/1rl) from Norm Johanson "We have been experimenting with .NET's preview AOT support for improving Lambda cold start. For some scenarios we are seeing big improvements.". 

**aws-vpc-builder-cdk**

[aws-vpc-builder-cdk](https://aws-oss.beachgeek.co.uk/1rn) this repo contains code that provide a simple and repeatable way to deploy and explore complex networking architectures on AWS, as well as helping to showcase the capabilities of the AWS Cloud Development Kit (CDK) to create and orchestrate a complex architecture.

![architecture of networking via cdk](https://raw.githubusercontent.com/aws-samples/aws-vpc-builder-cdk/main/images/index-1024x523.png)

**nodeblog.app**

[nodeblog.app](https://aws-oss.beachgeek.co.uk/1rh) Daniel Leu has created this sample project that puts together a number of AWS services using AWS CDK, to create a functional blogging app which you can use as a base for your own projects.

**deploying-unreal-engine-pixel-streaming-server-on-ec2**

[deploying-unreal-engine-pixel-streaming-server-on-ec2](https://aws-oss.beachgeek.co.uk/1r5) this repo contains code and documentation that allows you to deploy Windows-based Unreal Engine 4 Pixel Streaming builds to EC2. You can check out this blog post, [Unreal Engine Pixel Streaming in AWS with Ubuntu OS](https://aws-oss.beachgeek.co.uk/1r6) where Gena Gizzi and Noor Fairoza show you how you can get this project running on Ubuntu. This project looks fun to try out, so its on my weekend to do list. [hands on]

**rekognition-streaming-video-events**

[rekognition-streaming-video-events](https://aws-oss.beachgeek.co.uk/1rr) this project detects objects (people, pets, and packages) in live video streams and returns the detected label(s), bounding box coordinates, zoomed-in images of the object(s) detected, and timestamps.

![architecture of rekognition streaming events.](https://raw.githubusercontent.com/aws-samples/rekognition-streaming-video-events/main/img/sve_architecture.jpg)

**localize-content-using-aws-ml-services**

[localize-content-using-aws-ml-services](https://aws-oss.beachgeek.co.uk/1rs) This sample solution demonstrates how builders can use polly to generate audio different than the source audio, generate subtitles from a text file, generate speech marks and tie them all together.

![architecture of solution](https://github.com/aws-samples/localize-content-using-aws-ml-services/blob/main/img/polly-blog.png?raw=true)

### AWS and Community blog posts

**Realm**

Realm database is an open-source, developer-friendly project for mobile data storage, distributed under the Apache 2.0 license and backed by MongoDB. Robert Oberhofer has put together this post, [Increase app responsiveness with MongoDB Realm mobile database and AWS Wavelength](https://aws-oss.beachgeek.co.uk/1rv) introduces MongoDB Realm, and examines its core characteristics and key benefits. While Realm is widely used for building mobile applications, its capabilities are also relevant for other problem spaces, including IoT and Edge.

**Quarkus**

Another cracking post from Gary Stafford, this time showing you how go develop, test, build, and then deploy Native Quarkus applications to Kubernetes on AWS using GitOps in his post, [Building and Deploying Cloud-Native Quarkus Applications to Kubernetes](https://aws-oss.beachgeek.co.uk/1rc). This post covers more than Quarkus, and is essential reading for anyone looking to understand more about your options cloud native and Java. It is a long read, so grab your favourite beverage and enjoy!

![architecture of what you will build.](https://miro.medium.com/max/1400/1*dskKmb_gGLkAhMDg4rwZ4g.png)

**Spack**

[Spack](https://aws-oss.beachgeek.co.uk/1ra) is a multi-platform package manager that builds and installs multiple versions and configurations of software. It works on Linux, macOS, and many supercomputers. In the post 
[Introducing the Spack Rolling Binary Cache hosted on AWS](https://aws-oss.beachgeek.co.uk/1rb) Oliver Perks shares the announcement of a new public Spack Binary Cache, hosted on AWS. Spack users now have access to a public build cache hosted on Amazon Simple Storage Service (Amazon S3). The use of this Binary Cache will result in up to 20x faster install times for common Spack packages. Read this post to find out more, including how this works with other open source tools such as AWS ParallelCluster.

![diagram of Spack ecosystem](https://d2908q01vomqb2.cloudfront.net/e6c3dd630428fd54834172b8fd2735fed9416da4/2022/05/31/hpcblog-130-fig1v2.png)

**Dicoogle**

Dicoogle is an open source project that provides the functionality of a PACS (picture archiving and communication system). A PACS stores and indexes DICOM medical image files, and uses the DICOM protocol to facilitate the upload, download, and search of DICOM studies. DICOM is a data model organised in the sequence Patient – Study – Series – Instance. A patient has one or more studies, which may also be known as exams or procedures. In this post, [Running Dicoogle, an open source PACS solution, on AWS (part 1)](https://aws-oss.beachgeek.co.uk/1r8), Forrest Sun provides the first part of a two-part series that describes how to host a secure DICOM server on AWS. [hands on]

![architecture of dicom on aws](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2022/05/23/DicooglePartOne10.png)

**Apache Cassandra**

Lightweight transactions (LWT) is an Apache Cassandra API feature that allows developers to perform conditional update operations against their table data. Conditional update operations are useful when inserting, updating and deleting records based on conditions that evaluate the current state. Michael Raney has written [Improved performance for lightweight transactions with Amazon Keyspaces](https://aws-oss.beachgeek.co.uk/1r7) where he shares details about the improved performance characteristics of Amazon Keyspaces LWT API (lightweight transactions), advanced design patterns, and operational best practices.

![graph of Apache Cassandra](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2022/05/24/DBBLOG-2036-image001.jpg)


**Other posts you might like from the past week**

* [Making your Go workloads up to 20% faster with Go 1.18 and AWS Graviton](https://aws-oss.beachgeek.co.uk/1r0) shows how moving to the latest Go version can make a difference in performance when using Arm based AWS Graviton instance types
* [Run text classification with Amazon SageMaker JumpStart using TensorFlow Hub and Hugging Face models](https://aws-oss.beachgeek.co.uk/1r1) provides a step-by-step walkthrough on how to fine-tune and deploy a text classification model, using trained models from TensorFlow Hub [hands on]
* [Amazon EMR Serverless Now Generally Available – Run Big Data Applications without Managing Servers](https://aws-oss.beachgeek.co.uk/1r2) walks you through the GA announcement of Amazon EMR Serverless, a serverless deployment option for customers to run big data analytics applications using open-source frameworks like Apache Spark and Hive without configuring, managing, and scaling clusters or servers
* [Customizing scheduling on Amazon EKS](https://aws-oss.beachgeek.co.uk/1r4) demonstrates a proof of concept that makes it easy for you to customise the way Kubernetes schedules your workloads [hands on]

![proof of concept flow diagram](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2022/05/24/Kubernetes-Mutating-Admission-Controller-1.jpg)

* [Updated: Create CloudEvents from AWS EventBridge (and into Direktiv)](https://aws-oss.beachgeek.co.uk/1rd) an update from a post I shared in an earlier newsletter ([#64](https://dev.to/aws/aws-open-source-news-and-updates-5145)) this post shows how you can use this open source technology to convert the AWS EventBridge events into a standard CloudEvents

### Case studies

* [Mobileye’s journey towards scaling Amazon EKS to thousands of nodes](https://aws-oss.beachgeek.co.uk/1qy) reviews how Mobileye’s AI Engineering Group seamlessly runs their workflows on Amazon Elastic Kubernetes Service (Amazon EKS), supporting around 250 workflows daily.

### Quick updates

**AWS Amplify**

Earlier this week was the announcement of the general availability of Geofences for Amplify Geo. Amplify Geo enables frontend developers to add location-aware features to their web applications. Developers looking to display geometric boundaries or Geofences on a map, can now implement a complete Geofence management solution in minutes using the cloud-connected UI widget and APIs from Amplify Geo, powered by Amazon Location Service. Geofences are geometric boundaries that can be drawn around places of interest or areas on a map.

With this release, developers can add an interactive Geofence management UI widget to view, create, and edit Geofences on a map. This UI widget is built on top of the popular MapLibre open-source library and developers can choose from the wide array of community-contributed plugins to further customise their Geofence UI components. Amplify Geo also provides developers with client APIs powered by Amazon Location Service to manage Geofences programmatically from their frontend web application. Developers can use the guided workflow in the Amplify Command Line Interface (CLI) to provision all the necessary cloud resources to create Geofences, or they can use existing Geofence resources.

**SUSE Linux**

Announced earlier in the week were price reductions for Amazon EC2 instances running SLES. When you run SLES on Amazon EC2, you are charged one combined price for the Amazon EC2 infrastructure and the SUSE OS. Read more about the details in the post, [Price reductions on Amazon EC2 instances running SUSE Linux Enterprise Server (SLES) OS](https://aws-oss.beachgeek.co.uk/1qw)

**Dart**

The new Dart Signature V4 client allows developers to securely integrate with all 200+ AWS services using signed HTTP requests. This functionality enables Dart developers to make native calls to AWS backends in their Flutter or Dart applications, to make changes to the data or configurations of AWS services.

Developers can add the Signature V4 client as a dependency to their Flutter or dart application, and use it to interact with AWS services. For example, using the Dart Signature V4 client, a developer can interact with the Amazon Simple Storage Service (Amazon S3) using signed HTTP requests to create a new S3 Bucket. Developers can then choose to upload files to their S3 buckets and also manage the read/write permissions for the files within these buckets.

**OpenZFS**

You can now update the storage and IOPS capacity on your Amazon FSx for OpenZFS file systems with the click of the button, making it even easier to adapt to your evolving storage and performance needs.

Amazon FSx for OpenZFS provides fully managed cost-effective shared file storage powered by the popular OpenZFS file system. When you create an FSx for OpenZFS file system, you can specify its storage capacity, its throughput capacity, and it's disk IOPS capacity. Until today, FSx for OpenZFS only supported updating the throughput capacity of an active file system. Now, you can also increase the storage capacity or change the disk IOPS capacity on your file system in seconds, without disrupting your end users or applications. With this capability, you can now dynamically update all of the primary aspects of your FSx for OpenZFS file system configuration.

**Amazon Genomics CLI v1.5.0**

The Amazon Genomics CLI simplifies and automates the deployment of cloud resources like workflow engines and compute clusters, providing genomics and life science customers with an easy-to-use command line to quickly setup and run genomics workflows on Amazon Web Services (AWS).

Amazon Genomics CLI v1.5.0 has added support for workflows written in the Common Workflow Language (CWL) using the Toil workflow engine. In addition to CWL, the Amazon Genomics CLI supports workflows written with Workflow Definition Language (WDL), Nextflow, and Snakemake enabling customers to run a wide variety of genomics data analyses like joint calling of genome variants and single-cell RNAseq.

Read the full release update in, [Amazon Genomics CLI v1.5.0 adds support for the Common Workflow Language (CWL) with Toil](https://aws-oss.beachgeek.co.uk/1qx)

### Videos of the week

**Apache Kylin**

Apache Kylin™ is an open source, distributed Analytical Data Warehouse for Big Data. In this video, you will learn how you can deploy this open source project into AWS, and then explores some sample data sets (COVID and New York Taxi).

{{< youtube 5kKXEMjO1Sc >}}


**.NET Blazor**

Blazor is a free and open-source web framework that enables developers to create web apps using C# and HTML. In this video, Noah Gift shares with you how to deploy these apps using Amazon ECS.

{{< youtube Xs9vGM3U2Ek >}}


### Events for your diary


**OSPOs In Action: Ways On How Organizations Drive Open Source Innovation**
**Jun 9, 2022, 8:00am PDT**

From the registration page:
> What does it take to establish an Open Source Program Office (OSPO)? This expert-led webinar provides a wealth of insight on the leadership and tools necessary to help implement an OSPO (or an open source initiative) within your organisations. Whether you’re from enterprise, academia, non-profit, or the public sector, you’ll come away with an understanding of OSPO opportunities which drive differentiation and risk mitigation.
>
>You’ll hear from leaders from VMware, Bloomberg, Comcast, and Porsche to better understand the value of the OSPO, and where to get started.

Find out more and sign up for the webinar [here](https://aws-oss.beachgeek.co.uk/1qv).

**Machine Learning at scale using Kubeflow with Amazon EKS and Amazon EFS**
**June 16th, 10am PT**

My colleague Suman Debnath, Principal Developer Advocate at AWS, will discuss how to use the open-source machine learning toolkit Kubeflow. Suman will demonstrate how to deploy Kubernetes cluster utilising Amazon Elastic Kubernetes Service (EKS) and Amazon Elastic File System (EFS) as persistent storage in the backend, which will be utilised for staging the dataset for training, hosting jupyter notebooks, and running the machine learning model.

Find out more and register, [Machine Learning at scale using Kubeflow with Amazon EKS and Amazon EFS](https://aws-oss.beachgeek.co.uk/1rw)


**Observability: Open Source Solutions**
**June 28th, 10:00am - 2:15pm PDT**

The AWS Monitoring and Observability Team invites you to participate in a hands on session with Amazon Managed Service for Prometheus, Amazon Managed Service for Grafana and AWS Distro for Open Telemetry. During this session you will use these services in creating workspaces, ingesting/querying metrics, logs and trace data and viewing in a dashboard you will set up. The afternoon will close with demo of what you have done and highlighting the value in MTTD, MTTI, MTTR and application performance.

This event is designed for those looking to implement AWS Observability using open-source services to visualize their data with native or 3rd party tools. Site reliability engineers, operations engineers, systems engineers, and DevOps. Familiarity with monitoring concepts such as logs, metrics, traces, alarms, and the dashboard is recommended, but not required.

Register [via this page](https://aws-oss.beachgeek.co.uk/1qt).


**BOSC 2022**
**July 13-14, Madison, Wisconsin, USA**

The Bioinformatics Open Source Conference (BOSC) has been held annually since 2000, and this year AWS is proud to be a platinum sponsor for this event. BOSC covers all aspects of open source bioinformatics software and open science, including (but not limited to) these topics, Open Science and Reproducible Research, Open Biomedical Data, Citizen/Participatory Science, Standards and Interoperability, Data Science Workflows, Open Approaches to Translational Bioinformatics, Developer Tools and Libraries, Inclusion, and Outreach and Training. This is a hybrid event (in person/virtual) and you find out more by checking out the event page, [BOSC 2022](https://aws-oss.beachgeek.co.uk/1li)

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