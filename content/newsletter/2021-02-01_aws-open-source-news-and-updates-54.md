---
title: 'AWS open source news and updates #54'
date: '2021-02-01'
tags : [ oss-newsletter ]
---
## February 1st, 2021 - Instalment #54

Newsletter #54. Lots to choose from this week. Catch up with the latest from the Open Distro for Elasticsearch community, an event for your diary in the shape of Innovate AI/ML where I will be covering open source tools in your AI/ML pipeline, and the usual round up of AWS and community open source posts. We have some great open source projects that you need to check out - from tools and utilities that solve real pain points to complete solutions you can use as the base for your projects. Also this week, if you are looking for a fresh challenge, why not take a look at the opening within the JuypterLab team.

As always, I am always eager to hear from you about your projects or blogs/solutions you have been working on so please get in touch if you would like me to share your projects here.

**Open Distro for Elasticsearch**

[Update from the fork team: Jan 28](https://aws-oss.beachgeek.co.uk/3v) Kyle Davis provides an update on where we are at with the getting the public forks ready. The team had a community call which quickly became oversubscribed, but you can see details on the [Open Distro site, Community Meeting - Jan 26, 2021](https://aws-oss.beachgeek.co.uk/3w)

If you want to stay up to date then make sure you check out the meetup schedule - next meeting is on 8th Feb. You can check details [here](https://www.meetup.com/Open-Distro-for-Elasticsearch-Meetup-Group/events/).

Finally, with the recent news of the forking of Elasticsearch and Kibana, check out the [FAQ](https://aws-oss.beachgeek.co.uk/4n) that the Open Distro for Elasticsearch community have put together.

**Job**

Interested in Open Source and Machine Learning? AWS SageMaker open source JupyterLab contribution team is looking for Front End Engineers to join the team in Palo Alto. If you are interested, then take a look at the job description: [Frontend Software Development Engineer - Open Source JupyterLab](https://aws-oss.beachgeek.co.uk/3q)

**Innovate AI/ML**

I have been putting together some blog posts to support my session at the [Innovate AI/ML event](https://aws.amazon.com/events/aws-innovate/machine-learning/online/emea/?sc_channel=em&sc_campaign=EMEA_FIELD_WEBINAR_innovate-AIML_20210224_7014z000001MJbu&sc_medium=em_&sc_content=REG_t1_field&sc_geo=emea&sc_country=mult&sc_outcome=reg&sc_publisher=aws&trkCampaign=emea21_innovatemlq1&trk=em_emea21_innovatemlq1_ricardosueiras) happening on Feb, 24th. I will be covering using open source tools in your AI/ML pipeline, and taking a look at Apache Airflow specifically.

Here are the blog posts:

* [Automating the installation and configuration of Amazon Managed Workflows for Apache Airflow](https://aws-oss.beachgeek.co.uk/3h)
* [Working with Permissions](https://aws-oss.beachgeek.co.uk/3n)
* [Accessing Amazon Managed Workflows for Apache Airflow](https://aws-oss.beachgeek.co.uk/3o)
* Interacting with Amazon Managed Workflows for Apache Airflow via the command line

I will be adding more before my session on the 24th. Use the [sign up link here](https://aws.amazon.com/events/aws-innovate/machine-learning/online/emea/?sc_channel=em&sc_campaign=EMEA_FIELD_WEBINAR_innovate-AIML_20210224_7014z000001MJbu&sc_medium=em_&sc_content=REG_t1_field&sc_geo=emea&sc_country=mult&sc_outcome=reg&sc_publisher=aws&trkCampaign=emea21_innovatemlq1&trk=em_emea21_innovatemlq1_ricardosueiras) to register for this event.

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heros: Chang Ho Jung, Emile Nijssen, Sofian Hamiti, Shreyas Subramanian, Keith Andruch, Andrew Park, Fei Lang, Ray Liu, Nikolai Kolesnikov, Ugur KIRA, Dejun Hu, TP Kohli, Jim Mlodgenski, Kinnar Sen, Tarun Kumar,  Frank Liu, Matt Briggs, Mischa Spiegelmock, Rehan van der Merwe, Ian McKay and Artyom Pervukhin.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

**cfn-diagram**

[cfn-diagram](https://aws-oss.beachgeek.co.uk/4r) is an open source tool from the MatHem team that provides a cli tool to visualise CloudFormation/SAM/CDK templates as diagrams. I shared this project a while ago, but it came up again this week so if you missed it the first time, make sure you check it out this time.

![demo](https://raw.githubusercontent.com/mhlabs/cfn-diagram/master/demo.gif)

**cfn-stack-rename**

[cfn-stack-rename](https://aws-oss.beachgeek.co.uk/4d) AWS Hero and prolific open source builder Ian McKay has released a new project that lets you rename your CloudFormation stack. Ian provides a quick overview of how it works as well as some gotchas to look out for when trying this out.

**serverless-stack**

[serverless-stack](https://aws-oss.beachgeek.co.uk/4e) Serverless Stack Toolkit is an open source tool that allows you to build serverless apps using AWS CDK. Check out the detailed documentation with lots of examples [here](https://aws-oss.beachgeek.co.uk/4f)

**awsautodns**

[awsautodns](https://aws-oss.beachgeek.co.uk/4q) awsautodns is a tool that allows an AWS EC2 Instance to automatically register it's IP address in a Route53 Hosted Zone at startup. The install script creates a oneshot service, awsautodns.service, and sets it to start at boot, by installing it to multi-user.target. awsautodns is useful for avoiding fees associated with using an elastic IP address.

**aws-iot-device-client**

[aws-iot-device-client](https://aws-oss.beachgeek.co.uk/4g) The AWS IoT Device Client is an open-source, modular software written in C++ that you can compile and install on your Embedded Linux based IoT devices to access AWS IoT Core, AWS IoT Device Management, and AWS IoT Device Defender features by default. It serves as a reference implementation for your IoT devices to work with AWS IoT services, with operational best practices baked in

**s3fetch**

[s3fetch](https://aws-oss.beachgeek.co.uk/4h) s3fetch is a simple & fast multi-threaded S3 download tool, with a breakdown on the project page of how they have achieved the speed. This is a different project from last week.

**cloudfront-autoindex**

[cloudfront-autoindex](https://aws-oss.beachgeek.co.uk/4i) is a project from Artyom Pervukhin that solves a very particular pain point. Read the problem space that he has documented and see if you are having the same problems - he might just save you some time.

**porter**

[porter](https://aws-oss.beachgeek.co.uk/4j) this looks like a very nice project that anyone familiar with the Heroku model will be interested in. Porter is a Kubernetes-powered PaaS that runs in your own cloud provider such as AWS.  Porter brings the Heroku experience to Kubernetes. Check out this [thread](https://aws-oss.beachgeek.co.uk/4k) provides some additional discussion on this topic that is well worth reading.

**amazon-kinesis-video-streams-media-screencast-android**

[amazon-kinesis-video-streams-media-screencast-android](https://aws-oss.beachgeek.co.uk/4o) this open source project will show you how you can screencast your mobile app using Kinesis Video Stream with WebRTC in Android. Chang Ho Jung has also put together a detailed blog post to walk you through the process,[ How to screencast apps using Amazon Kinesis Video Streams with WebRTC on Android](https://aws-oss.beachgeek.co.uk/4p)

### Video of the week

**Juypter Notbooks on Amazon Lightsail**

This is a great new video blog from Julien Simon, always focused on helping you optimise whether that is performance or cost. In this post, he shows you how you can run Juypter notebooks on Amazon Lightsail for a very small amount indeed.

{% youtube vHjjuBJ5BoM %}

**ROS**

Check out this great video tutorial on how to run a simulation on AWS RoboMaker. Perfect if you are just starting out in ROS and want to know some of the tools and terminology.

{% youtube CocGUfhp-I8 %}

### Blog posts from the community and customers

**AWS CDK**

A couple of AWS CDK posts this week. First up we have [Web Services with AWS CDK](https://aws-oss.beachgeek.co.uk/48) Mischa Spiegelmock with a post that brought a smile to my face, introducing an open source application called Cursed Webring, featuring "the worst of the internet". So what I hear you say. Well, Mischa shows you how you can use the AWS CDK to build this application. Full source code is available in the [GitHub repository](https://aws-oss.beachgeek.co.uk/49) too. I guess the question I have is will this Newsletter ever make it into the Cursed Webring!

Following that we have AWS Community Hero Rehan van der Merwe with a post, [4 Methods to configure multiple environments in the AWS CDK](https://aws-oss.beachgeek.co.uk/4a) in which you will learn  different methods that can be used to pass configuration values to the AWS CDK. I will not give away what those four methods are, you will just have to read the post. Like all good open source posts, source code over at [his GitHub repo](https://aws-oss.beachgeek.co.uk/4b).

**AWS Amplify**

[Building a Ron Swanson Quote App on Amplify with Javascript and GraphQL](https://aws-oss.beachgeek.co.uk/4c) from my friends at Steamhaus, Paul Flowers with a great post with a hint of comedy (a winning combination) that shows you how easy it is to create a simple API that will be return Ron Swanson quotes to be displayed by a React frontend. Who (Why?) Ron Swanson, well only Paul will know that but this is a great fun post and a great way to learn how you can use AWS Amplify to quickly put something like this together.

**Linux OS for Kubernetes**

In this post from Talos Systems CEO, Steve Francis, [A Guide to Linux Operating Systems for Kubernetes](https://aws-oss.beachgeek.co.uk/40) he provides some insights into the specific needs around Linux operating systems within Kubernetes. If you want to know a little more as to what the AWS open source project Bottlerocket is helping to address, read this post and hopefully it will be clearer.

**Grafana**

[Monitoring AWS Elastic Beanstalk Memory and Disk Usage in Grafana](https://aws-oss.beachgeek.co.uk/4m) Emile Nijssen shows you how easy it is to setup a Grafana dashboard to display your CloudWatch metrics, in this case, metrics that the CloudWatch agent in an Elastic Beanstalk instance is generating.

### AWS open source posts

**Bottlerocket**

[How the Bottlerocket build system works](https://aws-oss.beachgeek.co.uk/47) is great post from Matt Briggs on Bottlerocket. Bottlerocket is an open source, special-purpose operating system designed for hosting Linux containers. This post dives deep into the build system for Bottlerocket, taking a look at how it uses Cargo, the Rust package manager and some of the tooling used. This is a great way to understand in more detail how this works for your own Rust projects potentially.

**MLflow**

[Managing your machine learning lifecycle with MLflow and Amazon SageMaker](https://aws-oss.beachgeek.co.uk/3x) Sofian Hamiti and Shreyas Subramanian take a look at an open source solution to helping data scientists manage their machine learning experiments. I took a look at this early in the year and hope to do some blog posts around it soon. In the meantime, this post shows how the open-source platform MLflow helps data scientists collaborate and share experiment results in order to find a solution to a business need. Great post, so read on to find out more about MLflow and how you can integrate this with Amazon SageMaker.

![arch](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2020/12/05/ML-1367-2.jpg)

**Deep Java Library**

[Model serving in Java with AWS Elastic Beanstalk made easy with Deep Java Library](https://aws-oss.beachgeek.co.uk/46) Frank Liu has put together this guide to show you how to deploy a model on Elastic Beanstalk using the Deep Java Library (DJL), using an example of sending an image through a post call to get inference results on what the image contains.

**Apache Airflow**

[Orchestrating analytics jobs on Amazon EMR Notebooks using Amazon MWAA](https://aws-oss.beachgeek.co.uk/3y) Fei Lang and Ray Liu have put together another great post that shows how to use Amazon Managed Workflows for Apache Airflow (Amazon MWAA) to orchestrate analytics jobs on EMR Notebooks. They walk you through an end to end solution and is essential reading if you are just getting to grips with what Apache Airflow can do for you.

![arch](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2021/01/26/BDB-1140-1.jpg) 

**Apache Cassandra**

[Compress and conquer with Amazon Keyspaces (for Apache Cassandra)](https://aws-oss.beachgeek.co.uk/41) Nikolai Kolesnikov with a helpful post that shows you how to compress your data using freely available compression tools and store that compressed data in Amazon Keyspaces. To help deliver fast performance, Amazon Keyspaces has a 1 MB row-size quota.  What if you already have rows larger than 1 MB in your existing Cassandra tables? To reduce the size of these rows, you can compress one or more large columns. Compressing large columns reduces your storage costs, improves performance, reduces I/O and network usage, and enables you to fit the data within the Amazon Keyspaces row quota. At that is what Nikolai will walk you through in this post.

**Apache Spark**

[Running cost optimized Spark workloads on Kubernetes using EC2 Spot Instances](https://aws-oss.beachgeek.co.uk/44) Kinnar Sen takes a look at how to run Apache Spark workloads in a resilient, scalable and cost optimised way using Amazon EKS service in conjunction with Spot Instances. Apache Spark is an open-source, distributed processing system used for big data workloads, and supports Kubernetes as one of its cluster managers allowing you to allocate and schedule your analytics resources. This is a detailed walkthrough, so set some time aside as you will cover a lot of ground.

![arch](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2021/01/21/eks-blog-1.png)

**Fluent Bit**

[Fluent Bit Integration in CloudWatch Container Insights for EKS](https://aws-oss.beachgeek.co.uk/42) Ugur KIRA, Dejun Hu and TP Kohli collaborate on this post that introduces CloudWatch Container Insights, which enables you to explore, analyze, and visualize your container metrics, Prometheus metrics, application logs, and performance log events through automated dashboards in the CloudWatch console. Fluent Bit is an open source and multi-platform log processor and forwarder that allows you to collect data and logs from different sources, and unify and send them to different destinations including CloudWatch Logs. In this post find out how these two integrate to help you considerably enhances your observability and debugging capabilities in your container workloads.

**PostgreSQL**

[Getting more with PostgreSQL purpose-built data types](https://aws-oss.beachgeek.co.uk/43) Jim Mlodgenski explores some of PostgreSQL’s purpose-built types, covering UUID and Network Addresses, Geospatial and Chemistry. This is just the tip however, and as Jim says in this post "PostgreSQL’s extensible architecture will allow new types to be created in the future as PostgreSQL moves into more industries requiring specialized data handling."

**AWS SAM**

[Building a Jenkins Pipeline with AWS SAM](https://aws-oss.beachgeek.co.uk/45) Tarun Kumar is here with a post that shows how to set up a multi-stage pipeline on a Jenkins host for a serverless application, using the AWS Serverless Application Model (AWS SAM).

![arch](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2021/01/22/1-workflow-1.png)

### AWS Partners

**Rancher and Amazon EKS**

[Optimizing Your Kubernetes Clusters with Rancher and Amazon EKS](https://aws-oss.beachgeek.co.uk/3z) Keith Andruch and Andrew Park take a look at how combining Rancher with Amazon EKS provides a solution that allows enterprises to overcome common technical challenges associated with Kubernetes, including learning and resourcing gaps, onboarding, and operational difficulties.

![arch](https://d2908q01vomqb2.cloudfront.net/77de68daecd823babbb58edb1c8e14d7106e83bb/2021/01/19/Rancher-Amazon-EKS-2.jpg)

### AWS Case Studies

[Expedia Group Speeds Up Vendor Payment Transactions from 1 Day to Seconds](https://aws-oss.beachgeek.co.uk/3t) is a case study on how they are using open source technologies, and how these are helping them break free of legacy, proprietary databases in order to achieve significant business value. To help migrate they are using a tool that has an open source community edition, [Flyway](https://aws-oss.beachgeek.co.uk/3u). Check them out if you are also thinking about migrating and want to explore your database migration options.

[How INESC TEC tests and deploys ROS applications with AWS RoboMaker](https://aws-oss.beachgeek.co.uk/4l) Rafael Arrais, Project Manager at INESC TEC describes how robotics researchers at INESC TEC in Portugal are using AWS RoboMaker to set up a simulation-based regression testing CI/CD pipeline, showing you how they used simulation to scale testing, speed up dev velocity and reduce errors.

![demo](https://d2908q01vomqb2.cloudfront.net/a9334987ece78b6fe8bf130ef00b74847c1d3da6/2021/01/30/ezgif-3-1c7f137cafc3.gif)

### Quick updates

**PostgreSQL**

Amazon Aurora with PostgreSQL compatibility now supports major version 12. PostgreSQL 12 includes better index management, improved partitioning capabilities, and the ability to execute JSON path queries per SQL/JSON specifications. It also enables nondeterministic collations that support case-insensitive and accent-insensitive comparisons for ICU provided collations, most common-value statistics for improved query plans, creation of generated columns that compute values with an expression, and many additional features.

This release also updates extensions including Address_standardizer, Address_standardizer_data_us, Amcheck, Citext, Hll, Hstore, Ip4r, Pg_repack, Pg_stat_statements, Pgaudit, Pglogical, Pgrouting, Plv8, Postgis, Postgis_tiger_geocoder, Postgis_topology.

**In place upgrades**

You can perform an in-place upgrade of your Amazon Aurora database cluster from PostgreSQL major version 11 to 12. Instead of backing up and restoring the database to the new version, you can upgrade with just a few clicks in the Amazon RDS Management Console or by using the AWS SDK or CLI.

**Fluent Bit**

AWS announces the availability of Fluent Bit support for Amazon CloudWatch, a fully managed, pay-as-you-go monitoring and observability service for resources running on AWS and on-premises. CloudWatch Container Insights and Log Insights enables you to explore, analyse, and visualise your container logs collected from the Fluent Bit processor. Container Insights also provides access to the automated dashboards that summarise the performance and availability of the FluentBit Daemon set running on Amazon Elastic Kubernetes Service (EKS) and Kubernetes. With few clicks in the AWS Management Console, you can start collecting Fluent Bit logs in CloudWatch to monitor and troubleshoot containers.

**Elasticsearch**

Amazon Elasticsearch Service now supports encryption of data at rest and node-to-node encryption on existing domains, enabling organisations hosting sensitive workloads to meet stringent security and compliance requirements.

Read more about the announcement, [Amazon Elasticsearch Service extends encryption at rest and node-to-node encryption to existing domains](https://aws-oss.beachgeek.co.uk/3s)

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen).
