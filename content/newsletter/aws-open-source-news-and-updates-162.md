---
title: 'AWS open source newsletter #162'
date: '2023-06-26'
tags : [ oss-newsletter, aws open source, AWS CDK, Cedar, OpenSearch, Apache Spark, Amazon EMR, Apache Iceberg, Kubernetes, Apache Kafka, AWS Amplify, MySQL, MariaDB, Redis, Amazon Corretto, Grafana, AWS ParallelCluster, PostgreSQL, Kubecost, Prometheus, AWS Cloud Map MCS Controller, AWS SAM, PyTorch]

---
## June  26th, 2023 - Instalment #162

Welcome to #162 of the AWS open source newsletter. As always, we search high and low for the best and latest open source content, and I think you will love what we have lined up this week. 

If you are looking for new projects to try out, then this weeks projects include a very handy tool for Amazon EKS admins, a new experimental project that looks to use ChatGPT to manage your AWS resources, a workshop on Generative AI on AWS, a new tool that helps simplify how you can connect to RDS resources, a PHP library to help you verify your JWT tokens, and a great example application of how you can use Cedar and Amazon Verified Permissions. Great stuff.

Also featured this week is content on popular open source technologies, which this week include Cedar, OpenSearch, Apache Spark, Apache Iceberg, Kubernetes, Apache Kafka, AWS Amplify, Amazon Corretto, Grafana, AWS ParallelCluster, PostgreSQL, Kubecost, Prometheus, AWS Cloud Map MCS Controller, PyTorch and more!

Also, be sure to check out the events section as there are a few events happening this week.

**Feedback**

