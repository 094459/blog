---
title: 'AWS open source news and updates No.43'
date: '2020-11-09'
tags : [ oss-newsletter ]
---
## November 9th - Instalment #43

Week No.43 or 101011 if you prefer binary notation. This week we have the usual collection of open source projects, blog posts, events, case studies and workshops. Of note this week is the GA of the Lambda Powertools for Java, news of the announcement last week of the new RabbitMQ message broker service, more AWS Nitro Enclave goodness, a brand new workshop from Nader Dabit and more events and webinars for your diary. There are several of those events running this week so check them out and you may still have time to reserve your spot. Make sure you check out the important note below if you are currently using Docker Hub within your environment to pull/store your container images as this update is for you. 

Without further ado, lets begin...

**Docker Hub**

If you currently are using Docker Hub then you need to read this. Docker, Inc. has announced that the Hub service will begin limiting the rate at which images are pulled under their anonymous and free plans. These limits will progressively take effect beginning November 2, 2020. Once fully in place, free plan anonymous use will be limited to 100 pulls per six hours, free plan authenticated accounts limited to 200 pulls per six hours, and Pro and Team accounts will not see any rate limits. Read, 
[Advice for customers dealing with Docker Hub rate limits, and a Coming Soon announcement](https://aws.amazon.com/blogs/containers/advice-for-customers-dealing-with-docker-hub-rate-limits-and-a-coming-soon-announcement/) Omar Paul and Michael Hausenblas to find out more details as well as understand what your options are.

### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to Philipp Schmid, Wilhelm Wonigkeit, Aidan Steele, Gunter Rotsaert, Richard Fan, Albert Corollari, Amrut Prabhu, Deniz Parmaksız , Maggie Carter, Grace Kitzmiller, Deniz Parmaksız, Michael Edge, Allan Zheng, Channy Yun, James Beswick, Deepak Singh, Ahmet Atalay, Yannick Pobiega, Tiago Reichert, Bruno Emer, Anuraag Agrawal, Matt Asay,  Chris Deigan, Adir Sharabi, Cristina Fuia, Nick Lee, Matteo Figus,  Luc van Donkersgoed, Duarte Nunes and Joseph M

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

**efsync**

[efsync](https://github.com/philschmid/efsync) is an open source CLI/SDK tool from Philipp Schmid, which automatically syncs files and dependencies to AWS EFS. This enables you to install dependencies with the AWS Lambda runtime directly into your EFS filesystem and use them in your AWS Lambda function. It enables you either combine this with syncing files from S3 or uploading them with SCP. You can also sync files from S3 and upload with SCP without installing Pip dependencies. Philipp also put togehter this walkthrough to get you started: [efsync my first open-source MLOps toolkit](https://towardsdatascience.com/efsync-my-first-open-source-mlops-toolkit-4af6181d16d6)

![arch](https://miro.medium.com/max/1400/0*nT7rIrAuCqwA7QBi.png)

**Qovery Engine**

[Qovery Engine](https://github.com/Qovery/engine) is an open-source abstraction layer library that makes it easy to deploy your applications on AWS (and other providers in the future). The Qovery Engine is written in Rust and takes advantage of Terraform, Helm, Kubectl, and Docker to manage resources so you can deploy your applications in minutes. Detailed documentation and some demos of how it works, this is a project worth spending some time checking out.

**amazon-redshift-db-driver**

[amazon-redshift-jdbc-driver](https://github.com/aws/amazon-redshift-jdbc-driver) and [amazon-redshift-python-driver](https://github.com/aws/amazon-redshift-python-driver) Amazon Redshift JDBC and Python drivers are now open source and available for the user community under the Apache-2.0 license. With this release, customers will gain enhanced visibility to the driver implementation and can contribute to its development. Users can now browse the code for both drivers on the relevant AWS GitHub repositories, submit driver functionality enhancements through Git Pull Requests, and report issues for review. These drivers introduce several enhancements: The JDBC driver now supports querying across databases (Preview), improves resultset metadata fetching, optimises batch INSERT performance through the reWriteBatchedInsertsSize parameter, improves support for client side cursor through the fetchRingBufferSize parameter, and adds support for SocketFactory. The new open source Python driver introduces IAM and IDP support for Single Sign On (SSO), NumPy and Pandas API support, and an extended database metadata API.

Check out more [here](https://aws.amazon.com/about-aws/whats-new/2020/11/amazon-redshift-announces-open-source-jdbc-python-drivers/).

**aws-color-region-navbar-extension**

[aws-color-region-navbar-extension](https://github.com/corollari/aws-color-region-navbar-extension) super nice project from 
Albert Corollari that provides an open source browser extension that changes the color of AWS' navbar depending on the region. This works on Firefox and Chrome, so take a look and start figuring out what colour scheme you will use.


**aws-lambda-powertools-java**

[aws-lambda-powertools-java](https://github.com/awslabs/aws-lambda-powertools-java) great to see this project go GA, so if you were a Java developer and were envious of those Python developers who had the awesome Lambda Powertools then you no longer need to worry. A suite of utilities for AWS Lambda Functions that makes tracing with AWS X-Ray, structured logging and creating custom metrics asynchronously easier. Pankaj Agrawal has put together this blog, [Simplifying serverless best practices with AWS Lambda Powertools Java](https://aws.amazon.com/blogs/opensource/simplifying-serverless-best-practices-with-aws-lambda-powertools-java/) to walk you through the project and get you started.

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2020/11/04/Face-recognition-serverless-app-v3.png)

**cpr_gazebo**

[cpr_gazebo](https://github.com/clearpathrobotics/cpr_gazebo) Clearpath have provided some open source Gazebo resources that you can use in your AWS RoboMaker simulations. Agriculture, Inspection, Office and World simulation worlds are provided complete with a quick start launch. Read the post [here](https://clearpathrobotics.com/blog/2020/11/clearpath-accelerates-processes-to-the-cloud-with-aws-robomaker-simulations/) for more details.


### AWS open source posts

**RabbitMQ**

[Amazon MQ Update – New RabbitMQ Message Broker Service](https://aws.amazon.com/blogs/aws/amazon-mq-update-new-rabbitmq-message-broker-service/) from Channy Yun provides this weeks big announcement on the launch of Amazon MQ for RabbitMQ, a managed messaging service that reduces the operational overhead for companies managing RabbitMQ message brokers. For those perhaps unfamiliar with RabbitMQ, it is an open source and popular message broker and a critical component of distributed applications. RabbitMQ is a mature project known for its feature richness, active community support, and broad range of supported clients and frameworks but it also requires knowledge and expertise to be able to build and manage clusters to support your application. This is a service (Amazon MQ) that is already super popular with customers and this launch expands the capabilities by adding RabbitMQ. Channy walks you through the service, setting up a quick message broker and then using a python client to test it.

![pika](https://d2908q01vomqb2.cloudfront.net/da4b9237bacccdf19c0760cab7aec4a8359010b0/2020/10/22/2020-mq-rabbitmq-web-console.png)

**Apache ActiveMQ**

[Using Amazon MQ as an event source for AWS Lambda](https://aws.amazon.com/blogs/compute/using-amazon-mq-as-an-event-source-for-aws-lambda/) James Beswick follows on from news in the last couple of weeks that Amazon MQ can now an event source for AWS Lambda with a post that shows you how to set up an Amazon MQ broker and networking configuration, and then create a Lambda function that is invoked by messages from Amazon MQ queues. For those perhaps unfamiliar, Amazon MQ provides a fully managed, highly available message broker service for Apache ActiveMQ.

![arch](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2020/11/03/mq2.png)

**Kubernetes**

[Amazon ECS vs Amazon EKS: making sense of AWS container services](https://aws.amazon.com/blogs/containers/amazon-ecs-vs-amazon-eks-making-sense-of-aws-container-services/) Deepak Singh provides this weeks must read post on the topic of how to approach thinking which container service is best for your application or workload needs. This post provides you with a list of all your options including where. This is a short read so well worth a couple of minutes of your time today.

**AWS App Mesh**

AWS App Mesh is a service mesh [based on the Envoy proxy](https://docs.aws.amazon.com/app-mesh/latest/userguide/envoy.html). This week a couple of posts. First up, we have [CI/CD with Amazon EKS using AWS App Mesh and Gitlab CI](https://aws.amazon.com/blogs/containers/ci-cd-with-amazon-eks-using-aws-app-mesh-and-gitlab-ci/) where Ahmet Atalay shows you how to deploy an application to Kubernetes in a CI/CD Pipeline using AWS App Mesh using Gitlab as a source code repository. In this post he shows you how to  build a complete CI/CD pipeline for applications deployed on Amazon Elastic Kubernetes Service (Amazon EKS), using Gitlab CI/CD pipelines, and how to deploy applications using canary techniques using AWS App Mesh resources.

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2020/10/31/CI-CD-on-Amazon-EKS-using-AWS-AppMesh-and-Gitlab-CI-v2.png)

Following that we have [Connecting services across multiple accounts using AWS App Mesh and Amazon ECS](https://aws.amazon.com/blogs/containers/connecting-services-across-multiple-accounts-using-aws-app-mesh-and-amazon-ecs/) from Yannick Pobiega shows how to utilise AWS App Mesh to connect multiple application components residing in different Amazon ECS clusters across multiple accounts. This is a pattern we are seeing as customers look to deploy their micro services across multiple AWS accounts to reduce the blast radius and/or give teams more independence during development. Either way, if you are looking at how to achieve this then check this post out.

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2020/11/05/AppMesh_ECS_multi_account.png)

Finally, Tiago Reichert and Bruno Emer follow with [Create a pipeline with canary deployments for Amazon EKS with AWS App Mesh](https://aws.amazon.com/blogs/containers/create-a-pipeline-with-canary-deployments-for-amazon-eks-with-aws-app-mesh/) demonstrate how you can leverage different AWS services in conjunction with AWS App Mesh to implement a canary deployment strategy for applications running on Amazon Elastic Kubernetes Service (Amazon EKS).

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2020/10/29/architecture_diagram.png)

**Bonus** Out this week was the launch of a new Service Mesh White Paper which you can download [here](https://d1.awsstatic.com/whitepapers/using-service-meshes-in-aws.pdf). This white paper provides a good introduction, the use cases and how you can apply service mesh with your AWS workloads.

**OpenTelemetry**

[Distributed tracing with OpenTelemetry](https://aws.amazon.com/blogs/opensource/distributed-tracing-with-opentelemetry/) Anuraag Agrawal gets you up and running with OpenTelemtry on Java and shows you how you can use the OpenTelemtry agent for Java and then shows how you can view this in Zipkin.

![zipkin](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2020/10/26/aanuraag_Distributed-Tracing-OpenTelemetry_f1.jpg)

**ROS**

[Building the future of robots development with ROS 2](https://aws.amazon.com/blogs/opensource/building-the-future-of-robots-development-with-ros-2/) Matt Asay provides insights into the world of open source Robotics and how the Robotics Operating System (ROS) is helping to change robotics in the same way that other open source frameworks (such as Linux Apache MySQL and PHP, LAMP) did for accelerating web applications on the web. If you want to read a piece to understand what this looks like, then look no further.

**Data Privacy**

[Handling data erasure requests in your data lake with Amazon S3 Find and Forget](https://aws.amazon.com/blogs/big-data/handling-data-erasure-requests-in-your-data-lake-with-amazon-s3-find-and-forget/) this collaboration between Chris Deigan, Adir Sharabi, Cristina Fuia, Nick Lee, and Matteo Figus provides a ready to roll solution that allows you to remove records from data lakes of any size that are in AWS Glue Data Catalog. This is going to help you meet obligations that operators may need to meet (for example GDPR), and provides the capability for you to be able to erase private data from your data lake when requested. The solution includes a web user interface that you can use and an API that you can use to integrate with your own applications.

![arch](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2020/10/06/data-erasure-find-and-forget-1.jpg)

**AWS SDKs**

[Introducing Middleware Stack in Modular AWS SDK for JavaScript](https://aws.amazon.com/blogs/developer/middleware-stack-modular-aws-sdk-js/) Allan Zheng is a post showing you how you can use middleware feature of the AWS SDK for Javascript v3, which I posted a few weeks ago in this newsletter. Allan provides you with a summary of what this feature is and then some sample use cases and code of how you can use it.

![middleware](https://d2908q01vomqb2.cloudfront.net/0716d9708d321ffb6a00818614779e779925365c/2020/11/03/middleware_stack-1-1.jpg)

Allan provides links to the GitHub repository, so feel free to post any issues to record any problems or request new features. 

If you are running the AWS SDK for .NET v1 then you need to be aware of the end of support announcement that was posted here, [Announcing the end of support for the AWS SDK for .NET version 1](https://aws.amazon.com/blogs/developer/announcing-the-end-of-support-for-the-aws-sdk-for-net-version-1/). On April 1st, 2021, the AWS SDK for .NET version 1 (v1) will reach the end of support, so read the post to find out what you can do.

**HyperLedger**

[Running Hyperledger Explorer on Amazon Managed Blockchain](https://aws.amazon.com/blogs/database/running-hyperledger-explorer-on-amazon-managed-blockchain/) Michael Edge shares in the first of a series of posts, how to build a Hyperledger Fabric network using Amazon Managed Blockchain. In this post, he shows you how to deploy and run Hyperledger Explorer to visualise the Fabric network. He walks you through the Hyperledger Explorer dashboard to view channels, chaincode, blocks, and transactions and you will also learn how to use the Swagger UI to interact with the RESTful API provided by Hyperledger Explorer.

![arch](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2020/10/14/Screen-Shot-2020-10-14-at-15.57.27.png)


### Partner / Industry spotlight

**Elasticsearch**

[How Insider Learned to Scale a Production Grade Elasticsearch Cluster on AWS](https://aws.amazon.com/blogs/apn/how-insider-learned-to-scale-a-production-grade-elasticsearch-cluster-on-aws/) Deniz Parmaksız who is a Sr. Machine Learning Engineer at Insider does a show and tell about Insider’s two-year journey of scaling up a production Elasticsearch cluster, a vital element for their recommendation and search products. This post covers the challenges faced and the solutions they used to overcome those.

![arch](https://d2908q01vomqb2.cloudfront.net/77de68daecd823babbb58edb1c8e14d7106e83bb/2020/10/28/Insider-Elasticsearch-Clusters-4.jpg)

Insider is an AWS Advanced Technology Partner with the AWS Digital Customer Experience Competency.

### Case Studies and Industries

**COVID**

[Crowdsourcing a cure for COVID-19: How the cloud is accelerating research and drug discovery](https://aws.amazon.com/blogs/publicsector/crowdsourcing-cure-covid-19-cloud-accelerating-research-drug-discovery/) Maggie Carter and Grace Kitzmiller provide an update on how the Cloud and distributed computing is help to tackle and accelerate research towards COVID-19 therapies. They share how COVID Moonshot, an open source project, is helping to bring about a low cost, patent free antiviral therapy. This post contains some pretty amazing data points, and I do not want to post any spoilers so you will have to check out what those are.

### Workshop of the week

**Next.js on AWS Amplify**

[next.js-amplify-workshop](https://github.com/dabit3/next.js-amplify-workshop) Fresh out from Nader Dabit, a new workshop where you will learn how to build a full stack cloud application with Next.js, GraphQL, & Amplify.


### Latest blog posts

**AWS Nitro Enclaves**

Some more great posts this week covering one of my favourite AWS innovations, AWS Nitro Enclaves.

First up we have [Serving IAM credentials to enclaves](https://awsteele.com/2020/11/02/2020-11-02-nitro-enclaves-first-impressions.html). In this post Aidan Steele explores some of the features of AWS Nitro Enclave. Aidan shows you a proof of concept of how you might create a service that would vend AWS IAM role session credentials to code running in enclaves. He has some code that accompanies this post, but as he says in the post, this should not be used in anger and is just to show what can be done.

![diagram](https://awsteele.com/assets/2020-11-02-sequence-diagram.png)

Richard Fan follows that with a post, [Running Python App on AWS Nitro Enclaves](https://levelup.gitconnected.com/running-python-app-on-aws-nitro-enclaves-56024667b684) which introduces what AWS Nitro Enclaves is and then walks you through using a sample Python app. As Richard says in the post, the best way to learn is often to just dive in and that is what he has done in this post. Read on to find out more about the key features that AWS Nitro Enclaves provides, as well as a look at what attestation is and why it is important. Make sure you follow Richard for further posts on this topic.

![app](https://miro.medium.com/max/1400/1*JEwiOUeHJfq0SMD6Y797Gg.png)

Colm MacCárthaigh follows with an epic Tweet thread which you can read [here](https://twitter.com/colmmacc/status/1324749177381793792?s=11). In this thread he breaks down some of the key components of AWS Nitro Enclaves as well as providing some good examples of the use cases where this capability might come in very hand. Maybe one day this will get turned into a blog post!

Finally, Luc Van Donkersgoed follows up with a third blog post, [Ultra Secure Password Storage with NitroPepper](https://www.sentiatechblog.com/ultra-secure-password-storage-with-nitropepper). In this post Luc shows you how to build a Nitro Enclave application that will protect user passwords, even when an attacker has full control over the application server and database. Luc calls this application is called NitroPepper, and provides everything you need. Very nice post Luc.

![arch](https://images.ctfassets.net/9gzi1io5uqx8/7ojKJqQrOLFwQQnfK01dTd/2a718d65c3e8700df29186f3dcee616f/login-flow.png?fit=scale&w=1330)


**Vorteil: Running ELK on AWS**

[An ELK stack without an OS](https://wilhelm-wonigkeit.medium.com/an-elk-stack-without-an-os-9d01a1761d8d) from Wilhelm Wonigkeit CEO & Co-founder at Vorteil.io. [Vorteil](https://github.com/vorteil/vorteil) is an operating system for running cloud applications on micro virtual machines, and they provide open source tools that allow you to build images  and then quickly deploy those. You can run those locally on Firecracker for example, or deploy them to AWS. In this post, Wilhelm walks you through how you can deploy an ELK stack (Elasticsearch, Logstash and Kibana) using Vorteil and deploy that stack on AWS.

![image](https://miro.medium.com/max/1400/1*YShwGrwzX_hjEYYiNpxhzg.png)

This is an interesting project and well worth reading and then playing with the tool.

**Spring**

[How to Deploy a Spring Cloud Function on AWS Lambda](https://mydeveloperplanet.com/2020/11/04/how-to-deploy-a-spring-cloud-function-on-aws-lambda/) this tutorial from Gunter Rotsaert shows you how you can deploy Spring Cloud Function's to AWS Lambda. Spring Cloud Function allow you to implement business logic via functions and deploy them via a Spring Boot application. Spring Boot is a very popular framework and so if you are looking to move your Spring Cloud functions to AWS Lambda, this is just the post you need. Gunter provides details breakdown of the steps and sample code in his repo.

Also this week on Spring was this post from Amrut Prabhu, [Spring Boot : Handle AWS RDS password change or rotation without restarting](https://dev.to/amrutprabhu/spring-boot-handle-aws-rds-password-change-or-rotation-without-restarting-301l) who walks you through using the AWS Secrets Manager JDBC open source drive to enable you to manage rotating your Amazon RDS passwords without impacting your applications.

**Rust**

[Building an AWS Lambda extension with Rust](https://dev.to/aws-builders/building-an-aws-lambda-extension-with-rust-3p81) fresh from AWS Community Builder Duarte Nunes is a post that shows you how you can use Rust to develop a new AWS Lambda Extension that were recently announced (and have covered in the past few editions of this newsletter)

![arch](https://res.cloudinary.com/practicaldev/image/fetch/s--95ZeJA8r--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/4fh6rpb2ywi0otr861u4.png)

**Tetraforce**

[How TetraForce runs Godot on AWS](https://dev.to/josephbmanley/how-tetraforce-runs-godot-on-aws-1gh6) Joseph B. Manley shows you how TetraForce, an open-source multiplayer action-adventure RPG inspired by the popular Zelda game, uses the open source [Godot](https://godotengine.org/) engine on AWS. The posts talks about how they were able to move the game onto AWS within a week and breaks out the architecture and some of the key components. A great read.

![arch](https://res.cloudinary.com/practicaldev/image/fetch/s--9Scc75z8--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/pujg9a9dp1hj0njyf34n.png)

### Quick updates

**Amazon Elasticsearch**

Amazon Elasticsearch Service now provides the ability to define a custom endpoint for your domain and associate an SSL certificate from AWS Certificate Manager (ACM). Defining a friendly name makes it easier for your users to access Kibana, and allows you to move to a new domain without updating your clients. You can define a custom endpoint when creating a new domain or by editing an existing domain from the Amazon Elasticsearch Service console, or through the Amazon Elasticsearch Service APIs. You can then link the custom endpoint to a certificate in ACM, and create an Alias or CNAME mapping in Route 53, or in your preferred Domain Name System (DNS), to route traffic to the custom endpoint.


**AWS IoT SDK for Embedded C**

AWS IoT Device SDK for Embedded C (C-SDK) version 202011.00 now includes refactored coreHTTP, AWS IoT Device Defender, and AWS IoT Jobs libraries alongside of the existing coreMQTT, coreJSON, and AWS IoT Device Shadow libraries. All libraries have been optimized for memory usage and modularity, and have undergone code quality checks (e.g. MISRA-C compliance, Coverity static analysis), and validation of memory safety with the C Bounded Model Checker (CBMC) automated reasoning tool.  C-SDK is a collection of C source files under the MIT open source license that can be used in embedded applications to securely connect IoT devices to AWS IoT Core. It is distributed in source form and intended to be built into customer firmware along with application code, other libraries, and an underlying operating system (OS) suitable for constrained embedded devices. For more details, see the [README](https://github.com/aws/aws-iot-device-sdk-embedded-C/tree/202011.00/README.md) and [Changelog](https://github.com/aws/aws-iot-device-sdk-embedded-C/tree/202011.00/CHANGELOG.md) files.

**SQL Server on Linux**

You can now use AWS Launch Wizard to perform single-instance deployments of Microsoft SQL Server on Windows Server and Ubuntu Server. AWS Launch Wizard offers a guided way of sizing, configuring, and deploying AWS resources for third party applications, such as Microsoft SQL Server and HANA-based SAP systems, without the need to manually identify and provision individual AWS resources. Previously, customers could use AWS Launch Wizard to easily perform SQL Server Always On deployments on Windows Server and Ubuntu Server. Now, you are able to leverage the same ease of use to perform SQL Server single-instance deployments on Windows Server and Linux. To learn more about using AWS Launch Wizard to accelerate your SQL Server deployments, visit the AWS [Launch Wizard page](https://aws.amazon.com/launchwizard/). 

### Events for your diary

Check out these events this week.

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

**Enabling Cloud Data Lakes for Analytics**
**11/11/2020 9:00am - 12:00pm PST**

In this virtual workshop, we’ll cover best practices for organisations to use powerful open source technologies to build and extend your AWS investments to make your data lake analytics ready. You’ll learn about the advantages of cloud-based data lakes in terms of security and cost. And finally, you’ll learn how data professionals are having a huge impact - lowering costs, changing time to market, and even revolutionising industries.

Full details and registration link [here](https://events.databricks.com/virtualclouddatalakedevdaywest).


**AWS Container Day: Kubernetes Edition**
**November 17th, 10:00am to 6:00pm EST**

Join us for AWS Container Day, a fully live, virtual day of sessions all about Amazon EKS and Kubernetes at AWS, hosted by Containers from the Couch. At this Day Zero KubeCon event, the AWS Kubernetes team will be discussing new launches, demoing products and features, covering best practices, and answering your question live on Twitch.

Register [here](https://awscontainerdayk8s.splashthat.com/#rsvp).

**Virtual ROS-Industrial Conference 2020**
**December 15 - 16, 2020**

The 8th edition of ROS-Industrial Conference will be held as a virtual event. It is not only the annual community meeting for the European ROS-Industrial community but this years event is also the final event of the H2020 ROSIN project. The conference gives you the chance to see the newest technical developments and to meet people and companies, which are active in the ROS community.

Learn more and sign up [here](https://rosindustrial.org/rosindustrial-conference-2020).

### Check out this newsletter on Cloud Native

**Cloud Native Newsletter**

Whilst not necessarily open source, I wanted to let you know about a fantastic newsletter that I have recently found and subscribed to. The Cloud Native Software Engineering Newsletter (now on [episode #17](https://dev.to/loujaybee/cloud-native-software-engineering-newsletter-17-october-2020-4mj9)) is something you should all subscribe to as it has great information and the latest news on all things cloud native. And let's face it, a lot of that is going to be open source related as well. Nice work Lou Bichard. You can sign up for the newsletter [here](https://www.thedevcoach.co.uk/cloud-native-software-engineering-newsletter-17/).

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen).

### Your feedback matters!

I have put together a short feedback survey, which I would ask you to take - it will take no more than 2 minutes. You can access [here](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn). Many thanks!

[Take the survey](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn)
26t4