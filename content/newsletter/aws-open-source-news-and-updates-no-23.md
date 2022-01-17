---
title: 'AWS open source news and updates No. 23'
date: '2020-06-08'
tags : [ oss-newsletter ]
---
## June 8th - Instalment #23

Episode 23 - I was reminded this week that I have now posted over 30 posts to dev.to since I joined the platform late last year. I am currently putting together some stats that I will share with you around the breakdown of various open source topics I have seen over that time. Watch this space.

This week I have added a Retro section as one of the things that keeps coming up is cool open source projects that are not new, but I had never heard of before and are getting new contributions or releases. So, for the ones that stand out, I will share so more people can hear about them.

Again, I am always looking for exclusive open source projects that I can share with the community. Please contact me with your AWS related open source projects as I have prizes for the best contributions...so look forward to seeing what you send.

**The breakfast club - Vipin Mohan**

For those who are not kids of the 80's, Breakfast Club was one of my favourite films at the time and has stood the test of time. A good metaphor for open source, perhaps. [In this super fun video podcast]() (really love the format), the host, CTO/Founder Gadi Naor speaks with Vipin Mohan, a segment lead at AWS. There is a lot of fun stuff as well as the good tech stuff you want, including some great direct questions probing open source projects and supply chain as well as a more forward look at what might be on the horizon. Like Vipin, I am also incredibly interested in what folks are doing on Unikernels, especially on AWS, so I would love to hear from you and what you are doing.

{% youtube n7ahpNqmY3o %}

BTW, the term Hackers should be thought of as the immune system of tech should check out the origin of that, in this [TEDx talk from Keren Elazri](https://www.ted.com/talks/keren_elazari_hackers_the_internet_s_immune_system?language=en). It might be an old talk, but it is still super relevant. Hat tip to [Steve Bryen](https://twitter.com/steven_bryen) for sharing this with me.

**Open source internships**

Before we start, wanted to share this curated set of open source internships and programs that might be useful if you are looking for more opportunities to join open source communities, projects or programs. Also, if you run your own or are aware of other programs that are not on this list, make a PR and get it added onto this useful list.

[Find the list here](https://github.com/deepanshu1422/List-Of-Open-Source-Internships-Programs).

### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created.

So thank you to [Matteo](https://twitter.com/spezam), Chris Armstrong, [Michael Hart](https://twitter.com/hichaelmart), [Steve Engledow](https://twitter.com/stilvoid), [Lee Packham](https://twitter.com/Joolz), Keith Rozario, Brad Johnson, [Grégoire Morpain](https://twitter.com/wz_), [Matt Bacchi](https://twitter.com/fshwsprr), Qing Lan, [James Beswick](https://twitter.com/jbesw), Sven A, Mark Avdi, Shashank Prasanna and Alex Chung 


### For your diary

**June 18th**

Nextflow is an open-source framework and language that enables complex, data-intensive workflow pipeline scripts, and simplifies the deployment of genomics analysis workflows in the cloud.

On June 18th, sign up to this virtual webinar/workshop and find out how you can use that open source framework on AWS to deploy a genomics analysis environment.

Registration [link for Run your Genomics Pipeline with Nextflow on AWS here](https://genomicspipelinenextflow.splashthat.com/?id=ricsue).

Who should attend? The event agenda is designed for developers, research scientists, clinical geneticists, bioinformaticians, computational biologists, and informatics practitioners across R&D, academia, start-ups, public services healthcare organizations, pharma & life science companies.

### Project of the week

**eventbridge-cli**

Thanks to Matteo (@spezam) for sending in this project, **eventbridge-cli**. Amazon EventBridge is a serverless event bus that makes it easy to connect applications together using data from your own applications, integrated Software-as-a-Service (SaaS) applications, and AWS services.

Eventbridge-cli is a tool to listen to an EventBus events. Useful for debugging, event pattern testing, CI pipelines integration. Here are some of the features:

* Listen to Event Bus messages
* Filter messages by event pattern
* Read event pattern from cli, file or SAM template
* Authentication via profile or env variables (AWS_ACCESS_KEY_ID, AWS_SECRET_ACCESS_KEY)
* Pretty JSON output
* CI mode

Go grab this tool from the [GitHub repository here](https://github.com/spezam/eventbridge-cli).

Thank you Matteo!

### Latest from open source projects

**Sizing Amazon DynamoDB**

**dynamodb-size** is an npm DynamoDB size calculator by Chris Armstrong which was inspired by a blog post, [How to calculate a DynamoDB Item's Size and Consumed capacity by Zac Charles](https://medium.com/@zaccharles/calculating-a-dynamodb-items-size-and-consumed-capacity-d1728942eb7c). This npm module allows you to do a few useful things;

* Identifying objects that are too big to store in DynamoDB (such as when using BatchWriteItem)
* Estimating the storage cost of a large number of objects before a bulk-import or data migration
* Optimising the size of objects in a busy table

Thanks Chris!

**dynalite**

Sticking with the Amazon DynamoDB theme, [dynalite](https://github.com/mhart/dynalite/blob/master/README.md) is a project by Michael Hart, offers an alternative to those using Amazon's DynamoDB Local.

This project is an implementation of Amazon's DynamoDB built on LevelDB for fast in-memory or persistent usage and aims to match the live DynamoDB instances as closely as possible (and is tested against them in various regions), including all limits and error messages.

Why not try it out and provide Michael with some feedback. Thanks Michael!


**Building a location based, scalable, serverless web application with SAM**

AWS Serverless Application Model, or AWS SAM, is an open source framework for building serverless applications. Fellow DA James Beswick has written up a nice project and walkthrough this week, the first in a series. 

In [Building a location-based, scalable, serverless web app – part 1](https://aws.amazon.com/blogs/compute/building-a-location-based-scalable-serverless-web-app-part-1/) you will get to build a nice demo application using lots of nice open source components and of course AWS SAM. I really like the idea behind this demo app, Ask Around Me, and it is a web application that allows you to ask questions to a community of local users. It’s designed to be used on a smartphone browser.

![demo app](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2020/05/29/ask-1-b.png)

You find the code on the [GitHub repository here](https://github.com/aws-samples/ask-around-me). Like all good box sets, I am not sure I can wait until the next instalment.

**panther**

I first mentioned panther back in [episode 7](https://dev.to/aws/open-source-news-and-updates-on-aws-7-networking-data-analytics-security-and-more-5954), but this time it is to talk about their security project focused on security for cloud native applications. So what does it do? From the project page;

> Panther is a platform for detecting threats with log data, improving cloud security posture, and conducting investigations.

You can use this for analysing your log files, help to tirage incidents, searching for security incidents and helping identify any security weakness to ensure you meet your compliance and best practice objectives.

The project provides clear documentation and a quick start to get you up and running within your AWS environment. Check out the [Quickstart](https://docs.runpanther.io/quick-start) section here. Head over to the actual [**panther** project on GitHub](https://github.com/panther-labs/panther) and give it a go

**ssosync**

Last week I introduced this new project from [Lee Packham](https://twitter.com/Joolz), and this week I put together a follow up post to help you automate how you run ssosync.

Nice work Lee!

**Webiny**

Webiny is a serverless, headless CMS that is very popular. In this [post](https://dev.to/webiny/serverless-headless-cms-by-webiny-open-source-31bk), [Sven A](https://dev.to/svenalhamad) introduces what Webiny is and how it is different to some of the other headless CMS technologies you might already be familiar with, and then provides a [walkthrough](https://docs.webiny.com/docs/get-started/quick-start/).

Thanks Sven.


**Rain**

[Rain](https://github.com/aws-cloudformation/rain) is an experimental (not quite ready for production) workflow tool for working with AWS CloudFormation allowing you to everything from creating, inspecting, monitoring and deploying CloudFormation templates. It looks really neat and follows the patterns of other cli tools.

[![asciicast](https://asciinema.org/a/269609.svg)](https://asciinema.org/a/269609)

After downloading the right binary for your environment, you can get started. How to use Rain is simple enough, check out the[ user guide docs here](https://aws-cloudformation.github.io/rain/). I also recommend you check the list of other CloudFormation tools they have listed as well.

As a side note, really like how this project has listed the design principles - I wish more projects would do this and is super helpful for contributors to the project.

Nice work Steve!

### Retro machine

So, these are not new projects, but they have come up this week in conversations, on social media, or because they have had some nice new update. Check them out

**AWS Limit Monitor Solution**

The AWS Limit Monitor Solution is a reference implementation that provides a foundation for monitoring AWS service limits. This is not a new project, but it was new to me and I think this is super useful, and you can read about the solution here on the [AWS Solutions Library page](https://aws.amazon.com/solutions/implementations/limit-monitor/).

![architecture diagram](https://d1.awsstatic.com/Solutions/Solutions%20Category%20Template%20Draft/Solution%20Architecture%20Diagrams/aws-limit-monitor-architecture.4faf691d25c496a8a4a5942e4ff22c9c66d1c794.png)

Customers can leverage the solution to monitor limits across services supported by Amazon Trusted Advisor; in multiple regions and multiple AWS accounts. The solution integrates with Amazon SNS and Slack to notify customers for service limits approaching thresholds.

Check out the [project source code on the GitHub project over here](https://github.com/awslabs/aws-limit-monitor).

**AWS Toolkit for Azure DevOps**

If you are using Azure DevOps for your build and release piplines, then this project is going to be of interest. This toolkit allows you to work with AWS services (for example, Amazon S3, AWS Elastic Beanstalk, AWS CodeDeploy, AWS Lambda and others) and run commands using the AWS Tools for Windows powershell module.

This works with certain versions of Team Foundation Server (wow, that brings back some memories) as well as Azure DevOps. Check out the [project page here](https://github.com/aws/aws-toolkit-azure-devops) and if you want to contribute, they are always looking for more people.

**aws-sso**

This [project from George Morpain, aws-sso](https://github.com/wnkz/aws-sso), came up this week in discussion around how to grab credentials into the cli when using AWS Single Sign on. Currently the solution is available and tested for MacOS clients.

Thank you George for this!


### Blog posts you should check out

**Minio performance bake off**

MinIO is a cloud storage server compatible with Amazon S3, released under Apache License v2. In this post, [Impact of Intel vs. ARM CPU Performance for Object Storage](https://blog.min.io/intel_vs_gravitron/), Frank Wessels runs some experiments to compare the performance of running MinIO on both Intel as well as the new Graviton2 instance types. The results are interesting - I do not want to give any spoilers, as I think you should read the post.

![graph](https://blog.min.io/content/images/size/w2000/2020/06/Screenshot-at-Jun-03-12-46-06.png)

Thanks Frank!


**Logging within AWS Lambda functions**

Keith Rozario post [Logging within AWS Lambda Functions (python edition)](https://www.keithrozario.com/2020/04/logging-within-lambda-functions.html) somehow slipped under my OSS radar, but super happy I found it.

![logs](https://www.keithrozario.com/wp-content/uploads/log_relationships.png)

The post is a deep dive into logging when you are starting out writing your functions in AWS Lambda. It is super clear, and you will be much clearer about how to approach logging within your functions after reading this. I was also happy that [AWS Lambda Powertools](https://github.com/awslabs/aws-lambda-powertools) is also called out in this post, and Keith shows you how to use it.

Thank you Keith!

**Amplify and DNS**

In this post on [Amplify and Custom Domain Management, Matt Bacchi](https://bacchi.org/posts/aws-amplify-domain/) walks us through some recent experience he had setting up custom domains with AWS Amplify. If you use AWS Amplify, then this is a must read post.

Thank you Matt!

**AWS CDK and AWS Cloud Stacks**

What are these I hear you say. Well, in this post, [How AWS CDK facilitates the development process of AWS Cloud Stacks Mark Avdi](https://www.linkedin.com/pulse/how-aws-cdk-facilitates-development-process-cloud-stacks-mark-avdi/) walks you through what AWS CDK is, why you should use it and breaks down the core concepts and constructs very nicely indeed, including a good summary of the cli commands you will need.

I am still learning AWS CDK too, so this was a great post to cement my understanding and I learnt a whole bunch of new stuff too.

Thanks Mark!

**The business of open source**

Not a technical post this time, but a post on the O'Reilly blog that takes a look at what it takes to build a business around open source, and looks at Chef as a good example of how to proceed.

T[he business of open source - read on](https://www.oreilly.com/radar/the-business-of-open-source)!


**Robot Operating System ROS**

Off the back of last weeks final ROS 1 release ([ROS Noetic Ninjemys](https://www.openrobotics.org/blog/2020/5/23/noetic-ninjemys-the-last-official-ros-1-release)) comes the announcement that ROS 2 Foxy Fitzroy was GA this week. There were plenty of posts, but [this one from Open Robotics](https://www.openrobotics.org/blog/2020/6/5/ros-2-foxy-fitzroy-release) does a great job summarising how ROS 2 is production ready. Some of the key points:

* Built on top of Ubuntu 20.04, with 3 years support horizon
* x86 and ARM support
* Windows, MacOS and Ubuntu ready

[Check out this link for a list](https://index.ros.org/doc/ros2/Releases/Release-Foxy-Fitzroy/#new-features-in-this-ros-2-release) of the new features available

If you are looking for a great primer on ROS then check out this post from Caelinsutch, [A Brief Introduction to the Robot Operating System (ROS)](https://dev.to/caelinsutch/a-brief-introduction-to-the-robot-operating-system-ros-15m5)

Thanks Caelinsutch

**Jenkins**

Jenkins is a thriving open source project, loved by many developers and open source enthusiasts, and in this post, Brad Johnson writes about how to get the most out of running Jenkins on AWS, including highlighting the available plugins, talking through running Jenkins on Amazon ECS and Fargate and deploying Lambda functions using Jenkins.

![Jenkins](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2020/05/22/Jenkins-Lambda-Arch-1-1024x619.png)

The post finishes up with a quick tour of Jenkins X and GitOps, so if you want to know more about running Jenkins within your AWS environment, then read on in [Why Jenkins still continuously serves developers](https://aws.amazon.com/blogs/opensource/why-jenkins-still-continuously-serves-developers/)

Thank you Brad!

**Object dection using PyTorch, Java and Amazon Deep Java Library**

PyTorch is one of most popular Machine Learning (ML) frameworks but while you have a number of options to deploy your models into production, your options are limited if you want to use Java.

Last year we released the Amazon Deep Java Library (DJL) to provide Java developers the ability to have a simpler option for serving PyTorch endpoints. By abstracting the complexity involved in ML and bundling tedious data processing routines, DJL simplifies running predictions with a PyTorch model down to a few lines of code.

In this post [Implement Object Detection with PyTorch in Java in 5 minutes](https://towardsdatascience.com/implement-object-detection-with-pytorch-in-java-in-5-minutes-c3ba5769e7aa), Qing Lan walks us through the first of a two part post on how to implement object detection with a pre-training PyTorch model in less than five minutes.

Nice post Qing!



### Open Distro for Elasticsearch v1.8

Fresh from the Open Distro for Elasticsearch blog comes news of the v1.8 release that aligns to Elasticseach and Kibana version 7.7.0.

This distribution also includes alerting, anomaly detection, index management, performance analyzer, security, SQL and k-NN plugins. Other components including SQL Workbench, SQL ODBC and JDBC drivers, SQL CLI client, and PerfTop, a client for Performance Analyzer are also available for download.

What is new in 1.8? Here are some of the new things to look out for:

* New feature Cosine Similarity 4 is available for use in k-NN plugin.
* The snapshot 5 feature is now available in the Index Management plugin.
* Anomaly Detection plugin releases the new count aggregation 4 feature to detect anomalies.
* PerfTop CLI 3, a client to interact with Performance Analyzer.

Check out the full release post [here](https://opendistro.github.io/for-elasticsearch/blog/odfe-updates/2020/06/Open-Distro-for-Elasticsearch-1.8.0-is-released-supports-Cosine-Similarity-in-k-NN/).

### AWS updates

**Amazon SageMaker components for Kubeflow pipelines**

Kubeflow is designed to enable using machine learning pipelines to orchestrate complicated workflows running on Kubernetes. 

In this public preview of Amazon SageMaker Components for Kubeflow Pipelines. Machine learning (ML) developers using Kubeflow Pipelines can convert their existing pipeline steps to run on SageMaker with the SageMaker Components. For instance, ML teams can use SageMaker for managed training on Spot instances which will automatically set up model checkpoints to S3 so that you can pause and resume training from the last saved state. Other SageMaker features that are supported in Kubeflow Pipelines are built-in algorithms, managed distributed training, and hyperparameter tuning. In addition, SageMaker can change instance types with one parameter swap, replacing the complicated autoscaling config in Kubernetes.

In this post, [Introducing Amazon SageMaker Components for Kubeflow Pipelines](https://aws.amazon.com/blogs/machine-learning/introducing-amazon-sagemaker-components-for-kubeflow-pipelines/), Shashank Prasanna and Alex Chung walk you through this and get you setting up your first pipeline and they also provide a video walkthrough as well.

{% youtube LKmkiUdhV58 %}

Thanks Alex and Shashank!

**Case study: SK Telecom**

In late April, Amazon announced that Korean mobile telecommunications company SK telecom, working with Amazon Web Services researchers, have released the first open-source, advanced Korean language Generative Pre-trained Transformer-2 (GPT-2) model, called KoGPT-2.
GPT-2 is a language model that has been trained to predict – to “generate” – the completion of a sentence or a paragraph based on as little as a one-word prompt.

KoGPT-2 is an open-source GPT-2 model pre-trained with Korean texts to improve machine learning (ML) performance in the Korean language. It can be used for chatbots, search engines, and other purposes.

KoGPT-2 is available from the GitHub repository of SKT AI Center (https://github.com/SKT-AI/KoGPT2) under a Modified MIT License. AWS also has released a [Git repository](https://github.com/aws-samples/kogpt2-sagemaker) with guidance on how to deploy the KoGPT-2 model into Amazon SageMaker.

Read the full post, [Amazon scientists help SK telecom create Korean-based natural language processor](https://www.amazon.science/latest-news/amazon-scientists-help-sk-telecom-create-korean-based-natural-language-processor) and my college and fellow open source champion Channy Yun told me about the Korean translated version [here](https://aws.amazon.com/ko/blogs/korea/amazon-scientists-help-sk-telecom-create-korean-based-natural-language-processor/).


**R on Amazon SageMaker notebook instances**

Many data scientists and data professionals use the popular open-source statistical computing and graphics software environment R. Amazon SageMaker has pre-installed R kernel out-of-the-box and comes with the reticulate library pre-installed, which offers an R interface for the Amazon SageMaker Python SDK so you can invoke Python modules from within an R script.

In [Coding with R on Amazon SageMaker notebook instances](https://aws.amazon.com/blogs/machine-learning/coding-with-r-on-amazon-sagemaker-notebook-instances/), Nick Minale 
describes how to train, deploy, and retrieve predictions from an ML model using R on Amazon SageMaker notebook instances.


### Quick updates

**AWS Toolkit support for Jetbrains**

The AWS Toolkit for JetBrains is an open source plugin for the integrated development environments (IDEs) from JetBrains. The toolkit makes it easier to create, debug, and deploy software applications on Amazon Web Services using any of the supported JetBrains IDEs (IntelliJ IDEA, PyCharm, WebStorm, Rider, CLion, PhpStorm, GoLand or RubyMine). Using the Toolkits, you can view resources in your AWS account in the ‘AWS Resource Explorer View’, and access various services, such as viewing the S3 browser, CloudWatch logs, remote lambda invoke from your IDE.  

Read the full announcement [here](https://aws.amazon.com/about-aws/whats-new/2020/05/aws-toolkit-for-jetbrains-anounces-support-for-clion-phpstorm-goland-rubymine-ides/).

**Amazon Aurora PostgresSQL**

Version and features update: Update version compatibility to support PostgreSQL minor versions 11.7, 10.12, and 9.6.17. These releases contains bug fixes and improvements from the PostgreSQL community. We have also updated some of the extensions supported in Aurora PostgreSQL: in Aurora PostgreSQL 11.7, we have updated orafce to version 3.8, PGAudit to version 1.3.1 , and pgTAP to version 1.1; in Aurora PostgreSQL 10,12, we have updated orafce to version 3.8, and PGAudit to version 1.2.1; and in Aurora PostgreSQL 9.6.17, we have updated orafce to version 3.8 and PGAudit to version 1.1.2.

Read the full announcement [here](https://aws.amazon.com/about-aws/whats-new/2020/06/amazon-aurora-supports-postgresql-versions-117-1012-and-9617-and-adds-global-database-for-postgresql-117/)

**Amazon Linux 2 based Tomcat**

The new generation of Tomcat on Amazon Linux 2 platforms come with Amazon Corretto, a no-cost production-ready distribution of the Open Java Development Kit (OpenJDK). These platforms support static files proxy and come in four platform branches: Tomcat 8.5 with Corretto 11, Tomcat 8.5 with Corretto 8, Tomcat 7 with Corretto 11, and Tomcat 7 with Corretto 8. Learn more about the Amazon Linux 2 based Elastic Beanstalk platforms in this blog post.

Read the full announcement [here](https://aws.amazon.com/about-aws/whats-new/2020/06/aws-elastic-beanstalk-announces-general-availability-of-amazon-linux-2-based-tomcat-platforms/).

**Amazon RDS MySQL**

Amazon RDS for MySQL has been updated to support release 8.0.19 of the MySQL database. This release includes a number of bug fixes as well as functionality improvements.

Read the full announcement [here](https://aws.amazon.com/about-aws/whats-new/2020/06/amazon-rds-for-mysql-supports-minor-version-8-0-19/).

**AWS Global Accelerator support in AWS CloudFormation**

This project adds support for AWS Global Accelerator resource definitions in CloudFormation. GitHub repository can be found [here](https://github.com/aws-cloudformation/aws-cloudformation-resource-providers-globalaccelerator).

### Open source builders

Following on from last weeks posts interviewing open source builders, Matt Assay has been hard at it again.

This week he talks to the force behind an open source tool you will almost certainly be familiar with and most likely use on a day to day basis. Daniel Stenberg created Curl way back in 1996 before the OSI had got together and created open source, but this project has been steadily growing and by some estimates now is used every day by billions of devices.

Read the full interview, [You're addicted to curl you just didn't know it](https://thenewstack.io/youre-addicted-to-curl-you-just-didnt-know-it/). One of my favourite posts this year.

#### Are you an open source builder?

If you are an open source builder and want to share your project or your open source story please get in touch. I am always looking to talk with people and write these up or video them.

---

### Share your open source projects 

Do you have some content you want to share with a broader audience? We are always looking for guest content for the AWS Open blog. Please get in touch (via comments below) and I would love to speak with you about what you are doing in open source. We are always looking for interesting new content.

The best submissions will get some AWS Credit codes as a thank you.


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)