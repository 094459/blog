---
title: 'AWS open source news and updates No.42'
date: '2020-11-02'
tags : [ oss-newsletter ]
---
## November 2nd - Instalment #42

Week No.42 - [42](https://en.wikipedia.org/wiki/Phrases_from_The_Hitchhiker%27s_Guide_to_the_Galaxy#Answer_to_the_Ultimate_Question_of_Life,_the_Universe,_and_Everything_(42)) may be the answer to the ultimate question of Life, the Universe and Everything, but for today it is just the latest roundup of all the open source news, projects, events, case studies related to AWS. This week we have a great case study from Intuit and their journey to Kubernetes, we have a couple of nice updates from the Open Distro for Elasticsearch, sleemo a nice new open source GraphQL framework and the Stelligent University, an open source curriculum to help bootstrap your learning on AWS. We also have some pretty awesome deep dives on Apache Flink and a look at AWS Nitro Enclaves.

Without further ado, over to the main talk of last week...


### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to Luc Van Donkersgoed, Anil Sener, Biff Gaut, Keerthan Vasist, Theo Salvo, Kyle Davis, Viraj Phanse, Ben Anscombe, Todd Kesselman, Wesley Pettit, Gal Bashan, Richard Downey, Nizar Tyrewalla, Cory Hall, Taewoo Kim, Vamshi Konduri, Bryan Lajoie, Nigel Harris, Dzung Nguyen, Greg LaVigne, Zach Kimberg, Frank Liu, Saurabh Bhutyani, Amir Basirat, Min Xia, Shaocheng Wang, Ying Wang, Tomal Deb, Atanu Roy, Sahika Genc, Nathaniel Slater, Sunil Mallya, Dr. Taha A. Kass-Hout, and Vinay Hanumaiah.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

**polp-fiction-metrics**

[polp-fiction-metrics](https://github.com/mercadolibre/polp-fiction-metrics) is contender for the best open source project name ever, so well done to the team at Mercadolibre. So what does this project do? This is an in-house tool that they developed that aims expose metrics of the current situation regarding privileges based on identities and access on AWS in order to implement the Principal of Least Privilege (PoLP) principle.

**r53db**

[r53db](https://github.com/apparentorder/r53db) this project enables you to access Amazon Route53 Database Zones like SQL tables, it supports reading from (SELECT) and writing to (INSERT/UPDATE/DELETE) your Route53 Database for simple records and ALIAS Targets. The project provides great and easy to understand documentation as well as some nice demo videos to show this in action. I know at least one person who will be delighted by this project - yes Corey, looking at you :)

**FastAI on torchserve**

[amazon-sagemaker-endpoint-deployment-of-fastai-model-with-torchserve](https://github.com/aws-samples/amazon-sagemaker-endpoint-deployment-of-fastai-model-with-torchserve) this project demonstrate how to deploy a FastAI trained PyTorch model in TorchServe eager mode and host it in Amazon SageMaker Inference endpoint. Over the past few years, FastAI has become one of the most cutting-edge open-source deep learning framework and the go-to choice for many machine learning use cases based on PyTorch, so this repository is a good starting point if you are looking to work with this and use this repository as a template to deploy your own FastAI models. 

**awc-cct**

[aws-cct](https://github.com/rocketmiles/aws-cct) is an open source tool from Rocket Travel that provides a simple CLI that wraps the AWS Cost Explorer APIs to be able to quickly identify cost anomalies between monthly bills.

**Trapheus**

[Trapheus](https://github.com/intuit/Trapheus) is an open source tool from the folks at intuit that automates restoration of RDS database instances from snapshots into any dev, staging or production environments. It supports individual RDS Snapshot as well as cluster snapshot restore operations. 

**AWS Lambda Powertools for Java**

[aws-lambda-powertools-java](https://github.com/awslabs/aws-lambda-powertools-java/issues/68#issuecomment-718483307) check out this RFC from the AWS Lambda Powertools community who are looking to get consensus on the question of whether or not to drop the @powertools prefix from the annotations. What do you think? RFC closing soon so get in asap.

**prod2vec**

[prod2vec](https://github.com/richjdowney/prod2vec) this sample project from Richard Downey contains a pipeline, orchestrated with Airflow, for training product vectors (prod2vec) with Amazon Sagemaker and the output of the pipeline is a set of trained product vectors that can be utilised in further modelling or analysis. This  makes it possible to identify the 'most similar' items to a given item. 

![arch](https://github.com/richjdowney/prod2vec/raw/master/Img/prod2vec_infrastructure.PNG)

**stelligent-u**

[stelligent-u](https://github.com/stelligent/stelligent-u) this project is the Stelligent University, and the repo includes a series of learning modules designed to give cloud engineers practical experience working with AWS and related technologies. Whilst this is intended for Stelligent associate engineers, you can take a look at these modules and probably learn a thing or two. I have just gone throw one of the sections and they are super nice and easy to follow. Rather than being a follow the instructions kind of workflow, it sets you tasks which you have to figure out. I prefer this approach myself as I learn way more that way. The folks at Stelligent have also written this post, [Open Sourcing Our DevOps Training Platform: Stelligent U](https://stelligent.com/2020/10/27/open-sourcing-our-devops-training-platform-stelligent-u/) and I can't say enough how I love this approach. Bravo Stelligent, this is my post of the week.

**sleemo**

[sleemo](https://github.com/twkiiim/sleemo) is a serverless GraphQL framework powered by AWS AppSync Direct Lambda Resolver. It is very much in the early phases, so Alpha release. Maintainer Taewoo Kim has put together this blog post, [Sleemo – A new way to develop serverless GraphQL backend using AWS AppSync](https://dev.classmethod.jp/articles/sleemo-introduction/) to help you understand why he created it and how to get going.

**aws-serverless-data-lake-framework**

[aws-serverless-data-lake-framework](https://github.com/awslabs/aws-serverless-data-lake-framework) this open sourced solution, "The Serverless Data Lake Framework (SDLF)" is a collection of reusable artefacts aimed at accelerating the delivery of enterprise data lakes on AWS, shortening the deployment time to production from several months to a few weeks. This is an Enterprise-grade, production-hardened, serverless data lake on AWS. This is what it looks like.

![arch](https://sdlf.readthedocs.io/en/latest/_images/sdlf-architecture.png)

Praful Kava and Changbin Gong have written up a companion blog post, [AWS serverless data analytics pipeline reference architecture
](https://aws.amazon.com/blogs/big-data/aws-serverless-data-analytics-pipeline-reference-architecture/) that dives deep into the different layers of the logical architecture as well as the specific individual components.

### AWS open source posts

**eRPC**

[Containerize and deploy a gRPC application on AWS Fargate](https://aws.amazon.com/blogs/opensource/containerize-and-deploy-a-grpc-application-on-aws-fargate/) great post from Theo Salvo around how to run gRPC application on AWS. gRPC, a high-performance, open source universal RPC framework, which is increasingly being looked at by customers who want to standardize their communication between services developed by distributed development teams. Theo walks you using a real example from the gRPC GitHub repository and show you how you can get started.

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2020/10/20/salvot_Containerizing-gRPC-Fargate_f1.png)

**AWS Nitro Enclaves**

[AWS Nitro Enclaves – Isolated EC2 Environments to Process Confidential Data](https://aws.amazon.com/blogs/aws/aws-nitro-enclaves-isolated-ec2-environments-to-process-confidential-data/) Jeff Barr's post announces the launch of AWS Nitro Enclaves, which provide customers running Linux on Nitro based instance types the ability to carve out an isolated environment by partitioning the CPU and memory of a single “parent” EC2 instance, protects highly sensitive data against other users or applications that are running on the same instance and is provably secure. The concept of attestation is a process that allows you to be certain that the image, operating system, and application code running in an enclave has not been inadvertently modified or tampered with in any way.

This environment is not accessible to other applications, users, or processes running on the parent EC2 instance with all data flowing into and out of an enclave moves across a local virtual socket (vsock) connection that terminates on the EC2 instance. There is a lot of detail to take in, so check out the full post and then you can also learn more by heading over to the GitHub repository and reviewing the [Nitro Enclaves CLI](https://github.com/aws/aws-nitro-enclaves-cli), the [AWS Certificate Manager for Nitro Enclaves](https://github.com/aws/aws-nitro-enclaves-acm) and having a look at some of the [sample applications](https://github.com/aws/aws-nitro-enclaves-samples).

**Open Distro for Elasticsearch**

This week we have a couple of great Open Distro for Elasticsearch (ODES) posts, as well as details of the community meet-up (See the Events section for that). First up is Kyle Davis, with a post [Using fine grained access control for search](https://opendistro.github.io/for-elasticsearch/blog/technical-posts/2020/10/fine-grained-access-control-for-search/) covering the extensive access control capabilities that are built right into ODES, and Kyle explores these capabilities in this post and walks you through how you can use them in building your own secure and locked down dashboards.

![arch](https://opendistro.github.io/for-elasticsearch/assets/media/blog-images/fgac-fields.png)

The second post a general announcement post, [Open Distro for Elasticsearch 1.11.0 is now available](https://opendistro.github.io/for-elasticsearch/blog/odfe-updates/2020/10/odfe-1.11.0-released/) where Viraj Phanse covers the key features of this release. The release has some new features (including a new pipe-based query syntax, high cardinality data support for Anomaly Detection, fine-grained access control support for Alerting and Anomaly Detection, SQL window functions, custom scoring in k-NN, and a new notebook reporting feature) and now includes version 7.9.1 of open source Elasticsearch and Kibana. Read for more in depth coverage and how and where to go to get started.

**AWS CDK**

[Building, bundling, and deploying applications with the AWS CDK](https://aws.amazon.com/blogs/devops/building-apps-with-aws-cdk/) Cory Hall takes a look at how you can easily compile your backend and front-end applications using the AWS CDK, building on an earlier blog post that shows you how to create CDK Pipelines to deploy a sample application, using build commands to compile and build your application package. It dives deeper in how to perform these build commands as part of your AWS CDK build process by using the native AWS CDK bundling functionality. You can check out the code in this post available [here](https://github.com/aws-samples/cdk-build-bundle-deploy-example).

[Rapid and flexible Infrastructure as Code using the AWS CDK with AWS Solutions Constructs](https://aws.amazon.com/blogs/devops/rapid-flexible-infrastructure-with-solutions-constructs-cdk/) Biff Gaut takes a look at AWS Solutions Constructs, a library of common service patterns built on top of the AWS CDK. These multi-service patterns allow you to deploy multiple resources with a single object, resources that follow best practices by default and allow you to create complex and complete architectures in a fraction of the time with very little code.

![diagram](https://d2908q01vomqb2.cloudfront.net/7719a1c782a1ba91c031a682a0a2f8658209adbf/2020/10/28/Comparison.jpg)

**CDK Weekly**

Also a reminder if you have not already done so to subscribe to Sebastian Korfmann's CDK Weekly newsletter. He sent the latest edition yesterday and it is packed with great content. Check it out [here](https://www.cdkweekly.com) and thanks Sebastian for this amazing resource.

**Hugo and AWS Amplify Console**

[Agile website delivery with Hugo and AWS Amplify](https://aws.amazon.com/blogs/devops/agile-website-delivery-with-hugo-and-aws-amplify/) Nigel Harris shows how you can rapidly configure and deploy a website using Hugo, AWS CodeCommit for source code control, and AWS Amplify to implement a source code-controlled, automated deployment process. For those unfamiliar with Hugo, it is an open source project that take source content in the form of Markdown files, provides a template engine that provides a flexible way for you to change the look and feel of your web site and can output your site in multiple languages and formats (including ebook formats). When combining Hugo with Amplify Console, you can rapidly deploy websites in minutes with features such as friendly URLS, environments matched to code branches, and encryption (SSL).

**AWS RoboMaker**

[Testing map generation at scale with 3D worlds from AWS WorldForge](https://aws.amazon.com/blogs/robotics/testing-map-generation-worldforge-simulation/) from Vamshi Konduri takes a look at AWS WorldForge. Developing and building Robots has been made easier by the adoption of modern application techniques, specifically how you can now run tests in simulated environments before your robots have even been built. Within ROS, Gazebo provides worlds in which you run those simulations. With AWS WorldForge, you can now dynamically and easily create more worlds to run those simulations on. Robotics developers can now test core algorithms, by setting up their applications to work with the WorldForge worlds within a couple of quick API calls!

![worlds](https://d2908q01vomqb2.cloudfront.net/a9334987ece78b6fe8bf130ef00b74847c1d3da6/2020/10/27/Flooring-plans.jpg)

Through a wizard in the console, you can say; build a world with 1 bathroom, 2 bedrooms, a living room and a kitchen. Then you can set bounds to the sizes of those rooms and a number of variations. You can take the existing worlds provided in AWS WorldForge and edit them to change some of the models used within those worlds to more closely match what you need to. AWS WorldForge will then automatically generate N number of worlds for you following that criteria. The output can be used in any Gazebo simulation.

Vamshi walks you through this is detail and provides a nice walkthrough. Whether you want to do those simulations within AWS RoboMaker or your own ROS environment, take a look at AWS WorldForge.

**Shibboleth**

[Enabling Identity Federation with Shibboleth and Amazon AppStream 2.0](https://aws.amazon.com/blogs/desktop-and-application-streaming/enabling-identity-federation-with-shibboleth-and-amazon-appstream-2-0/) Dzung Nguyen and Greg LaVigne show you how to configure Shibboleth for Security Assertion Markup Language 2.0 (SAML 2.0) identity federation with Amazon AppStream 2.0. Shibboleth is an old friend and I have used it many times in the past. For those unfamiliar, Shibboleth is an open-source project that provides single sign-on capabilities and identity federation solution used by research and education communities worldwide. In this post Dzung and Greg walk through configuring a Shibboleth identity provider to enable SAML 2.0 federation to an AppStream 2.0 stack.

![arch](https://d2908q01vomqb2.cloudfront.net/827bfc458708f0b442009c9c9836f7e4b65557fb/2020/10/26/diagram-1024x641.png)

**Deep Java Library**

A couple of posts this week on the Deep Java Library.

First up, [Video streaming and deep learning: Using Amazon Kinesis Video Streams with Deep Java Library](https://aws.amazon.com/blogs/machine-learning/video-streaming-and-deep-learning-using-amazon-kinesis-video-streams-with-deep-java-library/) Zach Kimberg and Frank Liu put their heads together and walk you through running an object detection model against a Kinesis video stream using the Deep Java Library. Deep Java Library (DJL) is an open-source deep learning framework for Java that I have covered in previous episodes of this newsletter (including last week!). It sits on top of native engines, so you can train entirely in DJL while using different engines on the backend, such as PyTorch and Apache MXNet. It can also import and run models built using Tensorflow, Keras, and PyTorch. DJL can bridge the ease of Kinesis Video Streams with the power of deep learning for your own video analytics application. 

The full project and instructions to run it are available in the DJL [demo repository](https://github.com/aws-samples/djl-demo/tree/master/aws/aws-kinesis-video-streams).

Following that we have Keerthan Vasist has put together this tutorial, [Deep Learning in Java](https://towardsdatascience.com/deep-learning-in-java-d9b54ae1423a) demonstrating the training capabilities of DJL by training a simple model on the popular MNIST dataset. From setting up your project to how you prepare the data and then finally kick off training, if you are looking for a getting started guide check this out. Keerthan also provides a GitHub repository with all the code used in this tutorial.

**H2O**

[Training and serving H2O models using Amazon SageMaker](https://aws.amazon.com/blogs/machine-learning/training-and-serving-h2o-models-using-amazon-sagemaker/) Anil Sener explains how to use Amazon SageMaker to train and serve models for an H2O framework in a production-scale design pattern. H2O was founded by H2O.ai, an AWS Partner Network (APN) Advanced Partner and the H2O framework supports three type of model artefacts which are covered in the post: Binary Models, Plain Old Java Object (POJO) and Model Object, Optimised (MOJO). The post goes on to talk about the high level design patterns and then how you could adapt these design patterns and artefacts to other ML use cases.  Anil provides further reading if you want to know more about H2O as well as all the source code from the post.

![h2o](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2020/10/26/1-SolutionArchitecture-1.jpg)

**Fluentd and Fluent Bit**

[How to set Fluentd and Fluent Bit input parameters in FireLens](https://aws.amazon.com/blogs/containers/how-to-set-fluentd-and-fluent-bit-input-parameters-in-firelens/) Ben Anscombe, DevOps Engineer at Space Ape Games and Wesley Pettit from AWS share this tutorial on how to configure Fluentd and Fluent Bit in FireLens. FireLens makes it easy for Amazon ECS customers to send and process logs using standard open source logging tools, Fluentd and Fluent Bit. In this quick post, read more about how Space Ape Games are using this to send logging data and how FireLens makes it easier for them to manage this.

**Athena Federated Query**

[Extracting and joining data from multiple data sources with Athena Federated Query](https://aws.amazon.com/blogs/big-data/extracting-and-joining-data-from-multiple-data-sources-with-athena-federated-query/) Saurabh Bhutyani and Amir Basirat collaborate on the first in a series of posts that will highlight how to configure Athena Federated Query connectors and use them to run federated queries for data residing in a number of different databases. Athena Federated Query is an [open source SDK](https://github.com/awslabs/aws-athena-query-federation) that enables you to customise Amazon Athena to integrate with new data sources, proprietary data formats, or build in new user defined functions by writing your own data connectors. These run on AWS Lambda, and the SDK provides sample projects to get you started. 

![arch](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2020/10/26/extracting-and-joining-data-4.jpg)

In this post Saurabh anmd Amir show you how to create multiple different connectors and run federated queries against multiple data sources. Watch out for future posts which I will cover in my newsletter.

**Open Distro for Telemetry**

A couple of posts last week following on from the recent preview announcement of Open Distro for Telemetry. OpenTelemetry is a community effort to simplify observability instrumentation for all. As a committed, active member of that community, AWS follows an upstream-first approach where all our enhancements are first contributed upstream. Our distribution is then built using the upstream code. 

First up we have  Nizar Tyrewalla with a post, [Distributed Tracing using AWS Distro for OpenTelemetry](https://aws.amazon.com/blogs/mt/distributed-tracing-aws-distro-for-opentelemetry/) which provides a walk through on how to use the OpenTelemetry Java auto-instrumentation agent to collect trace performance data from applications without having to re-instrument the applications. The post shows you the steps of how to instrument a sample application in Java and collect traces using OpenTelemetry for AWS X-Ray.

![xray](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2020/10/26/image2-1.png)

Following Nizar we have Min Xia, Shaocheng Wang, and Ying Wang who write, [Monitoring application health and performance with AWS Distro for OpenTelemetry](https://aws.amazon.com/blogs/opensource/monitoring-application-health-and-performance-with-aws-distro-for-opentelemetry/) that shows you how to send application metrics to CloudWatch with AWS Distro for OpenTelemetry.

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2020/10/22/aws-otel-metric-blog.jpg)

### Partner spotlight

**Cost optimisation**

[How Taloflow saved 60% by moving their data pipeline to AWS Fargate Spot](https://aws.amazon.com/blogs/containers/how-taloflow-saved-60-by-moving-their-data-pipeline-to-aws-fargate-spot/) Todd Kesselman of Taloflow (a company focused on cloud cost optimization, cloud cost accounting, and explaining the relationship between cloud costs and business metrics) walk their walk and show how they were able to reduce the cost of running their data pipelines that comprised of many open source tools such as Apache Flink and Apache Kafka. This is a great case study of how they optimised including change or architecture and using open source tools such as Kogito for scheduling. This post is well worth a read.

**GraphQL**

[Monitoring and Tracing GraphQL AWS AppSync Applications](https://epsagon.com/observability/tracing-aws-appsync/) from Gal Bashan at Epsagon writes about how you can approach the monitoring and tracing of AWS AppSync APIs that serve content from multiple data sources. After a quick intro into GraphQL and AWS AppSync, the post shows how you can use AWS X-Ray and AWS CloudWatch to help with monitoring and tracing.

**HashiCorp Consul**

[HashiCorp EKS Consul on AWS](https://aws.amazon.com/quickstart/architecture/eks-consul/) HashiCorp Consul is a tool that provides cloud networking automation by using a central shared registry for service-based networking, and in this link you will find an AWS Quick Start that helps you deploy a flexible, scalable AWS Cloud environment on Amazon Elastic Kubernetes Service (Amazon EKS). It uses HashiCorp Consul Helm to launch HashiCorp Consul into the configuration of your choice. Source code and all deployment details are provided in this Quick Start.

![arch](https://d1.awsstatic.com/partner-network/QuickStart/datasheets/hashicorp-eks-consul-architecture-diagram.76ae03f40dbdc5b7ef50ff653746369533195e97.png)

### Case Studies and Industries

**Kubernetes**

“In this world, nothing is certain except death, taxes and Kubernetes”

[TurboTax moves to Kubernetes: An Intuit journey — Part 1](https://medium.com/intuit-engineering/turbotax-moves-to-kubernetes-an-intuit-journey-part-1-aa861c061a11) and [TurboTax moves to Kubernetes: An Intuit journey — Part 2](https://medium.com/intuit-engineering/turbotax-moves-to-kubernetes-an-intuit-journey-part-2-f5217772fbb6) Anusha Ragunathan, Shrinand Javadekar, Corey Caverly, Jonathan Nevelson, and Rene Martin collaborate on this two part post that shares the background and approach Intuit took when architecting and moving to Kubernetes. Part one looks at the planning and design of the infrastructure, which is followed by part two which dives into some of the challenges the team faced, how they solved those and the lessons learned. A fascinating read. With KubeCon around the corner, you will find Intuit participating so you may have a change to ask them more about their journey.

**Open Data**

[DRAGEN reanalysis of the 1000 Genomes Dataset now available on the Registry of Open Data](https://aws.amazon.com/blogs/industries/dragen-reanalysis-of-the-1000-genomes-dataset-now-available-on-the-registry-of-open-data/) this guest post from Bryan Lajoie, Bioinformatics Scientist at Illumina Inc. introduces the Illumina Dynamic Read Analysis for GENomics (DRAGEN) Bio-IT platform. It combines hardware and software solutions including field-programmable gate array (FPGA) accelerated algorithms that helped it set a Guinness World Record for the fastest analysis of 1000 whole human genome. An international effort kicked of in 2008 called The 1000 Genome Project amassed a large dataset that can be used by researchers across the world. The post looks at the dataset, the methods to generate the data, and how you can quickly get started.

![graph](https://d2908q01vomqb2.cloudfront.net/c5b76da3e608d34edb07244cd9b875ee86906328/2020/10/22/Bar-plot-demonstrating-DRAGEN-run-time.png)

**COVID 19**

[Introducing the COVID-19 Simulator and Machine Learning Toolkit for Predicting COVID-19 Spread](https://aws.amazon.com/blogs/machine-learning/introducing-the-covid-19-simulator-and-machine-learning-toolkit-for-predicting-covid-19-spread/) Tomal Deb, Atanu Roy, Sahika Genc, Nathaniel Slater, Sunil Mallya, Dr. Taha A. Kass-Hout, and Vinay Hanumaiah talk about the open-sourcing of a toolset for researchers and data scientists to better model and understand the progression of COVID-19 in a given community over time. This toolset is comprised of a disease progression simulator and several machine learning (ML) models to test the impact of various interventions. Read to find out more including how to get up and running with the project.

![covid19](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2020/10/30/1-Diagram_Resized.jpg) 

### Video of the week

**cdk8s**

This week Paavan Mistry explores the CDK for Kubernetes, an open-source project that lets you define Kubernetes applications and reusable components using familiar programming languages, and generates standard Kubernetes YAML data, so you can use it with any Kubernetes cluster running anywhere, including on-premises and the cloud.

{% youtube AkPsCnEgWbY %}

### Latest blog posts

**Apache Flink**

[Stateful Functions Internals: Behind the scenes of Stateful Serverless](https://flink.apache.org/news/2020/10/13/stateful-serverless-internals.html) this deep dive from [Tzu-Li (Gordon) Tai](https://twitter.com/tzulitai), covering the internals of the 
Stateful Functions (StateFun) runtimes, a feature that simplifies the building of distributed stateful applications. The blog post features a demo application which is deployed on AWS and the stateful functions are deploy on AWS Lambda.

![arch](https://flink.apache.org/img/blog/2020-10-13-stateful-serverless-internals/aws-deployment.png)

**Presto on Kubernetes**

[Running Presto on Kubernetes With Ahana Cloud and AWS EKS](https://dzone.com/articles/running-presto-kubernetes-ahana-aws) Dipti Borkar provides an in-depth post on how Ahana Cloud have built their Presto as a service using Kubernetes, specifically on Amazon EKS. If you are looking for a good overview post on Presto or what Ahana Cloud is, then Dipti's post is just what you were looking for.

![arch](https://dzone.com/storage/temp/14082587-screen-shot-2020-10-23-at-121332-pm.png)

**AWS Nitro Enclaves**

[ACM for Nitro Enclaves - It's a Big Deal](https://www.sentiatechblog.com/acm-for-nitro-enclaves-its-a-big-deal) and [ACM for Nitro Enclaves - How Secure Are They?](https://www.sentiatechblog.com/acm-for-nitro-enclaves-how-secure-are-they) is a two part blog post from Luc Van Donkersgoed that takes a look and dives deep into AWS Nitro Enclaves and then explores in more detail how this can help you build provably secure environments for your applications. This is a must read post this week.

**.NET Core**

[AWS Open Sources Tool for Porting .NET Framework Apps to .NET Core](https://visualstudiomagazine.com/articles/2020/10/21/aws-net-porting-tool.aspx) David Ramel over at Visual Studio Magazine shares his views on the open sourcing a couple of weeks ago of the Porting Assistance for .NET.

### Quick updates

**Apache TinkerPop**

Amazon Neptune now supports Apache TinkerPop 3.4.8 in the latest engine release, 1.0.4.0, improving the development experience for Gremlin users. Engine release 1.0.4.0 is the default for newly created Neptune clusters. Apache TinkerPop 3.4.8 introduces new features and improvements, such as the elementMap() step and an improved behavior for working with Map instances. Upgrading your client drivers to TinkerPop 3.4.8 does not require any changes to your Gremlin code. 

To learn more about the changes made in Apache TinkerPop 3.4.8, please visit the [TinkerPop GitHub repository](https://github.com/apache/tinkerpop) and view the [changelog](https://github.com/apache/tinkerpop/blob/3.4.8/CHANGELOG.asciidoc).

**Kubernetes**

Amazon Elastic Container Service for Kubernetes (EKS) clusters running in standard AWS regions are now compliant with the Federal Risk and Authorization Management Program (FedRAMP) Moderate baseline.  With FedRAMP-Moderate compliance, customers that operate under FedRAMP guidelines can use Amazon EKS to run their Kubernetes clusters in US East (Virginia), US East (Ohio), US West (Oregon), and US West (N. California) regions. The security and compliance of Amazon EKS is assessed as part of multiple AWS compliance programs. In addition to FedRAMP moderate baseline, Amazon EKS is compliant with SOC, PCI, ISO, IRAP, C5, K-ISMS, ENS High, OSPAR, HITRUST CSF, and is a HIPAA eligible service.  

**AWS Copilot**

Today, the AWS Copilot CLI for Amazon Elastic Container Service (Amazon ECS) launched version 0.5.0. Starting with this release, you can deploy applications or jobs that need to run only on a particular schedule. AWS Copilot has built in timeouts and retries to provide more flexibility for how your scheduled jobs run. AWS Copilot will also deploy all the required infrastructure and settings, while you just provide the application and the schedule to be run. This allows you to focus on development instead of manually setting up rules and infrastructure to ensure your scheduled jobs run when needed. Additionally, you can now specify a container image name in your manifest and AWS Copilot will start containers based on that image and deploy the underlying infrastructure for you. You no longer need to have a Dockerfile and code to deploy, and can deploy and manage pre-built containers within AWS Copilot. 

Read the full release notes [here](https://github.com/aws/copilot-cli/releases/tag/v0.5.0).

**Elasticsearch**

Amazon Elasticsearch Service now supports open source Elasticsearch 7.8 and its corresponding version of Kibana. This minor release includes bug fixes and enhancements. This release includes popular open-source analyzers for Thai (Thaichub2), Chinese (IK Analyzer) and Vietnamese (Vietnamese Analysis plugin) language available under Apache-2.0 License. We now also support Open and Close API for Elasticsearch version 7.4 and above. With the close index API, you can close an open index. All write and search requests to the closed index are blocked. While the closed index has significantly lower overhead on the domain, they still occupy disk-space. A closed index can be opened using the open index API. Amazon Elasticsearch Service domains running Elasticsearch 7.8 include support for recently released features like Learning to Rank plugin, HTTP compression, Cosine Similarity search, and Audit Logs.

Amazon Elasticsearch Service now natively supports using Security Assertion Markup Language (SAML) to offer single sign-on (SSO) for Kibana. SAML authentication for Kibana enables users to integrate directly with third-party identity providers (IDP) such as Okta, Ping Identity, OneLogin, Auth0, Active Directory Federation Services (ADFS) and Azure Active Directory. With this feature, your users can leverage their existing usernames and passwords to log in to Kibana, and roles from your IDP can be used for controlling privileges in Elasticsearch and Kibana, including what operations they can perform and what data they can search and visualize.

**Linux**

AWS Systems Manager Patch Manager now includes common vulnerability identifiers (CVE ID) in the description of missing patches identified in your fleet, across multiple Linux platforms. CVE IDs help you identify security notices applicable to vulnerabilities within your fleet and recommended patches. You can use Amazon Inspector to conduct a detailed scan for CVE in your fleet. Previously, you had to query Change Calendar to determine whether change are allowed or blocked at a given time. With this release, you can trigger actions such as AWS Lambda, Systems Manager RunCommand task after the state of the Change Calendar has changed. For example, you can execute a RunCommand task to patch your instances after the Change Calendar state changes to open. To get started, visit AWS CloudWatch console to create an event rule with service as EC2 Simple Systems Manager and Event Type Change Calendar.

**Amazon Corretto**

Today Amazon announced quarterly updates for Amazon Corretto 8, Amazon Corretto 11, and Amazon Corretto 15. This release also includes Corretto 8 support for TLS1.3, Corretto 11 ARM64 updates and Corretto 11 general availability of the Shenandoah GC (Garbage Collector). Amazon Corretto is a no-cost, multi-platform, production-ready distribution of OpenJDK.


### Events for your diary

Check out these events this week.

**Open Distro for Elasticsearch - Community Meeting**
**November 2nd, 10:00am PST, 5:00PM GMT**

There is always a full agenda for this biweekly community meeting. This weeks topics will include Kibana Reports & Notebooks Piped Processing Language, High Cardinality Anomaly Detection and as always, they will go over the Open Distro for Elasticsearch roadmap and leave some time for questions and answers.

Check out [here](https://opendistro.github.io/for-elasticsearch/blog/meetings/2020/10/community-meeting-early-nov/) for details.

**OpenShift on AWS**
**Nov 10, 2020 6:00 PM - 7:00 PM GMT**

Mayur Shetty will discuss the benefits of Red Hat OpenShift 4.5 and all the consumption options available to customers on AWS.

Register [here](https://register.gotowebinar.com/register/7154011299129383181?source=Socialhttps://attendee.gotowebinar.com/register/7154011299129383181?source=Social).

**Unifying Data Pipelines and Machine Learning with Apache Spark™ and Amazon SageMaker**
**11/10/2020 9:00am CST**

Databricks and Slalom bring you this virtual event where you will:

* Learn how to build highly scalable and reliable pipelines for analytics
* Deeper insight into Apache Spark and Databricks, including the latest updates with Delta Lake
* Train a model against data and learn best practices for working with ML frameworks (i.e. - TensorFlow, XGBoost, Scikit-Learn, etc.)
* Learn about MLflow to track experiments, share projects and deploy models in the cloud with Amazon SageMaker

Get more details and register [here](https://events.databricks.com/machinelearningdevday1110).

**AWS Container Day: Kubernetes Edition**
**November 17th, 10:00am to 6:00pm EST**

Join us for AWS Container Day, a fully live, virtual day of sessions all about Amazon EKS and Kubernetes at AWS, hosted by Containers from the Couch. At this Day Zero KubeCon event, the AWS Kubernetes team will be discussing new launches, demoing products and features, covering best practices, and answering your question live on Twitch.

Register [here](https://awscontainerdayk8s.splashthat.com/#rsvp).

**Virtual ROS-Industrial Conference 2020**
**December 15 - 16, 2020**

The 8th edition of ROS-Industrial Conference will be held as a virtual event. It is not only the annual community meeting for the European ROS-Industrial community but this years event is also the final event of the H2020 ROSIN project. The conference gives you the chance to see the newest technical developments and to meet people and companies, which are active in the ROS community.

Learn more and sign up [here](https://rosindustrial.org/rosindustrial-conference-2020).

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen).

### Your feedback matters!

I have put together a short feedback survey, which I would ask you to take - it will take no more than 2 minutes. You can access [here](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn). Many thanks!

[Take the survey](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn)
26th