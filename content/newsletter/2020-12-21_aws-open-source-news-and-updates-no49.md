---
title: 'AWS open source news and updates No.49'
date: '2020-12-21'
tags : [ oss-newsletter ]
---
## December 21st - Instalment #49

Week No.49 and this will be the last newsletter this year. It is good to go out on a high, and this week we have a round up of the third week of re:Invent, following Dr Werner Vogels's keynote and announcements. There are plenty of great posts related to those launches as well as re:Invent sessions to find out more. We also have the usual round up of blog posts, case studies, videos and open source projects which you can think of as stocking fillers as we head into Christmas.

To finish 2020 I just want to wish you all the very best. I look forward to coming back in January 2021 and wish you all the very best for the holidays.

### Please complete my feedback survey

One final ask given this is the last newsletter for 2020. Please complete my feedback survey. At AWS we take customer feedback very seriously and use it to raise the bar and improve the customer experience. 

### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you and a very happy holiday to the following superstars: Jyothi Venkatesh, Gokul Chandra, Ali Spittel, Valentin Viennot, Guilherme França, Bruno Emer, Elamaran Shanmugam, Kyle Lee, Trivikram Kamat, Viraj Phanse, Edward Brown, Eduardo Piairo, Marcia Oliveira, Jack Hampson, Verdi March, Beibit Baktygaliyev, Zmnako Awrahman, Othmane Hamzaoui, Fatema Alkhanaizi, Viktor Malesevic, Andrew Cathrow, Joseph Morais, Jonah Kowall, James Gosling and Konstantin Dotchkoff, Angus McAllister, Matthew Liem, Joseph Marques,  Madelyn Olson, Yoav Eilat, Jon Handler, Carl Meadows, Steve Johnson, Brice Pelle, Nader Dabit, Lucio Di Jasio, James Beswick, Imaya Kumar Jagannathan, Michael Hausenblas, Baichuan Sun, Calvin Wang, Eden Duthie, Kavitha Rajendran, Jérôme Decq, Richard Anton, Tom Wilkie, Jason Swartz, Ian Mckay,  Wilbert Guo and Kelvin Lo

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

**ecsview**

[ecsview](https://github.com/swartzrock/ecsview) this open source tool from Jason Swartz is a terminal-based UI for browsing Amazon Elastic Container Service (ECS) clusters. You can use it to view cluster usage, services, tasks, and individual container instances (ec2's). Uses the excellent tview library to build and manage the UI.

**vscode-aws-cloudshell**

[vscode-aws-cloudshell](https://github.com/iann0036/vscode-aws-cloudshell) this is an another awesome open source project from AWS Hero Ian Mckay, providing (an unofficial) AWS CloudShell plugin for VS Code that allows you to open multiple AWS CloudShell terminals within VS Code on demand. Very much an Alpha release so if you like it make sure you feedback your experience and any issues you find (as well as fixes of course!)

![arch](https://raw.githubusercontent.com/iann0036/vscode-aws-cloudshell/master/resources/screenshot.png)

**aws-greengrass**

[aws-greengrass](https://github.com/aws-greengrass) this contains the open source projects from AWS Greengrass v2 - I have linked to more details below, so this is just the open source GitHub repos for you to check out.


### AWS open source posts

**Blender**

[AWS joins Blender Development fund](https://aws.amazon.com/blogs/media/aws-joins-blender-development-fund/) important news from Kyle Roche last week as AWS announced that it has joined the Blender Development Fund as a Patron Member to support continued development and innovation for Blender. The Blender Foundation has been an industry leader in providing production-grade open source software solutions, so check out the post to find out more about this announcement and the projects.

![blender](https://d2908q01vomqb2.cloudfront.net/fb644351560d8296fe6da332236b1f8d61b2828a/2020/12/17/1669.png)

**Open Distro for Elasticsearch**

[Open Distro for Elasticsearch 1.12.0 is now available](https://opendistro.github.io/for-elasticsearch/blog/releases/2020/12/opendistro-1-12-0-released/) Viraj Phanse shares news of the latest update to Open Distro for Elasticsearch, 1.12.0. New features in this release include Kibana reports, Gantt chart visualisations, rollups in index management, and support for Hamming distance in k-NN. It includes version 7.10 of open source Elasticsearch and Kibana, plus Apache 2.0-licensed plugins that provide alerting, anomaly detection, index management, performance analysis, security, SQL, k-NN, and more. Other components, including ODBC and JDBC drivers, a command line SQL client, and a command line performance visualisation tool (“PerfTop”) are also available to download. Read the post to read more about the release highlights of 1.12.0.

**Open Distro for OpenTelemtry**

[Go support for AWS X-Ray now available in AWS Distro for OpenTelemetry](https://aws.amazon.com/blogs/opensource/go-support-for-aws-x-ray-now-available-in-aws-distro-for-opentelemetry/) AWS interns Wilbert Guo and Kelvin Lo share their experience in enhancing the OpenTelemetry Go SDK to support sending traces to AWS X-Ray. These enhancements are also available in the AWS Distro for OpenTelemetry.

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2020/12/14/alolitas_go-support_f3.jpg)

**Apache Kafka**

[Using self-hosted Apache Kafka as an event source for AWS Lambda](https://aws.amazon.com/blogs/compute/using-self-hosted-apache-kafka-as-an-event-source-for-aws-lambda/) in this post James Beswick shows you how to set up an Apache Kafka cluster on Amazon EC2 and configure it so that you can use a Lambda function to consume messages from a Kafka topic. Apache Kafka is an open source event streaming platform used to support workloads such as data pipelines and streaming analytics. With the launch last week of Kafka as an event source for AWS Lambda, you can now consume messages from a topic in a Lambda function making it easier to integrate your Kafka clusters with downstream serverless workflows. James walks you through the details as well as how to do this based on whether you are rolling your own Apache Kafka cluster or using Amazon Managed Streaming for Apache Kafka (Amazon MSK).

**fast.ai, PyTorch & TorchServe**

In [Deploy fast.ai-trained PyTorch model in TorchServe and host in Amazon SageMaker inference endpoint](https://aws.amazon.com/blogs/opensource/deploy-fast-ai-trained-pytorch-model-in-torchserve-and-host-in-amazon-sagemaker-inference-endpoint/), Baichuan Sun, Calvin Wang, Eden Duthie, and Kavitha Rajendran collaborate to show you how to deploy a fast.ai-trained PyTorch model in TorchServe. Over the past few years, fast.ai has become one of the most cutting-edge, open source, deep learning frameworks and the go-to choice for many machine learning use cases based on PyTorch. In partnership with Facebook, AWS developed TorchServe, a flexible and easy-to-use, open source tool for serving PyTorch models. TorchServe removes the heavy lifting of deploying and serving PyTorch models with Kubernetes. This post provides an easy to follow walkthrough and you can use this repository as a template to deploy your own fast.ai models.

**Cortex**

Jérôme Decq and Richard Anton from AWS together with Tom Wilkie, VP of Product at Grafana Labs came together to write [How AWS and Grafana Labs are scaling Cortex for the cloud](https://aws.amazon.com/blogs/opensource/how-aws-and-grafana-labs-are-scaling-cortex-for-the-cloud/). Cortex is a horizontally scalable, highly available, multi-tenant, long term storage for Prometheus, and this post takes a look at some of the work AWS undertook with Grafana Labs on the path from design to implementation.

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2020/12/17/ranton-grafana-cortex_F1.png)

**AWS SAM**

[Using container image support for AWS Lambda with AWS SAM](https://aws.amazon.com/blogs/compute/using-container-image-support-for-aws-lambda-with-aws-sam/) Eric Johnson covers a lot in this post, starting off with a walk through building a simple serverless application that uses Lambda functions packaged as container images with AWS SAM. Eric follows that by demonstrating how you can create a new application and highlight changes to the AWS SAM template specific to container image support. Next you will get to know how to build the image locally for debugging in addition to eventual deployment and wrapping up, Eric shows you how AWS SAM handles packaging and deploying Lambda functions from a developer’s machine or a CI/CD pipeline. Great post, definitely check this one out.

**AWS SDKs**

[Modular AWS SDK for JavaScript is now generally available](https://aws.amazon.com/blogs/developer/modular-aws-sdk-for-javascript-is-now-generally-available/) Trivikram Kamat writes about the general availability of v3 if the AWS SDK for Javascript.  I have mentioned in previous newsletters some of the components included in this SDK, but this post brings everything together. So read the post to find out more about the modular package architecture, the middleware stack, first class TrueType support and more.

**AWS Amplify**

[Rapid iOS App Prototyping with Amplify Admin UI and SwiftUI](https://aws.amazon.com/blogs/mobile/rapid-ios-app-prototyping-with-amplify-admin-ui-and-swiftui/) Kyle Lee has a nice walkthrough using a new capability launched a few weeks ago, the Admin UI, to prototype a room booking app that allows a user to sign in, view seeded available rooms, book one of those rooms, and see the bookings associated with that user. This new Admin UI feature provides an easy-to-use interface where you can layout the models of your app, create relationships between them, and pull the Swift representation of those models into your codebase. Everything you need is in this post, so have fun!

**Envoy**

AWS App Mesh is a service mesh that provides application-level networking to make it easy for your services to communicate with each other across multiple types of compute infrastructure and uses the open source Envoy proxy. We have a couple of related posts this week.

First up is, [Sending Envoy metrics from AWS App Mesh to Amazon CloudWatch](https://aws.amazon.com/blogs/containers/sending-envoy-metrics-from-aws-app-mesh-to-amazon-cloudwatch/) where Elamaran Shanmugam provides a detailed walk through to help you understand the mechanisms used to send collected metrics to CloudWatch using an Envoy sidecar with App Mesh for container workloads. This might be useful as you look to improve your application’s monitoring and alerting of container workloads.

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2020/12/14/App-Mesh-Metrics-Architecture.png)

Following that we have [Leveraging App Mesh with Amazon EKS in a Multi-Account environment](https://aws.amazon.com/blogs/containers/leveraging-app-mesh-with-amazon-eks-in-a-multi-account-environment/) from Guilherme França and Bruno Emer show you how you can leverage AWS App Mesh capabilities to integrate different components of an application running across different EKS clusters in different AWS accounts. They use an open source application from Massimo Re Ferrè [Yelb](https://github.com/mreferre/yelb) which uses Redis and Postgres to make this easier to follow. 

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2020/12/10/Multi-Account-App-Mesh-and-Amazon-EKS-1024x570.png)

**AWS ParallelCluster**

[Remote visualization in HPC using NICE DCV with ParallelCluster](https://aws.amazon.com/blogs/opensource/remote-visualization-in-hpc-using-nice-dcv-with-parallelcluster/) in this post, Jyothi Venkatesh walks you through some example use cases combining High Performance Compute (HPC) workloads and remote visualisations. AWS ParallelCluster is an open source cluster management tool that makes deploying and managing HPC clusters on AWS easy. Combining that with the power of remote graphical workstations, this post provides insights across different industry use cases as to how you can apply this for your own needs.

![hpc](https://awsopensourceblog.s3.us-east-2.amazonaws.com/assets/venkatesh-nice-dcv-parallelcluster/jyothibv_F3_CFDBlogFinal.gif)


### Videos of the week

**Containers anywhere**

Rapidly becoming a regular fixture of this newsletter, the folks from Containers from the Couch have done it again. A stellar line up bring you a great session on running containers anywhere. Be prepared for a great demo that Justin shared a peek of last week before the episode went live via [Twitter](https://twitter.com/rothgar/status/1338954329705725952?s=11).

{% youtube VkkkJddXWO8 %}

Also, do you agree with their definition of "on premises" ?

**Amazon Managed Workflows for Apache Airflow**

Take a look at Derek Bingham talk with John Jackson about the Amazon Managed Workflows for Apache Airflow services that launched during pre:Invent.

{% twitch https://www.twitch.tv/videos/832962938?t=0h1m40s %}

### re:Invent

**Keynote**

There were a number of interesting open source related launches and updates during the Tuesday keynote from Dr Werner Wogels. He announced the preview of Amazon Managed Service for Grafana and Amazon Managed Service for Prometheus (both in preview), as well as announcing the general availability of the Open Distro for OpenTelemetry. 

Marcia Villalba’s blog post, [Announcing Amazon Managed Service for Grafana (in Preview)] (https://aws.amazon.com/blogs/aws/announcing-amazon-managed-grafana-service-in-preview/), announced the preview and how we are working in partnership with Grafana Labs on this new service. Why Grafana? Well, [Grafana] (https://grafana.com/) is one of the most popular open source technologies used to create observability dashboards for your applications. It has a pluggable data source model and support for different kinds of time series databases and cloud monitoring vendors. Read the post to find out more about how this will work and on details of how to sign up.

It was good to see Grafana Labs also write about this service launch, and talk about the new partnership in their post, [Our new partnership with AWS gives Grafana users more options.] (https://grafana.com/blog/2020/12/15/announcing-amazon-managed-service-for-grafana/)How are AWS collaborating with Grafana Labs was a question that Matt Asay looked at in hist post, [How AWS and Grafana Labs are collaborating to improve Grafana for all] (https://aws.amazon.com/blogs/opensource/how-aws-and-grafana-labs-are-collaborating-to-improve-grafana-for-all/)that shared how we are working closely with Grafana Labs, both in licensing revenue but also with code contributions to help make Grafana even better for all users wherever they choose to run Grafana. 

Imaya Kumar Jagannathan and Michael Hausenblas put together a great post on how you can get started in, [Amazon Managed Grafana – Getting Started](https://aws.amazon.com/blogs/mt/amazon-managed-grafana-getting-started/). This post will guide you in setting up your first Grafana workspace, integrate data sources and then walk you through some of the available dashboards.

![dashboards](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2020/12/09/image019-1024x651.jpg)

On the Prometheus side, we had Jeff Barr write about the launching a preview of Amazon Managed Service for Prometheus (AMP). In his post, [Join the Preview – Amazon Managed Service for Prometheus (AMP), ](https://aws.amazon.com/blogs/aws/join-the-preview-amazon-managed-service-for-prometheus-amp/) Jeff provides details on Amazon Managed Service for Prometheus (AMP), a fully-managed service is 100% compatible with Prometheus. If you are new to Prometheus, it is a leading open-source monitoring solution with an active developer and user community. If you are already using Promethues, it supports the same metrics, the same [PromQL] (https://prometheus.io/docs/prometheus/latest/querying/basics/) queries, and can also make use of the 150+ [Prometheus exporters] (https://prometheus.io/docs/instrumenting/exporters/). The preview has support for Amazon Elastic Kubernetes Service (EKS) and Amazon Elastic Container Service (ECS) but it can also be used to monitor your self-managed Kubernetes clusters that are running in the cloud or on-premises.

Sticking with Prometheus, Marc Chene and Jaana Dogan’s post, Introducing [Amazon Managed Service for Prometheus (AMP)] (https://virtual.awsevents.com/media/1_tau1fqqc)showed you how you can use the same open-source Prometheus data model, existing instrumentation, and query language to monitor performance with improved scalability, availability, and security without having to manage the underlying infrastructure.

Alolita Sharma and Nizar Tyrewalla shared in their blog post, [AWS Distro for OpenTelemetry adds Prometheus and Lambda support and other cool features, ](https://aws.amazon.com/blogs/opensource/aws-distro-for-opentelemetry-adds-prometheus-and-lambda-support-and-other-cool-features/) news that Open Distro for OpenTelemetry now brings support for Prometheus and AWS Lambda and adds AWS X-Ray support in Go and Python, as well as adding an OpenTelemetry Protocol (OTLP) HTTP exporter, an AWS EMF exporter, and an X-Ray exporter. Read the most for more details of this. 

Aman Brar and Jason Liu also wrote up [Building a reliable metrics pipeline with the OpenTelemetry Collector for AWS Managed Service for Prometheus] (https://aws.amazon.com/blogs/opensource/building-a-reliable-metrics-pipeline-with-the-opentelemetry-collector-for-aws-managed-service-for-prometheus) where they shared their experience working with the OpenTelemetry Collector and Prometheus Remote Write Exporter. Read this post to find out more about their experiences in tackling challenges they faced and how they applied lessons learned to ensure the reliability of the AWS Distro for the OpenTelemetry Collector as the de facto agent for sending metrics to AWS Managed Service for Prometheus.

**Other open source announcements**

Whilst not part of the keynote, there were also some really important announcements during week three. In Announcing AWS IoT Greengrass 2.0 – With an Open Source Edge Runtime and New Developer Capabilities (https://aws.amazon.com/blogs/aws/announcing-aws-iot-greengrass-2-0-with-an-open-source-edge-runtime-and-new-developer-capabilities/)Channy Yun announced the release of AWS IoT Greengrass 2.0. AWS IoT Greengrass that makes it easy for device builders to build, deploy, and manage intelligent device software. One of the big updates was the fact that this now provides an open source edge runtime. AWS IoT Greengrass (https://aws.amazon.com/greengrass) 2.0 edge runtime has been open sourced under an Apache 2.0 license, and available on Github (https://github.com/aws-greengrass). Access to the source code allows you to more easily integrate your applications, troubleshoot problems, and build more reliable and performant applications that use AWS IoT Greengrass. Make sure you check out the session from James Gosling and Konstantin Dotchkoff  that walked you through this in more detail (see below.

On a related note, Channy also shared news of FreeRTOS (https://freertos.org/) Long Term Support (LTS) in his post New – FreeRTOS Long Term Support to Provide Years of Feature Stability. (https://aws.amazon.com/blogs/aws/new-freertos-long-term-support-to-provide-years-of-feature-stability/) FreeRTOS is an open source, real-time operating system for microcontrollers that makes small, low-power edge devices easy to program, deploy, secure, connect, and manage. Read the post for more details.

AWS IoT Core is a managed cloud service that lets connected devices easily and securely interact with cloud applications and other devices. AWS IoT Core can support billions of devices and trillions of messages, and can process and route those messages to AWS endpoints. Last week we announced that you could now deliver those messages to Apache Kafka clusters, whether these are your own self managed Apache Kafka clusters or Amazon Managed Streaming for Apache Kafka (https://aws.amazon.com/msk/) (“Amazon MSK”).

Finally, bringing this back to observability, last week we also announced that AWS IoT SiteWise can integrate with Grafana (https://aws.amazon.com/about-aws/whats-new/2020/12/introducing-aws-iot-sitewise-plugin-for-grafana/) via a new plugin. This plugin lets you easily visualize your AWS IoT SiteWise data in your Grafana dashboards. With this plugin, you can easily visualize and monitor your equipment data in near-real time using the wide range of visualization options in Grafana dashboards. If you are not familiar with what AWS IoT SiteWise is, it is a managed service that makes it easy to collect, store, organize, and monitor data from industrial equipment at scale.

**Open source related sessions**

There were some great AWS Amplify and GraphQL/AWS AppSync related sessions during the third week.

[Model and access application data more efficiently with AWS Amplify] (https://virtual.awsevents.com/media/1_128yktbk) this session from Steve Johnson he shares how developers can leverage the power of GraphQL to model app data for faster production apps, that can scale across platforms and use the offline capabilities using Amplify DataStore. In this session, [Best practices to securely operate GraphQL at scale with AWS AppSync] (https://virtual.awsevents.com/media/1_gk92ddbw), Brice Pelle shared how AWS AppSync enables you to securely build and run GraphQL APIs at scale, covering  the options available to you and how you can leverage AWS security services. Nader Dabit looked at some of the capabilities that AWS AppSync GraphQL resolvers help you with in,  [Unify access to siloed data with AWS AppSync GraphQL resolvers.] (https://virtual.awsevents.com/media/1_ov2gbvu6) Nader shows you how to simplify how you query your data across different sources.

If you use Elasticsearch then there were a few sessions during week three for you to check out.  In the session, [What’s new in Amazon Elasticsearch Service](https://virtual.awsevents.com/media/1_b5wgsvzk), Jon Handler  did a deep dive into the service, customer use cases, best practices, and newly launched features, as well as sharing what’s next for Amazon Elasticsearch Service. In the session, [Security overview for Amazon Elasticsearch Service] (https://virtual.awsevents.com/media/1_4o865cc5) Carl Meadows dived deep and shared the rich set of security options that allow you to control access to your cluster and data as well as how to configure it for even your most sensitive data. This session covered so many topics, such as how to configure encryption, authorization using IAM and enterprise identity providers using SAML, set up of fine-grained access control for your indices, documents, and fields and much more.

Following on from her session in week one, Madelyn Olson returned this time with a talk, [Beyond caching: Advanced design patterns in Redis] (https://virtual.awsevents.com/media/1_l8i5ptlx), that explored the use cases, examples, and demos of how you can take advantage of Redis to solve distributed system problems like managing state, processing events, and transforming data in real time. If MySQL is more your thing, then check out this session from Yoav Eilat on [MySQL options on AWS: Self-managed, managed, serverless] (https://virtual.awsevents.com/media/1_ktmoo958). Great session where he covered an overview of the MySQL and MariaDB options available on AWS. This included a deep dive on Amazon RDS, the fully managed MySQL service; Amazon Aurora, a MySQL-compatible database with up to five times the performance; and other additional innovations.

[Run big data analytics faster at lower cost with Amazon EMR ](https://virtual.awsevents.com/media/1_9q41741u) Matthew Liem explored looked at some of the features of Amazon EMR and how these can help you run your Apache Spark, Apache Hive, Apache Flink, and Presto workloads both faster or more cost-effectively. He also took a look into the architectures and design patterns that organizations have employed when migrating their open-source analytics applications to Amazon EMR. Sticking with the same theme, Joseph Marques shared with you an in depth look at some of the performance improvements in Amazon EMR for Apache Spark and Presto in the session [Turbocharging query execution on Amazon EMR] (https://virtual.awsevents.com/media/1_17w4ps5f)

Next up was the session from Angus McAllister, where he introduced a new open source project, FHIR Works on AWS, that is helping accelerate the use of Fast Healthcare Interoperability Resources (FHIR) in customer solutions. FHIR is gaining popularity around the world as the standard to use for exchanging healthcare data, and it is being increasingly adopted in Europe and Australasia. In the US, it is actually mandated in the 21st Century Cures Act HHS final rule. This is both a challenge and an opportunity for those who manage healthcare data in EHRs and other systems. This session introduces the FHIR standard and FHIR Works on AWS. Check out the session, [An introduction to healthcare interoperability and FHIR Works on AWS] (https://virtual.awsevents.com/media/1_5a22g9eo)

There were many great AWS Cloud Development Kit (AWS CDK) sessions, too many for me to list, but Ryan Hayes session, [Turbocharge the AWS CDK with AWS Solutions Constructs](https://virtual.awsevents.com/media/Turbocharge+the+AWS+CDK+with+AWS+Solutions+Constructs/1_slk44vwk) really hit the mark for me. It is a level 400 session and to get the best out of it, you do need to know and have used AWS CDK before. A great demo, a look at now/next as well as summary of how AWS Solutions Constructs can accelerate your time to value make this a must see session.

Finally, in [What’s new with AWS IoT Greengrass] (https://virtual.awsevents.com/media/1_szkype68) James Gosling and Konstantin Dotchkoff did a session on AWS IoT Greengrass 2.0. For those unfamiliar with what AWS IoT Greengrass does, it seamlessly extends AWS to edge devices so that they can act locally on the data that they generate, while still using the cloud for management, analytics, and durable storage. They covered the new features with this major release, with AWS IoT Greengrass now providing customers an open source edge runtime, a rich set of pre-built software components, tools for local software development, and new features for managing device software on large fleets of devices.

**AWS Partner sessions**

There were some excellent partner sessions during week three as well, and here is such the ones that we checked out.

[What do 1,000 people say about open-source observability? ](https://virtual.awsevents.com/media/1_xmlhp2or) Jonah Kowall, CTO at [Logz.io] (http://logz.io/) shared with us the exciting tools communities are using to solve for observability needs and which best practices work when implementing and scaling open-source observability.

[Confluent Cloud metamorphosis: Making Apache Kafka easier] (https://virtual.awsevents.com/media/1_4n6oglvc)  Joseph Morais from Confluent, gave an overview of how the Confluent Cloud serverless Kafka offering makes it even easier, more secure, and cost-effective to build event-driven applications on AWS. Joseph then went on to dive deep into some of the capabilities, including features such as infinite storage, self-provisioned AWS PrivateLink endpoints, bringing your own encryption keys and more.

[Build cloud-ready apps faster with Red Hat OpenShift Service on AWS] (https://virtual.awsevents.com/media/1_a4haydgv) Andrew Cathrow took a look at the recently announced a fully managed joint service, Red Hat OpenShift Service on AWS, that can be deployed directly from the AWS Management Console and can integrate with other AWS Cloud-native services. Andrew looked at the new service, which delivers production-ready Kubernetes that many enterprises use on premises today, enhancing your ability to shift workloads to the AWS Cloud and making it easier to adopt containers and deploy applications faster.

### Quick updates

**Apache Kafka**

AWS IoT Core is a managed cloud service that lets connected devices easily and securely interact with cloud applications and other devices. AWS IoT Core can support billions of devices and trillions of messages, and can process and route those messages to AWS endpoints. Last week we announced that you could now deliver those messages to Apache Kafka clusters, whether these are your own self managed Apache Kafka clusters or Amazon Managed Streaming for Apache Kafka (https://aws.amazon.com/msk/) (“Amazon MSK”).

**FreeRTOS**

Channy Yun shared news of FreeRTOS (https://freertos.org/) Long Term Support (LTS) in his post [New – FreeRTOS Long Term Support to Provide Years of Feature Stability.](https://aws.amazon.com/blogs/aws/new-freertos-long-term-support-to-provide-years-of-feature-stability/) FreeRTOS is an open source, real-time operating system for micro controllers that makes small, low-power edge devices easy to program, deploy, secure, connect, and manage. Read the post for more details.

Another new announcement last week was news that FreeRTOS now includes a preview of a cellular LTE-M library and AWS IoT reference integrations with cellular modules from vendors such as Sierra Wireless, u-blox, and Quectel. With this launch, customers will find it easier to build IoT devices that use the cellular LTE-M protocol to connect to AWS IoT Core. In the post, [Introducing the FreeRTOS Cellular Library](https://freertos.org/2020/12/introducing-the-freertos-cellular-library.html) Lucio Di Jasio provides more details on this, covering the stack and talking about how to develop and test cellular applications.

**Grafana**

Another announcement last week was that [AWS IoT SiteWise can now integrate with Grafana](https://aws.amazon.com/about-aws/whats-new/2020/12/introducing-aws-iot-sitewise-plugin-for-grafana/) via a new plugin. This plugin lets you easily visualise your AWS IoT SiteWise data in your Grafana dashboards. With this plugin, you can easily visualise and monitor your equipment data in near-real time using the wide range of visualisation options in Grafana dashboards. If you are not familiar with what AWS IoT SiteWise is, it is a managed service that makes it easy to collect, store, organise, and monitor data from industrial equipment at scale.

**Apache Parque**

AWS IoT Analytics is a fully managed service that makes it easy to collect, pre-process, enrich, store and analyze IoT data at scale to run sophisticated analytics on massive volumes of IoT data and gain insights into how IoT devices are operating without having to worry about the complexity typically required to build an analytics platform. AWS IoT Analytics now supports the Apache Parquet format, an efficient open columnar storage format to store processed data in AWS IoT Analytics data stores. Apache Parquet consumes less storage and is faster for querying large volumes of data compared to text formats such as JSON which was previously the only storage format supported for storing processed data in AWS IoT Analytics. The Apache Parquet storage format is best suited when large volumes of processed data need to be stored and queried in AWS IoT Analytics and the schema of the processed data is fixed. On the other hand, the JSON storage format is best suited to store and query smaller volumes of data in AWS IoT Analytics when the schema of the processed data is expected to evolve.

### Case studies

**Apache TinkerPop**

[Building a knowledge graph with topic networks in Amazon Neptune](https://aws.amazon.com/blogs/database/building-a-knowledge-graph-with-topic-networks-in-amazon-neptune/) this guest post from AWS Partner Deeper Insights, featuring Edward Brown, Head of AI Projects, Eduardo Piairo, Architect, Marcia Oliveira, Lead Data Scientist, and Jack Hampson, CEO. In this post they share how they used the graph database service Amazon Neptune to build a robust, scalable graph database infrastructure to extract knowledge from a large textual dataset, in this case study medical papers describing research on COVID-19, to create the Covid Insights Platform. Managed open source services are often a great way for customers to get immediate utility from the open source project without having to go through the learning curve of how to set it up, configure and run it, and that was certainly the case here. Finally, I loved this quote from this post worth sharing, from Dr Matt Morgan, Critical Care Research Lead for Wales said “The Covid Insights platform has the potential to change the way that research is discovered, assessed and accessed for the benefits of science and medicine.”

![arch](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2020/11/21/Building-a-knowledge-graph-4.jpg)

**Novartis**

Last week we shared a four part post covering some of the work being done with Novartis featuring open source technologies that cover analytics and machine learning. Novartis, headquartered in Basel, Switzerland, is reimagining medicine to improve and extend people’s lives, and leveraging digital technologies is one of Novartis’ key tenets as they transform treatments and produce products that reach 800 million people globally. This series of posts took a look at one part of that collaboration, the work on their Buying Engine platform.

To start with we have Othmane Hamzaoui, Fatema Alkhanaizi, and Viktor Malesevic with [Novartis AG uses Amazon SageMaker and Amazon Neptune to build and enrich a knowledge graph using BERT](https://aws.amazon.com/blogs/industries/novartis-ag-uses-amazon-to-build-knowledge-graph-using-bert/) that focused on the Knowledge Base of the Buying Engine, which provides business analysts with a complete view on catalog data, along with insights. The post goes on to share how they were able to use TensorFlow 2 and open source models such as BERT to build a custom Named Entity Recognition model, and share how these predictions were used to build a knowledge graph to query, analyse and extract insights about the products on Neptune.

Following that Othmane Hamzaoui focuses on the search and recommendation components of the Buying Engine, specifically on the usage of Amazon Elasticsearch Service and its k-nearest neighbours (KNN) functionality. Novartis were able to build a scalable search and recommendation engine powered by machine learning, and you can read more in [Novartis AG uses Amazon Elasticsearch K-Nearest Neighbor (KNN) and Amazon SageMaker to power search and recommendation](https://aws.amazon.com/blogs/industries/novartis-ag-uses-amazon-elasticsearch-k-nearest-neighbor-knn-and-amazon-sagemaker-to-power-search-and-recommendation/)

![arch](https://d2908q01vomqb2.cloudfront.net/c5b76da3e608d34edb07244cd9b875ee86906328/2020/10/30/Automated-ingestion-pipeline.png)

Finally in [Demand Forecasting using Amazon SageMaker and GluonTS at Novartis AG ](https://aws.amazon.com/blogs/industries/novartis-ag-uses-amazon-sagemaker-and-gluonts-for-demand-forecasting/) Verdi March, Beibit Baktygaliyev, and Zmnako Awrahman  take a look at how they are using the open source [GluonTS](https://ts.gluon.ai/) library. Gluon Time Series (GluonTS) is the Gluon toolkit for probabilistic time series modelling which allows you to train and evaluate on any of the built-in models on your own data to come up with a solution for your time series tasks and provides a set of abstractions and building blocks that allow you to create custom time series models. This post focuses on the demand forecasting component in the Buying Engine using GluonTS. 

### Other open source blog posts

**Amazon SageMaker Clarify**

[AI modelling tool developed by Oxford academics incorporated into Amazon anti-bias software](https://www.oii.ox.ac.uk/news/releases/ai-modelling-tool-developed-by-oxford-academics-incorporated-into-amazon-anti-bias-software/) Amazon SageMaker Clarify is a new capability within Amazon SageMaker that helps customers detect bias in machine learning (ML) models, and increase transparency by helping explain model behaviour to stakeholders and customers. This post provides some further reading on this topic including links to the research papers. To quote from the post:

>“I’m incredibly excited to see our work being implemented by Amazon Web Services as part of their cloud computing offering.    I’m particularly proud of the way our anti-bias test can be used to detect evidence of intersectional discrimination, which is an area that is often overlooked by developers of AI and machine learning systems.“It’s less than a year since we published our paper, ‘Why Fairness Cannot Be Automated: Bridging the Gap Between EU Non-Discrimination’ and it’s very rewarding to see our work having such impact.”
>

**Firecracker**

[Hardware acceleration in the Age of Functions (vol II)](https://blog.cloudkernels.net/posts/vaccel_v2/) great post from the team at CloudKernels that takes a look at different options available for hardware acceleration options available and how Firecracker in combination with an open source project, [vAccel](https://github.com/cloudkernels/vaccelrt) provides you with perhaps some better options. Make sure you check out their first post too (linked in the blog).

![arch](https://blog.cloudkernels.net/static/vaccel_v2/vaccelrt.png#center)

**AWS Amplify Admin UI**

[Get Started with the AWS Amplify Admin UI](https://egghead.io/playlists/get-started-with-the-amplify-admin-ui-9e79) this is a great collection of tutorials from Ali Spittel that help you get hands on with the recently launched AWS Amplify Admin UI. She will take you through How to create a database schema, testing your data locally, deploying to AWS, adding authentication and. more. 

**Netx.js**

[Next.js CI / CD on AWS with GitHub Actions](https://dev.to/dabit3/next-js-ci-cd-on-aws-with-github-actions-3502) Nader Dabit shows you how to set up CI/CD with Next.js on AWS using GitHub Actions and the Serverless Framework. A short post with accompanying video to help walk you through this. Nice!

{% youtube iEgeuzKEIFs %}

**Amazon EKS Distro**

We had a couple of great posts this week covering the Amazon EKS Distro that we recently launched.

First up we have [Amazon EKS Distro (EKS-D): The Kubernetes Distribution Used by Amazon EKS](https://itnext.io/amazon-eks-distro-eks-d-the-kubernetes-distribution-used-by-amazon-eks-fa23b54025fb) that has been written by Gokul Chandra Software Engineer at Workday and provides a super comprehensive and detailed roundup of what Amazon EKS Distro is but also diving deep into the details including for example, how the distribution uses Prow.

Following that we had a nice post from Valentin Viennot, [Use Amazon ECR Public and EKS-D to deploy LTS Docker Images](https://ubuntu.com/blog/use-amazon-ecr-public-and-eks-d-to-deploy-lts-docker-images) where he shows you how you can quickly install Amazon EKS Distro (or EKS-D) with the EKS Snap, a frictionless way to try all the EKS-D experience on Ubuntu. The post then follows that by showing you the LTS Docker Image Portfolio of secure container images from Canonical that are available on Amazon ECR Public.

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen).

### Your feedback matters!

I have put together a short feedback survey, which I would ask you to take - it will take no more than 2 minutes. You can access [here](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn). Many thanks!

[Take the survey](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn)