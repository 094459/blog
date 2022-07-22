---

title: 'AWS open source news and updates #121'
date: '2022-07-22'
tags : [ oss-newsletter, aws open source, OpenSearch, Spring Boot, Kotlin, Kubernetes, Cloudscape, Apache Kafka, Porting Assistant for .NET, Amazon Corretto, Amazon EMR, AWS Lambda Power Tools, ]

---

## July 22nd, 2022 - Instalment #121

Welcome to regular and new readers alike, to the AWS open source newsletter episode #121.

Am super excited about this weeks new projects, including a number of AWS CDK related projects so if you are a fan of AWS CDK then make sure you check them all out. We feature projects such as "openrolesanywhere", a proof of concept client for the recently released AWS IAM Roles Anywhere, "amazon-redshift-odbc-driver" an open source ODBC driver for Amazon Redshift, "spot-interruption-simulation" a very handy tool to help you test and simulate spot interuptions for your EC2 workloads, "magento-ecs-cdk" a quick way to deploy a scalable Magento environment, "using-rekognition-to-detect-sounds" a very interesting project that will help you hear sounds from your pictures (yes, you did not read that wrong!), and many other projects to check out.

We have blog posts on content covering OpenSearch, Spring Boot, Kotlin, Kubernetes, Cloudscape, Apache Kafka, Porting Assistant for .NET, Amazon Corretto, Amazon EMR, AWS Lambda Power Tools and more. This weeks featured videos include the kick off of the new AWS BuildOn series, which is an open source special, and we have more events for you to check out and reserve your spot for.

**Feedback**

At Amazon we work backwards from our customers, and one of the ways we do that is collecting data to help us know what is important and what we should focus on. Please could you [complete this simple](https://eventbox.dev/survey/8G7HRWY), anonymous survey. The first 25 will get an AWS $25 credit code.

### Celebrating open source contributors

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created. 

So thank you to the following open source heroes: Aiden Steel, Bob Tordella, Roy Ra, Rajit Paul, Franck Pachot, Matthew Tan, Philipp Klose, Tim Anderson, Darko Mesaroš, and Jacquie Grindrod

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution.*

#### Tools

**amazon-redshift-odbc-driver**

[amazon-redshift-odbc-driver](https://aws-oss.beachgeek.co.uk/1wk) the Amazon Redshift ODBC driver is now open source and available for the user community under the Apache-2.0 license. With this release, customers will gain enhanced visibility to the driver implementation and can contribute to its development. Users can browse the code for the ODBC driver on the relevant AWS GitHub repository, submit driver functionality enhancements through Github pull requests, and report issues for review.

We are also introducing a binary protocol support for Amazon Redshift. With binary protocol enabled, data from the Amazon Redshift cluster is sent to the ODBC driver without being converted to textual format, and is kept in binary format. The binary format provides an average of 30% decrease in data sent over the wire resulting in faster end-to-end query performance for queries returning large result-sets. For example, internal tests have shown end-to-end query times for queries returning over 100 columns and over one million rows have had a 43% speed-up. Binary protocol is enabled by default for all users using the latest ODBC driver, as well as the latest JDBC & Python drivers.

**openrolesanywhere**

[openrolesanywhere](https://aws-oss.beachgeek.co.uk/1wm) Aiden Steel has put together and open source proof-of-concept client for the recently released AWS IAM Roles Anywhere. Aiden has put together this blog post, [openrolesanywhere - an IAM Roles Anywhere client](https://aws-oss.beachgeek.co.uk/1wn) to accompany this project, so make sure you read it to get the most out of the code.

**spot-interruption-simulation**

[spot-interruption-simulation](https://aws-oss.beachgeek.co.uk/1wp) this repository has sample that provides end to end automation of EC2 Spot Interruption simulation with application availability testing during Spot interruption. This tool will be super handy for a number of different use cases, from understanding the behaviour of your applications and the applicability of EC2 Spot instance types, to how you can use this together with the Fault Injection Service (FIS) to test different resilience scenarios.

![architecture of spot interuption](https://github.com/aws-samples/spot-interruption-simulation/blob/main/architecture.png?raw=true)

**cdk-backup-plan**

[cdk-backup-plan](https://aws-oss.beachgeek.co.uk/1wt) this repo provides an easy to use reusable CDK construct to create Backup Plans using AWS Backups. It allows to indicate how frequently and what resources to backup.

**aws-cdk-lambda-layer-builder**

[aws-cdk-lambda-layer-builder](https://aws-oss.beachgeek.co.uk/1wv) Amazon Lambda functions often require extra modules which can be packaged in an Amazon Lambda Layer. The Layer is then attached to the Lambda to make the packaged module easily usable in the function code. AWS CDK does not have a simple, production ready solution to create a Lambda Layer. This repo is a collection of AWS CDK constructs to build Python Lambda Layers with minimum requirements on the user side, e.g. no bash or zip cli has to be available on the user's machine.

**cdk-testable-infrastructure**

[cdk-testable-infrastructure](https://aws-oss.beachgeek.co.uk/1wu) Reliable integration testing gives developers the confidence needed to promote the changes from testing to production environments. But how should you think about implementing tests for your applications? This repo provides some examples of how you can add integration tests to your infrastructure deployment code, and provides a number (three) patterns for you to explore and then think about what might work for you.

### Demos, Samples, Solutions and Workshops

**magento-ecs-cdk**

[magento-ecs-cdk](https://aws-oss.beachgeek.co.uk/1wq) Magento is a very popular open-source e-commerce platform written in PHP. This repository consist of a sample project providing infrastructure as code based on AWS Cloud Development Kit (AWS CDK) in order to run open-source e-commerce Magento software platform. The CDK application will deploy highly-available and scalable Magento platform by leveraging Amazon Elastic Container Services (Amazon ECS) and several additional AWS services.

![overview of magento on aws ecs architecture](https://github.com/aws-samples/magento-ecs-cdk/blob/main/doc/images/magento-archi.png?raw=true)

**using-rekognition-to-detect-sounds**

[using-rekognition-to-detect-sounds](https://aws-oss.beachgeek.co.uk/1wr) this looks like a very interesting sample project. This project demonstrates the use of Rekognition to detect audio events when used in combination with spectrographic analysis. The project has two main aspects: generating training data (spectrograms) from audio samples of background noise and alarms, and an inference pipeline to use the model to detect if a smoke alarm sound is present in an audio file.

**aws-cdk-web-app-example**

[aws-cdk-web-app-example](https://aws-oss.beachgeek.co.uk/1ws) This is an example of how to build a resilient web application with just 30 lines lines of TypeScript code by using the AWS CDK. It consists of one Amazon Virtual Private Cloud (VPC) with private and public subnets in multiple Availability Zones, in which an Application Load Balancer and an Amazon EC2 Auto Scaling Group are deployed. The Application Load Balancer accepts requests via HTTP (port 80) and forwards them to the instances of the Auto Scaling Group. The Auto Scaling Group is using a Launch Configuration that contains a User Data script to install the Apache HTTP Server and serve a static HTML page.

**amazon-athena-execution-parameters-blog**

[amazon-athena-execution-parameters-blog](https://aws-oss.beachgeek.co.uk/1ww) this repo contains everything you need to deploy a sample web application to demonstrate new ability to pass executions parameters to Amazon Athena StartQueryExecution API. This sample application uses a number of AWS services to demonstrate a Data-as-a-Service (DaaS) architecture pattern that uses Amazon Athena to query the Amazon.com customer reviews dataset.

![architecture of data as a service](https://github.com/aws-samples/amazon-athena-execution-parameters-blog/blob/main/ParameterizedQueriesDiagram.png?raw=true)

### AWS and Community blog posts

**Cloudscape**

This week it was great to see the launch of [Cloudscape](https://aws-oss.beachgeek.co.uk/1wb), a new open source React design system for web applications, released under the Apache 2.0 license. Tim Anderson wrote about this in his post, [AWS open sources Cloudscape Design System](https://aws-oss.beachgeek.co.uk/1wc).

![demo of cloudscape diagram](https://devclass.com/wp-content/uploads/2022/07/servicedash.jpg)

From the official news launch, [Announcing Cloudscape Design System, an open source solution for building intuitive web applications](https://aws-oss.beachgeek.co.uk/1wd)

>  Cloudscape Design System is an open source solution for building intuitive, engaging, and inclusive user experiences at scale. Cloudscape consists of an extensive set of guidelines to create web applications, along with the design resources and front-end components to streamline implementation.
>Cloudscape was built for and is used by AWS products and services. We created it in 2016 to improve the user experience across AWS web applications, and also to help teams implement those applications faster. Since then, we have continued enhancing the system based on customer feedback and research. If you’ve ever used the AWS Management Console, you’ve seen Cloudscape in action.
>
>We are releasing Cloudscape as open source so that anyone building cloud products can benefit from our design system, and also join a community of designers and developers who continually improve it. Whether you’re building a product that extends the AWS Management Console, designing a user interface for a hybrid cloud management system, or setting up an on-premises solution that uses AWS, Cloudscape offers a solid base of 60+ components, 30+ pattern guidelines, and 20+ demos to make your work easier. To customize your user experience, Cloudscape offers theming, dark mode, and content density modes.

Head on over to the [documentation site](https://aws-oss.beachgeek.co.uk/1wf) to learn more about the features, how to use and start building with Cloudscape, as well as checking out some demo code available for you to help you get started. There is really some great stuff in this documentation site, so make sure you do not miss this.

**Apache Kafka**

In the post, [Creating a serverless Apache Kafka publisher using AWS Lambda](https://aws-oss.beachgeek.co.uk/1wh) Philipp Klose shares a general integration pattern between AWS Lambda and Apache Kafka, and then walks you through how to create of this using Apache Managed Streaming for Apache Kafka (MSK), using AWS CDK to help you deploy this easily so you can try this out for yourself. [hands on]

![architecture of apache kafka solution](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2022/06/21/kafka2.png)

**Amazon EMR**

EMR on EKS facilitates running Spark jobs on Kubernetes to achieve very fast and cost-efficient Spark operations.
A contender for this weeks longest blog title, [Stream Amazon EMR on EKS logs to third-party providers like Splunk, Amazon OpenSearch Service, or other log aggregators](https://aws-oss.beachgeek.co.uk/1wi) Matthew Tan shares how a solution using pod templates and Fluent Bit, that will help you to To log all these operations in the same lifecycle of the Spark jobs. [hands on]

![architecture for amazon emr on eks logging](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2022/07/05/emr_eks_logforwarding_images_1.png)

**Other posts you might like from the past week**

* [How (and Why) to Build a Welcoming Open Source Community](https://aws-oss.beachgeek.co.uk/1wa) my colleague Libby provides some good advice for those looking to nurture communities around their open source projects 
* [How NRCan used an AWS open source solution to complete a PBMM evidence package in 60 days](https://aws-oss.beachgeek.co.uk/1wg) is a great case study (in English and French) that looks at how open source is supporting increased agility and speed of delivery of new solutions
* [Which Way is the Compass Pointing?](https://aws-oss.beachgeek.co.uk/1wl) nice post from the OpenSearch blog that shows how they are taking a data driven approach (powered by OpenSearch) to manage feedback and understand which documentation to create

### AWS Community Builder and Heroes picks

The AWS Community Builder and Heroes community creates a lot of great content over at [dev.to/heroes](https://dev.to/aws-heroes) and [dev.to/builders](https://dev.to/aws-builders). Here is a selection of the posts that I enjoyed this week.

* [Where are those CloudTrail IP addresses coming from?](https://aws-oss.beachgeek.co.uk/1wo) Bob Tordella shows you how you can use Steampipe with the AWS and ipstack plugins to enrich your CloudTrail events with location information [hands on]
* [Using DynamoDB on Spring Boot (feat.Kotlin)](https://aws-oss.beachgeek.co.uk/1w7) Roy Ra shows you how to use Amazon DynamoDB with Spring Boot application made with Kotlin [hands on]
* [Deploy your application on Kubernetes (Amazon EKS) using AWS Serverless (Codebuild)](https://aws-oss.beachgeek.co.uk/1w8) Rajit Paul takes a look at how you can use AWS CodeBuild to deploy your Kubernetes environments, something I have been playing around with myself (expect a blog soon)
* [IoT benchmark on Distributed SQL from MaibornWolff on Amazon EKS](https://aws-oss.beachgeek.co.uk/1w9) Franck Pachot shares his journey of deploying the distributed SQL benchmark from MaibornWolff on Amazon EKS

### Quick updates

**AWS Lambda Powertools for TypeScript**

Last week saw the general availability of AWS Lambda Powertools for TypeScript, an open-source developer library to help you incorporate Well-Architected Serverless best practices into your Lambda function code as early and as fast as possible. In this release, Lambda Powertools for TypeScript focuses on three observability features: distributed tracing (Tracer), structured logging (Logger), and asynchronous business and application metrics (Metrics). Developers can use Lambda Powertools for TypeScript to adopt these practices in mere seconds.

**Amazon Corretto**

This week we announced quarterly security and critical updates for Amazon Corretto Long-Term Supported (LTS) versions of OpenJDK. Corretto 18.0.2, 17.0.4, 11.0.16, 8u342 are now available for download. Amazon Corretto is a no-cost, multi-platform, production-ready distribution of OpenJDK. Check out the [Amazon Corretto July, 2022 quarterly updates](https://aws-oss.beachgeek.co.uk/1wj) for more info and links to the full list of updates.

**Porting Assistant for .NET**

Porting Assistant for .NET is an open source analysis tool that reduces the manual effort and guesswork involved in porting .NET Framework applications to .NET Core 3.1, .NET 5, or .NET 6, helping customers move to Linux faster. It identifies incompatibilities, generates an assessment report with known replacement suggestions, and assists with porting.

Porting Assistant for .NET now supports assessment and porting of legacy .NET Framework applications written in VB.NET language. With this release, Porting Assistant will translate VB.NET class libraries, web APIs, and console applications to .NET Core 3.1, .NET 5, or .NET 6 to simplify the modernisation of legacy .NET Framework applications written in VB.NET . Developers can use the Porting Assistant for .NET standalone tool or Porting Assistant for .NET Visual Studio IDE extension to modernise their legacy VB.NET applications. Support for VB.NET is added in addition to existing support for assessment and porting of C# based .NET Framework applications.

**Amazon EMR**

Announced last week were a couple of new features that help enforce access controls with Amazon EMR on EC2 clusters (EMR Clusters). These features are supported with jobs that are submitted to the cluster using the EMR Steps API. First is Runtime Role with EMR Steps. A Runtime Role is an AWS Identity and Access Management (IAM) role that you associate with an EMR Step. An EMR Step uses this role to access AWS resources. The second is integration with AWS Lake Formation to apply table and column-level access controls for Apache Spark and Apache Hive jobs with EMR Steps.

Previously, all jobs running on an EMR cluster used the IAM role associated with the EMR cluster’s EC2 Instances to access resources. This role is called the EMR EC2 Instance Profile. For example, if a Spark job and Hive job running on the same cluster needed to access different S3 buckets, then the Instance Profile must allow access to both the buckets. With Runtime Role for EMR Steps, you specify a different IAM role for the Spark and the Hive job, thus scoping down access at a job level. This allows you to simplify access controls on a single EMR cluster that is shared between multiple tenants, wherein each tenant is isolated using IAM roles.

In addition, you can use AWS Lake Formation to apply Table and Column-level permissions with Apache Spark and Apache Hive jobs submitted as EMR Steps. AWS Lake Formation is a fully managed service that makes it easy to build, secure, and manage data lakes. AWS Lake Formation enables you to apply fine-grained access control to data stored in data lakes, through a simple grant or revoke mechanism, much like a relational database management system (RDBMS). With this feature, table and column-level permissions defined in AWS Lake Formation for an IAM Role are seamlessly enforced with Apache Hive and Apache Spark jobs submitted as EMR Steps. This allows you to further simplify access controls, and provide each job with access to specific Databases, Tables, and Columns.

### Videos of the week

**OpenSearch**

Check out the new [OpenSearch You Tube channel](https://aws-oss.beachgeek.co.uk/1w6), for all your OpenSearch content you need.

**BuildOn AWS Open Source**

If you missed the opening show of the new AWS BuildOn AWS series, my good friends Darko and Jacqui walk you through some nice open source projects as well as talk all things open source with David Nalley, who heads up open source strategy and marketing at AWS.

{{< youtube S7xuTViq2r0 >}}


### Events for your diary

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)

**Introduction to Amazon Managed Workflows for Apache Airflow**
**July 28th, 8:00 am - 1:15 pm PT**

Managed Workflows for Apache Airflow (MWAA) is a managed service from AWS that makes it super easy to get started with one of my favourite (and hottest) open source projects, Apache Airflow. If you want to get hands on and learn more about MWAA, then sign up at [Solutions-Focused Immersion Day:Introduction to Amazon Managed Workflows for Apache Airflow](https://aws-oss.beachgeek.co.uk/1we) (it is free)

**Just-in-time Worker Nodes with Karpenter**
**5th August, 2pm IST**

Karpenter helps improve your application availability and cluster efficiency by rapidly launching right-sized compute resources in response to changing application load. In this webinar with my colleague Rohini Goankar, you will get an overview of Karpenter and it’s features, see a demonstration of how Karpenter simplifies Kubernetes infrastructure with the right nodes at the right time, and there will be practical demos on how to use Karpenter.

Find out more and register via this link, [An Open-Source High-Performance Kubernetes Cluster Autoscaler](https://aws-oss.beachgeek.co.uk/1w5)

**Digital Payments Architecture and Implementation with AWS Open Source Databases**
**August 18th**

Check out this Webinar on how to use open source databases to build a digital payments solution. You can view it live direct on [YouTube here](https://www.youtube.com/watch?v=kbjtLPYToaI)

**OpenSearchCon 2022**
**Sept 21st, 2022 Seattle**

Come to the first annual OpenSearchCon!

This day-long conference will be packed with presenters who build and innovate with OpenSearch. It doesn’t matter if you’re just getting started on your OpenSearch journey, running giant clusters, or contributing tons of code; the event is for everyone. Join us to celebrate the progress and look into the future of the project. Admission is free, and registration will be open in the next few weeks. All you will need to do is sign up, and get to Seattle!

Check out the full details, including signing up and location, at the [meetup page here](https://aws-oss.beachgeek.co.uk/1n1).


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)

