---

title: 'AWS open source news and updates #118'
date: '2022-06-24'
tags : [ oss-newsletter, aws open source, Backstage, OpenSearch, Qiskit, PostgreSQL, Prometheus, Kubernetes, ROS, Unified ID, Grafana, PostGraphile, CloudQuery, Apache Iceberg, Apache Airflow, AWS SAM, Babelfish for PostgreSQL, Apache Hudi]

---

## June 22nd, 2022 - Instalment #118

Welcome to regular and new readers alike, to the AWS open source newsletter episode #118.

This week we feature more new open source projects, such as "seed-farmer", and orchestration tool modelled after GitOps deployments, "aws-proton-plugins-for-backstage" Backstage plugins for interacting with AWS Proton, "dcv-gnome-shell-extension" is a GNOME Shell extension to provide functionalities required by NICE DCV, "simpleiot-arduino" an Arduino library to integrate with the SimpleIOT framework, "event-driven-weather-forecasts" an event driven weather forecasting demo, and many more.

We also have blog posts, tutorials and videos on topics that include Backstage, OpenSearch, Qiskit, Unified ID, Grafana, PostGraphile, CloudQuery, Apache Iceberg, Apache Airflow, AWS SAM, Babelfish for PostgreSQL and many more. Finally, make sure you check out the events section for the latest open source events, there are some great events coming up over the next week.


**Feedback**

At Amazon we work backwards from our customers, and one of the ways we do that is collecting data to help us know what is important and what we should focus on.

