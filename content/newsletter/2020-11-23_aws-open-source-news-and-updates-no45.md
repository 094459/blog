---
title: 'AWS open source news and updates No.45'
date: '2020-11-23'
tags : [ oss-newsletter ]
---
## November 23rd - Instalment #45

Week No.45 and this is the last edition before re:Invent so look out this week for some blog posts sharing news about the open source track and open source sessions at re:Invent this year. This week we have another great selection of posts, projects and more. Make sure you check out the Karpenter project that was announced last week during AWS Container Day at KubeCon, a great selection of Kubernetes/container related posts and some more great posts on AWS Graviton2 and Nitro Enclaves.

A reminder that the[ Architecture Monthly Magazine: Open Source](https://aws.amazon.com/blogs/architecture/aws-architecture-monthly-magazine-open-source/) came out last week. Plenty of great stuff in there, from Ask an Expert, case studies, reference architectures, white papers and more. Fits perfectly in your Kindle, whichever version you have.

**Open Source Job of the Week**

We are still looking for applications, so if you fancy working with the AWS Amplify crew (I know, I know it means you will have to toil with the likes of Matt Auerbach and Nader Dabit) then check out this opening within their team. They are looking for folks excited about OSS to support Amplify developers in their GitHub repos and Discord channels. This is a great opportunity to work on the Amplify product team, and even better this is a remote role.

Details [here](https://www.amazon.jobs/en-gb/jobs/1345338/developer-support-engineer-amplify-framework) but feel free to reach out to Matt, Nader or myself.

### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to Istvan Szukacs, Nicola Venuti, Tyler Lynch, Andrea Cavagna,  Nathan Peck, Cagatay Gürtürk, Nader Dabit,  Namita Devadas, Rohit Kumar, Yan Cui, Ian Meyers, Bob Wise, Raja Jadeja, Alex Weibel, Gyuho Lee, Vishal Pathak, Jay Chen, Farhan Munir, Isan Rivkin, John Taylor, Richard Fan, Stephen Mallette, Anand Krishna, Steven David, Anuj Singh, Theo Salvo, Massimo Re Ferre, Re Alvarez-Parmar, Vikram Venkataraman, Rumeshkrishan Mohan, Krithivasan Balasubramaniyan, James Randall, Anand Krishna, Patrick Leung, Alec Littlechild, Steven David and Anuj Singh

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

**karpenter**

[karpenter](https://github.com/awslabs/karpenter) if you were watching the AWS Container Day last week you will have seen this new open source project being announced. Karpenter enables metrics driven node scaling in Kubernetes that allows you to optimise for any workload, cluster and any environment. This is an early stage, experimental project and is available as a developer preview. Don't miss Justin Garrison's[ tweet thread](https://twitter.com/rothgar/status/1329912982818615296?s=11) about this project either.

If you missed AWS Container Day then worry not, scroll down to the bottom and check out the videos section.

**aws-data-api**

[aws-data-api](https://github.com/awslabs/aws-data-api) this [tweet](https://twitter.com/IanMeyers/status/1329760321234460672) from open source developer Ian Meyers brought this new beta project to my attention. AWS Data API's is an open source project that provides the ability to replace traditional database back ends for your applications with simple HTTP API's. They offer the speed, scalability, reliability, and security of a sophisticated NOSQL platform, but with zero coding and no servers to manage. In seconds, you can create a new Data API Namespace that includes your data model, natural language search, and sophisticated data lineage tracking which is presented to your application as an HTTPS REST API.

**global-load-test**

[global-load-test](https://github.com/cagataygurturk/global-load-test) this open source project from AWS Community Hero Cagatay Gürtürk, is a command line tool that allows its users to load test HTTP(S) endpoints from seven geographical different regions leveraging AWS Route53 Health Checks against the endpoint and reports the latency from these regions. Cagatay provides some sample use cases in the README. Now this is not a new project, but speaking with him recently about why he created this and how you might use it he added "I first created this project because I noticed I was using Route53 a lot to test our geo proximity routing and also measure latencies from different parts of the world, so I have decided to create this to automate that" If this sounds like something you would find useful, why not check it out. Thanks Cagatay

**IAMFinder**

[IAMFinder](https://github.com/prisma-cloud/IAMFinder) is an open source tool that enumerates and finds users and IAM roles in a target AWS accounts, and using only the AWS account number IAMFinder is able to identify users and roles in that environment. You can read this post from Jay Chen, [IAMFinder: Open Source Tool to Identify Information Leaked from AWS IAM Reconnaissance](https://unit42.paloaltonetworks.com/iamfinder/) to find out more about this tool and how it works.

![arch](https://unit42.paloaltonetworks.com/wp-content/uploads/2020/11/word-image-49.png)

**cloudquery**

[cloudquery](https://github.com/cloudquery/cloudquery) is an open source tool that exposes your cloud configuration and metadata as sql tables, providing powerful analysis and monitoring without writing code. You can check out the detailed docs [here](https://docs.cloudquery.run/) including the [quickstart](https://docs.cloudquery.run/quick-start) which is the fastest way to get to grips with what this project can do for you.


**s3BucketManager**

[s3BucketManager](https://github.com/ronin1770/s3BucketManager) an open source python library from Farhan Munir that provides a simple way for users to create a bucket on AWS S3, upload local files to s3 bucket (filterable by extension type), get the list of files in the bucket.

**route53-cli**

[route53-cli](https://github.com/Isan-Rivkin/route53-cli) is an open source tool from Isan Rivkin that allows you to get info about your Route53 records from the Command line. Why would you use this over the aws cli? Well, Isan takes a shot at answering that with this response [here](https://www.reddit.com/r/aws/comments/jx1ifi/introducing_r53_cli_tool_input_a_domain_name_and/). As is often the case, sometimes these invent and simplify projects are all about making life easier for developers and users.

**sqs_clipboard**

[sqs_clipboard](https://github.com/jftuga/sqs_clipboard) this interesting open source tool from John Taylor uses AWS SQS in an interesting way. This tool uses AWS SQS as a clipboard to copy and paste across different systems and platforms, and John provides Windows, Mac and cross platform builds available.

### AWS open source posts

**AWS Graviton2 and Docker**

[Creating multi-architecture Docker images to support Graviton2 using AWS CodeBuild and AWS CodePipeline](https://aws.amazon.com/blogs/devops/creating-multi-architecture-docker-images-to-support-graviton2-using-aws-codebuild-and-aws-codepipeline/) Tyler Lynch provides a clear path for customers who are evaluating and adopting Graviton2 instance types for performance improvements and cost-optimisation by performing native builds for each architecture, instead of attempting to cross-compile on homogenous hardware. This post will show you how to build a CI/CD pipeline using AWS CodePipeline and AWS CodeBuild that can build multi-architecture Docker images in parallel to aid you in evaluating and migrating to Graviton2.

![illustration](https://d2908q01vomqb2.cloudfront.net/7719a1c782a1ba91c031a682a0a2f8658209adbf/2020/11/09/CodeBuild-and-CodePipeline.png)

**etcd**

[etcd gets ready to graduate](https://aws.amazon.com/blogs/opensource/etcd-gets-ready-to-graduate/) Gyuho Lee shares in this post how the CNCF project etcd has now moved from incubating to graduated. Etcd, is an open source project that provides a distributed key-value store that helps powers projects such as Kubernetes. This post shares a little about what this means as well as talking about how AWS has been contributing to this project and community. Given that it was KubeCon last week, Gyuho also shares a link to a talk where etcd is covered.

**gRPC**

[The versatility of gRPC, an open source high-performance RPC framework](https://aws.amazon.com/blogs/opensource/the-versatility-of-grpc-an-open-source-high-performance-rpc-framework/) Theo Salvo's post provides an introduction into gRPC. gRPC is an emerging open source protocol and a successor to HTTP designed to focus around the contract between applications and to let other protocols handle traffic routing. gRPC makes it easy to build functions in code that can be separated by networks, programming languages, and even different types of compute resources. Read on to learn more about gRPC and how it compares to TCP and HTTP.

![illustation](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2020/11/13/salvot_gRPC_f2.png) 

**Kubernetes**

We have a few Kubernetes related posts this week.

First up we have [Kubernetes and the path to cloud native application – An example with SAP Commerce](https://aws.amazon.com/blogs/awsforsap/kubernetes-and-the-path-to-cloud-native-application-an-example-with-sap-commerce/). Patrick Leung and Alec Littlechild tackle the question around how do you approach modernising existing enterprise workloads you might have that you might typically always deploy on virtual machines? Using the example of SAP Commerce, they take you through how you can approach modernising these kinds of workloads.

Next up is [Implementing Runtime security in Amazon EKS using CNCF Falco](https://aws.amazon.com/blogs/containers/implementing-runtime-security-in-amazon-eks-using-cncf-falco/) from Anand Krishna who demonstrates how you can set up an Amazon EKS cluster and configure runtime container security analysis and alerting with CNCF Falco and Amazon CloudWatch using custom dashboards and alarms. What is CNCF Falco? CNCF Falco is a runtime security tool for deep container security events analysis and alerts and  works in conjunction other AWS services such as Firelens and Amazon CloudWatch.  Falco continuously scans the containers running in the pods and sends the security, debug, or audit events as JSON format as STDOUT and this post explains in depth on how to install Falco and how to it works with other AWS services.

Steven David and Anuj Singh follow that post with [Open Source Calico for Windows Containers on Amazon EKS](https://aws.amazon.com/blogs/containers/open-source-calico-for-windows-containers-on-amazon-eks/) where they walk you through a tutorial on how to install and use Calico for Windows containers running on Amazon Elastic Kubernetes Service (EKS).

Up next is [Deploy applications on Amazon ECS using Docker Compose](https://aws.amazon.com/blogs/containers/deploy-applications-on-amazon-ecs-using-docker-compose/) from Massimo Re Ferre and is a must read post this week. He covers the basic features of the Docker Compose integration with Amazon ECS and AWS Fargate and how this integration allows for extending the investments many developers have made in producing Docker Compose artifacts over the years.

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2020/11/18/image-81.png)

Finally we have a collaboration between Re Alvarez-Parmar and Vikram Venkataraman in [Analyze Kubernetes container logs using Amazon S3 and Amazon Athena](https://aws.amazon.com/blogs/containers/analyze-kubernetes-container-logs-using-amazon-s3-and-amazon-athena/) where they show how you can capture Kubernetes application logs using Fluent Bit, store them in Amazon S3, and analyse them using Amazon Athena.  At the crux of the solution is Fluent Bit, an open source log processor and forwarder that allows you to collect logs from different sources, and unify and send them to multiple destinations. Fluent Bit plugins support various AWS and partner monitoring solutions, including Amazon CloudWatch, Amazon Kinesis, Datadog, Splunk, and Amazon S3.

![logs](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2020/11/18/image-8.jpg)

**Apache TinkerPop**

[Exploring Apache TinkerPop 3.4.8’s new features in Amazon Neptune](https://aws.amazon.com/blogs/database/amazon-neptune-now-supports-apache-tinkerpop-3-4-8/) [Apache TinkerPop](https://github.com/apache/tinkerpop) is an open source graph computing framework and provides a standard way to interface with a number of different databases, and in AWS that means AWS Neptune.  When a data system is TinkerPop-enabled, its users are able to model their domain as a graph and analyse that graph using the Gremlin graph traversal language. In this post, Stephen Mallette outlines some of the new features available and provides some examples to demonstrate their capabilities with Neptune.

**Apache Hudi**

[Creating a source to Lakehouse data replication pipe using Apache Hudi, AWS Glue, AWS DMS, and Amazon Redshift](https://aws.amazon.com/blogs/big-data/creating-a-source-to-lakehouse-data-replication-pipe-using-apache-hudi-aws-glue-aws-dms-and-amazon-redshift/) Vishal Pathak shares with you how you can use Apache Hudi to address the challenge of how you efficiently capture changes in your source data sources and sync to Amazon S3. Vishal shows how to use Apache Hudi to create tables in the AWS Glue Data Catalog using AWS Glue jobs and then create jobs to move source inserts and deletes into Hudi tables. There is a lot packed into this solution, but CloudFormation templates are provided to make it easy for you.

![arch](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2020/11/16/image-10.png)

**Apache Spark**

[Building Python modules from a wheel for Spark ETL workloads using AWS Glue 2.0](https://aws.amazon.com/blogs/big-data/building-python-modules-from-a-wheel-for-spark-etl-workloads-using-aws-glue-2-0/) Rumeshkrishan Mohan and Krithivasan Balasubramaniyan go through some new capabilities to install or upgrade Python modules from a wheel file, from a PyPI repository, or from modules you store in Amazon S3 when creating an AWS Glue Spark ETL job. This will allow you to create jobs that complete faster, enabling you to run micro-batching and time-sensitive workloads more cost-effectively. AWS Glue is a fully managed extract, transform, and load (ETL) service that makes it easy to prepare and load your data for analytics and provides infrastructure for running Apache Spark ETL jobs

**AWS ParallelCluster**

[Monitoring dashboard for AWS ParallelCluster](https://aws.amazon.com/blogs/compute/monitoring-dashboard-for-aws-parallelcluster/) Nicola Venuti walks you through an add-on extension that you can use if have deployed and are using AWS ParallelCluster to help monitor your cloud resources with AWS ParallelCluster. AWS ParallelCluster is an AWS-supported, open source cluster management tool that makes it easy to deploy and manage High Performance Computing (HPC) clusters on AWS. Nicola shares how you can create lovely looking dashboards in Grafana, and provides all the code and instructions you need so you can do this for yourself.

![grafana](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2020/11/10/Master-node-details-1.2-1024x536.jpg)

**AWS CDK**

[Announcing the General Availability of Amazon ECS Service Extensions for AWS CDK](https://aws.amazon.com/blogs/containers/general-availability-amazon-ecs-service-extensions-for-aws-cdk/) Nathan Peck shares some thoughts on using AWS Cloud Development Kit (AWS CDK) to programmatically define containerised deployments for Amazon ECS.  Nathan does a great job summarising and putting into context what AWS CDK is, before sharing some concrete examples of how to apply this within Amazon ECS.

![illus](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2020/11/12/cdk-levels-of-contructs-1024x576.png)

Nathan goes on to introduce the ecs-service-extensions module showing you how you can use it. 

**Real-time Serverless APIs**

[Building Real-time Serverless APIs with PostgreSQL, CDK, TypeScript, and AWS AppSync](https://aws.amazon.com/blogs/mobile/building-real-time-serverless-apis-with-postgres-cdk-typescript-and-aws-appsync/) Nader Dabit provides a tutorial, building from an earlier post, where you will learn how to build a real-time AppSync API. You will use PostgreSQL as the database, use infrastructure as code via AWS CDK written in TypeScript and using GraphQL to build a blogging back end. Finally you will use the CDK CLI to create an outputs file that can be integrated into a client application using AWS Amplify.

![arch](https://d2908q01vomqb2.cloudfront.net/0a57cb53ba59c46fc4b692527a38a87c78d84028/2020/11/13/archdi-1024x459.jpg)

**Hybrid post-quantum cipher suites**

[Round 2 post-quantum TLS is now supported in AWS KMS](https://aws.amazon.com/blogs/security/round-2-post-quantum-tls-is-now-supported-in-aws-kms/) This is the second post following an earlier edition of this newsletter, [link here](https://aws.amazon.com/blogs/security/post-quantum-tls-now-supported-in-aws-kms/), and in this post Alex Weibel shares how the AWS Key Management Service (AWS KMS) now supports three new hybrid post-quantum key exchange algorithms for the Transport Layer Security (TLS) 1.2 encryption protocol that’s used when connecting to AWS KMS API endpoints. These new hybrid post-quantum algorithms combine the proven security of a classical key exchange with the potential quantum-safe properties of new post-quantum key exchanges undergoing evaluation for standardisation.

To use the post-quantum cipher suites with AWS KMS, you need the preview release of the AWS Common Runtime (CRT) HTTP client for the AWS SDK for Java 2.x as well as configure the AWS CRT HTTP client to use the s2n post-quantum hybrid cipher suites. These are both open source projects which you can find [here](https://aws.amazon.com/blogs/developer/introducing-aws-common-runtime-http-client-in-the-aws-sdk-for-java-2-x/) and [here](https://github.com/awslabs/s2n).

![latecny](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2020/11/15/Round-2-post-quantum-Figure-2.jpg)

### Partner / Industry spotlight

**OpenShift**

[Announcing Red Hat OpenShift Service on AWS](https://aws.amazon.com/blogs/containers/announcing-red-hat-openshift-service-on-aws/) Bob Wise and Raja Jadeja introduce a new offering, Red Hat OpenShift Service on AWS (ROSA), that is available in preview today. ROSA will provide a fully managed OpenShift service with integrated cluster creation, consumption-based billing model, single invoice through AWS, and joint support from AWS and Red Hat. Bob and Raja cover how this will work and share with you how to sign up for the preview.

**Public Sector**

[Simpson College and eThink Education: Promoting institutional success through Moodle](https://aws.amazon.com/blogs/publicsector/simpson-college-ethink-education-promoting-institutional-success-moodle/) this is a case study on how the Simpson College together with eThink Education, an AWS Partner, were able to respond quickly to the changing demands brought about by the pandemic, and deploy Moodle, a well known open source learning management system. Beyond providing students with information on courses, it has also helped fuel success for students and the institution, and set up a new way of operating beyond the pandemic.

### Case Studies and Industries

**Intuit**

[What is Trapheus?](https://aws.amazon.com/blogs/opensource/what-is-trapheus/) this post is from Namita Devadas and Rohit Kumar, Senior Software Engineers at Intuit introduce Trapheus. I covered this project a few weeks ago in this newsletter, and Trapheus is an open source Python serverless utility for automated restoration of Relational Database Service (RDS) instances from snapshots into any development, staging, or production environments. This post provides more details as to this projects capabilities as well as walks you through how to get started and a peek at what the future/road map looks like.

![trapheus](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2020/11/02/spotaws_What-is-Trapheus_f3.png)

**AWS AppSync**
**Real-Time Live Sports Updates**

[Real-Time Live Sports Updates Using AWS AppSync](https://aws.amazon.com/solutions/implementations/real-time-live-sports-updates-using-aws-appsync/)

This solution is designed to demonstrate a serverless solution that enables media customer to deliver real-time live sports updates to web and mobile application via AppSync subscriptions. Many companies in M&E have mobile and web apps that enable their customers to view sports scores, track live game/match info, receive fantasy sports updates and enable their subscribers to chat. The common use cases for delivering real-time sports data to customers are:

* A person is viewing a screen in the mobile or web app that is showing live game updates. An event occurs (e.g. goal scored, time left in game, player injured) and the M&E company must push this to the view in the application.
* In a fantasy sports league, the scores for a fantasy team are changing with each play in the game. Their points, standings, status in the head-to-head competition against another player in the fantasy league will continue to change. These changes are delivered to live viewers of the fantasy game.
* Also, in fantasy sports, members of a league want to chat. They want to talk trash or banter with their friends. Building chat requires the right real-time platform.
* When mobile app users do not have an app in the foreground, the M&E company wants to deliver updates via a push notification. The solution must recognize whether a viewer is actively watching the live updates with the app in the foreground or the app is in the background. If the app is in the background, the live update should be delivered as a push notification.

![arch](https://d1.awsstatic.com/Solutions/Solutions%20Category%20Template%20Draft/Solution%20Architecture%20Diagrams/real-time-live-sports-reference-architecture.612903fa80b8811eb8840e76aca0cc86735fc83e.jpg)

Source code is available in the GitHub repository [here](https://github.com/awslabs/real-time-live-sports-updates-using-aws-appsync).

### Latest blog posts

**AWS Nitro Enclaves**

[How to Use AWS Nitro Enclaves Attestation Document](https://richardfan1126.medium.com/how-to-use-aws-nitro-enclaves-attestation-document-7824e176ffa4) another great post from AWS Community Builder Richard Fan on AWS Nitro Enclaves, following up from his previous post that I shared last week. This week he takes a look at attestation documents with AWS Nitro Enclaves. What they are and how you can use them, providing a help sample use case which makes it nice and easy to follow along.

![arch](https://miro.medium.com/max/1400/1*YQWFBpog_Clz58nHPnPN0Q.png)

**.NET on AWS Graviton2**

[Compute “Bang for Buck” on Azure and AWS – 20% to 40% advantage on AWS](https://www.azurefromthetrenches.com/compute-bang-for-buck-on-azure-and-aws/) another great benchmark post from James Randall (minus fractals this time, which is a shame). As James writes at the beginning of this post:

> It struck me there were some interesting differences across ARM, x86, Azure and AWS and I’ve expanded my testing and attempted here to present these findings in (hopefully) useful terms.

Warning, this post contains plenty of bar graphs and data points! If you are interested and want to maybe learn more as to how this can help you with your .NET workloads then make sure you contact James - he provides his contact details in this post.

**GraphQL**

[How I built a social network in 4 weeks with GraphQL and serverless](https://theburningmonk.com/2020/11/how-i-built-a-social-network-in-4-weeks-with-graphql-and-serverless/) this latest post from AWS Serverless Hero Yan Cui shares a recent client project to help launch a new social network for university students to engage with each other to do sports. Yan shares some interesting details including the tech stack. Even better is Yan provides masterclass sessions where you can learn this stack and how to create your own solutions. Check this post for more details on this project as well as how to sign up for his Masterclass sessions.

![app](https://theburningmonk.com/wp-content/uploads/2020/11/img_5fb419bff2b2a-1536x854.png)

**Leapp**

[Remote access to EC2 instances. The easy (and secure) way](https://www.itscava.com/remote-access-to-ec2-instances-the-easy-and-secure-way) a few weeks ago I shared this open source project that allowed you to simplify how you managed ssh access to your AWS EC2 instances. I have been using it since, and I love it. I reminds me of my old favourite tool I used to use ages ago called SecureCRT in how easy it was to manage my secure sessions. Anyway, Andrea Cavagna has put this blog post together to show you how to get up and running with this tool.

![demo](https://cdn.hashnode.com/res/hashnode/image/upload/v1605693914859/p1enNhguc.gif)

The project is in active development, so whether you use it and want to feedback issues or feature requests, or even better want to help drive the project, get in touch with the team.

**Firecracker**

Istvan Szukacs comes up with a great solution if you have any Raspberry Pi's about that you do not know what to do with. In [Getting started with Firecracker on Raspberry Pi](https://dev.l1x.be/posts/2020/11/22/getting-started-with-firecracker-on-raspberry-pi/), Istvan walks you through the high level architecture of Firecracker and the VM/micro VM continuum before providing this handy walkthrough. Keep following him for part two.


### Videos of the week

I have some great videos for you this week. First up we have [Capturing Trace Data with the AWS Distro for OpenTelemetry](https://www.youtube.com/watch?feature=share&v=837NtV0McOA&app=desktop) which shows how to capture trace data using the AWS Distro for OpenTelemetry. It covers auto-instrument trace sending from Java web applications to AWS X-Ray so that you can analyse trace data and debug errors.

{% youtube 837NtV0McOA %}

Following that we have Colm MacCárthaigh in a deep dive on AWS Nitro Enclaves, where he covers what Nitro Enclaves are, explores the Nitro Enclaves architecture and how it works and then how you would use Nitro Enclaves for confidential computing.

{% youtube K5PRNHaEdOw %}

Finally, if you missed AWS Container Day then worry not, you can view all the sessions here.

{% youtube o2_sGFkYNvA %}

### Quick Updates

A round up of smaller updates and quick bites of open source goodness.

**Apache Flink**

A couple of items this week. First up, Amazon Kinesis Data Analytics for Apache Flink now provides access to the Apache Flink Dashboard, giving you greater visibility into your applications and advanced monitoring capabilities. You can now view your Apache Flink application’s environment variables, over 120 metrics, logs, and the directed acyclic graph (DAG) of the Apache Flink application in a simple, contextualised user interface. Read more about this [here](https://aws.amazon.com/about-aws/whats-new/2020/11/amazon-kinesis-data-analytics-now-supports-the-apache-flink-dashboard/). The second item is that you can now build and run streaming applications using Apache Flink version 1.11 in Amazon Kinesis Data Analytics for Apache Flink. Apache Flink v1.11 provides improvements to the Table and SQL API, which is a unified, relational API for stream and batch processing and acts as a superset of the SQL language specially designed for working with Apache Flink. Apache Flink v1.11 capabilities also include an improved memory model and RocksDB optimisations for increased application stability, and support for task manager stack traces in the Apache Flink Dashboard. With this launch, Kinesis Data Analytics supports JDK 11 and Scala 2.12, with support for Python coming soon. Read the full announcement [here](https://aws.amazon.com/about-aws/whats-new/2020/11/amazon-kinesis-data-analytics-now-supports-apache-flink/).

**AWS ParallelCluster**

AWS ParallelCluster is a fully supported and maintained open source cluster management tool that makes it easy for scientists, researchers, and IT administrators to deploy and manage High Performance Computing (HPC) clusters in the AWS cloud. HPC clusters are collections of tightly coupled compute, storage, and networking resources that enable customers to run large scale scientific and engineering workloads. Significant feature enhancements to this latest release of AWS ParallelCluster include:

* Support for P4d instances: Customers can now select P4d instances for use in their clusters. These instances include support for NVIDIA GPUDirect Remote Direct Memory Access (RDMA) enabled through Elastic Fabric Adapter, which can accelerate tightly coupled applications using the NVIDIA Collective Communications Library (NCCL) for GPU-to-GPU communication. This option can be enabled using the new enable_efa_gdr configuration setting.
* Support for the CentOS 8 Operating System: Customers can now choose CentOS 8 as their base operating system of choice to run their clusters for both x86 and Arm architectures. As with other operating systems supported by AWS ParallelCluster, you can choose your operating system using the base_os configuration option, and can also choose to create and use your own custom AMI built on top of CentOS 8. CentOS 8 support also includes compatibility with all of AWS ParallelCluster’s supported schedulers and NICE DCV for remote visualization.
* Amazon CloudWatch Cluster Metrics Dashboard: Customers can track and visualize operational metrics for their clusters in CloudWatch. This includes metrics such as CPU and network utilization, file system read and write data operations, and read and write operations for Amazon Elastic Block Store volumes. Customers can use this dashboard to visualize cluster usage or identify performance bottlenecks to diagnose how best to improve cluster performance.

**Elasticsearch**

Amazon Elasticsearch Service now supports the ability to reload dictionary files without reindexing your data. Elasticsearch uses analysers to convert string data into terms or tokens that power its search capabilities. These analysers can do things like remove white space and stop words, perform stemming, handle compound words, and add synonyms. Previously, on Amazon Elasticsearch Service these analysers could only process data as it was indexed. If you wanted to add some additional synonyms at a later time, you had to reindex your data with the new dictionary file. With the new hot reload capability, you can call analysers at search time, and your dictionary files augment the search results during the query. This feature also lets you version your dictionary files in Amazon Elasticsearch Service and update them on your domains, also without having to reindex your data. 

This feature is powered by Open Distro for Elasticsearch, an Apache 2.0-licensed distribution of Elasticsearch. To learn more about Open Distro for Elasticsearch and this feature, visit the [project website](https://opendistro.github.io/for-elasticsearch/).

Hot reload of dictionary files is available on any Amazon Elasticsearch Service domain running Elasticsearch 7.8 or later. To learn more, see the [documentation](https://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/custom-packages.html).

**AWS CDK**

Two updates this week relating to AWS CDK.

[AWS CDK EKS Construct Library in Developer Preview and Adds Support for cdk8s](https://aws.amazon.com/about-aws/whats-new/2020/11/aws-cdk-eks-construct-library-available-developer-preview/) The EKS Construct Library is an AWS CDK module that helps customers provision Amazon EKS clusters using infrastructure-as-code best practices. Up until now, it has been in an experimental state, incorporating lots of customer feedback and undergoing multiple API and behavioural changes. Starting from version 1.65.0 (https://github.com/aws/aws-cdk/releases/tag/v1.65.0), the library is graduating to Developer Preview. This means that we are not planning any breaking changes going forward and are preparing the library for GA.

In addition to cluster provisioning, the EKS Construct Library enables customers to deploy Kubernetes resources onto their clusters. Currently, those resources can be deployed by either manually creating Kubernetes manifests, or by installing Helm charts. Starting with version 1.67.0, customers can also utilise manifest authoring capabilities provided by The CDK for Kubernetes (cdk8s). These include type-safety, IDE assistance, and higher level constructs available via the cdk8s+ library.

[Amazon ECS extensions for AWS CDK](https://aws.amazon.com/about-aws/whats-new/2020/11/amazon-ecs-extensions-for-aws-cdk-is-now-generally-available/) The Amazon Elastic Container Service (Amazon ECS) extensions module that extends the service construct in AWS Cloud Development Kit (AWS CDK), is now generally available. The new Amazon ECS service construct for AWS CDK supports extensions that automatically add additional capabilities such as AWS App Mesh or FireLens to your containerised services using familiar programming languages. Read more in the blog post above from Nathan Peck.

### Events for your diary

**re:Invent 2020**
**November 30th to December 18th**

AWS re:Invent is a learning conference hosted by Amazon Web Services (AWS) for the global cloud computing community. The event features keynote announcements, launches, sessions, and more. It is FREE to attend and we have some amazing open source sessions as well as a dedicated open source track with unmissable content.

Read there FAQ [here](https://reinvent.awsevents.com/faq/) and then Sign up for re:Invent using this link [here](https://reinvent.awsevents.com/).

We will be posting a couple of blog posts to share some of the open source sessions with you this week. Until you get them, you can use this list to search the sessions as the agenda is now live.

**Open source track**

* OPN 203: Redis 2020: Creating a Community-Driven Project
* OPN 305: Build real-time apps with Apache Flink
* OPN 206: Building End-To-End ML Workflows with Kubeflow Pipelines
* OPN 301: Open Source Observability at AWS
* OPN 302: The Serverless LAMP stack
* OPN 303: Open Source Meets SaaS: Accelerating the Path to SaaS Adoption
* OPN 304: Open source failure injection on AWS
* OPN 201: Introduction to GraphQL
* OPN 204: Accelerate that App! with Amplify opensource framework
* OPN 202: App modernization on AWS with Apache Kafka & Confluent Cloud

**Other open source sessions**

* ADM 301 Running ultra-high throughput ad tech workloads on Aerospike
* AIM 313 Scaling MLOps on Kubernetes with Amazon SageMaker Operators
* AIM 402 Fast distributed training and near-linear scaling with PyTorch on AWS
* AIM 404 Productionizing R workloads using Amazon SageMaker, featuring Siemens 
* AIM 405 Train large models with billions of parameters in TensorFlow 2.0
* ARC 307 Going global in minutes: Multi-Region expansion simplified
* CMP 206 HPC on AWS: Innovating without infrastructure constraints 
* CON 201 Getting an insight into your Kubernetes applications
* CON 202 AWS Copilot: Simplifying container development
* CON 207 Define AWS service resources with AWS Controllers for Kubernetes 
* CON 211 Red Hat OpenShift Service on AWS
* DAT 314 Running Apache Cassandra workloads with Amazon Keyspaces
* DOP 202 AWS CDK: What’s new and what’s next
* FWM 201 Power modern serverless applications with GraphQL and AWS AppSync
* FMW 202 Empower front-end web and mobile app development with AWS Amplify
* FMW 303 Build iOS & Android mobile apps in record time with Flutter and AWS Amplify
* FMW 304 Unify access to siloed data with AWS AppSync GraphQL resolvers
* FMW 306 Best practices to securely operate GraphQL at scale with AWS AppSync
* IOT 303 Developing and deploying modern edge applications at scale
* NFX 302 Simplifying delivery as code with Spinnaker and Kubernetes

**Virtual ROS-Industrial Conference 2020**
**December 15 - 16, 2020**

The 8th edition of ROS-Industrial Conference will be held as a virtual event. It is not only the annual community meeting for the European ROS-Industrial community but this years event is also the final event of the H2020 ROSIN project. The conference gives you the chance to see the newest technical developments and to meet people and companies, which are active in the ROS community.

Learn more and sign up [here](https://rosindustrial.org/rosindustrial-conference-2020).

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen).

### Your feedback matters!

I have put together a short feedback survey, which I would ask you to take - it will take no more than 2 minutes. You can access [here](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn). Many thanks!

[Take the survey](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn)