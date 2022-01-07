---
title: 'AWS open source news and updates No.50'
date: '2021-01-04'
tags : [ oss-newsletter ]
---
## January 4th, 2021 - Instalment #50

Newsletter #50 and the first one this year. I hope you all had a good break over the festive season. I am busy catching up with all the open source posts, projects, case studies and more, much of which I have shared this week. I have also covered what is happening next week with the concluding week of re:Invent - plenty more open source sessions to check out.

**The AWS Viewpoint on Open Source and Kubernetes**

![pic](https://cdn.thenewstack.io/media/2020/11/6e3629ed-aws--1024x576.png)

If you missed this podcast, [The AWS Viewpoint on Open Source and Kubernetes](http://aws-oss.beachgeek.co.uk/m) a few weeks back it is well worth re-visiting. Bob Wise, AWS’ general manager of Kubernetes, and Peder Ulander, AWS head of product marketing talk about AWS, Kubernetes and more. Well worth adding to your podcast playlist queue. 

{% soundcloud https://soundcloud.com/thenewstackmakers/2-kccnc-cncf-dop-aws-peder-bob-f2 %}

### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following superstars: Shanthan Kesharaju, Cecil Patterson, Sean McGrail, Romain Marcadier, Trivikram Kamat, Jonah Jones, Leo Di Donato,  Asser Moustafa, John Jackson,  Vinay Selvaraj, Jimmy Dahlqvist, Jorel Jean-Charles, Ian Mckay, Kelvin Lo, Abbas Nemr, Calvin Wang, Chris Ghyzel, Veronika Megler and Jerome Van Der Linden.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### re:Invent

If you missed the open source track or sessions during re:Invent during November 30th and December 17th, then check out a few blog posts I put together that summarises the key announcements, new launches and some of the great open source sessions that you can now view via the on-demand capability which should be around until the end of this month. You can start with [re:Invent open source highlights: Week 1](https://aws.amazon.com/blogs/opensource/reinvent-open-source-highlights-week-1/) and from there navigate to weeks two and three.

**January 11th - re:Invent continues**

The final part of re:Invent kicks off on January 11th. Here are the sessions you can look forward to next week. As these are already in the re:Invent catalog so you can add them to your calendar (links provided).

**Jan 12th**

OPN205: [Next-gen networking infrastructure with Rust and Tokio](http://aws-oss.beachgeek.co.uk/1)
OPN401: [Securing Bottlerocket updates with TUF and Rust](http://aws-oss.beachgeek.co.uk/2)

**Jan 13th**

OPN207: [The future of Elasticsearch: Open Distro for Elasticsearch](http://aws-oss.beachgeek.co.uk/3)
OPN306: [Deploying PyTorch models for inference using TorchServe](http://aws-oss.beachgeek.co.uk/4)
OPN307: [Pronto: An IaC suite for managing Cassandra at scale](http://aws-oss.beachgeek.co.uk/5)

**Jan 14th**

OPN308: [Designing better ML systems: Learnings from Netflix](http://aws-oss.beachgeek.co.uk/6)
OPN402: [Rust-vmm: Secure VM-based isolation made simple](http://aws-oss.beachgeek.co.uk/7)

### Latest from open source projects

**gitlab-runners-on-aws**

[gitlab-runners-on-aws](https://github.com/JimmyDqv/gitlab-runners-on-aws) if you missed this over the last few weeks, then catch it now. Jimmy Dahlqvist's open source project that makes it easy to setup and run GitLab CI/CD runners on AWS in an auto scaled way using AWS Lambda. GitLab webhooks are used to start Lambda functions to perform the Job in a Docker container.

![arch](https://github.com/JimmyDqv/gitlab-runners-on-aws/raw/main/images/base_infra.png)

**ec2-spot-converter**

[ec2-spot-converter](https://github.com/jcjorel/ec2-spot-converter) this open source project from Jorel Jean-Charles that is going to be very popular I think. This tool converts existing AWS EC2 instances back and forth between On-Demand and 'persistent' Spot billing models while preserving instance attributes (Launch configuration, Tags..), network attributes (existing Private IP addresses, Elastic IP), storage (Volumes), Elastic Inference accelerators and Elastic GPUs. Detailed and easy to follow documentation with examples, check this project out and as always, Jorel welcomes any PRs you might want to make so feel free to join the project.

**cloud9-sso**

[cloud9-sso](https://github.com/iann0036/cloud9-sso) this new project from Ian Mckay looks very interesting. Still in very early beta stage, it provides a simple way to add AWS Cloud9 environments to AWS SSO. Ian has put together a quick walkthrough for you and I am going to try this one out myself over the coming week or so.

### AWS open source posts

**Apache Airflow**

[Amazon Managed Workflows for Apache Airflow unaffected by Airflow 1.10.12 vulnerability](http://aws-oss.beachgeek.co.uk/g) is a quick post from  John Jackson that takes a look at the recently published CVE ([CVE-2020-17526)](https://lists.apache.org/thread.html/rfd8802d9898263b0dc57e97232e4fa5594e889ac9b7c67d07f522fa6%40%3Cdev.airflow.apache.org%3E) and what it means to customers who are using Amazon Managed Workflows for Apache Airflow. You might miss this, but John also talks about the efforts as part of the effort to help customers migrate  to Apache Airflow 2.0. This will mean that you will be able to run your current Apache Airflow DAGs as and when version 2.0 is available. The post shares how this will work, so if you use Apache Airflow and are thinking about migration, then check it out.

**PyDeequ**

[Testing data quality at scale with PyDeequ](http://aws-oss.beachgeek.co.uk/k) Calvin Wang, Chris Ghyzel, and Veronika Megler introduce PyDeequ, an open-source Python wrapper over Deequ (an open-source tool developed and used at Amazon). This tool helps data scientists test and validate the quality of your data, and is used extensively within Amazon. This post provides an introduction into this tool and then provides a walkthrough on how you can get started.

![arch](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2020/12/22/BDB-1023-1.jpg)

**OpenTelemtry**

In this post, [Enhancing AWS X-Ray support in OpenTelemetry JavaScript SDK](http://aws-oss.beachgeek.co.uk/i) AWS intern Kelvin Lo shares his experience of enhancing the OpenTelemetry JavaScript SDK to support AWS X-Ray. These enhancements are also available in the AWS Distro for OpenTelemetry. This is a detailed post that covers the various components that were needed a look at the integration tests and CI/CD workflows to make it easier for contributors to participate and finally technical documentation. This post is a good summary of some of the things you can expect when working on open source projects and open source communities.  

**Kubernetes**

Falco is an incubating Cloud Native Computing Foundation (CNCF), open source, cloud native runtime security tool. In this post, [How Falco uses Prow on AWS for open source testing](http://aws-oss.beachgeek.co.uk/e) Jonah Jones and Leo Di Donato, share how this open source project is using another open source project, Prow, as part of its CI/CD build system. The key thing here is that Prow is a tool that has been developed by the Kubernetes sig-testing Special Interest Group, to address some specific requirements the project had - I don't want to spoil this, read the post to find out. This is a really great deep dive, so suggest you check this out.

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2020/12/14/jonahjo_Falco-Security_f3.jpg)

**jsii**

[How the jsii open source framework meets developers where they are](http://aws-oss.beachgeek.co.uk/a) great post from Romain Marcadier that you absolutely have to check out. In this post, Romain takes a look at the open source project jsii, what it is, why we created it and how it is helping us meet developers where they are. I have shared and talked about jsii in this newsletter many times, and this post goes much deeper including how other projects are beginning to explore how they can use this project beyond the original scope of the AWS CDK. Great stuff.

**Grafana**

The use of conversational interfaces across many different applications and uses cases continues to grow. As these conversational services become more important, there is a need to be able to monitor the performance and effectiveness of these interfaces with analytics and dashboards to drive continuous improvements in these interfaces. In this post, [Analyzing Amazon Lex conversation log data with Grafana](http://aws-oss.beachgeek.co.uk/8) Shanthan Kesharaju and Cecil Patterson collaborate and share a solution architecture that streams conversation logs from Amazon Lex to Amazon CloudWatch, using Grafana to build visualisation and reporting insights for missed utterances, user requests, and sentiment metrics.

![arch](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2020/12/01/Conv-Analytics-Dash.png)

**Jenkins**

[Integrating EC2 macOS workers with EKS and Jenkins](http://aws-oss.beachgeek.co.uk/b) Paul Roberts shares a great post that takes advantage of one of the announcements made during re:Invent, namely support for macOS instance types. In this post, Paul shares how you can leverage those as part of your developer workflows to build, test, package, and sign Xcode applications for the Apple platforms including macOS, iOS, iPadOS, tvOS, watchOS, and Safari. In this post, Paul uses Jenkins to show you how you can build your own build environment to do this.

**AWS SDK's**

A couple of posts this week on the AWS SDK's. First up we have [AWS SDK for Go version 2 (v2) – Release Candidate](http://aws-oss.beachgeek.co.uk/9), and in this short post from Sean McGrail he announces the Release Candidate (RC) of the AWS SDK for Go. This has undergone a major rewrite from the v1 code base thanks to customer feedback. Read the post to find out more, how to get started as well as a useful list of additional resources. Following that we have [HTTP keep-alive is on by default in modular AWS SDK for JavaScript](http://aws-oss.beachgeek.co.uk/c) from Trivikram Kamat, where he talks about a feature of the v3 AWS SDK for Javascript that has been enabled by default if you are using Node.js applications. Trivikram shows you what this is and how it works as well as the benefits it brings. 

**JMeter**

[Building high-quality benchmark tests for Amazon Redshift using Apache JMeter](http://aws-oss.beachgeek.co.uk/f) Asser Moustafa takes a look at how you can use the open source testing tool Apache JMeter, to setup and run your own benchmarking tests. Asser shares tips on what to think about as you approach this as well as how to optimise Apache JMeter.

**Maven**

[Continuously building and delivering Maven artifacts to AWS CodeArtifact](http://aws-oss.beachgeek.co.uk/h) Vinay Selvaraj's post shows you how you can build a continuous integration pipeline to deliver Maven artefacts to AWS CodeArtifact. Java developers often use Apache Maven artefact repositories to share and reuse Maven packages, and so with this solution you can now deploy those Maven packages to an AWS service called AWS CodeArtifact that provides a fully managed pay-as-you-go artefact repository service.

![arch](https://d2908q01vomqb2.cloudfront.net/7719a1c782a1ba91c031a682a0a2f8658209adbf/2020/11/13/drawio_diagram-1024x429.png)

**Java**

[Testing AWS Lambda functions written in Java](http://aws-oss.beachgeek.co.uk/l) Jerome Van Der Linden announces the release of [aws-lambda-java-tests](https://github.com/aws/aws-lambda-java-libs/tree/master/aws-lambda-java-tests), an opinionated library that simplifies writing tests when using Java on AWS Lambda. This post is going to go down very well writing unit and integration tests for Lambda can be a challenge, something this project and post aim to help you with.

**FFMpeg**

[Processing user-generated content using AWS Lambda and FFmpeg](http://aws-oss.beachgeek.co.uk/j) Abbas Nemr shows you how you can use the open source GPLv3 tool FFMpeg combined with AWS Lambda and storage services such as Amazon S3 and Amazon EFS to create serverless media processing workflows. Given some of the typical sizes of these artefacts, this posts covers how you can overcome those limits and still win with serverless.

### Quick updates

**Apache Kafka**

Amazon Managed Streaming for Apache Kafka (Amazon MSK) now supports Apache Kafka version 2.7.0 for new and existing clusters. Apache Kafka 2.7.0 includes several bug fixes and new features that improve performance. Some key features include the ability to throttle create topic, create partition, and delete topic operations (KIP-599) and configurable TCP connection timeout (KIP-601). For a complete list of improvements and bug fixes, see the Apache Kafka release notes for 2.7.0.

**FreeRTOS**

FreeRTOS now supports the ability to update multiple file types in an over-the-air (OTA) update operation. With this feature, FreeRTOS users can classify different types of files (e.g. firmware, certificate, general image) while creating an OTA update job. This enables a FreeRTOS device to identify the category of an incoming update and use it for a specific purpose (e.g. firmware update, certificate rotation, picture download) or target (e.g. secondary microcontroller, external memory) in an embedded application. Learn more here.

FreeRTOS is an an MIT licensed open source, real-time operating system for microcontrollers that makes small, low-power edge devices easy to program, deploy, secure, connect, and manage. You can use AWS IoT Device Management with FreeRTOS devices for an integrated OTA update solution.

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen).

### Your feedback matters!

I have put together a short feedback survey, which I would ask you to take - it will take no more than 2 minutes. You can access [here](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn). Many thanks!

[Take the survey](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn)