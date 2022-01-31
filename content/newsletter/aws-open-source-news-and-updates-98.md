---

title: 'AWS open source news and updates #98'
date: '2022-01-29'
tags : [ oss-newsletter, aws open source, Kubernetes, Tekton, ArgoCD, Suricata, Apache Log4j, Gitlab, Porting Assistant for dotNET, Apache Airflow, PostgreSQL, AWS CDK, Apache JMeter, Lambda Powertools, Terraform ]

---

## Jan 29th, 2022 - Instalment #98

Newsletter #98. Welcome to another edition of AWS open source news and updates, featuring more new open source projects. This week, these include eventbridge-assistant (a VScode plugin to help you whilst you are developing with Amazon EventBridge), stratus-red-team (a tool you can use to emulate offensive attack techniques), critter (AWS Config rule integration testing), syne-tune-s3-transfer (an example of how to apply the distributed parameter search library to optimise download performance), karpenter-terraform (a Terraform module to help you automate deployment of karpenter), and a couple of super interesting open source solutions covering last mile delivery and software defined radio.

This weeks community and AWS authored articles and blog posts feature topics covering Kubernetes, Tekton, ArgoCD, Suricata, Apache Log4j, Gitlab, Porting Assistant for dotNET, Apache Airflow, PostgreSQL, AWS CDK, Apache JMeter, Lambda Powertools, and more. We also have a number of events happening this and next week, so make sure you review those and sign up whilst you can. 

To wrap things up we have videos from last weeks OpenUK's Future Founders series (make sure you watch this, really great session), and the Open Cloud Innovations (we have the keynote from Deepak as well as the AWS Heros panel session). 

As always, if you have any cool posts you would like me to share, or if you have a request for particular topics you would like to see more of, then please drop me a message or write a comment below.

**Job of the week**

[Principal Developer Advocate, Containers](https://aws-oss.beachgeek.co.uk/1b7)

Amazon Web Services (AWS) is looking for a talented leader to lead the Bottlerocket and Amazon Linux Developer Advocacy program, part of Container services. Find out more, and apply via [this link](https://aws-oss.beachgeek.co.uk/1b7). If you want to have a chat about what it is like, feel free to drop me a mail.

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Anton Arhipov, Jannik Wempe, Ajit Puthiyavettle, Carlos Santos, Thomas Liddle, Chris Hendon, Muhammad Mirza, Valentin Widmer, Wojciech Matuszewski, Christophe Tafani-Dereeper, and NaveenKumar Namachivayam

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest open source projects

**Community**

**eventbridge-assistant**

[eventbridge-assistant](https://aws-oss.beachgeek.co.uk/1ah) AWS Community Builder Lars Jacobsson over at Mathem just missed last weeks edition with this [new plugin for VSCode](https://aws-oss.beachgeek.co.uk/1ai). This extension integrates with Amazon EventBridge Schema Registry to provide autocomplete when composing event patterns.

![demo](https://github.com/mhlabs/eventbridge-assistant/raw/HEAD/images/demo.gif)

**stratus-red-team**

[stratus-red-team](https://aws-oss.beachgeek.co.uk/1aj) this open source project from DataDog, Stratus Red Team,  allowing you to emulate offensive attack techniques in a granular and self-contained manner. Read the blog post from Christophe Tafani-Dereeper, [Elevate AWS threat detection with Stratus Red Team](https://aws-oss.beachgeek.co.uk/1ak), to find out more.

![demo](https://raw.githubusercontent.com/DataDog/stratus-red-team/main/docs/demo.gif)

**Tools**

**critter**

[critter](https://aws-oss.beachgeek.co.uk/1an) critter enables AWS Config rule integration testing and validate that AWS Config rules evaluate resources as expected. Customers use AWS Config rules to evaluate their AWS resources against their own unique compliance and governance requirements. critter is a command line tool that enables a continuous integration workflow to validate that Config rules evaluate resources as expected. This is essential to guaranteeing compliance within AWS accounts, especially when you consider the potential impact of unexpected behaviour from Config rule auto-remediations.

**syne-tune-s3-transfer**

[syne-tune-s3-transfer](https://aws-oss.beachgeek.co.uk/1ao) Syne Tune is a distributed parameter search library open-sourced by AWS AI researchers. This tool uses Syne Tune to learn an optimal configuration of boto3's Download_file method, for a given file and a given client EC2 instance type. Using this code, we were able to reduce the download time of various files (5GiB, 10GiB) up to ~40% vs boto3 default transfer configuration.

**aws-mqtt-wavelength-latency**

[aws-mqtt-wavelength-latency](https://aws-oss.beachgeek.co.uk/1ap) an interesting utility that provides code so you can build an Android application that is purpose-built to test 5G roundtrip latency to EC2 MQTT brokers in a Wavelength zone.

**aws-codeguru-cli**

[aws-codeguru-cli](https://aws-oss.beachgeek.co.uk/1al) this project provide a simple CLI wrapper for CodeGuru reviewer that provides a one-line command to scan a local clone of a repository and receive results. This CLI wraps the AWS CLI commands to communicated with AWS CodeGuru Reviewer.

**Resources**

**aws-network-hub-for-terraform**

[aws-network-hub-for-terraform](https://aws-oss.beachgeek.co.uk/1aq) this repository demonstrates a scalable, segregated, secured AWS network hub for multi-account organisations using Terraform.

![arch](https://github.com/aws-samples/aws-network-hub-for-terraform/blob/main/images/diagram.png?raw=true)

**karpenter-terraform**

[karpenter-terraform](https://aws-oss.beachgeek.co.uk/1ar) this repository provides a Terrform module that helps automate the steps need to provision Karpenter.

**Demos and Samples**

**aws-last-mile-delivery-hyperlocal**

[aws-last-mile-delivery-hyperlocal](https://aws-oss.beachgeek.co.uk/1as) this is an interesting looking demo application, that provides a number of solutions useful in the retail industry around last mile logistics. Whilst this project is a work in progress, it provides a re-usable solution for tracking their (tens of thousands of) drivers and instantly make pick-up and routing decisions. The system provides granular real time tracking, complex search, as well as assignment of drivers to orders using latest mathematical optimisation techniques.

![arch](https://github.com/aws-samples/aws-last-mile-delivery-hyperlocal/blob/main/docs/architecture/solution-architecture.png?raw=true)

**encrypted-mqtt-communication-using-gnu-radio**

[encrypted-mqtt-communication-using-gnu-radio](https://aws-oss.beachgeek.co.uk/1at) this project provides a solution for an encrypted MQTT data transfer solution for the GNU Radio Software Defined Radio (SDR). [GNU Radio](https://aws-oss.beachgeek.co.uk/1au) is a free & open-source software development toolkit that provides signal processing blocks to implement software radios. It can be used with readily-available, low-cost external RF hardware to create software-defined radios, or without hardware in a simulation-like environment. It is widely used in hobbyist, academic, and commercial environments to support both wireless communications research and real-world radio systems.

![arch](https://github.com/aws-samples/encrypted-mqtt-communication-using-gnu-radio/blob/main/docs/encrypted-MQTT-GNU-Radio-generic.png?raw=true)

### AWS and Community blog posts

**AWS Lambda Powertools**

A new tutorial that progressively introduces Lambda Powertools core utilities by using one feature at a time is now available, so if you were looking for a way to get to know this project, check out the [Tutorial](https://aws-oss.beachgeek.co.uk/1ag)

![demo](https://awslabs.github.io/aws-lambda-powertools-python/latest/media/tracer_utility_showcase_3.png)

**AWS SDK for Kotlin**

With the recent announcement at re:Invent of the AWS SDK for Kotlin, it was good to read [The new AWS SDK for Kotlin with Coroutines support](https://aws-oss.beachgeek.co.uk/1b8) from Anton Arhipov that provides a nice quick summary of how to get started.

**AWS CDK**

This week we have a couple of posts on AWS CDK Aspects, a way to apply an operation to all constructs in a given scope. The aspect could modify the constructs, such as by adding tags, or it could verify something about the state of the constructs, such as ensuring that all buckets are encrypted.

First up we had AWS Community Builder Wojciech Matuszewski has put together this post, [Enforcing compliance with AWS CDK Aspects](https://aws-oss.beachgeek.co.uk/1av) walks you through with an example of how to get started with AWS CDK Aspects, and how it can help you enforce compliance of the various resources you deploy to AWS.

![illustration](https://res.cloudinary.com/practicaldev/image/fetch/s--BACQcKhK--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/hacw3cnkm05wi3bqdy7f.png)

And following that, Jannik Wempe was busy putting [The Power of AWS CDK Aspects](https://aws-oss.beachgeek.co.uk/1b6) together for you to all enjoy. Jannik walks you through some of the typical use cases with examples to help you get a better understanding of how to apply these to your own CDK applications.

![demo](https://cdn.hashnode.com/res/hashnode/image/upload/v1642622909709/M0HvdhMxq.png?auto=compress,format&format=webp)

**Apache Airflow**

I somehow missed this post when it first came out, but searching for something this week brought it to my attention. Felipe de Mello Rodrigues has put together, [How to work with Airflow Docker operator in Amazon MWAA](https://aws-oss.beachgeek.co.uk/1aw) which dives deep into one particular Apache Airflow operator, and how you might use it.

**Apache JMeter**

NaveenKumar Namachivayam has put together a great article, [Deploy JMeter on AWS using Terraform](https://aws-oss.beachgeek.co.uk/1ax) that helps you deploy this well loved testing project on AWS using Terraform. As NaveenKumar points out:
> 
> "Maintaining JMeter infrastructure for performance testing, CI/CD integration with the enterprise pipeline, and managing are cumbersome tasks."
> 
So read on to find out how to simplify your life.

![demo](https://cdn.shortpixel.ai/spai/w_1240+q_glossy+ret_img+to_webp/https://qainsights.com/wp-content/uploads/2022/01/image-16.png)

**AWS Cloud Map MCS Controller for K8s**

Thomas Liddle and Chris Hendon explore some common issues customers face when attempting to adopt a multicluster architecture and how AWS Cloud Map MCS Controller for K8s enables multicluster service discovery, in their post [Introducing AWS Cloud Map MCS Controller for K8s](https://aws-oss.beachgeek.co.uk/1aa). AWS Cloud Map MCS Controller for K8s, is an open source implementation of the Kubernetes proposed API, KEP-1645: Multicluster Services API. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2022/01/26/cloudmap-multi-cluster-diagram.png)

**Tekton and ArgoCD**

In the post, [Cloud Native CI/CD with Tekton and ArgoCD on AWS](https://aws-oss.beachgeek.co.uk/1ad) Valentin Widmer shows you how to use the Kubernetes native CI/CD system Tekton on top of Amazon Elastic Kubernetes Service (Amazon EKS). The walkthrough uses uses another open source project called ArgoCD. ArgoCD connects to one or more Git repositories and listens for changes to them. If a change is detected, ArgoCD pulls the repository and applies the content of it to the cluster, allowing for a GitOps-like workflow [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2022/01/12/CICDTekton.jpg)

**Kubernetes and Apache Log4j**

Muhammad Mirza has put together a post that offers a less intrusive and minimalistic solution to mitigate vulnerabilities in the applications using Apache Log4j, in [Protect Kubernetes workloads from Apache Log4j vulnerabilities](https://aws-oss.beachgeek.co.uk/1ab)

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2022/01/24/blog-log4j-exploit-solution.png)

Muhammad has created a simple application that contains a Log4j vulnerable application, and demonstrates discovery of the Log4j vulnerabilities and, how to protect the vulnerable application from such exploits. [hands on]

**Suricata**

Suricata is an open source-based intrusion detection system and intrusion prevention system. In the post, [How to deploy AWS Network Firewall to help protect your network from malware](https://aws-oss.beachgeek.co.uk/1a8) Ajit Puthiyavettle describes how to use custom Suricata Rules with AWS Network Firewall to add protections that prevent users from downloading malware. You can use your own internal list, or a list from commercial or open-source threat intelligence feeds. [hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2022/01/22/image1-3.png)

**Porting Assistant for .NET**

Porting Assistant for .NET is an open source analysis tool that reduces the manual effort and guesswork involved in porting .NET Framework applications to .NET Core 3.1, .NET 5, or .NET 6. 
Carlos Santos walks you through how to use the standalone version of Porting Assistant for .NET to modernise a Web Forms application to Blazor with the Web Forms starter project of eShopOnBlazor in his post, [Modernizing ASP.NET Web Forms applications to Blazor using Porting Assistant for .NET](https://aws-oss.beachgeek.co.uk/1a9) [hands on]

**Other posts worth checking out**

Last week, these posts also caught my eye.

* [How Prime Video updates its app for more than 8,000 device types](https://aws-oss.beachgeek.co.uk/1b9) a look at how Prime Video uses Rust and WebAssembly to significantly improve performance, stability, CPU consumption, and reduce the memory utilisation.
* [Manage AWS account alternate contacts with Terraform](https://aws-oss.beachgeek.co.uk/1b4) will explain how you can automate the set up and management of alternate contacts across all of your member accounts within an AWS Organisations using Terraform’s infrastructure-as-code module
* [Deploy and Manage Gitlab Runners on Amazon EC2](https://aws-oss.beachgeek.co.uk/1ac) guides you through utilising Infrastructure-as-Code to automate Gitlab Runner deployment and administrative tasks on Amazon EC2
![arch](https://d2908q01vomqb2.cloudfront.net/7719a1c782a1ba91c031a682a0a2f8658209adbf/2021/10/14/fig1arc-1.png)
* [Create an Amazon CloudWatch dashboard to monitor Amazon RDS for PostgreSQL and Amazon Aurora PostgreSQL](https://aws-oss.beachgeek.co.uk/1ae) helps you build a dynamic dashboard to monitor Amazon Relational Database Service (Amazon RDS) for PostgreSQL and Amazon Aurora PostgreSQL–Compatible Edition databases.
* [Overview of security best practices for Amazon RDS for PostgreSQL and Amazon Aurora PostgreSQL-Compatible Edition](https://aws-oss.beachgeek.co.uk/1af) is an overview of different options available with both Amazon RDS for PostgreSQL or Aurora PostgreSQL and natively with the PostgreSQL engine to run your databases securely on AWS. We discuss network security, database security, and data encryption options.

### Quick updates

**Apache Airflow**

You can now create Apache Airflow 2.2 environments on Amazon Managed Workflows for Apache Airflow (MWAA). Apache Airflow 2.2 is the latest version of the popular open-source tool that helps customers author, schedule, and monitor workflows. Further, MWAA will install Python requirements, provider packages, and plugins on the Airflow web server starting with 2.2 environments. I know a lot of customers have been asking for this feature.

### Videos of the week

If you missed it last week, we had a number of sessions as part of Open Cloud Innovations, featuring a number of sessions which you can now check out on demand.

**Open Cloud Innovations - keynote**

Deepak Singh, Vice President of AWS Compute services kicks things off, and talks a little about our approach to open source.

{{< youtube 6En_Bdv3C0U >}}

**Open Cloud Innovations - AWS Heroes Panel **

Catch up with AWS Heroes Liz Rice, Erica Windisch, Brian LeRoux, & Casey Lee while they discuss critical components, common pathways, and best practices for achieving real business outcomes with Open Source.

{{< youtube 4wpAYzdMNCw >}}

Read the full story in, [AWS Heroes Panel spotlights open-source community, security and funding](https://aws-oss.beachgeek.co.uk/1am)

**Future Founders**

OpenUK are doing a tremendous job helping folk understand more about the business of open source. In their first session, join a great line up of Alexis Richardson, David Mytton, and Liz Rice which is expertly hosted by Matt Barker in Why found an Open Source Business?

{{< youtube Dk_k7nSdPNU >}}


### Events for your diary

If you have an event you want me to publish here, please contact me and I will include it in this listing. 

**FOSDEM'22**
**5th/6th February**

Every year, thousands of developers of free and open source software from all over the world gather at the event in Brussels. You can check out the [schedule](https://aws-oss.beachgeek.co.uk/1b5), to find out more about what is on. There are so many great sessions, this really is an unmissable event. Whilst I will not be there in person, I will be attending online, as their online/virtual coverage is excellent.

Find out more on the registration page, [FOSDEM'22](https://fosdem.org/2022/)

**AWS HPC Speeds and Feeds**
**February 9, 2022 | 8:30AM - 10:00AM PST**

Over the past year, AWS HPC has introduced a host of new HPC products and services (many of them using open source technologies and project) to help today's scientists, engineers and researchers to run their workloads at scale for less cost and faster. Join us to hear directly from the engineers to learn more about the latest and greatest innovations from AWS HPC. To find out more about the talks, read the blog post [Join us for our HPC “Speeds n’ Feeds”](https://aws-oss.beachgeek.co.uk/1b0) to find out more, and use [this link to register](https://aws-oss.beachgeek.co.uk/1b1).

**Cloud DevSecOps with Bridgecrew and Terraform**
**Thursday, February 10th at 2pm GMT**

From scanning infrastructure as code (IaC) for security misconfigurations to implementing automated DevSecOps workflows, this workshop will provide a hands-on experience to automate your cloud security.

Read more and register, [AWS Dev Day Cloud DevSecOps with Bridgecrew and Terraform](https://aws-oss.beachgeek.co.uk/1ay)

**HashiTalks 2022**
**Thursday, Feb 17th**

The 24-hour HashiTalks is back for its fourth edition on Thursday, February 17. Tune-in to hear from and learn with fellow practitioners.

Find your local chapter, find more details and [register here](https://aws-oss.beachgeek.co.uk/1b3).


**OpenSearch**
**Every Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting - Feb2022](https://aws-oss.beachgeek.co.uk/1az)

**GitOpsCon Europe**
**May 17th, Valencia Spain**

GitOpsCon Europe is designed to foster collaboration, discussion, and knowledge sharing on GitOps. This event is aimed at audiences that are new to GitOps as well as those currently using GitOps within their organisation. Get connected with others that are passionate about GitOps. Learn from practitioners about pitfalls to avoid, hurdles to jump, and how to adopt GitOps in your cloud native environment.

The event is vendor-neutral and is being organised by the CNCF GitOps Working Group. Topics include getting started with GitOps, scaling and managing GitOps, lessons learned from production deployments, technical sessions, and thought leadership.

Read more about this from the official page [here](https://events.linuxfoundation.org/gitopscon-europe/).


### CFP

**GitOpsCon**
**CFP closes Feb, 14th**

GitOpsCon Europe (#GitOpsCon) is designed to foster collaboration, discussion, and knowledge sharing on GitOps. This event is aimed at audiences that are new to GitOps as well as those currently using GitOps within their organization. Get connected with others that are passionate about GitOps. Learn from practitioners about pitfalls to avoid, hurdles to jump, and how to adopt GitOps in your cloud native environment.

The CFP is now open, and you can read more about, and [submit your own session here](https://aws-oss.beachgeek.co.uk/1b2).

**Apache Airflow**
**CFP closes March, 14th**
A heads up to folks who are interested in all things Apache Airflow. Apache Airflow Summit 2022 has been announced and the call for papers (cfp) is now open. The bar for sessions is always very high, so looking forward to this event already.

If you have an idea for a talk, why not submit one via the cfp process. Check out the event, [Apache Airflow Summit 2022](https://aws-oss.beachgeek.co.uk/19e)

If you maybe have wanted to do a session, then I am very happy to help with feedback or coaching to help you feel more comfortable in creating and/or delivering your session. If this something that has been on your mind, but you just needed a little support, PLEASE get in touch.

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)