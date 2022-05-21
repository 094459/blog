---

title: 'AWS open source news and updates #113'
date: '2022-05-20'
tags : [ oss-newsletter, aws open source, OpenZFS, Apache Kafka, Kubernetes, FreeRTOS, KubeFlow, Envoy, OpenSSF, Apache Spark, AWS Copilot, Amazon EMR, Kotlin, Amazon Corretto, DGL, Jaeger, ArgoCD, ROSA, Node-Red]

---

## May 13th, 2022 - Instalment #113

Newsletter #113. 

A little later than usual this week thanks to KubeCon, #113 of the AWS open source newsletter provides you with yet more new open source projects. "aws-iam-utils" is a Python library to help you work with IAM, "iot-app-kit" is a new IoT visualisation framework, "s3pathlib-project" that provides the Pythonic objective oriented programming (OOP) interface to manipulate AWS S3 object / directory, "collaboration-chambers-on-aws" which is a cool and very comprehensive project to help you do Scale-Out Computing on AWS, and many more!

Also featured this week is content covering OpenZFS, Apache Kafka, Kubernetes, FreeRTOS, KubeFlow, Envoy, OpenSSF, Apache Spark, AWS Copilot, Amazon EMR, Kotlin, Amazon Corretto, DGL, Jaeger, ArgoCD, ROSA, as well as this weeks featured video that features my favourite open source project, Node-Red.

Make sure you check out the events, looking forward to Airflow Summit next week. Check out my session on the Monday, as well as all the other great sessions.

**ApacheCon**

The call for papers (cfp) for ApacheCon closes on Monday, 23rd May so there is still time to put together a submission. This year features a new data engineering track, but there are many other tracks including Community, Internet of Things, Cloud, as well as some of your favourite Apache projects such as Tomcat, Pulsar and more.

Give this some thought and when ready, [check out this page](https://aws-oss.beachgeek.co.uk/1p5) to submit your proposal.

(Big thanks to Ismael Mejia for nudging me to include this)


### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Ismael Mejia, Sudhir Jena, Jesse Cox, Michael Hausenblas, Annerieke Kortier, Yang Wanxian, Yiming Peng, Bo Xiong, Ovidiu Valeanu, Ryan Niksch, Mark Taylor, Ian Packer,  Arnaud Lauer, Vikram Venkataraman, Imaya Kumar Jagannathan, Rodrigue Koffi, Munish Dabra, Ramesh Kumar, Sean Kane, Juan Sebastián Urrego Escobar, Liz Fong-Jones, and Mohamed Radwan.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest open source projects

#### Community

**aws-iam-utils**

[aws-iam-utils](https://aws-oss.beachgeek.co.uk/1pl) is an open sourced Python library with some utility functions for working with AWS IAM policies. [Jonny](https://github.com/jtyers) wrote this because he wanted a simpler solution to what was already available and wanted an easy and quick way to interact without having to use the API. The docs cover what you can do with this in more detail, so check this project out.

#### Tools

**s3pathlib-project**

[s3pathlib-project](https://aws-oss.beachgeek.co.uk/1pr) is the python package provides the Pythonic objective oriented programming (OOP) interface to manipulate AWS S3 object / directory. Check out the details [documentation](https://s3pathlib.readthedocs.io/en/latest/) to find out more.

**collaboration-chambers-on-aws**

[collaboration-chambers-on-aws](https://aws-oss.beachgeek.co.uk/1pq) this repo provides the code needed for the Scale-Out Computing on AWS. This is a solution that helps customers more easily deploy and operate a multiuser environment for computationally intensive workflows.

**iot-app-kit**

[iot-app-kit](https://aws-oss.beachgeek.co.uk/1p3) this project is a development library for creating web applications to visualise industrial data. You can quickly get up to speed by checking out the blog post from Sudhir Jena, [Build IoT web applications using AWS IoT Application Kit](https://aws-oss.beachgeek.co.uk/1p4) which provides everything you need to know to get up and running. [hands on]

![example of iot-app-kit being used](https://d2908q01vomqb2.cloudfront.net/f6e1126cedebf23e1463aee73f9df08783640400/2022/05/08/AWS-IoT-App-Kit-Demo-Screenshot-1-1024x602.png)

**aws-systemsmanager-automate-hybrid-activations**

[aws-systemsmanager-automate-hybrid-activations](https://aws-oss.beachgeek.co.uk/1pm) AWS Systems Manager (formerly known as SSM) is an AWS service that you can use to view and control your servers on AWS cloud and and on-premise infrastructure. To set up servers and virtual machines (VMs) in your hybrid environment as managed instances, you create a managed-instance activation. This repo contains a solution to help you automate the System Manager Hybrid Activations creation.

![architecture of ssm](https://github.com/aws-samples/aws-systemsmanager-automate-hybrid-activations/blob/main/Images/architecture.jpg?raw=true)

### Demos, Samples and Workshops

**amazon-ivs-chat-web-demo**

[amazon-ivs-chat-web-demo](https://aws-oss.beachgeek.co.uk/1pp) provides the code and details of how to set this up for a demo web application intended as an educational tool to demonstrate how you can build a simple live video and chat application with Amazon IVS.

![demo chat app screenshot](https://github.com/aws-samples/amazon-ivs-chat-web-demo/blob/main/app-screenshot.png?raw=true)

**aws-lambda-ml-monitoring**

[aws-lambda-ml-monitoring](https://aws-oss.beachgeek.co.uk/1ps) this project contains source code and supporting files for a serverless application for providing real-time inferencing for the HuggingFace Question & Answer Natural Language Processing(NLP) model using PyTorch.

**aws-spring-boot-optimization**

[aws-spring-boot-optimization](https://aws-oss.beachgeek.co.uk/1po) provides an example of how to deploy a Spring Boot application across a number of different scenarios. Watch out for the blog post coming soon.

**process-optimization-workshop**

[process-optimization-workshop](https://aws-oss.beachgeek.co.uk/1pn) is a new Workshop that introduces participants to IoT and machine learning technologies that can extract insight from industrial data and use it to improve the performance of industrial processes. Participants will gain hands-on experience on using AWS IoT Greengrass to deploy and run software on edge devices. This workshop will illustrate how an edge device can be added to an industrial control network to publish sensor data to the cloud for near real-time monitoring and analysis of historical data. In the cloud, historical data will be used to build machine learning models for predictive (what-if analysis) and prescriptive (set point optimisation) purposes. Finally, participants will learn how to deploy machine learning models to edge devices to leverage insights as part of latency-critical applications, such as set point optimisation.

### AWS and Community blog posts

**Amazon Corretto**

This weeks must read post is from guest writer Liz Fong-Jones, Principal Developer Advocate at Honeycomb.io. In the post, [Tuning Apache Kafka and Confluent Platform for Graviton2 using Amazon Corretto](https://aws-oss.beachgeek.co.uk/1pe) shares how they were able to work with the Amazon Corretto team to find and then optimise the performance of Apache Kafka on AWS Graviton2 processors.

![graphs of performance](https://d2908q01vomqb2.cloudfront.net/0716d9708d321ffb6a00818614779e779925365c/2022/05/19/image2-300x192.png)

**Kotlin**

Juan Sebastián Urrego Escobar has put together this nice post (the first of a series) that shows you how you can use the serverless project to deploy a Kotlin application on AWS Lambda. From outlining the selection of Kotlin over Java, to the tooling used and comparisons with others, this promises to be a good series. Go ahead and see what you think by reading, [Week of Java: Part 1 - Setting Up the Project](https://aws-oss.beachgeek.co.uk/1pi) and make sure you don't miss the other episodes which are already out.

**OpenSSF**

There was some big news last week as we announced an increased investment in the Open Source Security Foundation (OpenSSF) in the post, [AWS Investing an Additional $10 Million in Open Source Supply Chain Security](https://aws-oss.beachgeek.co.uk/1p2)

**Kubernetes**

What better way to celebrate KubeCon than a bunch of Kubernetes related content.

AWS Community Builder Mohamed Radwan put together this post, [Using Lambda to Automate OIDC and IAM role for Service Account in EKS](https://aws-oss.beachgeek.co.uk/1pf) which provides a guided walkthrough of how you can automate the configuration OpenID Connect and IAM Roles when provisioning your Amazon EKS clusters. [hands on]

Sean Kane wrote this post, [Zero to GitOps: Terraform and the AWS EKS Blueprints Project](https://aws-oss.beachgeek.co.uk/1pg) together with code in a GitHub repo introduces how Superorbital were able to explore via a proof of concept, how to leverage Terraform to spin up Kubernetes and ArgoCD instances in AWS. [hands on]

![diagram of GitOps and ArgoCD](https://superorbital.io/journal/terraform-aws-eks-blueprints/argocd-addons.png)

In the post, [Introducing Amazon EKS Observability Accelerator](https://aws-oss.beachgeek.co.uk/1pb), Vikram Venkataraman, Michael Hausenblas, Imaya Kumar Jagannathan, Rodrigue Koffi, Munish Dabra, and Ramesh Kumar Venkatraman have come together to share how customers can now leverage EKS Observability Accelerator to deploy the opinionated EKS clusters and configure observability for specific workloads without spending much time manually deploying the resources and configuring the agent to scrape the metrics. [hands on]

![graph of eks observability accelerator](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2022/05/17/C_OPS_880_17.jpg.png)

**ROSA**

Red Hat OpenShift Service on AWS (ROSA) is a fully managed OpenShift service, jointly supported by both Red Hat and Amazon Web Services (AWS) and managed by the Red Hat SRE team. We had a number of posts this week on this topic.

Kicking things off we had [Fine-grained IAM roles for Red Hat OpenShift Service on AWS (ROSA) workloads with STS](https://aws-oss.beachgeek.co.uk/1pa) from Ovidiu Valeanu who shows you how to use RBAC for implementing IAM roles for service accounts in a ROSA cluster to provide fine-grained permissions to pods and access AWS API securely. Ovidiu dives deep into how to use the OpenID Connect (OIDC) identity provider that is created during cluster installation and then use that with IAM roles for service accounts (IRSA). [hands on]

A collaboration between Mark Taylor and Ian Packer from IBM Consulting, and Arnaud Lauer from AWS on the topic of  portability time objectives (PTO) resulted in this post, [Measuring portability time objective as a metric for migrating to Red Hat Openshift Service on AWS (ROSA)](https://aws-oss.beachgeek.co.uk/1p8). What is PTO and why does this matter? Well I know you are all curious and want to find out, so dive in and all shall be revealed.

![architecture of pto](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2022/05/18/rosa-2.png) 

The final post in this round up ROSA related content is [Self-service AWS native service adoption in OpenShift using ACK](https://aws-oss.beachgeek.co.uk/1p9), from Ovidiu Valeanu and Ryan Niksch. AWS Controllers for Kubernetes (ACK) is an open-source project that allows you to define and create AWS resources directly from within OpenShift. Using ACK, you can take advantage of AWS-managed services to complement the application workloads running in OpenShift without needing to define resources outside of the cluster or run services that provide supporting capabilities like databases or message queues. This post provides a great hands on introduction to help get you going. [hands on]

![availble ack controllers on rosa](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2022/05/17/ovid-1.jpg)

**Apache Spark**

In the post, [A new Spark plugin for CPU and memory profiling](https://aws-oss.beachgeek.co.uk/1oz) Bo Xiong takes a look at a newly open sourced plugin ([amazon-codeguru-profiler-for-spark](https://aws-oss.beachgeek.co.uk/1p0)) that uses a feature of Spark 3, SparkPlugins, that enables profiling for JVM based Spark apps via Amazon CodeGuru and gain visibility of the runtime characteristics of yours Spark applications to help identify any bottlenecks or inefficiencies. [hands on]

![demo of new plugin](https://d2908q01vomqb2.cloudfront.net/7719a1c782a1ba91c031a682a0a2f8658209adbf/2022/05/13/DEVOPS_2010_1_B.gif)

**AWS Copilot**

AWS Copilot CLI is an open-source command line interface that makes it easy for developers to build, release, and operate production-ready containerised workloads on a number of AWS Services. Yang Wanxian and Yiming Peng have come together to write [Enabling AWS X-Ray tracing for AWS App Runner service using AWS Copilot CLI](https://aws-oss.beachgeek.co.uk/1p1) to show you how you can used AWS Copilot to easily integrate and use observability tools within your applications. [hands on]

![architecture of solution](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2022/05/13/apprunner461_001.png)

**Other posts you might like from the past week**

* [Deep dive into Amazon EMR Kerberos authentication integrated with Microsoft Active Directory](https://aws-oss.beachgeek.co.uk/1p6) walks you through creating the trust between Amazon EMR’s Kerberos daemon and an Active Directory domain [hands on]
* [TLS 1.3 Incompatibility with AWS SDK for Java versions 1.9.5 to 1.10.31](https://aws-oss.beachgeek.co.uk/1p7) helps you uncover the options when dealing with how to move from older versions of the AWS SDK that do not support TLS 1.3
* [Analyze Amazon Ion datasets using Amazon Athena](https://aws-oss.beachgeek.co.uk/1pc) find out about Amazon ION, a richly typed, self-describing, hierarchical data serialization format offering interchangeable binary and text representations [hands on]
* [Detect social media fake news using graph machine learning with Amazon Neptune ML](https://aws-oss.beachgeek.co.uk/1pd) shows you how Deep Graph Library (DGL), an open-source library for working with graph data, can be used to detect social media fake news [hands on]

![examples of graphs for DGL](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2022/05/17/workings.png)

* [Using AWS Distro for OpenTelemetry with Jaeger](https://aws-oss.beachgeek.co.uk/1pj) demonstrates a complete example of using AWS Distro for OpenTelemetry (ADOT) and Jaeger as a tracing backend [hands on]

![example architecture](https://miro.medium.com/max/1400/1*HI2y4rbOW1CkiRNiWiHHIw.png)

**Podcast**

Check out our very own Michael Hausenblas, who joins Annerieke Kortier in talking about all things observability in the pod cast, [Open Source Observability With Michael Hausenblas of AWS](https://aws-oss.beachgeek.co.uk/1ph)

### Quick updates

**KubeFlow**

Announced earlier in the week, was the general availability of AWS support for Kubeflow v1.4. Kubeflow on AWS streamlines data science tasks and helps build highly reliable, secure, portable, and scalable ML systems with reduced operational overheads through integrations with AWS managed services. You can use this Kubeflow distribution to build ML systems on top of Amazon Elastic Kubernetes Service (Amazon EKS) to build, train, tune, and deploy ML models for a wide variety of use cases, including computer vision, natural language processing, speech translation, and financial modelling.

Kubeflow on AWS provides a clear path to use Kubeflow with Amazon EKS for managed Kubernetes clusters, Amazon Simple Storage Service (Amazon S3) for an easy-to-use pipeline artefacts store, Amazon Relational Database Service (Amazon RDS) for highly scalable pipelines and metadata store, Amazon Elastic File System/Amazon FSx for Lustre for a simple, scalable and serverless file storage solution for increased training performance, AWS Secrets Manager to protect secrets needed to access your applications, AWS CloudWatch for persistent log management, AWS Deep Learning Containers for highly optimised Jupyter notebook server images, AWS Application Load Balancer for secure external traffic management over HTTPS, AWS Cognito for user authentication with TLS. These AWS service integrations with Kubeflow allow you to decouple critical parts of the Kubeflow control plane from Kubernetes providing secure, scalable, resilient and cost optimised design.

**Kubernetes**

Amazon Elastic Kubernetes Service (EKS) Anywhere now allows you to enable Amazon-curated software packages that extend the core functionalities of Kubernetes on your EKS Anywhere clusters. You can install the Harbor package as a local container registry starting today, with the Emissary-Ingress package and the support for service type load balancing through MetalLB coming in the next few months. More curated packages may be added over time based on customer demand.

If you operate EKS Anywhere clusters on-premises, you probably install additional software for capabilities such as ingress, load balancing, and container registry to ensure the security and reliability of your clusters. However, you may be spending a lot of effort researching for the right software, tracking updates, and testing them for compatibility. Now with EKS Anywhere Curated Packages, you can rely on Amazon to provide trusted, up-to-date, and compatible software that is supported by Amazon, reducing the need for multiple vendor support agreements and the time required to maintain additional software.

**Envoy**

AWS App Mesh makes it easy to monitor, control, and debug the communications between services. App Mesh uses Envoy, an open source service mesh proxy which is deployed alongside your microservice containers.

AWS App Mesh now supports IPv6 allowing customers to support workloads running in IPv6 networks and to invoke App Mesh APIs over IPv6. This helps customers to meet IPv6 compliance requirements, and removes the need for expensive networking equipment to handle address translation between IPv4 and IPv6. AWS App Mesh is a service mesh that provides application-level networking to make it easier for your services to communicate with each other across multiple types of compute infrastructure. AWS App Mesh standardises how your services communicate, giving you end-to-end visibility and options to tune for high-availability of your applications.

**OpenZFS**

Amazon FSx for OpenZFS is a fully managed file storage service that makes it easy to move data residing in on-premises ZFS or other Linux-based file servers to AWS without changing your application code or how you manage data. AWS Backup is a policy-based service that provides you a fully managed experience to centralise and automate data protection of your application data spanning across AWS services for compute, database, and storage.

AWS Backup now allows you to protect your Amazon FSx for OpenZFS file systems, helping you meet your centralised data protection and regulatory compliance needs. Using AWS Backup’s seamless integration with AWS Organisations, you can centrally create and manage immutable backups of Amazon FSx for OpenZFS file systems across all your accounts, protect your data from inadvertent or malicious actions, and restore the data with a few simple clicks. Additionally, you can generate unified auditor-ready reports to demonstrate compliance status of your organisational data protection policies.

**Apache Kafka**

AWS Glue can now connect to Apache Kafka using additional client authentication mechanisms. AWS Glue now supports SASL (Simple Authentication and Security Layer) using either SCRAM (Salted Challenge Response Authentication Mechanism) or GSSAPI (Kerberos).


### Videos of the week

**Node-Red**

Node-Red is my most favourite open source project. Any time I see content I get super excited, so this video fro Jesse Cox is something that I think you should watch. In this video, Jesse walks you through his WAGO KBUS API,  an open source project to unlock diverse IO systems and read/write the process data directly with MQTT. This means you can swap out your PLC runtime for any programming tool you like, even Node-RED, Python, or directly connect to AWS and control your system from anywhere in the world!

{{< youtube ooiabi6T2Hk >}}

### Events for your diary

**Airflow Summit**
**May 23rd - 27th**

A combination of online viewing as well as local chapters where you can congregate to watch and discuss sessions, as well as a number of the sessions being delivered live from those physical locations, this years Airflow Summit promises to be incredible.

Check out the [schedule](https://airflowsummit.org/program/) and [speakers](https://airflowsummit.org/speakers/), there is something for everyone. [Sign up](https://aws-oss.beachgeek.co.uk/1pk) and hopefully see you there.

**CDK Day**
**May 26th - Virtual**

This is a community organised event about AWS CDK, cdktf, projen and cdk8s. This will be third year they run this event, and if the previous two are anything to go by, this will be essential viewing - live streamed via You Tube. Check out and register for the event over at their home page at [https://www.cdkday.com/](https://www.cdkday.com/)

**BOSC 2022**
**July 13-14, Madison, Wisconsin, USA**

The Bioinformatics Open Source Conference (BOSC) has been held annually since 2000, and this year AWS is proud to be a platinum sponsor for this event. BOSC covers all aspects of open source bioinformatics software and open science, including (but not limited to) these topics, Open Science and Reproducible Research, Open Biomedical Data, Citizen/Participatory Science, Standards and Interoperability, Data Science Workflows, Open Approaches to Translational Bioinformatics, Developer Tools and Libraries, Inclusion, and Outreach and Training. This is a hybrid event (in person/virtual) and you find out more by checking out the event page, [BOSC 2022](https://aws-oss.beachgeek.co.uk/1li)

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)

**OpenSearchCon 2022**
**Sept 21st, 2022 Seattle**

Come to the first annual OpenSearchCon!

This day-long conference will be packed with presenters who build and innovate with OpenSearch. It doesn’t matter if you’re just getting started on your OpenSearch journey, running giant clusters, or contributing tons of code; the event is for everyone. Join us to celebrate the progress and look into the future of the project. Admission is free, and registration will be open in the next few weeks. All you will need to do is sign up, and get to Seattle!

Check out the full details, including signing up and location, at the [meetup page here](https://aws-oss.beachgeek.co.uk/1n1).


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)