To that end, please could you [complete this simple](https://eventbox.dev/survey/8G7HRWY), anonymous survey. The first 25 will get an AWS $25 credit code.


**10th Annual Open Source Jobs Report**

If you missed this last week, the Linux Foundation shared publication of its tenth iteration of the Linux Foundation’s Open Source Jobs Report for organisations, hiring managers, and, of course, open source professionals. It is well worth reading, you can grab the report via this link, [The 10th Annual Open Source Jobs Report: Critical Skills, Hiring Trends, and Education](https://aws-oss.beachgeek.co.uk/1tz). Always provides some interesting insights. One to pique your interest is that 86% of hiring managers say hiring open source talent is a priority for 2022. Read the report to find out even more interesting stats.

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created. 

So thank you to the following open source heroes: Syeda Marium Faheem, Niall Thomson, Siddharth Kothari, Kishore Dhamodaran, Mohit Mehta, Giovanni Matteo Fumarola, Jared Keating, Jack Ye, Romaric Philogène, Jordan Sullivan, Justin Leto, Sai Parthasaradhi, Rakesh Raghav, Veeranjaneyulu Grandhi, Prathap Thoguru, Kishore Dhamodaran, Yevgeny Pats, Arvind Raghu, Adam Solomon, J.D. Bean, Kanishk Prasad, Anuj Gupta, James Eastham , Álvaro Hernández and Bart Farrell.

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution.*

#### Tools

**seed-farmer**

[seed-farmer](https://aws-oss.beachgeek.co.uk/1u9) is an open source orchestration tool that works with AWS CodeSeeder (see [#97](https://dev.to/aws/aws-open-source-news-and-updates-97-55gf)) and acts as an orchestration tool modelled after GitOps deployments. It has a CommandLine Interface (CLI) based in Python. It leverages modular code deployments ([modules](https://aws-oss.beachgeek.co.uk/1ua)) leveraging manifests and deployspecs, keeping track of changes and applying changes as need / detected.

![architecture of seed-farmer solution](https://seed-farmer.readthedocs.io/en/latest/_images/SeedFarmer.png)

**aws-proton-plugins-for-backstage**

[aws-proton-plugins-for-backstage](https://aws-oss.beachgeek.co.uk/1u8) This repository contains a set of Backstage plugins for interacting with AWS Proton. The plugins provide an entity card to display the status of an AWS Proton service, and A scaffolder action to create an AWS Proton service. See the blog post below for more details on getting started with this project.

![demo of aws proton plugin for backstage](https://raw.githubusercontent.com/awslabs/aws-proton-plugins-for-backstage/main/docs/images/proton-backstage-demo.gif)

**dcv-gnome-shell-extension**

[dcv-gnome-shell-extension](https://aws-oss.beachgeek.co.uk/1u5) is a GNOME Shell extension to provide functionalities required by NICE DCV. NICE DCV is a high-performance remote display protocol that provides customers with a secure way to deliver remote desktops and application streaming from any cloud or data center to any device, over varying network conditions.

**config-daily-report**

[config-daily-report](https://aws-oss.beachgeek.co.uk/1u1) this repo contains a solution that you can use in order to generate a daily CSV report at specific time. The report will include new or changed resources, with a link to the AWS Config UI. The reporter is triggered using a Cloudwatch event, that will trigger a Lambda function. The Lambda will use SES to send an email.

![architecture of solution for daily reports](https://github.com/aws-samples/config-daily-report/blob/main/draw/config-daily-reporter.drawio.png?raw=true)

**simpleiot-arduino**

[simpleiot-arduino](https://aws-oss.beachgeek.co.uk/1u4) is an Arduino library is an easy way to connect and send/receive data to the cloud via the SimpleIOT framework. SimpleIOT abstracts out IoT device connectivity and hides the underlying details so you can focus on your application's unique features.

![architecture for simpleiot arduino](https://github.com/awslabs/simpleiot-arduino/blob/main/media/readme/Basic-Concepts.png?raw=true)

### Demos, Samples, Solutions and Workshops

**event-driven-weather-forecasts**

[event-driven-weather-forecasts](https://aws-oss.beachgeek.co.uk/1u2) this demo is a fully automated cloud-native event driven weather forecasting. It uses the Unified Forecast System (UFS), a community-based, coupled, comprehensive Earth modelling system.

![architecture and demo of weather forecast](https://raw.githubusercontent.com/aws-samples/event-driven-weather-forecasts/main/plot_ufs_phyf_tprcp.gif)

**aws-nitro-enclaves-bidding-service**

[aws-nitro-enclaves-bidding-service](https://aws-oss.beachgeek.co.uk/1u3) is a Proof of Concept (POC) bidding service application will demonstrate the use of AWS Nitro Enclaves to perform computation on multiple sensitive datasets. We will utilise Nitro Enclaves with AWS Key Management Service (KMS) to create an isolated compute environment, allow the environment to process encrypted datasets from multiple parties, and return an output. The POC application will be centred around the scenario of real estate bidding where a bidding service will take in encrypted bids from two buyers and determine the highest bid on each property without disclosing the bid amounts to each buyer. 

![architecture of enclave bidding solution](https://github.com/aws-samples/aws-nitro-enclaves-bidding-service/blob/main/BiddingServiceApplicationDiagram.png?raw=true)

**route53resolver-dns-firewall-automation-bring-your-own-lambda**

[route53resolver-dns-firewall-automation-bring-your-own-lambda](https://aws-oss.beachgeek.co.uk/1u6) this project provides a serverless mechanism to update your AWS DNS Firewall lists.

![architecture of dns firewall solution](https://github.com/aws-samples/route53resolver-dns-firewall-automation-bring-your-own-lambda/blob/main/img/solution.png?raw=true)

**amazon-redshift-streaming-workshop**

[amazon-redshift-streaming-workshop](https://aws-oss.beachgeek.co.uk/1u7) In this workshop, you will build a streaming analytics application using Amazon Redshift streaming ingestion. You will create a near-real time logistics dashboard using Amazon Managed Grafana to provide augmented intelligence and situational awareness for the logistics operations team. It connects to a Redshift cluster which uses Redshift streaming to analyse data from a Kinesis data stream.

![streaming ingestion workshop](https://github.com/aws-samples/amazon-redshift-streaming-workshop/blob/main/images/image-20220601123345968.png?raw=true)

### AWS and Community blog posts

**Backstage**

[Backstage](https://aws-oss.beachgeek.co.uk/1tj) is an open-source project, originally created at Spotify and now a CNCF incubating project, that provides a framework for building developer portals. AWS Proton is a managed service for platform engineers that helps you define, vend, and maintain infrastructure templates for self-service deployments. In this post, [Provisioning infrastructure using the AWS Proton open-source Backstage plugin](https://aws-oss.beachgeek.co.uk/1tk), Niall Thomson shares how AWS is contributing to the Backstage open source community with our AWS Proton plugin for Backstage. Check out the code repos above if you want to dive deeper, and follow along with the tutorial. [hands on]

![architecture of backstage and proton plugin](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2022/06/15/backstage-1.png)

**OpenSearch**

In the post/tutorial, [Tutorial: Build Search UI with OpenSearch and ReactiveSearch](https://aws-oss.beachgeek.co.uk/1ty), Siddharth Kothari walks you through how to build search UIs powered by OpenSearch and ReactiveSearch.

**Apache Iceberg**

Apache Iceberg is an open-source table format for data stored in data lakes. In the post, [Build an Apache Iceberg data lake using Amazon Athena, Amazon EMR, and AWS Glue](https://aws-oss.beachgeek.co.uk/1tx) Kishore Dhamodaran, Mohit Mehta, Giovanni Matteo Fumarola, Jared Keating, and Jack Ye come together to share how to use Amazon EMR Spark to create an Iceberg table, load sample books review data, and use Athena to query, perform schema evolution, row-level update and delete, and time travel, all coordinated through the AWS Glue Data Catalog. [hands on]

![architecture of apache iceberg solution](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2022/06/07/Apache-Iceberg-Amazon-Athena-e1654625504144.png)

**Qovery**

Qovery Engine is an open-source abstraction layer library that turns easy application deployment on AWS (and other Cloud providers) in just a few minutes. The Qovery Engine is written in Rust and takes advantage of Terraform, Helm, Kubectl, and Docker to manage resources. If you have not checked this project out, I would encourage you to do so - it is pretty incredible what the team are doing. CEO and co-founder Romaric Philogène is a prolific blogger/vblogger, and last week he shared a super interesting post, [The Top 10 AWS Architecture Built with Qovery in 2022](https://aws-oss.beachgeek.co.uk/1tv). This weeks must read post.

![sample architecture - no 2](https://images.prismic.io/qovery/42a5fa0c-181f-4260-aec1-0999a442df35_The+DMZ.png?auto=compress,format)
 
**Qiskit**

[Qiskit [kiss-kit]](https://aws-oss.beachgeek.co.uk/1tw) is an open-source SDK for working with quantum computers at the level of pulses, circuits, and application modules. In the post, Introducing the Qiskit provider for Amazon Braket, Jordan Sullivan shares an open sourced solution (a Qiskit provider for Amazon Braket) that allows users to take their existing algorithms written in Qiskit and run them directly on Amazon Braket. [hands on]

**PostgreSQL**

We have a number of posts this weeks covering PostgreSQL. First up we have [Optimized bulk loading in Amazon RDS for PostgreSQL](https://aws-oss.beachgeek.co.uk/1tq) where Justin Leto presents several bulk data loading strategies optimised for Amazon Relational Database Service (Amazon RDS) for PostgreSQL.

![architecture of bulk loading](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2022/06/15/DBBLOG-1701-image001.png)

Following that, Sai Parthasaradhi, Rakesh Raghav, and Veeranjaneyulu Grandhi walk you through how to validate database schema objects migrated from Db2 LUW to Amazon RDS for PostgreSQL or Aurora PostgreSQL in their post, [Validate database objects after migrating from IBM Db2 LUW to Amazon Aurora PostgreSQL or Amazon RDS for PostgreSQL](https://aws-oss.beachgeek.co.uk/1tr) [hands on]

And finally, in the post [Modernize database stored procedures to use Amazon Aurora PostgreSQL federated queries, pg_cron, and AWS Lambda](https://aws-oss.beachgeek.co.uk/1ts) Prathap Thoguru and Kishore Dhamodaran demonstrate how to modernise your stored procedures using Aurora PostgreSQL extensions such as postgres_fdw, pg_cron, and aws_lambda. [hands on]

![architecture of postgres modernisation](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2022/06/10/DBBLOG-2065_Architecture.png)

**PostGraphile & CloudQuery**

Yevgeny Pats shares how to setup CloudQuery (an open-source cloud asset inventory tool powered by SQL) to build your cloud asset inventory in PostgreSQL and build a GraphQL API query layer with PostGraphile (an open source project that enables you to provide a lightning-fast GraphQL API backed primarily by your PostgreSQL database) on top of it, in his post/tutorial [How to expose CloudQuery with PostGraphile](https://aws-oss.beachgeek.co.uk/1tu) 

**Unified ID 2.0**

[Unified ID 2.0 (UID2)](https://aws-oss.beachgeek.co.uk/1tn) is a deterministic identifier based on PII (for example, email or phone number) with user transparency and privacy controls. In the post, [Introducing Unified ID 2.0 Private Operator Services on AWS Using Nitro Enclaves](https://aws-oss.beachgeek.co.uk/1to), Arvind Raghu, Adam Solomon, J.D. Bean, Kanishk Prasad, and Anuj Gupta collaborate to provides a brief overview of UID2 functionality and then show you how [you can deploy this on AWS](https://aws-oss.beachgeek.co.uk/1tp).

![architecture of solution](https://d2908q01vomqb2.cloudfront.net/c5b76da3e608d34edb07244cd9b875ee86906328/2022/06/20/uid2-1.png)

**Other posts you might like from the past week**

* [Create cross-account, custom Amazon Managed Grafana dashboards for Amazon Redshift](https://aws-oss.beachgeek.co.uk/1tl) is a a step-by-step tutorial to use the Amazon Redshift data source plugin to visualize metrics from your Amazon Redshift clusters hosted in different AWS accounts using [hands on]

![architecture of redshift and grafana multi account tutorial](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2022/06/15/BDB-2040-image001.png)

* [Build and simulate a Mini Pupper robot in the cloud without managing any infrastructure](https://aws-oss.beachgeek.co.uk/1tm) uses a simple Mini Pupper sample application to demonstrate how to use AWS RoboMaker for robotics application development, testing, and simulation. [hands on]
* [Troubleshooting Amazon EKS API servers with Prometheus](https://aws-oss.beachgeek.co.uk/1tt) walks you through some nice dashboards that can help you when you run into operational issues with your Kubernetes clusters

![example dashboard for eks prometheus post](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2022/06/17/shane-13.png)

### Quick updates

**PostgreSQL**

Amazon Aurora PostgreSQL-Compatible Edition now supports PostgreSQL major version 14 (14.3). PostgreSQL 14 includes performance improvements for parallel queries, heavily-concurrent workloads, partitioned tables, logical replication, and vacuuming. PostgreSQL 14 also improves functionality with new capabilities. For example, you can cancel long-running queries if a client disconnects and you can close idle sessions if they time out. Range types now support multi-ranges, allowing representation of non-contiguous data ranges, and stored procedures can now return data via OUT parameters. This release includes new features for Babelfish for Aurora PostgreSQL version 2.1. 

**Apache Kafka**

Amazon Managed Streaming for Apache Kafka (Amazon MSK) now supports Apache Kafka version 3.1.1 and 3.2.0 for new and existing clusters. Apache Kafka 3.1.1 and Apache Kafka 3.2.0 includes several bug fixes and new features that improve performance. Some of the key features include enhancements to metrics and the use of topic IDs. MSK will continue to use and manage Zookeeper for quorum management in this release for stability. 

### Videos of the week

**Apache Airflow**

A great summary and links to the videos from the Apache Airflow Summit from Jarek Potiuk, in his post [Airflow Summit 2022 — The Best Of.](https://aws-oss.beachgeek.co.uk/1u0) Make sure you go through those, as there are some great sessions.

**Babelfish for PostgreSQL**

AWS Data Hero Álvaro Hernández and Bart Farrell show how you can use Postgres Babelfish (a SQL Server-compatible Postgres flavour) and Timescaledb (time-series extension for Postgres) we can deliver open source time-series native capabilities on top of SQL Server protocol, available to SQL Server users.

{{< youtube CUE2Rj3Sp8Y >}}


**AWS SAM and .NET**

James Eastham shares how to get started using AWS SAM to build serverless applications using .NET 6.

{{< youtube 0C9KWutITf0 >}}


**Apache Hudi: EMR on EKS**

From the Apache Hudi community call, Syeda Marium Faheem shares the success story of how Bazaar Technologies leveraged Apache Hudi to build robust cost efficient data pipelines using EMR on EKS.

{{< youtube 5h4i63aB1-I >}}


### Events for your diary

**Build and Operate Containers Apps with AWS Copilot**
**June 25th 6pm Singapore time**

In this session of the Angular PH and AWS Siklab Monthly Meetup, learn how to Build and Operate Containers Apps with AWS Copilot with speaker Donnie Prakoso, Senior Developer Advocate at AWS.

You still have time to register for this event as it will be live cast. Register via [this link here](https://aws-oss.beachgeek.co.uk/1ud)

**Observability: Open Source Solutions**
**June 28th, 10:00am - 2:15pm PDT**

The AWS Monitoring and Observability Team invites you to participate in a hands on session with Amazon Managed Service for Prometheus, Amazon Managed Service for Grafana and AWS Distro for Open Telemetry. During this session you will use these services in creating workspaces, ingesting/querying metrics, logs and trace data and viewing in a dashboard you will set up. The afternoon will close with demo of what you have done and highlighting the value in MTTD, MTTI, MTTR and application performance.

This event is designed for those looking to implement AWS Observability using open-source services to visualize their data with native or 3rd party tools. Site reliability engineers, operations engineers, systems engineers, and DevOps. Familiarity with monitoring concepts such as logs, metrics, traces, alarms, and the dashboard is recommended, but not required.

Register [via this page](https://aws-oss.beachgeek.co.uk/1qt).

**Distributed ML training using PyTorch on High-Performance Computing (HPC) clusters**
**June 29th 7:00am**

By using PyTorch Fully Sharded Data Parallel (FSDP) library for distributed training with powerful Amazon EC2 instances and AWS ParallelCluster, you can easily implement distributed training architectures to accelerate training for large ML models. Attend this hands-on workshop to learn about best practices when deploying distributed training architectures on AWS using EC2 and PyTorch FSDP library.

Attend this webinar to learn how to get started with AWS on PyTorch, learn how to create a distributed training architecture using AWS ParallelCluster, and lLearn about PyTorch Fully Sharded Data Parallel (FSDP) library for distributed training.

Get more info and sign up, on the [Building Deep learning applications using PyTorch on AWS](https://aws-oss.beachgeek.co.uk/1ub) registration page.

**German CDK Happy Hour**
**June 29th 5pm CET**

One for any German speaking open source readers, the CDK Happy Hour is an hour of sharing of the open source project AWS CDK.

Find out more and sign up by checking out the [meetup registration page](https://aws-oss.beachgeek.co.uk/1uc).

**Deploy NextJS to AWS Amplify**
**June 30th, 7:00 pm Indonesia time**

From our German community to our Indonesian community, join AWS Community Builder Rogers Dwiputra Setiady as he shares how to create a website using Next.js and deploy via CI/CD to AWS Amplify.

Find out more and sign up by clicking on the [eventbrite link](https://aws-oss.beachgeek.co.uk/1ue)

**AWS Tech Conference**
**30th June, 9am**

Join this online conference that is being organised by the AWS User Group Ukraine. Among the talks you will find Darko who will be sharing three open source tools that will make your life working with AWS easier. Find out more about the other sessions and register, by heading over to the [AWS User Group Ukraine home page](https://aws-oss.beachgeek.co.uk/1ti). The event is free to attend, but you can also buy a number of different sponsorship tickets which will help fund the Ukrainian charity fund.


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