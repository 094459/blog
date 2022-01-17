---
title: 'AWS open source news and updates #59'
date: '2021-03-08'
tags : [ oss-newsletter ]
---
## March 8th, 2021 - Instalment #59

Newsletter #59. This week we have a really great selection of open source projects for you to take a look at. Quail, not just a fancy egg you enjoy on those special occasions but an interesting project that helps you easily provision resources for your developers was my pick from a very good bunch. Aside from that, the usual round up of fresh blog posts from AWS and the community, some new events that are happening later this week and next and a new newsletter for you to sign up to. Speaking of which...

**Observability newsletter**

Launched in the last week or so, a great new regular newsletter covering all topics on observability (abbreviated to o11y for short, which I like as I have troubles spelling it!), coming from Michael Hausenblas. From the newsletter itself he writes:

> This is the observability (o11y) newsletter. I'll be covering o11y topics including but not limited to OpenTelemetry, Prometheus, FluentBit, and other related CNCF projects. My goal is to keep you up-to-date concerning o11y topics, from blog posts to webinars to tooling.

You can read online and sign up for the regular instalments via the link [https://o11y.news/](https://aws-oss.beachgeek.co.uk/99)

**Update on the Elasticsearch Fork**

If you have not kept up to date, the latest Fork update, [Feb 26th Fork Update](https://aws-oss.beachgeek.co.uk/97), shows great progress is being made. One thing I would add however it to make sure you check the comments in the main [thread here](https://aws-oss.beachgeek.co.uk/98) as there is lots of interesting information, comments as well as opportunities to contribute/share your knowledge.


### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Greg Farrow, Kyle Davis, Michael Hausenblas, Gayan Weerakutti, Jesse Cox, Abhishek Sinha, Al MS,  BJ Haberkorn, Tyler Lynch, Praneeth Tekula, Mahesh Biradar, Nikhil Dabhade, Ashish Mehra, Simon Zamarin, Nihal Harish, Lu Huang, Qingwei Li, Satadal Bhattacharjee, Jeremy Cowan, Trevor Roberts, Farhad Jahangirov, Shane Miller, Niko Matsakis, Alex Chung, Matthew Rose, Nicholas Thomson, Ragha Prasad, Sahika Genc, Kyle Saltmarsh, Nicholas Therkelsen-Terry, Leonard O’Sullivan, Alex Chung, Dustin Luong, Suraj Kota, Joan Aoanan, Calvin Wang, Veronika Megler, Christopher Adigun, Young Jung, Mrudhula Balasubramanyan, Jon Fautley and Vivek Sonar.


Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

So many great projects this week, you really are spoiled for choice.

**quail**

[quail](https://aws-oss.beachgeek.co.uk/9t) are you looking for an open source tool that helps you to provision the compute instances you need without involving your operations staff? Well, you are in luck, as this new open source project from Qube Research may be what you need. It comes with a user interface where you can select configure EC2 instance and provision with a click of a button in any supported region or account. It manages cleaning up the resources as well - so, check out Quail. Not just a posh egg.

![demo](https://raw.githubusercontent.com/qube-rt/quail/master/img/screenshot.png)

**rpCheckup**

[rpCheckup](https://aws-oss.beachgeek.co.uk/9u) is an open source project from Gold Fig Labs, that is an AWS resource policy security checkup tool that identifies public, external account access, intra-org account access, and private resources. In effect, it helps you check for naughty back doors or wide open privileges by making it easier to reason about resource visibility across all the accounts in your org.

Check out a sample resource - don't worry, your resolution will improve.

![report](https://user-images.githubusercontent.com/291215/109552865-2bdcdb00-7a87-11eb-95a8-977269043f1d.png)

**actions2aws**

[actions2aws](https://aws-oss.beachgeek.co.uk/9v) this open source tool from Glass Echidna lets you assume AWS IAM roles from GitHub Actions workflows with no stored secrets. From the README.md:

> GitHub Actions are a pretty nice solution for CI/CD. Where they fall short is integration with other services, like AWS. The approach suggested by AWS is to create an IAM user, allocate it a long-lived access key and store those credentials in GitHub's secret storage. This is undesirable for folks working in an environment where IAM users are not permitted.
> This repo is a GitHub action that can grant your workflows access to AWS via an AWS IAM role session. This means no need to store long-lived credentials in GitHub and comes with a few other benefits.

![arch](https://github.com/glassechidna/actions2aws/raw/main/docs/sequence.png)

**checkov-vscode**

[checkov-vscode](https://aws-oss.beachgeek.co.uk/9w) Checkov is an open source static code analysis tool for infrastrucutre-as-code from the folks at Bridgecrew which I have covered in some of the very earliest versions of this newsletter. Happy news for folks (like me) who are using the Visual Studio tools, as you can now use this open source plugin to get real-time scan results, as well as inline fix suggestions as they develop cloud infrastructure.

![demo](https://raw.githubusercontent.com/bridgecrewio/checkov-vscode/master/docs/checkov-vscode-demo.gif)

**Chrome Extension**

Not technically open source (I could not find it at least) is this plugin you can use if you are using Chrome that helps you better organise your tabs. [Chrome Extension to Auto-Group AWS Tabs by Region](https://aws-oss.beachgeek.co.uk/9x)

### Community open source posts

**Lambda Power Tools**

[Simple Serverless: Neat and Tidy Lambda Functions Use Powertools](https://aws-oss.beachgeek.co.uk/a0) I somehow missed this post from Greg Farrow at the tail end of last year, taking a look at the event source data classes functionality that was recently added to Lambda Power Tools and how you can use these as well as a look at [pydantic](https://aws-oss.beachgeek.co.uk/a1), an open source library for data validation and settings management using python type annotations. If you have been using Lambda Power Tools for a while, then dive deep with this post.

**Grafana**

[Using the Grafana Cloud Agent with Amazon Managed Prometheus, across multiple AWS accounts](https://aws-oss.beachgeek.co.uk/9z) Jon Fautley has you covered if you are looking for a quick guide on how to setup the Grafana Cloud Agent (the bit that generates the source metrics from your applications and systems) and use that to feed into the Amazon Managed Prometheus service.  Jon covers how to do this both single and across multiple AWS accounts.

**Container Registry**

[How to Setup and Use Amazon's Elastic Container Registry](https://aws-oss.beachgeek.co.uk/9y) Vivek Sonar has put together this well written tutorial on how to get started with the Amazon Elastic Container Registry service (ECR). If you run your open source in containers, and are looking for a public or private container registry, Amazon ECR is a great option and this tutorial will show you some of the capabilities and how to get started.

**Snowplough**

[Setup Snowplow Open Source on AWS](https://aws-oss.beachgeek.co.uk/9a) Snowplow Open Source is an open source event data collection platform from AWS Partner Snowplough Analytics, that helps you with the collection and warehousing of data across all of your platforms in real-time. This post shows you how to quickly get up and running within your AWS environment, so why not give it a try.

![arch](https://docs.snowplowanalytics.com/wp-content/uploads/2020/02/snowplow-aws-pipeline-all.png)

**SonarQube**

[Running SonarQube in ECS](https://aws-oss.beachgeek.co.uk/9b) SonarQube is an open-source platform that has been around for a while, is tried and test and is used to help you as part of your automated code deployment process to help perform a continuous inspection of your code quality, doing things such as code reviews with static analysis that help you identify potential bugs, code smells, and security vulnerabilities. This post from Gayan Weerakutti is a brief guide on how to get this up and running on Amazon ECS.

**Obervability**

[Open-Source Monitoring Tools: In-Depth Comparison](https://aws-oss.beachgeek.co.uk/9e) this is a handy post from AWS Partner epsagon, that provides a quick benchmark and review of some of the key open source tools that are being used when it comes to monitoring. The post takes a look at four open source tools: Prometheus, Graphite, Grafana, and Kibana. If you are using these or wonder how the one you are using compares, take a peek.

**AWS Greengrass**

[Greengrass: The Quiet Hero of AWS](https://aws-oss.beachgeek.co.uk/9f) this is a great post from Jesse Cox, takes a look at some of the problems that AWS Greengrass is helping to solve, putting it in the context of manufacturing and industrial use cases. The post covers what the key components of AWS Green and then how it works.

### AWS open source posts

**Rust**

[How our AWS Rust team will contribute to Rust’s future successes](https://aws-oss.beachgeek.co.uk/9o) Shane Miller and Niko Matsakis share details about the Rust team at AWS, and how that team will deliver on its charter of : **The AWS Rust team works to make Rust performant, reliable, and productive for all its users.**. If you are even a little bit interested in Rust then you will want to check this post out, but irrespective of that, this post also highlights one of the mechanisms we use within Amazon to help the team articulated their shared vision and goals. Shane and Niko talk about the tenets they have set out for the Rust team, and both of these things combine to make this an unmissable post this week.

**Open5gs**

[Open source mobile core network implementation on Amazon Elastic Kubernetes Service](https://aws-oss.beachgeek.co.uk/9r) Christopher Adigun and Young Jung with a great deep dive post that you should enjoy slowly with a nice cup of your favourite hot beverage (oh, Yorkshire tea as you are asking). The posts shows you a practical implementation for creating a 4G core network using the open source project Open5gs. The Open5gs is an open source project that provides 4G and 5G mobile packet core network functionalities for building a private LTE/5G network under the GNU AGPL 3.0 license.

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/02/26/jungy-adigunca_Mobile-Core-Network-EKS_f3_1000.png)

The posts provides all the resources you need to build this, and one thing I learned when going through this is that you could use emulators to test LTE connections. Nice.

**XGBoost**

[Utilizing XGBoost training reports to improve your models](https://aws-oss.beachgeek.co.uk/9k) XGBoost is an open-source software library which provides a gradient boosting framework, and in this post, Simon Zamarin, Nihal Harish, Lu Huang, Qingwei Li, and Satadal Bhattacharjee huddle together to show you an end-to-end example of training an XGBoost model on Sagemaker and how to enable the automatic XGBoost report functionality in Sagemaker Debugger to quickly and easily evaluate model performance and identify areas of improvement for your model. Code used in this post is provided in the GitHub repo linked within the post.

**Hugging Face**

[Embracing natural language processing with Hugging Face](https://aws-oss.beachgeek.co.uk/9i) a post from my good self last week, where I sat down with a few of the folks from Hugging Face, including Co-founder Julien Chaumond, to find out more about who they were, their origins and history in open source and exactly what is Hugging Face. I left inspired by their enthusiasm and passion for making it easier for developers to build natural language processing into their apps, and if this is something you are looking to do, then definitely check out their home page.

![hug](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/02/26/ricsue_Hugging-face_f1.png)

**KubeFlow**

A couple of Kubeflow related posts this week.

First up we have [Analyzing open-source ML pipeline models in real time using Amazon SageMaker Debugger](https://aws-oss.beachgeek.co.uk/9p) where Alex Chung, Dustin Luong, and Suraj Kota take a look at how you can use SageMaker Debugger to help model debugging in your Kubeflow Pipelines, going beyond just losses and accuracies during training to getting the full visibility into all tensors flowing through the graph during training, monitoring your training in near-real time using rules, and providing alerts if it detects an inconsistency in the training flow. All of which ultimately reduces costs and improves your company’s effectiveness on ML. Very nice post indeed.

Next, we have [Introducing Amazon SageMaker Reinforcement Learning Components for open-source Kubeflow pipelines](https://aws-oss.beachgeek.co.uk/9n) is a mega-collaboration between Alex Chung, Nicholas Thomson, Ragha Prasad and Sahika Genc from AWS, together with from Kyle Saltmarsh from Woodside Energy and Nicholas Therkelsen-Terry, Matthew Rose, and Leonard O’Sullivan from Max Kelsen, one of Australia’s leading Artificial Intelligence (AI) and Machine Learning (ML) solutions businesses. This post has lots of great stuff, including machine learning and robots, and takes a look at how you can build re-inforcement learning models with open source Kubeflow pipelines  using SageMaker RL Components. Source code, samples notebooks and everything you need to get started is shared in the post, so check it out if you want to learn more.

![arch](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2021/02/22/KFP-Architecture-Woodside-1.png)

**Jupyter**

[Field Notes: Accelerate Research with Managed Jupyter on Amazon SageMaker](https://aws-oss.beachgeek.co.uk/9s) Mrudhula Balasubramanyan shares with you how to set up a managed Jupyter environment using custom tools used in Life Sciences research. You could customise this solution however for your own needs, to help you provision your own Jupyter notebook environments by using the same approach, and then make it super easy to provide your data scientists or users with all the resources they need from within their notebook environment.

![arch](https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2021/03/01/Architecture-from-a-researcher-perspective.jpg)

**PyDeequ**

[Monitor data quality in your data lake using PyDeequ and AWS Glue](https://aws-oss.beachgeek.co.uk/9q) Joan Aoanan, Calvin Wang, and Veronika Megler with a post on how you can use PyDeequ, an open-source project that enables you to write unit tests on your data to ensure data quality, to help you monitor your data quality in uses cases where your data is changing, detecting anomalous changes over time. Building from a previous post where they showed you how you can do this with more historical, static data, this posts guides you gently through the uses cases, understanding anomalies and then the architecture you can implement to do this yourself.

![arch](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2021/03/02/bdb1061-pdq-glue-1-1.jpg)

**Agones**

[Introducing the Amazon GameLift FleetIQ adapter for Agones](https://aws-oss.beachgeek.co.uk/9l) Jeremy Cowan and Trevor Roberts take a look at how you can optimise and reduce the cost of running your Agones game servers. Agones is a popular open source project for managing the lifecycle of containerised game servers and is built on top of Kubernetes. The post takes a look at how you can integrate this with AWS services, specifically the Amazon GameLift FleetIQ product, that helps customers to optimise by using low cost Spot instances. In keeping with the spirit of the Agones project, the adaptor has also been open sourced and you can find out more details about the benefits of using this project by reading on.

![arch](https://d2908q01vomqb2.cloudfront.net/91032ad7bbcb6cf72875e8e8207dcfba80173f7c/2021/03/03/gamelift_fleetiq_agones_blog.png)

**Selenium**

[Integrating AWS Device Farm with your CI/CD pipeline to run cross-browser Selenium tests](https://aws-oss.beachgeek.co.uk/9j) Mahesh Biradar, Nikhil Dabhade and Ashish Mehra collaborate on a great post of how you can use AWS Device Farm in conjunction with your CI/CD pipeline and the open source tool Selenium to test different desktop browsers hosted in AWS. For each test executed on the service, you get generated action logs, web driver logs, video recordings, all of which help you to quickly identify issues with your app. This post runs you through the solution so you can use it as the baseline for your own testing.

**AWS Graviton2**

[Supporting AWS Graviton2 and x86 instance types in the same Auto Scaling group](https://aws-oss.beachgeek.co.uk/9h) Tyler Lynch and Praneeth Tekula share the ready to roll solution that I shared in last weeks newsletter, allowing you to combine multiple instance types and processor architectures within your auto-scaling groups. This walk through shows you how you can do this with a simple Node application but why not try this out as a way of running your open source projects.

![arch](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2021/03/04/Screen-Shot-2021-03-04-at-8.18.45-AM.png)

**Amazon EMR**

[Amazon EMR 2020 year in review](https://aws-oss.beachgeek.co.uk/9g) Abhishek Sinha, Al MS, and BJ Haberkorn provide a nice summary of open source analytics tools that make part of the Amazon EMR service, how these are helping customers and some of the big improvements made in 2020. From optimisation, improved developer productivity, improved performance and more, if you are using tools such as Apache Spark, Apache Hive, Apache HBase, Apache Flink, Apache Hudi, and Presto, then check this post out.

### Case Study

**WordPress**

[Using AWS for on-premises WordPress site continuity](https://aws-oss.beachgeek.co.uk/9m) Who doesn't like a good Wordpress blog post? I know I do, and so it is great to see this post from Farhad Jahangirov taking a look at how Cardiff University have approached building a Wordpress architecture than spans their local environment and AWS, and how this is enabling them to eliminate the need for physical backup infrastructure and improve recovery time. This is a must read post for all Wordpress infrastructure specialists who are looking to make sure their environments remain up and running no matter what.

![arch](https://d2908q01vomqb2.cloudfront.net/9e6a55b6b4563e652a23be9d623ca5055c356940/2021/03/03/Figure-1-DR-solution-in-standby.jpg)

### Quick updates

**Ethereum**

Last week we announced the general availability of Ethereum on Amazon Managed Blockchain. Ethereum is a popular decentralised blockchain framework that establishes a peer-to-peer network allowing participants to transact without a trusted central authority. It enables popular use cases such as decentralised finance (DeFi), a network of financial applications built on top of blockchain networks. DeFi is different from existing financial networks because it is open and programmable, operates without a central authority, and enables customers to offer new methods for payments, investing, lending and trading. As customers build these Ethereum-based applications, they find it complicated and time-consuming to operate and manage their Ethereum infrastructure. Specific concerns include data reliability due to out-of-sync nodes, data storage scaling challenges, and time-sensitive Ethereum software upgrades.

With this launch, AWS customers can easily provision Ethereum nodes in minutes and connect to the public Ethereum main network and test networks such as Rinkeby and Ropsten. With Amazon Managed Blockchain, customers get secure networking, encryption at rest and transport, secure access to the network via standard open-source Ethereum APIs, fast and reliable syncs to the Ethereum blockchain, and durable elastic storage for ledger data. Amazon Managed Blockchain monitors node health, replaces unhealthy nodes, and automates Ethereum software upgrades, improving the availability of customers’ Ethereum infrastructure. In addition to DeFi applications, customers building analytical products such as smart contract monitoring tools and fraud detection software can also benefit from this scalable, highly available, and fully managed Ethereum service on Amazon Managed Blockchain.

**FreeRTOS**

A couple of quick updates this week for FreeRTOS users/fans.

First up we have news that FreeRTOS is now certified for the Security Evaluation Standard for IoT Platforms (SESIP) Assurance Level 2. With this certification, FreeRTOS libraries have demonstrated meeting a specific set of security criteria for IoT platforms. In addition, embedded developers writing FreeRTOS-based applications can achieve SESIP certification for their own applications more quickly because the underlying libraries have been tested for compliance. According to the technical standards organisation GlobalPlatform, SESIP provides a common and optimised approach for evaluating the security of connected products that meets the specific compliance, security, privacy and scalability challenges of the evolving IoT ecosystem. SESIP is based on the industry-established Common Criteria framework.

The certification assessment was performed by Riscure, an independent security lab licensed by TrustCB, a commercial Certification Body conforming to international and industry standards. FreeRTOS 202012.00 LTS libraries including the FreeRTOS kernel and related IoT libraries were evaluated as part of the certification process. The certification tested for verification of platform identity and instance identity, firmware updates over-the-air (OTA), secure communications, software isolation capabilities, and cryptographic operations. You can learn more in the blog: [Why SESIP Certification for FreeRTOS Matters](https://aws-oss.beachgeek.co.uk/9c).

Following that we have news that FreeRTOS Long Term Support (LTS) release 202012.01 now includes the over-the-air update (OTA), AWS IoT Device Defender, and AWS IoT Jobs libraries in the first LTS release (FreeRTOS 202012.00 LTS). With this release, developers can use the FreeRTOS LTS libraries to update firmware, manage device fleets, and monitor fleet metrics for their microcontroller-based IoT devices. In addition, developers can rely on a FreeRTOS version that provides feature stability, and security patches and critical bug fixes for two years. You can read the [full announcement here](https://aws-oss.beachgeek.co.uk/9d), which goes into a lot of detail.

**Elasticsearch**

Amazon Elasticsearch Service now supports tag-based authorisation for easy management of access to configuration APIs that are used for operations such as creating, modifying, or updating Amazon Elasticsearch Service domains. You can create an Identity Policy in AWS Identity and Access Management (IAM) using Resource Tags that allows or denies access to specific configuration APIs for an Amazon Elasticsearch Service domain. You can use Request Tags or Tag Keys to control what tags can be used on a domain or passed in a request. In addition, tagging is now supported on resource creation, which means you can now add a tag when you create an Amazon Elasticsearch Service domain.

### Events for your diary

We have one of these events happening later this week, so check it out and register before it is too late.

**Cloud Data Lake Dev Day Live Workshop**
**March 11th, 9:00am PST**

In this live workshop, we’ll cover the best practices for organizations to use with powerful open source technologies so you can build and extend your AWS investments and make your data lake analytics-ready. You’ll learn about the advantages of cloud-based data lakes in terms of security and cost. How to enable SQL analysts to easily access data in your data lake for reporting and visualization.

Find out more and register via [this link](https://aws-oss.beachgeek.co.uk/8a)

**Embracing Observability in Distributed Systems**
**March 16th, 9:00am EST**

Michael Hausenblas is your speaker and he will look at the motivation for observability in distributed systems such as containerized microservices. We discuss good practices and current developments around CNCF open source projects and specifications including OpenTelemetry and FluentBit.

This is not a free event, but part of the InfoQ event. You can find out more details and register here](https://live.infoq.com/ve2021/presentation/observability).

**Kickstart Your Kubernetes Projects With Amazon EKS-D and KubeOne**
**March 18, 5:00PM CET**

In this session, Michael Hausenblas (AWS) and Mario Fahland (Kubermatic) will take a closer look at EKS-D and dive into how to set up your very own cluster running EKS-D with KubeOne – our open source and infrastructure agnostic Kubernetes cluster lifecycle management tool. We will also have a peek into the future and show how to bring EKS-D to your data centres so you can use the very same tooling on-premises and in the cloud.

Register [here](https://aws-oss.beachgeek.co.uk/7u).

**CDK Day**
**April 30th**

Announced this week was the second [CDK Day](https://sessionize.com/cdkday/), which will be on April 30th. Check out [the web page](https://sessionize.com/cdkday/) to find out more about the first CDK Day, which was incredible. This second event promises to be even better. The CFP is open until the 19th of March. Check out this supporting blog post, [CDK Day CFP Is Open!!!!](https://aws-oss.beachgeek.co.uk/4v) from Matt as to what to expect and what they are looking for when it comes to sessions.

**Cloud Native Rust Day**
**May 3rd**

Rust is a language empowering everyone to build secure, reliable, and efficient software. Rust is becoming more widely used in cloud native, powering everything from lightning-fast service meshes and powerful developer tools to internet-scale distributed databases.

Come explore what makes Rust a fantastic choice for new cloud native development, and learn about how the community uses Rust today. Find out [more and register here](https://aws-oss.beachgeek.co.uk/5y).

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen).