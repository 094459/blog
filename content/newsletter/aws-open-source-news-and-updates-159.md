---
title: 'AWS open source newsletter #159'
date: '2023-06-05'
tags : [ oss-newsletter, aws open source, Kubernetes, Amazon EKS, PostgreSQL, AWS Copilot, Redis, AWS CDK, Apache Iceberg, datree, Grafana, GraphQL, Go, Apache Flink, Deep Java Library, DJL, containerd, Cedar, Tailscale, Apache Cassandra  ]

---

## June  5th, 2023 - Instalment #159

Welcome to #159 of the AWS open source newsletter, where we try and share all the important open source news, projects, events, and content that open source builders want. This week we have new projects that include tools to help you generate test data, an accelerator for stable diffusion, tools to help you with managing application credentials and variables, a new connector for Apache Kafka, and more! From the AWS and broader community we have posts covering Kubernetes, PostgreSQL, AWS Copilot, Redis, AWS CDK, Apache Iceberg, datree, Grafana, GraphQL, Go, Apache Flink, Deep Java Library, DJL, containerd, Cedar, Tailscale and more.

Before diving into the newsletter, make sure you check out these two important announcements and please take some time to complete the OpenUK survey which is helping shine a light on the impact open source has in the UK.

Finally, the AWS Summit London is happening this week, including the Open Source Symposium the day before. Check out the events section for details of that if you are interested in how organisations are running open source at scale.

**End of Life announcements**

Last week there were a couple of important announcements you need to be aware of in case you missed them.

* [Amazon Keyspaces (for Apache Cassandra) support for Cassandra v3.11 end of life schedule](https://aws-oss.beachgeek.co.uk/2v7) looks at what the end of life (EOL) date for Apache Cassandra v3.11(May 1, 2023) means for users of Amazon Keyspaces (for Apache Cassandra)

* [Version 1 of the AWS Cloud Development Kit (AWS CDK) has reached end-of-support](https://aws-oss.beachgeek.co.uk/2v8) as of June 1, 2023, AWS CDK v1 has officially reached its end-of-support, so make sure you read this to find out more about your options and why you should be moving to AWS CDK v2

**OpenUK Survey**

OpenUK have been running an annual survey for a number of years now, collecting data and then producing and sharing reports that are widely cited. They are looking for more folk to respond, so please take a few minutes to complete the survey and provide your feedback on the state of open source in the UK.

Read more and find the link to the survey over at, [State of Open: The UK 2023 Survey](https://aws-oss.beachgeek.co.uk/2tw)

**Feedback**

Please please please take 1 minute to [complete this short survey](https://pulse.buildon.aws/survey/PJRTOUMK) and bask in the warmth of having helped improve how we support open source.

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes:  Marco Leong, Arthur Busser, Lukonde Mwila, Shimon Tolts, Peter Celentano,  Jeremy Ber, Gaurav Rele, Deepthi Mohan, Arun Nalpet Ramakrishna, Chance Lee, Gowtham S, Ken Collins, and Gabriel Manor

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution.*

#### Tools

**eventbridge-kafka-connector**

[eventbridge-kafka-connector](https://aws-oss.beachgeek.co.uk/2v6) This Kafka sink connector for Amazon EventBridge allows you to send events (records) from one or multiple Kafka topic(s) to the specified event bus, including useful features such as configurable topic to event detail-type name mapping, IAM role-based authentication, support for dead-letter queues, and schema registry support for Avro and Protocol Buffers (Protobuf). See configuration below for details.

**murmur**

[murmur](https://aws-oss.beachgeek.co.uk/2vi) is a small binary from Arthur Busser that reads its environment variables, replaces references to secrets with the secrets' values, and passes the resulting variables to your application. Variables that do not reference secrets are passed as-is. We like the detailed README and docs, including a comparison of how this works against other similar tools. It is also worth reading the [Reddit thread](https://aws-oss.beachgeek.co.uk/2vj) for even more context and info.

**cognito-token-verifier**

[cognito-token-verifier](https://aws-oss.beachgeek.co.uk/2vk) this library verifies that the signature of the JWT is valid, comes from a desired application, and that the token has not been tampered with or expired. Amazon Cognito is a service provided by Amazon Web Services (AWS) that allows users to authenticate and access AWS resources through credentials such as ClientID and Secret, or username and password. After a user successfully authenticates, Cognito returns a JSON Web Token (JWT), which contains the main information required to verify that the user has accessed our application. This library verifies that the signature of the JWT is valid, comes from a desired application, and that the token has not been tampered with or expired.

**aws-doc-extractor**

[aws-doc-extractor](https://aws-oss.beachgeek.co.uk/2vn) this project from Kevin Lin that pulls in AWS documentation and extracts, consolidates, and organises it. Kevin publishes this over at [https://awsnotes.dendron.so/about/readme](https://aws-oss.beachgeek.co.uk/2vo) so you can see what this project is capable of. Hat Tip to Corey Quin's newsletter where I found this project.

**aws-glue-test-data-generator**

[aws-glue-test-data-generator](https://aws-oss.beachgeek.co.uk/2vp) is an AWS Glue Configurable Test Data Generator. Test data generation plays a critical role in evaluating system performance, validating accuracy, bug identification, enhancing reliability, assessing scalability, ensuring regulatory compliance, training machine learning models, and supporting CI/CD processes. It enables the discovery of potential issues and ensures that systems operate as intended across diverse scenarios. The AWS Glue Test Data Generator provides a configurable framework for Test Data Generation using AWS Glue Pyspark serverless Jobs. The required test data description is fully configurable through a YAML configuration file.

![overview of architecture for glue test data generator](https://user-images.githubusercontent.com/17237690/219859235-924c127e-0c2d-40d3-837b-cb5c68aa2c45.png)

### Demos, Samples, Solutions and Workshops

**handsfree-stable-diffusion**

[handsfree-stable-diffusion](https://aws-oss.beachgeek.co.uk/2vl) is a CloudFormation template and script from Marco Leong for deploying Stable Diffusion webui - fully hands free. If you wanted to jump on the Generative AI wagon, then why not give this a go, and Marco is also [looking for feedback](https://aws-oss.beachgeek.co.uk/2vm) so let him know what you think.

### AWS and Community blog posts

**Community Roundup**

A couple of posts caught my eye this week in the AWS Community round up. As regular readers will know, I am a big fan of our recently Cedar launch and Gabriel Manor has put together a very nice post, [Scaling Authorization with Cedar and OPAL](https://aws-oss.beachgeek.co.uk/2ve) which is one of the clearest posts on how you might incorporate Cedar into your own applications. An essential read this week!

![app authorisation with cedar and opal](https://media.graphassets.com/amEDs7K9SdCK5oPQ6Udq)

AWS Hero Ken Collins also piqued my interest with his post, [Using Tailscale on Lambda for a Live Development Proxy](https://aws-oss.beachgeek.co.uk/2vg). [Tailscale](https://aws-oss.beachgeek.co.uk/2vh) makes networking fun/easy (according to their website) and in this post Ken explores how he extended a project to make it even easier to use Tailscale in Lambda Container.

![overview of using tailscale with aws lambda](https://res.cloudinary.com/practicaldev/image/fetch/s--7U22VKmy--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://lamby.cloud/img/blog/tailscale/live-development-proxy-overview.png)

**containerd**

In the post, [All you need to know about moving to containerd on Amazon EKS](https://aws-oss.beachgeek.co.uk/2v9), Arun Nalpet Ramakrishna, Chance Lee, and Gowtham S walk you through the context around Dockershim removal and the implications when moving from Docker Engine to containerd runtime to help you prepare run your Kubernetes workloads on it. [hands on]

![overview of moving to containerd](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2023/05/26/CRI-plugin.png)

**Apache Flink**

Apache Flink is a framework and distributed processing engine for stateful computations over data streams. Jeremy Ber, Gaurav Rele, and Deepthi Mohan have come together to write, [Real-time inference using deep learning within Amazon Kinesis Data Analytics for Apache Flink](https://aws-oss.beachgeek.co.uk/2va) where they present a solution for real-time classification using the Deep Java Library within Kinesis Data Analytics for Apache Flink. [hands on]

![overview of architecture for apache flink and djl](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2023/05/30/bdb-3098-arch-diagram.png)

**Other posts and quick reads**

* [Extending Java applications to directly access files in Amazon S3 without recompiling](https://aws-oss.beachgeek.co.uk/2vd) looks at the benefits of the [aws-nio-spi-for-s3](https://aws-oss.beachgeek.co.uk/1kt) package, design decisions and implementation, and how it can be employed with java-based applications without any requirement to modify code or recompile the application [hands on]

![overview of aws-nio-spi-for-s3](https://d2908q01vomqb2.cloudfront.net/e1822db470e60d090affd0956d743cb0e7cdf113/2023/05/25/Figure-1-3.png)
 
* [Announcing pull through cache for registry.k8s.io in Amazon Elastic Container Registry](https://aws-oss.beachgeek.co.uk/2v3)  shows you how to create a container image pull through cache for Kubernetes images from registry.k8s.io [hands on]
* [Open-Source Chip Design on AWS](https://aws-oss.beachgeek.co.uk/2vb) discusses the benefits of using open-source electronic design automation (EDA) software, which is required for designing integrated circuits

![graph of open source chip design](https://d2908q01vomqb2.cloudfront.net/c5b76da3e608d34edb07244cd9b875ee86906328/2023/05/09/Screenshot-2023-05-09-at-1.26.10-PM.png)

* [AWS SDK for Go Aligns with Go Release Policy on Supported Runtimes](https://aws-oss.beachgeek.co.uk/2vc) looks at how the AWS SDK for Go will now align with the Go Release policy
* [Go and Redis, Better Together](https://aws-oss.beachgeek.co.uk/2vf) provides a very nice walk through of Abhishek's session at Conf42 Goland, looking at how to leverage Redis from within Go [hands on]

![overview of Redis and go](https://miro.medium.com/v2/resize:fit:1400/format:webp/0*IEYRWrRhzyQDl1Ah.png)

### Quick updates

**PostgreSQL**

A few of updates this week.

Amazon Relational Database Service (RDS) for PostgreSQL now supports the latest minor versions PostgreSQL 15.3, 14.8, 13.11, 12.15, and 11.20. We recommend you upgrade to the latest minor versions to fix known security vulnerabilities in prior versions of PostgreSQL, and to benefit from bug fixes, performance improvements, and new functionality added by the PostgreSQL community. Please refer to the PostgreSQL community announcement for more details about the release.

Amazon RDS for PostgreSQL 16 Beta 1 is now available in the Amazon RDS Database Preview Environment, allowing you to evaluate the pre-release of PostgreSQL 16 on Amazon RDS for PostgreSQL. You can deploy PostgreSQL 16 Beta 1 in the Amazon RDS Database Preview Environment that has the benefits of a fully managed database, making it simpler to set up, operate, and monitor databases. The PostgreSQL community released PostgreSQL 16 Beta 1 on May 25, 2023. PostgreSQL 16 includes enhancements to logical replication, including enabling logical replication from standbys and numerous performance improvements. PostgreSQL 16 also adds support for SQL/JSON constructors and identity functions, more query types that can use parallelism, introduction of using SIMD CPU acceleration, and the ‘pg_stat_io’ view that provides statistics on I/O usage. Please refer to the PostgreSQL community announcement for more details about the release.

Amazon RDS for PostgreSQL now supports the HypoPG extension for creating hypothetical indexes, which lets you test the performance impact of an index on query plans before you build it.  Indexes are a way to accelerate queries in PostgreSQL, however, building indexes in a production system requires additional storage and may not necessarily improve the performance of slow-running queries. The HypoPG extension lets you test the impact of adding an index without having to build it, and lets you determine if you should build an index before using CPU and storage resources. HypoPG helps to provide you insight into whether the PostgreSQL query planner will choose to use an index and any performance benefits that result from the use of the index. The HypoPG extension is available on all database instances in Amazon RDS running PostgreSQL 15.3 and higher, 14.8 and higher, and 13.11 and higher.

You can dive deeper into this topic by checking out the blog post, [Build hypothetical indexes in Amazon RDS for PostgreSQL with HypoPG](https://aws-oss.beachgeek.co.uk/2v5) where Peter Celentano provides a hands on guide into how you can use HypoPG for testing and evaluating index configurations in PostgreSQL before going to the expense of building actual indices on your database.

**Grafana**

Amazon Managed Grafana is a fully managed service for Grafana, a popular open-source analytics platform that enables you to query, visualise, and alert on your metrics, logs, and traces. Last week we announced that Amazon Managed Grafana is now System and Organization Controls (SOC) compliant. You can now use Amazon Managed Grafana to visualise data that is subject to SOC compliance. AWS SOC reports are independent third-party examination reports that demonstrate how AWS achieves key compliance controls and objectives. The purpose of these reports is to help you and your auditors understand the AWS controls established to support operations and compliance. AWS SOC 1 and SOC 2 Security, Availability, and Confidentiality, and Privacy Reports are also now available. You can download the AWS SOC reports in [AWS Artifact](https://aws-oss.beachgeek.co.uk/2v4). 

**GraphQL**

AWS AppSync enables developers to build serverless, scalable and performant GraphQL APIs that are designed to securely connect their apps to data and events. Today, we announce the general availability of Merged APIs, which enable GraphQL schema composition and federation for AppSync APIs. A Merged API is a single GraphQL API composed from multiple source GraphQL APIs, representing different services or data sources. With a Merged API an organisation can provide a single API schema to data consumers, while enabling independent evolution of sub-schemas by the teams that are most familiar with its related data domain. For teams sharing development of a single AppSync API, the Merged APIs feature allows them to collaborate seamlessly while operating independently.

**Redis**

Amazon ElastiCache for Redis data tiering on Graviton2-based R6gd nodes now supports auto scaling to automatically adjust capacity to maintain steady and predictable performance at the lowest possible cost. You can automatically scale your cluster horizontally by adding or removing shards or replica nodes. ElastiCache for Redis data tiering uses AWS Application Auto Scaling to manage scaling and Amazon CloudWatch metrics to determine when it is time to scale up or down.  ElastiCache for Redis data tiering supports target tracking and scheduled scaling policies. With target tracking, you define a target metric and ElastiCache adjusts resource capacity in response to live changes in resource utilisation. The intention is to provide enough capacity to maintain utilisation at the target value specified. For instance, when capacity utilisation rises, ElastiCache will add R6gd nodes to your cluster to increase capacity and reduce utilisation back to the target level. This enables your cluster to adjust capacity automatically to maintain high performance. Conversely, when capacity utilisation drops below the target amount, ElastiCache will remove R6gd nodes from your cluster to reduce over-provisioning and lower costs. With scheduled scaling, you can set specific days and times for ElastiCache to scale your cluster to accommodate predictable workload capacity changes.

**AWS Copilot**

Version 1.28 of AWS Copilot now supports a new Static Site pattern, that makes it easier to deploy single page web applications on AWS. AWS Copilot is a command-line interface (CLI) that makes it easier for customers to build, deploy, and operate containerised applications on AWS by providing common application architecture and infrastructure patterns, user-friendly operational workflows, and configuring deployment pipelines.

Customers can get a single-page static website created by simply running copilot svc init -t Static Site. Previously, customers could only build dynamic websites that relied on server-side rendering and lacked a convenient pattern to create static sites or single page applications using AWS Copilot. The new Static Site pattern simplifies the multi-step process of creating a Amazon CloudFront distribution, AWS S3 bucket, AWS Certificate Manager certificate, Amazon Route 53 records, and uploading local assets. With this launch, developers can define static websites along with their other existing Amazon Elastic Container Service and AWS App Runner services.


### Videos of the week

**Enforcing Kubernetes Security Policies with Datree**

Fresh from the Containers from the Couch Channel is this session from Lukonde Mwila and Shimon Tolts, where they show you how you can use [Datree](https://aws-oss.beachgeek.co.uk/2vq) to enforce Kubernetes security policies.

{{< youtube keGWfWlpP5Y >}}
{% youtube keGWfWlpP5Y %}

**Build on Open Source**

For those unfamiliar with this show, Build on Open Source is where we go over this newsletter and then invite special guests to dive deep into their open source project. Expect plenty of code, demos and hopefully laughs. We have put together a playlist so that you can easily access all (sixteen) of the episodes of the Build on Open Source show. [Build on Open Source playlist](https://aws-oss.beachgeek.co.uk/episodes).

We are currently planning the third series - if you have an open source project you want to talk about, get in touch and we might be able to feature your project in future episodes of Build on Open Source.

# Events for your diary

If you are planning any events in 2023, either virtual, in person, or hybrid, get in touch as I would love to share details of your event with readers. 

**AWS Open Source Symposium**
**RSA House Durham Street Auditorium, London, June 6th**

The AWS Open Source Symposium will focus on the two themes of Data Analytics and Developer Platforms built with CNCF technologies.

For Developer Platforms, the following will be discussed: 1/Components of a Developer Platform, 2/Building or Assembling Developer Platforms, 3/Operating Developer Platforms, and 4/Existing Tooling and Technologies.

­­For Data Analytics and AI/ML, the discussion will focus on customers' open source implementations on Kubernetes and their integration with AWS services, such as Open Source Spark, Iceberg, Hudi, Trino, JupyterHub, and more.

There will also be a focus on running scalable data workloads on Kubernetes and discussing Cloud Native Batch Systems, such as Apache YuniKorn and Volcano batch schedulers, as well as any multi Kubernetes cluster batch schedulers like Armada.

­­The goal of the symposium is to bring customers together to share thoughts on how they are using these solutions to solve big data and observability use cases, as well as to discuss lessons learned and mistakes to avoid.

Register and save your spot via the [AWS Open Source Symposium](https://aws-oss.beachgeek.co.uk/2tv) link.


**Open source Table Formats with AWS Glue and Amazon EMR**
**Online, 6th June 5PM UK time**

Curious about Transactional Data Lakes? Come join our AWS experts as we take you through the most popular open source table formats, how these table formats can help you enable a modern data strategy, and how to build on these formats with Amazon EMR and AWS Glue. In this session, we'll cover some of the key differences between these different table formats, help you decide which table format may be the best fit for your workloads, and show you how to start building today.

You can [join via YouTube live here](https://aws-oss.beachgeek.co.uk/2pu)

**London Open Source Data Infrastructure Meetup**
**Huckletree Shoreditch, 6:30PM - 9:30PM**

As part of London Tech Week Aiven are co-hosting the 'London Open Source Data Infrastructure Meetup' on the 14th of June. This event is in collaboration with Hugh Evans from Daemon the 'AI and Deep Learning for Enterprise' group. The speaker panel includes Ricardo Sueiras from Amazon Web Services (AWS) discussing the wonders of Apache Airflow, Davies Oludare from Confluent shedding light on the intricate world of Kafka, and Ed Shee from Seldon breaking down the nuances of ML-powered summarisation.

Spaces are limited, so make sure you reserve your spot by [checking and out the meetup page](https://aws-oss.beachgeek.co.uk/2tu)

**Open Source Festival**
**Lagos, Nigeria - June 15th-17th**

An established and essential event for all open source developers, Open Source Festival promises to be even bigger and better than previous years. I feel very privileged to have spoken at this event in 2020, and so make sure you check this out if you are in the region or perhaps if you are maybe looking to sponsor an open source event, then maybe this is the one you should check out.

Check out more on their homepage, [Open Source Festival](https://aws-oss.beachgeek.co.uk/2ss) 

**Live AWS and Apache Hudi Workshop**
**Online, June 22nd at 8am PT**

Nadine Farah and Soumil S are teaming up to deliver  a live workshop that will mimic a typical use case, in this instance, building near real time dashboards for a fictional ride sharing company. 

![overview of workshop technologies covered](https://assets.website-files.com/61f2440c9fcbc37831846652/647657293b4973482c3a3b58_AWS%20WORKSHOP%20Q2%202023%20-%20Copy%20of%20Architecture-version-1%20(1).jpg)

Make sure you reserve your place by going to the registration page, [Live AWS and Apache Hudi Workshop: Build a ride share lakehouse platform](https://aws-oss.beachgeek.co.uk/2v2)


**Cortex**
**Every other Thursday, next one 16th February**

The Cortex community call happens every two weeks on Thursday, alternating at 1200 UTC and 1700 UTC. You can check out the GitHub project for more details, go to the [Community Meetings](https://aws-oss.beachgeek.co.uk/2h5) section. The community calls keep a rolling doc of previous meetings, so you can catch up on the previous discussions. Check the [Cortex Community Meetings Notes](https://aws-oss.beachgeek.co.uk/2h6) for more info.

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)

### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)