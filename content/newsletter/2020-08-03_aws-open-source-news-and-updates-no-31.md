---
title: 'AWS open source news and updates No. 31'
date: '2020-08-03'
tags : [ oss-newsletter ]
---
## August 3rd - Instalment #31

Week No.31 and the last update for a few weeks. I will be taking a break from all things open source and tech, seeking solace in nature and recharging my curiosity batteries for the next couple of weeks, so there will be no updates August 10th and 17th. In the meantime, enjoy another packed edition - there appears no slow down when it comes to open source.

### Event for your diary

A selection of open source related events happening this week and later in August. If you have any open source events you want me to include, let me know and I will add it.

**Cloud Robotics Summit**
**August 18th-19th, starting at 5PM BST (6:00PM CEST, 9:00am PST)**

Join technical experts from across the robotics industry for a complimentary educational event. We’ve designed our program to help you learn best practices and the latest technology for robotics application development. Check out our schedule of sessions hosted by AWS Robotics engineers and solutions architects with guest speakers from the Open Robotics, ROS-Industrial Consortium, iRobot, and Labrador Robotics.

[Sign up here](https://pages.awscloud.com/Cloud-Robotics-Summit?sc_channel=sm&sc_campaign=Open_Source&sc_publisher=TWITTER&sc_country=Open+Source&sc_geo=GLOBAL&sc_outcome=event_registration&trk=open_source_TWITTER&linkId=94846423#).

**Kubecon**
**August 17th, 8:00am PST**
**August 19th, 9:00am - 5:00pm ASIA/Shanghai APAC edition**
**August 24th, 9:00am - 5:00pm CEST EMEA edition**

Start off your KubeCon 2020 with AWS at Container Day on August 17th. In this full-day virtual event, we’ll cover how Amazon EKS makes it easy to deploy, manage, and scale containerised applications using Kubernetes on AWS. Virtual sessions throughout the day will consist of technical deep dives, product demos, and product announcements. The AWS Kubernetes team will be streaming on Twitch all day, ready to answer your questions.

Read more about the AWS Containers Day at KubeCon [here](https://aws.amazon.com/blogs/containers/save-the-date-aws-container-day-at-kubecon/) and register [here](https://awscontainerday.splashthat.com/?&trk=el_a134p000003ygmIAAQ&trkCampaign=AWS_Container_Day&sc_channel=el&sc_campaign=GLOBAL_PM_WEBINAR_aws-container-day_20200817_NAMER&sc_outcome=Product_Marketing&sc_geo=mult). For APAC regions/time register [here](https://awscontainerdayapac.splashthat.com/?&trk=el_a134p000003ygmXAAQ&trkCampaign=AWS_Container_Day_APAC&sc_channel=el&sc_campaign=GLOBAL_PM_WEBINAR_aws-container-day_20200817_APAC&sc_outcome=Product_Marketing&sc_geo=mult), for EMEA regions/time register [here](https://awscontainerdayemea.splashthat.com/?&trk=el_a134p000003ygmcAAA&trkCampaign=AWS_Container_Day_EMEA&sc_channel=el&sc_campaign=GLOBAL_PM_WEBINAR_aws-container-day_20200817_EMEA&sc_outcome=Product_Marketing&sc_geo=mult).

### Your feedback matters!

I have put together a short feedback survey, which I would ask you to take - it will take no more than 2 minutes. You can access [here](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn). Many thanks!

[Take the survey](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn)

### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to Model Zoo, Andrew O'Hara, Nick Bordeau, Mayank Madhukar, David Berg, Ravi Kiran Chirravuri, Romain Cledat, Jason Ge, Savin Goyal, Ferras Hamad, Ville Tuulos, Javier Ramirez, Chris Fregly, Jiaxin Shan, Richard Gate, Shrinath Kurdekar, Sebastian Doell, Re Alvarez-Parmar, Ashwin Raghuraman, Shawn Przybilla, Sam Patzer, Pratip Bagchi and Jonathan Rau

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

**scikit-learn-lambda**

[scikit-learn-lambda](https://github.com/model-zoo/scikit-learn-lambda) is an open source project from Model Zoo that provides a toolkit for deploying scikit-learn models for realtime inference on AWS Lambda. This project provides a few things; first, it provides a handler for serving scikit-learn predictions via AWS Lambda, designed for use with API Gateway; second, it provides supporting Lambda layers that include the necessary supporting libraries; and thirdly, examples of how to get this up and running. Checkout the documentation as it also includes some cost benchmarks.

**mock-aws-java-sdk**

[mock-aws-java-sdk](https://github.com/oharaandrew314/mock-aws-java-sdk) - local testing can be easy with this open source project from Andrew O'Hara, which provides a library that lets you mock AWS out of your tests, allowing you to achieve for better coverage with far less hassle. Works with Java 8, clear documentation and samples provided to get you up and mocking. Not all AWS services are supported yet, so if the one you need is missing, why not add it yourself and grow the project.


**mir_robot**

[mir_robot](https://github.com/GimpelZhang/mir_robot) - project from Junchuan Zhang that shows off the MiR robot in the AWS warehouse gazebo environment. The project provides plenty of guidance on how to set this up, and whether you have a MiR robot or not, you can still get this up and running and test it out - one of the great advantages of ROS is that it allows you to experiment with robots you do not quite have yet!

![demo](https://github.com/GimpelZhang/mir_robot/raw/master/doc/gazebo_screen.gif)

**c3**

[c3](https://github.com/SSHcom/c3) this open source project, C3: Compliant Cloud Components from SSH Communications Security Oyj
is a library provides configuration to AWS CDK components which is compliant with CIS, GDPR and other security standards. The library acts as an overlay for existing AWS CDK components. It aims to minimize effort required to enable compliancy with privacy and security best practices.

**SyntheticSun**

[SyntheticSun](https://github.com/jonrau1/SyntheticSun) an open source project from Jonathan Rau, is a defense-in-depth security automation and monitoring framework which utilizes threat intelligence, machine learning, managed AWS security services and, serverless technologies to continuously prevent, detect and respond to threats. This is now GA, so if you haven't already done so get over to the repository and check it out asap. 

### Fresh blog posts for your reading pleasure

**Docker Compose**

[Docker partners with AWS to smooth container deployments](https://www.zdnet.com/article/docker-partners-with-aws-to-smooth-container-deployments/) last week I mentioned this announcement, simplifying the developer workflows when creating containerised applications. In this post on ZDNet, they share some further thoughts and comments on what this means for customers and builders.


**AWS SAM, AWS SAM CLI and Typescript**

[Creating an AWS SAM CLI project with Typescript and Both Types of Layers](https://t.co/DLlExcqFUy?amp=1) Nick Bordeau shares a detailed walkthrough where you will build a serverless boilerplate using AWS SAM and AWS SAM CLI. Nick shares how he was able to create a specific setup that worked for him using the tools he loved. So if you are a Typescript fan, then check this post out and try Nick's setup for yourself, as well as his GitHub repository for the code. Remember, if you find it useful, give it a star.


**GPG using AWS Lambda**

[Processing PGP Encrypted Data in AWS Lambda using Python](https://medium.com/@mayankmadhukar7191/processing-pgp-encrypted-data-in-aws-lambda-using-python-3b3eeb34b393) - this post covers a creative use of the open version of PGP (Pretty Good Privacy) encryption tool and how to simplify this using AWS Lambda. Mayank Madhukar walks you through how you would create a function to encrypt/decrypt files and then how you could use this. I love creative use cases like this, nice post Mayank!


**Metaflow**

[Unbundling Data Science Workflows with Metaflow and AWS Step Functions](https://t.co/9fRq1poqns?amp=1), in the collaboration between David Berg, Ravi Kiran Chirravuri, Romain Cledat, Jason Ge, Savin Goyal, Ferras Hamad and Ville Tuulos, they announce new capabilities with the Metaflow tool that Netflix open sourced late last year. Metaflow is a framework that attempts to abstract the complexities of data science and engineering tasks using a layered approach. As the posts states at the start:

>The idea of abstraction layers is a fundamental way to manage complexity in computing: Atoms make transistors, transistors make functional units in CPUs, CPUs implement instruction sets that are targeted by compilers for higher-level languages. A key benefit of these layers is that they can be developed independently by separate groups of people, as they are coupled together only through a well-scoped interface. The layers can have independent life cycles that enable higher layers of the stack to maintain a semblance of stability without hindering innovation at the layers below.
>

This post dives deep into the scheduling layer and specifically how they are integrating with AWS Step Functions. You can check the Netflix Tech blog for earlier posts on Metaflow as well if you want to start with a primer, then check out this post - [Open-Sourcing Metaflow, a Human-Centric Framework for Data Science](https://netflixtechblog.com/open-sourcing-metaflow-a-human-centric-framework-for-data-science-fa72e04a5d9)


### AWS open source posts

**Apache Flink**

Colleague Javier Ramirez shows you how to deploy Apache Flink on AWS in ten minutes.

{% youtube qBUVZzoukpA %}

Check out the code he uses here - https://github.com/javier/wiki-edits


**Graylog on Amazon Lightsail**

[Building a Graylog server to run on an Amazon Lightsail instance](https://aws.amazon.com/blogs/compute/building-a-graylog-server-to-run-on-an-amazon-lightsail-instance/) - a guest post from customer Richard Gate, shows you how to build a Graylog server on Amazon Lightsail. Graylog is an open source tool that allows you to collect, aggregate and then manage large amounts of log files from computer systems, networks, devices and more. In this walkthrough, he shows you how to get this up and running on Amazon Lightsail using a simple networking setup to show how you might manage all your network device logs.

![arch](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2020/07/28/graylog1.png)

**Enterprise grade Kubeflow**

[Enterprise-ready Kubeflow: Securing and scaling AI and machine learning pipelines with AWS](https://aws.amazon.com/blogs/opensource/enterprise-ready-kubeflow-securing-and-scaling-ai-and-machine-learning-pipelines-with-aws/) - join post by Chris Fregly and Jiaxin Shan they describe AWS contributions to the Kubeflow project, which provide enterprise readiness for Kubeflow deployments. Many AWS customers are building AI and machine learning pipelines on top of Amazon Elastic Kubernetes Service (Amazon EKS) using Kubeflow across many use cases, including computer vision, natural language understanding, speech translation, and financial modelling. The post highlights how AWS customers can use Kubeflow with native AWS-managed services for secure, scalable, and enterprise-ready AI/ML workloads.

![image](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2020/07/28/fregly_f1-2020-07-13_lead.png)

**Caffe2**

[How SNCF Réseau and Olexya migrated a Caffe2 vision pipeline to Managed Spot Training in Amazon SageMaker](https://aws.amazon.com/blogs/machine-learning/how-sncf-reseau-and-olexya-migrated-a-caffe2-vision-pipeline-to-managed-spot-training-in-amazon-sagemaker/) co-written by guest authors from SNCF and Olexya, this post shows how the French state-owned railway company Société Nationale des Chemins de fer Français (SNCF) uses ML from AWS with the help of its technology partner Olexya to research, develop, and deploy innovative computer vision solutions.

SNCF was founded in 1938 and employs more than 270,000 people. SNCF Réseau is a subsidiary of SNCF that manages and operates the infrastructure for the rail network. SNCF Réseau and its technology partner Olexya deploy innovative solutions to assist the operations of the infrastructure and keep the bar high for infrastructure safety and quality. The field teams detect anomalies in the infrastructure by using computer vision.

This post shows how using open source machine learning frameworks, tooling together with AWS Services, they were able to make significant cost and time savings.

**Metaflow**

[How Netflix’s ML framework, Metaflow drives open source adoption with AWS Service Catalog](https://aws.amazon.com/blogs/mt/how-netflixs-ml-framework-metaflow-drives-open-source-adoption-with-aws-service-catalog/) a second post this week on Metaflow, this time from Sanjay Garje of AWS and Savin Goyal from Netflix. In this post, you will learn how Netflix uses Metaflow sandboxes to provision AWS resources required for running ML workloads. Metaflow in combination with AWS Service Catalog provides an easy and automated way for you to centrally manage your cloud footprint while providing self-service infrastructure provisioning capabilities to your engineering and data science teams.

![architecture](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2020/07/31/Netflix-SC-Architecture-Diagram-1024x499.png)

**AutoML with AutoGluon**

[Code-free machine learning: AutoML with AutoGluon, Amazon SageMaker, and AWS Lambda](https://aws.amazon.com/blogs/machine-learning/code-free-machine-learning-automl-with-autogluon-amazon-sagemaker-and-aws-lambda/) a joint effort between Abhi Sharma, Tatsuya Arai, and Ryan Brand, looks at the open source AutoML library AutoGluon and demonstrates how to train ML models and make predictions without writing a single line of code. Thanks to AutoGluon, Amazon SageMaker, and a bit of AWS Lambda magic, you can use this code-free pipeline to leverage the power of ML without any prior programming or data science expertise.

![diagram](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2020/07/30/automl-001.jpg)

**AWS CloudFormation and GitHub Actions**

[Deploy AWS CloudFormation stacks with GitHub Actions](https://aws.amazon.com/blogs/opensource/deploy-aws-cloudformation-stacks-with-github-actions/) - post by Sebastian Doell, that explains how to use AWS CloudFormation Action for GitHub Actions. Last year we open sourced four GitHub Actions for Amazon ECS and ECR, but this has expanded with the release of AWS CloudFormation Action for GitHub Actions. GitHub Action enables developers and cloud engineers to maintain their infrastructure as code in a AWS CloudFormation stack on their favourite open source platform. The action uses AWS CloudFormation to continuously deploy updates to the described infrastructure. The post provides sample code and templates which you can use and tailor for your own applications.

**Amazon EKS and Kubecost**

[How to track costs in multi-tenant Amazon EKS clusters using Kubecost](https://aws.amazon.com/blogs/containers/how-to-track-costs-in-multi-tenant-amazon-eks-clusters-using-kubecost/) - written by Re Alvarez-Parmar, this post explores in detail the options you have around building multi-tenant solutions on Amazon EKS and then introduces Kubecost, an open source (open core) project that you can use to track costs in a shared EKS environment.

![kubecost](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2020/07/27/image-55.png)

**Amazon FSx for Lustre**

[Automatically import Amazon S3 object updates into Amazon FSx for Lustre](https://aws.amazon.com/blogs/storage/automatically-import-amazon-s3-object-updates-into-amazon-fsx-for-lustre/) - Shrinath Kurdekar talks about Amazon FSx for Lustre, a high performance open source file system, and how you can configure your FSx for Lustre file system to automatically update its contents as new objects are added, or as existing objects are updated in your Amazon S3 buckets.

![architecture](https://d2908q01vomqb2.cloudfront.net/e1822db470e60d090affd0956d743cb0e7cdf113/2020/07/27/New-objects-and-new-and-changed-objects-goign-into-Amazon-S3-and-then-eventually-automatically-imported-into-Amazon-FSx-for-Lustre.png)

This post will walk you through the options and give you everything you need to know about how to set this up.

**Blazor WebAssembly**

[Run Blazor-based .NET Web applications on AWS Serverless](https://aws.amazon.com/blogs/developer/run-blazor-based-net-web-applications-on-aws-serverless/) - Pratip Bagchi provides an introduction into Blazor WebAssembly (a new client-side web development framework that lets developers to use C# to create application front end, and is part of the open-source .NET platform) and then shows you how you can build a sample application using Blazor and some AWS services such as Amazon S3 and AWS Lambda.

![architecture](https://d2908q01vomqb2.cloudfront.net/0716d9708d321ffb6a00818614779e779925365c/2020/07/27/BlazorWebHosting.png)

Check out the project repository so you can follow along, https://github.com/aws-samples/serverless-video-downloader

**Amplify Video**

[Introducing AWS Amplify Video on Demand](https://aws.amazon.com/blogs/media/introducing-aws-amplify-video-on-demand/) - Ashwin Raghuraman, Shawn Przybilla, and Sam Patzer walk you through a new video-on-demand (VOD) resource type to AWS Amplify Video that allows you to easily store, manage, and serve file-based video content from AWS within minutes through the Amplify Command Line Interface (CLI). Last year, we announced the launch of Amplify Video, an open source Amplify category that helps you quickly build video streaming applications. Designed for applications built on the AWS Amplify ecosystem, Amplify Video lets you manage the back-end infrastructure used for video streaming from the comfort of your Amplify project.

![arch](https://d2908q01vomqb2.cloudfront.net/fb644351560d8296fe6da332236b1f8d61b2828a/2020/07/28/Picture1-18.png)

This post will help you to build your very first VOD streaming pipeline using the Amplify Video plugin. You can then use this project as a base in which to continue developing your application by adding a player (such as video.js) or making use of the other Amplify categories such as Auth and Analytics.

**ROS**

[Testing a PR2 Robot in a simulated Hospital World](https://aws.amazon.com/blogs/robotics/hospital-world-simulating-robot/) this post from Matt Hansen is a great introduction to and exploration of the use of robotics and robots in hospitals. I posted over the last couple of weeks some gazebo resources (hospital resources for gazebo) and this posts kind of brings this all together nicely.

![diagram](https://d2908q01vomqb2.cloudfront.net/a9334987ece78b6fe8bf130ef00b74847c1d3da6/2020/07/31/PR2-stuck-in-doorway-3.png)

**AWS SAM and AWS Toolkit for VS Code**

[Introducing launch configurations support for SAM debugging in the AWS Toolkit for VS Code](https://aws.amazon.com/blogs/developer/introducing-launch-configurations-support-for-sam-debugging-in-the-aws-toolkit-for-vs-code/) - Justin Keyes shows you in this post how the AWS Toolkit for Visual Studio Code implements a new SAM debugging experience based on VS Code launch configurations that replaces the old Run Locally | Debug Locally experience. The new experience embraces VS Code’s standard debugger experience, from configuration, to running and debugging, and stepping through code. If you use VS Code and do Serverless, then this should be on your reading list.

### Case Study

**Bhinneka**

In this customer case study from Bhinneka, [Bhinneka Cuts Time-to-Market in Half with AWS](https://aws.amazon.com/solutions/case-studies/bhinneka/) they share how they "reduced our costs by 30 percent with AWS, while gaining a broader set of open-source cloud applications and uptimes of 99.98 percent." according to CTO Lodewijk Tanamal. 

Launched 25 years ago, Bhinneka is an offline retailer in Indonesia that has embraced e-commerce. The company now runs business-to-consumer (b2c), business-to-business (b2b), and business-to-government (b2g) websites, selling office supplies to b2b and b2g customers and a wide range of items including clothing, tools and computers to its b2c audience.

To drive innovation, it wanted to switch from proprietary to open-source software to cut costs and free up resources for artificial intelligence (AI) and machine-learning (ML) projects.  Lodewijk added, “We’ve reduced our costs by 30 percent by moving our Windows workloads to Linux on AWS, while gaining a broader set of Linux cloud applications and uptimes of 99.98 percent.”


### Quick updates

**Amazon RDS PostgreSQL**

Amazon Aurora Supports In-Place Upgrade from PostgreSQL 10 to 11. You can upgrade your Amazon Aurora with PostgreSQL compatibility database cluster from major version 10 to 11, with just a few clicks in the AWS Management Console. PostgreSQL 11 includes major improvements to partitioning and parallelism, and many useful performance improvements like adding columns with a non-null column default faster. It supports SQL stored procedures that allow embedded transactions within a procedure.

**AWS ParallelCluster 2.8.0**

AWS ParallelCluster is a fully supported and maintained open source cluster management tool that makes it easy for scientists, researchers, and IT administrators to deploy and manage High Performance Computing (HPC) clusters in the AWS cloud. HPC clusters are collections of tightly coupled compute, storage, and networking resources that enable customers to run large scale scientific and engineering workloads.  Significant feature enhancements to this latest release of ParallelCluster include:

* Support for ARM-based instances: AWS has recently released both the M6g and the C6g instances that use the next-generation ARM-based chip designed by AWS (and Annapurna Labs, an Amazon company), utilizing 64-bit Arm Neoverse N1 cores. These instances give customers another way to optimize their price performance (up to 40% cost-performance ratio improvement relative to M5 instances) on AWS when running their HPC workloads in AWS.
* Enhanced pcluster update functionality: The pcluster update command allows customers to modify attributes of a running ParallelCluster cluster such as the instance type of compute nodes. With the latest version of ParallelCluster we have provided an improved interface so that customers can stage and inspect the changes to be applied by an update action before execution, as well as review instructions for further actions required to perform the update safely.
* Support for automatic backups with FSx for Lustre: You can now create point-in-time backup copy of your FSx for Lustre file system, use backups as the source for your Lustre file system, and specify a schedule for creating these file system backups. You can find more information on this backup feature here as well as information on how to configure it in ParallelCluster here.

### Share your open source projects 

Do you have some content you want to share with a broader audience? We are always looking for guest content for the AWS Open blog. Please get in touch (via comments below) and I would love to speak with you about what you are doing in open source. We are always looking for interesting new content.

The best submissions will get some AWS Credit codes as a thank you.


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)