---
title: 'AWS open source news and updates No. 29'
date: '2020-07-20'
tags : [ oss-newsletter ]
---
## July 20th - Instalment #29

Week No.29, and another epic edition packed with lots of great projects and posts, as well as a larger than normal number of case studies this week. Pick of the bunch from me (always hard) is the walkthrough of the CDK Patterns from Matt, the customer case studies and the finala and inframap projects. Remember, if you have a project you want me to mention or talk about, then please reach out. I do provide prizes for the ones that I particularly like, so there is also that incentive too.

**open source builders**

Super excited this week about the Open source builder videos and blog posts that we released late last week. It was a lot of fun talking with Olaf, Alex and Liz, all of whom have featured in past episodes of this newsletter, either because of open source projects they are behind or open source products they have launched.

[Part one](https://aws.amazon.com/blogs/opensource/open-source-builders-getting-started/) is all about how they got started in open source, and we follow that up in [part two](https://aws.amazon.com/blogs/opensource/open-source-builders-lessons-learned/) with lessons learnt. Now I have to apologise that there is no video of Liz and this is entirely my fault. During the recording of these sessions, I had a complete fail and whilst I recorded the video, there was no audio. Very sad, as it was an epic session.

{% youtube b6arpt3l7yM %}

If you want to take part then please contact me as I am currently organising recording of the next batch.

### Event for your diary

There is still time to sign up to these events that I shared last week.

**Spack Tutorial on AWS**
**July 28 - July 29,  at 3PM BST (4:00PM CEST, 7:00am PST)**

Spack is an open source package manager that simplifies building, installing, customizing, and sharing HPC software stacks. In recent years, Its adoption has grown rapidly: by end-users, by HPC developers, and by the world’s largest HPC centers. Spack is also used to build reproducible scientific workflows in AWS.

This event is broadly targeted at HPC users, developers, and user support teams. There’s something for everyone, from academia to national labs to industry.

**Databricks machine learning workshop**
**30th July, at 3PM BST (4:00PM CEST, 7:00am PST)**

A date and time for your diary, on **30th July, at 3PM BST (9:00am CDT)** Databricks are running a workshop on [Unifying Data Pipelines and Machine Learning with Apache Spark™ and Amazon SageMaker](https://events.databricks.com/awsdatabricksmldevday730?utm_source=bambu&utm_medium=social&utm_campaign=advocacy&blaid=668173). This event will cover:

* building scalable and reliable pipelines for analytics
* a look at Apache Spark and Databricks
* training  a model against data and learn best practices for working with ML frameworks (i.e. - TensorFlow, XGBoost, Scikit-Learn, etc.)
* see how to tack experiments in MLflow, share projects and deploy models in the cloud with Amazon SageMaker



### Your feedback matters!

I have put together a short feedback survey, which I would ask you to take - it will take no more than 2 minutes. You can access [here](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn). Many thanks!

[Take the survey](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn)

### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to Łukasz Mitka, Kong Zhao, Farid Gurbanov, Daniel Schroeder, [Joel Lutman](https://twitter.com/JoelLutman),  [cycloidio](https://www.cycloid.io/), the Keiko project, Moheeb Zara, Zerobase Foundation, Ashwin Raghuraman, Pedro C. González, Akash Deep Verma, Dipta S. Bhattacharya, Nikhil Khokhar, Derek Tan, Savin Goya, Jeremy Wallace, Chris Burns, Qingwei Li, David Ping, Lauren Yu, Vaibhav Goel, Raja Hafiz Affandi, Sivasamy Subramaniam, Ismail Shaik, Kiran Moka, Pratip Bagchi, Saleha Haider, Dr Tara Madhyastha, Ahmed Elzeftawi, Sebastian Pop, Ben Smith, Rico Huijbers, Chris Fife, Anubhav Mishra, Matt Coulter, Naveen M, Anthony Alford, [Kyle Lee](https://twitter.com/kilo_loco), Cyril Tovena, Liz Rice, Aliza Carpio, [Emmanuel Awotunde](https://twitter.com/olaoluwa_98), [Damian Sosnowski](https://twitter.com/sosnowsd) and SimilarWeb.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

**finala**

[finala](https://github.com/similarweb/finala) - this project from [SimilarWeb](https://github.com/similarweb) is a resource cloud scanner that analyzes, discloses, and notifies about wasteful and unused resources in your company's infrastructure so that you can save money and take action on any unused resources (for example, to improve security)

**inframap**

[inframap](https://github.com/cycloidio/inframap) - this project from [cycloidio](https://www.cycloid.io/) is a neat tool that helps you generate maps, using your Terraform state of HCL files as input. Very useful for trying to make sense of an existing environment, creating 'living' documentation and more.

**aws-glue-sbt-quickstart**

[aws-glue-sbt-quickstart](https://github.com/jhole89/aws-glue-sbt-quickstart) - project from [Joel Lutman](https://twitter.com/JoelLutman) provides a quickstart for new AWS Glue projects using Scala. Using SBT and the AWS Glue SDK, this repo enables local development and unit testing of AWS Glue scripts.

**serverless-data-pipelines-demo**

[serverless-data-pipelines-demo](https://github.com/jhole89/serverless-data-pipelines-demo) - another project from Joel, this time one that demonstrates how you can use Serverless AWS services to construct a modular big data pipeline. It builds both the architecture required to build a standard enterprise datalake and deploys application code for performing ETL. Check out [Joel Lutman](https://twitter.com/JoelLutman) blog, might be the best thing you do today -> https://manta-innovations.co.uk/blog

**iam-manager**

[iam-manager](https://github.com/keikoproj/iam-manager) - is am open source provide that provides a k8s CRD (Custom Resource Definition) to manage AWS IAM roles as Kubernetes resources. Check out the blog post below for more details.

**EC2 Spot Instances integration roadmap**

[EC2 Spot Instances integrations roadmap](https://github.com/aws/ec2-spot-instances-integrations-roadmap) - this project that was announced last week is the public roadmap for Amazon EC2 Spot Instances integrations. This is an experimental public roadmap for Amazon EC2 Spot Instances integrations with open source software and frameworks. This repository contains information about current activities and allows all AWS customers to give direct feedback.

**aws-serverless-pyportal-lock**

[aws-serverless-pyportal-lock](https://github.com/aws-samples/aws-serverless-pyportal-lock) -  another project and post from Moheeb Zara, this time showing you how to build an electronic keypad lock system using a basic relay circuit and a microcontroller. The system is managed by a serverless backend API deployed using the AWS Serverless Application Repository. The backend uses API Gateway to provide a REST API for Lambda functions that handle fetching lock state, updating lock state, and sending a random four-digit code via SMS using Amazon Pinpoint. Language consistency is achieved by using CircuitPython on the PyPortal and Python 3.8 in the Lambda function code. Check out the walkthrough post that accompanies this project - [Building an electronic security lock using serverless](https://aws.amazon.com/blogs/compute/building-an-electronic-security-lock-using-serverless/)

**bump-cdk**

[bump-cdk](https://github.com/cdk-tools/bump-cdk/) - this open source project helps you with a common issue when working with AWS CDK, which is version mismatch and the way CDK's modules interface together requires them to always be on the same version. This introduces maintenance overhead by forcing you to always have your CDK dependencies on the same version. Use this tool to have those dependencies upgraded and pinned to the same version!

**iam-floyd**

[iam-floyd](https://github.com/udondan/iam-floyd) - this project from Daniel Schroeder came up over the weekend, and is an early version of this tool that is an AWS IAM policy statement generator with [fluent interface](https://en.wikipedia.org/wiki/Fluent_interface). This project will help you craft your IAM policies for your applications, and you can use this with or without AWS CDK.

**DSE Pronto**

[A New Intuit Open Source Release: DSE Pronto](https://medium.com/@SocialAC/dse-pronto-ea336bc00ee0) - this post from Aliza Carpio, Technology Evangelist at Intuit, shares a new open source project from Intuit called DSE Pronto. DSE Pronto is a framework of automation tools to help manage and deploy your DataStax Cassandra clusters in AWS. Great quote from the post:

> Ben started by releasing DSE Pronto internally at Intuit via InnerSource, and the user community has grown quickly. He hopes open sourcing will help it to grow even further.

You can find the GitHub repository [here](https://github.com/intuit/dse-pronto).

### Blog posts you should check out

**kube bench**

kube-bench is a Go application that checks whether Kubernetes is deployed securely by running the checks documented in the CIS Kubernetes Benchmark. Check out this short video from Liz Rice, VP of open source engineering at Aqua Security, on using [kube-bench](https://github.com/aquasecurity/kube-bench) on Amazon EKS.

https://www.youtube.com/watch?v=MwsUg3168YI&feature=emb_logo

Aqua Security have plenty of more videos on how to use their open source tools - [check them out here](https://www.youtube.com/c/AquaSecurityOpenSource/videos).

**ECS and Bitbucket**

[Easy Deployment Setup With Bitbucket and Amazon ECS](https://dev.to/olaoluwa98/easy-deployment-setup-with-bitbucket-and-aws-ecs-46ac) - nice walkthrough from [Emmanuel Awotunde](https://twitter.com/olaoluwa_98) that shows you how to quickly setup your Bitbucket repositories so you can deploy to Amazon ECS, deploying a simple express application to show you how it is done.

**Loki tutorial: Analysing logs on AWS EC2 with promtail**

[Loki tutorial: How to set up Promtail on AWS EC2 to find and analyze your logs](https://grafana.com/blog/2020/07/13/loki-tutorial-how-to-set-up-promtail-on-aws-ec2-to-find-and-analyze-your-logs/) - this post from Cyril Tovena is a detailed walkthrough of how to setup Loki and Promtail within your AWS environment to be able to better search your logs that your instances will produce.

[Loki](https://grafana.com/oss/loki/) is an open source horizontally-scalable, highly-available, multi-tenant log aggregation project started at Grafana Labs in 2018 and released under the Apache 2.0 License. With Loki aggregation, you can group all your logs from all your virtual machines in one place, and with its search capabilities, you can quickly find and analyze them. Promtail is an agent which ships the contents of local logs to a private Loki instance.

This tutorial explains how you can set up the Promtail agent on an AWS EC2 instance and configure it to send all its logs to a Loki instance, so you can start getting the most out of your workload.

**Amplify and IOS setup**

[Amplify iOS Project Setup](https://www.kiloloco.com/articles/002-Amplify-iOS-Project-Setup/) - this post from from [Kyle Lee](https://twitter.com/kilo_loco) walks you through his setup when developing Amplify IOS projects. The Amplify Framework is an open source project for building cloud-enabled mobile and web applications, consisting of libraries, UI components, and a CLI toolchain. You can easily add capabilities organised in to categories such as Analytics, AI/ML, APIs (GraphQL and REST), DataStore, and Storage to your mobile applications. AWS Amplify Libraries for iOS allows you to extend that model when building your IOS apps, and this walkthrough from Kyle is a great starting point if you want to get started. Make sure you check out his other posts too.

You should also check out Kyle's post on how he when [From Master to Main](https://www.kiloloco.com/articles/003-From-Master-To-Main/), where he provides you with a set of easy to follow steps on how you can change your current setup and move to Main.

**NetxJS, AWS CloudFront and Terraform**

[How to create statically generated, serverless site with NextJS, AWS CloudFront and Terraform](https://sosnowski.dev/post/static-serverless-site-with-nextjs) - this is a great walkthrough (with [source code](https://github.com/sosnowski/blog)) by [Damian Sosnowski](https://twitter.com/sosnowsd) showing how he built a statically pre-rendered site, using NextJS, and deployed it fully serverless  and adopting best practices by writing infrastructure as code (using Terraform). What is nice about this post is that it is very well written and gently eases you into each step; what you will be doing and why. Great stuff.

**ROS 2 Foxy Fitzroy**

[ROS 2 Foxy Fitzroy Release Improves Security and Tooling](https://www.infoq.com/news/2020/07/ros2-foxy-security-tooling/) - this short post from Anthony Alford summarises some of the benefits of moving to ROS 2 and specifically talks about some of the security and tooling improvements.

**ROS to ROS2**

[Porting a project from ROS1 to ROS2 — our experience](https://medium.com/husarion-blog/porting-a-project-from-ros1-to-ros2-our-experience-ef27b1748915) - this post from Łukasz Mitka at Husarion provides one of the first posts I have seen outlining the experience of migrating from ROS to ROS2. It covers what they did, highlights some of the challenges they came across and should be something you read if you are looking to do the same.

**IAM and Kubernetes**

[Managing IAM Roles as K8s Resources](https://medium.com/keikoproj/managing-iam-roles-as-k8s-resources-aa00c5c4447f), this post by Naveen M shows how to use an open source project called iam-manager (see above, in projects) that allows applications to safely and conveniently create and manage IAM roles as part of their deployment pipeline (i.e. kubectl apply) along with other Kubernetes resources. iam-manager is part of a bigger project, [Keiko](https://medium.com/keikoproj/keiko-running-kubernetes-at-scale-1178491c1440).

**CDK Patterns**

[CDK Patterns at 20! Let's Walk Through all 20 Serverless Patterns for AWS](https://dev.to/nideveloper/cdk-patterns-at-20-let-s-walk-through-all-20-serverless-patterns-for-aws-d1n) - Liberty IT's Matt Coulter takes some time to reflect and walk you through some of the patterns that are available on the cdkpatterns.com site (which I have talked about in previous episodes of this newsletter). Matt covers each pattern: what it is, what it looks like and when you should think about applying this, as well as providing alternative options. This is such a great resource, thanks Matt!  


**Security culture in open source**

[Building a culture of security in open source software development](https://dev.to/aws/building-a-culture-of-security-in-open-source-software-development-292f) - this is a blog post I released in the middle of last week where I talk about how to think about security on both the producing and consuming side of open source. How to you make sure you are setting your open source project to take security seriously, and how to ensure you manage security when you are using open source in your projects. From both ends of the spectrum, but key to ensuring you get security right is culture. 

Pleased that this has been well received, so if you missed it, you can let me know what you think.

**Realtime Security Data Lake - Reference architecture**

[Real-time Security Data Lake. Reference Architecture](https://www.linkedin.com/pulse/real-time-security-data-lake-reference-architecture-farid-gurbanov/) - this post from Farid Gurbanov is a super deep dive on building a reference architecture that you can use if you want to build a capability within your security operations teams to be able to store and perform log analysis of your applications events and logs - not just real time but for extended periods of time in the past.

![architecture](https://media-exp1.licdn.com/dms/image/C5612AQFEdnLl5htERw/article-inline_image-shrink_1500_2232/0?e=1600905600&v=beta&t=DLjTjOPy3j8KllvRbI8EN_GEJ1xTkcBWbAvAspzRbZU)

Farid breaks down each architecture component, introduces what they do, provides configuration details and then also provides cost guidance and estimates too. This has everything you need, and even if you do not implement it, you will learn a lot.


### AWS open source posts

**AWS CDK for Terraform**

[Introducing the Cloud Development Kit for Terraform (Preview)](https://aws.amazon.com/blogs/developer/introducing-the-cloud-development-kit-for-terraform-preview/) - post from Chris Fife and Anubhav Mishra that introduces the developer preview of the Cloud Development Kit for Terraform, or cdktf, that leverage two key technologies of the AWS CDK: the CDK construct programming model, and the javascript interoperability interface, or jsii. **cdktf** lets you define application infrastructure with familiar programming languages, while leveraging the hundreds of providers and thousands of module definitions provided by Terraform and the Terraform community. The CDK for Terraform preview is initially available in TypeScript and Python, with other languages planned in the future.

![architecture](https://d2908q01vomqb2.cloudfront.net/0716d9708d321ffb6a00818614779e779925365c/2020/07/14/TerraformPlatform.png)

**AWS CDK Pipelines**

[CDK Pipelines: Continuous delivery for AWS CDK applications](https://aws.amazon.com/blogs/developer/cdk-pipelines-continuous-delivery-for-aws-cdk-applications/) - this post from Rico Huijbers, he announces the Developer Preview release of CDK Pipelines. CDK Pipelines is a high-level construct library that makes it easy to set up a continuous deployment pipeline for your CDK applications, powered by AWS CodePipeline. What are pipelines? A pipeline consists of several stages, which represent logical phases of the deployment. Each stage contains one or more actions that describe what to do in that particular stage. A CDK pipeline starts with several predefined stages and actions, but you can add stages and actions to it to suit the needs of your application.

The post walks you through how to use CDK Pipelines to deploy an AWS Lambda-powered Amazon API Gateway endpoint to two different accounts and you can learn more about how Amazon development teams define application infrastructure in code and deploy it in stages across multiple AWS accounts and Regions, in the [Amazon Builders’ Library](https://aws.amazon.com/builders-library/) article, [Automating safe, hands-off deployments](https://aws.amazon.com/builders-library/automating-safe-hands-off-deployments/).

**Serverless LAMP - part 3**

[The Serverless LAMP stack part 3: Replacing the web server](https://aws.amazon.com/blogs/compute/the-serverless-lamp-stack-part-3-replacing-the-web-server) - Ben Smith provides another instalment in this series, this time focusing in on the Apache/NGNIX side of things. This series has been epic so far, and I suspect we are going to be seeing more serverless related PHP content.

![architecture](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2020/07/13/fpm-cycle.png)

**PHP on AWS Graviton2**

[Improving performance of PHP for Arm64 and impact on AWS Graviton2 based EC2 instances](https://aws.amazon.com/blogs/compute/improving-performance-of-php-for-arm64-and-impact-on-amazon-ec2-m6g-instances/) - Sebastian Pop discusses how AWS worked together with the PHP community to drive major improvements to the performance of the PHP software stack on the Graviton2-based instances. By using AWS Graviton2 based instances, the latest release of PHP-7.4 currently experiences up to 37% faster execution time compared to the previous release PHP-7.3. This significantly lowers the cost of running PHP software such as WordPress on Amazon EC2 M6g instances. This post has benchmark data that you will want to check out if you are running any meaningful PHP workloads.

**Scaling Electronic Design Automation workloads**

[Scaling EDA Workloads using Scale-Out Computing on AWS](https://aws.amazon.com/blogs/industries/scaling-eda-workloads-using-scale-out-computing-on-aws/) - Ahmed Elzeftawi's post shows you have to implement a scale out computing architecture using several open source components (Linux OS, Amazon Elasticsearch and Amazon FSx for Lustre) for this specific industrial vertical, although you can adapt this to other verticals too. You can check out the source code [here](https://awslabs.github.io/scale-out-computing-on-aws/install-soca-cluster/). This is a good example of how combining open source components and cloud can enable high scale, robust solutions to solve industry use cases.

![architecture](https://d2908q01vomqb2.cloudfront.net/c5b76da3e608d34edb07244cd9b875ee86906328/2020/07/08/AhmedBlog_Image1-1024x667.png)

**Research workflows on AWS**

[Five things to consider when moving your research workflows to AWS](https://aws.amazon.com/blogs/publicsector/five-things-consider-when-moving-research-workflows-aws) - Dr Tara Madhyastha, Ph.D writes about how research is done differently in the cloud compared to on-premises lab, and what you should be looking at when you are beginning to move computational research to the cloud. It starts with your workflows, which are well-developed sets of computer analyses that turn raw data into results that researchers can publish. Analysis methods can overlap, so workflows vary by lab and project to suit the research question. This post provide some solid guidance on what to think as you begin that migration. Key to much research is the use of HPC computing, so the post covers HPC Parallel Cluster but also talks about some of the open source workflow tools such as [NextFlow](https://github.com/nextflow-io/nextflow).

**Modernising .NET applications**

[Modernizing and containerizing a legacy MVC .NET application with Entity Framework to .NET Core with Entity Framework Core: Part 1](https://aws.amazon.com/blogs/devops/modernizing-and-containerizing-a-legacy-mvc-net-application-with-entity-framework-to-net-core-with-entity-framework-core-part-1/) - this post from Pratip Bagchi and Saleha Haider shows the process for modernizing a legacy enterprise MVC ASP.NET web application using .NET Core and convert Entity Framework to Entity Framework Core. They will post a follow up post which I will share in a future newsletter.

![workflow](https://d2908q01vomqb2.cloudfront.net/7719a1c782a1ba91c031a682a0a2f8658209adbf/2020/07/10/MIgrationBlog-FeatureImage.png)

**Migrate Azure data to Amazon S3**

[One way to migrate data from Azure Blob Storage to Amazon S3](https://aws.amazon.com/blogs/storage/one-way-to-migrate-data-from-azure-blob-storage-to-amazon-s3/) - this post from Ismail Shaik and Kiran Moka show you how you can quickly use a NodeJS package called [azure-blog-to-s3](https://github.com/bendrucker/azure-blob-to-s3) to migrate data from Azure to Amazon S3.

![storage](https://d2908q01vomqb2.cloudfront.net/e1822db470e60d090affd0956d743cb0e7cdf113/2020/07/16/Elastic-Beanstalk-based-solution-with-node-package-hosted-in-Beanstalk-environment.png)

You can use this solution to migrate data from Azure Cosmos DB, Azure Table Storage, Azure SQL, and more, to Amazon Aurora, Amazon DynamoDB, Amazon RDS for SQL Server, and more. So if this is something you are exploring, then read this and give it a go.

**X11 forwarding on Amazon EC2**

[How to enable X11 forwarding from Red Hat Enterprise Linux (RHEL), Amazon Linux, SUSE Linux, Ubuntu server to support GUI-based installations from Amazon EC2](https://aws.amazon.com/blogs/compute/how-to-enable-x11-forwarding-from-red-hat-enterprise-linux-rhel-amazon-linux-suse-linux-ubuntu-server-to-support-gui-based-installations-from-amazon-ec2/) - this post from Sivasamy Subramaniam brought back memories of running X over ssh tunnels, and in this post he shares how to enable X11 forwarding from Red Hat Enterprise Linux (RHEL), Amazon Linux, SUSE Linux, Ubuntu servers running on Amazon EC2 if you need to have access to a GUI. You might need it one day, despite most things moving to command line, very occasionally a GUI comes up so now you know how to deal with it.

**Apache Spark and Deep Java Library**

[How Amazon retail systems run machine learning predictions with Apache Spark using Deep Java Library](https://aws.amazon.com/blogs/opensource/how-amazon-retail-systems-run-machine-learning-predictions-with-apache-spark-using-deep-java-library/) - this post from Vaibhav Goel and Raja Hafiz Affandi share their experiences and talk about the key challenges we faced while building these propensity models (a model that helps improve customer experience through personalisation) and how we solved them at the Amazon scale with Apache Spark using the Deep Java Library (DJL). DJL is an open source library to build and deploy deep learning in Java, which I have covered extensively in previous newsletters. Make sure you do not miss out the conclusion of this post, and how this approach was able to significantly improve the time it took to run.

**Fine-tuning a PyTorch BERT**

[Fine-tuning a PyTorch BERT model and deploying it with Amazon Elastic Inference on Amazon SageMaker](https://aws.amazon.com/blogs/machine-learning/fine-tuning-a-pytorch-bert-model-and-deploying-it-with-amazon-elastic-inference-on-amazon-sagemaker/) - this collaboration between Qingwei Li, David Ping, and Lauren Yu demonstrates how to use Amazon SageMaker to fine-tune a PyTorch BERT model and deploy it with Elastic Inference. I have mentioned BERT, or Bidirectional Encoder Representations from Transformers, in a previous newsletter, is a technique for natural language processing (NLP) and one of the key technical innovations is the application of bidirectional training of Transformer, a popular attention model, to language modelling. The code from this post is available in the [GitHub repo](https://github.com/aws-samples/amazon-sagemaker-bert-pytorch)

**RAPID Amazon EMR**

[Improving RAPIDS XGBoost performance and reducing costs with Amazon EMR running Amazon EC2 G4 instances](https://aws.amazon.com/blogs/big-data/improving-rapids-xgboost-performance-and-reducing-costs-with-amazon-emr-running-amazon-ec2-g4-instances/) - this post Kong Zhao at NVIDIA Corporation, shows you how you can make use of accelerated GPU instances to improve the performance of Amazon EMR. Amazon EMR is the cloud big data platform for processing vast amounts of data using open-source tools such as Apache Spark, Apache Hive, Apache HBase, Apache Flink, Apache Hudi, and Presto. This post talks about RAPIDS, a project that helps with the configuration and optimisation of GPU based instances to accelerate these workloads.


**AWS JPL Open Source Rover Challenge**

[Navigating robots on Mars: Results of the AWS JPL Open Source Rover Challenge](https://aws.amazon.com/blogs/robotics/navigating-robots-on-mars-jpl-open-source-rover-challenge/) - Jeremy Wallace and Chris Burns share an update on the AWS JPL Open Source Rover Challenge, a four-month competition where participants from around the world used deep reinforcement learning to drive digital robot models on a virtual Mars landscape. Participants created autonomous navigation models for the robot and trained them in AWS RoboMaker simulation. The virtual robot used in this competition was based on the NASA-Jet Propulsion Laboratory (JPL) Open Source Rover, a build-it-yourself scaled down version of the six-wheeled rover that NASA uses on Mars.

![robot](https://d2908q01vomqb2.cloudfront.net/a9334987ece78b6fe8bf130ef00b74847c1d3da6/2020/07/13/JPL-Rover.jpg)

Read the post to find out more and hear about the winning entry.

### Customer stories and case studies

**INEOS**

[INEOS TEAM UK Accelerates Boat Design for America’s Cup Using AWS](https://aws.amazon.com/solutions/case-studies/ineos-team-uk-case-study/) - A look at how Team UK were able to use the HPC capabilities of AWS to rapidly accelerate the number of simulations they could do. Sir Ben Ainslie hailed this as a “game-changer” in their preparations for the America’s Cup. HPC uses a number of open source projects, such as[ AWS Parallel Cluster](https://github.com/aws/aws-parallelcluster), as well as AWS services including Amazon FSx for Lustre, an open source high performance filesystem.

My favourite quote from this customer, was from Nick Holroyd, Ineos Team UK’s chief designerm who said: “They say that ‘time cannot be bought’, but by working with AWS, we are able to do just that."

This was also picked up by various other sites, including [Computerweekly](https://www.computerweekly.com/news/252486048/AWS-HPC-tech-selected-to-help-Ineos-Team-UK-secure-first-British-victory-in-the-Americas-Cup) and [Yahoo](https://uk.finance.yahoo.com/news/sir-ben-ainslie-hails-game-070000096.html).
 
**Netlfix**

A lot of folk probably know about Netflix open source projects, and you may in fact use some of these. But did you know that Netflix also makes available content resources? [Check out these resources here](https://opencontent.netflix.com/?fbclid=IwAR3WNNwDoDjBlXn8_GZ9eAEBBMl-BCJwTq6OxtxTbaz8uRCVYNU1B967Els), a large selection of content with different formats that you can use to get started in your own media based projects.

[Metaflow: Netflix Machine Learning Platform with Savin Goyal](https://www.softwaredaily.com/post/5f0c276514881b000cdf585c/Metaflow-Netflix-Machine-Learning-Platform-with-Savin-Goyal) - in this podcast on the Software Daily, check out Savin Goya talk about how open source projects like Metaflow are helping Netflix overcome some of the typical challenges, and show how they integrate with AWS services and other open source projects such as Apache Airflow. Metaflow is an open source machine learning platform built on top of AWS that allows engineers at Netflix to build directed acyclic graphs (DAG) for training models, and these are then deployed to AWS as Step Functions, a serverless orchestration platform.

Be sure to check out the other podcasts available on [Software Daily](https://www.softwaredaily.com/) - one of my favourite podcasting sites.

**WeRide**

[Build a Cross-Region Hybrid Cloud Storage Gateway for AI at WeRide](https://www.alluxio.io/blog/building-a-cross-region-hybrid-cloud-storage-gateway-for-engineers-at-weride/?preview_id=9681%E2%AA%AFview_nonce=2bd3ec0a86%E2%AA%AFview=true) - In this post published on Alluxio's blog from WeRide's Derek Tan, you will see how the engineers at WeRide leverage Alluxio as a hybrid cloud data gateway for application to access public cloud storage like Amazon S3, and allows them to accelerate localised access to that data. This case study is a great post to read as you begin to think how to use the data you have in your data lakes (like Amazon S3) and make this available at the right performance and cost.

![weride](https://lh3.googleusercontent.com/G6UowA3YBNLHJhTswp_Ih-ZWmUBJwok1-3i421wb3cHAinhTENnmOQazX3mtMx0zUxjzJHqejn0XXmi6kgtZDkyf6T_Yf_4baMhR_BnbLHo6yBAmy5f2zU168oMOwycLiSq_qL52)

**Delhivery**

[Best practices from Delhivery on migrating from Apache Kafka to Amazon MSK](https://aws.amazon.com/blogs/big-data/best-practices-from-delhivery-on-migrating-from-apache-kafka-to-amazon-msk/) - guest post on the AWS Big Data blog from Akash Deep Verma, Senior Technical Architect at Delhivery, Dipta S. Bhattacharya (from AWS) and Nikhil Khokhar (from AWS). The post shows the steps Delhivery took to migrate from self-managed Apache Kafka running on Amazon Elastic Compute Cloud (Amazon EC2) to Amazon Managed Streaming for Apache Kafka (Amazon MSK), and talks about some of the reasons why they made this change. Make sure you check out the conclusion to see why this made sense for this customer.

**Public Sector: DG SANTE, DG DIGIT and DG CONNECT**

[European Convalescent Plasma Collection Platform: Data-driven initiative to fight COVID-19](https://aws.amazon.com/blogs/publicsector/european-convalescent-plasma-collection-platform-data-driven-initiative-fight-covid-19/) - this post shows how the European Convalescent Plasma Collection Platform (EU CCP) is using open source technologies and AWS to experiment with a testing environment and adopt big data technologies and data analytics skills to process data, promote open source technologies, and advance research on convalescent plasma therapy. 

![architecture](https://d2908q01vomqb2.cloudfront.net/9e6a55b6b4563e652a23be9d623ca5055c356940/2020/07/15/CCP-platform-architecture-1024x474.jpg)

**OrangeTheory Fitness**

[Delivering Video at Scale in Mobile and Web Applications with Orangetheory Fitness](https://aws.amazon.com/blogs/mobile/delivering-video-at-scale-in-mobile-and-web-applications-with-orangetheory-fitness/) - a deep dive from Ashwin Raghuraman from AWS and Pedro C. González, Enterprise Solutions Architect at Orangetheory Fitness. I mentioned this case study last week, and this week we have a closer look at this solution and how it uses some of the AWS open source technologies to help achieve agility and nimbleness so they can continue to serve their customers, through the use of a video basesd solution.

![architecture](https://d2908q01vomqb2.cloudfront.net/0a57cb53ba59c46fc4b692527a38a87c78d84028/2020/07/10/Screen-Shot-2020-07-10-at-5.54.45-PM-1024x777.png)

**Zerobase**

[Zerobase creates private, secure, and automated contact tracing using Amazon Neptune](https://aws.amazon.com/blogs/database/zerobase-creates-private-secure-and-automated-contact-tracing-using-amazon-neptune/) this is a guest post from the Zerobase Foundation. In their own words, “The Zerobase Foundation is a nonprofit organization whose mission is to build free, open-source public health technology for the good of communities around the world. Zerobase’s privacy-first contact tracing platform empowers individuals, communities, and local officials to stop the spread of COVID-19.”

The post looks at how they have approached developing their open source contact tracing application to help the fight against COVID-19. The post looks at the architecture and how this solution works.

![arch](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2020/07/13/zerobase-2.png)

Find out more by looking at the Zerobase source code repository [here](https://github.com/zerobase-io).


### Quick updates

**Amazon EKS 1.7**

Amazon Elastic Kubernetes Service (EKS) now supports Kubernetes version 1.17. Kubernetes is rapidly evolving, with frequent feature releases and bug fixes. Highlights of the Kubernetes 1.17 release include Cloud Provider Labels, ResourceQuotaScopeSelectors, TaintNodesByCondition, Finalizer protection, and CSI Topology graduating to generally available. Additionally, the Windows containers RunAsUsername feature is now in beta, allowing you to run Windows applications in a container as a different username than the default. Learn more about Kubernetes version 1.17 in the Kubernetes project release notes. 

**Amazon Athena * Apache Hudi**

Amazon Athena now supports querying the read-optimized view of an Apache Hudi dataset in your Amazon S3-based data lake.   Apache Hudi is an open-source data management framework used to simplify incremental data processing and data pipeline development. Hudi enables Amazon S3-based data lakes to comply with data privacy laws, consume real time streams and change data capture logs, reinstate late arriving data, and track change history and rollback. Apache Hudi is open-source and supports storing data on Amazon S3 in open source formats such as Apache Parquet and Apache Avro.  Data engineers use Apache Hudi support in Amazon EMR to develop data pipelines and to simplify incremental data management and data privacy use cases that require record-level insert, updates, and delete operations. With this release, customers can now run Athena queries to read the read-optimized view of a Hudi dataset. 

**Amazon Corretto**

Amazon Corretto is releasing its July quarterly critical updates. This release also includes Corretto 8 & 11 support for Alpine Linux, Corretto 8 with JFR (JDK Flight Recorder) which can be used with JMC (JDK Mission Control) built for (to support) Corretto, Corretto 11 32bit x86 for Linux and ARM64 optimizations for both Corretto 8 & 11.

**Fluent Bit supports Amazon Elasticsearch Service as a destination**

Customers using container services including Amazon Elastic Container Service (ECS), Amazon Elastic Kubernetes Services (EKS), or self-managed Kubernetes can now send their container logs to Amazon Elasticsearch Service using the Fluent Bit log router. Fluent Bit allows customers to route container logs to various AWS and partner monitoring solutions including CloudWatch, Amazon Kinesis, Datadog, Splunk, and now Amazon Elasticsearch Service.

**Amazon MQ**

Amazon MQ now supports mq.t3.micro, the next generation of micro instance, priced at 8% to 13% less than the previous generation mq.t2.micro.  

**Amazon EC2 VM Import / Export adds support for Red Hat Linux (RHEL) 8 and CentOS 8**

EC2 VM Import / Export (VMIE) now allows you to import virtual machine images with Red Hat Linux (RHEL) 8/8.1/8.2 and CentOS 8/8.1/8.2 for creating Amazon Machine Images (AMI). You can use the AMI to create Amazon EC2 instances.  

VMIE enables you to easily import virtual machine images from your existing environment to AWS and export them back to your on-premises environment. This offering allows you to leverage your existing investments in the virtual machines that you have built to meet your IT security, configuration management, and compliance requirements by converting your VM into an Amazon Machine Image, which you can use to run Amazon EC2 instances.  

### In other news

**Startups**

[Open Source Growth Benchmarks and the 20 Fastest-Growing OSS Startups](https://t.co/c0IQh8iAVR?amp=1) - in this analysis from Konstantin Vinogradov, see how to take a more analytical look at the activities in open source projects happening within GitHub and how you can begin to try and understand some of the signals, whether those signals are good or weak indicators and what it means to understanding the hot open source projects. This is probably my favourite post from this week.


**Transformation: Building and re-using open source in government**

This is a great video that provides insights into how public sector and governments are thinking about open source and how they are approaching it with regards to help address a number of concerns they care about.

https://www.youtube.com/watch?time_continue=1729&v=YPS1neFtm6Q

**Source available**

[Source Available Scorecard](https://heathermeeker.com/2018/12/15/source-available-scorecard/) post from Heather Meeker that does a deep dive in source available available licences - the catalyst for them and what the current state of play is. 

### Share your open source projects 

Do you have some content you want to share with a broader audience? We are always looking for guest content for the AWS Open blog. Please get in touch (via comments below) and I would love to speak with you about what you are doing in open source. We are always looking for interesting new content.

The best submissions will get some AWS Credit codes as a thank you.


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)