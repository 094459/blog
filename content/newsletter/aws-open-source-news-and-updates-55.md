---
title: 'AWS open source news and updates #55'
date: '2021-02-08'
tags : [ oss-newsletter ]
---
## February 8th, 2021 - Instalment #55

Newsletter #55. 

Another newsletter full of great content for you this week. Make sure you read the essential read this week, Rights Ratchet Model, keep on top of the latest news on the fork of Elasticsearch, some events for your diary, more great videos, a new workshop and of course the usual open source projects and posts from the community and AWS. Pick of the week has to be Ian Mckay's new open source project, iamlive - make sure you check it out in the projects section below. 

As always, I am always eager to hear from you about your projects or blogs/solutions you have been working on so please get in touch if you would like me to share your projects here.

**Essential read this week**

There have been many things said and written over the past few weeks about Elastic recent open source licensing changes. In this post, [A Bit Of A Stretch](https://aws-oss.beachgeek.co.uk/54) Simon Phipps articulates better than most on this topic, and uses the "Rights Ratchet Model" to describe the open source exploitation model that is being leveraged. A great read and well worth 10 minutes of your time to digest.

**Elasticsearch**

Kyle Davis shared some more news from the Open Distro for Elasticsearch community last week in [Update from the fork team: Feb 3](https://aws-oss.beachgeek.co.uk/56) and [Feb 5 Fork Update](https://aws-oss.beachgeek.co.uk/5n), sharing some key data points on how the forks of Elasticsearch and Kibana are going. I will continue to share these here, but why not join the community and attend their regular meet ups to stay ahead.

### Events for your diary

**Innovate AI/ML**
**Feb 24th**

Last week I shared that I have been putting together some blog posts to support my session at the [Innovate AI/ML event](https://aws.amazon.com/events/aws-innovate/machine-learning/online/emea/?sc_channel=em&sc_campaign=EMEA_FIELD_WEBINAR_innovate-AIML_20210224_7014z000001MJbu&sc_medium=em_&sc_content=REG_t1_field&sc_geo=emea&sc_country=mult&sc_outcome=reg&sc_publisher=aws&trkCampaign=emea21_innovatemlq1&trk=em_emea21_innovatemlq1_ricardosueiras) happening on Feb, 24th. I have been working on more posts, and this week I managed to complete the fourth and fifth posts which you can find below. Use the [sign up link here](https://aws.amazon.com/events/aws-innovate/machine-learning/online/emea/?sc_channel=em&sc_campaign=EMEA_FIELD_WEBINAR_innovate-AIML_20210224_7014z000001MJbu&sc_medium=em_&sc_content=REG_t1_field&sc_geo=emea&sc_country=mult&sc_outcome=reg&sc_publisher=aws&trkCampaign=emea21_innovatemlq1&trk=em_emea21_innovatemlq1_ricardosueiras) to register for this event.

**Apache Kafka**
**Feb 25th**

[Building ML-driven streaming applications with Apache Kafka](https://aws-oss.beachgeek.co.uk/4y) join Joseph Morais from Confluent and Kanchan Waikar from AWS in this webinar to learn how to build Apache Kafka®-based streaming applications backed by machine learning models. The event is across three time zones so whether you are in Asia, Europe or the Americas, there will be a time you can attend.

**CDK Day**
**April 30th**

Announced this week was the second [CDK Day](https://sessionize.com/cdkday/), which will be on April 30th. Check out [the web page](https://sessionize.com/cdkday/) to find out more about the first CDK Day, which was incredible. This second event promises to be even better. The CFP is open until the 19th of March. Check out this supporting blog post, [CDK Day CFP Is Open!!!!](https://aws-oss.beachgeek.co.uk/4v) from Matt as to what to expect and what they are looking for when it comes to sessions.

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Ian Mckay, Michael Labieniec, Mike George, Joseph Morais, Kanchan Waikar, Matt Coulter, Peng Su, Shan Huang, Denis Gladkikh, Carlos Zambrano, John Preston, Simon Phipps, Anton Babenko, Dave Horton, Anoop Rachamadugu, Rodrigue Koffi, Roberto Meda,  Ben Smith, Abdullahi Olaoye, Alolita Sharma, Nizar Tyrewalla, Robert Fratto, Imaya Kumar Jagannathan, William Lee and Kyle Davis.


Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

**iamlive**

[iamlive](https://aws-oss.beachgeek.co.uk/5p) the latest open source project from AWS Hero Ian Mckay, that is a very nice tool to help you generate basic IAM policies by from AWS client-side monitoring. Take a look at this demo on the project's GitHub repo to get a better idea.

![demo](https://raw.githubusercontent.com/iann0036/iamlive/assets/iamlive.gif)

**terraform-aws-pricing**

[terraform-aws-pricing](https://aws-oss.beachgeek.co.uk/55) is an open source project from AWS Community Hero Anton Babenko that is a Terraform module which calculates price of AWS infrastructure (from Terraform state and plan). I think this is an excellent concept and something I used to advise when helping organisations transition to the Cloud, building strong economic methods and techniques into the design and architecture methodologies. Anton shares other options you might want to look at. Great stuff Anton.

**amplify-flutter-sample**

[amplify-flutter-sample](https://aws-oss.beachgeek.co.uk/5s) this sample project from Michael Labieniec provides an example application using the Amplify Framework and Flutter.

**aws-iam-management-as-code**

[aws-iam-management-as-code](https://aws-oss.beachgeek.co.uk/4w) is a MIT licensed open source project from Peng Su and Shan Huang at Alpha Health that helps you to create IAM policies as code, defining a set of atomic permissions and using a tree data structure with multi-level inheritance. This allows you to better manage via best practices such as source control, those policies.

To understand more, you can read their supporting blog post from Peng Su and Shan Huang, IAM Management as Code. The post takes a look at the context and background that led to the creation of this solution. It is very detailed and shows the specific workflows that they were looking to automate and protect. If you have similar requirements, then take a look at this project.

![problem-space](https://github.com/alpha-health/aws-iam-management-as-code/raw/main/images/IAM_as_code_Design.svg)

### Community open source posts

**AWS CDK and cdkpatterns.com**

[How AWS CDK released this Architect from 'the ivory tower'](https://aws-oss.beachgeek.co.uk/4u) Matt Coulter with an essential post you should read this week on cdkpatterns.com, what it is, why it exists and why you should care. There is something so re-assuring about design patterns, and it certainly appeals to the part of me that craves order and neatness. Check this post out then, and also while I have your attention, make sure you check out CDK Day (see above)

**Apache Airflow**

[Adding Custom Operators on Amazon Managed Workflows for Apache Airflow](https://aws-oss.beachgeek.co.uk/50) Carlos Zambrano provides yet more Apache Airflow content this week, although this is an older post which somehow I missed. Carlos walks you through creating a custom plugin that create a notification plugin that allows your Apache Airflow workflows to notify your Slack channels. This is a nice walkthrough if you want to know more about creating custom plugins you can use in your workflows. Source code (and DAGs) are provided in his [GitHub repository](https://aws-oss.beachgeek.co.uk/51).

Adding to Carlos' post I have a couple more blog posts as part of the series I am doing. First up we have [Part 4 - Interacting with Amazon Managed Workflows for Apache Airflow via the command line](https://aws-oss.beachgeek.co.uk/4s) where I explore the different options you have to interact with Amazon Managed Workflows for Apache Airflow (MWAA) and then [Part 5 - A simple CI/CD system for your development workflow](https://aws-oss.beachgeek.co.uk/4t) which walks you through how you can set up a simple CI/CD pipeline to simplify your workflow development but also reduce the access requirements to your AWS environment.
 
**AWS Amplify**

[Analyzing AWS Amplify Access logs. Part 2.](https://aws-oss.beachgeek.co.uk/4z) Denis Gladkikh is back with the second part as he looks at more ways of taking the information from your AWS Amplify applications, in particular how you can use AWS services like AWS Lambda and AWS Athena to generate reports that will help you stay on top of your apps.

**compose-x**

[Use your docker-compose files as a CloudFormation template](https://aws-oss.beachgeek.co.uk/52) another great post from John Preston takes a look at a new feature of this project, ECS Compose-X macro, its origins in the path that was AWS CloudFormation Macros and how ECS Compose-X macro looks to achieve the same thing but instead of using a CloudFormation template as the source, you can use your docker-compose files.

### AWS open source posts

**AWS Distro for OpenTelemetry**

[AWS Distro for OpenTelemetry adds partner exporters for metrics and traces](https://aws-oss.beachgeek.co.uk/5i) Alolita Sharma and Nizar Tyrewalla write about the latest release of AWS Distro for OpenTelemetry (ADOT) version 0.7.0 adds support for four more partner monitoring solutions—Datadog, Dynatrace, New Relic, and Splunk—enabling customers to send correlated metrics and traces using OpenTelemetry.

**AWS Amplify and Vue 3**

[Amplify JavaScript releases support for Vue 3](https://aws-oss.beachgeek.co.uk/5k) William Lee with a post that talks about how Amplify JavaScript now supports version 3 of Vue JS. The post walks you through a quick example application build a chatbot app quickly thanks to the capabilities that AWS Amplify gives you.

**Prometheus**

This week we have a few posts on Prometheus.

First up we have Imaya Kumar Jagannathan with [Set up cross-region metrics collection for Amazon Managed Service for Prometheus workspaces](https://aws-oss.beachgeek.co.uk/5f) who follows on from a previous blog post around how to ingest metrics from your applications running on Amazon EKS clusters in a single region, to how you can scale that up and do this across multiple AWS regions. This post is a practical walkthrough that you can follow to understand all the moving pieces.

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/01/28/ijaganna_Cross-Region-Metrics-Prometheus_f1.jpg)

Following that we have [Using Amazon Managed Service for Prometheus to monitor EC2 environments](https://aws-oss.beachgeek.co.uk/5b) from Rodrigue Koffi, with a great post on how to use the Amazon Managed Service for Prometheus (AMP) to ingest your metrics both in AWS or your on premises workloads.

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/01/29/koffir_AMP-monitored-EC2_f1.jpg)

Finally we have Mike George's post, [Monitor and scale your Amazon ECS on AWS Fargate application using Prometheus metrics](https://aws-oss.beachgeek.co.uk/5o) where Mike shows you how you can monitor and scale your Amazon Elastic Container Service (Amazon ECS) on AWS Fargate applications using Prometheus metrics.

![scaling](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2021/02/05/Figure9-1-1024x685.png)

**Grafana**

Not to be left out, we also have a couple of posts on Grafana this week.

First up, collaborating on [Configuring Grafana Cloud Agent for Amazon Managed Service for Prometheus](https://aws-oss.beachgeek.co.uk/5j) are Robert Fratto, Imaya Kumar Jagannathan, and Alolita Sharma talking about the Grafana Cloud Agent, a lightweight alternative to running a full Prometheus server. This makes it easier to collect Prometheus-compatible metrics and scale to distribute scrape load by deploying one process per node. Read the post to find out how to do this, with detailed steps to guide you.

Following that we have Imaya Kumar Jagannathan with another post. In [Setting up Grafana on EC2 to query metrics from Amazon Managed Service for Prometheus](https://aws-oss.beachgeek.co.uk/5g) he covers how to set up a self hosted Grafana server running on AWS EC2 and integrate this so that you create a dashboards and visualisations and ingest data from within your Amazon Managed Service for Prometheus (AMP).

Also, if you are interested in Grafana, check out my Apache Airflow blog post on logging and monitoring which shows how you can integrate your Apache Airflow metrics from AWS CloudWatch with Grafana.

**AWS ParallelCluster**

[AWS ParallelCluster post-install: EnginFrame and DCV Session Manager Broker](https://aws-oss.beachgeek.co.uk/5c) Roberto Meda writes and shows you how to automatically install EnginFrame and DCV Session Manager Broker via an AWS ParallelCluster post-installation script. AWS ParallelCluster is an open source cluster management tool that simplifies deploying and managing HPC clusters, and NICE EnginFrame is an advanced web front end for accessing technical and scientific applications in the cloud. The code for this article is available on the [GitHub repo](https://aws-oss.beachgeek.co.uk/5d).

**NodeJS**

[Node.js 14.x runtime now available in AWS Lambda](https://aws-oss.beachgeek.co.uk/5e)  Benjamin Smith with a quick post to announce the support with AWS Lambda of the Node.js 14.x runtime. All the details you need to know, including the deprecation schedule you should take note of.

**Cloud Custodian**

[Continuous deployment of Cloud Custodian to AWS Control Tower](https://aws-oss.beachgeek.co.uk/5h)
 Abdullahi Olaoye with a post that talks how Cloud Custodian, an open source cloud security, governance, and management tool,  enables users to keep their Amazon Web Services (AWS) environment secure and well managed by defining policies. If you are looking to scale your compliance, then this post is just what you need to read.
 
 ![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/01/26/olaoyea_CD-Cloud-Custodian_f1.jpg)

**Database Migration** 
 
[Migrating a commercial database to open source with AWS SCT and AWS DMS](https://aws-oss.beachgeek.co.uk/5l) Hooman Hamilton shares some guidance on how you can approach migrating your current database to an open source data, using tools such as the AWS Database Migration Service and Schema Conversion Tool.

### AWS Partners

**Chef InSpec**

[Testing EC2 Image Builder pipelines using Chef InSpec](https://aws-oss.beachgeek.co.uk/5a) Anoop Rachamadugu writes about how you can use an open source project, Chef InSpec, to walk through how you can use it in your build pipeline. Chef InSpec is an open-source framework for testing and auditing your applications and infrastructure, and it works by comparing the actual state of your system with the desired state that you write in Chef InSpec code. It then generates the findings in a report. So find out more how you might be able to use this project by reading this post.

### Case Studies

[How Baqend built a real-time web analytics platform using Amazon Kinesis Data Analytics for Apache Flink](https://aws-oss.beachgeek.co.uk/5m) in this post, customer Baqend share their journey from a high-volume batch analytics solution to a continuous aggregation pipeline using Kinesis Data Analytics for Apache Flink which allowed them to reduce to less than a minute of end-to-end latency from data ingestion to visual output in the dashboard.

Baqend is one of the fastest-growing software as a service (SaaS) startups in Germany, serving over 5,000 business customers with more than 100 million monthly users and $2 billion EUR revenue per year.

![arch](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2021/02/04/BDB-1045-4.png)

### Workshops

[CDK with Next.js and AWS Amplify Workshop](https://aws-oss.beachgeek.co.uk/53) Nader Dabit has built a new workshop that will help you to build a full stack cloud application using lots of great open source projects such as Next.js, AWS CDK, AWS AppSync, and AWS Amplify. In this workshop you will learn how to use these technologies by building an app that is a multi-user blogging app with a markdown editor.

### Videos of the week

**HashiCorp Boundary**

A regular feature now, the Containers from the Couch crew show you how you can secure your Kubernetes API access using Hashicorp's open source project [Boundary](https://aws-oss.beachgeek.co.uk/58).

{% youtube tb5k4MPNgJM %}

**Node Red and Amazon Lex**

Node Red is probably my most favourite open source project, and whilst I have not had the opportunity to use it much lately, I came across this video from Dave Horton who takes a look at how you can integrate the open source CPaaS project, [jambonz](https://aws-oss.beachgeek.co.uk/57) with Amazon Lex all through the magic that is Node Red.

{% youtube k97DpGmDytg %}

### Quick updates

**AWS Copilot**

AWS Copilot  launched version 1.2 which now provides more deployment capabilities for applications hosted on Amazon Elastic Container Service (Amazon ECS). AWS Copilot now lets you add a pipeline to safely deploy resources from AWS CodeCommit repositories, in addition to the existing GitHub repository option. All deployments from AWS Copilot now use ECS deployment circuit breakers by default, letting you detect and roll back failed deployments quickly. Finally, you can view the progress of your deployment with a new progress UI displayed in your CLI shell, giving you more insight to the status of your deployment and resources being modified.

You can also refer to the AWS Copilot release notes for v1.2 [here](https://github.com/aws/copilot-cli/releases/tag/v1.2.0).

**AWS Amplify**

AWS Amplify Hosting now allows users to monitor metrics for Amplify hosted applications in near real-time. Amplify provides a dashboard with metrics for Incoming requests, Bytes downloaded, Bytes uploaded, 4XX/5XX errors, and latency. You can create CloudWatch alarms in the Amplify console that send notifications when specific criteria are met. An alarm watches a single metric and sends an Amazon Simple Notification Service notification when the metric breaches the threshold for a specified number of evaluation periods.

**NodeJS**

You can now author AWS Lambda functions in Node.js 14 and use its new features, such as top-level-await, enhanced diagnostics, modifications of the streams APIs, and a revised JavaScript engine for better performance. Lambda functions written in Node.js 14 run on Amazon Linux 2, the latest generation of Amazon Linux. To learn more about writing functions in Node.js 14, see the Node.js programming model in the Lambda documentation.  Read more [here](https://aws-oss.beachgeek.co.uk/59).


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen).
