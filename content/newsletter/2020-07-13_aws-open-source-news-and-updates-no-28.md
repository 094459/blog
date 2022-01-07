---
title: 'AWS open source news and updates No. 28'
date: '2020-07-13'
tags : [ oss-newsletter ]
---
## July 13th - Instalment #28

Week No.28, and this week we have another fantastic  collection of open source posts covering robotics, containers, serverless, machine learning and more. I cover a number of projects you can get stuck into, including robotics projects and resources, a continuous machine learning project posts and the usual collection of indispensable projects that you will wonder how you ever managed without. Finally there are some events you might want to put in your diary.

Remember, if you have a project you want me to mention or talk about, then please reach out. I do provide prizes for the ones that I particularly like, so there is also that incentive too.

Super excited this week about the Open source builder videos and blog posts that we released late last week. It was a lot of fun talking with Olaf, Alex and Liz, all of whom have featured in past episodes of this newsletter, either because of open source projects they are behind or open source products they have launched.

[Part one](https://aws.amazon.com/blogs/opensource/open-source-builders-getting-started/) is all about how they got started in open source, and we follow that up in [part two](https://aws.amazon.com/blogs/opensource/open-source-builders-lessons-learned/) with lessons learnt. Now I have to apologise that there is no video of Liz and this is entirely my fault. During the recording of these sessions, I had a complete fail and whilst I recorded the video, there was no audio. Very sad, as it was an epic session.

{% youtube b6arpt3l7yM %}

If you want to take part then please contact me as I am currently organising recording of the next batch.

### Looking for a project to join?

[Adam Crockett](https://dev.to/adam_cyclones) is a developer who has been documenting his journey in creating a new open source project called [didi](https://github.com/adam-cyclones/didi). You should definitely check out his posts as I think you will all learning something and I really love how Adam is building in the open and sharing his thoughts and getting help from the community.

In his latest post, [Review my open source repository](https://dev.to/adam_cyclones/review-my-open-source-repository-1n1d), Adam shares more info about this project and is now looking for more community engagement to help review and participate. So didi is a a transpiler for JavaScript and Typescript, transforming CommonJS modules into distinct ES Modules which front end and Deno developers will hopefully find useful.

Here is to lots of success in your project Adam, and I hope you inspire others to document their path so we can all benefit.

### Event for your diary

Two events that you should take a look at this week.

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

So thank you to Adam Crockett, Maurice Rahme, Matteo Lucchi, DVC, [Jeshan Giovanni](https://twitter.com/jeshan25), Sakti Mishra, [Nathan Peck](https://twitter.com/nathankpeck), Viraj Phanse, Vamshi Konduri, Miaofei, Eli Polonsky, Elad Ben-Israel, James Beswick, Yassine Landa, Mihai Anghel, Dongie Agnir, Kiran Sahoo, [Michael Whiteman](https://www.linkedin.com/in/cybersec-michael/), [Dennis O'Keeffe](https://twitter.com/dennisokeeffe92), Ben Smith,  Abhishek Gupta, Carmen Puccio, Artyom Keydunov, Sigit Priyanggoro, Martin Paradesi, [Paul Duvall](https://twitter.com/paulduvall), [Chris Nagy](https://twitter.com/chris_the_nagy), [Sanjay Siddhanti](https://twitter.com/siddhantis)


Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

**spot mini mini**

A great project and resource if you are interested in Robotics. The [SpotMicro](https://spotmicroai.readthedocs.io/en/latest/) is a self build quadraped robot, and is a really great way to go deep into this field of robotics. Maurice Rahme has put this project together, [Spot Mini Mini](https://github.com/moribots/spot_mini_mini) which is a PyBullet simulation environment for Spot Micro's that can be used for reinforcment learning tasks and gait simulation.

**robo-gym**

Following on from spot_mini_mini we have another Robotics open source project, this time **[robo-gym](https://github.com/jr-robotics/robo-gym)** an open source project that provides a collection of reinforcement learning environments involving robotic tasks applicable in both simulation and real world robotics. Matteo Lucchi has also put together [a blog post](https://discourse.ros.org/t/introducing-robo-gym-an-open-source-toolkit-for-distributed-deep-reinforcement-learning-on-real-and-simulated-robots/15284) and very short video to show you what this is and how to get started.

**AWS RoboMaker Hospital World**

I have shared some of the gazebo resources before, but this time we have the Hospital World, which provides a great starting point for building out simulation environments in which to test your robots. You can find the resources in the [GitHub repository here.](https://github.com/aws-robotics/aws-robomaker-hospital-world)

![hospital](https://github.com/aws-robotics/aws-robomaker-hospital-world/raw/master/docs/images/hospital_world.jpg)

**cml**

Fresh in from my social media feed (check out [DVC's tweet here](https://twitter.com/DVCorg/status/1280505393496629249)) is Continuous Machine Learning (CML) is an open-source library from [DVC](https://dvc.org/) for implementing continuous integration & delivery (CI/CD) in machine learning projects that you can use to automate parts of your development workflow, including model training and evaluation, comparing ML experiments across your project history, and monitoring changing datasets. This project provides great documentation and in depth instructions on how you can use this and get started on AWS. I have put this project on my todo list to check out over the weekend, maybe you will too? GitHub repo is [here](https://github.com/iterative/cml)

**serverless ghost**

This very early project from [Jeshan Giovanni](https://twitter.com/jeshan25), provides a guide on running the popular blogging platform Ghost, running (mostly) on serverless technologies on AWS. Check out the [GitHub repository here](https://github.com/jeshan/serverless-ghost). Jesham provides good documentation and an easy way to deploy this if you are in a hurry.

**copilot-cli**

[copilot-cli](https://github.com/aws/copilot-cli) is an open source project for developers to build, release and operate production ready containerized applications on Amazon ECS and AWS Fargate. From getting started, pushing to a test environment and releasing to production, Copilot helps you through the entire life of your app development. Got a Dockerfile and some code? Get it up and running on ECS in under 10 minutes, with just one command. Ready to take that app to production? Spin up new environments and a continuous delivery pipeline without having to leave your terminal. Find a bug? Tail your logs and deploy with one tool. You can use Copilot to:

* Organize all your related micro-services in one application
* Set up test and production environments, across regions and accounts
* Set up production-ready, scalable ECS services and infrastructure
* Set up CI/CD Pipelines for all of the micro-services
* Monitor and debug your services from your terminal

Read below for more details, and check the [Whats New announcement here](https://aws.amazon.com/about-aws/whats-new/2020/07/amazon-ecs-announces-aws-copilot/).

**action-hero**

[action-hero](https://github.com/princespaghetti/actionhero) is a project from [Anthony Barbieri ](https://dev.to/prince_of_pasta)that aims to simplify and help builders create least priviledge policies. In the corresponding blog to help you get started, [Action Hero to the rescue! Creating least privilege AWS IAM policies](https://dev.to/prince_of_pasta/action-hero-to-the-rescue-creating-least-privilege-aws-iam-policies-53o2) you will see how to get started with the easy to follow examples.

**s3-log-ingestion-lamda**

[s3-log-ingestion-lambda](https://github.com/newrelic/aws_s3_log_ingestion_lambda) is an open source project from New Relic that sends log data from an S3 bucket of your choice to New Relic. Also, the nice folks at New Relic have made this [available via the Serverless Application repository](https://serverlessrepo.aws.amazon.com/applications/arn:aws:serverlessrepo:us-east-1:533243300146:applications~NewRelic-log-ingestion-s3) to make your life easy.

**Hybrid open source workshop**

Adrian Cantrill is a technical trainer, Solutions Architect and consultant based in Brisbane, Australia. He [posted something](https://www.linkedin.com/posts/adriancantrill_its-almost-weekend-the-time-to-get-busy-activity-6687286024063852544-m73i) over the weekend which was amazing, some deep dive demo lessons/workshops which he is releasing on his GitHub repository. Now these are going to be really useful for those enterprise customers or folk who are looking at migrating to AWS and looking to build hybrid architecture and capabilities as a bridge.

![hybrid](https://github.com/acantril/learn-cantrill-io-labs/raw/master/aws-hybrid-activedirectory/hybriddirectoryadvdemo.png)

You can find [Adrian's blog here](https://cantrill.io/), and his [GitHub repository here](https://github.com/acantril/learn-cantrill-io-labs/tree/master/aws-hybrid-activedirectory).

**php resources**

[The Serverless Lamp Stack GitHub project](https://github.com/aws-samples/php-examples-for-aws-lambda/blob/master/serverless-php-resources.md) is a community effort to consolidate resources (blog posts, projects, walk throughs and more) around building serverless PHP applications. Hat tip to Ben Smith for sharing this gem of a resource with me. If you have your own favourite resources, then make a PR and add.

![lamp](https://github.com/aws-samples/php-examples-for-aws-lambda/raw/master/repository-resources/serverless-lamp-stack.png)

### Blog posts you should check out

**AppSec Platform**

[Reducing Our Attack Surface with AppSec Platform](https://medium.com/ww-tech-blog/reducing-our-attack-surface-with-appsec-platform-4b6717a16709) - Great post from [Michael Whiteman](https://www.linkedin.com/in/cybersec-michael/) from WW,  who talks about how to approach building an automated security and scanning platform that allows you to continuously discover and monitor your digital assets. He shares how did this using open source tools and low cost AWS services. To find out more about the AppSec platform, read the post and congratulate yourself on 10 well spent minutes.

![architecture](https://miro.medium.com/max/700/1*_NO0gFwpkbmKPXSS68Uccg.png)

**Streamlit**

[Creating Shareable Data Apps Using Streamlit and AWS EC2](https://www.linkedin.com/pulse/creating-shareable-data-apps-using-streamlit-aws-ec2-abhishek-gupta/) - Abhishek Gupta shares his experience on finding a new Python framework, Streamlit. I mentioned this in No. 27, but this time Abhishek provides a tutorial on creating your first Streamlit application on AWS. 

**Getting started with AWS SAM**

[How to get your SAM Hello World done easily](https://blog.heyitschris.com/posts/get-your-foot-in-the-door-with-sam/) - this post from [Chris Nagy](https://twitter.com/chris_the_nagy) is another great introduction and walkthrough in how to get started with AWS Serverless Application Model (SAM). This post is very pleasing, both in presentation and in the way that the walk through is presented - this seemed to work exactly like my brain was expecting. Check out Chris' other posts and make sure to follow him on Twitter.

**Automate your serverless deployments**

[Continuous Deployment for Serverless Applications on AWS](https://stelligent.com/2020/06/25/continuous-deployment-for-serverless-applications-on-aws/) - this post from [Paul Duvall](https://twitter.com/paulduvall) you will see how you can use AWS SAM as part of a automation approach to full automate your serverless application deployments. All source code is provided so you can use this to learn how it works and then begin applying the same approach to your own projects.

**Serverless Gatsby**

[Build Serverless Blog with Gatsby and AWS Amplify](https://dev.to/sigitp/build-serverless-blog-with-gatsby-and-aws-amplify-1h96) another walk through from Sigit Priyanggoro, this time you will learn how to create a serverless Gatsby blog project using AWS Amplify to integrate front-end with back-end resources hosted in AWS cloud. These serverless blog and cms systems are getting ever more popular, and you have even more choice now with Gatsby.

**Serverless Go with AWS CDK**

[Deploying Serverless Golang APIs With The AWS CDK](https://blog.dennisokeeffe.com/blog/2020-07-06-deploying-a-serverless-go-api/) - this post from [Dennis O'Keeffe](https://twitter.com/dennisokeeffe92) will walk you through using AWS CDK to setup and deploy Go APIs (in this post, [Gin](https://github.com/gin-gonic/gin) is used) in a matter of minutes. As Dennis points out, from small beginnings (i.e. this walkthrough) become potentially huge things. I am with you on that one Dennis!

**Serverless apps with Zappa**

[Serverless Web Apps in Python](http://www.sanjaysiddhanti.com/2020/07/05/serverless/) - this post [Sanjay Siddhanti](https://twitter.com/siddhantis) shares his experience from deploying a full stack web application written in Python, using the Zappa framework. The post shows you how to get started and interact/configure AWS services to do things such as storing and managing secrets, handling the database and managing static content.

**Financial trading and Reinforcement Learning**

[Training RL models for financial trading using TensorTrade on Amazon SageMaker Studio](https://medium.com/@martin.paradesi/training-rl-models-for-financial-trading-using-tensortrade-on-aws-sagemaker-studio-9ebc7996c277) - Martin Paradesi talks about the application of Reinforcement Learning for financial trading, going into a lot of details and providing you with sample notebooks you can get started on straight away.

Check out his short 5 min video too

https://www.youtube.com/watch?v=Bfh6lyu9ca8&feature=emb_logo

**Cube.js**

[Building an Open Source Web Analytics Platform. Part 1: Overview and Analytics Backend](https://dev.to/keydunov/building-an-open-source-web-analytics-platform-part-1-overview-and-analytics-backend-4kdf) - this first of a series from Artyom Keydunov (Co-Founder of [Cube.js](https://cube.dev)) is a walk through on building an open source web analytics platform with Cube.js. Cube.js is an open-source framework for building analytical web applications. It creates an analytics API on top of the database and handles things like SQL organization, caching, security, authentication, and much more.

Make sure you follow Artyom on Dev.to and tune into future installments.


### AWS open source posts

**Docker Compose deloyment straight to Amazon ECS**

[AWS and Docker collaborate to simplify the developer experience](https://aws.amazon.com/blogs/containers/aws-and-docker-collaborate-to-simplify-the-developer-experience/) - this announcement from Carmen Puccio was one of the big news items last week and generated a lot of positive [feedback](https://www.zdnet.com/article/docker-partners-with-aws-to-smooth-container-deployments/). This collaboration between Docker and AWS that allows developers to use Docker Compose and Docker Desktop to deploy applications on Amazon ECS on AWS Fargate. This new functionality streamlines the process of deploying and managing containers in AWS from a local development environment running Docker. The folks and Docker put their own blog to announce this too, [From Docker Straight to AWS](https://www.docker.com/blog/from-docker-straight-to-aws/).

**AWS Copilot**

[Introducing AWS Copilot](https://aws.amazon.com/blogs/containers/introducing-aws-copilot/), this blog post from Nathan Peck introduces and walks you through AWS Copilot. AWS Copilot is designed to help you deploy a production ready containerized service with only a few commands. You provide your Dockerfile, and let Copilot build, push, and launch your container on AWS. This is just the beginning of Copilot’s powerful features and using Copilot, you also get an easy way to:

* Set up a CI/CD pipeline automatically so you can deploy by simply pushing to a Git repository
* (Coming soon) Provision storage for your services, including S3 buckets, NoSQL, and SQL databases

![copilot](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2020/06/24/optimized-copilot-init.gif)

Follow [Nathan on Twitter](https://twitter.com/nathankpeck) to keep up to date on AWS Copilot and more.

**Open Distro for Elasticsearch**

[Open Distro for Elasticsearch 1.9.0 is now available](https://opendistro.github.io/for-elasticsearch/blog/odfe-updates/2020/07/Open-Distro-for-Elasticsearch-1.9.0-is-released/) post from Viraj Phanse announced the general availability of Open Distro for Elasticsearch 1.9.0. This release introduces Root Cause Analysis Engine in Performance Analyzer, batch actions like start, stop and delete for anomaly detectors in Anomaly Detection, support for remote cluster indexes in Anomaly Detection, and an ability to set index priority action in Index State Management feature. It maps to Elasticsearch version 7.8.0, and Kibana version 7.8.0.


**AWS RoboMaker and Amazon S3 rosbag extensions**

[Easily record and store robotic application data with the S3 rosbag cloud extension for AWS RoboMaker](https://aws.amazon.com/blogs/robotics/record-store-robot-data-rosbag/) this post from Vamshi Konduri and Miaofei introduces a set of new ROS nodes that developers, QA engineers and fleet managers can use to debug, test, and develop features for their robots. The post talks about the new S3 rosbag cloud extension that enables customers to easily configure and record data from robots as rosbags, and upload them to Amazon S3, which they can later use to analyze events, troubleshoot existing applications, and provide as inputs to AWS RoboMaker log-based simulation for regression. This post looks at three ROSnodes in the S3 rosbag cloud extension that create and upload rosbag files from the robot to Amazon S3, and gives you some hands-on examples of how to us the nodes. 


**cdk8s+**

[Introducing cdk8s+: Intent-driven APIs for Kubernetes objects](https://aws.amazon.com/blogs/containers/introducing-cdk8s-intent-driven-apis-for-kubernetes-objects/) this post from  Eli Polonsky and Elad Ben-Israel talks about the many options you have to define Kubernetes applications via code, including the recent launch of cdk8s an open-source project that enables you to use general purpose programming languages to synthesize manifests. This post talks about the next step for cdk8s, not surprisingly called cdk8s+. cdk8s+ is a library built on top of cdk8s and provides a rich, intent-based class library for using the core Kubernetes API. It includes hand crafted constructs that map to native Kubernetes objects, and expose a richer API with reduced complexity.

The post then walks you through deploying a sample application and looks at the different approaches you have. This was the best part of this post, and I think you will like how you can use much of the thinking as you approach how you automate the deployment of your applications.

![summary](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2020/07/01/Screen-Shot-2020-07-01-at-1.32.52-PM.png)

This project is still in alpha, and the team are looking for feedback as well as builders who want to roll their sleeves up and contribute.

**Logging in AWS Fargate**

[How to capture application logs when using Amazon EKS on AWS Fargate](https://aws.amazon.com/blogs/containers/how-to-capture-application-logs-when-using-amazon-eks-on-aws-fargate/) post from Kiran Sahoo is very timely as I was discussing this very topic this week with some customers. When working with your applications, ensuring you can capture and access logs is essential to help you understand and diagnose problems. This post shows how to capture and ship application logs for pods running on Fargate, and provides some good options and suggestions for some alternate ways you can achieve this.

**AWS SDK for Java**

[Using the New Client-Side Metrics feature in the AWS SDK for Java v2](https://aws.amazon.com/blogs/developer/using-the-new-client-side-metrics-feature-in-the-aws-sdk-for-java-v2/) -  Dongie Agnir's post provides a quick walkthrough with examples of the new preview release of the metrics module for the AWS SDK for Java which allows you to collect and publish performance metrics that are captured automatically by the SDK as you use it. With that information, you can use it to help diagnose issues in your applications such as increase latency in API calls or startup lag.

**Amazon EKS and Kiosk**

[Set up soft multi-tenancy with Kiosk on Amazon Elastic Kubernetes Service](https://aws.amazon.com/blogs/containers/set-up-soft-multi-tenancy-with-kiosk-on-amazon-elastic-kubernetes-service/) - in this post from Mihai Anghel, you will find out how to set up soft multi-tenancy in a single Kubernetes cluster with Kiosk. Kiosk is an open source framework for implementing soft multi-tenancy in a Kubernetes cluster. Multi-tenancy in Kubernetes is a hot topic in the open source community these days due to the evolution of the platform and the complexity that this feature brings in the implementation. To get the latest updates, you can follow the Kubernetes multi-tenancy Special Interest Group community at kubernetes-sigs/multi-tenancy.

![kiosk](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2020/07/06/k8s.png)

**Building an Angular front end to Amazon SageMaker Ground Truth**

[Building a custom Angular application for labelling jobs with Amazon SageMaker Ground Truth](https://aws.amazon.com/blogs/machine-learning/building-a-custom-angular-application-for-labeling-jobs-with-amazon-sagemaker-ground-truth/) - Yassine Landa 
 provides a walk through on how to build a custom labeling UI with Angular. The ability to use a custom front-end framework like Angular enables you to easily create modern web applications that serve your exact needs when tapping into public, private, or vendor labeling workforces that Amazon SageMaker Ground Truth provides. Find the [source code for this project in the GitHub repository here](https://github.com/aws-samples/sagemaker-groundtruth-custom-angular-app-template).

**Serverless Loadtesting**

[Load testing a web application’s serverless backend](https://aws.amazon.com/blogs/compute/load-testing-a-web-applications-serverless-backend/) post from James Beswick continues on from his series where he developed an application ([Ask Around Me, source code here](https://github.com/aws-samples/ask-around-me)) but this time he looks at how to perform load testing using the open source tool Artillery. This post provides everything you need to think about as you approach how you start designing how you are going to load test your applications.

![load](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2020/07/01/load-testing1.png)


### Customer stories and case studies

**Compass**

Urban Compass, Inc. (Compass) operates as a global real estate technology company. The Company provides an online platform that supports buying, renting, and selling real estate assets. In their own words, “Compass is building the first-of-its-kind modern real estate platform, pairing the industry’s top talent with technology to make the search and sell experience intelligent and seamless. Compass operates in over 24 markets, with over 2 billion in sales this year to date, with 2,300 employees and over 15,000 agents with a vision to find a place for everybody in the world.”

In this post, [Simplifying and modernizing home search at Compass with Amazon ES](https://aws.amazon.com/blogs/big-data/simplifying-and-modernizing-home-search-at-compass-with-amazon-es/), from Sakti Mishra, you will find out how Compass’s search solution evolved, what challenges and benefits they found with different architectures, and how they approached moving to managed open source services.

**Orangetheory Fitness**

Great [write up in the SiliconANGEL](https://siliconangle.com/2020/07/10/orangetheory-fitness-pivoted-digital-business-aws-cloud/) on how Orangetheory Fitness were able to leverage AWS Amplify to build an 'at home' experience with integrated with AWS video services. Amplify Video is an open source plugin for AWS Amplify that makes it easier to build serverless, video-enabled,web and mobile applications. Developers can create both video-on-demand and livestreaming applications. From the post I love this quote:

“From the time AWS pointed me to the Video plugin code repository and the Amplify CLI, the initial setup was under an hour,” González recounted.

### Quick updates

**Introducing Amazon EMR Managed Scaling**

This post discussed EMR Managed Scaling, which automatically resizes your cluster for best performance at the lowest possible cost. This is a new feature that automatically resizes your cluster for best performance at the lowest possible cost. With EMR Managed Scaling you specify the minimum and maximum compute limits for your clusters and Amazon EMR automatically resizes them for best performance and resource utilization. EMR Managed Scaling continuously samples key metrics associated with the workloads running on clusters. EMR Managed Scaling is supported for Apache Spark, Apache Hive and YARN-based workloads on Amazon EMR versions 5.30.1 and above. Read the full post here, [Introducing Amazon EMR Managed Scaling – Automatically Resize Clusters to Lower Cost](https://aws.amazon.com/blogs/big-data/introducing-amazon-emr-managed-scaling-automatically-resize-clusters-to-lower-cost/).

**Amazon Keyspaces point-in-time-recovery (PITR)**

Amazon Keyspaces (for Apache Cassandra), a scalable, highly available, and fully managed Apache Cassandra–compatible database service, now enables you to back up your table data continuously by using point-in-time recovery (PITR). 

PITR provides you with continuous backups of your Amazon Keyspaces table data to help you protect against accidental writes or deletes. When you enable PITR, Amazon Keyspaces backs up your table data automatically with per-second granularity. You can restore your table data to any second in time in the preceding 35 days. You can enable PITR with a single click in the AWS Management Console or with a simple Cassandra Query Language (CQL) API call. Using PITR, you can back up tables with hundreds of terabytes of data, with no impact on the performance or availability of your production applications. You also can use PITR to recover Amazon Keyspaces table deleted in the preceding 35 days that had PITR enabled, and restore the table to its state just before it was deleted. 

**Amazon FSx for Lustre Now Supports AWS Graviton2-based Instances**

Amazon FSx for Lustre now enables you to use the open source and popular high-performance file system from Amazon EC2 instances powered by Arm-based AWS Graviton2 processors. This capability makes it easier and even more cost-effective to run workloads where speed matters, such as machine learning, gaming, electronic design automation, high-performance computing, video processing, and financial modeling. 


**Amazon EMR and Customer-managed CMKs in AWS Key Management Service (KMS)**

Amazon EMR now supports encrypting log files using Customer-managed Customer master keys (CMKs) stored in AWS Key Management Service (KMS). Amazon EMR automatically upload log files to Amazon S3 when logging and debugging is enabled With this new feature, you can associate Customer managed CMKs in AWS KMS when launching a cluster. Amazon EMR will automatically encrypt logs using the Customer managed CMKs in AWS KMS. Previously you could only encrypt log files written to S3 using Server-Side Encryption with Amazon S3-Managed Keys (SSE-S3). Click here to learn more about encrypting log files please see the documentation. Log encryption using customer managed CMKs is available in EMR version 5.30, in all regions where EMR is available 

**Amazon RDS for MariaDB **

Amazon RDS for MariaDB has been updated to support release 10.3.23 and release 10.4.13 of the MariaDB database. These releases include a number of bug fixes as well as functionality improvements.

### In other news

**SapienSecure**

In this post, [AWS-powered Covid-19 diagnostic tool seeks lung scans from India](https://menafn.com/1100452786/AWS-powered-Covid-19-diagnostic-tool-seeks-lung-scans-from-India), you can read about how collaboration from researchers across the globe to tackle COVID-19 is being enabled by open source tools such as SapienSecure developed by SapienML and AWS.

**Redis**

RedisLabs has announced that Madelyn Olson, a senior software development engineer at Amazon Web Services, and Zhao Zhao, senior engineer at Alibaba Cloud, have have joined the core team. Read the full announcement on the Redislabs website, [Redis Core Team Update](https://redislabs.com/blog/redis-core-team-update/). This was warmly received on[ social last week](https://twitter.com/thenewstack/status/1281293739928010753) when the announcement dropped.


### Share your open source projects 

Do you have some content you want to share with a broader audience? We are always looking for guest content for the AWS Open blog. Please get in touch (via comments below) and I would love to speak with you about what you are doing in open source. We are always looking for interesting new content.

The best submissions will get some AWS Credit codes as a thank you.


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)