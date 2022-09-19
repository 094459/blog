---

title: 'AWS open source news and updates #127'
date: '2022-09-16'
tags : [ oss-newsletter, aws open source, Kubeflow, OpenSearch, Jenkins, Amazon EMR, Apache Spark, AWS CDK, AWS ParallelCluster,  GitOps, AWS Distro for OpenTelemetry, Prometheus, Grafana, Karpenter, Firecracker, Rust, O3DE, Kotlin, Squid]

---

## September 16th, 2022 - Instalment #127

**Welcome**

Welcome to the AWS open source newsletter, edition #127. I hope some of you were able to catch Derek and myself sharing a peek at this edition, and enjoyed as our special guest, AWS Hero Ian Mckay walked us through some of his open source projects. It was very cool indeed, and if you have not yet watched, Ian shares an early glimpse of a new project - so make sure you check that out.

As always, this week we feature more great new open source projects from AWS and around the AWS community. "cfn-trace" is a cli tool that provides x-ray like traces for your Cloudformation stacks, "tree-view-cfn" extends the recently launched tree view for CDK resources to Cloudformation stacks, "aws-lambda-live-tuner" takes AWS Lambda Power tuning and makes it real time, "surf" allows you to easily search your Cloud resources via the cli, "airflow-on-eks" provides a reference stack for self managed Apache Airflow, "SEGG" a tool for those working with Step Functions, "centralised-egress-proxy" a nice example of how to deploy Squid proxy servers, and many other projects. 

We also have blog posts and technical articles covering open source technologies including Kubeflow, OpenSearch, Jenkins, Amazon EMR, Apache Spark, AWS CDK, AWS ParallelCluster, GitOps, AWS Distro for OpenTelemetry, Prometheus, Grafana, Firecracker, Rust, O3DE, Kotlin, and more! Make sure you don't miss the videos section, this week featuring Karpenter and getting started with Amazon EKS. We finish as always with a round up of events.


**Feedback**

If you enjoy reading this newsletter, please let me know how we can improve it as well as how AWS can better work with open source projects and technologies by completing [this very short survey ](https://eventbox.dev/survey/NUSZ91Z)that will take you probably less than 30 seconds to complete. Thank you so much!

**Celebrating open source contributors**

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created. 

So thank you to the following open source heroes: Samrose Ahmed, Gunner Grosch,  Thirumalai Aiyalu, Justin Garrison, Todd Neal, Alex Kestner, Kevin Hakanson, Mike George, Vikram Venkataraman, Abhi Khanna, Michael Hausenblas, Imaya Kumar Jagannathan, Rodrigue Koffi, nkmehta, and Toshal Dudhwala, Josh Thornes, Jack Mazanec and Othmane Hamzaoui, Vara Bonthu, Melody Yang, Karthik Prabhakar, Paul Roberts, Mohamed (Mo) Ahmed, Viktor Farcic, Madeleine Song, Elena van Engelen - Maslova, Valentina Palmiotti, Jan Ritter, Isan-Rivkin, and Victor Iwuoha

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution.*

#### Tools

**cfn-trace**

[cfn-trace](https://aws-oss.beachgeek.co.uk/21w) this tool from Grunet looks very interesting for AWS Cloudformation users. It captures Cloudformation nested stack deploy events as traces. The tool takes the stack events from when they were updated and converts that info into distributed tracing-style waterfall diagrams to visualise the deployments. Work in progress, so keep an eye on this tool.

![example of a trace from cfn-trace](https://github.com/Grunet/cfn-trace/blob/main/examples/hollow-only-nesting/visualization.png?raw=true)

**tree-view-cfn**

[tree-view-cfn](https://aws-oss.beachgeek.co.uk/21z) **HOT PRESS** if you were watching the latest episode of the Build on AWS open source (S01E02) AWS Hero Ian Mckay walked us through some of his open source projects, and mentioned this new project, tree-view-cfn. So what does it do? Well if you look at the Quick Updates section below, you will see that a new Tree View was introduced as a way to better visualise the resources that your CDK applications deploy. TreeViewCFN is an open source project that can convert any CloudFormation template into one that allows the console to use the tree-view. Very cool indeed!

**aws-lambda-live-tuner**

[aws-lambda-live-tuner](https://aws-oss.beachgeek.co.uk/21s) this looks like a super interesting tool from Jan Ritter for those developers writing AWS Lambda functions. AWS Lambda Live Tuner tests memory configurations based on real incoming events instead of a single test event. Influenced by my colleagues Alex Casalboni's tool, AWS Lambda Power Tuner, this is what Jan has to say:

> Let's imagine we are testing a Lambda function that processes a queue, since the Lambda function is idempotent, messages that have already been processed will be successfully processed again. Using the same test event on all invocations might falsify the results because all subsequent invocations after the initial one might be way faster (event was already processed before). Using different incoming events instead helps you test the actual behaviour of the Lambda.

**surf**

[surf](https://aws-oss.beachgeek.co.uk/21r) this is a nice tool from Isan-Rivkin that provides a CLI Text Search across your infrastructure platforms, think of it like grep for infrastructure.

**airflow-on-eks**

[airflow-on-eks](https://aws-oss.beachgeek.co.uk/21q) this Terraform module helps you deploys the production ready Self-managed Apache Airflow deployment on EKS. Using this it will help you deploy the following AWS resources: A VPC with 3 Private Subnets, 3 Public Subnets for Public ALB, three Database Subnets for RDS
PostgreSQL RDS security group; creates EKS Cluster Control plane with public endpoint (for demo purpose only) with one managed node group; deploys Managed add-ons vpc_cni, coredns, kube-proxy; deploys Self-managed add-ons aws_efs_csi_driver, aws_for_fluentbit, aws_load_balancer_controller, prometheus; Apache Airflow add-on with production ready Helm configuration; and S3 bucket for Apache Airflow logs and EFS storage class for mounting dags to Airflow pods.

**shepard**

[shepard](https://aws-oss.beachgeek.co.uk/21p) Shepard is a one-stop shop to turn a container into a highly scalable easy to manage workflow in AWS. It is a machine that makes machines that execute your code - very meta!

![shepard architecture](https://github.com/ginkgobioworks/shepard/blob/master/pictures/shepard_architecture.jpg?raw=true)

**SEGG**

[SEGG](https://aws-oss.beachgeek.co.uk/21o) Step Function Express Graph Generator (or SEGG) gives visibility to express each execution of a AWS Step Function Express Workflows making it much easier to build and troubleshoot. This tool will help you see the execution visually similar to the execution graph of a Step Function Standard Worflow provided by AWS, and build applications at a much faster rate. Very cool. Check out the short video that provides more info.

{{< youtube u_mXh03CIIU >}}


**iam-identitycenter-identitystoreapi-operations**

[iam-identitycenter-identitystoreapi-operations](https://aws-oss.beachgeek.co.uk/21m) this project provides examples and sample code to manage and audit AWS IAM identity store User and Group operations at scale using APIs.

### Demos, Samples, Solutions and Workshops

**AWS_File_Trans_Lamda_S3_SN**

[AWS_File_Trans_Lamda_S3_SN](https://aws-oss.beachgeek.co.uk/21n) Victor Iwuoha has put together this sample project to show you how you can easily build a serverless data engineering pipeline using a collection of AWS services.

![architecture of data engineering example](https://github.com/VICIWUOHA/AWS_File_Trans_Lamda_S3_SNS/blob/main/AWS_Lambda_S3_by_viciwuoha.png?raw=true)

**aws-sec-checkov-terraform**

[aws-sec-checkov-terraform](https://aws-oss.beachgeek.co.uk/21u) Checkov is a tool that perform security analysis on terraform code. This demo is used in a pipeline that runs automatically every time there is a code commit in the git repository (AWS CodeCommit). The pipeline uses Checkov to analyse terraform code and requests a validation of the security team to continue with environment creation/change

**aiops-serverless**

[aiops-serverless](https://aws-oss.beachgeek.co.uk/21l) Under the Sea is an official AWS workshop delivered by AWS SAs and AWS Partners to help customers and partners to learn about AIOps with serverless architectures on AWS. Under the Sea is an exciting MMORPG developed by the famous entrepreneur behind Wild Rydes, the most popular unicorn taxi service in the world. This time the game design team went above and beyond to bring us a steam-punk adventure 20,000 leagues under the sea. The engineering team brought to live this technology masterpiece that can host hundreds of players simultaneously. 

**centralised-egress-proxy**

[centralised-egress-proxy](https://aws-oss.beachgeek.co.uk/21k) this repo contains a re-usable and customisable solution based on a fleet of open source Squid proxies running on Amazon Elastic Container Service (ECS) with AWS Fargate. Internet access is provided centrally via a NAT Gateway and an Internet Gateway deployed in the central VPC. Amazon ECS uses a Network Load Balancer (NLB) configured as an endpoint service to make the solution available to ‘spoke’ VPCs. Interface endpoints are deployed into the ‘spoke’ (application) VPCs to enable resources inside these VPCs to use the deployed endpoint as its proxy server.

**building-resilient-apps-amazon-dynamodb-global-tables**

[building-resilient-apps-amazon-dynamodb-global-tables](https://aws-oss.beachgeek.co.uk/21v) this repository has sample code demonstrating how to build a resilient multi-region application with DynamoDB Global Tables as the data store.

![architecture of global dynamodb tables](https://github.com/aws-samples/building-resilient-apps-amazon-dynamodb-global-tables/blob/main/images/dynamo-global-pattern-monitoring.png?raw=true)

### AWS and Community blog posts

**Firecracker**

Great post from Valentina Palmiotti, and essential reading this week. In [Attacking Firecracker: AWS' microVM Monitor Written in Rust](https://aws-oss.beachgeek.co.uk/21h) Valentina dives deep and explores virtualisation, Firecracker, KVM and looks at the various layers of virtualisation and VM escape exploitations.

![architecture of firecracker security](https://uploads-ssl.webflow.com/61a8a9fbeff4dc7f21784049/631916976b4fff56992d7feb_Firecracker_2%20(2).svg)

**Kotlin**

Kotlin is a modern, programming language that is easy to learn, especially if you already know Java. Kotlin is used to develop Android apps, server side apps, and much more. I have shared posts in previous newsletters about how Kotlin is being used within AWS and Amazon, but in this post, [Kotlin on AWS Lambda](https://aws-oss.beachgeek.co.uk/21i) Elena van Engelen - Maslova dives deeper into why you might want to run Kotlin Lambda functions, and some of the practicalities.

![graph of Kotlin on lambda](https://miro.medium.com/max/1400/1*CFMpBPPMAOdAi5k2_PAJWg.png)

**O3DE**

In the post, [Advance Prototyping of the InteractiveTutorials Gem for O3DE](https://aws-oss.beachgeek.co.uk/21j), Madeleine Song shares her experience of her summer project focused on advanced prototyping, and how this prototype teaches users how to work with Open 3D Engine, right in O3DE Editor.

![O3DE prototype tutorial](https://www.o3de.org/images/blog/interactive-tutorials-prototyping/interactive-tutorials.png)

**GitOps**

GitOps is an operational framework that takes DevOps best practices used for application development such as version control, collaboration, compliance, and CI/CD tooling, and applies them to infrastructure automation. In the post, [How to Apply GitOps to Everything Using Amazon Elastic Kubernetes Service (Amazon EKS), Crossplane, and Flux](https://aws-oss.beachgeek.co.uk/21g) Paul Roberts, Mohamed (Mo) Ahmed, and Viktor Farcic take you in a step-by-step workflow to provision Amazon Elastic Kubernetes Service (Amazon EKS) clusters and an Amazon RDS database the GitOps way using Crossplane and Flux. [hands on]

**Apache Spark**

In the post, [Run Apache Spark with Amazon EMR on EKS backed by Amazon FSx for Lustre storage](https://aws-oss.beachgeek.co.uk/218) Vara Bonthu, Melody Yang, and Karthik Prabhakar demonstrates how to use EMR on EKS to submit Spark jobs with FSx for Lustre as the storage. [hands on]

![architecture of Apache Spark on EMR on EKS](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2022/09/08/bdb-2181-image003.jpg)

We had more Apache Spark content this week, and Ramesh Raghupathy and Kiran Guduguntla put together this post,  [Optimize Ama­zon EMR costs for legacy and Spark workloads with managed scaling and node labels](https://aws-oss.beachgeek.co.uk/21y) that shows you how to configure an EMR cluster with managed scaling, assign node labels, and use a capacity scheduler to run mixed workload jobs on the EMR cluster.

**Apache Iceberg**

Matano is an open-source security lake platform for AWS. In this post, Serverless asynchronous Iceberg data ingestion, Samrose Ahmed looks at how they leverage Apache Iceberg as part of their main data lake store, showing how they ingest data.

![architecture of Matano and Apache Iceberg](https://www.matano.dev/assets/images/arch-e64180970c00e38fe1fb90892a170f57.png)

**OpenSearch**

The k-NN problem is relatively simple compared to other ML techniques: given a set of points and a query, find the k nearest points in the set to the query. As the number of data points reaches the hundreds of millions or even billions, scaling a k-NN search system can be a major challenge. In [Choose the k-NN algorithm for your billion-scale use case with OpenSearch](https://aws-oss.beachgeek.co.uk/21a) Jack Mazanec and Othmane Hamzaoui cover different algorithms and techniques used to perform approximate k-NN search at scale (over 1 billion data points) within OpenSearch. [hands on]

![illustration of running k-NN in OpenSearch](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2022/08/22/image003oh.jpg)

**Jenkins**

Jenkins is a popular open-source automation server that provides hundreds of plugins to support building, testing, deploying, and automation. Josh Thornes has put together this blog post, [DevOps with serverless Jenkins and AWS Cloud Development Kit (AWS CDK)](https://aws-oss.beachgeek.co.uk/21b) that walks you through how to set up a completely serverless Jenkins environment on AWS Fargate using AWS Cloud Development Kit (AWS CDK). [hands on]

![architecture of jenkins on fargate using cdk](https://d2908q01vomqb2.cloudfront.net/7719a1c782a1ba91c031a682a0a2f8658209adbf/2022/09/07/devops_2093_1.png)

**Observability**

The AWS Observability Accelerator provides a one-click solution that deploys out-of-the-box Amazon Managed Grafana dashboards, AWS Distro for OpenTelemetry collector to collect metrics, store them on Amazon Managed Service for Prometheus and configure alerts and recording rules. Check out the post, [Announcing AWS Observability Accelerator to configure comprehensive observability for Amazon EKS](https://aws-oss.beachgeek.co.uk/21d) Vikram Venkataraman, Abhi Khanna, Michael Hausenblas, Imaya Kumar Jagannathan, Rodrigue Koffi, nkmehta, and Toshal Dudhwala have come together and put together this solution, and have used Terraform so that you can integrate this into your Terraform configurations and customise to your needs.  [hands on]

![example dashboard from observability accelerator](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2022/09/08/cloudops_1053_15N.png)

**Prometheus**

In the post, [Introducing the ACK controller for Amazon Managed Service for Prometheus](https://aws-oss.beachgeek.co.uk/21t) Mike George announces the GA of the Amazon Managed Service for Prometheus ACK controller. This lets you take advantage of Managed Prometheus using custom resource definitions (CRDs) and native Kubernetes objects without having to define any resources outside of your cluster. Mike then how you how to configure Amazon Managed Service for Prometheus resources via ACK, and how to migrate a Prometheus workload to use these newly provisioned resources. [hands on]

**Other posts you might like from the past week**

* [How to develop distributed IoT applications using the AWS IoT Greengrass PubSub SDK](https://aws-oss.beachgeek.co.uk/217) looks at common challenges developers face when designing distributed IoT PubSub applications, and some of the approaches you can take [hands on]

![architecture of iot greengrass](https://d2908q01vomqb2.cloudfront.net/f6e1126cedebf23e1463aee73f9df08783640400/2022/04/20/end-to-end-pubsub-sdk-consistant-messaging.png)

* [Easing your migration from SGE to Slurm in AWS ParallelCluster 3](https://aws-oss.beachgeek.co.uk/219) covers the things you need to know to make a more frictionless move to Slurm
* [Using Python to power an AppStream 2.0 Linux Imaging Assistant GUI](https://aws-oss.beachgeek.co.uk/21c) shows you how to add, launch, and use a graphical Imaging Assistant for Amazon AppStream 2.0 Linux [hands on]
* [Validate database objects post-migration from Microsoft SQL Server to Amazon RDS for MySQL and Amazon Aurora MySQL](https://aws-oss.beachgeek.co.uk/21f) discusses post-migration validation of database objects [hands on]
* [Twin Neural Network Training with PyTorch and Fast.ai and its Deployment with TorchServe on Amazon SageMaker](https://aws-oss.beachgeek.co.uk/21x) demonstrates how to train a Twin Neural Network based on PyTorch and Fast.ai, and deploy it with TorchServe on Amazon SageMaker inference endpoint [hands on]

**Case Studies**

* Kubeflow - The post, [Build repeatable, secure, and extensible end-to-end machine learning workflows using Kubeflow on AWS](https://aws-oss.beachgeek.co.uk/21e) sees Kanwaljit Khurmi, Tyler Kalbach, Victor Krylov, Sasank Vemuri, Anu Tumkur, and William Tsen come together to share how athenahealth uses Kubeflow on AWS (an AWS-specific distribution of Kubeflow) to build and streamline an end-to-end data science workflow.

![architecture of kubeflow case study](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2022/08/31/ML-10889-image005.png)

### Quick updates

**OpenSearch**

The latest version of OpenSearch hit the download links this week, with OpenSearch 2.3 now ready for you to get your hands on. James McIntyre put together this blog post, [OpenSearch 2.3 is ready for download!](https://aws-oss.beachgeek.co.uk/216) that takes a look at three key new features: Segment replication, remote-backed storage, and 	drag-and-drop visualisation.

![demo of opensearch 2.3](https://opensearch.org/assets/media/blog-images/2022-09-14-opensearch-2-3-is-ready-for-download/opensearch_drag_and_drop.gif)

**AWS CDK**

Customers using CDK want a simple way to map the resources synthesised in a CloudFormation template back to the source CDK Construct. In an effort to display all resources in a CloudFormation template the Management Console loses the hierarchical nature of CDK Constructs, which customers are used to today. CDK Construct tree view in the CloudFormation console is intended for the customers who want to observe the context from which the resources were created to the CloudFormation console, in order to provide a better, focused experience.

Tree view capability will automatically organise the resources that were synthesised by AWS CDK Constructs: the top level will be the AWS CDK Construct (by name) and all resources will be placed as a second level under the Construct that generated them. As a user, the Constructs tree view will allow you to easily identify the hierarchy of the resources and their logical location in the application: each resource is placed in an app-logical context, which is presented as a tree view in CloudFormation Console.

**aws-icons-for-plantuml**

[aws-icons-for-plantuml](https://aws-oss.beachgeek.co.uk/1va) provides a way to use the official AWS Architecture Icons with diagrams-as-code tool PlantUML. Kevin Hakanson reached out to me to tell me more about the latest release, 14.0, that includes icons updates from Q3 2022. Additionally, community member Matthew Warman contributed a PR which added support for Groups, enabling more types of architecture diagrams. In a related blog titled [Sequence Diagrams enrich your understanding of distributed architectures](https://aws-oss.beachgeek.co.uk/215), Kevin shows how to use PlantUML and the AWS Icons for PlantUML to explore the design of a serverless architecture.

**MySQL**

Amazon Relational Database Service (Amazon RDS) for MySQL now supports MySQL minor version 8.0.30. We recommend that you upgrade to the latest minor versions to fix known security vulnerabilities in prior versions of MySQL, and, to benefit from the numerous fixes, performance improvements, and new functionality added by the MySQL community.

**Seekable OCI (SOCI)**

Seekable OCI (SOCI) is a technology open sourced by AWS that enables containers to launch faster by lazily loading the container image. SOCI works by creating an index (SOCI Index) of the files within an existing container image. This index is a key enabler to launching containers faster, providing the capability to extract an individual file from a container image before downloading the entire archive.

Most methods for launching containers download the entire container image from a remote container registry before starting the container. Waiting for all of the data is wasteful in cases when only a small amount of data is needed for startup. Prior research has shown that the container image downloads account for 76% of container startup time, but on average only 6.4% of the data is needed for the container to start doing useful work.

There are various solutions to this problem, including reducing the size of a container image and pre-fetching container images to local storage. Lazy loading is an approach where data is downloaded from the registry in parallel with the application startup. Container images are stored as an ordered list of layers, and layers are most often stored as gzipped tar files. It’s usually not possible to fetch individual files from gzipped tar files. Some projects enable lazy loading through format conversion. One such project is stargz-snapshotter, which takes an existing OCI image and builds a new OCI image with an embedded table of contents. With SOCI, we borrowed some of the design principles from stargz-snapshotter, but took a different approach. A SOCI index is generated separately from the container image, and is stored in the registry as an OCI Artifact and linked back to the container image by OCI Reference Types. This means that the container images do not need to be converted, image digests do not change, and image signatures remain valid.

An open-source build tool is used to create SOCI indices for existing OCI container images and a remote snapshotter, called [soci-snapshotter](https://aws-oss.beachgeek.co.uk/20n), provides containerd the ability to lazy load images that have been indexed by SOCI. SOCI and the [soci-snapshotter](https://aws-oss.beachgeek.co.uk/20n) are open sourced under Apache 2.0.

### Videos of the week

**Karpenter**

Check out the Containers from the Couch crew, and join Justin Garrison, Todd Neal and Alex Kestner as they walk through a recently released feature on how the optimisation feature within Karepenter can help you reduce costs.

{{< youtube BnksdJ3oOEs >}}


**Kubernetes**

Join my colleague Gunner Grosch as he talks with Thirumalai Aiyalu, a solutions architect at AWS, for a look at how to get started with Kubernetes on AWS.

{{< youtube TReCo9c4MY4 >}}


### Events for your diary

**OpenSearchCon 2022**
**Sept 21st, 2022 Seattle**

Come to the first annual OpenSearchCon!

This day-long conference will be packed with presenters who build and innovate with OpenSearch. It doesn’t matter if you’re just getting started on your OpenSearch journey, running giant clusters, or contributing tons of code; the event is for everyone. Join us to celebrate the progress and look into the future of the project. Admission is free, and registration will be open in the next few weeks. All you will need to do is sign up, and get to Seattle!

Check out the full details, including signing up and location, at the [meetup page here](https://aws-oss.beachgeek.co.uk/1n1).

**Build on AWS Open Source**
**September 23rd, 9am BST**

The third episode of a new show where Derek Bingham and myself walk you through the latest AWS open source news, show you code and demos of some of the interesting projects we think you should know about and we invite guests to share their open source projects via the medium of demo.

This episode (S01E03) we are very lucky to have the AWS Cloudscape team who will be talking more about this open source project and then diving into the code. Should be great!

https://twitch.tv/aws

**ApacheCon North America 2022**
**October 3-6, New Orleans**

ApacheCon is the official open source software convention of the Apache Software Foundation (ASF), focused on the software projects hosted at the ASF. With over 160 sessions covering all your favourite Apache open source projects and more, 

[Check out the ApacheCon registration page](https://aws-oss.beachgeek.co.uk/221) for more details, including the sessions and keynotes.

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)




### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)

