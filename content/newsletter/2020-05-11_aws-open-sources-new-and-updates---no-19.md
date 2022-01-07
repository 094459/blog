---
title: 'AWS open sources new and updates - No. 19'
date: '2020-05-11'
tags : [ oss-newsletter ]
---
## May 11th - Instalment #19

Episode 19, and this week's edition is bursting at the seams with probably the biggest amount of news and updates to share (hence the later posting). Looks like everyone has been busy, and there were some things I had to leave out for another time. 

Before I get started though, I think it is worth reflecting on this blog post by Matt Asay, [The most important part of an open source project](https://www.infoworld.com/article/3541751/the-most-important-part-of-an-open-source-project.html), where he talks about the value of all contributions in open source projects, not just the developers cutting code. It is well worth 10 minutes of your day to reflect upon this post, as well as think about this data point from a [study from the World Bank on open source contributions](https://blogs.worldbank.org/opendata/leveraging-open-source-public-institution-new-analysis-reveals-significant-returns-investment-open), that highlighted:

>57% of the invested resources went to writing code. The rest, 43%, was spent on things like marketing, docs, meet-ups and other activities that aided the collaboration effort.

So, without further delay, let's dive into this weeks latest open sources news and updates. 

### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created.

So thank you to Ben Kehoe (@ben11kehoe), Adrian Horn (@adhorn), Joseph Maney (@josephbmanley), Luca Bianchi(@bianchiluca), Michael Garcia, Anish Yadav, Josh Kahn, Julie Lerman, Fernando Dingler, Jared Short, Cosmin Sanda, Nader Dabit, Nico Vibert, Dario La Porta, Mikhail Shapirov, Harish Shenoy, Letu Yang and Bernd Mathiske. 

### Latest from open source projects

**AWS SSO credential process**

This project from Ben Kehoe helps you get AWS SSO working with all the AWS SDK's that you might be using that do not currently understand it. [Here is a link to the GitHub repository for aws sso credential process](https://github.com/benkehoe/aws-sso-credential-process). Thank you Ben!

**AWS Chaos Scripts**

This week from Adrian Hornsby, ([Operational Excellence](https://dev.to/aws/towards-operational-excellence-3hnj) and [Chaos engineering](https://dev.to/aws/chaos-engineering-q-a-how-to-safely-inject-failure-3n5e) writer and general all round good guy), comes [this collection of scripts](https://github.com/adhorn/aws-chaos-scripts) to help you inject a bit of failure into your life. Make sure you read the disclaimer, but if you have heard or read his posts on operational excellence and building resilience, then you can check these scripts out and get started on your own journey. Thank you Adrian.

**Thanks Adrian** for helping me with my own operational excellence by spotting the mistakes. I would love to say these were part of a deliberate plan to embed Chaos into my workflow, but alas.....


**AWS Billing Alerts**

Setting up billing alerts for your AWS environments is general good practice, so here is a sample architecture complete with open sourced templates to get you started from Jospeh Manley.
![Billing Arts architecture](https://camo.githubusercontent.com/1669f1edf8148492ff6c9eda2b96e4a9022c935e/68747470733a2f2f7374617469632e636c6f756473756d752e636f6d2f62696c6c696e67616c657274732f6469616772616d2e706e67)

You can find the details of how to set this up following Joseph's instructions on his GitHub repository [here](https://github.com/josephbmanley/aws-billing-alerts). Be sure to check out his other repositories too. Thank you Jospeh!

**IAM Policy Generator**

Luca Bianchi (@bianchiluca) [shared](https://twitter.com/bianchiluca/status/1257334263285977092) this week a nice little library you can find on his [GitHub repository, IAM policy generator](https://github.com/aletheia/iam-policy-generator/). 
 
It helps you generate a valid IAM PolicyStatement object without having to “guess” the right Action (and to avoid human error and typos in general), thanks to proper validation and code completion.

Thank you Luca!

**Security - Cloudsplaining**

The lovely folk at Salesforce bring you this open source project to help improve the security of your deployments on AWS. Cloudsplaining is an AWS IAM Security Assessment tool that identifies violations of least privilege and generates a risk-prioritised HTML report with a triage worksheet. 

![Demo of cloudsplaining](https://github.com/salesforce/cloudsplaining/raw/master/docs/_images/cloudsplaining-report.gif)

Check out the GitHub repo at [https://github.com/salesforce/cloudsplaining](https://github.com/salesforce/cloudsplaining)

**VMware Cloud on AWS - pyVMC**

Are you a python developer that has been looking for a way to automate your VMWare Cloud on AWS Software defined data centre environments? If so, then you are in luck as Nico Vibert has put together this project, pyVMC on GitHub and written up a [supporting blog post, Introducing pyVMC.](https://nicovibert.com/2020/02/25/pyvmc-python-vmware-cloud-aws/) and you can also read [this post too.](https://flings.vmware.com/python-client-for-vmc-on-aws)

![pyVMC](https://flings.vmware.com/files/uploads/0/0/0/0/4/0/6/pyvmc_780_screenshot.png)

Check out [Nico's project on GitHub here.](https://github.com/nvibert/pyVMC-public)


### Blog posts you should check out

There have been lots of great posts this week, as well as new releases and updates so check these out.

**DynamoDB Workbench for Linux**

NoSQL Workbench for Amazon DynamoDB is a client-side application that helps developers build scalable, high-performance data models, and simplifies query development and testing. NoSQL Workbench is now available for Ubuntu 12.04, Fedora 21, Debian 8, and any newer versions of these Linux distributions, in addition to Windows and macOS.

Read the full announcement [here](https://aws.amazon.com/about-aws/whats-new/2020/05/nosql-workbench-for-dynamodb-adds-support-for-linux/), and if you just want the [download link, here it is for Linux, Windows and MacOS installs](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/workbench.settingup.html).

**Mosquitto mqtt to AWS IoT**

Mosquitto mqtt is an open source package I have used extensively to connect all sorts of devices and sensors to the Cloud. In this updated [blog post, How to Bridge Mosquitto MQTT broker to AWS IoT](https://aws.amazon.com/blogs/iot/how-to-bridge-mosquitto-mqtt-broker-to-aws-iot/), Michael Garcia and Anish Yadav show you how to implement the Mosquitto broker ‘Bridge’ capability to setup bi-directional exchange of data with AWS IoT Core through MQTT messages. This will enable your devices to communicate locally with the Mosquitto broker and with AWS IoT Core to benefit from the power of the AWS Cloud.

![architecture diagram](https://d2908q01vomqb2.cloudfront.net/f6e1126cedebf23e1463aee73f9df08783640400/2020/05/04/Schema-How-to-bridge-Mosquitto-to-AWS-IoT-Core.png)

Now let me dust off one of my many Raspberry Pi's and give this a go.

**AWS AppSync and Amazon QLDB**

Amazon Quantum Ledger Database (QLDB) is a purpose-built database for use cases that require an authoritative data source. Amazon QLDB maintains a complete, immutable history of all changes committed to the database (referred to as a ledger). Amazon QLDB fits well in finance, eCommerce, inventory, government, and numerous other applications.

Pairing Amazon QLDB with services such as AWS AppSync allows you to safely expose data and that data’s history for mobile applications, websites, or a data lake. In this two part post, [part one](https://aws.amazon.com/blogs/database/part-1-building-a-graphql-interface-to-amazon-qldb-with-aws-appsync/) and [part two](https://aws.amazon.com/blogs/database/part-2-building-a-graphql-interface-to-amazon-qldb-with-aws-appsync/) Josh Kahn explores a reusable approach for integrating Amazon QLDB with AWS AppSync to power an example government use case.

![AWS AppSync to Amazon QLDB](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2020/04/24/Building-a-GraphQL-interface-to-Amazon-QLDB-1.png)

**Amazon CloudWatch powers Prometheus metrics**

You can use Amazon CloudWatch to monitor Prometheus metrics from Amazon Elastic Kubernetes Service (EKS) and Kubernetes clusters, now available in beta. With this new feature, DevOps teams can automatically discover services for containerised workloads such as AWS App Mesh, NGINX, and Java/JMX. They can also expose custom metrics on those services, and ingest the Prometheus metrics in CloudWatch.

Read the [full announcement here](https://aws.amazon.com/about-aws/whats-new/2020/05/amazon-cloudwatch-now-monitors-prometheus-metrics-now-in-beta/). 

**.NET Core**

Julie Lerman writes about AWS for .NET developers in [Discovering AWS for .NET Developers](https://www.codemag.com/Article/2005041). If you a .NET developer and are new or just getting started with AWS, then this will be a useful starting point for you. From getting started to actually writing some code, you will soon be on your way to running open source .NET workloads on AWS.

Thank you Julie.


**Amplify DataStore**

[Fernando Dingler, shares a reference application and architecture](https://aws.amazon.com/blogs/mobile/aws-appsync-offline-reference-architecture/) that demonstrates how to build a modern mobile application with built-in offline and cloud synchronisation capabilities using React Native with the Amplify DataStore in the front end and AWS AppSync with Amazon DynamoDB in the backend.

![dataStore architecture](https://d2908q01vomqb2.cloudfront.net/0a57cb53ba59c46fc4b692527a38a87c78d84028/2020/05/04/Offline1.png)

AWS AppSync is a GraphQL serverless backend for mobile and web applications. It provides a flexible and reliable API with a built-in compute layer to run queries, mutations, and subscriptions to securely access, manipulate, and combine data from one or more data sources for any application. On the client device, the Amplify DataStore provides a familiar programming model for leveraging shared and distributed data without writing additional code for offline, real-time and online scenarios, which makes working with distributed, cross-user data just as simple as working with local-only data.

You can check out the [docs and links to the GitHub repository for Amplify here](https://docs.amplify.aws/), the quickest way to get started.

**HPC**

AWS ParallelCluster is an AWS supported Open Source cluster management tool that makes it easy for you to deploy and manage High Performance Computing (HPC) clusters in the AWS cloud. This week, we have a great post covering this area.

**Using AWS ParallelCluster with a serverless API**

[In Using AWS ParallelCluster with a serverless API](https://aws.amazon.com/blogs/compute/using-aws-parallelcluster-with-a-serverless-api/), Dario La Porta, AWS Senior Consultant for HPC writes about creating a serverless API of the AWS ParallelCluster command line interface. With this API, you can create, monitor, and destroy your clusters. This makes it possible to integrate AWS ParallelCluster programmatically with other applications you may have running on-premises or in the AWS Cloud.

![Serverless HPC](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2020/05/05/cluster-architecture.png)

Thank you Dario La Porta!


**Amazon Corretto - introducing Heapothesys**

Load testing and performance tuning Java stacks are going to be a lot easier with this open source project, Heapotheys. Created by the Amazon Corretto team, the Heapothesys benchmark is a synthetic workload that simulates fundamental application characteristics that affect garbage collector (GC) latency. The benchmark creates and tests GC load scenarios defined by object allocation rates, heap occupancy, and JVM flags, then reports the resulting JVM pauses. OpenJDK developers can thus produce reference points to investigate capability boundaries of the technologies they are implementing.

Read the post by Letu Yang and Bernd Mathiske, [Introducing Heapothesys, an open source Java GC latency benchmark with predictable allocation rates](https://aws.amazon.com/blogs/opensource/introducing-heapothesys-an-open-source-java-gc-latency-benchmark-with-predictable-allocation-rates/) and then go to the [GitHub repository for Heapothesys, here](https://github.com/corretto/heapothesys).

Thank you Letu Yang and Bernd Mathiske!

**Deep Java Library (DJL) and Spring Boot**

The java programming language is still very popular and dominant in the enterprise space. Organisations looking to adopt machine learning and deep learning in their existing applications are looking for solutions that enable existing talent and resources to rapidly get started using the programming languages and tools they know.

Recognising this challenge, AWS has created a few open source projects to facilitate the adoption of ML for Java and microservices, and ultimately to help our customers, partners and the open source community as a whole. The [Deep Java Library](https://djl.ai/) is one such open source project.

In this post, [Adopting machine learning in your microservices with DJL (Deep Java Library) and Spring Boot](https://aws-blogs-prod.amazon.com/opensource/adopting-machine-learning-in-your-microservices-with-djl-deep-java-library-and-spring-boot/), Mikhail Shapirov walks you through building a Spring Boot application that uses the Deep Java Library to create a simple object detection application using Apache MXNet and DJL.

Thank you Mikhail!


**German readers** will find [this post on the DJL](https://divis.io/2020/04/amazon-djl-ein-neues-deep-learning-framework-fuer-java/) interesting but you can also use various translation services to go through this introduction into Deep Java Library.

### Other blog posts

**SaaS and open source**

In this detailed blog post, Jared Short shares his advice for what you should think about when [building your SaaS products](https://www.trek10.com/blog/guiding-priciples-for-building-saas-on-aws). Check out #2 Build as if you might open source any time. Thanks Jared.

**Experiment tracking with MLflow inside Amazon SageMaker**

Fantastic post by Cosmin Sanda, [Experiment tracking with MLflow inside Amazon SageMaker](https://cosminsanda.com/posts/experiment-tracking-with-mlflow-inside-amazon-sagemaker/), walking you through how to support Apache MXNet using MLFlow and Amazon SageMaker. Thank you Cosmin!

**Amplify - a play list**

The modern equivalent to an 80's mix cassette, Nader Dabit shares with you a curated set of resources to get you started with Amplify. Head over to [Up and Running with Amplify Hosting and CI/CD](https://egghead.io/playlists/up-and-running-with-amplify-console-hosting-ci-cd-c680). Thank you Nader.


**Manage changes to your databases using Liquibase and Jenkins**


In his post [Deploy, track, and roll back RDS database code changes using open source tools Liquibase and Jenkins](https://aws.amazon.com/blogs/opensource/rds-code-change-deployment/), Harish Shenoy walks you through building a cost effective, database-independent solution in AWS using open source tools Liquibase and Jenkins that help DBAs to deploy, track, and perhaps roll back the database changes as and when developers need them to.

![Architecture diagram](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2020/04/23/Img1.jpg)

Thank you Harish Shenoy!

**Blockchain - deploying HyperLedger Fabric on AWS**

In this post, find out how [Nix Solutions deploy HyperLedger Fabric 1.4 on AWS](https://habr.com/en/company/nix/blog/500876/). This is a detailed walkthrough, and you will finish up with a sample application using smart contracts.


---

### Do you use AWS and love open source? 

Do you have some content you want to share with a broader audience? We are always looking for guest content for the AWS Open blog. Please get in touch (via comments below) and I would love to speak with you about what you are doing in open source. We are always looking for interesting new content.

### We are hiring

We are hiring, so if you love open source, then why not check out the current openings. We would love to hear from you and if you want to chat and ask me anything, connect to me via LinkedIn or Twitter and always happy to talk.

[Open Source jobs at Amazon and AWS](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) - scroll to bottom, on left.

### Stay in touch with open source at AWS

I hope this summary has been useful. I have looked for all the session videos that have been uploaded to date, but if I have missed anything, please get in touch and I will update this summary. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on @AWSOpen.