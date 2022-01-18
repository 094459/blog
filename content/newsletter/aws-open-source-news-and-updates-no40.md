---
title: 'AWS open source news and updates No.40'
date: '2020-10-19'
tags : [ oss-newsletter ]
---
## October 19th - Instalment #40

Week No.40 - if life begins at 40 then I am pleased that this newsletter has reached this milestone. We are only just getting started, and since producing this in January we have covered over 800 articles and over 300 different authors covering open source projects and topics. This week we have the usual round up of new projects, a variety of blog post topics including a couple of unmissable posts on how you can combine Rancher, Kubernetes and the AWS Snowball family of products for some interest 'edge of edge' deployment models and a great post covering an old favourite of mine, AWS DeepRacer. There are some important Graviton2 related posts in the Quick Updates, so check those out and make sure you check out the case studies which we have a lot of this week, and then some new events for your diary later this month and November.

If you are attending All Things Open later today or tomorrow, pop by the AWS booth. I will be on it later, but we have a great team supporting the event and a couple of sessions as well as Matt Asay's keynote.

As always, if you have something you want me to cover, drop me a DM on Twitter or use the contact form and I would love to feature your project or post. Until next week, I will let you dive straight in.


**Appsmith**

Last week I had the chance to speak with Arpit Mohan, CTO of Appsmith, an innovative open source no/low code service that is help customers accelerate how they can deliver applications without the need to know how to code. In this podcast, find out more about what this project is and why they open sourced it. [Podcast - open source builders: Arpit Mohan ](https://dev.to/aws/podcast-open-source-builders-arpit-mohan-37cl)

**Tweet of the Week**

This [tweet](https://twitter.com/_msw_/status/1316833011908833280?s=11) from Matthew Wilson caught my eye this week. Matt's adds: "Linux kernel support for AWS Nitro Enclaves land in Linus' tree today ⬇️. This is part of practicing "upstream first" #OpenSource development, which I have found to be really important for Linux." Why? well, as Matt adds in a subsequent tweet, "A question I ask technology vendors regularly is, 'is that supported in upstream Linux?' It is important in how I evaluate about what technology and products to adopt at work, and I have heard the same from my customers as well."

Check out the kernel commit [here](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=726eb70e0d34dc4bc4dada71f52bba8ed638431e).

### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to Ray Goh, Sergey Voinich, Sébastien Stormacq, Dan Neault, Nathan Taber, Josh Powers, Amir Bar Or, Aaron Friedman, Ali Spittel, Mark Schreiber, Junjie Tang, Dean Phillips, Michael Hausenblas, Imaya Kumar Jagannathan, Cong Zou, Siben Nayak, Oz Katz, Ben Kehoe, Peak, Onramper, Greg Cook, Jacob Mevorach, John Trollinger, Adam Toy and  Casey Burns.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

**lakeFS**

[lakeFS](https://github.com/treeverse/lakeFS) this is an open source layer that delivers resilience and manageability to object-storage based data lakes. With lakeFS you can build repeatable, atomic and versioned data lake operations - from complex ETL jobs to data science and analytics. Check out the documentation [here](https://docs.lakefs.io/) which provides info on what it can do and how to get started.

![arch](https://github.com/treeverse/lakeFS/raw/master/docs/assets/img/wrapper.png)

**Thanks Oz for spotting my mistake and providing me with the right link to use!*

**cdk-aurora-globaldatabase**

[cdk-aurora-globaldatabase](https://github.com/guan840912/cdk-aurora-globaldatabase) if you are looking for a CDK construct to help you deploy Amazon Aurora Global databases, then this is just what you have been looking for.

**aws-sso-login-gui**

[aws-sso-login-gui](https://github.com/benkehoe/aws-sso-login-gui) AWS Hero Ben Kehoe is back with a new project which is a prototype for getting users logged in via AWS SSO without requiring the AWS CLI. Ben is looking for input and thoughts on this folks, and is focused on non technical user experience (not having to manage/setup the various files for example). Give this a look and share your views.

**eks-token**

[eks-token](https://github.com/peak-ai/eks-token) this open source tool from Peak-AI provide a python Package to get EKS auth token (the equivilant to running "aws eks get-token ...." via the AWS CLI). Documentation and examples provided to get you started.

**action-deploy-aws-static-site**

[action-deploy-aws-static-site](https://github.com/onramper/action-deploy-aws-static-site) this GitHub action from Onramper might be what just you need if you are looking for a simple GitHub action that will deploy a static site to AWS Cloudfront, taking care of DNS, SSL certs and S3 buckets. Nice workflow diagram and usage guidelines - as they say, batteries included!

**Shepard**

[shepard](https://github.com/ginkgobioworks/shepard) this is a very interesting project from Jacob Mevorach during his time at  Ginkgo Bioworks. So what is Shepard and what does it do? It is a one-stop shop to turn a container into a highly scalable easy to manage workflow in AWS. It is a machine that makes machines that execute your code and Jacob shares a blog post [Automating the Creation of Batch Processing Workflows in AWS](https://www.ginkgobioworks.com/2020/06/15/shepard-automating-the-creation-of-batch-processing-workflows-in-aws/) that provides a clear write up of the problem space and this solution. Super detailed documentation which has everything you need to both understand and get going.

![arch](https://github.com/ginkgobioworks/shepard/raw/master/pictures/shepard_architecture.jpg)

### AWS open source posts

**Prometheus**

[Amazon CloudWatch Prometheus metrics now generally available](https://aws.amazon.com/blogs/containers/amazon-cloudwatch-prometheus-metrics-ga/) Michael Hausenblas and Imaya Kumar Jagannathan announce the general availability of Amazon CloudWatch supporting the ingestion of Prometheus metrics and walk you through a simple setup to demonstrate it in action. They share some of the key reasons why you might want to do this, so no spoilers and check out the post for more info.

**Prometheus/OpenTelemetry**

A couple of posts from AWS interns on their contribution to these open source projects. First up we have;

[Building a Prometheus remote write exporter for the OpenTelemetry Go SDK](https://aws.amazon.com/blogs/opensource/building-a-prometheus-remote-write-exporter-for-the-opentelemetry-go-sdk/) where Eric Lee and Connor Lindsey—describe their experience building a Prometheus remote write exporter for the popular open source observability project OpenTelemetry. OpenTelemetry provides a single set of APIs, libraries, agents, and collector services to capture distributed traces and metrics from applications. Users can analyse these traces and metrics using Prometheus, Jaeger, and other observability tools.

Following that we have [Integrating the OpenTelemetry JavaScript SDK with AWS X-Ray](https://aws.amazon.com/blogs/opensource/integrating-the-opentelemetry-javascript-sdk-with-aws-x-ray/) Cong Zou shares his experience contributing to OpenTelemetry for the first time. Read this post to find out what lessons Cong learnt and the outcomes he was able to achieve.

They all conclude that working with the OpenTelemetry community was an amazing experience, and encourage you all to join.

**CloudFormation Guard**

[Integrating AWS CloudFormation Guard into CI/CD pipelines](https://aws.amazon.com/blogs/devops/integrating-aws-cloudformation-guard/) written by Sergey Voinich covers in this post how to integrate CloudFormation Guard into CodePipeline and fully automate pre-deployment compliance checks of your CloudFormation templates. What is [CloudFormation Guard](https://github.com/aws-cloudformation/cloudformation-guard) I can hear you all asking? It is an open source tool  to automate and simplify pre-deployment compliance checks of your AWS CloudFormation templates. This enables your teams to define a single source of truth for what constitutes valid infrastructure definitions, to be compliant with your company guidelines and streamline AWS resources’ deployment lifecycle. In this post Sergey walks you through a solution you can deploy yourself in your own AWS environments, so if you are using AWS CloudFormation in a CI/CD setup, this is a must read post.

![arch](https://d2908q01vomqb2.cloudfront.net/7719a1c782a1ba91c031a682a0a2f8658209adbf/2020/10/14/Architecture-Diagram.jpg)

**Graviton2 powered Amazon RDS**

[New – Amazon RDS on Graviton2 Processors](https://aws.amazon.com/blogs/aws/new-amazon-rds-on-graviton2-processors/) more exciting news from my colleague Sébastien Stormacq, who shares news about the availability of the AWS Graviton2 powered instances (M6g and R6g) to power your Amazon RDS MariaDB, MySQL and PostgreSQL instances. Learn more about the different performance and cost characteristics of these instance types against these workloads. Graviton2 instances provide up to 35% performance improvement and up to 52% price-performance improvement for RDS open source databases, based on internal testing of workloads with varying characteristics of compute and memory requirements. With that news, what is holding you up? If you are running Amazon RDS workloads, you should be checking this out today.

**Ubuntu support in Amazon EKS**

[Introducing Ubuntu support for Amazon EKS 1.18](https://aws.amazon.com/blogs/containers/introducing-ubuntu-support-for-amazon-eks-1-18/) Nathan Taber and Josh Powers share how you can now use Ununtu optimised AMIs for Amazon EKS versions 1.17 and 1.18. These images combine the Ubuntu OS with Canonical’s distribution of upstream Kubernetes that automates K8s deployment and operations. In addition to using a slimmed-down, minimal image these images take advantage of a custom kernel that is jointly developed with AWS. The post also walks you through how you can run managed node groups using these AMIs too.

**Kubernetes and Rancher**

[Managing Edge of the Edge deployments with Rancher](https://aws.amazon.com/blogs/publicsector/managing-edge-of-edge-deployments-rancher/) this is a really interesting post from John Trollinger and Adam Toy who show how to leverage a combination of open source technologies like Kubernetes (via K3s) and Rancher to deploy a managed kubernetes cluster running on the AWS Snowball family of compute and edge devices. This post provides a great example of how you can deploy K3s on the AWS Snowcone to help facilitate use cases such where there is poor or intermittent quality connectivity and with limited bandwidth. I do not want to give too much away, but this is this weeks unmissable post.

![arch](https://d2908q01vomqb2.cloudfront.net/9e6a55b6b4563e652a23be9d623ca5055c356940/2020/10/16/Edge-of-edge-with-rancher-overview-of-solution.png)

**AWS DeepRacer**

[Using log analysis to drive experiments and win the AWS DeepRacer F1 ProAm Race](https://aws.amazon.com/blogs/machine-learning/using-log-analysis-to-drive-experiments-and-win-the-aws-deepracer-f1-proam-race/) Ray Goh, a tech executive at DBS Bank shares some of his secrets on how to get the fastest lap times in AWS DeepRacer. It has been a while since I have raced, either virtually or physically, but the AWS DeepRacer community is a vibrant and thriving community who share code and tools to help each other learn about reinforcement learning as well as how to improve lap times. Ray shares some of his log analysis tools (which look amazin) and you can find those in his [GitHub repository here.](https://github.com/TheRayG/deepracer-log-analysis)

![image](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2020/10/08/18-.jpg)

### Partner

**Apache Cassandra on AWS**

[Apache Cassandra on AWS](https://aws.amazon.com/quickstart/architecture/datastax-oss/) if you are looking for a reference architecture for deploying Apache Casandra, this quick start from DataStax will help you deploy an Apache Cassandra cluster on the Amazon Web Services (AWS) Cloud for development or testing purposes in about 20 minutes. Everythong you need to get started, so why not start your Apache Cassandra journey here.

![cassandra](https://d1.awsstatic.com/partner-network/QuickStart/datasheets/datastax-architecture-diagram.c534b27ccababf19b8d42c58788e0d8393fbe150.png)

### Case Studies and Industries

**Database Freedom**

[AWS Database Migration Service: Obsessed with helping customers break free from old-guard databases](https://aws.amazon.com/blogs/database/aws-database-migration-service-obsessed-with-helping-customers-break-free-from-old-guard-databases/) Dan Neault walks you through how customers are using the database migration service to free themselves of proprietry databases, with many of them choosing to migrate to open source databases such as MySQL and PostgreSQL. This posts dives a little deeper into how this works, so if you were ever curious about how you might migrate that proprietary database of yours, check this out.

**Open Data**

[50 years of innovation: How open data is supporting NOAA’s “science, service, and stewardship” mission](https://aws.amazon.com/blogs/publicsector/50-years-innovation-how-open-data-noaa-science-service-stewardship-mission/) in this post read about National Oceanic and Atmospheric Administration (NOAA) as they celebrate 50 years of pushing the boundaries of technological innovation to collect and understand data, as well as share that knowledge and information with others. We are proud to support NOAA’s mission, in particular by providing public access to the agency’s environmental datasets since 2015 through the Registry of Open Data on AWS. The agency has an open data policy that makes available its data from satellites, radars, ships, weather models, and other sources to help organisations accelerate research and innovation. 

[Addressing environmental challenges with the AWS Cloud](https://aws.amazon.com/blogs/publicsector/addressing-environmental-challenges-aws-cloud/) Jessica Cahail product manager at Azavea, to share how her organisation is using AWS and open data to develop tools that help users address environmental challenges and deliver knowledge to support decision making. 

**Cromwell**

[Cromwell on AWS: A simpler and improved AWS Batch backend](https://aws.amazon.com/blogs/industries/cromwell-on-aws-a-simpler-and-improved-aws-batch-backend/) Mark Schreiber talks about Cromwell, an open sourced workflow management system that is geared towards scientific workflows, and how to optimise this for running on AWS and taking advantage of some specific AWS services such as AWS Batch. The post talks about how we have worked with this project to upstream improvements that provide users the ability to better use the elastic resources of AWS when running workflows, such as genomics. 

![arch](https://d2908q01vomqb2.cloudfront.net/c5b76da3e608d34edb07244cd9b875ee86906328/2020/10/15/CromwellOrchestrator.png)

**PartiQL**

[Analyzing healthcare FHIR data with Amazon Redshift PartiQL](https://aws.amazon.com/blogs/big-data/analyzing-healthcare-fhir-data-with-amazon-redshift-partiql/) Amir Bar Or and Aaron Friedman share how  PartiQL, an open source SQL-compatible query language that makes it easy to efficiently query data regardless of where or in what format it is stored, is helping to simplify how data scientists can use SQL to directly query Fast Healthcare Interoperability Resources (FHIR) resources. FHIR is built around resources that logically organise healthcare information in a structured but fully extensible format and is quickly becoming the standard for information exchange in the healthcare industry. This post shows you the power of Amazon Redshift PartiQL and how your data science and data engineer team can handle complex data formats like FHIR easily with automation. Adopting these technologies can bring new innovation to the healthcare world and unlock new benefits and cost-optimization.

![arch](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2020/09/10/analyzing-fhir-1.jpg)

**AWS AppSync/Amplify**

[Building a medical image search platform on AWS](https://aws.amazon.com/blogs/machine-learning/building-a-medical-image-search-platform-on-aws/) this post and application from by Gang Fu, Erhan Bas, and Ujjwal Ratan has everything you need to get started with building an application to index and search medical images, and integrates with AI services to allow you to do things like transform unstructured data into more structured data. Check out the source code on [GitHub here](https://github.com/aws-samples/medical-image-search).

![arch](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2020/09/17/2-Solution-Architecture.jpg)

**Apache AirFlow**

[Field Notes: Building an Autonomous Driving and ADAS Data Lake on AWS](https://aws.amazon.com/blogs/architecture/field-notes-building-an-autonomous-driving-and-adas-data-lake-on-aws/) - Junjie Tang and Dean Phillips share the reference architecture that was used to build the Autonomous Driving  and ADAS data lake for one of our customers, BMW. In this you will learn how this has been built but also how they are using Apache Airflow as a foundational part of that architecture. The post talks about other AWS open source services, so if you want to know what building a data lake at scale looks like, then take a peek at this post.

![airflow](https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2020/10/12/radar-and-video-data-processing-in-MDF4-format-1024x652.jpg)

**CalCAT**

[California using open source solutions and the cloud to create a model of models](https://aws.amazon.com/blogs/publicsector/california-using-open-source-solutions-cloud-create-model-of-models/) this post from Casey Burns shows how public sector's use of open source software is helping to tackle important societal issues such as in this post, the fight against COVID-19.  California COVID Assessment Tool (CalCAT) is an ensemble of models that gives public health leaders and the public the ability to understand in more detail how COVID-19 is spreading at state or county levels and more. Read on to find out more about this project which they open sourced so that more states can use this solution.

### Latest blog posts

**AWS CDK**

[Scalable Deployment Automation Using AWS CDK](https://medium.com/@greg_89568/scalable-deployment-automation-using-aws-cdk-b2e7310fdc87) Greg Cook shares a deep dive and walkthrough of using AWS CDK and .NET to build and deploy serverless functions. Greg provides all the code you need. It is always good to share non Typescript examples, so thanks for putting this together Greg.

**AWS Amplify**

[Build a Music Sharing App with Amazon S3 and AWS Amplify](https://dev.to/aws/getting-started-with-amazon-s3-using-aws-amplify-5ake) a fantastic project and walkthrough from fellow advocate Ali Spittel, which will walk you through how to build a simple music sharing application. Check out the code on Ali's [GitHub repository here](https://github.com/aspittel/s3-demo).

**Bottlerocket**

[Why We Expect AWS Bottlerocket to Take Off](https://uk.nttdataservices.com/en/blog/2020/october/why-we-expect-aws-bottlerocket-to-take-off) in this post, NTT Data provide an overview of what Bottlerocket, what they feel it's strengths are and then conclude what some of the unique features of Bottlerocket that will be important to customers. 

### Quick updates

**Bottlerocket**

Check the full release notes [here](https://github.com/bottlerocket-os/bottlerocket/releases/tag/v1.0.2).

**Apache Avro**

Streaming extract, transform, and load (ETL) jobs in AWS Glue can now read data encoded in the Apache Avro format. Previously, streaming ETL jobs could read data in the JSON, CSV, Parquet, and XML formats. With the addition of Avro, streaming ETL jobs now support all the same formats as batch AWS Glue jobs. AWS Glue streaming ETL jobs continuously consume data from streaming sources, clean and transform the data in-flight, and make it available for analysis in seconds. Apache Avro is a popular format for streaming data because of its support for schema evolution and fast serialisation and deserialisation. 

**Open Source databases and AWS Graviton2**

AWS Graviton2-based database instances are now generally available for Amazon Relational Database Service (RDS). Graviton2 instances provide up to 35% performance improvement and up to 52% price/performance improvement for RDS open source databases depending on database engine, version, and workload. You can launch these database instances when using Amazon RDS for MySQL, Amazon RDS for PostgreSQL, and Amazon RDS for MariaDB. Support for Amazon Aurora is coming soon. AWS Graviton2 processors are custom built by Amazon Web Services using 64-bit Arm Neoverse cores and deliver several performance optimisations over first-generation AWS Graviton processors. This includes 7x the performance, 4x the number of compute cores, 2x larger private caches per core, 5x faster memory, and 2x faster floating-point performance per core. Additionally, the AWS Graviton2 processors feature always-on fully encrypted DDR4 memory and 50% faster per core encryption performance.

Read more [here](https://aws.amazon.com/about-aws/whats-new/2020/10/achieve-up-to-52-percent-better-price-performance-with-amazon-rds-using-new-graviton2-instances/) in the full announcement.

**Amazon EMR on AWS Graviton2**

Amazon EMR now supports Amazon EC2 M6g instances to deliver the best price performance for cloud workloads. Amazon EC2 M6g instances are powered by AWS Graviton2 processors that are custom designed by AWS utilizing 64-bit Arm Neoverse cores. Amazon EMR provides up to 35% lower cost and up to 15% improved performance for Spark workloads on Graviton2-based instances versus previous generation instances. In addition, the combination of EMR runtime for Apache Spark and EC2 M6g instances offer up to 76% lower total cost and 3.6 times improved performance compared to running open source Apache Spark on previous generation instances.

**Apache Kafka**

Streaming extract, transform, and load (ETL) jobs in AWS Glue can now ingest data from Apache Kafka clusters that you manage yourself. Previously, AWS Glue supported reading specifically from Amazon Managed Streaming for Apache Kafka (Amazon MSK). With this update, AWS Glue allows you to perform streaming ETL on data from Apache Kafka whether it is deployed on-premises or in the cloud.

**Kubernetes**

Kubernetes is rapidly evolving, with frequent feature releases and bug fixes. Highlights of the Kubernetes 1.18 release include Topology Manager reaching beta status, a new beta of Server-side Apply, and a new IngressClass resource for the Ingress specification which makes it simpler to customise Ingress configuration. Additionally, you can now configure the behavior of horizontal pod autoscaling. Learn more about Kubernetes version 1.18 in the Kubernetes project release notes. 

Read more about this announcement, including links to the topics mentioned [here](https://aws.amazon.com/about-aws/whats-new/2020/10/amazon-eks-supports-kubernetes-version-1-18/).

### Events for your diary

**AWS Copilot**
**October 19, 2020, 1:00 PM (PT) | 4:00 PM (ET)**

AWS Copilot is a command line interface tool that helps customers develop, release, and operate containerised applications on AWS. AWS Copilot creates all the infrastructure and artefacts required to run a production-ready service on Amazon ECS and AWS Fargate, including task definitions, image repositories, and AWS resources like load balancers and deployment pipelines. In this tech talk, you will learn how to leverage AWS Copilot to containerise applications and deploy production ready micro-services faster on Amazon ECS, with code demos.

Sign up [here](https://pages.awscloud.com/AWS-Online-Tech-Talks_October-2020.html?webinar=2020_1003-CON).

**KubeFlow**
**October 23, 2020, 1:00 PM (PT) | 4:00 PM (ET)**

Distributed training on Kubernetes is both hard to set up and optimise for ML jobs. In this tech talk, you'll learn how to do distributed training in a Kubeflow Pipelines workflow with a Mask-RCNN model in PyTorch. We'll set up an end to end training job for a computer vision use case on multiple GPU nodes and then deploy that model onto a production endpoint using Kubeflow Pipelines for orchestration and Amazon Sagemaker Components for Kubeflow Pipelines. Our model is a Mask-RCNN model from the Detectron2 model zoo trained on the COCO2017 dataset and further fine-tuned on a custom dataset with aerial imagery.

Sign up [here](https://pages.awscloud.com/AWS-Online-Tech-Talks_October-2020.html?webinar=2020_1015-MCL).

**cdk8s**
**October 27, 2020, 11:00 AM (PT) | 2:00 PM (ET)**

The new CDK for Kubernetes (cdk8s) is an open-source project that lets you define Kubernetes applications and reusable components using familiar programming languages. In this tech talk, learn how csk8s works locally on your machine and generates standard Kubernetes YAML data, so you can use it with any Kubernetes cluster running anywhere, including on-premises and the cloud.

Sign up [here](https://pages.awscloud.com/AWS-Online-Tech-Talks_October-2020.html?webinar=2020_1020-CON).

**What’s New with Amazon ElastiCache for Redis**
**October 30, 2020, 9:00 AM (PT) | 12:00 PM (ET**

Amazon ElastiCache for Redis is a blazing fast in-memory data structure store. Customers use ElastiCache for Redis to accelerate and store data for all manner of distributed applications. In Redis 6.0, customers can make their Redis applications more secure by applying Resource Based Access Control (RBAC) to data structures and commands. Furthermore, customers can now use client-side caching to further improve performance. In this tech talk, we will explain and demonstrate these new capabilities.

Register [here](https://pages.awscloud.com/AWS-Online-Tech-Talks_October-2020.html?webinar=2020_1028-DAT)

**OpenShift on AWS**
**Nov 10, 2020 6:00 PM - 7:00 PM GMT**

Mayur Shetty will discuss the benefits of Red Hat OpenShift 4.5 and all the consumption options available to customers on AWS.

Register [here](https://register.gotowebinar.com/register/7154011299129383181?source=Socialhttps://attendee.gotowebinar.com/register/7154011299129383181?source=Social).

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen).

### Your feedback matters!

I have put together a short feedback survey, which I would ask you to take - it will take no more than 2 minutes. You can access [here](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn). Many thanks!

[Take the survey](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn)
