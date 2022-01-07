---
title: 'AWS open source news and updates #71'
date: '2021-06-07'
tags : [ oss-newsletter ]
---
## 7th June, 2021 - Instalment #71

Newsletter #71.

This week we have a number of security related projects, covering reference/best practice deployments of open source security tools as well as new tools that will help you identify misconfigured assets. Another interesting project this week is moot, a serverless project to help yo simplify your deployments. On top of the new projects, we have some great community and AWS blog posts on Kubernetes, OpenSearch, Eventbridge Atlas, Keycloak, Apache Kafka, SQLAlchemy, AWS Copilot, OpenShift and many more. Make sure you also check out the events section, with a little over a week to go before Open@Amazon, have you registered yet?

**Do you love Rust?**

In the past few weeks there have been some great new contributions to the Rust SDK. We had [MediaLive and MediaPackage](https://aws-oss.beachgeek.co.uk/kz) services as well as improvements to others such as [this one](https://aws-oss.beachgeek.co.uk/l0), but I know they are looking for more folks to roll their sleeves up and get stuck in. If you are looking to get into Rust, then this might be a great opportunity as the project has a number of "good first issues" and "documentation" tasks that might make a good starting point.

**Please help me improve this newsletter**

Thank you to those who have provided such great feedback already, I am currently reviewing and thinking how to incorporate the suggestions. I would still love to hear from more of you, and I have more AWS credit vouchers as a thank you for taking the time to complete the survey. The first 20 will get an AWS credit voucher for $25, so thank you again. It is only 5 questions, and will probably only take you a minute or two to complete.

[Take me to the survey!](https://eventbox.dev/survey/9UQSAU3)

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes:  Alberto Falzone, Dario La Porta, Marcilio Mendonca, Srijit Mitra, Mandakini Saroop, Peiyu Wu, Pallavi Ravishankar, Jason Nicholls, Tim Gustafson, Vastin He, Min Xia, Tori Hara, Vu Dao, Kris Howard, Amitai Stern, David Boyne, Kyle Davis, Dotan Horovits, Augusto Valdivia, Łukasz Budnik, Gary Stafford, Chris Christensen, Ryan Petrich, Ryan Niksch, Noga Yam Amitai, and Sean Turner 

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

**aws-sdk-client-mock**

[aws-sdk-client-mock](https://aws-oss.beachgeek.co.uk/ll) when Maciej Radzikowski was looking for greater support for testing when using the AWS JavaScript SDK v3, he created this library to provide mocking it in unit tests. If you are a users of the AWS JS SDK v3, then the clear documentation with examples should help you get started straight away.

![demo](https://raw.githubusercontent.com/m-radzikowski/aws-sdk-client-mock/main/.github/aws-client-mock-example.gif)

**moot**

[moot](https://aws-oss.beachgeek.co.uk/lm) it has been a long time since I have walked along Cuba St enjoying the fine Sushi in Wellington, New Zealand, and hailing from the same city we have this project from Sean Turner, moot. This is a serverless solution that implements a release dashboard that provides a single button press for deploying code changes to production and integrates with GitHub and GitLab. One for the weekend I think.

![demo](https://raw.githubusercontent.com/seanturner026/moot/main/assets/repositories.png)

**Apache Airflow and AWS CodeArtifact**

[mwaa-with-codeartifact](https://aws-oss.beachgeek.co.uk/lk) this project will be super helpful if you want tighter control over where you install your Python dependencies in your Apache Airflow DAGs when using Managed Workflows for Apache Airflow (MWAA), by integrating with AWS CodeArtifact. Aside from more control, this enables users to avoid providing MWAA with an internet access via NAT Gateway and hence reduce the cost of their infrastructure.

![arch](https://github.com/aws-samples/amazon-mwaa-examples/blob/main/usecases/mwaa-with-codeartifact/docs/architecture.png?raw=true)

**patrolaroid**

[patrolaroid](https://aws-oss.beachgeek.co.uk/lq) this open source project from Ryan Petrich looks interesting for those looking for the latest security tools. Patrolaroid snapshots AWS instances and buckets to uncover malware, backdoors, cryptominers, toolkits, and other attacker tomfoolery that you probably don’t want in your prod. Software engineers, security engineers, and cloud administrators only need familiarity with YARA and the AWS Management Console to use it. I am going to have to check this out for sure. 

**nexus-oss-on-aws**

Nexus Repository is an open source artefact repository that supports various formats (Maven/Java, npm, NuGet, Helm, Docker, Android APT, GO, and many more) integrates nicely with a broad range of developer tools and is really useful when helping to create nice reports of your applications and what open source libraries they are using. This project, [nexus-oss-on-aws](https://aws-oss.beachgeek.co.uk/li) will help you to deploy a Nexus Repository via Helm on Amazon EKS.

![arch](https://github.com/aws-samples/nexus-oss-on-aws/blob/master/arch.png?raw=true)

**red-bucket**

[red-bucket](https://aws-oss.beachgeek.co.uk/ln) this open source tool from Lightspin scans your Amazon S3 Buckets for public access and cross-account attacks and analyses bucket's block public access settings, bucket policy and ACL and object ACL. Noga Yam Amitai has put together a couple of blog posts to help get you started.

**xroad-security-servers**

[xroad-security-servers](https://aws-oss.beachgeek.co.uk/lj) X-Road® is an open-source solution for secure data exchange between organisations. Data is exchanged on X-Road through access points called Security Servers implementing the same technical specifications. This project provides best practices for deploying those on AWS, through the lens of the Well Architected Framework.

**aws-sso-login**

[aws-sso-login](https://aws-oss.beachgeek.co.uk/lp) this tool from Chris Christensen is his first Go application, and this tool will help you automate the process of logging into multiple AWS accounts using AWS's SSO service.

**GrandNode**

[GrandNode](https://aws-oss.beachgeek.co.uk/lh) - GrandNode is a GPLv3 licensed open source e-commerce tool built in .NET 5 that last week introduced support for AWS DocumentDB.

### Community open source posts

**deps.dev**

Last week Google launched a rather nice tool that allows you to explore the dependency graph of your open source projects. You can check the tool out at [https://deps.dev/](https://aws-oss.beachgeek.co.uk/la) and try it out on some of your projects to see the graph and reports created. Python and .Net packages will arrive at some point, but you should take a look at this project. One of the ways I think it might help folks is in pulling together things such as the licences used, which this helps simplify. Nice job.

**EventBridge Atlas**

David Boyne has been prolific over the past few months, releasing some great open source project, including EventBridge Atlas. In this post, [AWS EventBridge with Flow (Node Diagrams)](https://aws-oss.beachgeek.co.uk/lb) he walks you through the recently added visual output that he has incorporated using React Flow. Very nice indeed.. 

![demo](https://www.boyney.io/static/images/blogs/eventbridge-atlas-flow/flow-example.png)

**Kubernetes**

[Kubernetes-based Microservice Observability with Istio Service Mesh](https://aws-oss.beachgeek.co.uk/lo) this is the first of a two part series from Gary Stafford that will explore a number of popular open-source observability tools integrated with the Istio service mesh. These tools include Jaeger for distributed transaction monitoring, Kiali for application visualisation, Prometheus for metrics collection and alerting, and Grafana for metrics querying, visualisation, and alerting. I have read quite a few of these type of blog posts over the past few months, and the clarity and depth of this sets it apart from all the others. A must read this week.

![arch](https://miro.medium.com/max/2878/1*XJGRL8oxig119UfbkSMcig.png)

**OpenSearch**

[My First Steps in OpenSearch Plugins](https://aws-oss.beachgeek.co.uk/lc) sees Amitai Stern share his experiences as part of creating his first OpenSearch plugin. This is a really great post, and whether you are considering contributing to OpenSearch or not, the approach and topics he covers apply to many if not all projects.

![arch](https://opensearch.org/assets/media/blog-images/2021-06-03-my-first-steps-in-opensearch-plugins/plugins-architectural-diagram.jpg)

**Bonus** If you missed the podcast, [OpenSearch: The Open Source Successor of Elasticsearch](https://aws-oss.beachgeek.co.uk/ld) featuring Kyle Davis and Dotan Horovits takes a look at OpenSearch, starting with the origins and then taking a look at how the community and project are progressing.

**duckyPad**

Great post from colleague Kris Howard, sharing her build out of the [duckyPad](https://aws-oss.beachgeek.co.uk/l9). What is that I can hear you all asking...well, it is a rather nice piece of open source hardware/software that allows you to create your own Stream Deck setup, except that you build it yourself. Kris walks you through the build out, everything from the hardware to software and she even shares her key setup with you. Even though I already have a Stream Deck, this just looks so nice I might have to invest.

![duckypad](https://www.web-goddess.org/wp-content/uploads/2021/06/img_7070-scaled.jpg)

**frp**

[frp](https://github.com/fatedier/frp) is an open source reverse proxy to help you expose a local server behind a NAT or firewall to the Internet. Vu Dao has put together this post, [FRP - Fast Reserve Proxy - Connect To Database In Private Network](https://aws-oss.beachgeek.co.uk/l8) on how you can use this open source tool, to deploy (via AWS CDK) a solution that allows you to access resources in a private network, in this instance connecting to a database.

![arch](https://res.cloudinary.com/practicaldev/image/fetch/s--VH8DZkD3--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://github.com/vumdao/k8s-frp/blob/master/img/flow.png%3Fraw%3Dtrue)

**Keycloak**

[Keycloak](https://aws-oss.beachgeek.co.uk/lf) is an open source Identity and Access Management project I have covered in previous editions of this newsletter, and Łukasz Budnik takes a closer look at this project in his post, [Why I choose Keycloak over AWS Cognito](https://aws-oss.beachgeek.co.uk/lg) comparing how this compares to AWS services such as Cognito, and some of the considerations you might want to think about as you architect your solutions. 

**Terraform**

[AWS Data Lake with Terraform](https://aws-oss.beachgeek.co.uk/le) AWS Community Builder Augusto Valdivia kicks off a six part series helping you to create your data lakes on AWS via Infrastructure as Code (IaC), in this instance using Terraform. He aims to cover how you can use Terraform scripts to allow for fast and repeatable deployments, efficient testing and to decrease recovery time in case of an unplanned event. 

![arch](https://res.cloudinary.com/practicaldev/image/fetch/s--YtBPUf7f--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/fgnzhqg35ef62jj8tdwe.png)

### AWS and Amazon open source posts

**AWS Distro for OpenTelemetry**

In this post, [Managing AWS Distro for OpenTelemetry (ADOT) Collector with AWS Systems Manager Distributor](https://aws-oss.beachgeek.co.uk/l5) Vastin He and Min Xia discuss the design for packaging and publishing the ADOT Collector so that you can simplify how you roll this out at scale with the help of a number of AWS services such as Systems Manager Distributor and Systems Manager Distributor, using GitHub Actions to provide a simplified installation experience.

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/05/10/He-ADOT-Collector_F1.png)

**SQLAlchemy**

SQLAlchemy is an open-source (MIT) SQL toolkit and object-relational mapper (ORM) for the Python programming language. Marcilio Mendonca and Srijit Mitra have written this post, [Use Python SQLAlchemy ORM to interact with an Amazon Aurora database from a serverless application](https://aws-oss.beachgeek.co.uk/l1) on how developers can migrate their monolithic applications to a serverless stack using Amazon API Gateway and Lambda while continuing to use SQLAlchemy, taking a look at how separation of duties between the database and the development team can be achieved.

![arch](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2021/05/21/dbblog_1131_01.png)

**Linux GRUB**

Pallavi Ravishankar and Jason Nicholls' post, [Using EC2 Serial Console to access the GRUB menu and recover from boot failures](https://aws-oss.beachgeek.co.uk/l2), takes a look at how you can use a recent new capability of Amazon EC2, the EC2 Serial Console, to troubleshoot boot failures, showing how you can access the GNU Grand Unified Bootloader (GRUB) to directly fix the problem (in this post they are using Amazon Linux 2, but other flavours will work too). I am so happy that this exists, as you never know when you might need it - I am sure we all have our own Kernel/GRUB stories, feel free to share them in the comments :-)

![error](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2021/06/01/grub2.png)

**AWS Copilot**

Copilot is an open source command line interface created by AWS, and was originally created to make it easy for developers to build, release, and operate production ready containerised workloads on Amazon ECS and AWS Fargate. In this post, [Enabling continuous workflows for AWS App Runner service with persistency using AWS Copilot CLI](https://aws-oss.beachgeek.co.uk/l6) Tori Hara takes a look at how Copilot has been updated to support AWS App Runner, a new service that provides the simplest way to build and run your containerised stateless web application on AWS, Copilot was updated so you can run your containerised application on App Runner with Copilot.

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2021/05/29/diagram-final.png)

**OpenShift**

[Red Hat OpenShift Service on AWS: architecture and networking](https://aws-oss.beachgeek.co.uk/lr) Ryan Niksch takes a look at customers who are moving/migrating their OpenShift workloads to ROSA, Red Hat OpenShift on AWS and explores the AWS and OpenShift architecture differences across a number of different use cases, such as private/public looking at the resources and components, where these are placed, what are the implementation differences when deploying single vs multi-Availability Zone clusters, and differences between public and private clusters.

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2021/06/03/rosa-arch-multi.png)

**Apache Kakfa**

Mandakini Saroop and Peiyu Wu have put together this post, [Setting up AWS Lambda with an Apache Kafka cluster within a VPC](https://aws-oss.beachgeek.co.uk/l3), which is a follow up to a previous one I shared on how to use AWS Lambda functions as a consumer of Apache Kakfa streaming data, and in this post they dive into setup considerations and best practices you should think about if you are considering doing something similar.

![arch](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2021/06/01/msk6.png)

**MySQL**

Tim Gustafson writes how you can reduce or eliminate application down-time associated with database schema changes in your MySQL and MariaDB applications in, [Upgrade Amazon RDS for MySQL or MariaDB database schemas with minimal downtime](https://aws-oss.beachgeek.co.uk/l4). The steps described in this post should allow you to make database schema changes that reduce the impact to your application, improving the end-user experience and reducing the burden of database schema changes. 


**High Performance Computing (HPC)**

If you want to do High Performance Computing (HPC) there is a good chance you are going to be using a lot of open source tools to help you across all the parts of your workflows. In this post from Alberto Falzone and Dario La Porta, [Building highly-available HPC infrastructure on AWS](https://aws-oss.beachgeek.co.uk/ky) take a look at some of those open source projects and how together with AWS, you can build highly available HPC infrastructure.

![arch](https://d2908q01vomqb2.cloudfront.net/e6c3dd630428fd54834172b8fd2735fed9416da4/2021/06/03/ha-hpc-fig1.png)


### Quick updates

**AWS Systems Manager**

The AWS Systems Manager Session Manager plugin for the AWS Command Line Interface (AWS CLI) is now open source. Customers can access the source code for the Session Manager plugin for the AWS CLI on GitHub, contribute to its development, and use it as a building block to embed Session Manager capabilities into their own applications.

Customers get greater visibility into the design and implementation of the Session Manager plugin. Developers can contribute to its development by making suggestions, reporting issues, and submitting pull requests. With the Session Manager plugin for the AWS CLI, you can start and end sessions with your compute nodes managed by Systems Manager, from your local machine using the AWS CLI. You can install the Session Manager plugin for the AWS CLI as an installer package for different operating systems including Windows, Linux, and macOS. With open source, you can now customise the plugin to include the ability to work with Session Manager sessions, within any custom application for your users.







### Events for your diary

**Maintainer Week**
**week of June 7th**

Make sure you check out this week long event starting on the 7th of June, for open source maintainers to gather, share, and be celebrated. You can find details of [all the weeks sessions on their GitHub page](https://aws-oss.beachgeek.co.uk/kq), with Upstream on June 7th, Global Maintainer Summit on the 8/9th, The Changelog: Maintainer Spotlight on the 10th and FundOSS on the 11th.

**Open@Amazon**
**June 16th, 9:00am - 5:00PM EDT**

If you missed it last week, next week we are running Open@Amazon, a celebration of open source on AWS with a fabulous cast of speakers, a fantastic broad set of topics and the event will be fully live so you can get your chance to interact with the speakers and the broader open source and AWS community. Check out the blog post, [What’s up with open source at AWS? Attend Open@Amazon live on Twitch June 16](https://aws-oss.beachgeek.co.uk/jo) or just register to get a handy calendar invite [HERE](https://aws-oss.beachgeek.co.uk/jn)

**Cloud Native Day**
**23rd September, Bern Switzerland**

What is this, an in person event returning? A stellar line up including our own Michael Hausenblas, an event looking at CNCF projects and the future of IT. Find out more and to view prices/register, by clicking [here](https://cloudnativeday.ch/en/#speakers).


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen).