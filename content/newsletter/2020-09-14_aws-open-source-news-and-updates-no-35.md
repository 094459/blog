---
title: 'AWS open source news and updates No. 35'
date: '2020-09-14'
tags : [ oss-newsletter ]
---
## September 14th - Instalment #35

Week No.35, this week we have more great blog posts, projects, events and case studies for you. This week we have the first open source themed Dev Day (see below) which is something I encourage you all to check out as some AWS's best speakers will be covering some great open source topics. As always, thanks for everyone who contributes these posts - please follow them to keep up with future posts and updates.

[Dev Day: Open source edition](https://pages.awscloud.com/EMEA-field-OE-DevDay-OpenSource-2020-reg-event.html) - this week's must attend event, with four excellent sessions covering open source topics from Kubernetes networking, looking at different options on running Apache Flink, building machine learning workflows with Kubernetes and Kubeflow Pipelines and finally full-stack TypeSafety with React, GraphQL, and TypeScript. Use the link on that page to sign up and then sit back with the glow of satisfaction.

### Your feedback matters!

I have put together a short feedback survey, which I would ask you to take - it will take no more than 2 minutes. You can access [here](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn). Many thanks!

[Take the survey](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn)


### Events for your diary

This week folks, some great events if you have not already signed up for then why not have a look today. As always, if you have an event you want me to share with readers, please drop me a message.

**MLops Best Practices with Amazon SageMaker and KubeFlow**
**September 15th, 9am Singapore TZ**

This webinar will present best practice deployment of Machine Learning workloads using Amazon Sagemaker and Kubeflow (the open source toolkit for Kubernetes). Details and registration can be found [here](https://pages.maxkelsen.com/mlops).

**Dev Day: Open Source**
**September 17th, 10:00 BST - 4:00PM BST**

[Dev Day: Open source edition](https://pages.awscloud.com/EMEA-field-OE-DevDay-OpenSource-2020-reg-event.html) - our first Dev Day featuring open source topics from Kubernetes networking, looking at different options on running Apache Flink, building machine learning workflows with Kubernetes and Kubeflow Pipelines and finally full-stack TypeSafety with React, GraphQL, and TypeScript.


**CDK Day**
**September 30th, 3PM BST**

Now this is an event you should put in your diaries, an event that has been put together by the AWS CDK community (and a lot of familiar faces from posts I have shared in this weekly newsletter), has a fantastic line up of speakers and promises to be an unmissable event if you are thinking of or looking at AWS CDK. Find more details, including speaker line up and registration, at the link -> https://www.cdkday.com/

### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to  Nir Mashkowski, Yan Cui, Tim Hinrichs, Torin Sandall, Lars Jacobsson, Vladimir Budilov, Moshe Simantov, Oscar Medina, Karthi Thyagarajan, Deepthi Mohan, Yegor Tokmakov, Baji Shaik, Zoe Wang, Yoshitaka Haribara, Joseph Glover, André Sionek, Adrian Hornsby,  Maysam Ali, Massimo Re Ferre, Pahud Hsieh, David Surey and Bastian Klein

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.


### Latest from open source projects

**aws-crt-client**

[aws-crt-client](https://github.com/aws/aws-sdk-java-v2/tree/master/http-clients/aws-crt-client) AWS CRT HTTP Client is an open source project that provides asynchronous, non-blocking HTTP client built on top of the Java bindings of the AWS Common Runtime. You can use the CRT HTTP client to benefit from features such as improved performance, connection health checks, and post-quantum TLS support. It is the second first-party asynchronous HTTP client supported by the SDK for Java after Netty NIO HTTP client. To learn more about this and how you can use it, check out the blog post, [Introducing AWS Common Runtime HTTP Client in the AWS SDK for Java 2.x](https://aws.amazon.com/blogs/developer/introducing-aws-common-runtime-http-client-in-the-aws-sdk-for-java-2-x/) from Zoe Wang. There was also some coverage from ADTMag, and you can read what John Waters wrote  in [Preview Release of AWS CRT HTTP Client for Java SDK Now Available](https://adtmag.com/articles/2020/09/09/aws-crt-http-client-preview.aspx). 

![pic](https://d2908q01vomqb2.cloudfront.net/0716d9708d321ffb6a00818614779e779925365c/2020/09/08/lambda_coldstart-1024x508.png)

**chaos-ssm-documents**

[chaos-ssm-documents](https://github.com/adhorn/chaos-ssm-documents) Adrian Hornby's open source project provides a collection of AWS SSM Documents to perform Chaos Engineering experiments. Adrian added some new capabilities this week, including injecting the rollback first to make the failure injection safer and adding an AWS service specific latency injection document using published IP ranges. This is a good place to start, but make sure you check out Adrian's "words of caution" before you begin.

**aws-lambda-traffic-shifting**

[aws-lambda-traffic-shifting](https://github.com/adhorn/aws-lambda-traffic-shifting) another project from Adrian, this time Python source code and supporting files for a serverless application that you can deploy with the SAM CLI and that uses CodeDeploy and Lambda traffic shifting for deployment. Adrian used this for a demo, but you can use this as the base for your own experimentation.

**cdk-k3s-cluster**

[cdk-k3s-cluster](https://github.com/aws-samples/aws-cdk-for-k3scluster) hot new project from Massimo Re Ferre and Pahud Hsieh, cdk-k3s-cluster is a new JSII construct library for AWS CDK that deploys a scalable Kubernetes K3s cluster on Graviton2 Arm-based (mg6) Spot instances with one click command on AWS. Check out [this thread on Twitter](https://twitter.com/mreferre/status/1304431239542300674) where Massimo goes into some more details and background about this project. As always, the documentation and getting started are what you expect with Massimo's projects - clearer than mountain spring water.

![arch](https://github.com/aws-samples/aws-cdk-for-k3scluster/raw/master/images/ks3clusterdeploy.png)

**sort-key**

[sort-key](https://github.com/neuledge/sort-key) from Moshe Simantov is an open source Node library for generating safe sort keys for DynamoDB, helping you to generate sort keys from multiple string parts as per [this post](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/bp-sort-keys.html).

**dynamodb-to-slack**

[dynamodb-to-slack](https://github.com/vbudilov/dynamodb-to-slack) an open source project from Vladimir Budilov that allows you to propagate dynamoDB data to slack as it's added. Check out his [YouTube videos](https://www.youtube.com/watch?v=XaO8BBgBRH0) as to how you might incorporate this tool to solve problems in your own applications and projects.

**lambda-timeout-metric**

[lambda-timeout-metric](https://github.com/lumigo-io/SAR-lambda-timeout-metric) is an open source Serverless Application Repository app that automatically create timeout metrics for Lambda functions using CloudWatch metric filters. Check out [this tweet](https://twitter.com/theburningmonk/status/1304925849062453248?s=11) from Yan Cui for more info.

**GitHub Action & Copilot**

[Setup AWS Copilot](https://github.com/softprops/setup-aws-copilot) this open source GitHub action from Doug Tangren might be useful if you are looking at setting up and configuring the AWS Copilot command line interface for your projects.

### Fresh blog posts for your reading pleasure

**Kubernetes YAML files**

[This Kubernetes YAML generator](https://k8syaml.com/) from Octopus Deploy might not be open source, but if you are working with Kubernetes, this handy tool is perfect for automating the creation of those YAML files.

**Apache Airflow on AWS**

[How to deploy Airflow on AWS: best practices](https://t.co/FxTvWHjixw?amp=1) nice post from André Sionek sharing his best practices on getting Apache Airflow up and running on AWS, including his [repository on GitHub here](https://github.com/andresionek91/airflow-autoscaling-ecs). This covers everything you need to know, including a short piece around what you can expect to see cost wise. If you are struggling with Apache Airflow, then this might be the post for you.

**Travis CI on AWS Graviton2**

[Announcing General Availability of Graviton2 CPU Support!](https://blog.travis-ci.com/2020-09-11-arm-on-aws) this blog post from the folks at Travis CI announces the general availability to support users to build and test projects using AWS Graviton2 processor. The post talks in details what you can do and how you can get started.

**TensorFlow**

[Build, Train and Deploy A Real-World Flower Classifier of 102 Flower Types](https://towardsdatascience.com/build-train-and-deploy-a-real-world-flower-classifier-of-102-flower-types-a90f66d2092a) in this post from Juv Chan, he shares his project on building a real-world flower classifier with TensorFlow, Amazon SageMaker and Docker. If you love flowers as much as Juv, then why not check this project out. If you, like myself, do not know the first thing about them, then this will be the perfect opportunity to learn more.

**Developer productivity**

[A brief summary of our AWS productivity tools](https://dev.to/ljacobsson/a-brief-summary-of-our-aws-productivity-tools-2ofl) an excellent post from Lars Jacobsson, where he reviews a number of open source tools that his team have authored, covering how they are used, features and why they developed them in the first place. Awesome stuff, and I have mentioned some of these tools in previous instalments of this newsletter.

**Redis**

[Add a Serverless front-end to your ElastiCache Redis cluster](https://t.co/a6YxNPPpqI?amp=1) Nir Mashkowski shares his learning from the past 18 months using Redis, including a practical example of how to use Serverless technology together with Amazon ElastiCache for Redis that allow you to create cost effective solutions quickly.

![arch](https://miro.medium.com/max/441/1*ef_6G0HJg6M4ykGZzXfzuA.jpeg)

### AWS open source posts

**Amazon SageMaker and Blueoil**

[Using Fewer Resources to Run Deep Learning Inference on Intel FPGA Edge Devices](https://aws.amazon.com/blogs/apn/using-fewer-resources-to-run-deep-learning-inference-on-intel-fpga-edge-devices/) Yoshitaka Haribara and Joseph Glover share how you can use innovative open source projects like Blueoil, to train and convert a neural network model for image classification to an edge-optimized binary for Intel FPGA hardware. Blueoil is an open source edge deep learning framework that helps you create a neural network model for low-bit computation. Using Amazon SageMaker with Blueoil you can train and optimizes deep learning models for inference at the edge on Intel FPGA processors with fewer computational resources,  overcoming the constraints of large industrial deployments of inference at the edge by providing low latency with high throughput without sacrificing accuracy.

![arch](https://d2908q01vomqb2.cloudfront.net/77de68daecd823babbb58edb1c8e14d7106e83bb/2020/09/03/DeepLearning_SageMaker_Fig1_SolutionOverview.jpg)

**TensorFlow and TensorBoard**

[Visualizing TensorFlow training jobs with TensorBoard](https://aws.amazon.com/blogs/machine-learning/visualizing-tensorflow-training-jobs-with-tensorboard/) TensorBoard is an open-source toolkit for TensorFlow users that allows you to visualise a wide range of useful information about your model, from model graphs; to loss, accuracy, or custom metrics; to embedding projections, images, and histograms of weights and biases. Yegor Tokmakov shares in this post, how to use TensorBoard with Amazon SageMaker training jobs, write logs from TensorFlow training scripts to Amazon Simple Storage Service (Amazon S3), and ways to run TensorBoard: locally, using Amazon Elastic Container Service (Amazon ECS) on AWS Fargate, or inside of an Amazon SageMaker notebook instance. 

![tensorboard](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2020/09/01/2-TensorBoard-Screenshot.jpg)

**PostgreSQL**

[Migrate to an Amazon Aurora PostgreSQL instance from another PostgreSQL source](https://aws.amazon.com/blogs/database/migrate-to-an-amazon-aurora-postgresql-instance-from-another-postgresql-source/)  Baji Shaik shares with you a number of different approaches you can take when looking to move your PostgreSQL data; whether that is self managed or using managed services like Amazon Aurora PostgreSQL. I have spent this past week doing a lot of experimentation with Amazon Aurora, and it really is a great way to run your PostgreSQL workloads, so this guide is going to be handy for those that are looking to do just that.

**Jenkins X and Tekton**

[Modernize Your CI/CD Pipeline Using Jenkins X with Amazon EKS](https://aws.amazon.com/blogs/apn/modernize-your-ci-cd-pipeline-using-jenkins-x-with-amazon-eks/) this guest post from Oscar Medina, Developer Advocate for Jenkins X at CloudBees that walks you through setting up Jenkins X via the Jenkins X Boot CLI, using a sample application from GitHub. [Jenkins X](https://github.com/jenkins-x/jenkins-x-platform) is an open source based continuous integration/continuous delivery (CI/CD) solution for your Kubernetes clusters, and Jenkins X Boot is a command line interface that has made it easier to get up and running with it more quickly. This post has it all: DevOps, GitOps and ChatOps, so if you want to know more about those, this might be the perfect post for you.
 
 **Apache Flink**
 
[ Enhanced monitoring and automatic scaling for Apache Flink](https://aws.amazon.com/blogs/big-data/enhanced-monitoring-and-automatic-scaling-for-apache-flink/) Apache Flink is an open-source framework and engine for processing data streams and developers use Apache Flink to build streaming applications to transform and analyse data in real time, and in this post from Karthi Thyagarajan and Deepthi Mohan, you will learn how to easily monitor and automatically scale your Apache Flink applications with Amazon Kinesis Data Analytics, use application metrics to automatically scale the application and finally use CloudWatch dashboards for monitoring your application and showing metrics that you can alarm on.

![dashboard](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2020/08/21/enhanced-monitoring-flink-3.jpg)

**BigBlueButton**

[How to build a scalable BigBlueButton video conference solution on AWS](https://aws.amazon.com/blogs/opensource/how-to-build-a-scalable-bigbluebutton-video-conference-solution-on-aws/) David Surey and Bastian Klein show you how to set up a scaleable video conference solution using AWS services and the open source software, [BligBlueButton](https://bigbluebutton.org/). BigBlueButton is an open source video conference system that supports various audio and video formats and allows the use of integrated video-, screen- and document-sharing functions. BigBlueButton has features for multi-user whiteboards, breakout rooms, public and private chats, polling, moderation, emojis, and raise-hands.

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2020/08/31/suredavi_bigbluebutton_f1_sm-981x1024.png)

**Firecracker**

[How AWS’s Firecracker virtual machines work](https://www.amazon.science/blog/how-awss-firecracker-virtual-machines-work) this post from Adrian Costin Catangiu and Marc Brooker published way back in March slipped past my usually efficient content catching mechanism. A short post that talks about how Firecracker virtual machines work.

### Videos

The Containers from the Couch team have been busy this week, releasing a couple of YT videos that you need to check out, covering AWS CoPilot and then talking about OPA, the Open Policy Agent.

**AWS CoPilot**

Nathan Peck joins the Containers from the Couch team to share how you can use Copilot to Build CI/CD + Integration tests for your ECS applications.

{% youtube SpTI9be5whk %}

**OPA the Open Policy Agent**

In this post, join the CftC team as they talk with the co founders fo the Open Policy Agent, Tim Hinrichs and Torin Sandall, as they look at managing your security policy using [OPA, Open Policy Agent](https://www.openpolicyagent.org/docs/latest/). From their website:

>The Open Policy Agent (OPA, pronounced “oh-pa”) is an open source, general-purpose policy engine that unifies policy enforcement across the stack. OPA provides a high-level declarative language that let’s you specify policy as code and simple APIs to offload policy decision-making from your software. You can use OPA to enforce policies in microservices, Kubernetes, CI/CD pipelines, API gateways, and more.

{% youtube Lez1c2K8r1o %}

### Case Study

**Public Sector: National Center for Atmospheric Research (NCAR)**

[Building cloud-based community knowledge about machine learning to predict and understand extreme weather
](https://aws.amazon.com/blogs/publicsector/building-cloud-based-community-knowledge-machine-learning-predict-understand-extreme-weather/) David John Gagne from the National Centre for Atmospheric Research (NCAR) talks about how they has been using open datasets and open source technologies such as Kubernetes and Juypter, powered by AWS services to undertake large-scale Earth system science research projects in collaboration with the broader university community.

**Education**

[Open source tools are scaling and expanding access to education](https://aws.amazon.com/blogs/opensource/open-source-tools-expanding-access-to-education/) in this piece from Maysam Ali, she shares how open source technologies have helped universities and colleges around the world scale remote learning. The post talks about some of the open source tools they are using, and talks about some of the things they have learnt along the way.

### Quick updates

**SAP on SUSE**

AWS Launch Wizard now allows customers to deploy SAP workloads using SUSE Linux Enterprise Server 15 SP1 and SUSE Linux Enterprise Server 12 SP5.
AWS Launch Wizard offers a guided way of sizing, configuring, and deploying AWS resources for SAP HANA and SAP HANA-based Netweaver systems with a purpose built, easy to use wizard.

**AWS AppSync and GraphQL**

AWS AppSync is a managed GraphQL service that simplifies application development by letting you create a flexible API to securely access, manipulate, and combine data from one or more data sources with less network calls. With AWS AppSync you can build scalable applications, including those requiring real-time updates, on a range of data sources such as NoSQL data stores, relational databases, HTTP APIs, and your custom data sources with AWS Lambda.

AppSync leverages the popular open source tool GraphiQL in the AWS AppSync GraphQL Console. GraphiQL is a graphical, in-browser GraphQL development environment that provides an interactive playground to compose, test, and see the live results of your queries. Today we’re integrating the popular GraphiQL Explorer plugin built and open sourced by the team at OneGraph into the AWS AppSync GraphQL Console. The Explorer adds a graphical representation of available fields and inputs that can be used to construct full queries by clicking through available fields and inputs without the repetitive process of typing the queries out by hand.

Read more [here](https://aws.amazon.com/about-aws/whats-new/2020/09/aws-appsync-improves-the-experience-to-query-graphql-apis-in-the-aws-console/).

**PostgreSQL 13 beta 3**

PostgreSQL 13 Beta 3 can now be deployed for development and testing in the Amazon RDS Database Preview Environment without the hassle of installing, provisioning, and managing the database. This release includes support for a number of extensions.  The PostgreSQL community released PostgreSQL 13 Beta 3 on August 13, 2020. PostgreSQL 13 includes improved functionality and performance such as better duplicate data handling by B-tree indexes, improvements added to partitioning functionality, incremental sorting to accelerate data sorts, parallel processing of indexes with the VACUUM command, more ways to monitor activity within a PostgreSQL database, new security capabilities, and more.  

The Amazon RDS Database Preview Environment supports both Single-AZ and Multi-AZ deployments on the latest generation of instance classes (currently T3, M5, and R5), and can be encrypted at rest using KMS keys. Amazon RDS Database Preview Environment database instances are retained for a maximum period of 60 days and are automatically deleted after the retention period. Amazon RDS database snapshots that are created in the preview environment can only be used to create or restore database instances within the preview environment. Customers can use standard PostgreSQL dump and load functionality to import or export their databases from the preview environment.  

**FreeRTOS**

FreeRTOS kernel v10.4.0 is now available for download. The new version brings numerous new features such as improved direct to task notification capabilities, improved memory protection unit (MPU) support, and a new Linux port. FreeRTOS V10.4.0 includes improved Memory Protection Unit (MPU) support for both the ARMv7-M (ARM Cortex-M3/4/7) and ARMv8-M (ARM Cortex-M23/33) RTOS ports. Additionally the ARMv7-M MPU port now supports devices that have 16 MPU regions, and tickless idling support has been extended to the the ARMv8-M RTOS port. See the MPU support documentation page for important upgrade information.

The the full announcement [here](https://aws.amazon.com/about-aws/whats-new/2020/09/freertos-kernel-v10-4-0-now-available-with-new-features-and-enhanced-ports/).


### Share your open source projects 

Do you have some content you want to share with a broader audience? We are always looking for guest content for the AWS Open blog. Please get in touch (via comments below) and I would love to speak with you about what you are doing in open source. We are always looking for interesting new content.

The best submissions will get some AWS Credit codes as a thank you.


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)14