Before you dive in however, I need your help!  Please please please take 1 minute to [complete this short survey](https://pulse.buildon.aws/survey/PJRTOUMK) and you will forever have my gratitude!

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes:  Aidan Steele, Rio Astamal, Cristian Magherusan-Stanciu, David Nalley, Mark Ryland, Vikas Bajaj, Daniel Aniszkiewicz, AJ, John Mille, Sunita Nadampalli, Ankith Gunapal, Cameron Senese, Imaya Kumar Jagannathan, Vikram Venkataraman, Vivek Gautam, Naresh Gautam, Harsha Tadiparthi, and Mikhail Vaynshteyn

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution.*

#### Tools

**ChatGPT-cloud-plugin**

[ChatGPT-cloud-plugin](https://aws-oss.beachgeek.co.uk/2yl) is the latest project from our good friend, Cristian Magherusan-Stanciu, and is a new experimental project that one day, will help you manage your AWS resources using ChatGPT. One to watch.

**lightsail-miab-installer**

[lightsail-miab-installer](https://aws-oss.beachgeek.co.uk/2ym) is a user-friendly command-line tool from my colleague Rio Astamal, that will help you streamline the setup of [Mail-in-a-Box](https://aws-oss.beachgeek.co.uk/2yn) on Amazon Lightsail. I have featured [Mail-in-a-Box](https://aws-oss.beachgeek.co.uk/2yn) in previous newsletters, and this project provides everything you need to run a turn-key mail system. It uses lots of other open source projects and technologies (postfix, Dovecot, nginx, dns4, and lots more!).

**rdsconn**

[rdsconn](https://aws-oss.beachgeek.co.uk/2yo) is the latest project from AWS Hero Aidan Steele, that makes connecting to an AWS RDS instance inside a VPC from your laptop easier. It uses the recently launched EC2 Instance Connect to achieve this. This is something that I am going to try out as I do run a lot of RDS demo instances, and so I can see this being very handy indeed (good by ssh-tunnel)

**kafka-connect-watcher**

[kafka-connect-watcher](https://aws-oss.beachgeek.co.uk/2yp) is a project from AWS Community Builder John Mille, that will actively probe and monitor your Kafka connect clusters using the Connect API. It can report metrics to AWS CloudWatch (Prometheus coming) using AWS EMF to allow creating alerts and alarms. While that alone is pretty cool, John has also put together a blog post, [Kafka Connect Watcher - actively monitor your clusters](https://aws-oss.beachgeek.co.uk/2yq), to help you get started. Awesome as always from John!

**cognito-token-verifier**

[cognito-token-verifier](https://aws-oss.beachgeek.co.uk/2yr) is a PHP  library verifies that the signature of the JWT is valid, comes from a desired application, and that the token has not been tampered with or expired.

**eks-pod-information-collector**

[eks-pod-information-collector](https://aws-oss.beachgeek.co.uk/2yv) This project was created to collect Amazon EKS resource information related to a specific POD such as Configurations/Specification, PV/PVC etc., logs (optional) etc. for troubleshooting Amazon EKS customer support cases.

**cdk-appflow**

[cdk-appflow](https://aws-oss.beachgeek.co.uk/2yw) is a new AWS CDK construct for Amazon Appflow, a centralised control hub for managing data integrations between third-party SaaS Applications and AWS. The library is currently in tech preview, so if you do try it out you can provide feedback through the usual mechanisms in GitHub.

### Demos, Samples, Solutions and Workshops

**avp-petstore-sample**

[avp-petstore-sample](https://aws-oss.beachgeek.co.uk/2yu) sample web application demonstrates authentication and policy-based authorization of diffrent user types to an imaginary Pet Store web app. This application uses Amazon Cognito for authentication and uses Cedar policies and Amazon Verified Permissions for policy-based authorisation, the application uses Amplify platform to accelerate deployment and provisioning of backend resources.

![demo of avp petstore demo](https://github.com/aws-samples/avp-petstore-sample/blob/main/static/PetStore-test.gif?raw=true)


**generative-ai-immersion-day**

[generative-ai-immersion-day](https://aws-oss.beachgeek.co.uk/2ys) it seems impossible to avoid Generative AI, so if you are looking to dive deeper into this topic on AWS, check out this workshop that is set up following the popular AWS Immersion Day format and provides guidance on how to get started with Generative AI on AWS.

### AWS and Community blog posts

**Community roundup**

AWS Community Builder Daniel Aniszkiewicz has put together a great post on Cedar, [Authorization and Cedar: A New Way to Manage Permissions - Part I](https://aws-oss.beachgeek.co.uk/2yj) which is the first of a series of articles Daniels is putting together where he will share how to create an authorisation decisions system for an e-commerce platform scenario. This looks like one to watch folks.

[Fast and Efficient Search with OpenSearch and MinIO](https://aws-oss.beachgeek.co.uk/2yk) from AJ also caught my eye last week, that looks at how you can leverage MinIO as a storage backend for OpenSearch.

**PyTorch**

In the post, [Optimized PyTorch 2.0 Inference with AWS Graviton processors](https://aws-oss.beachgeek.co.uk/2yf), Sunita Nadampalli and Ankith Gunapal dive deep into benchmarking PyTorch inference against a number of different AWS instance types. I am not going to give anything away, if you want answers, then read the post!

![graph of benchmarks for pytorch on graviton](https://pytorch.org/assets/images/optimized/im3.png)

**Kubernetes**

More fabulous* Kubernetes posts this week. Kickings this off this week we have Cameron Senese who put together, [Kubernetes Multi-Cluster Service Discovery using Open Source AWS Cloud Map MCS Controller](https://aws-oss.beachgeek.co.uk/2yd). Open source tooling exists to help manage multi-cluster workloads, including the upstream Kubernetes Multi-Cluster Services API (mcs-api), and the open source Amazon Web Services (AWS) Cloud Map MCS Controller (MCS-Controller). In this post, Cameron provides an overview of Kubernetes multi-cluster workload management, the mcs-api, and the MCS-Controller which is the AWS open source implementation of the mcs-api. [hands on]

![overview of mcs-api architecture](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2023/06/21/AWS-cloud-map-controller-solution-diagram.png)

Next up is a collaboration between Imaya Kumar Jagannathan and Vikram Venkataraman, who have put together [Multi-cluster cost monitoring for Amazon EKS using Kubecost and Amazon Managed Service for Prometheus](https://aws-oss.beachgeek.co.uk/2ye). In this hands on post, you will learn how you can use Kubecost to monitor multi-cluster Amazon EKS environments using Amazon Managed Service for Prometheus as the metrics store so you don’t have to worry about managing your own infrastructure to store Kubecost data. [hands on]

![overview of architecture solution](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2023/06/08/Large-scale-option.png)

Finally, make sure you check under Quick Updates Amazon EMR on EKS section for a couple of other useful new features and capabilities recently launched.

*we really need to use this word more in blogs!

**Apache Iceberg**

In [Accelerate data science feature engineering on transactional data lakes using Amazon Athena with Apache Iceberg](https://aws-oss.beachgeek.co.uk/2yg) Vivek Gautam, Naresh Gautam, Harsha Tadiparthi, and Mikhail Vaynshteyn review the benefits of using Athena with the Apache Iceberg open table format and how it simplifies common feature engineering tasks for data scientists. [hands on]

**Apache Kafka**

[Multi-tenancy Apache Kafka clusters in Amazon MSK with IAM access control and Kafka Quotas – Part 1](https://aws-oss.beachgeek.co.uk/2yh) is the first of a two part series from Vikas Bajaj that explains the concepts of how to enforce Kafka quotas in MSK multi-tenant Kafka clusters while using AWS Identity and Access Management (IAM) access control for authentication and authorisation. [hands on]

![overview of apache kafka quotas](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2023/06/08/BDB-2595-MSKQuotas-no-zero-trust-msk-cluster.jpg)

**Other posts and quick reads**

* [Introducing Industry Blueprints for Data & AI to Help AWS Partners Accelerate Solution Development](https://aws-oss.beachgeek.co.uk/2yc)  introduces AWS Industry Blueprints for Data & AI (Preview), an open-source initiative that offers a collection of building components, to accelerate how industry verticals are able to turn-data-to-insights needs

![overview of aws industry blueprints](https://d2908q01vomqb2.cloudfront.net/77de68daecd823babbb58edb1c8e14d7106e83bb/2023/06/13/Industry-Blueprints-Data-AI-1.png)

* [Enable remote reads from Azure ADLS with SAS tokens using Spark in Amazon EMR](https://aws-oss.beachgeek.co.uk/2yi) demonstrates how to set up quick, constrained, and time-bound authentication and authorisation to remote data sources in Azure Data Lake Storage (ADLS) using a shared access signature (SAS) when running Apache Spark jobs via EMR Notebooks attached to an EMR cluster [hands on]

![overview of azure adls and spark on amazon emr architecture](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2023/05/25/BDB-2904-01-arch.png)

* [Testing AWS Lambda functions with AWS SAM remote invoke](https://aws-oss.beachgeek.co.uk/2y7) looks at a new feature within AWS SAM that enables developers to invoke a Lambda function in the AWS Cloud from their development environment [hands on]
* [Encrypt Amazon RDS for PostgreSQL and Amazon Aurora PostgreSQL database with minimal downtime](https://aws-oss.beachgeek.co.uk/2y8) provides a hands on guide that walks you through how to convert an unencrypted RDS for PostgreSQL database to an encrypted database with minimum downtime [hands on]
* [Customize Slurm settings with AWS ParallelCluster 3.6](https://aws-oss.beachgeek.co.uk/2y9) looks at how you can customise the settings for the Slurm scheduler in your cluster configuration file to tweak the behaviour of your cluster to meet your specific use cases [hands on]
* [Optimize the cost of your Amazon ElastiCache for Redis workloads](https://aws-oss.beachgeek.co.uk/2ya) explores the top five recommendations on how to optimize the cost when running ElastiCache for Redis workloads using native ElastiCache features

![overview of redis workload optimisation](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2023/06/20/DBBLOG2805_image001-1024x576.png)


**Case Studies**

* [How Quora modernized MLOps on Amazon EKS to improve customer experience with scalable ML applications](https://aws-oss.beachgeek.co.uk/2yb) looks at how Quora modernised its MLOps platform on Amazon EKS. The key factors that drove the modernisation decisions were the ability to scale the ML platform with effective compute resource management for model training and serving, increase system reliability, and reduce cost of operations. Want to know more? Dive right in.

![overview of quora mlops on eks architecture](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2023/06/07/Quora-machine.png)

### Quick updates

**Amazon Corretto**

Amazon Corretto nightly builds are now available at [downloads.corretto.aws](https://aws-oss.beachgeek.co.uk/2y6) for Linux, Windows and Mac platforms. Developers can now test the latest OpenJDK community code and bug fixes without waiting for the next quarterly release.

Binaries for Corretto 8, 11, 17, and the latest Feature Release, Corretto 20, are being built combining the latest stable and development code from the next release of the OpenJDK projects. Early Access builds of upcoming releases will also be available prior to GA. Release and fast-debug builds, which contain assertions on JVM state and correctness, are available. In addition, we will be sharing early builds of experimental projects in binary form, for evaluation, validation and testing. For example, right now we have the Generational Shenandoah and Lilliput projects back ported to Corretto 17. The Generational Shenandoah Garbage Collector adds generational collection capabilities and aims to eventually reduce GC pauses below 1 ms for large-heap, high-throughput applications. The Lilliput project reduces the size of Java Object headers from 96 bytes down to 64 bytes, with a future goal of 32 bytes, which will reduce memory pressure and can result in fewer/shorter GC pauses. Along with the Corretto binaries, corresponding functional and integration test results are available so that anyone can see what fixes and issues are still present in the build.

Nightly Builds are for evaluation only and should not be relied on for production use.

**AWS CDK**

Alex Pulver shared [this post](https://aws-oss.beachgeek.co.uk/2y4) and looks at a new app-level bootstrap experimental feature for your AWS CDK stacks. You can read more in the docs about [app-staging-synthesizer-alpha module](https://aws-oss.beachgeek.co.uk/2y5)

**AWS Amplify**

AWS Amplify announced the UI Builder Figma plugin last week, empowering design and development teams to seamlessly collaborate within a Figma file. Use this plugin with the Amplify UI kit to easily theme your components, upgrade to new UI kit versions, and generate and preview React code from your designs directly in Figma.

**Grafana**

Amazon Managed Grafana now supports Trace Analytics with the OpenSearch Grafana data source plugin, in addition to the existing support for Log Analytics. Amazon Managed Grafana is a fully managed service for Grafana, a popular open-source analytics platform that enables you to query, visualise, and alert on your metrics, logs, and traces. OpenSearch is an open-source search and analytics engine for use cases such as log analytics, observability, real-time application monitoring, and clickstream analysis that is also offered as a fully managed Amazon OpenSearch Service. 

With this release, you can analyse your logs and trace data stored in OpenSearch, alongside metrics from your other data sources, in a single view in Amazon Managed Grafana, thus simplifying the correlation and analysis of these data points. The newly added trace views show the timeline of traces and allow you to drill down into spans, helping you to isolate the source of performance problems and diagnose their root cause directly from your Amazon Managed Grafana workspace.

**Amazon EMR on EKS**

A couple of quick updates this week.

First up was news that Volcano and Apache Yunikorn have been added as job schedulers when running EMR on EKS using Spark operator and spark-submit. Amazon EMR on EKS enables customers to run open-source big data frameworks such as Apache Spark on Amazon EKS. Using a custom job scheduler for Spark jobs enables fine-grained capacity management and faster pod provisioning at scale. The default Kubernetes scheduler handles the placement of individual pods, while maintaining constraints such as available capacity, resource requests and limits, and node affinity. However, it does not support scheduling based on jobs. With this new feature, customers have the option to use Apache Yunikorn and Volcano to schedule EMR on EKS Spark jobs with Spark operator and spark-submit. Customers can leverage features like gang scheduling, queue management, preemption, fair-share scheduling in these schedulers, which helps to deliver high scheduling throughput and optimised capacity.

We also announced the ability to control container log rotation when running Apache Spark jobs in EMR on EKS. Amazon EMR on EKS enables customers to run open-source big data frameworks such as Apache Spark on Amazon EKS. Customers can now enable container log rotation to avoid excessive log files impacting pod execution. For long running Spark jobs like Spark streaming, customers can run into low disk space issues which may cause performance degradation or job failure, and might get forced to manually delete logs from Kubernetes pods. With this release, customers can now enable container log rotation and customise how many log files will be kept in the Spark driver/executor pods, including setting the maximum size of each log file.

**MySQL**

Amazon Relational Database Service (Amazon RDS) for MySQL now supports MySQL minor versions 5.7.42 and 8.0.33. We recommend that you upgrade to the latest minor versions to fix known security vulnerabilities in prior versions of MySQL, and to benefit from the bug fixes, performance improvements, and new functionality added by the MySQL community. You can leverage automatic minor version upgrades to automatically upgrade your databases to more recent minor versions during scheduled maintenance windows.

**MariaDB**

Amazon Relational Database Service (Amazon RDS) for MariaDB now supports MariaDB minor versions 10.6.13, 10.5.20, 10.4.29, and 10.3.39. We recommend that you upgrade to the latest minor versions to fix known security vulnerabilities in prior versions of MariaDB, and to benefit from the bug fixes, performance improvements, and new functionality added by the MariaDB community. You can leverage automatic minor version upgrades to automatically upgrade your databases to more recent minor versions during scheduled maintenance windows. 

**Software Bill of Materials export**

Whilst not open source, I thought I would share this update as it might help folk provide Software Bill of Materials (SBOM) files within their AWS workloads. Announced at re:Inforce last week, Amazon Inspector now offers the ability to export a consolidated Software Bill of Materials (SBOMs) for all Amazon Inspector monitored resources across your organisation in industry standard formats, including CycloneDx and SPDX. With this new capability, you can use automated and centrally managed SBOMs to gain visibility into key information about your software supply chain. This includes details about software packages used in the resource, along with associated vulnerabilities. 

After Amazon Inspector exports the SBOMs to an Amazon S3 bucket, you have the option to download the SBOM artefacts and use Amazon Athena or Amazon QuickSight to analyse and visualise software supply chain trends. This capability in Amazon Inspector is available with a few clicks in the Amazon Inspector console or using Amazon Inspector APIs. 

### Videos of the week

**AWS re:Inforce 2023 - Security in the Open: OSS and AWS**

re:Inforce is a security learning conference featuring AWS experts and industry-leading customers. One of the highlights for me was the leadership session on open source security, where David Nalley and Mark Ryland provided a very nice overview of how we think of this space and some of the things we are working with the community on. This is a must watch session in my view.

{{< youtube kMY8gGmWfAI >}}

**Finding Your Way With CDK**

Recorded at the AWS Perth UG Meetup on June 23rd, James Vulling provided an in depth session on everything you needed to know about AWS CDK.

{{< youtube LmdZLAPdLcs >}}

**Build on Open Source**

For those unfamiliar with this show, Build on Open Source is where we go over this newsletter and then invite special guests to dive deep into their open source project. Expect plenty of code, demos and hopefully laughs. We have put together a playlist so that you can easily access all (sixteen) of the episodes of the Build on Open Source show. [Build on Open Source playlist](https://aws-oss.beachgeek.co.uk/episodes).

We are currently planning the third series - if you have an open source project you want to talk about, get in touch and we might be able to feature your project in future episodes of Build on Open Source.

# Events for your diary

If you are planning any events in 2023, either virtual, in person, or hybrid, get in touch as I would love to share details of your event with readers. 

**Apache Kafka London**
**Sainsbury's HQ, 33 Holborn, London EC4A1AA,  26th June 2023 5.45 - 8:30 pm**

OSO are teaming up with Sainsbury's, special sponsor for this event, to deliver an exciting program of talks that include AWS Community Builder John Mille whose talk, Kafka enterprise strategy to evolve with demand, will go over insights of early days, lessons learnt and successful governance patterns which made the onboarding smoother as time went. He will also review the different tooling involved in making this journey successful not only for business but for developers, along with leveraging Kafka community driven projects such as Kafka Connect.

If you are about and want to learn more about Apache Kafka, there is nothing better than attending a user group. Head over to the meetup page and sign up: [IN-PERSON: Kafka Enterprise Strategies: Best Practices](https://aws-oss.beachgeek.co.uk/2x0)

**CNCF Maintainer Circle - Community Management**
**June 28th, 2023 @ 10:00am PT / 17:00 UTC**

Managing a project is hard work. Maintainers are expected to wear many hats. Defining those hats early on can help a project grow and ultimately be sustainable enough to not rely on a few maintainers to do it all. Let’s deep dive in one role around - community and contributor management.

In this session, we will discuss strategies on how to build out strategy around intentional community roles, groups, and more so you aren’t doing everything. What’s everything?

* Creating, maintaining, and moderating mailing lists, slacks, forums, and more
* Recruiting and onboarding new contributors: outreach, their documentation, workflows, and processes
* Maintaining current contributors: swag, recognition programs, events, and more
* Social media
* User adoption strategies and operations
* Governance operations
* Website updates
* Documentation

Sounds interesting and very useful right? Check out more and add this to your calendar by [checking out the event page](https://aws-oss.beachgeek.co.uk/2y1)


**Yocto Project Developer Day 2023**
**EOSS, Prague, Czech Republic, Mon, Jun 26, 8 AM - 4 PM**

The Yocto Project DevDay is a technical conference for engineers, open source technologists, students and academia in the OSS space. This 1-day event is where individuals will learn about Yocto Projects’ direction -- including, but not limited to, new releases, development tools, features -- get training on the next wave of embedded Linux technologies (segment previously known as Yocto Project Developer Day), and network with their industry peers, Yocto Project maintainers, OpenEmbedded maintainers and experts.

[Check out more here](https://aws-oss.beachgeek.co.uk/2wy) and if you are going to be in Prague, why not pop along...after registering of course!

**Amplify Your Ideas: Hack, Host, and Share with Hashnode & AWS**
**July 1st — July 31, 2023**

This hackathon presents an opportunity for you to quickly transform your ideas into reality, easily build and ship feature-rich, fullstack apps using AWS Amplify, and share your experience on Hashnode. Prizes and complete details on how to participate will be announced on June 26th. [Register now](https://aws-oss.beachgeek.co.uk/2xx) for early notifications.


**CDK Day, 2023**
**Online, 29th September 2023**

Back for the fourth instalment, this Community led event is a must attend for anyone working with infrastructure as code using the AWS Cloud Development Kit (CDK). It is intended to provide learning opportunities for all users of the CDK and related libraries. The CFP is open, so if you have some ideas for some talks then make sure you check that section out. Also, this year they are accepting talks in Espanol! Woohoo, love it!

Check more at the website, [CDK Day](https://aws-oss.beachgeek.co.uk/fr) 


**Cortex**
**Every other Thursday, next one 16th February**

The Cortex community call happens every two weeks on Thursday, alternating at 1200 UTC and 1700 UTC. You can check out the GitHub project for more details, go to the [Community Meetings](https://aws-oss.beachgeek.co.uk/2h5) section. The community calls keep a rolling doc of previous meetings, so you can catch up on the previous discussions. Check the [Cortex Community Meetings Notes](https://aws-oss.beachgeek.co.uk/2h6) for more info.

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)

### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)