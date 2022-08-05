---

title: 'AWS open source news and updates #123'
date: '2022-08-05'
tags : [ oss-newsletter, aws open source, Firecracker, AWS Lambda Power Tools, OpenSearch, Flutter, Kyber, Babelfish for Aurora PostgreSQL, MySQL, AWS libcrypto, Apache TinkerPop, PostgreSQL, ROSA, OpenShift, Kubernetes, CDKTF, dbt]

---

## August, 5th, 2022 - Instalment #123

**Welcome**

Welcome to the AWS open source newsletter episode #123.

I sometimes speak with builders who are experienced developers but perhaps new to open source. A common question I get asked is what the impact of them working on open source might be on their careers. Whilst it is never a guarantee, open source can be a great career accelerator. I was reminded of that last week when reading the excellent post from Ran Isenberg, who shared his experience in his post [How One Open-Source Code Donation Got Me Promoted](https://aws-oss.beachgeek.co.uk/1xv). I would encourage you all to read his account as I am sure you will all take away something different but something that will hopefully help you understand the positive value that engaging with open source might have in your future.

Back to this weeks new open source projects, and we have another fantastic selection. Starting off we "xray-cli" with provides some ascii goodness via the cli for xray users, "crypteia" for AWS Lambda users who need secure environment variables available, "amazon-connect-rules-engine" a really interesting looking tool for Amazon Connect users, "aws-cyclone-solution" a cloud-native HPC job scheduler, "awsresecurity" a tool to help educate your users on security, "aws-codeartifact-semantic-release-example" an example of implementing semantic versioning in your releases, "aws-lambda-powertools-dotnet" the preview of AWS Lambda Powertools for .NET users, and many other projects for you to practice your four freedoms.

This week also features a wide variety of content, and topics include Firecracker, AWS Lambda Power Tools, OpenSearch, Flutter, Babelfish for Aurora PostgreSQL, MySQL,  Apache TinkerPop, OpenShift, and dbt. Don't miss the video section, with a great video from re:Inforce covering AWS libcrypto, and a round up of events you should be checking out.

**Feedback**

At Amazon we work backwards from our customers, and one of the ways we do that is collecting data to help us know what is important and what we should focus on. Please could you [complete this simple](https://eventbox.dev/survey/NUSZ91Z), anonymous survey. The first 25 will get an AWS $25 credit code.

**Celebrating open source contributors**

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created. 

So thank you to the following open source heroes: Gerardo Castro Arica, Abdallah Shaban, Muhammed Salih Güler, Ashish Nanda, Jean Latiere, Ludvig Nordstrom, Ran Isenberg, Alex Ellis, Richard Case, Andrew Hopkins, Alex Casalboni, Darren Lin, CK Wang, Stephen Mallette, Ketrina Thompson, Michael Zhang, Shinji Hayama, Randy Chng and Sean Beath.

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution.*

#### Tools

**xray-cli**

[xray-cli](https://aws-oss.beachgeek.co.uk/1ya) when anyone mentions ascii art, I tend to get very excited. So when AWS Community Builder Lars Jacobsson pinged me about this new project from Mathem, I was very happy indeed. xray-cli is a command line tool for quickly analysing AWS X-Ray traces. You can get a quick overview of you applications traces to learn about bottlenecks and failure points. Awesome stuff.

![demo of xray-cli tool](https://raw.githubusercontent.com/mhlabs/xray-cli/main/images/demo1.gif)

**crypteia**

[crypteia](https://aws-oss.beachgeek.co.uk/1y9) this project from Custom Ink provides a Rust Lambda Extension for any Runtime to preload SSM Parameters as 🔐 Secure Environment Variables.

**developer-cost-guide**

[developer-cost-guide](https://aws-oss.beachgeek.co.uk/1yb) projects come in all shapes and sizes, and this repo from Macroscope is less code and more a collection of resources for learn everything you need to know about your AWS Bill. Make sure you check out the website as it provides the documentation to guide you through how you can set everything up and then use these resources to help you stay on top of your AWS Bill.

**amazon-connect-rules-engine**

[amazon-connect-rules-engine](https://aws-oss.beachgeek.co.uk/1y6) This project aims to deliver an engine sitting on top of Amazon Connect which has the capability to build a hyper-personalised interactive voice response (IVR) experience for customers. Looks very nice and feature rich this project, so if you are an Amazon Connect user then you have to check this one out.

![screenshot of admin screen of connect-rules-engine](https://github.com/aws-samples/amazon-connect-rules-engine/blob/main/manual/graph_filtered.png?raw=true)

**aws-cyclone-solution**

[aws-cyclone-solution](https://aws-oss.beachgeek.co.uk/1xn) Jean Latiere and Ludvig Nordstrom reached out to me to share this new project they have been working on. What are they excited about? AWS-Cyclone-Solution is a cloud-native HPC job scheduler and resource orchestrator built for AWS customers that require large compute capacity and high scheduling throughput. Customers can deploy compute clusters that span across all AWS regions and their on-premise compute from a single control plane. They can submit jobs at high throughput to increase resource utilisation and enable massive scale, even for short running jobs.

![overview of the cyclone architecture](https://github.com/awslabs/aws-cyclone-solution/blob/main/media/front-end-arch.png?raw=true)

**awsresecurity**

[awsresecurity](https://aws-oss.beachgeek.co.uk/1y7) check out this interactive learning tool from AWS Community Builder Gerardo Castro Arica, that helps develop skills in the areas of Cloud Security and Blue Team. 

### Demos, Samples, Solutions and Workshops

**aws-codeartifact-semantic-release-example**

[aws-codeartifact-semantic-release-example](https://aws-oss.beachgeek.co.uk/1y8) This repository shows how to integrate semantic-release into your project to automate the entire package release workflow of determining the next version number, generating release notes, and publishing the package to AWS CodeArtifact.

**aws-lambda-powertools-dotnet**

[aws-lambda-powertools-dotnet](https://aws-oss.beachgeek.co.uk/1xp) AWS Lambda Powertools for .NET is now preview. The project makes available three core observability features: 1. Distributed tracing (Tracing), 2. Structured logging (Logging), and 3. Async business and application metrics (Metrics) 

**meta-aws-ewaol**

[meta-aws-ewaol](https://aws-oss.beachgeek.co.uk/1yc) This repository provides the example code and instructions for building a customised [Edge Workload Abstraction and Orchestration Layer (EWAOL)](https://aws-oss.beachgeek.co.uk/1yd) distribution in form of an Amazon Machine Image (AMI). EWOL provides users with a standards based framework using containers for the deployment and orchestration of applications on edge platforms.

![architecture diagram of aws ewaol](https://github.com/aws4embeddedlinux/meta-aws-ewaol/blob/main/graphics/meta-aws-ewaol.png?raw=true)

**minimum-eks-devsecops-with-monitoring-options**

[minimum-eks-devsecops-with-monitoring-options](https://aws-oss.beachgeek.co.uk/1ye) This sample code base will demonstrate how to build an end to end DevSecOps pipeline on Amazon EKS using IaC code scanning static scanning and dynamic (runtime) scanning using native AWS services as well as 3rd party services and continous monitoring and alerting with Prometheus and Grafana. The products/services used include Hadolink/Shellcheck, Checkov, Anchore Engine, CNCF Falcao Family, Prometheus, and Grafana. 

![architecture diagram for min devsecops](https://github.com/aws-samples/minimum-eks-devsecops-with-monitoring-options/blob/main/images/eks-devsecops.png?raw=true)

**demo-auto-aws-iotfleetwise**

[demo-auto-aws-iotfleetwise](https://aws-oss.beachgeek.co.uk/1yf) This demo aims to exhibit how AWS IoT Fleetwise can make it easy and cost effective to collect, transform, and transfer vehicle data to the cloud in near-real time and use it to build applications with analytics and machine learning that improve vehicle quality, safety, and autonomy.

![architecture diagram of iotfleetwise](https://github.com/aws4embeddedlinux/demo-auto-aws-iotfleetwise/blob/main/doc/architecture.png?raw=true)

The demo simulates two kind of vehicles:

* An NXP GoldBox powered by an Automotive Grade Linux distribution that runs the AWS IoT FleetWise agent as a AWS IoT Greengrass component. The agent has access to one of the NXP GoldBoX CAN interfaces which is connected to a PC, equipped with a USB to CAN Adapter. The PC generates CAN signals from a virtual vehicle in CARLA Simulator. The vehicle in CARLA can self drive or be driven with game steering wheel connected to a PC.
* A completely virtual vehicle, implemented as a AWS Graviton ARM based EC2 instance powered by a ubuntu linux distribution. In this EC2 instance, we have both the AWS IoT FleetWise agent and a process that generate random signals that are sent on a virtual CAN bus where the agent is listening on.

### AWS and Community blog posts

**Apache TinkerPop**

This is my favourite post this week, and takes a look at some of the broader contributions that go into making open source projects. Stephen Mallette speaks with Ketrina Thompson, developer by day, artist by night, on what some of those contributions look like. Make sure you read this post!

![artist illustrations for apache tinkerpop](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2022/07/27/TinkerPop-mascots.png)

Check out the post, [Beyond Code: The Artist Who Contributes to Apache TinkerPop](https://aws-oss.beachgeek.co.uk/1yg)

>Thanks to Taylor Riggan for flagging that I had missed the link!

**dbt**

dbt is a popular open-source command line tool that helps data engineering teams move and transform data into data warehouses more effectively. Randy Chng and Sean Beath have put together this post, [Manage data transformations with dbt in Amazon Redshift](https://aws-oss.beachgeek.co.uk/1y5) demonstrate some features in dbt that help you manage data transformations in Amazon Redshift. There is also a link to a workshop for you to dive even deeper if you want to learn more about how dbt can help you. [hands on]

![example of dbt workflow](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2022/07/22/Picture-1-2.png)

**Flutter**

Flutter is an open-source UI software development kit used to develop cross platform applications for Android, iOS, Linux, macOS, Windows. AWS Amplify Flutter had its initial Developer Preview release on August 2020. With that release Amplify Flutter provided a set of tools and services for building secure, scalable Flutter applications targeting iOS and Android. Abdallah Shaban, Muhammed Salih Güler, and Ashish Nanda have collaborated on this post, [Authentication with AWS Amplify Flutter for Mobile, Web, and Desktop](https://aws-oss.beachgeek.co.uk/1xw) where they share how you can use AWS Amplify Authentication and the Authenticator UI libraries on all supported platforms.

![demo of flutter on amplify with cross platform support](https://d2908q01vomqb2.cloudfront.net/0a57cb53ba59c46fc4b692527a38a87c78d84028/2022/08/02/output-1.gif)

**Kubernetes**

AWS Local Zones are a type of infrastructure deployment that places compute, storage, and other select AWS services close to large population and industry centres. In the post, [Running Workload on Amazon EKS in Local Zones with resilient architecture](https://aws-oss.beachgeek.co.uk/1y0), Darren Lin and CK Wang provide an example for running the WordPress application workload in the Local Zone on Amazon EKS, and failover to the region in the rare event of an issue in the Local one. [hands on]

![architecture of eks running on aws localzone](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2022/08/01/eks-localzone-arch-1024x878.png)

**OpenZFS**

Amazon FSx for OpenZFS is a high-performance shared file storage with hundreds of microseconds latency and 1 million input/output operations per second (IOPS) accessed via a Network File System (NFS) (v3, v4–4.2) protocol. It provides the familiar features and capabilities of OpenZFS file systems as a fully managed AWS service. In the post, [Backup and restore Amazon FSx for OpenZFS with AWS Backup](https://aws-oss.beachgeek.co.uk/1y2) Michael Zhang and Shinji Hayama demonstrate how to use AWS Backup to backup an Amazon FSx for OpenZFS file system, make a copy of the backup to a different account, and restore the file system locally in that account. [hands on]

![architecture of openzfs backup](https://d2908q01vomqb2.cloudfront.net/e1822db470e60d090affd0956d743cb0e7cdf113/2022/07/13/Figure-1-Solution-overview-1024x416.png)

**Other posts you might like from the past week**

* [Fine-tune and deploy a summarizer model using the Hugging Face Amazon SageMaker containers bringing your own script](https://aws-oss.beachgeek.co.uk/1y4) shows you how to build and deploy a custom Hugging Face text summarizer and deploy it to production on SageMaker [hands on]
* [How to containerize legacy code into Red Hat OpenShift on AWS (ROSA)](https://aws-oss.beachgeek.co.uk/1y1) is a great post that shows you how to re-platform and even augment a COBOL application using container technologies [hands on]

![architecture of replatforming cobol](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2022/07/15/redhat-1.png)

* [Manage long-running read queries on Amazon Aurora PostgreSQL-Compatible Edition](https://aws-oss.beachgeek.co.uk/1y3) shares some common use cases and scenarios of long-running queries and shares some  best practices on how to proactively manage these

![long running queries on postgres diagram](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2022/07/25/DBBLOG-2192-image001.png)

### Quick updates

**CDKTF**

Cloud Development Kit for Terraform (CDKTF) allows you to use familiar programming languages to define and provision infrastructure. This gives you access to the entire Terraform ecosystem without learning HashiCorp Configuration Language (HCL) and lets you leverage the power of your existing toolchain for testing, dependency management, etc. It currently supports TypeScript, Python, Java, C#, and Go.

Earlier in the week HashiCorp wrote, [CDK for Terraform Is Now Generally Available](https://aws-oss.beachgeek.co.uk/1xu) announcing the general availability of this tool.

![architecture of cdktf](https://content.hashicorp.com/api/assets?product=terraform-cdk&version=refs%2Fheads%2Fstable-website&asset=website%2Fdocs%2Fcdktf%2Fconcepts%2Fimages%2Fcdktf-terraform-workflow.png&width=4096&height=3070)

**Flutter**

AWS Amplify is announcing a developer preview to expand Flutter support to web and desktop, starting with the Authentication category. With this release, developers can use Amplify to create new Flutter apps that support web and desktop in addition to mobile platforms. Developers can also extend existing mobile Amplify Flutter projects to support web and desktop. 

With this developer preview version, developers can use a single codebase with the Amplify Authentication category to build Flutter apps that target iOS, Android, web, and desktop (Mac, Linux, Windows). Our Authenticator UI library has also been upgraded to support Flutter web and desktop, providing developers with a sign in/sign up experience that works across iOS, Android, web, and desktop with minimal configurations. We will be expanding web and desktop support for the rest of Amplify Flutter categories in future releases.

**MySQL**

Amazon RDS for MySQL supports encrypted SSL/TLS connections to the database instances. Starting today, you can enforce SSL/TLS client connections to your RDS for MySQL database instance for enhanced transport layer security. To enforce SSL/TLS, simply enable the require_secure_transport parameter (disabled by default) through the Amazon RDS Management Console, the AWS CLI or the API. When the require_secure_transport parameter is enabled, a database client will be able to connect to the RDS for MySQL instance only if it can establish an encrypted connection.

**PostgreSQL**

Amazon Relational Database Service (Amazon RDS) for PostgreSQL now supports PostgreSQL minor versions 14.3, 13.7, 12.11, 11.16, and 10.21. We recommend you upgrade to the latest minor versions to fix known security vulnerabilities in prior versions of PostgreSQL, and to benefit from the bug fixes, performance improvements, and new functionality added by the PostgreSQL community. This PostgreSQL release also includes updates for existing supported PostgreSQL extensions: pglogical extension is updated to 2.4.1, pg_hint_plan extension is updated to 1.4, and hll extension is updated to 2.16.

**Kyber**

[Kyber](https://aws-oss.beachgeek.co.uk/1xs) is a key encapsulation method (KEM) designed to be resistant to cryptanalytic attacks with future powerful quantum computers.

Connections to AWS Secrets Manager now support hybrid post-quantum key establishment using Kyber for transport layer security (TLS) from Round 3 of the NIST Post-Quantum Cryptography (PQC) selection process. This allows you to measure the potential performance impact of the post-quantum algorithm. You can also benefit from the longer-term confidentiality afforded by hybrid post-quantum TLS.

Hybrid post-quantum TLS combines a classical key agreement, such as ECDHE, with a post-quantum key encapsulation mechanism, in this case Kyber, which NIST has selected for future standardisation. The result is that your TLS connections inherit the security properties of both the classical and post-quantum key exchanges.  

**OpenSearch**

Amazon OpenSearch Service, with the availability of OpenSearch 1.3., now gives customers the ability to organise their logs, traces and visualisations in an application-centric view. Customers can also benefit from enhanced log monitoring support with live tailing of logs, the ability to see surrounding log data, and the ability to do powerful ad-hoc analysis of unformatted log data at query time.

You can read more about this in the official post, [Amazon OpenSearch Service now includes advanced log and application analytics](https://aws-oss.beachgeek.co.uk/1xr)

**AWS DMS**

Babelfish for Aurora PostgreSQL is a capability for Aurora PostgreSQL that enables Aurora to understand commands from applications written for Microsoft SQL Server.

With Babelfish, Aurora PostgreSQL can understand T-SQL, SQL Server’s proprietary SQL dialect, and supports the same communications protocol, so your apps that were originally written for SQL Server can work with Aurora with fewer code changes. As a result, the effort required to modify and move applications running on SQL Server 2005 or newer to Aurora is reduced, leading to faster, lower-risk, and more cost-effective migrations.

AWS DMS v3.4.7 introduces a new Babelfish target endpoint, which allows you to migrate your SQL Server workloads directly to PostgreSQL. As of this writing, AWS DMS supports full load migration to Babelfish support, and CDC is planned for future releases

To find out more, read the detailed blog post, [New features in AWS DMS 3.4.7](https://aws-oss.beachgeek.co.uk/1xt)

### Videos of the week

**Firecracker**

In this vide Alex Ellis and Richard Case from Weaveworks share what's got them so excited about [Firecracker](https://aws-oss.beachgeek.co.uk/1xy), the kinds of use-cases they see for microVMs, fundamentals of Linux Operating Systems and plenty of demos. Well worth a watch this week.

{< youtube CYCsa5e2vqg >}}


**AWS libcrypto**

There were a lot of great sessions at [AWS re:Inforce](https://www.youtube.com/hashtag/reinforce2022) so it would be remiss of me not to include something in this weeks round up. Andrew Hopkins covers and introduction into the open source [AWS libcrypto (AWS-LC) library](https://aws-oss.beachgeek.co.uk/1xx), shares how we migrated s2n to use it, and why AWS is invested in improving open-source cryptography. Well worth 35 mins of your time.

{< youtube OLaKGzZAxRM >}}


**AWS Lambda Power Tuning**

[AWS Lambda Power Tuning](https://aws-oss.beachgeek.co.uk/1xz) is an awesome open source project from my good friend Alex Casalboni, that allows you to understand the performance characteristics of your AWS Lambda functions and then provide information to help you make good decisions around performance and cost. In this video, Be a Better Dev provide a nice overview of the tool.

{< youtube QUJ_Govd0CQ >}}


### Events for your diary

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)

**Just-in-time Worker Nodes with Karpenter**
**5th August, 2pm IST**

Karpenter helps improve your application availability and cluster efficiency by rapidly launching right-sized compute resources in response to changing application load. In this webinar with my colleague Rohini Goankar, you will get an overview of Karpenter and it’s features, see a demonstration of how Karpenter simplifies Kubernetes infrastructure with the right nodes at the right time, and there will be practical demos on how to use Karpenter.

Find out more and register via this link, [An Open-Source High-Performance Kubernetes Cluster Autoscaler](https://aws-oss.beachgeek.co.uk/1w5)

**Digital Payments Architecture and Implementation with AWS Open Source Databases**
**August 18th**

Check out this Webinar on how to use open source databases to build a digital payments solution. You can view it live direct on [YouTube here](https://www.youtube.com/watch?v=kbjtLPYToaI)

**Bottlerocket Community Meeting**
**August, 24th 8:30am PDT**

You're invited to the Bottlerocket community meeting where we'll discuss project news, share Bottlerocket tips, tricks, and techniques, and you'll have the opportunity to ask questions in an open forum.

Find out more and [reserve your spot here](https://www.meetup.com/bottlerocket-community/events/287425423).

**Introduction to Amazon Managed Workflows for Apache Airflow**
**August 25th, 8am-1pm PDT**

In this workshop, you will learn to build and orchestrate data and ML pipelines that include many of the above mentioned services, and with that you will gain familiarity and a better understanding of the hooks and operators available as part of Airflow to manage your pipelines/workflows on AWS. We start with an introduction to the basics if you want to get familiar with the concepts in Airflow before you get to the hands-on modules.

Join this event and learn how to leverage Amazon MWAA as well as key concepts.

* Learn how to build your Data/ML pipeline orchestrated by Airflow
* Apache Airflow basics within AWS
* Get hands-on experience with an AWS Solution Architect for best practices
* 
**Who Should Attend?**

If you work with data in any form, and build pipelines to transform/consume the data, then this workshop is for you! Level 200 and up. Although you don't need to be an expert to take this workshop, it will help if you had some basic understanding about AWS Analytics services, and some familiarity with SQL and Python programming languages. We recommend some familiarity with the AWS Console but it is not required. We recommend two monitors for the best experience.

To register and reserve your spot, [use this link](https://aws-oss.beachgeek.co.uk/1xq).

**OpenSearchCon 2022**
**Sept 21st, 2022 Seattle**

Come to the first annual OpenSearchCon!

This day-long conference will be packed with presenters who build and innovate with OpenSearch. It doesn’t matter if you’re just getting started on your OpenSearch journey, running giant clusters, or contributing tons of code; the event is for everyone. Join us to celebrate the progress and look into the future of the project. Admission is free, and registration will be open in the next few weeks. All you will need to do is sign up, and get to Seattle!

Check out the full details, including signing up and location, at the [meetup page here](https://aws-oss.beachgeek.co.uk/1n1).


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)

