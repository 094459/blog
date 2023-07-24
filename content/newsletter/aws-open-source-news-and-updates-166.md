---
title: 'AWS open source newsletter #166'
date: '2023-07-24'
tags : [ oss-newsletter, aws open source, Grafana, AWS Amplify, PostgreSQL, karpenter, Amazon Corretto, Amazon EMR on EKS, Powertools for AWS Lambda,  Apache Iceberg, OpenZFS, Redis, AWS CDK, FHIR, OpenSearch, Apache Hive, Apache Airflow, MWAA, Seekable OCI, SOCI, eksctl, Cedar, komiser, Terraform, Dev Containers]

---

## July 24th, 2023 - Instalment #166

Welcome to #166 of the AWS open source newsletter. As always, we search high and low for the best and latest open source content, and I think you will love what we have lined up this week.

This weeks new projects include a library to help you managed and validate your environment variables when working with AWS Lambda, a new Rust based tool for interacting with your S3 buckets, an essential tool to help CDK developers remove a lot of the setup work, and a tool that helps you run  Yocto embedded Linux build jobs in AWS. Also featured are repositories that help you bootstrap open source observability tools in your AWS account, a repo that provides code and supporting material to help deploy an OIDC for your Managed Workflow for Apache Airflow environments, and sample code on how you can use the Fault Injection Service around a number of uses cases.

From projects to blog posts, and this week we have select some great content covering Grafana, AWS Amplify, PostgreSQL, karpenter, Amazon Corretto, Amazon EMR on EKS, Powertools for AWS Lambda,  Apache Iceberg, OpenZFS, Redis, AWS CDK, OpenSearch, Apache Hive, Apache Airflow, Seekable OCI, eksctl, Cedar, and komiser. Also, be sure to check out the events section as there are a few events happening this week as we have added quite a few new events including a couple running this week.

That should keep you busy for the week. As always, let me know what open source projects you want featured, or drop me a line or DM to include your project. Until next week, enjoy!

**Feedback**

Please please please take 1 minute to [complete this short survey](https://www.pulse.aws/promotion/10NT4XZQ) and you will forever have my gratitude! 

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created.

So thank you to the following open source heroes:  Ran Isenberg, Efi Merdler-Kravitz, Thomas Roos, Jake Page, Darin McAdams, Daryll Swager, Lukas Gentele, Rich Burroughs, Lukonde Mwila, Abdallah Shaban, Ashish Nanda, Shayon Sanyal, Marcio Morales, Bill Pfeiffer, Farhan Angullia, Adarsh Janakiraman, Jay Vohra, Aneel Murari, Jaswanth Kumar Jonnalagadda, Parnab Basak, Olly Pomeroy, Vaibhav Khunger, Donnie Prakoso, Mike Stefaniak, Mohamed Ahmed, Amardeepsingh Siglani, Subhobrata Dey, Jimish Shah, Saurabh Singh, Surya Sashank Nistala, Nate Archer, Nicholas Knize, Prabhakar Sithanandam, Praveen Sameneni, Pallavi Priyadarshini, Xenia Tupitsyna, Wooyoung Jung, Eunju Rho, Sean Lee, Elamaran Shanmugam, Imaya Kumar Jagannathan, Rodrigue Koffi, and Mikhail Shapirov.

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution. The projects mentioned here do not represent any formal recommendation or endorsement, I am just sharing for greater awareness as I think they look useful and interesting!*

#### Tools

**aws-lambda-env-modeler**

[aws-lambda-env-modeler](https://aws-oss.beachgeek.co.uk/32a) is a Python library from AWS Hero Ran Isenberg designed to simplify the process of managing and validating environment variables in your AWS Lambda functions. It leverages the power of Pydantic models to define the expected structure and types of the environment variables. This library is especially handy for serverless applications where managing configuration via environment variables is a common practice. The project documentation is what you would expect from Ran, amazing and very clear. Check out this repo, read the problem statement and see if this is something that you will find useful in your projects.

**aws-cli-tools**

[aws-cli-tools](https://aws-oss.beachgeek.co.uk/32b)  is a new tool that Efi Merdler-Kravitz has been working, written in Rust that quickly deletes S3 buckets. It's a part of a bigger adventure that he has embarked on - revamping some AWS CLI tools to make things faster with Rust. Check out the top level project,  [https://github.com/aws-cli-tools](https://aws-oss.beachgeek.co.uk/32c) for updates and new tools that he might create. Very nice work Efi, and certainly one that I am going to find very useful.


**iac-devtools-cli-for-cdk**

[iac-devtools-cli-for-cdk](https://aws-oss.beachgeek.co.uk/30h) is a command line interface tool automates many of the tedious tasks of building, adding to, documenting, and extending AWS CDK applications. It helps you by doing the following: 1/Automates templated build of a basic multi-stack CDK application with integrated security, devops, and pre-formatted documentation, 2/Automates templated build of a starter CDK stack, 3/Automates templated build of a starter CDK construct, and 4/Automates templated build of DevOps tooling for CDK deployment on Github or Gitlab. It is an opinionated tool that integrates Well-Architected principals of cloud native software design by default.

![demo of cdk-powertools-cli](https://github.com/aws-samples/cdk-powertools-cli/blob/main/assets/documentation/images/cpt-setup.gif?raw=true)

**meta-aws-buildbot**

[meta-aws-buildbot](https://aws-oss.beachgeek.co.uk/32d) This repository contains buildbot using AWS CDK to run Yocto embedded Linux build jobs in AWS. Thank you Thomas Roos for giving me a heads up on this project, and Thomas added that they use this to test meta-aws with all supported releases and archs (with shared SSTATE, polling changes of remote repos, kvm testimage...)

**cdk-git-tagger**

[cdk-git-tagger](https://aws-oss.beachgeek.co.uk/32e) is a tool for CDK users that will tag your CDK Stacks with the current git repo location for easier identification of deployed stacks. It provides a CDK [aspect](https://aws-oss.beachgeek.co.uk/32g) that will automatically add the Git repository URL to all of your assets as tags. This can make getting from AWS resource back to CDK significantly easier. 

**cdk-aws-observability-accelerator**

[cdk-aws-observability-accelerator](https://aws-oss.beachgeek.co.uk/31y) is a set of opinionated modules to help you set up observability for your AWS environments with AWS Native services and AWS-managed observability services such as Amazon Managed Service for Prometheus,Amazon Managed Grafana, AWS Distro for OpenTelemetry (ADOT) and Amazon CloudWatch. It provides curated metrics, logs, traces collection, cloudwatch dashboard, alerting rules and Grafana dashboards for your EKS infrastructure, Java/JMX, NGINX based workloads and your custom applications. The blog post, [Announcing AWS CDK Observability Accelerator for Amazon EKS](https://aws-oss.beachgeek.co.uk/31z) provides more details, with Elamaran Shanmugam, Imaya Kumar Jagannathan, Rodrigue Koffi, and Mikhail Shapirov showing you how to use AWS CDK Observability Accelerator to apply open source observability using AWS-managed open source services to a single Amazon EKS cluster.

![overview of cdk aws observability accelerator](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2023/07/19/Image1-Blog-1024x507.png)

### Demos, Samples, Solutions and Workshops

**amazon-cloudfront-end-to-end-tracing-with-opentelemetry**

[amazon-cloudfront-end-to-end-tracing-with-opentelemetry](https://aws-oss.beachgeek.co.uk/31w) this repo provides sample code that demonstrates how to setup an end-to-end tracing with OpenTelemetry that starts from Amazon CloudFront. To help you get going, Wooyoung Jung, Eunju Rho, and Sean Lee have put together this blog post, [Set up end-to-end tracing with Amazon CloudFront using OpenTelemetry](https://aws-oss.beachgeek.co.uk/31x).

![overview of opentelemetry end to end tracing architecture](https://d2908q01vomqb2.cloudfront.net/5b384ce32d8cdef02bc3a139d4cac0a22bb029e8/2023/06/07/blog-picture-1.png)

**aws-fis-exp-tem-using-cft-automation**

[aws-fis-exp-tem-using-cft-automation](https://aws-oss.beachgeek.co.uk/32f) this repository contains CloudFormation templates for AWS Fault Injection Simulator (FIS). AWS FIS is a service that helps you perform fault injection experiments on your applications and infrastructure to test their resiliency. By using these templates, you can easily provision and configure FIS resources in your AWS account. Experiment Templates for the following Experiments are included in the CFN: 1/ Stopping an EC2 instance, 2/ Reboot an EC2 instance, 3/Stop and Start an EC2 instance, 4/ Kernel Crash - intentionally causing a kernel crash at the operating system level, 5/ Network Disruption (Subnet) - Causing a disruption in network connectivity at the subnet level by blocking incoming and outgoing traffic to and from the subnet, and 6/ EBS IO Stuck - This will temporarily halt the input/output (IO) activity on all the underlying EBS volumes attached to the database server including root volumes.

**alb-sso-mwaa**

[alb-sso-mwaa](https://aws-oss.beachgeek.co.uk/32h) provides sample code and details on how you can integrate your organisation’s existing OIDC-based IdPs with Amazon Managed Workflow for Apache Airflow (MWAA) to grant secure access to your existing Amazon MWAA environments. Check out the detailed walk through on how to use this code by reading the post from Jay Vohra, Aneel Murari, Jaswanth Kumar Jonnalagadda, and Parnab Basak who put together, [Automate secure access to Amazon MWAA environments using existing OpenID Connect single-sign-on authentication and authorization](https://aws-oss.beachgeek.co.uk/31r) . [hands on]

![overview of mwaa and oidc integration](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2023/07/05/DBSBLOG_3543_1_image1.jpg)

### AWS and Community blog posts

**Community round up**

First up are the community posts that caught my eye, starting off with [Correlating security events across different log sources](https://aws-oss.beachgeek.co.uk/327) written by Amardeepsingh Siglani, Subhobrata Dey, Jimish Shah, Saurabh Singh, Surya Sashank Nistala, Nate Archer, Nicholas Knize, Prabhakar Sithanandam, Praveen Sameneni, Pallavi Priyadarshini, and Xenia Tupitsyna (might be the biggest collaboration featured in this newsletter, go crew!). In the post they look at how OpenSearch Security Analytics provides an open-source solution for security practitioners that addresses the cost and complexity of running security operations by automating threat detection and threat analysis. 

![opensearch security analytics workflow](https://opensearch.org/assets/media/blog-images/2023-07-13-correlating-security-events/detector-infrastructure.png)

From OpenSearch to Cedar, where Darin McAdams talks a look at Cedar policies and looks at how compressible they are in his post, [How well do Cedar policies compress?](https://aws-oss.beachgeek.co.uk/328). Darin dives deep and provides some experiments that provide some answers (no spoilers, read the post).

![overview of graph for cedar compression](https://cedarland.blog/usage/compression/compression-ratios.png)

The last post in this roundup is from Jake Page, who writes [Harnessing Komiser and Grafana for Custom Cloud Dashboards](https://aws-oss.beachgeek.co.uk/329). Komiser is an open-source cloud-agnostic resource manager that integrates with your AWS environments and helps you to build a cloud asset inventory, and helps you break down your cost at the resource level. Jake shows you how you can combine this with Grafana to create very nice looking dashboards.

![overview of komiser on grafana](https://uploads-ssl.webflow.com/6373a295d370a41a1a802e8c/64afbaed342b526eb3f116e7_Screenshot%202023-07-12%20at%2010.51.56.png)

**eksctl**

Whilst most folk will probably still be thinking how do you pronounce this word, (for the record, I am in the e-k-s, control camp) Mike Stefaniak and Mohamed Ahmed have been putting together [Weaveworks and AWS Joining Forces to Maintain Open Source eksctl](https://aws-oss.beachgeek.co.uk/31v) that looks at the work behind this tool, and news of the joint maintainer-ship between Weaveworks and AWS. They cover how the eksctl project has been moved from the Weaveworks GitHub organization to a new top level GitHub organisation https://github.com/eksctl-io, and how that will be jointly maintained by Weaveworks and AWS moving forward.

**Seekable OCI (SOCI)**

A couple of posts this week on this open source project from AWS. Seekable OCI (SOCI), is a technology that enables container runtimes to implement lazy loading the container image to start applications faster without modifying the container images. 

First up we had my colleague Donnie Prakoso put together [AWS Fargate Enables Faster Container Startup using Seekable OCI](https://aws-oss.beachgeek.co.uk/320) which looks at the announcement that AWS Fargate now supports SOCI, which helps applications deploy and scale out faster by enabling containers to start without waiting to download the entire container image.

![illustration of SOCI](https://d2908q01vomqb2.cloudfront.net/da4b9237bacccdf19c0760cab7aec4a8359010b0/2023/07/13/soci-index.png)

Diving deeper into this topic was the theme of the next post, [Under the hood: Lazy Loading Container Images with Seekable OCI and AWS Fargate](https://aws-oss.beachgeek.co.uk/321) where Olly Pomeroy and Vaibhav Khunger dive deeper into SOCI and how it can index a container image without modifying its contents or requiring a change to existing tools or workflows. Very cool post.

![automating soci in your workflows](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2023/07/18/aws_cfn_soci_index_builder_architecture_diagram.png)

**Apache Airflow**

In the post [Schedule automated operations for your Terraform managed resources on AWS](https://aws-oss.beachgeek.co.uk/31q) where Farhan Angullia and Adarsh Janakiraman show you how you can schedule operations of your Terraform resources (in this specific example, they use Amazon Managed Workflows for Apache Airflow - MWAA) in your AWS account using mainly Amazon EventBridge Scheduler and AWS CodeBuild. Why would you want to do this? Well this can help save operating costs for resources that does not need to run 24/7, something that I get ask a lot about on how you can do this with MWAA. hands on]

![overview of scheduling terraform resources on aws](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2023/07/13/Figure-2-1.png)

**Other posts and quick reads**

* [Build a serverless log analytics pipeline using Amazon OpenSearch Ingestion with managed Amazon OpenSearch Service](https://aws-oss.beachgeek.co.uk/324) provides a detailed guide on how to create a serverless ingestion pipeline to deliver Apache access logs to an OpenSearch Service domain using OpenSearch Ingestion [hands on]
* [Query your Apache Hive metastore with AWS Lake Formation permissions](https://aws-oss.beachgeek.co.uk/322) demonstrates how to apply Lake Formation permissions on a Hive metastore database and tables and query them using Athena [hands on]

![overview of hive metastore architecture for lake formation](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2023/07/20/HMS-blog-diagram.jpg)

* [How to write and execute integration tests for AWS CDK applications](https://aws-oss.beachgeek.co.uk/31p) looks at the experimental integ-runner and integ-tests constructs, that provide valuable tooling for defining and conducting automated integration tests for your AWS CDK applications [hands on]

![overview of writing and executing cdk integration tests](https://d2908q01vomqb2.cloudfront.net/7719a1c782a1ba91c031a682a0a2f8658209adbf/2023/07/18/cdk-integ-assertion.png)

* [Enhanced interoperability with SMART on FHIR support in Amazon HealthLake](https://aws-oss.beachgeek.co.uk/31s) examines how to achieve better patient outcomes by supporting this standard within Amazon HealthLake

![overview of smart on fhir](https://d2908q01vomqb2.cloudfront.net/c5b76da3e608d34edb07244cd9b875ee86906328/2023/07/12/SMART-on-FHIR-authentication-flow-with-HealthLake_rev-1024x480.png)

* [Migrate data from Amazon Aurora PostgreSQL to Amazon MemoryDB for Redis using AWS DMS](https://aws-oss.beachgeek.co.uk/31t)  shows you how you can migrate data from Amazon Aurora PostgreSQL-Compatible Edition to Amazon MemoryDB using AWS Database Migration Service (AWS DMS), using an example retail use case [hands on]

![migrating postgresql to redis overview](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2023/07/14/image1.png)

* [Configuring the auto-expansion of Amazon FSx for OpenZFS with Amazon CloudWatch and AWS Lambda](https://aws-oss.beachgeek.co.uk/31u) helps show you how you can use CloudWatch to monitor your Amazon FSx for OpenZFS file system, automating the expansion of your file system based on user-configured conditions [hands on]

![overview of clever OpenZFS filesystems](https://d2908q01vomqb2.cloudfront.net/e1822db470e60d090affd0956d743cb0e7cdf113/2023/06/22/pic1-1.jpg)

**Case Studies**

* [Orca Security’s journey to a petabyte-scale data lake with Apache Iceberg and AWS Analytics](https://aws-oss.beachgeek.co.uk/323) looks at Orca’s journey building a transactional data lake using Amazon Simple Storage Service (Amazon S3), Apache Iceberg, and AWS Analytics.

### Quick updates

**Powertools for AWS Lambda**

If you missed the [tweets](https://aws-oss.beachgeek.co.uk/31o) from Heitor Lessa last week, Lambda Powertools is now Powertools for AWS Lambda. It is more than just a name change however, so make sure you check out the full thread where Heitor breaks it all down for you. Powertools for AWS Lambda is now an official AWS team, which brings long term sustainability to this open source project loved by many developers, among other things. 

**Amazon EMR on EKS**

Amazon EMR on EKS now supports programmatic execution of Jupyter notebooks when running interactive workloads via managed endpoints. Amazon EMR on EKS enables customers to run open-source big data frameworks such as Apache Spark on Amazon EKS. Amazon EMR on EKS customers can setup and use a managed endpoint (available in preview) to run interactive workloads using integrated development environments (IDEs) such as EMR Studio.  Today, customers use Jupyter notebooks on Amazon EMR on EKS using managed endpoints with the convenience of EMR Studio Workspaces using a web-based interface. With programmatic execution for EMR on EKS managed endpoints, data engineers now have the added flexibility to run jupyter notebooks using scripts, chain multiple notebooks, or use orchestration services such as AWS Step Functions or Apache Airflow to build pipelines and run interactive workloads..

**Karpenter**

Karpenter is a flexible, high-performance Kubernetes node provisioning and management solution that helps improve application availability, operational overhead, and cluster compute utilisation by launching new EC2 instances that are best fit to the scale, scheduling, and resource requirements of the workloads in a cluster. When Karpenter is installed in your cluster, it .it automatically launches EC2 instances to meet applications’ compute needs, upgrades them to improve security, and optimizes the instances launched to lower costs. By doing this, Karpenter reduces the scheduling latencies and infrastructure costs of your cluster. With the launch of v0.29.0, Karpenter extends the automated node provisioning support for Windows containers running on EKS.

Find out more about this new capability by reading the post, [Karpenter now supports Windows containers](https://aws-oss.beachgeek.co.uk/31l), where Marcio Morales and Bill Pfeiffer show you how you can scale out/in Windows Server 2019 and Windows Server 2022 using Karpenter. [hands on]

![overvierw of karpenter on windows](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2023/07/13/Karpenter-Scheduling.png)

**Amazon Corretto**

On July 18, 2023 Amazon announced quarterly security and critical updates for Amazon Corretto Long-Term Supported (LTS) and Feature (FR) versions of OpenJDK. Corretto 20.0.2, 17.0.8, 11.0.20, 8u381 are now available for download. Amazon Corretto is a no-cost, multi-platform, production-ready distribution of OpenJDK. Check out the [downloads page](https://aws-oss.beachgeek.co.uk/31j) for more details and download links.

**PostgreSQL**

Amazon Aurora PostgreSQL-Compatible Edition now supports the pgvector extension to store embeddings from machine learning (ML) models in your database and to perform efficient similarity searches. Embeddings are numerical representations (vectors) created from generative AI that capture the semantic meaning of text input into a large language model (LLM). pgvector can store and search embeddings from Amazon Bedrock, Amazon SageMaker, and more.

By using pgvector on Aurora PostgreSQL, you can simply set up, operate, and scale databases for your ML-enabled applications. The pgvector extension allows you to build ML capabilities into your e-commerce, media, health applications, and more to find similar items within a catalog. For example, a streaming service can use pgvector to provide a list of film recommendations similar to the one you just watched. Aurora machine learning enables you to add ML-based predictions to applications via the familiar SQL programming language, so you don't need to learn separate tools or have prior machine learning experience. The pgvector extension is available on Aurora PostgreSQL 15.3, 14.8, 13.11, 12.15 and higher.

If using pgvector is something you are looking at or interested in, make sure you read [Leverage pgvector and Amazon Aurora PostgreSQL for Natural Language Processing, Chatbots and Sentiment Analysis](https://aws-oss.beachgeek.co.uk/31n) where Shayon Sanyal walks you through a couple of typical use cases in depth. [hands on]

![overview of langchain using pgvector](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2023/07/13/DBBLOG-3334-image001.png)

**AWS Amplify**

Great to see improvements to the AWS Amplify JavaScript library that were announced last week, specifically reducing the bundle sizes for our Auth, Storage, Notifications, and Analytics categories. We've improved our codebase so that you get leaner bundles, resulting in faster load times and improved performance for your applications. You can benefit from these improvements by installing or updating to version 5.3.4 or beyond of the Amplify JavaScript library. This is the first in a series of enhancements aimed at reducing the bundle size for apps built with AWS Amplify JavaScript. A key focus for upcoming releases of the Amplify JavaScript library is further bundle size reductions and improved tree shaking capabilities. Stay tuned for more updates, as we work towards making AWS Amplify JavaScript the go-to solution for your app development needs.

Abdallah Shaban and Ashish Nanda have put together [AWS Amplify JavaScript Library Announces Leaner Bundles and Faster Load Times](https://aws-oss.beachgeek.co.uk/31k) that show you what these look like with some specific details on what those bundle size improvements are.

**Grafana**

Amazon Managed Grafana is a fully managed service for Grafana, a popular open-source analytics platform that enables you to query, visualise, and alert on your metrics, logs, and traces. You can now upgrade your existing workspaces from version 8.4 to 9.4. Version 9.4 includes several new features to further enhance your experience in Amazon Managed Grafana, such as: plugin enhancements to support Amazon CloudWatch cross-account querying, Amazon OpenSearch Serverless, querying multiple asset properties from AWS IoT Sitewise, query result reuse and async queries for Athena; Prometheus and Loki query builders that make it even easier to create and modify queries for your data sources; and service accounts that provide a secure and efficient way to automate tasks within your Grafana instance. 

**Open Data**

The AWS Open Data Sponsorship Program makes high-value, cloud-optimized datasets publicly available on AWS. A couple of weeks ago we added and updated more data sets, which you can read about in the post [36 new or updated datasets on the Registry of Open Data: AI analysis-ready datasets and more](https://aws-oss.beachgeek.co.uk/31m) where Erin Chu takes you through a quick tour of these thirty-six data sets.

### Videos of the week

**Running Dev Containers with DevPod**

It has been a while since I have reached into the rich repository of the Containers from the Couch, but this video takes a look at DevPod, an open source, un opinionated, client-side tool for running dev containers and managing their lifecycles. DevPod uses a provider model, like Terraform, and allows you to launch dev containers on all the major cloud providers, your local Docker daemon, and Kubernetes. And if there's not already a provider for your infrastructure, you can build one. Lukas Gentele and Rich Burroughs from Loft Labs join Lukonde Mwila from the Couch crew to talk about how DevPod compares to managed offerings like Codespaces and GitPod, and to walk us through a demo of how DevPod works. 

{{< youtube pV2ymHluPtE >}}

**Build on Open Source**

For those unfamiliar with this show, Build on Open Source is where we go over this newsletter and then invite special guests to dive deep into their open source project. Expect plenty of code, demos and hopefully laughs. We have put together a playlist so that you can easily access all (sixteen) of the episodes of the Build on Open Source show. [Build on Open Source playlist](https://aws-oss.beachgeek.co.uk/episodes).

We are currently planning the third series - if you have an open source project you want to talk about, get in touch and we might be able to feature your project in future episodes of Build on Open Source.

This newsletter will also now be appearing on the AWS Community Radio show, put together by my good chum Ric Harvey. Make sure you subscribe to his channel to keep up to date and be notified when new videos appear.

{{< youtube rmQZCr0EfL4 >}}

# Events for your diary

If you are planning any events in 2023, either virtual, in person, or hybrid, get in touch as I would love to share details of your event with readers. 

**Building Scalable Microservices with TiDB and AWS Lambda**
**AWS Offices in New York, July 24th, 10am - 2pm**

TiDB is an open-source New SQL database that supports Hybrid Transactional and Analytical Processing workloads. It is MySQL compatible and can provide horizontal scalability, strong consistency, and high availability. Join PingCAP and AWS for an in-person workshop where you’ll learn about TiDB Serverless and AWS Lambda. You’ll explore how to combine them to build scalable, highly-available microservices while generating real-time insights directly from raw application data.

You will need to register to save your place, so head over to [Building Scalable Microservices with TiDB and AWS Lambda](https://aws-oss.beachgeek.co.uk/30q) and find out more.

**Discover AWS' Cedar With its Creator and Community Leaders**
**Online, July 26th, 11:00 EST / 15:00 GMT**

If you are interested in Cedar, then make sure you check out this must attend online event where discussing AWS’ new open-source policy language and engine Cedar!
Learn more about its benefits, ecosystem, integrations, and this new breakthrough in the IAM space! Plenty of familiar faces including Mike Hicks, Or Weis, Daniel Aniszkiewicz, and Filip Grebowski will be covering the Cedar policy language and how it works, and you can expect plenty of demos.

Sign up and register your spot over at the [Discover AWS' Cedar With its Creator and Community Leaders](https://hello.permit.io/cedar?) page.

**RADIUSS AWS Tutorials: Learn how to use a modern HPC software stack**
**Online, throughout August 2023**

Check out this series of online tutorials happening throughout August demonstrating how to use several GPU-ready projects in the cloud and on premises. Follow along on your own EC2 instance (provided). No previous experience necessary. Lots of open source technologies are covered in this series, so if you are looking to get started in this space, check out the details on the information page, [Learn how to use a modern HPC software stack](https://aws-oss.beachgeek.co.uk/31h). Brenden Bouffler has also put together a great blog post, [Call for participation: RADIUSS Tutorial Series 2023](https://aws-oss.beachgeek.co.uk/31i) that dives deeper into some of these topics and provides further information.

**Building ML capabilities with PostgreSQL and pgvector extension**
**YouTube, 14th September 4pm UK time**

Generative AI and Large Language Models (LLMs) are powerful technologies for building applications with richer and more personalized user experiences. Application developers who use Amazon Aurora for PostgreSQL or Amazon RDS for PostgreSQL can use pgvector, an open-source extension for PostgreSQL, to harness the power of generative AI and LLMs for driving richer user experiences. Register now to learn more about this powerful technology.

Watch it [live on YouTube](https://aws-oss.beachgeek.co.uk/325).

**Build ML into your apps with PostgreSQL and the pgvector extension**
**YouTube, 21st September 4pm UK time**

This office hours session is a follow up for those who attended the fireside chat titled "Building ML capabilities into your apps with PostgreSQL and the open-source pgvector extension". Others are also welcome. Office hours attendees can ask questions related to this topic. Application developers who use Amazon Aurora for PostgreSQL or Amazon RDS for PostgreSQL can use pgvector, an open-source extension for PostgreSQL, to harness the power of generative AI and LLMs for driving richer user experiences. Join us to ask your questions and hear the answers to the most frequently asked questions about the pgvector extension for PostgreSQL.

Watch it [live on YouTube](https://aws-oss.beachgeek.co.uk/326).

**Open Source Summit, Europe**
**September 19th-21st, Bilboa Spain**

"Open Source Summit is the premier event for open source developers, technologists, and community leaders to collaborate, share information, solve problems, and gain knowledge, furthering open source innovation and ensuring a sustainable open source ecosystem. It is the gathering place for open-source code and community contributors." You will find AWS as well as myself at Open Source Summit this year, so come by the AWS booth and say hello - from the glimpses I have seen so far, it is going to be awesome! Find out more at the official site, [Open Source Summit Europe 2023](https://aws-oss.beachgeek.co.uk/31f).

**OpenSearchCon**
**Seattle, September 27-29, 2023**

Registration is now open source OpenSearchCon. Check out this post from Daryll Swager, [Registration for OpenSearchCon 2023 is now open!](https://aws-oss.beachgeek.co.uk/2zk) that provides you with what you can expect, and resources you need to help plan your trip.

**CDK Day, 2023**
**Online, 29th September 2023**

Back for the fourth instalment, this Community led event is a must attend for anyone working with infrastructure as code using the AWS Cloud Development Kit (CDK). It is intended to provide learning opportunities for all users of the CDK and related libraries. The CFP is open, so if you have some ideas for some talks then make sure you check that section out. Also, this year they are accepting talks in Espanol! Woohoo, love it!

Check more at the website, [CDK Day](https://aws-oss.beachgeek.co.uk/fr) 

**Open Source India**
**October 12-13th, NIMHANS Convention Center, Bengaluru**

One of the most important open source events in the region, Open Source India will be welcoming thousands of attendees all to discuss and learn about open source technologies. I will be there too, doing a talk so I would love to meet with any of you who are also planning on attending. Check out more details on their web page, [here](https://aws-oss.beachgeek.co.uk/31d).

**All Things Open**
**October, 15th-17th, Raleigh Convention Center, Raleigh, North Carolina**

I will be attending and speaking at All Things Open, looking at Apache Airflow as an container orchestrator. I will be there with a bunch of fellow AWS colleagues, and I hope to meet some of you there. Check us out at the AWS booth, where you will find me and the other AWS folk throughout the event. Check out the event and sessions/speakers at the official webpage for the event, [AllThingsOpen 2023](https://aws-oss.beachgeek.co.uk/31e)
 

**Cortex**
**Every other Thursday, next one 16th February**

The Cortex community call happens every two weeks on Thursday, alternating at 1200 UTC and 1700 UTC. You can check out the GitHub project for more details, go to the [Community Meetings](https://aws-oss.beachgeek.co.uk/2h5) section. The community calls keep a rolling doc of previous meetings, so you can catch up on the previous discussions. Check the [Cortex Community Meetings Notes](https://aws-oss.beachgeek.co.uk/2h6) for more info.

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)

### Stay in touch with open source at AWS

Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)