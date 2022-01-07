---
title: 'AWS open source news and updates 84'
date: '2021-10-04'
tags : [ oss-newsletter ]
---
## October 4th, 2021 - Instalment #84

Newsletter #84.

Welcome to issue #84 of this newsletter, and we have more great new open source projects for you this week. We have a couple of great security/compliance/governance tools that will help you with security in **cloudgraphdev** and (the amazingly named) **wonk**, **placebo**, a tool to help you mock tests, a new cli from AWS to help you simplify those of you working with genomics workloads, and more. 

With the GA last week of OpenTelemetry and Prometheus managed services on AWS, we have a plethora of posts covering a number of different topics as well as Apache Tinkerpop, Bottlerocket, Apache Kafka, OpenSearch and Terraform. make sure you check out the events section too, and as always, if you use, or are creating/ working on an open source project you would like me to include in this newsletter, then please get in touch.
   

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Danilo Poccia, Mitch Garnaat, jaitl, AutoCloud, Amino Inc, Kyle Davis, Jegan Sundarapandian, Chloe Goldstein, Imaya Kumar Jagannathan, Marc Chene, Vikram Venkataraman, Arun Chandapillai, Abhi Khanna, Mike George, Abhi Khanna, Channy Yun, Jeremy Cowan, Sai Charan Teja Gopaluni, and Vijay K Sikha, Alolita Sharma, Nizar Tyrewalla, Brad Bebee, Kelvin Lawrence, Stephen Mallette, Huy Vo, Iris Song, Michael Hausenblas and Garry Stafford.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest open source projects

**amazon-genomics-cli**

