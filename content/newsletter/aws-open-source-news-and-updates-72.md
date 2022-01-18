---
title: 'AWS open source news and updates #72'
date: '2021-06-14'
tags : [ oss-newsletter ]
---
## 14th June, 2021 - Instalment #72

Newsletter #72.

This week we have new open source projects such as Lift, that makes it super easy to deploy applications to production, a couple of new mods for the Steampipe project that let you do cost optimisation and security auditing, a nice project for tmux fans as well as a project that will get you started with ECS Anywhere. Community and AWS posts covering security, DevOps and IoT/Robotics, as well as Kubernetes, Open Shift, Apache Airflow, Linux and many more. And of course, later this week we have Open@Amazon, a free, live, event on Wednesday June 16th that starts at 9am on EDT.

If you have not yet registered for Open@Amazon then don't worry, there is plenty of time. I hope I will see many of you on Wednesday for this event which is shaping up to be a really fantastic celebration of great open source builders and projects, covering a variety of different open source technologies. Check out the events section for more details.


### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes:  Eric Greene, Rafa Xu, Yuan Shi, Elizabeth Nguyen, Colm Harte, Victor Julien, Kelley Misata, Shakeel Ahmad, Maritza Mills, Brian Carlson, Matt Laver, Jeremy Wallace, Imaya Kumar Jagannathan, Vikram Venkataraman, Alistair McLean, Jon Handler, Prashant Agrawal, Rodrigue Koffi and Rafael Pereyra, Francisco Gonzalez, Matthew Miller, Vu Dao, Vishesh Jindal, Petr Pridal, Andre Dufour, Ramses Alexander Coraspe Valdez, Jay Yeras, David Boeke, elpy1, Matthieu Napoli, Jason Umiker, Yehuda Cohen, Vani Eswarappa, Kostis Kapelonis and Curtis Rissi. 

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

**lift**

[lift](https://aws-oss.beachgeek.co.uk/mi) is an exciting new open source project from Theodo that I noticed last week thanks to a tweet from Matthieu Napoli. Lift is a plugin that leverages the AWS CDK to expand the Serverless Framework beyond functions. This allows you to quick deploy production-ready websites, queues, storage buckets and more with a few lines in serverless.yml.

**ssm-multi-tmux**

[ssm-multi-tmux](https://aws-oss.beachgeek.co.uk/mj) this project from elpy1, is perfect for you tmux fans. It enables you to run an interactive AWS SSM command in synchronised tmux panes on one or more EC2 instances by specifying the autoscaling group name or tag key and value. Check out the quick demo to see how this looks executing htop on an autoscaling group containing 4 instances:

![demo](https://github.com/elpy1/ssm-multi-tmux/blob/master/demo/multissm.gif?raw=true)

**Steampipe mods**

Thank you David Boeke for sharing with me a couple of new open source projects that built on top of steampipe, an open source project I previous covered, that lets you use SQL to query your AWS environment.

* [steampipe-mod-aws-thrifty](https://aws-oss.beachgeek.co.uk/mg) - this Steampipe mod checks your AWS account(s) for unused and under-utilised resources, with many (25+) cost savings/avoidance checks
* [steampipe-mod-aws-compliance](https://aws-oss.beachgeek.co.uk/mh) - open source scanning of 200+ security and compliance checks, that lets you run individual configuration, compliance and security controls or full compliance benchmarks for CIS and PCI across all your AWS accounts.

**ecsanywhere-dind**

ecsanywhere-dind Jason Umiker has put together this repository that will help you quickly get started with running ECS Anywhere, and builds an Amazon Linux 2 container that has both systemd and docker that can serve as an ECS Anywhere sandbox.

### Community open source posts

**Docker registry**

[Reducing data transfer costs with a Docker registry cache](https://aws-oss.beachgeek.co.uk/m9) this is a super nice post from Vishesh Jindal on how they were able to reduce the cost of their AWS bill by first identifying an area of optimisation, and then putting together this creative solution that both helped them reduce the cost put also improve the performance of obtaining container images. This is a must read post this week.

**Kubernetes**

In last weeks newsletter I covered the first of a two part series from Garry Stafford exploring open-source observability tools you can integrate with the Istio service mesh, and he has published the follow up post, [Kubernetes-based Microservice Observability with Istio Service Mesh: Part 2](https://aws-oss.beachgeek.co.uk/ml)

![arch](https://miro.medium.com/max/700/1*ZPqwYhuZhICm0Z1ehdvKhA.png)

[IAM Service Account For aws-node DaemonSet](https://aws-oss.beachgeek.co.uk/m8) prolific blogger and open source builder Vu Dao has put together this post on how to configure the Amazon VPC CNI plugin in your Kubernetes environments to use IAM roles for service accounts. He walks you step by step on what you need to do.

**Linux**

[Running ECS on CIS Hardened Amazon Linux](https://aws-oss.beachgeek.co.uk/mm) nice post from Yehuda Cohen that shows what customer obsession looks like, as he works to get Amazon ECS up and running on the CIS hardened Amazon Linux images and runs into some problems. 

**MapLibre GL Native**

MapLibre GL Native is a community led fork derived from mapbox-gl-native prior to their switch to a non-OSS license, for both Android and iOS, developed by the MapTiler team in cooperation with Amazon, Facebook, Microsoft, and the MapLibre community. Following on from [this tweet](https://aws-oss.beachgeek.co.uk/ma) from Andre Dufour, was the announcement post from Petr Pridal at MapTiler, [MapLibre GL Native: open-source mobile SDK for Android and iOS](https://aws-oss.beachgeek.co.uk/mb) that shares more detail about the community, the project and resources on how you can get started. Check out the GitHub repo, [maplibre-gl-native, here](https://aws-oss.beachgeek.co.uk/mc).

**Snyk**

[Automate vulnerability scanning in AWS CodePipeline with Snyk](https://aws-oss.beachgeek.co.uk/md) Jay Yeras with an import post this week on how you can use [Snyk](https://aws-oss.beachgeek.co.uk/me) (an open source tool that helps you to find, fix and monitor known vulnerabilities in open source) and integrate with AWS CodePipeline so you can easily integrate security testing as part of your automated delivery pipelines. This post shows you how to set this up, and if you are not already doing this today, this is a good post to get you started.

**Apache Airflow**

Two posts this week on Apache Airflow. Kicking things off is this amazing post, [Building an ETL pipeline with Apache Airflow and Visualizing AWS Redshift data using Microsoft Power BI](https://aws-oss.beachgeek.co.uk/mf) from Ramses Alexander Coraspe Valdez that walks you through creating an epic solution on managing your Uber expenses (both Uber Eats and Rides) by incorporating Apache Airflow to orchestrate how to move and transform that data and then finally how you can visualise it. This is another must read post this week.

[Working with Amazon EKS and Amazon Managed Workflows for Apache Airflow (MWAA) v2.x](https://aws-oss.beachgeek.co.uk/m7) this is a quick post I threw together last week, that came out of some conversation in the Apache Airflow open source slack community (if you use or are even experimenting with Apache Airflow, you should most certainly check it out, lots of deep expertise on all things Apache Airflow related). This post is an update on how to get the Amazon EKS example up and running, and builds upon the existing code example in the MWAA docs.

### AWS and Amazon open source posts

**Suricata**

Suricata is a fast, robust, open source network threat detection engine that includes real-time intrusion detection (IDS), an inline intrusion prevention system (IPS), network security monitoring (NSM), and offline packet capture (pcap) processing. In this post, [Scaling threat prevention on AWS with Suricata](https://aws-oss.beachgeek.co.uk/lw) Victor Julien, Kelley Misata, Shakeel Ahmad, and Maritza Mills introduce you to Suricata and to the Open Information Security Foundation, which supports it. They also explain the important role open source security projects have in the security community as a whole and walked through an example of how you can import open source rulesets into AWS Network Firewall.

**AWS Distro for OpenTelemetry**

[Using AWS Distro for OpenTelemetry collector for cross-account metrics collection on Amazon ECS](https://aws-oss.beachgeek.co.uk/m3) in this post, Rodrigue Koffi and Rafael Pereyra share with you how to use the AWS Distro for OpenTelemetry (ADOT) agent to collect application and platform metrics for workloads running on Amazon ECS.

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/06/04/koffir_otel_cross-account-metrics_ecs-f1.png)

**COVID**

Colm Harte, Technical Director at NearForm wrote in the AWS open source blog last week, [How open source on AWS helped NearForm quickly build and scale its Covid-19 contact tracing app](https://aws-oss.beachgeek.co.uk/lv) sharing why and how they use open source and AWS to help build digital products at speed and scale and then exploring how open source helps to build effective, trustworthy applications.

**Rust**

[Building an ARM64 Rust development environment using AWS Graviton2 and AWS CDK](https://aws-oss.beachgeek.co.uk/m1) Alistair McLean's post aims to show how you can set up the Visual Studio Code-based Code Server IDE, running on a Graviton2 EC2 instance, and use this environment for Rust development, including how you can build and install the rust-analyzer and CodeLLDB debugger plugins.

![arch](https://d2908q01vomqb2.cloudfront.net/7719a1c782a1ba91c031a682a0a2f8658209adbf/2021/05/13/blog_arch.png)

**OpenShift**

[Integrate ROSA with AWS CodeCommit](https://aws-oss.beachgeek.co.uk/mn) Vani Eswarappa has put together this post that demonstrates how to integrate Red Hat OpenShift Service on AWS (ROSA) with AWS CodeCommit.

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2021/06/08/Screen-Shot-2021-05-17-at-11.06.30-PM.png)

**Bottlerocket**

[Run Codefresh Pipelines on Amazon EKS Using Bottlerocket OS](https://aws-oss.beachgeek.co.uk/mo) this collaboration between Kostis Kapelonis (Developer Advocate at Codefresh) and Curtis Rissi from AWS show you how to deploy Codefresh Runners on Amazon EKS using Bottlerocket-based nodes to help scale your build environments quickly and benefit from Bottlerocket OS’s hardened security and simplified management. Codefresh is a deployment platform specifically built for containers and Kubernetes, and you can use Codefresh to create CI/CD pipelines that take an application from source code all the way to production. 

**DevOps**

[Choosing a Well-Architected CI/CD approach: Open-source software and AWS Services](https://aws-oss.beachgeek.co.uk/lx) Brian Carlson continues his series of posts that discuss how to make informed decisions when choosing to implement open-source tools on AWS services, adopt managed AWS services, or use a combination of both - through the view of the Well Architected framework. Brian looks at key considerations for evaluating open-source software and AWS services from the perspectives of a startup company and a mature company as examples. Great post, really enjoyed reading this one.

**.NET on AWS Graviton 2**

[Build and deploy .NET web applications to ARM-powered AWS Graviton 2 Amazon ECS Clusters using AWS CDK](https://aws-oss.beachgeek.co.uk/ly) Matt Laver has put together this post that demonstrates the low barrier to entry for .NET developers wanting to apply modern application development practices, using AWS CDK to define cloud applications as code, taking advantage of the price performance of ARM-based processors such as Graviton.

![arch](https://d2908q01vomqb2.cloudfront.net/7719a1c782a1ba91c031a682a0a2f8658209adbf/2021/06/02/cdk-dotnet.jpeg)

**Java/Jackson**

[The AWS SDK for Java version 1.12 upgrades its dependency on Jackson](https://aws-oss.beachgeek.co.uk/m5) Matthew Miller shares news on the minor version of AWS SDK for Java from 1.11 to 1.12 in order to upgrade the SDK’s dependency on the popular third-party JSON library, Jackson. He covers why we are doing this and how this might affect your applications.

**Grafana**

[Monitoring hybrid environments using Amazon Managed Service for Grafana](https://aws-oss.beachgeek.co.uk/m0) Imaya Kumar Jagannathan and Vikram Venkataraman have put together this really nice post that walks you through the steps to visualise metrics from an Azure Cloud environment to Amazon Managed Service for Grafana (AMG) and create alert notifications in AMG to be sent to Amazon Simple Notification Service (Amazon SNS) and Slack.

![arch](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2021/06/07/fig7-1024x482.png)

**Elasticsearch**

[Monitor your Amazon ES domains with Amazon Elasticsearch Service Monitor](https://aws-oss.beachgeek.co.uk/m2) Jon Handler and Prashant Agrawal show you how you can deploy and use an open source solution, the Amazon Elasticsearch Service Monitor, as way to monitor your Amazon ES infrastructure. Great post and very clear to follow as well as providing guidance on what costs you can expect to run this solution.

![arch](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2021/06/04/bdb1578-monitor-es-3.png) 

**Redis**

[RedisConf Wrap Up](https://aws-oss.beachgeek.co.uk/lu) Elizabeth Nguyen shares details and videos of a number of sessions we delivered and collaborated on as part of the recent RedisConf which we were a proud platinum sponsor of. Sessions included Building for high availability and extreme performance with Redis cluster, Microservices and Redis: A love story, Mitigating and preventing connection storms to keep your Redis cluster highly available, Working without a net: Extreme use cases of Redis and Better together: How AWS is helping build a stronger open source community. Lots of great sessions, so check them out.

{% youtube CB2HEa6wS0Q %}

**AWS IoT EduKit**

AWS IoT EduKit an IoT device and reference hardware that makes it easy for developers, from students to experienced professionals, to get hands-on experience building end-to-end IoT applications. If you want to take part in this really cool Hackathon, [Reinventing healthy spaces with AWS IoT EduKit](https://aws-oss.beachgeek.co.uk/m6), where you will build an open source healthy spaces solution using the M5Stack Core2 for AWS IoT EduKit reference hardware, AWS IoT Core, and at least one other cloud service. There are of course prizes for the best submissions, and details of how you can apply for the hardware as well as supporting resources. 

To get you ready, then check out this post from Francisco Gonzalez, [How to access and display files from Amazon S3 on IoT devices with AWS IoT EduKit](https://aws-oss.beachgeek.co.uk/m4) as walks you through one of the sample tutorials available as part of the AWS IoT EduKit. Starting with one of the tutorial projects, Francisco builds this out into something more useful to provide you with ideas of how you can do something similar for your own projects.

![arch](https://d2908q01vomqb2.cloudfront.net/f6e1126cedebf23e1463aee73f9df08783640400/2021/06/04/Slide1.jpeg)

**ROS**

[Deploy and Manage ROS Robots with AWS IoT Greengrass 2.0 and Docker](https://aws-oss.beachgeek.co.uk/lz) Jeremy Wallace introduces you to a new way to deploy and manage robot software on production fleets at scale using AWS IoT Greengrass 2.0. AWS IoT Greengrass 2.0 is an open-source edge runtime and cloud service that reduces complexities when deploying and managing applications on robots. With AWS IoT Greengrass 2.0, developers can add local compute, messaging, and data management capabilities to their robotics fleets.

![arch](https://d2908q01vomqb2.cloudfront.net/a9334987ece78b6fe8bf130ef00b74847c1d3da6/2021/06/09/gg_deploy_01_ota_architecture_diagram.jpeg)

This is a hands on keyboard type of post, my favourite!

**Open Data on AWS**

[Exploring the UniProt protein knowledgebase with AWS Open Data and Amazon Neptune](https://aws-oss.beachgeek.co.uk/lt) Eric Greene, Rafa Xu, and Yuan Shi collaborate on this post showing you how you can ingest Open Data sets available from the Open Data at AWS registry into your own Amazon Neptune database and then query the data with SPARQL, creating new relationships in the data, and visualising the data as a graph.

![demo](https://d2908q01vomqb2.cloudfront.net/c5b76da3e608d34edb07244cd9b875ee86906328/2021/05/29/Example-5-results.png)


### Quick updates

**ActiveMQ**

You can now launch Apache ActiveMQ 5.16.2 brokers on Amazon MQ. This version update to ActiveMQ contains several fixes, improvements, and new features compared to the previously supported version, ActiveMQ 5.15.15.

**Apache Cassandra**

Amazon Keyspaces (for Apache Cassandra), a scalable, highly available, and fully managed Apache Cassandra–compatible database service, is now in scope for AWS System and Organization Controls (SOC) Reports to help you run highly regulated Cassandra workloads more easily.

AWS SOC Reports are independent third-party examination reports that demonstrate how AWS achieves key compliance controls and objectives. The purpose of these reports is to help you and your auditors understand the AWS controls established to support operations and compliance. Now, you can run Cassandra workloads that require the use of in-scope services for SOC 1, SOC 2, and SOC 3 reports more easily by using a fully managed and serverless database service.

Amazon Keyspaces is in scope for AWS SOC 1, SOC 2, and SOC 3 Reports in all AWS Regions where AWS offers Keyspaces. To learn more, see Compliance Validation for Amazon Keyspaces (for Apache Cassandra).

### Events for your diary

This week, make sure you attend Open@Amazon. I am super excited about this event, so check out the blog post to find out more about the sessions and see you there on Wednesday.

**Open@Amazon**
**June 16th, 9:00am - 5:00PM EDT**

If you missed it last week, next week we are running Open@Amazon, a celebration of open source on AWS with a fabulous cast of speakers, a fantastic broad set of topics and the event will be fully live so you can get your chance to interact with the speakers and the broader open source and AWS community. Check out the blog post, [What’s up with open source at AWS? Attend Open@Amazon live on Twitch June 16](https://aws-oss.beachgeek.co.uk/jo) 

**Cloud Native Day**
**23rd September, Bern Switzerland**

What is this, an in person event returning? A stellar line up including our own Michael Hausenblas, an event looking at CNCF projects and the future of IT. 


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen).