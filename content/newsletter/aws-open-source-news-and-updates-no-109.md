---

title: 'AWS open source news and updates #109'
date: '2022-04-22'
tags : [ oss-newsletter, aws open source, AWS CDK, Istio, Crossplane, Apache Flink, AWS Orbit Workbench, Consul, OpenZFS, Open Policy Agent, MySQL, dbt, Delta Lake, Kubernetes, AWS Lambda Powertools, Apache Hudi, Jaeger, MySQL, Karpenter, cdktf, OpenSearch]

---

## April 22nd, 2022 - Instalment #109

Newsletter #109. 

Welcome to edition #109 of the AWS open source newsletter. Big news, I have shaken things up and will be changing the publish date to Friday mornings, starting today with this edition. Over the months I have received some feedback about changing the published date to Fridays, so I am hoping this will give everyone plenty of time to check out the projects, read the posts and provide everyone with something to do over the weekend (if they want!). 

It has been a couple of weeks since the last newsletter, thanks to the Easter break. That means that this week there is a lot to unpack. We have over 13 great new open source projects, including "ts2asl" that simplifies developing AWS Step Functions using the TypeScript programming language, "route53-cli" a neat command line tool for interacting with Rout53, "sageinspector" another cli tool, this time to make it easier to interact with your Amazon SageMaker resources, "automating-pii-data-detection" a nice solution to help you automate the detection of pii data, and lots of more great tools, samples and demos.

Featured content in the newsletter this week covers a number of topics, including a number of articles and posts on AWS CDK and Kubernetes. Other topics featured include Istio, Crossplane, Apache Flink, AWS Orbit Workbench, OpenZFS, Open Policy Agent, MySQL, AWS Lambda Powertools, Apache Hudi, Jaeger, MySQL, Karpenter, cdktf, and more. 

This weeks videos feature reckoner, Consul Service Mesh and Data Science on AWS taking a look at dbt and Delta Lake. Finally, I have updated the events section to include up coming events, so make sure you check those out (and please let me know what events you might be attending that I should include)


**OpenSearch news**

Big news from last week was announcement of updates and improvements to the OpenSearch governance model around maintainers, and the first non AWS maintainer in the OpenSearch project. There were many tweets, too many to list, but [here was one of the first I saw](https://twitter.com/nknize/status/1514378767099207683).

Whilst I am talking about OpenSearch, the project created a new issue last week asking for feedback around client compatibility as new versions roll out. Check out the issue, [[PROPOSAL] Ensure clients are compatible across at least 2 major versions](https://aws-oss.beachgeek.co.uk/1m8) and share your thoughts with the project.


**Do you have an interesting open source project you want to share?**

As always, if you are working on anything interesting you would like me to include in this weekly round up, please drop me a line at ricsue@amazon.com.


### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Isan-Rivkin, Emir Özbir, Lorenzo Garuti, Vara Bonthu, Manabu McCloskey, Nima Kaviani, Farooq Ashraf, Jeremy Ber, Olalekan Elesin, Nick Corbett, Ajish Abraham, Paul Hargis, Matt Winkler, Jack G. M. FitzGerald, Kevin Coleman, Apoorva Kulkarni, Mikhail Shapirov, Jerome Van Der Linden, Dariusz Osiennik, Dmitry Kolomiets, Rosh Plaha, Ken Winner, Michael Lin, Saravanan G, Prima Virani, Vu Dao,  Viji Sarathy, Michael Hauss, Eric Hsueh, Benjamin Menuet, Anouar Zaaber, Moshir Mikael, and Armando Segnini.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest open source projects

#### Community

**ts2asl**

[ts2asl](https://aws-oss.beachgeek.co.uk/1m6) this project enables developers to define AWS Step Functions using the TypeScript programming language. It allows developers to benefit from a familiar syntax, type safety, and mature ecosystem of tools for linting, editing, and automated testing. Good docs and examples should help you get started quickly with this tool. 

**route53-cli**

[route53-cli](https://aws-oss.beachgeek.co.uk/1m5) if you are looking for a cli tool to interact with the Route53 service, then you are in luck. Isan-Rivkin has put together this neat tool with great documentation and plenty of examples to help you stay in the terminal.

**Invictus-AWS**

[Invictus-AWS](https://aws-oss.beachgeek.co.uk/1m4) this tool is a python script that will help automatically enumerate and acquire relevant data from an AWS environment. The tool doesn't require any installation it can be run as a standalone script with minimal configuration required. The goal for Invictus-AWS is to allow incident responders or other security personnel to quickly get an insight into an AWS environment to answer the following questions: What services are running in an AWS environment, for each of the services what are the configuration details, and what logging is available for each of the services that might be relevant in an incident response scenario.

#### Tools

**k8s-aws-terraform-cluster**

[k8s-aws-terraform-cluster](https://aws-oss.beachgeek.co.uk/1m2) Lorenzo Garuti has created this repository that will help you to deploy in a few minutes a high available Kubernetes cluster on Amazon AWS using mixed on-demand and spot instances. Great and detailed documentation makes this easy to follow, and some examples stacks are provided so you can see how this works (including of course, WordPress)

![architecture diagram for k8s using terraform](https://camo.githubusercontent.com/428f6b314cae17b364bb50a082d540e9d147525344eb0191014a08ef07d4c9f7/68747470733a2f2f6761727574696c6f72656e7a6f2e6769746875622e696f2f696d616765732f6b38732d696e6672612e706e673f)

**kubectl-irsa**

[kubectl-irsa](https://aws-oss.beachgeek.co.uk/1m7) is a tool from Emir Özbir that provides a kubectl plugin to test abilities of IAM policies which is assigned to the serviceAccount roles via AWS IAM Policy simulator service.

![example of using kubectl-irsa plugin](https://github.com/WoodProgrammer/kubectl-irsa/blob/master/img/main.gif?raw=true)

**sageinspector**

[sageinspector](https://aws-oss.beachgeek.co.uk/1ld) this is an open source cli tool to inspect SageMaker resources more easily. I think this is a pretty neat tool, so make sure you check this out if you are a user of Amazon SageMaker.

**amazon-sagemaker-training-jobs-benchmarks**

[amazon-sagemaker-training-jobs-benchmarks](https://aws-oss.beachgeek.co.uk/1lc) this repository contains examples and related resources for Amazon SageMaker Training jobs over different instance types focusing on the aspects of time to train and cost to train. Amazon SageMaker makes it easy to train machine learning using EC2 instances. There are many instance types to choose from and this choice affects the speed and cost of training. This repository contains example benchmark for various deep learning use cases. You can see results directly in the notebook, reproduce results by re-running the notebooks. And alter the notebooks to create new scenarios to benchmark.

**aws-backup-compliance**

[aws-backup-compliance](https://aws-oss.beachgeek.co.uk/1le) this repo contains code that integrates Backup Audit Manager with Security Hub and AWS CodePipeline. The integration with Security Hub configures AWS Backup Audit Manager framework with 5 default controls (and you can additional controls to the template), which generate and trigger AWS Config rules and the rule evaluations are converted to Security Hub findings. The integration with AWS CodePipeline, enables developers to embed automated backup controls for AWS resources in their development workflows and shift left with backup compliance in AWS.

**eks-jumphost**

[eks-jumphost](https://aws-oss.beachgeek.co.uk/1lf) this repo contains a Terraform module to create an EC2 instance used as a jump host to interact with a private EKS cluster. Its usage is meant for development environments, not production: in the latter case provisioning should be done via a continuous integration and deployment platform.

![example architecture produced by sample project](https://github.com/aws-samples/eks-jumphost/blob/main/docs/images/architecture.png?raw=true)

#### Demos and Samples

**devsecops-quickstart**

[devsecops-quickstart](https://aws-oss.beachgeek.co.uk/1la) this repo will help development teams to quickly set up a ready to use environment integrated with a multi-account CI/CD pipeline following security and DevOps best practices, and the use of a number of open source tools such as Bandit, Snyk, cfn-nag, and enables you define and enforce policies using Open Policy Agent (OPA).

**automating-pii-data-detection**

[automating-pii-data-detection-and-data-masking-tasks-with-aws-glue-databrew-and-aws-step-functions](https://aws-oss.beachgeek.co.uk/1l4) this repository provides an AWS CloudFormation template that deploys a sample solution demonstrating how to leverage AWS Glue DataBrew to automatically detect PII data, and mask the respective PII data with its native transformation functions. In the post, [Build a data pipeline to automatically discover and mask PII data with AWS Glue DataBrew](https://aws-oss.beachgeek.co.uk/1l5), Samson Lee walks you through this project in detail.

![architecture for solution on automating pii data detection](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2022/04/01/ArchitectureDiagram.jpg)

**wav2vec2-huggingface**

[amazon-sagemaker-fine-tune-and-deploy-wav2vec2-huggingface](https://aws-oss.beachgeek.co.uk/1lb) this repo contains code that will help you fine-tune and deploy Wav2Vec2 model for speech recognition with HuggingFace and SageMaker. There is a helpful blog post, [Fine-tune and deploy a Wav2Vec2 model for speech recognition with Hugging Face and Amazon SageMaker](https://aws-oss.beachgeek.co.uk/1l8), that explains how to use SageMaker to easily fine-tune the latest Wav2Vec2 model from Hugging Face, and then deploy the model with a custom-defined inference process to a SageMaker managed inference endpoint

![flow of demo for fine tune wav2vec](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2022/04/13/ML-7125-image001.png)

**aws-lambda-domain-model-sample**

[aws-lambda-domain-model-sample](https://aws-oss.beachgeek.co.uk/1lh) this project contains a Lambda function with domain model objects. By using Hexagonal Architecture (Ports and Adapters pattern), it separates domain model from other layer code. The Hexagonal Architecture, or ports and adapters architecture, is an architectural pattern used in software design. 

![hexagonal architecture model diagram](https://github.com/aws-samples/aws-lambda-domain-model-sample/blob/main/hexagonal_architecture.png?raw=true)

### Kubernetes

This week we had several posts related to Kubernetes, so they get their own section.

**EKS Blueprints**

Last week I was excited to read about the introduction of a new open-source project called EKS Blueprints that makes it easier and faster for you adopt Amazon Elastic Kubernetes Service (Amazon EKS). EKS Blueprints is a collection of Infrastructure as Code (IaC) modules that will help you configure and deploy consistent, batteries-included EKS clusters across accounts and regions. Kevin Coleman, Apoorva Kulkarni, and Mikhail Shapirov have collaborated on a blog post, [Bootstrapping clusters with EKS Blueprints](https://aws-oss.beachgeek.co.uk/1lk) that dives into the details. This is an exciting project that will help make it even easier to use your favourite open source technologies on Amazon EKS.

![architecture of eks blueprints](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2022/04/18/eks-blueprints-ref-951x1024.png)

**Crossplane**

[Crossplane](https://aws-oss.beachgeek.co.uk/1ky) is an open source Kubernetes add-on that enables platform teams to assemble infrastructure from multiple vendors, and expose higher level self-service APIs for application teams to consume, without having to write any code. (check out [the GitHub repo](https://aws-oss.beachgeek.co.uk/1ky) for more info). In the post [Introducing AWS Blueprints for Crossplane](https://aws-oss.beachgeek.co.uk/1kz), Vara Bonthu, Manabu McCloskey, and Nima Kaviani share how we have open sourced AWS Blueprints for Crossplane. Crossplane offers a higher abstraction layer called Compositions, and these allow users to build opinionated templates for deploying cloud resources. This new project aims to simplify and accelerate your journey to managing AWS resources with Crossplane example Compositions. [hands on]

**Istio**

When building SaaS solutions in the Cloud, many builders leverage Istio, an open-source service mesh, for deploying their multi-tenant applications. It provides features such as traffic management, security, and observability at the Kubernetes pod level. In the post, [SaaS Identity and Routing with Istio Service Mesh and Amazon EKS](https://aws-oss.beachgeek.co.uk/1l1), Farooq Ashraf explains how to develop an architecture based on Amazon EKS that demonstrates a siloed SaaS deployment model, using Istio Service Mesh to manage request authentication and per-tenant routing. [hands on]

![architecture of istio service mesh on eks](https://d2908q01vomqb2.cloudfront.net/77de68daecd823babbb58edb1c8e14d7106e83bb/2022/03/30/SaaS-Istio-Service-Mesh-EKS-3.png)

**Karpenter**

AWS Community Builder (and prolific blogger) Vu Dao has created a two series blog post looking at Karpenter. Karpenter is an open-source node provisioning project built for Kubernetes. Its goal is to improve the efficiency and cost of running workloads on Kubernetes clusters. Whilst this is currently integrated with AWS, the project has been designed so that other providers could be added. In [AWS Karpenter Hands-on](https://aws-oss.beachgeek.co.uk/1m0) Vu provides a good introduction and gets you up and running, and then in [Karpenter with AWS Node Termination Handler](https://aws-oss.beachgeek.co.uk/1m1) he explores how you might use this with Spot instances. [hands on]

**FleetDM**

[osquery](https://aws-oss.beachgeek.co.uk/1ly) is an open source SQL powered operating system instrumentation, monitoring, and analytics framework. [Fleet](https://aws-oss.beachgeek.co.uk/1lz) is the most widely used open source osquery manager. Combining the two, and showing you how you can deploy them on AWS is Prima Virani in the blog post, [Hosting FleetDM on Amazon EKS](https://aws-oss.beachgeek.co.uk/1lx) [hands on]

![architecture for fleetdm](https://images.ctfassets.net/i8bfc4nr05rq/6cxHqCtjgcRVNcUjTvLFje/ee95051c4fb43e7c8295f8ecc6ed81a8/image2.png)

**AWS Distro for OpenTelemetry**

AWS Distro for OpenTelemetry (ADOT) offers AWS customers the ability to reduce the installation footprint of observability tools in their environments. Amazon EKS add-ons are a capability within Amazon EKS that were  introduced in December 2020 to provide lifecycle management for operational software in your clusters that make it easy for users to operate production-grade clusters in a stable and secure manner. In the post, [Metrics and traces collection using Amazon EKS add-ons for AWS Distro for OpenTelemetry](https://aws-oss.beachgeek.co.uk/1m9) Viji Sarathy, Michael Hauss, and Eric Hsueh share an overview of the design of Amazon EKS add-ons for ADOT and how the add-on employs an ADOT Operator to manage the lifecycles of one or more instances of an ADOT Collector in an EKS cluster.

![architecture of ADOT an EKS Add Ons](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2022/04/20/Addon-2.png)


### AWS and Community blog posts

**dbt**

dbt has established itself as one of the most popular tools in the modern data stack. The dbt tool makes it easy to develop and implement complex data processing pipelines in SQL, and provides developers with a simple interface to create, test, document, evolve, and deploy their workflows. Benjamin Menuet, Anouar Zaaber, Moshir Mikael, and Armando Segnini have put together [Build your data pipeline in your AWS modern data platform using AWS Lake Formation, AWS Glue, and dbt Core](https://aws-oss.beachgeek.co.uk/1ma) share how to deploy a data pipeline in your modern data platform using the dbt-glue adapter built by the AWS Professional Services team in collaboration with dbtlabs.

![dbt on aws](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2022/04/20/BDB-2022-image001.jpg)

**Apache Hudi**

Kyle Weller from Onehouse highlights the key integrations between Apache Hudi and AWS in his post, [Apache Hudi Native AWS Integrations](https://aws-oss.beachgeek.co.uk/1lp) where you can learn how you can build an open Lakehouse on AWS with Apache Hudi.

![architecture diagram from post](https://assets.website-files.com/61f38d7a4e41d6a673cd65c7/62575aadca5d807da9f05dd7_Screen%20Shot%202022-04-13%20at%204.11.27%20PM.png)

**Amazon RDS MySQL**

[Automate RDS Slow Query Log Analysis With Slack Integration](https://aws-oss.beachgeek.co.uk/1lq) is an interesting post from the folks at ShellKode, that helps you to automate the slow query log analysis using an open source tool, pt-query-digest, sending the results to the developers on daily basis via email or Slack. I think this is interesting as a few weeks ago I shared an open source project called [aws-slack-clickoops-watcher](https://github.com/phzietsman/aws-slack-clickoops-watcher) which caught the interest of a lot of readers of this newsletter. [hands on]

![rds mysql slow log analysis architecture](https://miro.medium.com/max/1400/1*mM1KfbAVBK0pJvn5QjXYcQ.png)

**Jaeger**

Jaeger is an open source distributed tracing platform created by Uber Technologies, that is useful for monitoring microservices-based distributed systems. Dmitry Kolomiets has put together this blog post, [Introducing Jaeger Quick Start — Deploying on AWS](https://aws-oss.beachgeek.co.uk/1lr) that explores an alternative tracing backend for your AWS originated traces that you might want to know more about. This post will provide you everything you need to know to get started. 

![Jaeger quickstart on AWS](https://miro.medium.com/max/1400/1*HvxrPI6X6l1QEBiRdhsTZw.png)

**AWS CDK**

A number of great posts last week on AWS CDK. Starting off with Rosh Plaha's post, [We’ve begun to move towards the AWS CDK and here’s why](https://aws-oss.beachgeek.co.uk/1lt) who provides a nice overview of the key features of CDK and then looks at the trade offs and pros/cons of moving towards AWS CDK.

Following that we have Ken Winner from those nice folks at Stedi who wrote a few weeks ago, [Parallel CDK stack deployments with GitHub Actions](https://aws-oss.beachgeek.co.uk/1lu) diving in how to accelerate deployments using AWS CDK, and the journey they took in dramatically reducing their deployment times. Great read, and essential if you are using CDK.

![example gif from the stedi blog](https://www.stedi.com/images/blog/parallel-cdk-stack-deployments/github-actions-workflow.gif)

The next post is super interesting, and covers an area that is well underserved from content. The post, [Deploy Infrastructure using CDK for Terraform with Go](https://aws-oss.beachgeek.co.uk/1lv) from Michael Lin shows you how you can use cdktf to deploy a Go application in a different Cloud provider. cdktf works in a similar fashion to AWS CDK, except that rather than synthesising to CloudFormation, this generates Terraform code and allows you to leverage the hundreds of providers and thousands of module definitions provided by Terraform and the Terraform ecosystem. This is a great example of the CDK project being used by builders in a much broader context than just AWS. [hands on]

The final post, and still on cdktf, is AWS Community Builder Saravanan G with his post, [Create AWS Infrastructure using CDK for Terraform](https://aws-oss.beachgeek.co.uk/1lw) that provides an introduction into using cfktf, using it to deploy a sample Python application. [hands on]

![example flow using cfktf](https://res.cloudinary.com/practicaldev/image/fetch/s--ax04OYhm--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://mktg-content-api.vercel.app/api/assets%3Fproduct%3Dterraform-cdk%26version%3Dmain%26asset%3Dwebsite/docs/cdktf/concepts/images/cdktf-terraform-workflow.png)

**AWS Orbit Workbench**

AWS Orbit Workbench is an open source framework for building a data analytics workbench on AWS, which I featured [back in #69](https://dev.to/aws/aws-open-source-news-and-updates-69-50bf) of this newsletter. You can build a workbench that gives you access to the right tools for your use cases, either through the out-of-the-box integrations or through the extensible architecture. AWS Hero Olalekan Elesin, Head of Data Platform & Data Architect at HRS Group did a guest blog post on the open source blog, [Scheduling Jupyter Notebooks with AWS Orbit Workbench](https://aws-oss.beachgeek.co.uk/1l3) where he shares how this project has become an integral part of their data platform, and how this has enabled a simplified experience from data exploration to productionising data workloads within the business.

**Open Policy Agent**

Open Policy Agent (OPA) is an open source general-purpose policy engine, licensed under the Apache License 2.0, that allows you to decouple policy decision-making from application code. Ajish Abraham writes, [Easily Running Open Policy Agent Serverless with AWS Lambda and Amazon API Gateway](https://aws-oss.beachgeek.co.uk/1l9) demonstrates how to run OPA as a service within a container in Lambda using just the standard precompiled OPA binary. OPA is commonly used in cloud-native environments and ran as a service or container. Because OPA decisions are stateless, OPA is a great candidate to run in a serverless architecture for cost savings, simplicity, and performance. [hands on]

![architecture for open policy agent](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2022/04/12/OPAblog1.png)

**AWS Lambda Powertools**

In the post, [Handling Lambda functions idempotency with AWS Lambda Powertools](https://aws-oss.beachgeek.co.uk/1ln), Jerome Van Der Linden and Dariusz Osiennik explores what idempotency is and how to implement it more easily with AWS Lambda Powertools.

![flow diagram of example application and idempotency](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2022/04/14/idempotency1.png)

**Apache Flink**

Amazon Kinesis Data Analytics Studio makes it easy for customers to analyse streaming data in real time, as well as build stream processing applications powered by Apache Flink. Jeremy Ber shares how to get started querying data interactively from an Amazon Kinesis Data Stream using the Python API for Apache Flink (Pyflink) in his post, [Query your data streams interactively using Kinesis Data Analytics Studio and Python](https://aws-oss.beachgeek.co.uk/1l2) [hands on]

![graph of demo apache flink in python](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2022/04/01/BDB1610-image005.png)

**Other posts worth checking out**

* [Announcing the General Availability of openCypher support for Amazon Neptune](https://aws-oss.beachgeek.co.uk/1ll) looks at announcement last week of the general availability of openCypher query language support with Amazon Neptune
* [Tracing an AWS App Runner service using AWS X-Ray with OpenTelemetry](https://aws-oss.beachgeek.co.uk/1l0) shares how you can instrument applications deployed using AWS App Runner with the AWS Distro for OpenTelemetry (ADOT)  [hands on]
* [Develop and test AWS Glue version 3.0 jobs locally using a Docker container](https://aws-oss.beachgeek.co.uk/1l6) develop and test your AWS Glue scripts locally (spark-submit, pyspark, JupyterLab, and pytest) using this solution [hands on]
* [Let’s Architect! Using open-source technologies on AWS](https://aws-oss.beachgeek.co.uk/1lm) explores how you can use a number of open source projects from AWS when building your solutions
* [Deploy .NET Blazor WebAssembly Application to AWS Amplify](https://aws-oss.beachgeek.co.uk/1lo) shows you how to build a full CI/CD pipeline for a Blazor WebAssembly using the AWS amplify [hands on]

**Case Studies**

A couple of interesting case studies this week, featuring the Amazon Genomics CLI and the use of open source big data projects at Uber.

* The Amazon Genomics CLI is an open source tool that simplifies genomics workflows in the cloud. The UC Santa Cruz Genomics Institute shared how they were collaborating with AWS and using tools like the Amazon Genomics CLI in their blog post, [UCSC and Amazon Web Services work to accelerate genomics research](https://aws-oss.beachgeek.co.uk/1lg)

* [Presto® on Apache Kafka® At Uber Scale](https://aws-oss.beachgeek.co.uk/1ls) is a look at how Uber uses Presto on Apache Kafka at scale, and is a really great read. Essential reading this week.

![architecture of presto on apache kafka at uber](https://1fykyq3mdn5r21tpna3wkdyi-wpengine.netdna-ssl.com/wp-content/uploads/2022/04/Figure-4.png)

### Quick updates

**ActiveMQ**

Amazon MQ now provides support for ActiveMQ 5.16.4. This update to ActiveMQ contains [several fixes and enhancements](https://aws-oss.beachgeek.co.uk/1mb) compared to the previously supported version, ActiveMQ 5.16.3.

**Amazon Corretto**

On April 19th, 2022 Amazon announced quarterly security and critical updates for Amazon Corretto Long-Term Supported (LTS) versions of OpenJDK. Corretto 18.0.1, 17.0.3, 11.0.15, and 8u332 are now available for download.

**Apache Cassandra**

Amazon Keyspaces (for Apache Cassandra), a scalable, highly available, and fully managed Cassandra-compatible database service, now helps you read and write data in Apache Spark more easily by using the open-source Spark Cassandra Connector. Apache Spark is an open-source engine for large-scale data analytics. Customers use Apache Spark to perform analytics on data stored in Amazon Keyspaces more efficiently. Customers also use Amazon Keyspaces to provide applications consistent, single-digit-millisecond read access to analytics data from Spark. Now, you can read and write data between Amazon Keyspaces and Spark more easily by using the open-source Spark Cassandra Connector. Amazon Keyspaces support for the Spark Cassandra Connector helps you run Cassandra workloads in Spark-based analytics pipelines more easily by using a fully managed and serverless database service. With Amazon Keyspaces, you don’t need to worry about Spark competing for the same underlying infrastructure resources as your tables. Amazon Keyspaces tables scale up and down automatically based on your application traffic.

**Open Data**

This quarter, we released 13 new or updated datasets including CMIP5, 1950s US Decennial Census, and open genomics data for Galaxy. Read the post [Downscaled CMIP5, 1950 US Census, and open genomics data for Galaxy: The latest open data on AWS](https://aws-oss.beachgeek.co.uk/1l7) for some highlights among the new datasets.

On a related note, Jack G. M. FitzGerald wrote [Amazon releases 51-language dataset for language understanding](https://aws-oss.beachgeek.co.uk/1lj) in the Amazon Science blog, sharing three announcements including news about the availability of a new dataset called MASSIVE, which is composed of one million labeled utterances spanning 51 languages, along with open-source code, which provides examples of how to perform massively multilingual NLU modelling. Read the post to learn more.

**MySQL**

You can now configure your database connections on Amazon Aurora MySQL-Compatible Edition from an allowable list of ciphers. Configurable cipher suites help provide you with more security control over the connection encryption that your database server accepts. The supported ciphers, dependent on the version of your Aurora MySQL-compatible database, include the following:

* DHE-RSA-AES128-SHA
* DHE-RSA-AES128-SHA256
* DHE-RSA-AES128-GCM-SHA256
* DHE-RSA-AES256-SHA
* DHE-RSA-AES256-SHA256
* DHE-RSA-AES256-GCM-SHA384
* ECDHE-RSA-AES128-SHA
* ECDHE-RSA-AES128-SHA256
* ECDHE-RSA-AES128-GCM-SHA256
* ECDHE-RSA-AES256-SHA
* ECDHE-RSA-AES256-SHA384
* ECDHE-RSA-AES256-GCM-SHA384

**OpenZFS**

AWS DataSync now supports transferring files to and from Amazon FSx for OpenZFS, a fully managed service that offers highly reliable, scalable, performant, and feature-rich file storage built on the open-source OpenZFS file system. Using DataSync, you can easily and securely migrate your on-premises file or object storage to FSx for OpenZFS or perform ongoing transfers of your data between FSx for OpenZFS and your on-premises storage or AWS Storage services. You can also use DataSync to move data between FSx for OpenZFS file systems.

### Videos of the week

**Data Science on AWS**

Antje Barth and Chris Fregly introduce a couple of guest speakers, Paul Hargis and Matt Winkler that share how to use use open source *Delta Lake* and *dbt* in your ML data pipelines. Essential viewing this weeks folks.

{{< youtube uAm8vJADmMw >}}

**Consul Service Mesh**

Continuing in their series of shows featuring HashiCorp open source tools running on AWS, colleague and fellow DA Jenna Pederson and J. Cole Morrison from HashiCorp show you how to set up a Consul Service Mesh for their microservices architecture on ECS. They cover the main concepts in Consul and build out the infrastructure components required for the Consul servers.

{{< youtube qYpqzbxPSdA >}}

**reckoner**

It has been a while since I have shared a video from the Containers from the Couch team, but last week they (Justin Garrison and Sai Vennam, plus Luke Reed from Fairwinds) put together a show that featured how to manage your helm charts with open source tools such as reckoner from Fairwinds, that lets you declaratively manage multiple helm charts. Watch to see more.

{{< youtube A-N_zwjJwL0 >}}

### Events for your diary

**AWS London Summit**
**April 27th**

We have a number of open source sessions (including my very own on Apache Airflow), so if you are about later this week why not register and pop along.

[AWS London Summit registration page](https://aws.amazon.com/events/summits/london/)

**AWS Berlin Summit**
**May 11th/12th**

Aside from the AWS open source sessions (including me again, talking about Apache Airflow) we will have our very own Spot and myself manning the open source booth. Really looking forward to this and would love to see you come down and share your open source projects on our booth.

[AWS Berlin Summit registration page](https://aws.amazon.com/events/summits/berlin/)

**KubeCon**
**May 16th-20th, Valencia Spain**

The Cloud Native Computing Foundation’s flagship conference gathers adopters and technologists from leading open source and cloud native communities in Valencia, Spain from 16 – 20 May 2022. I will be there with many of the open source team and other AWS colleagues, so if you are going, make sure you swing by the AWS Booth.

Find out more about the [event here](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/).

**GitOpsCon Europe**
**May 17th, Valencia Spain**

GitOpsCon Europe is designed to foster collaboration, discussion, and knowledge sharing on GitOps. This event is aimed at audiences that are new to GitOps as well as those currently using GitOps within their organisation. Get connected with others that are passionate about GitOps. Learn from practitioners about pitfalls to avoid, hurdles to jump, and how to adopt GitOps in your cloud native environment.

The event is vendor-neutral and is being organised by the CNCF GitOps Working Group. Topics include getting started with GitOps, scaling and managing GitOps, lessons learned from production deployments, technical sessions, and thought leadership.

Read more about this from the official page [here](https://events.linuxfoundation.org/gitopscon-europe/).

**CDK Day**
**May 26th - Virtual**

This is a community organised event about AWS CDK, cdktf, projen and cdk8s. This will be third year they run this event, and if the previous two are anything to go by, this will be essential viewing - live streamed via You Tube. Check out and register for the event over at their home page at [https://www.cdkday.com/](https://www.cdkday.com/)

**BOSC 2022**
**July 13-14, Madison, Wisconsin, USA**

The Bioinformatics Open Source Conference (BOSC) has been held annually since 2000, and this year AWS is proud to be a platinum sponsor for this event. BOSC covers all aspects of open source bioinformatics software and open science, including (but not limited to) these topics, Open Science and Reproducible Research, Open Biomedical Data, Citizen/Participatory Science, Standards and Interoperability, Data Science Workflows, Open Approaches to Translational Bioinformatics, Developer Tools and Libraries, Inclusion, and Outreach and Training. This is a hybrid event (in person/virtual) and you find out more by checking out the event page, [BOSC 2022](https://aws-oss.beachgeek.co.uk/1li)

**OpenSearch**
**Every Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting - Feb2022](https://aws-oss.beachgeek.co.uk/1az)



https://www.meetup.com/OpenSearch/events/285152025/


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)