[amazon-genomics-cli](https://aws-oss.beachgeek.co.uk/yk) this open source project is a tool to simplify the processes of deploying the AWS infrastructure required to run genomics workflows in the cloud, to submit those workflows to run, and to monitor the logs and outputs of those workflows. You can find out more and get hands on by reading and working through Danilo Poccia's blog post, [New – Amazon Genomics CLI Is Now Open Source and Generally Available](https://aws-oss.beachgeek.co.uk/yq). You can also check out [this YT session](https://www.youtube.com/watch?v=mMeBeFbFzq0) that provides some additional background before showing you this in action.

**cloudgraphdev**

[cloudgraphdev](https://aws-oss.beachgeek.co.uk/yp) another interesting tool to help you manage security on AWS, CloudGraph is an open-source search engine for your public cloud infrastructure, powered by DGraph and GraphQL. You can quickly query assets, configurations, and more across accounts and providers. CloudGraph also enables you to solve a host of security, compliance, governance, and FinOps challenges in the time it takes to write a single GraphQL query. Very nice project from the folks at AutoCloud

![demo](https://raw.githubusercontent.com/cloudgraphdev/cli/master/docs/images/init.png)

**wonk**

[wonk](https://aws-oss.beachgeek.co.uk/yl) this project from Amino Inc is a tool for combining a set of AWS policy files into smaller compiled policy sets. Good documentation covering the typical use cases and why you might find this useful. Definitely a tool for your armoury as you look to put security first.

**placebo**

[placebo](https://aws-oss.beachgeek.co.uk/yn) Mitch Garnaat has put together this open source tool Placebo, that allows you to mock boto3 calls that look just like normal calls but actually have no effect at all. It does this by allowing you to record a set of calls and save them to a data file and then replay those calls later (e.g. in a unit test) without ever hitting the AWS endpoints. Provide examples on how to get up and running

**kDynamoMapper**

[kDynamoMapper](https://aws-oss.beachgeek.co.uk/yo) if you are a Kotlin developer, this project from jaitl will be of interest. It provides a lightweight AWS DynamoDB mapper for Kotlin written in pure Kotlin. Check out the full README.md for more details.

### AWS and Community blog posts

**Apache Kafka**

When it comes to the topic of Data Analytics, you can always count on Gary Stafford to come up with the goods, and last week he published another great post, [Stream Processing with Apache Spark, Kafka, Avro, and Apicurio Registry on Amazon EMR and Amazon MSK](https://aws-oss.beachgeek.co.uk/z1). This is the second part of previous post I shared a few weeks ago, and in this post he shows you how you can read and write messages to and from Amazon MSK in Apache Avro format. The post also shows how you can store the Avro-format Kafka message’s key and value schemas in Apicurio Registry and retrieve the schemas instead of hard-coding the schemas in the PySpark scripts. [hands on]

![arch](https://miro.medium.com/max/4800/1*XGnUIP5Xj3w1ODheHBEl-A.png)

**Bottlerocket**

Bottlerocket is an open source Linux-based operating system from Amazon that was purpose built for running containers with a strong emphasis on security. The result is an operating system that comes with a variety of built-in controls for creating a secure environment for running containerised workloads. If you want to dive deep and find out more, then Jeremy Cowan, Sai Charan Teja Gopaluni, and Vijay K Sikha have collaborated together on this post, [Security features of Bottlerocket, an open source Linux-based operating system](https://aws-oss.beachgeek.co.uk/yx) where they explore several of the security features available in Bottlerocket and how they protect your environment. [deep dive]

**Apache TinkerPop**

Apache TinkerPop is an open source computing framework for graph databases and graph analytic systems. Designed to appeal to software developers, TinkerPop lets developers add graph computing capabilities to their applications without worrying about developing APIs, graph processing engines, or graph algorithms. In this post, [Why developers like Apache TinkerPop, an open source framework for graph computing](https://aws-oss.beachgeek.co.uk/z0) Brad Bebee, Kelvin Lawrence, and Stephen Mallette provide an introduction to the Apache TinkerPop open source project and explain how it helps developers create and explore directed property graphs.

![graph](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/09/21/lakelvin_tinkerpop_f3_sm.png)

**Prometheus**

Last week AWS announced the general availability (GA) of Amazon Managed Service for Prometheus, a fully managed Prometheus-compatible service. To celebreate, we saw a number of posts covering this open source project.

First up we had [Amazon Managed Service for Prometheus is now Generally Available](https://aws-oss.beachgeek.co.uk/ys) Imaya Kumar Jagannathan, Marc Chene, and Vikram Venkataraman walk you through everything new since the announcement at re:Invent and walk you through how to get started. [hands on] My colleague Channy Yun also wrote about this launch in [Amazon Managed Service for Prometheus Is Now Generally Available with Alert Manager and Ruler](https://aws-oss.beachgeek.co.uk/yv) and covers how we contributed the high-availability alert manager to the open source Cortex project, a project providing horizontally scalable, highly available, multi-tenant, long-term store for Prometheus.

If you like to receive alerts in Slack, then the next post, [How to integrate Amazon Managed Service for Prometheus with Slack](https://aws-oss.beachgeek.co.uk/yt) is perfect for you. Arun Chandapillai and Abhi Khanna walk you through a solution on how to set up the Alert manager in Amazon Managed Service for Prometheus to publish alerts to a Slack channel via Amazon Simple Notification Service (SNS) and AWS Lambda. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2021/09/30/11-2.jpg)

If you prefer to receive your alerts in PagerDuty, that is cool too and Mike George and Abhi Khanna have you covered in the post, [Using Amazon Managed Service for Prometheus Alert Manager to receive alerts with PagerDuty](https://aws-oss.beachgeek.co.uk/yu) [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2021/09/27/Figure1-1-1024x520.png)

The last post is [Using Prometheus Adapter to autoscale applications running on Amazon EKS](https://aws-oss.beachgeek.co.uk/yw) from Vikram Venkataraman and it is a good one. He walks you through how to utilise Prometheus Adapter to autoscale Amazon EKS Pods running an Amazon App Mesh workload. AWS App Mesh is a service mesh that makes it easy to monitor and control services. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2021/09/28/custom-metric-blog.png)

**Open Telemetry**

Last week saw the announcement from Alolita Sharma and Nizar Tyrewalla thatAWS Distro for OpenTelemetry (ADOT) is now generally available with production-ready tracing support, in the post [AWS Distro for OpenTelemetry is now GA for tracing](https://aws-oss.beachgeek.co.uk/yy).

Following that we had AWS interns, software engineers Huy Vo and Iris Song, share their experience with adding StatefulSet support in the OpenTelemetry Operator in the post [Adding StatefulSet support in the OpenTelemetry Operator](https://aws-oss.beachgeek.co.uk/yz). They talk about how they added StatefulSet support to the OpenTelemetry Operator, and describe our design choices and lessons learned.

![design](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/09/02/vo-song_stateful-support-opentelemetry-operator_f3.png)

One final thing to share, is the always excellent, weekly roundup of Observability news from Michael Hausenblas. [This was last weeks newsletter](https://aws-oss.beachgeek.co.uk/yi), and I urge you to sign up as they always contain excellent material. 

**OpenSearch**

A few weeks back I shared news about new clients for OpenSearch. Kyle Davis has now put together a nice blog post, [OpenSearch clients in Python, Go, and Node.js](https://aws-oss.beachgeek.co.uk/ym) which shows you how to get up and running with these. [hands on]

**Terraform**

If you use Terraform as your preferred infrastructure as code (IaC) tool, then check out this post, [How to Deploy AWS Config Conformance Packs Using Terraform](https://aws-oss.beachgeek.co.uk/yr) from Jegan Sundarapandian and Chloe Goldstein. They walk you through creating a Terraform template file that you can use to deploy and configure an AWS service (AWS Config) to help you with checking for conformance/compliance against Amazon S3 bucket best practices. [hands on]

### Quick updates

**Apache Kafka**

Amazon Managed Streaming for Apache Kafka (Amazon MSK) now supports Apache Kafka version 2.8.1 for new and existing clusters. [Apache Kafka 2.8.1 includes several bug fixes](https://aws-oss.beachgeek.co.uk/yj).

### Events for your diary

Coming up later this week we have...

**GraphQL API security best practices with AWS AppSync and AWS Amplify**
**14th October, 11am AEST**

As a developer, the most important parts of managing your applications should always include enhancing performance while strengthening security. In this webinar, we take you through security best practices for your GraphQL API’s with AWS AppSync and AWS Amplify, providing you with an understanding of how these can be applied to your applications. In this session, you will learn about:

* GraphQL Protocol and how to configure a schema
* Possible ways to authenticate and authorise access to GraphQL APIs
* How to configure network security for your API
* How to enable observability for your API with logging, tracing or auditing

To [register for this event, use this link](https://aws-oss.beachgeek.co.uk/ue).


**Amazon SageMaker and Open-Source Tools for ML: Better Together**
**October 7 | 11 AM PT | 2 PM ET**

Many organisations rely on open-source tools to support the Machine Learning lifecycle. Amazon SageMaker has been rapidly evolving by introducing support and compatibility for various open-source frameworks. In this session, you will learn how to build a customisable ML Infrastructure based on Amazon SageMaker and open-source components. We will discuss pros and cons, the limitations of different tools that support specific stages of the ML workflow, and best practices for MLOps, to automate these stages into repeatable pipelines.

To read more and [register for this event, click here](https://aws-oss.beachgeek.co.uk/wz).


**Flink Forwards Global 2021**
**October 26th/27th**

Flink Forward Global 2021 is a 2-day virtual conference for the Apache Flink and stream processing communities. Apache Flink is an open-source distributed engine for processing data streams that can support both streaming and batch workloads. Flink Forward has keynote presentations and talks on production Flink use cases, technical deep dive sessions, and the growth of the Flink ecosystem. You can meet core Flink committers, new and experienced users, and thought leaders who share experiences and best practices in stream processing, real-time analytics, and the management of mission-critical Flink deployments in production.

[Read more and sign up here.](https://aws-oss.beachgeek.co.uk/wh)

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)