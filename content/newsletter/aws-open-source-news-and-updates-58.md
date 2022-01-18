---
title: 'AWS open source news and updates #58'
date: '2021-03-01'
tags : [ oss-newsletter ]
---
## March 1st, 2021 - Instalment #58

Newsletter #58.

This week we have posts covering some of my favourite topics, AWS Graviton and AWS CDK, we have some new events to check out, more great videos from the Containers on the couch folk, as well as the usual round up of new open source projects, AWS and community related posts and quick updates.  

Before we crack on, why not start by reading this post, [The real value of open source in the cloud](https://aws-oss.beachgeek.co.uk/7t) that Matt Asay wrote last week that talks about the freedom and choice that open source provides, whether that is in the Cloud or not. Matt also shares some data points from a recent survey we commissioned. Read the post to get to the good stuff and I will just leave you with this graph to tempt you in.

![graph](https://images.idgesg.net/images/article/2021/02/cloud-provider-leadership-aws-100877870-large.jpg)

### Looking for a fresh open source challenge?

**Terraform**

Hashicorp is looking to hire a new steward for the AWS Terraform Provider. This is a wonderful team that builds a wonderful product. This role interacts with folks at AWS as we have a strategic relationship and often work together to bring new features to market.

**PHP**

If that does not take your fancy, then what about working on PHP at AWS? The AWS SDK for PHP team is hiring. They are looking to build the next major version of the SDK that will feature strong typing, codegen, and lots of other goodies.

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Vu Dao, Tyler Lynch, Matt Asay, Richard Elberger, Andrew (Qingjie) Ren,  Viji Sarathy, Krishnakumar Rengarajan, Usman Umar, Christian Weber, Sunil Ramachandra, Imaya Kumar Jagannathan, Mark Schreiber, Ankit Malhotra, Matt Herson, Brandon Lindauer, Kim Wendt, Mario Monello, Alolita Sharma, Nizar Tyrewalla, Zoe Wang, Eric Smalling, Jan Bauer, Jim Mlodgenski, Andy Katz, Justin Lam, Yann Léger, Alisdair Broshar, Steven Staley, Holt Calder, Greg Cockburn, Jonathan Rau, Max Brennerm, Jake Partusch and Jan-Christoph Küster.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

**aws-quota-checker**

[aws-quota-checker](https://aws-oss.beachgeek.co.uk/8i) a new open source project from Max Brennerm that is a tool that helps keeping track of your AWS quota utilisation. It'll determine the limits of your AWS account and compare them to the number of current resources. This is going to be super useful, I know I have been caught out by this before - yes I am looking at you VPC!

![demo](https://raw.githubusercontent.com/brennerm/aws-quota-checker/master/img/example.png)

**serverlessui**

[serverlessui](https://aws-oss.beachgeek.co.uk/8j) Jake Partusch has put together this new open source project that provides you a command-line utility for deploying serverless applications to AWS. Complete with custom domains, deploy previews, TypeScript support, and more. Detailed documentation with examples, why not give this a go and provide Jake feedback.

**serverless-url-shortener**

[serverless-url-shortener](https://aws-oss.beachgeek.co.uk/8k) this open source from from Owen Morgan is a fully serverless project to help you create a tool to shorten your urls. Read the detailed README.md to find out the full feature set (it does more than just the basics!). There is also a nice blog post to help you get up and running from Vu Dao, [Shorten Long URL Using CDK And Serverless](https://aws-oss.beachgeek.co.uk/8l)

![arch](https://res.cloudinary.com/practicaldev/image/fetch/s--37bSXy81--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://cdn.hashnode.com/res/hashnode/image/upload/v1612715356287/xIxqONMut.png)

**awsrm**

[awsrm](https://aws-oss.beachgeek.co.uk/8m) Jan-Christoph Küster has put together this open source project following on from the ideals of unix (do one thing, do that one thing well) that is a remove command for AWS resources. This is going to be a really useful tool - I used it over the weekend to do some housecleaning of my demo account and it worked really well. I installed the corresponding awsls tool (again from Jan) as they compliment each other. Jan provides a disclaimer at the bottom - this tool will delete resources, so make sure you know what you are doing before you start deleting things. 

**aws asset collection gist**

[aws asset collection gist](https://aws-oss.beachgeek.co.uk/8o) not so much a project but a gist shared by Jonathan Rau that provides a mechanism to retrieve all AWS Accounts from AWS Organizations and get all opted-in Regions from the EC2 DescribeRegions API and provide them to STS and Boto3 Sessions to create multiple thread-safe Boto3 Clients for the purpose of parallelized asset collection in your entire AWS Organization. Sounds useful, so check it out if you need to do something similar.

**amazon-lookout-for-vision-python-sdk**

amazon-lookout-for-vision-python-sdk released last week, the Amazon Lookout for Vision Python SDK is an open-source library that allows data scientists and software developers to easily build, train and deploy computer vision (CV) models using Amazon Lookout for Vision.

**aws-media-asset-preparation-system**

[aws-media-asset-preparation-system](https://aws-oss.beachgeek.co.uk/84) is a new open source project (MAPS for short) that facilitates the preparation and movement of media assets across AWS storage mediums such as Amazon S3 and Amazon FSx. Matt Herson, Brandon Lindauer, Kim Wendt, and Mario Monello have collaborated on this blog post, [Introducing the AWS Media Asset Preparation System](https://aws-oss.beachgeek.co.uk/83) to help you get started.

### Community open source posts

**AWS Graviton2**

[Performance & Price Comparison](https://aws-oss.beachgeek.co.uk/8n) great post from Greg Cockburn, which after checking out his blog turns out that it is one of a number of blog posts he has put together to compare the price/performance of running workloads against different AWS instance types. Another must read post this week.

**Smart Sourdough**

[Precision Sourdough: A Smart Lid for Your Starter](https://aws-oss.beachgeek.co.uk/8c) this post from Justin Lam combines two of the things that I most like: sourdough bread and aws. This is a complete makers delight, from creating and designing of the electronics components, 3D printing the components, some nice Mcgyver style hacks, a steampunk reference and of course, alga-bread (not my joke, Justin's) and of course all the integration with the Cloud. This one deserves to be consumed slowly with a cup of your favourite beverage. Nice work Justin.

![arch](https://www.justinmklam.com/imgs/blog-imgs/sourdough-starter-monitor-lid/aws-iot.png)

**Firecracker**

[10 Reasons Why We Love Firecracker MicroVMs](https://aws-oss.beachgeek.co.uk/8d) Yann Léger and Alisdair Broshar break down their ten reasons why you should be taking a look at what Firecracker can do for you on the Koyeb blog. The Koyeb Serverless Platform natively launches their serverless Apps in Firecracker MicroVMs to make sure workloads perform faster and more efficiently. It is great to see other companies making use of these open source technologies to provide services for their customers like this.

**Serverless**

[Exploring An OpenAPI/Swagger First Approach to Serverless Development on AWS](https://aws-oss.beachgeek.co.uk/8e) Steven Staley has put together this really nice post on why you consider declaring your serverless APIs with OpenAPI instead of using the Severless/SAM config options. Developers working with serverless and using tools such as API Gateway and AWS SAM may already be used to declaring APIs via a particular format, and Steven takes a look at how there is an alternative approach, using OpenAPI. OpenAPI (or the API specification formerly known as Swagger) provides tooling for generating APIs based on the OpenAPI spec, and in this post Steven explores how this works and then why you should care. Really nice post.

**Tableau**

[Introducing the Amazon SageMaker Integration for Tableau](https://aws-oss.beachgeek.co.uk/8f) Holt Calder with a post and video tutorial on how to use the open source [Amazon SageMaker Integration for Tableau](https://aws-oss.beachgeek.co.uk/8g) which uses the [Tableau’s Analytics Extension Framework](https://aws-oss.beachgeek.co.uk/8h), to simplify how you can integrate Amazon SageMaker within your Tableau applications. If you are a Tableau user, a must read post.

![arch](https://interworks.com/wp-content/uploads/2021/02/Sage1.jpg)

### AWS open source posts

**AWS Graviton2**

Hot off the press from Tyler Lynch we have news that as part of Graviton2 adoption/enablement, the Auto Scaling team recently released a feature that allows customers to use multiple launch templates in a mixed instance policy. The feature is named **Launch Template Overrides**. This feature supports using both Graviton2 and x86 based Amazon EC2 instances in the same Auto Scaling group with different AMIs. This allows customers to introduce Graviton2 based instances as part of a multiple instance type strategy.

Additionally, this feature could be applied to fleets who have different configurations needed for different instance types. Variability such as disk sizes, networking configurations, placement groups, and tagging can now be accomplished in the same Auto Scaling group. Customers with large fleets and HPC workloads will be able to use the Launch Template Override feature.

The AWS Provider for Terraform incorporates this feature as of [3.33.0](https://aws-oss.beachgeek.co.uk/7q) and you can check out the docs, [Specifying a different launch template for an instance type](https://aws-oss.beachgeek.co.uk/7r)

Following that post we have Mark Schreiber and Ankit Malhotra write in the AWS Public Sector blog, [A generalized approach to benchmarking genomics workloads in the cloud: Running the BWA read aligner on Graviton2](https://aws-oss.beachgeek.co.uk/85). Burrow-Wheeler Aligner (BWA) is an open source project for mapping DNA sequences against a large reference genome, such as the human genome, that consists of a number of algorithms. As it is open source, this post shows how they re-compiled the project to run on AWS Graviton2 and then performed some tests to see how it performed to evaluate its cost effectiveness. As for all these kinds of posts, I do not want to reveal the punchline - you will have to dive in. Well worth a read.

![graph](https://d2908q01vomqb2.cloudfront.net/9e6a55b6b4563e652a23be9d623ca5055c356940/2021/02/23/Figure-5-Cost-efficiency-by-optimization-type.jpg)

**AWS CDK**

A couple of good posts this week covering one of my favourite open source projects at AWS. First up we have Krishnakumar Rengarajan and Usman Umar with a post that I have been waiting to share for a while. In [Developing enterprise application patterns with the AWS CDK](https://aws-oss.beachgeek.co.uk/2b) they share with you how you can define IaC patterns and blueprints that can help organisations with strict governance, compliance or quality control rules, so that they can be easily consumed and used by the organisations builders.

Following that we have Christian Weber with [CDK Corner February 2021](https://aws-oss.beachgeek.co.uk/81) with a round up of all the latest news and updates within the AWS CDK community, including new updates/features and a shout out to the contributors who have made their pull requests merged into the project. Christian also reminds us that the community driven CDK Day event (see Events above) is looming fast - you can register to attend and perhaps if you have been using it and would like to share your journey/story/use case, why not submit a session via the CFP.

**Spring Boot**

[Deploy a Spring Boot application on a multi-architecture Amazon EKS cluster](https://aws-oss.beachgeek.co.uk/7z) Andrew (Qingjie) Ren follows up the previous post with another AWS Graviton2 related post, this time focused around cost optimisation and using different instance families (from AMD, ARM and Intel) as well as purchase options to optimise your workloads. This post walks you through how you can think and approach this using a sample Spring Boot app, using AWS CDK to provision all the resources. A really good post to understand the potential and choice this provides customers.

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2021/02/23/image-2021-02-23T130240.039.png)

Source code provided within the post, so dive right in.

**GraalVM**

[GraalVM Native Image Support in the AWS SDK for Java 2.x](https://aws-oss.beachgeek.co.uk/87) Zoe Wang with a quick post announcing that AWS SDK for Java 2.x (version 2.16.1 or later) now has out-of-the-box support for GraalVM Native Image compilation. GraalVM is a universal virtual machine that supports JVM-based languages (e.g. Java, Scala, Kotlin), dynamic languages (e.g. Python, JavaScript), and LLVM-based languages (e.g. C, C++). Zoe walks you through the benefits of using native image compiled of applications using the AWS SDK for Java, and provides links to the source code too.

**TensorFlow**

[Using container images to run TensorFlow models in AWS Lambda](https://aws-oss.beachgeek.co.uk/88) Jan Bauer with a new post that shows you how to use any TensorFlow model with Lambda for scalable inferences in production with up to 10 GB of memory. This allows you to use ML models in Lambda functions up to a few gigabytes, and in this instance using a TensorFlow-Keras pre-trained ResNet50 for image classification. If you want to understand more about how to deploy your machine learning models via AWS Lambda, this is the post for you.

![arch](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2021/02/01/ML-2181-2-WHITE.png)

**PostgreSQL**

[Designing high-performance time series data tables on Amazon RDS for PostgreSQL](https://aws-oss.beachgeek.co.uk/89) Jim Mlodgenski and Andy Katz take a look at how you can use native PostgreSQL functionality to work with time series data. With just simple planning on the data model design, a moderately sized Amazon RDS for PostgreSQL or Amazon Aurora PostgreSQL instance can easily ingest over 1 million metrics per second while still leaving resources available to query the data. If you are already working with time series data or have a looming project, make sure you do your homework and read this post.

![graph](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2021/02/22/DBBLOG-1473-5.jpg)

**Prometheus**

[Autoscaling Amazon ECS services based on custom CloudWatch and Prometheus metrics](https://aws-oss.beachgeek.co.uk/80)  Viji Sarathy talks about how you can use a couple of metrics collection strategies in conjunction with Application Auto Scaling to scale services deployed to Amazon ECS based on custom metrics data. Whilst you have been able to do this with CloudWatch metrics, the recent announcement and general availability of Container Insights Prometheus Metrics Monitoring for Amazon ECS, means customers can now automate the discovery and collection of custom Prometheus metrics from their containerised applications. In this post, Viji will show you how you can do both. 

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2021/02/17/ECS-Autoscaling-Arch.png)

**Grafana**

[Integrating identity providers, such as OneLogin, Ping Identity, Okta, and Azure AD, to SSO into AWS Managed Service for Grafana](https://aws-oss.beachgeek.co.uk/82) looking to win this weeks longest blog post title we have Sunil Ramachandra and Imaya Kumar Jagannathan who show you how you can use a number of different identity providers to enable single sign on with the AWS Managed Service for Grafana (AMG). Folks may be aware that I have written about and shared lots of AWS SSO related posts in the past, so this one was a favourite this week. Definitely check this post out.

![signonflow](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/02/17/suramac_grafana_f01_new.png)

**.NET & OpenTelemtry**

[AWS Distro for OpenTelemetry adds .NET tracing support](https://aws-oss.beachgeek.co.uk/86) Alolita Sharma and Nizar Tyrewalla with a short post on how AWS Distro for OpenTelemetry (ADOT) now support .NET, which now means you can add tracing to your .NET applications using open source OpenTelemetry’s .NET API and SDK.

**FreeRTOS**

A curated list from within a curated list. Don't worry though, this post from Richard Elberger contains the hottest posts and updates from the world of FreeRTOS.org. As there is so much great content, why not check out his list of his current favourites. I have covered some of these in the past, but there are plenty of new ones too. Without further ado, dive right into [Top FreeRTOS articles in 2020](https://aws-oss.beachgeek.co.uk/7y)


### Videos of the week

What is rapidly becoming a regular Containers from the Couch section, this week we have a couple of videos from last week where they invited Eric Smalling from Snyk to talk about how you can secure your containers, in your CI/CD pipelines and your EKS Clusters.

In this vide, Eric walks you through security testing of your dockerized applications

{% youtube HLEw7B0I5v4 %}

And following that, Eric takes a look at how to secure your EKS clusters with the Snyk controller to identify image and/or configuration vulnerabilities.

{% youtube 7f1_WCDUU78 %}

### Quick updates

**PostgreSQL**

A couple of quick updates this week.

* **Amazon RDS for PostgreSQL now supports major version 13.** PostgreSQL 13 includes improved functionality and performance from new features and performance from new features and enhancements such as de-duplication of B-tree index entries, improved performance for queries that use partitioned tables, incremental sorting to accelerate data sorts, parallel processing of indexes with the VACUUM command, more ways to monitor activity within a PostgreSQL database, new security capabilities, and more. This release also adds support for bool_plperl, which simplifies writing Perl procedures. With PostgreSQL 13 on Amazon RDS for PostgreSQL you can create time series data tables with improved data ingestion rates of several hundred thousands of metrics per second for use cases such as storing DevOps metrics or tracking business metrics (e.g., daily sales).
* **Patches 1.8.1 / 2.6.2 / 3.3.2 are now available for customers using Amazon Aurora PostgreSQL.** For detailed release notes visit our version documentation. You can apply the new patch version in the AWS Management Console, via the AWS CLI, or via the RDS API.

**MariaDB**

* AWS Database Migration Service (AWS DMS) has expanded functionality by adding support for MariaDB version 10.5. Using AWS DMS, you can now perform live migrations from any AWS DMS supported sources to MariaDB 10.5 databases, and from MariaDB 10.5 databases to any [AWS DMS supported targets](https://docs.aws.amazon.com/dms/latest/userguide/CHAP_Target.html).  

**Elasticsearch**

* Amazon Elasticsearch Service now supports Reporting, a new feature that enables Kibana users to generate and download reports. They can now generate reports directly from the Dashboard, Visualise and Discover panels, and export them to PDF, CSV and PNG file formats. Reporting is powered by Open Distro for Elasticsearch, an Apache 2.0-licensed distribution of Elasticsearch and is supported on all Amazon Elasticsearch Service domains running Elasticsearch 7.9 or greater.
* Amazon Elasticsearch Service introduces index rollups that lets you summarise high granularity data and preserve feature-rich aggregations over large data sets for analytics while reducing the storage costs. As time-series data grows to considerable sizes over time, it can slow down your aggregations and you may incur a substantial storage cost. Also, the usefulness of granular data reduces with time. Rollups lets you create a new index containing only relevant fields aggregated into coarser time buckets. With rolled up indexes, users can store up to years of data with reduced storage costs. Users can initiate rollups on the data, either on-demand or through scheduled runs at regular intervals. Rollups is also integrated with Index Management enabling users to automatically move the data from hot node to warm storage, like UltraWarm, as their need for high granularity decreases. The rollups feature is powered by Open Distro for Elasticsearch, an Apache 2.0-licensed distribution of Elasticsearch.

### Events for your diary

**AWS Community Summit**
**March 4th, 2PM GMT**

A number of talks from probably the best run and produced community meetup. Join a host of great speakers, including of course open source content from Matt Johnson from Bridgecrew will be talking about [Automating security in your infrastructure with open source](https://aws-oss.beachgeek.co.uk/7v). Check out and sign up for the event [here](https://aws-oss.beachgeek.co.uk/7w).

**Cloud Data Lake Dev Day Live Workshop**
**March 11th, 9:00am PST**

In this live workshop, we’ll cover the best practices for organizations to use with powerful open source technologies so you can build and extend your AWS investments and make your data lake analytics-ready. You’ll learn about the advantages of cloud-based data lakes in terms of security and cost. How to enable SQL analysts to easily access data in your data lake for reporting and visualization.

Find out more and register via [this link](https://aws-oss.beachgeek.co.uk/8a)

**Kickstart Your Kubernetes Projects With Amazon EKS-D and KubeOne**
**March 18, 5:00PM CET**

In this session, Michael Hausenblas (AWS) and Mario Fahland (Kubermatic) will take a closer look at EKS-D and dive into how to set up your very own cluster running EKS-D with KubeOne – our open source and infrastructure agnostic Kubernetes cluster lifecycle management tool. We will also have a peek into the future and show how to bring EKS-D to your data centres so you can use the very same tooling on-premises and in the cloud.

Register [here](https://aws-oss.beachgeek.co.uk/7u).

**CDK Day**
**April 30th**

Announced this week was the second [CDK Day](https://sessionize.com/cdkday/), which will be on April 30th. Check out [the web page](https://sessionize.com/cdkday/) to find out more about the first CDK Day, which was incredible. This second event promises to be even better. The CFP is open until the 19th of March. Check out this supporting blog post, [CDK Day CFP Is Open!!!!](https://aws-oss.beachgeek.co.uk/4v) from Matt as to what to expect and what they are looking for when it comes to sessions.

**Cloud Native Rust Day**
**May 3rd**

Rust is a language empowering everyone to build secure, reliable, and efficient software. Rust is becoming more widely used in cloud native, powering everything from lightning-fast service meshes and powerful developer tools to internet-scale distributed databases.

Come explore what makes Rust a fantastic choice for new cloud native development, and learn about how the community uses Rust today. Find out [more and register here](https://aws-oss.beachgeek.co.uk/5y).


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen).
