---

title: 'AWS open source news and updates #100'
date: '2022-02-14'
tags : [ oss-newsletter, aws open source, Rust, OpenSearch, Apache Airflow, mwaa, Prometheus, Grafana, Trivy, AWS ParallelCluster, Terraform, Amazon EKS, Envoy, KVM, Linux, Wordpress, Micronaut, Kotlin, Graal VM, AWS Lambda Powertools, Traefik Proxy, Apache Iceberg, Dokku, Apache Cassandra, MemQ,]

---

## Feb 14th, 2022 - Instalment #100

Newsletter #100. 

Happy Valentines everyone, and welcome to this landmark 100st edition of this newsletter. This week we celebrate the love that many builders have for open source with more great new open source projects and content. Cuddle up to new projects that will help you build scalable systems, simplify your work with AWS DynamoDB, integrate your .NET applications with OpenSearch, keep on top of your VPC networks, and more. After checking those out, you can read the open source love letters featuring topics on Rust, Apache Airflow, Trivy, Envoy, KVM, Micronaut, Kotlin,  Traefik Proxy, Apache Cassandra, MemQ and many more. If you prefer video content, then this week we have videos covering Apache Iceberg, Dokku, and Trivy. We feature a new WhitePaper on federated identity use cases and solutions for Apache Airflow, and wrap up with open source events, meetups and webinars happening over the next week or so.


### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Ambud Sharma, Shane Millar, Jeremy Persing, Justin Pirtle, Joan Morgan, Jim Thario, Mike Rizzo, Steve Coplan, Scott Morrison, Shovan Das, Mark Sailes, Sakis Kaliakoudas, Ivica Kolenkaš, Michael Matur, Shane Miller and Carl Lerche.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest open source projects

#### Community

**joiful-dynamo**

[joiful-dynamo](https://aws-oss.beachgeek.co.uk/1c9) is an open source library from [Chocolate Soup](https://twitter.com/ChocolateSoupCA/status/1491829547943268354) uses Typescript Decorators to easily let developers to manage data models. This IS NOT a complete ORM, but a facilitator to make the experience of using AWS DynamoDB easier and with less code repetition. 

**amazon-managed-service-for-prometheus**

[amazon-managed-service-for-prometheus-roadmap](https://aws-oss.beachgeek.co.uk/1cd) is the public space where you can add and influence feature requests for the Amazon Managed Service for Prometheus roadmap and allows all AWS customers to give direct feedback.

**amazon-managed-grafana**

[amazon-managed-grafana-roadmap](https://aws-oss.beachgeek.co.uk/1ce) is the public roadmap for Amazon Managed Grafana. We share information about what we are working on and equally, you can use this repo to provide feedback and suggest features. Note that this roadmap presents features that we are considering developing, however it does remain subject to change from time to time.

#### Tools

**opensearch-net**

[opensearch-net](https://aws-oss.beachgeek.co.uk/1cj) this project is the official high-level .NET client of OpenSearch.

**aws-vpc-network-resource-counter**

[aws-vpc-network-resource-counter](https://aws-oss.beachgeek.co.uk/1ch) this looks like an incredibly helpful and useful project, which I am going to deploy in my own AWS environment. This project is intended to help with tracking networking resources in a single Amazon VPC. It will create an AWS Lambda function that will count specific network resources and create CloudWatch metric for each measurement. The measurements are published at an interval of your choice. Check the README for more details.

**automated-prefix-list-to-security-group-synchronization**

[automated-prefix-list-to-security-group-synchronization](https://aws-oss.beachgeek.co.uk/1cf) this repo provides a solution designed to automatically synchronise private IP addresses for ENIs associated with a Security Group to a Managed Prefix List in the same or different region as the Security Group. This can enable strict IP based filtering across region or when crossing a Transit Gateway, as well as when using a middle box appliance in a VPC where security group referencing is not supported. To help you get started with this, Scott Morrison and Shovan Das have put together a blog post, [Automated VPC prefix list population for cross-Region and in-Region security group referencing](https://aws-oss.beachgeek.co.uk/1cg)

![arch](https://d2908q01vomqb2.cloudfront.net/5b384ce32d8cdef02bc3a139d4cac0a22bb029e8/2022/02/08/AutoSG2PL.png)

#### Demos and Samples

**aws-virtual-waiting-room**

[aws-virtual-waiting-room](https://aws-oss.beachgeek.co.uk/15i) AWS Virtual Waiting Room solution helps absorb and control incoming user requests to your website during an unusually large burst of traffic, usually due to a large-scale event. Justin Pirtle, Joan Morgan, and Jim Thario have put together this blog post, [Introducing AWS Virtual Waiting Room](https://aws-oss.beachgeek.co.uk/1c3)  to help you get started and walk you through the key components of this project and how to get it up and running.

![arch](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2022/02/09/waiting-room1.jpg)

**subtitle-generator-cdk-app**

[subtitle-generator-cdk-app](https://aws-oss.beachgeek.co.uk/1ci) this sample provisions the infrastructure, backend, and frontend required for a subtitle generator app with AWS CDK.

![demo](https://github.com/aws-samples/subtitle-generator-cdk-app/blob/master/assets/sample.gif?raw=true)

**pizza-delivery-tracker**

[pizza-delivery-tracker](https://aws-oss.beachgeek.co.uk/1ck) This sample project contains a map-based pizza ordering app with real-time tracking of your delivery. The browser-based frontend shows a map with your current location and lists all pizza places nearby. You can select one to order a pizza from there. Shortly after ordering, a delivery route is calculated and you can monitor the delivery progress in real-time while the pizza icon is moving closer and closer to your location on the map.

![demo](https://raw.githubusercontent.com/aws-samples/pizza-delivery-tracker/main/demo.gif)

### AWS and Community blog posts

**Rust**

During re:Invent, one of the most popular sessions in the Open Source track was Using Rust to minimise environmental impact, presented by Shane Miller and Carl Lerche.

{{< youtube yQZaBtUjQ1w >}}


I am delighted they are both back, this time writing on this topic in their post [Sustainability with Rust](https://aws-oss.beachgeek.co.uk/1cu) and diving a little deeper into this topic with plenty of nice data points. This weeks must read post.

![table](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2022/02/09/sust-rust-3.png)

**Trivy**

Aqua Security’s open source project [Trivy](https://aws-oss.beachgeek.co.uk/1cc) is a scanner for vulnerabilities and configuration issues in container images, file systems, and Git repositories. In the post, [Identify Security Risks in AWS CloudFormation Templates with Trivy](https://aws-oss.beachgeek.co.uk/1cb) Steve Coplan looks at a new feature of this project that now lets you scan AWS CloudFormation templates to help developers better identify and remediate security issues within infrastructure as code (IaC) templates.

**KVM**

Simeon Adeniyi Oladokun has put together a great post showing you how you can deploy an AWS DataSync agent on Linux KVM hypervisor host, providing a cost-effective hypervisor solution that creates a simpler and easier migration of large datasets from on-premises storage systems to AWS storage services. See how by following along in, [Simplify data migrations using an AWS DataSync agent on Linux KVM Hypervisor](https://aws-oss.beachgeek.co.uk/1c5)
[hands on]

**Envoy**

In his post, [Using a CI/CD Pipeline to Inject an Envoy Proxy Sidecar Container into an Amazon ECS Task](https://aws-oss.beachgeek.co.uk/1c4) Mike Rizzo demonstrates how you can use a pipeline to inject an Envoy proxy sidecar container into your ECS tasks so that they can be used with AWS App Mesh. Why would you want to do this I can hear you asking...as Mike puts in his post:
>
> By using a pipeline to build the required task and service definition files, developers can focus on building service logic with minimal effort required on service configuration. The pipeline can also be used to enforce any deployment conventions and policies as may be required by a platform team.
>

[hands on]

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2022/02/08/3-ServicePipelinesArchitecture.png)

**MemQ**

[MemQ](https://aws-oss.beachgeek.co.uk/1cs) is a new open source PubSub system from the folks at Pinterest. It uses a decoupled storage and serving architecture similar to Apache Pulsar and Facebook Logdevice, but relies on a pluggable replicated storage layer i.e. Object Store's such as Amazon S3, for storing data. Ambud Sharma, a tech lead at Pinterest, discusses MemQ in more details, and shares how it has been powering near-real-time data transportation use cases whilst being over 90% more cost-efficient in some cases. Read more in the post, [MemQ by Pinterest: An efficient, scalable, cloud-native publish/subscribe system](https://aws-oss.beachgeek.co.uk/1cr)

![arch](https://d2908q01vomqb2.cloudfront.net/e1822db470e60d090affd0956d743cb0e7cdf113/2022/02/10/MemQ_Internals_Diagram-1024x489.png)

**Micronaut + Kotlin + Graal VM**

Sakis Kaliakoudas has put together this post, [Serverless on AWS Lambda With Micronaut + Kotlin + Graal VM](https://aws-oss.beachgeek.co.uk/1cm) that takes a look at the technology stack decisions for Caribou, a developer tool that helps developers use data-driven insights to manage their technical debt. There is a hint in the title I guess, but read on to find out more and why.

**Apache Airflow**

In his post, [My Thoughts on AWS Managed Workflows for Apache Airflow](https://aws-oss.beachgeek.co.uk/1cn) Ivica Kolenkaš shares his thoughts and observations on Amazon Managed Workflows for Apache Airflow (MWAA) and whether you it can replace self-hosted Airflow in his use cases.

I also started the first in a series of blog posts that will share my experiences as I look to contribute to the upstream Apache Airflow project, in my post [Contributing to the Apache Airflow project](https://aws-oss.beachgeek.co.uk/1cq). 

**traefik-proxy**

Michael Matur shows you how configure your Ingress Controller Traefik Proxy with the support of HTTP/3 on an EKS cluster in his post, [How to use Traefik Proxy and HTTP/3 on AWS EKS](https://aws-oss.beachgeek.co.uk/1co) [hands on]

**Other posts worth checking out**

* [Introducing AWS ParallelCluster multiuser support via Active Directory](https://aws-oss.beachgeek.co.uk/1c2) takes a look at ParallelCluster 3.1 which now supports multiuser authentication based on Active Directory (AD)
* [Running WordPress on Amazon EKS with Amazon EFS Intelligent-tiering](https://aws-oss.beachgeek.co.uk/1c6) will show you how to deploy a containerised instance of WordPress using the Amazon Elastic Kubernetes Service (EKS) with persistent file storage leveraging EFS with Intelligent-tiering enabled for cost optimisation
* [Deploy Python Application using AWS App Runner](https://aws-oss.beachgeek.co.uk/1cp) provides a walkthrough on how to deploy a containerised Python application that interacts with Amazon DynamoDB using AWS App Runner.
* [IAM authentication with Amazon RDS for MariaDB](https://aws-oss.beachgeek.co.uk/1ct) helps you to set up an RDS for MariaDB instance and connect to the instance using IAM database authentication

**Podcast**

[Episode #168](https://aws-oss.beachgeek.co.uk/1cl), AWS Lambda Powertools Java on the Airhack.fm podcast features our very own Mark Sailes talking about all things AWS Lambda Powertool. 

### Whitepapers

**Apache Airflow**

This week we have a white paper that dives deep into and provides a step-by-step guide on how to build a solution that allows using federated identities to seamlessly access private Amazon MWAA environments securely.

Grab a cup of your favourite beverage and dive into [Accessing a private Amazon MWAA environment using federated identities](https://aws-oss.beachgeek.co.uk/1c7)

### Quick updates

**Terraform**

Version 4.0 of the HashiCorp Terraform AWS provider brings usability improvements to data sources and attribute validations along with a refactored S3 bucket resource. Check out the release notes with links to the code and modules, [Terraform AWS Provider 4.0 Refactors S3 Bucket Resource](https://aws-oss.beachgeek.co.uk/1c8)

### Videos of the week

**Apache Iceberg**

Apache Iceberg is a high-performance format for huge analytic tables. Iceberg brings the reliability and simplicity of SQL tables to big data, while making it possible for engines like Spark, Trino, Flink, Presto, and Hive to safely work with the same tables, at the same time. Dremio walks you through how to set up the Iceberg Glue connector, write an Iceberg table using AWS Glue, and analyse it with Dremio.

{{< youtube lFShBi5Qkdg >}}

**Trivy**

Perfect timing given the post on Trivy above, last week I had a quick look at this video from Rawkode Academy that takes a look at continuously scanning for misconfiguration and vulnerabilities within your container images with Aqua's open source project, Trivy.

{{< youtube 4jHmTEghEYU >}}

**Dokku**

Dokku is an open source platform as a service, and similar in some ways to Heroku, and services like that. In this video, Jeremy Persing shows you how to get this up and running on AWS.

{{< youtube D5WkX-oYhmI >}}

### Events for your diary

If you have an event you want me to publish here, please contact me and I will include it in this listing. 


**Apache Cassandra**
**Thursday, Feb 17th, 1PM PST**

Make sure you check out the AWS Twitch channel for a convo with Brian Houser from the Amazon Keyspaces (for Apache Cassandra) open-source team. He will be talking about OSS projects and contributions the team is working on. [http://twitch.tv/aws](http://twitch.tv/aws)


**HashiTalks 2022**
**Thursday, Feb 17th**

The 24-hour HashiTalks is back for its fourth edition on Thursday, February 17. Tune-in to hear from and learn with fellow practitioners.

Find your local chapter, find more details and [register here](https://aws-oss.beachgeek.co.uk/1b3).


**AWS | Databricks ML Dev Day Workshop**
**24 February, 9am – 11:30am GMT**

In this workshop you will get to learn about the current good practices for enterprises to use with powerful open source technologies to simplify and scale your data and ML efforts. Covering Delta Lake, Apache Spark, TensorFlow, XGBoost, scikit-learn and MLFlow, a lot of stuff is going to be covered so read the full details and register at [AWS | Databricks ML Dev Day Workshop](https://databricks.com/p/webinar/feb-2022-emea-aws-databricks-ml-dev-day-workshop)

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