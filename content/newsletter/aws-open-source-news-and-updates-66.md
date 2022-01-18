---
title: 'AWS open source news and updates #66'
date: '2021-05-04'
tags : [ oss-newsletter ]
---
## May 4th, 2021 - Instalment #66

*Updated Jan 18th, to remove dead links*

Newsletter #66. 

This week we have a really outstanding collection of new open source projects, including eventbridge-atlas, ecsk, spotinfo, pecos and more, so make sure you spend some time checking those out. Following on from CDK Day, we have plenty of great posts for CDK fans. As always, there are lots of great community and AWS blog posts covering event driven architectures, containers, big data, and so happy to see the AWS DeepRacer open source announcements last week. Finally, we have a couple of great videos, a podcast and events you should check out and put in your diary.

Before you dive in, make sure you are aware of the following important updates from last week.

**NodeJS**

If you are using NodeJS then last week we had an important post that you should read and check out the recommendations. Trivikram Kamat writes in, [Announcing the end of support for Node.js <10.x in the AWS SDK for JavaScript (v2)](https://aws-oss.beachgeek.co.uk/fw) the timelines, versions as well as the motivation behind this.

**AWS Neuron**

[AWS Neuron](https://github.com/aws/aws-neuron-sdk) is the SDK for running machine learning inference using AWS Inferentia chips, and last week we announced an important change in how you install and update this SDK. To find out more, read [End of support for Neuron Conda packages in Deep Learning AMI](https://aws-oss.beachgeek.co.uk/go)

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Matt Hansen, Eric Johnson, Al MS, Michele Sancricca, Hari Rajaram, Jeremy Ber, Kumar Abhinav, David Duncan, Tracy Pierce, Trivikram Kamat, Zachary Whitford, Richa Prajapati, Aldo Piddiu, Christian Weber, Mark Richman, Jason Gudalis, Baichuan Sun, Eden Duthie, Charles Frenzel, Thom Lane, David Smith, Camilo Buscaron, Eddie Calleja, Siddalingesha Devarmani Shivakumar, Jayadev Vadakkanmarveettil, Bob Wise, Peder Ulander, Willy Tarreau, Jaana Dogan, Jarrod Watts, Jason Umiker, Alexei Ledenev, yukiarrr, OlegA, David Boyne, Teadeveloper, Hsiang-Fu Yu, Inderjit S. Dhillon, Chris Fife, Eric Beard, Rico Huijbers, Sundeep Kumar, Rahul Sonawane, Jasper Wang and Van Vo Thanh.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.


### Latest from open source projects

**eventbridge-atlas**

[eventbridge-atlas](https://aws-oss.beachgeek.co.uk/gg) this is a great open source project from David Boyne, that allows you to document, discover and share your EventBridge schemas. Great documentation that shows you the motivation behind the project as well as how to get started, David also put together this blog post, [Introducing EventBridge Atlas](https://aws-oss.beachgeek.co.uk/gh) which is a must read this week.

![arch](https://www.boyney.io/static/images/blogs/eventbridge-atlas/how-it-works.png)

**ecsk**

[ecsk](https://aws-oss.beachgeek.co.uk/ge) this open source tool from yukiarrr is a CLI tool that you can interactively call Amazon ECS APIs (run-task, execute-command, stop-task), copy files between ECS and local, and view logs. Clear documentation to help you install and get started, check out this demo to see it in action.

![demo](https://raw.githubusercontent.com/yukiarrr/ecsk/main/docs/images/ecsk.gif)

**spotinfo**

[spotinfo](https://aws-oss.beachgeek.co.uk/gf) this open source project from Alexei Ledenev is a command-line tool that helps you determine AWS Spot instance types with the least chance of interruption and provides the savings you get over on-demand rates. Awesome little tool.

**pecos**

[pecos](https://aws-oss.beachgeek.co.uk/gj) PECOS is a versatile and modular open source machine learning (ML) framework for fast learning and inference on problems with large output spaces, such as extreme multi-label ranking (XMR) and large-scale retrieval. PECOS' design is intentionally agnostic to the specific nature of the inputs and outputs as it is envisioned to be a general-purpose framework for multiple distinct applications. You can read more about this project in the blog post, [Amazon open-sources library for prediction over large output spaces](https://aws-oss.beachgeek.co.uk/gk) from Hsiang-Fu Yu and Inderjit S. Dhillon.

![pecos](https://assets.amazon.science/dims4/default/f395830/2147483647/strip/true/crop/2346x1228+0+0/resize/1200x628!/quality/90/?url=http%3A%2F%2Famazon-topics-brightspot.s3.amazonaws.com%2Fscience%2F44%2F70%2F4c683029463da1022b8b582635e3%2Frecursive-matcher.png)

**aws-mwaa-local-runner**

[aws-mwaa-local-runner](https://aws-oss.beachgeek.co.uk/gd) this is a project I have been waiting to be released for a while, and this provides you with a local environment that replicates an Amazon Managed Workflows for Apache Airflow (MWAA) environment. Check out the docs for details on how to get this up and running, but I have been running it for a while and find it super useful for doing local development and testing.

**aws-ec2-dashboard**

[aws-ec2-dashboard](https://aws-oss.beachgeek.co.uk/gc) this open source project from OlegA is a Node.js/JavaScript application that displays list of EC2 instances in a compact and simple way.

**yake**

[yake](https://aws-oss.beachgeek.co.uk/gi) Alexander Mancevice has put this open source project together that is a Rake like DSL for writing AWS Lambda handlers. Rake is a software task management and build automation tool, so this project might appeal to those Ruby developers looking to explore writing functions and deploying them on AWS Lambda.

**awscloudexplorer**

[awscloudexplorer](https://aws-oss.beachgeek.co.uk/gl) this open source tool from Teadeveloper for TUI (terminal user interface) lovers to explore the resources in AWS Cloud using a TUI  instead a GUI or AWS web console. tmux and nc fans will love this tool, currently checking it out.

https://asciinema.org/a/1IkBGa3DB0xKuhCmWtOjeoYSx

### Community open source posts

**Direktiv**

[Direktiv v0.2.1: deploying on AWS EKS or Docker and new UI!](https://aws-oss.beachgeek.co.uk/g8) I covered this project last week, and Wilhelm Wonigkeit from Direktiv has a new post this time showing you how you can deploy this open source project (an event driven, container based workflow engine) on AWS, as well as covering some of the latest new features they have added. This is a really interesting project, so check it out if you missed this last week.

![demo](https://miro.medium.com/max/1000/1*sAHvteh5UOXZyqjEGdxxRg.png)

**GraphQL**

[Get Started With AWS Amplify, Next.JS & Typescript. Full Stack with GraphQL + Authentication in 10 minutes!](https://aws-oss.beachgeek.co.uk/g7) Jarrod Watts puts himself in the leaderboard for blog post with the longest title this week, and what a great post it is - 10 minutes you will not regret. Easy to follow with video backup incase you prefer that.

**HAProxy**

[HAProxy Forwards Over 2 Million HTTP Requests per Second on a Single Arm-based AWS Graviton2 Instance](https://aws-oss.beachgeek.co.uk/g6) Willy Tarreau takes an in depth look at how HAProxy scales when running on AWS Graviton2 instance types. This is a great post, covering the methodology, results and analysis. As with all benchmark posts, I don't want to spoil the conclusion so make sure you read this post to find out more. I will leave you with this tantalising graph though...

![haproxy](https://cdn.haproxy.com/wp-content/uploads/2021/04/7.png)

**Amazon EKS**

If you are looking to expand upon the core Amazon EKS cluster, perhaps been inspired or manually deploying a number of add-ons that you might have seen as part of the [Amazon EKS Workshop](https://aws-oss.beachgeek.co.uk/ga), then this post from Jason Umiker,[Automating the provisioning of a production-ready Kubernetes cluster with AWS EKS & CDK](https://aws-oss.beachgeek.co.uk/g9) will show you how to automate the configuration of those add-ons. Very nice indeed. What is even better is that Jason has written his CDK app in Python, and that makes me very happy.

**Apache Airflow**

[Using AWS CDK to deploy your Amazon Managed Workflows for Apache Airflow environment](https://dev.to/aws/using-aws-cdk-to-deploy-your-amazon-managed-workflows-for-apache-airflow-environment-12cf) to celebrate CDK Day last week I put together this post showing you how you can use AWS CDK to configure and deploy an Amazon Managed Workflows for Apache Airflow environment. I hope it is useful, and builds upon earlier posts where I showed you how you can do this via CloudFormation.


### AWS open source posts

**AWS DeepRacer**

It has been a while since I have done anything with AWS DeepRacer, but the DeepRacer community are very close to my heart and they have some amazing folks doing some really great things. I am very happy therefore, that last week we published a couple of blog posts announcing the open sourcing of AWS DeepRacer.

First up we had my good friend (and follower of DeepRacer cars!) David Smith who post, [AWS DeepRacer device software now open source](https://aws-oss.beachgeek.co.uk/g2) dives into more details about this announcement including a look at some of the sample projects that have been compiled by the AWS DeepRacer team and members of that awesome DeepRacer community, before walking you through some of those samples. David also shares details about discounts you can get yourself which are not to be sniffed at, so make sure you check this post out.

Following that we have a collaboration between Camilo Buscaron, Eddie Calleja, Siddalingesha Devarmani Shivakumar, and Jayadev Vadakkanmarveettil on the post, [AWS DeepRacer is now open source and ready to hit the road with ROS 2](https://aws-oss.beachgeek.co.uk/g3) looks at this announcement from the Robotics perspective, taking a look at some of the ROS packages that are being open sourced and how you can use these to start building projects. They also cover the sample projects, taking a look at the Follow the Leader, Off Road and Mapping projects.

![deep racer](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/04/27/deepracer-mapping_1000.gif)

Really excited as to the possibilities and look forward to sharing future projects in this newsletter.

**ROS**

If you are into Robotics, this post from Matt Hansen, [AWS announces a new developer desktop feature within the AWS RoboMaker IDE](https://aws-oss.beachgeek.co.uk/gt), will be right up your street, showing you a really cool new way we are making it easier for roboticists to develop their robot applications by extending the developer tooling beyond the RoboMaker IDE to now include a full virtual Ubuntu desktop. You can run your favourite ROS tools, Gazebo, RViz, and other tools directly as if it were a local Ubuntu desktop. I can see my Ubuntu machine next to me getting nervous.

![demo](https://d2908q01vomqb2.cloudfront.net/a9334987ece78b6fe8bf130ef00b74847c1d3da6/2021/04/30/fig5.jpg)

**Streamlit**

[Using Streamlit to build an interactive dashboard for data analysis on AWS](https://aws-oss.beachgeek.co.uk/g1) Baichuan Sun, Eden Duthie, Charles Frenzel, and Thom Lane collaborate on this tutorial that show how to stand up an Exploratory Data Analysis (EDA) dashboard for business users using Streamlit. Streamlit is an open source framework for data scientists to efficiently create interactive web-based data applications in pure Python. This walkthrough will show you how you can easily deploy this into your AWS environment with the least effort - always a good thing.

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/04/27/tholane_arch_1000.png) 

**Grafana**

[Using Amazon Managed Service for Grafana to troubleshoot a serverless application](https://aws-oss.beachgeek.co.uk/fz) Mark Richman builds upon an earlier blog post to show you how you can integrate Amazon CloudWatch logs and metrics with Amazon Managed Service for Grafana (AMG), using it to see how you might troubleshoot a serverless application built using Amazon API Gateway and AWS Lambda. The post covers how to visualise, analyze, alarm, and notify on metrics and logs across multiple data sources, all from within Grafana and Mark provides a link to the source code so you can try it yourself.

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/04/12/Richman-Grafana_F1.png)

**AWS CDK**

As the dust settles after another amazing CDK Day event, what better way to celebrate that to catch up on the latest AWS CDK news.

Christian Weber dropped his latest post in his regular [CDK Corner – April 2021](https://aws-oss.beachgeek.co.uk/fy) series. Plenty of updates and news from around the world, so make sure you check out this post. As always, love the community acknowledgements so well done folks who have successfully had their first PRs merged.

Jasper Wang and Van Vo Thanh put together this post, [Building and deploying Fargate with EKS in an enterprise context using the AWS Cloud Development Kit and cdk8s+](https://aws-oss.beachgeek.co.uk/gs) that shows you how you can deploy a sample Kubernetes workload on an Amazon EKS cluster running Kubernetes pods on AWS Fargate using cdk8s/cdk8s+, an open-source software development framework for defining Kubernetes applications a la CDK.

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2021/03/12/CDK8s-1.png)

Announced the evening before CDK Day, Eric Johnson's post [Better together: AWS SAM and AWS CDK](https://aws-oss.beachgeek.co.uk/gp) announced the public preview of AWS Serverless Application Model CLI (AWS SAM CLI) support for local development and testing of AWS CDK projects. If you are not familiar with AWS SAM/SAM CLI, it is a developer tool that makes it easier to build, locally test, package, and deploy serverless applications. This new capability extends the previous ability to test/package using CloudFormation to now be able to build/test with AWS CDK. If you want to know more check out the videos from CDK Day (I will post when they are uploaded in future newsletters) where Eric showed you this in action. This new capability generated a lot of love at CDK Day, so make sure you check this post out.

Finally, it was great to see AWS CDKv2 announced last week, in the post [Announcing AWS Cloud Development Kit v2 Developer Preview](https://aws-oss.beachgeek.co.uk/gq) Chris Fife, Eric Z. Beard, and Rico Huijbers talk you through the changes between CDK v1 and v2. They talk about the AWS Constructs Library, the constructs compatibility layer, the new lifecycle for experimental APIs and more.

**RedHat Linux**

[Announcing availability of Red Hat Enterprise Linux with High Availability on Amazon EC2](https://aws-oss.beachgeek.co.uk/fv) this post from Kumar Abhinav and David Duncan provides a quick walk through of deploying Red Hat Enterprise Linux with High Availability and combining this with the scale, performance and elasticity of AWS to provide an operating system for your highly available compute clusters. I was not aware of Corosync before reading this post, so I am sure you will learn something new too.

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/04/19/kabhinaa_Red-Hat-Enterprise-Linux_f1.png)

**Apache Airflow**

[Orchestrate AWS Glue DataBrew jobs using Amazon Managed Workflows for Apache Airflow](https://aws-oss.beachgeek.co.uk/gr) Sundeep Kumar and Rahul Sonawane show you how you can use to orchestrate and schedule DataBrew jobs with Amazon Managed Workflows for Apache Airflow (MWAA). In this particular post they create a simple transformation logic pipeline, using DataBrew jobs to join two datasets, rename a column, and add a new column and then use Amazon Athena to verify the results.

![arch](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2021/04/27/bdb1364-databrew-mwaa-orchestration-1.jpg)

**Apache Flink**

[Enrich your data stream asynchronously using Amazon Kinesis Data Analytics for Apache Flink](https://aws-oss.beachgeek.co.uk/gm) from Hari Rajaram and Jeremy Ber show you how you can approach asynchronous enrichment of a data stream through the Apache Flink API for asynchronous I/O with external data sources. Why does this matter? Well, you might need this if you have use cases such as  enriching a streaming payload with additional elements, to passing data elements to an API for a machine learning (ML) prediction, or loading data streams into a data lake for near-real-time analytics. Read the post to find out more.

**Presto**

I have spent some time recently working with Presto on Amazon EMR, so I enjoyed reading this new post,[Amazon EMR introduces EMR runtime for Presto, providing a 2.6 times speedup](https://aws-oss.beachgeek.co.uk/gn) from Al MS and Michele Sancricca. Running Presto on Amazon EMR is a popular choice because Amazon EMR provides the latest, stable, open-source community Presto innovations and Amazon EMR platform-level optimisations for Presto workloads - and this posts takes a look at some of those optimisations.


**Apache Kafka**

[How Goldman Sachs migrated from their on-premises Apache Kafka cluster to Amazon MSK](https://aws-oss.beachgeek.co.uk/fx) this guest post from Zachary Whitford, Richa Prajapati, and Aldo Piddiu from the Global Investment Research engineering team at Goldman Sachs takes a look at their migration journey as they moved from self hosted Apache Kakfa to using Amazon Managed Streaming for Apache Kafka (or Amazon MSK). The post covers the rational and thinking behind the move, the options they considered as well as the lessons learned. If you are using/running Apache Kafka workloads, make sure you read this post.

![arch](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2021/04/22/bdb1229-gir-msk-2.jpg)

**Performance Dashboard**

[New Performance Dashboard on AWS makes delivering open, responsive government simple](https://aws-oss.beachgeek.co.uk/g0) Jason Gudalis writes about a newly open sourced solution that aims to help manage and showcase the data you have. The post focuses specifically on doing this with data at the heart of how public services are working, but you could adapt it to your own needs. If you want to see it in action, there is a very short video that shows you what you can expect.

![arch](https://d2908q01vomqb2.cloudfront.net/9e6a55b6b4563e652a23be9d623ca5055c356940/2021/04/28/Performance-Dashboard-on-AWS-Figure-1-architecture.jpg)

### Quick updates

**Node 14.x**

You can now use the Node.js 14.x runtime to develop functions in AWS Lambda@Edge. This runtime is in addition to the currently supported Node.js 10.x and Node.js 12.x runtimes. Node.js 14.x, the current Long Term Support (LTS) version of Node.js, uses the new V8 8.1 engine and provides better performance than the previous LTS version, 12.x. In addition, Node.js 14.x supports new features such as nullish coalescing (?? operator), options chaining (?. operator), and diagnostic reporting

**Apache Kafka**

Amazon Managed Streaming for Apache Kafka (Amazon MSK) now supports Apache Kafka version 2.8.0 for new and existing clusters. Apache Kafka 2.8.0 includes several bug fixes and new features that improve performance. Some of the key features include connection rate limiting to avoid problems with misconfigured clients (KIP-612) and topic identifiers which provides performance benefits (KIP-516). There is also an early access feature to replace zookeeper with a self-managed metadata quorum (KIP-500), however this is not recommended for use in production.

**Kubernetes**

AWS Secrets Manager launched the AWS Secrets and Configuration Provider (ASCP), a plugin for the industry-standard Kubernetes’ Secrets Store CSI driver. ASCP enables applications running in Kubernetes pods to retrieve secrets from AWS Secrets Manager easily, without the need for custom code. Once installed, ASCP ensures your applications always receive the most recent version of your secrets as these are rotated. As a result, you automatically benefit from the rotation and lifecycle management features that Secrets Manager provides, without added coding effort. ASCP also enables convenient and secure access to your configurations in AWS SSM Parameter Store. You can read more about this in the blog post from Tracy Pierce, [How to use AWS Secrets & Configuration Provider with your Kubernetes Secrets Store CSI driver](https://aws-oss.beachgeek.co.uk/fu).

### Video of the week

**ROSA**

A couple of must view videos this week, starting off with Bob Wise and Peder Ulander sharing some insights into how Red Hat OpenShift on AWS (ROSA) is helping enterprises simplify, scale cloud projects as they move toward the edge. This was recorded during the Red Hat Summit, and is well worth watching as it covers more than just ROSA but open source at AWS too. Check out the original coverage [here](https://aws-oss.beachgeek.co.uk/g4), or watch the video below from the Cube.

{% youtube sqqg1tOyjtk %}

**AWS Copilot**

The final video is a recording from the Containers from the Couch crew of the Amazon ECS Workshop, where you will learn how to deploy your application to Amazon ECS using AWS Copilot.

{% youtube o8o9Ea9o0aI %}

### Podcast of the week

Jaana Dogan (@rakyll) explains which problems the industry, and especially cloud vendors, try to solve with their investment in open source standards such as OpenTelemetry and gives an update where OpenTelemetry is, the next upcoming milestones and what a bright future with OpenTelemetry being widely adopted could bring.

[The State of OpenTelemetry with Jaana Dogan](https://aws-oss.beachgeek.co.uk/g5)

### Events for your diary

**Cloud Native Rust Day**
**May 3rd**

Rust is a language empowering everyone to build secure, reliable, and efficient software. Rust is becoming more widely used in cloud native, powering everything from lightning-fast service meshes and powerful developer tools to internet-scale distributed databases.

Come explore what makes Rust a fantastic choice for new cloud native development, and learn about how the community uses Rust today. Find out [more and register here](https://aws-oss.beachgeek.co.uk/5y).

**Container Day**
**May 4, 2021 | 10:00AM - 6:00PM CEST**

Container Day x KubeCon is a fully live, virtual day of sessions all about Amazon EKS and Kubernetes at AWS, hosted by Brent Langston and Adam Keller of Containers from the Couch. At this Day Zero KubeCon event, the AWS Kubernetes team will be revealing new launches, demoing products and features, covering best practices, and answering your questions live on Twitch! If you have a question before the event, you can email the team at awscontainerday@amazon.com and maybe get them answered.

Find out more and to register, [click here](https://aws-oss.beachgeek.co.uk/cr).

**An Introduction to Amazon Managed Blockchain**
**5th May**

Amazon Managed Blockchain (AMB) is a fully managed service that makes it easier to build scalable blockchain networks using popular open source frameworks, including Hyperledger Fabric and Ethereum. AMB includes several features and enhancements beyond those provided by the open-source projects on which it is based. It supports public and private blockchain options, each of which favors different use cases. We review reference architectures outlining example applications on both Hyperledger Fabric and Ethereum. In this lecture, you will also hear several customer success stories building solutions on Amazon Managed Blockchain.

Find out more and register [via this link](https://aws-oss.beachgeek.co.uk/dx).

**Building And Maintaining Your Own Secure Container OS**
**May 13th 9am PST**

Curtis Rissi, a Principal Partner SA at AWS will walk attendees through the Bottlerocket (an open-source Linux-based operating system meant for hosting containers) build process, and provide some key use cases for customisation: how to add new configuration options; how to add new packages; how to configure your own update repositories; how to add security policy; and other common customisations. 

Find out more and to register, click [here](https://aws-oss.beachgeek.co.uk/ed)

**Mobile and Front-End Live**
**May 25th, 9:00 - 15:00 PDT**

This is a LIVE streamed event on Twitch  focused on accelerating full-stack mobile and web development. Learn about AWS Amplify, a set of purpose-built tools and services for front-end web and mobile developers that simplify app development. Deep dive into GraphQL and AWS AppSync, a fully-managed GraphQL service that improves app performance and developer productivity.

You can read more about what you can expect in the blog post, [Mobile and Front-End Live, May 25](https://aws-oss.beachgeek.co.uk/f4) and [register via this link](https://aws-oss.beachgeek.co.uk/f3).


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen).