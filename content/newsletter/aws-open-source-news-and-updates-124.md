---

title: 'AWS open source news and updates #124'
date: '2022-08-12'
tags : [ oss-newsletter, aws open source, OCSF, Open Cybersecurity Schema Framework, Cello, AWS CDK, Kubernetes, Karpenter, cdk8s, EKS Anywhere, AWS IoT Greengrass v2, PostgreSQL, Driftctl, Steampipe, Terraform, Grafana, Apache Spark, Deep Graph Library, Smithy, OpenSearch]

---

## August, 12th, 2022 - Instalment #124

**Welcome**

Welcome to edition #124 of the AWS open source newsletter. This is a very special edition as this will be the first edition that we cover in the new Build on AWS Open Source fortnight show on twitch.tv/aws. I hope some of you were able to attend, but if not don't worry we will be sharing links to the recording. To keep up to date on future episodes, make sure you follow [@buildonopen](https://twitter.com/buildonopen). The next episode will be on September 9th, so see you then. This will also be the last newsletter for the next two weeks as I will be on holiday, recharging and resting.

To celebrate the fact that we are in the holiday season, this week we have another bumper selection of projects for you to practice your open source four freedoms. First up we have "matano", an open source security lake platform for AWS, "granted-approvals" which provides a really nice way to implement controls and self service for access to your cloud services, "pike" a tool to help you assess the IAM permissions you need when creating infrastructure as code, "AFT-SSO-account-configuration" that lets you use Terraform to define SSO Group and SSO User access, "aws-aurora-rds-postgresql-excel-generator" a neat tool that allows you to export Excel worksheets directly from PostgreSQL, "amazon-codewhisperer-workshop" a new workshop for those who have preview access to Amazon Codewhisperer, "aws-eksd-eksa-hybrid" a very interesting project to help you get going with hybrid Kubernetes cluster, and many more projects.

We have blog posts and articles featuring Open Cybersecurity Schema Framework, Cello, AWS IoT Greengrass v2, PostgreSQL, Driftctl, Steampipe, Terraform, Grafana, Apache Spark, Deep Graph Library, Smithy, OpenSearch, and more. Make sure you check out this weeks videos which include a number of videos from Container Day earlier in the year, featuring some nice sessions on Karpenter, cdk8s, and EKS Anywhere. Finally, we have the events section featuring events that you need to check out.

**Open Cybersecurity Schema Framework**

[Open Cybersecurity Schema Framework](https://aws-oss.beachgeek.co.uk/1yl), or [OCSF](https://aws-oss.beachgeek.co.uk/1yl) was announced this week, and is an open-source project, delivering an extensible framework for developing schemas, along with a vendor-agnostic core security schema. AWS, together with a number of other organisations, are working together on this initiative which aims to help companies respond to cyberattacks more effectively. How does it do this? The idea is to help organisations respond to cyberattacks more effectively by simplifying and standardising data management.

Mark Ryland provides more details about this in his post, [AWS co-announces release of the Open Cybersecurity Schema Framework (OCSF) project](https://aws-oss.beachgeek.co.uk/1yu)


**Celebrating open source contributors**

The articles and projects shared in this newsletter are only possible thanks to the many contributors in open source. I would like to shout out and thank those folks who really do power open source and enable us all to learn and build on top of what they have created. 

So thank you to the following open source heroes: Kevin Stich, Brett Weaver, Jerome Kuptz, Sai Vennam, Ram Vennam, Justin Garrison, Irshad Buchh, Pavaan Mistry, James Woolfenden, Peter Bengtson, Lee Tickett, Philipp Garbe, Bob Tordella, Jon Udell, Jamal Arif, and Francesco Bersani.

### Latest open source projects

*The great thing about open source projects is that you can review the source code. If you like the look of these projects, make sure you that take a look at the code, and if it is useful to you, get in touch with the maintainer to provide feedback, suggestions or even submit a contribution.*

#### Tools

**matano**

[matano](https://aws-oss.beachgeek.co.uk/1z7) is an open source security lake platform for AWS. It lets you ingest petabytes of security and log data from various sources, store and query them in an open Apache Iceberg data lake, and create Python detections as code for realtime alerting. Matano is fully serverless and designed specifically for AWS and focuses on enabling high scale, low cost, and zero-ops. Matano deploys fully into your AWS account. Looks super interesting, and is on my todo list.

![architecture of matano](https://github.com/matanolabs/matano/blob/main/website/src/assets/diagram.png?raw=true)


**granted-approvals**

[granted-approvals](https://aws-oss.beachgeek.co.uk/1yx) is an open source privileged access management framework which makes requesting roles a breeze and looks super nice. Using this project you can set up your team members so they can request elevated permissions to your cloud environment and SaaS services. This one another project on my todo list!

![screenshot of project running](https://docs.commonfate.io/assets/images/approvals-home-77ec50087f6b7688162059cb078d35ef.png)

**pike**

[pike](https://aws-oss.beachgeek.co.uk/1yw) is a tool from James Woolfenden for determining the permissions or policy required for IAC code. As James points out in the README, its a work in progress so checkout the roadmap and ideas he has, and he is open to issues/PRs.

**AFT-SSO-account-configuration**

[AFT-SSO-account-configuration](https://aws-oss.beachgeek.co.uk/1yt) this project from Peter Bengtson allows you to use AFT (Account Factory for Terraform) to declaratively specify SSO Group and SSO User access to an account. Very nice indeed.

**autopkg-recipes**

[autopkg-recipes](https://aws-oss.beachgeek.co.uk/1yj) this repo contains official recipes for AWS products for the AutoPkg Community. AutoPkg is an automation framework for macOS software packaging and distribution, oriented towards the tasks one would normally perform manually to prepare third-party software for mass deployment to managed clients. To add this repository to your AutoPkg setup, run: ```autopkg repo-add aws/autopkg-recipes```

**aws-aurora-rds-postgresql-excel-generator**

[aws-aurora-rds-postgresql-excel-generator](https://aws-oss.beachgeek.co.uk/1yp) this project contains a PL/PGSQL Package to create EXCEL workbooks. This package enables developers to export data from an RDS or Aurora PostgreSQL database to Excel files using simple PL/PGSQL functions and procedures.

### Demos, Samples, Solutions and Workshops

**amazon-codewhisperer-workshop**

[amazon-codewhisperer-workshop](https://aws-oss.beachgeek.co.uk/1yr) if you have managed to get onto the Amazon Codewhisperer preview, then why not try this hands-on workshop that demonstrates how to leverage Amazon CodeWhisperer for building a fully fledged serverless app on AWS.

![architecture of codewhisperer workshop](https://github.com/aws-samples/amazon-codewhisperer-workshop/blob/main/images/architecture.png?raw=true)

**aws-eksd-eksa-hybrid**

[aws-eksd-eksa-hybrid](https://aws-oss.beachgeek.co.uk/1yn) this project will help you to get to know how to build and automate creation of development and prototype environments for hybrid software delivery using the AWS CDK to automate EKS Distro and EKS Anywhere environments provisioning for development purposes, allowing a seamless experience while standing up and standardising Kubernetes environments and applications deployment on top of EKS. It was designed to explore ways and best practices to abstract the challenges and complexities of deploying hybrid-EKS development infrastructure targeted at DevOps teams, allowing repeatable workload development and testing which can be easily integrated with existing CI/CD pipelines using a simple and consistent method, as needed. 

![architecture of eks hybrid solution](https://github.com/aws-samples/aws-eksd-eksa-hybrid/blob/main/images/EKShybridarchitecture-v3-numbered.png?raw=true)

**multi-cluster-gitops**

[multi-cluster-gitops](https://aws-oss.beachgeek.co.uk/1yv) This repo contains the implementation of a multi-cluster GitOps system that addresses the application development teams use cases, as well as the platform teams use cases. It shows how to extend GitOps to cover the deployment and the management of cloud infrastructure resources (e.g. Amazon RDS, Amazon DynamoDB, and Amazon SQS), in addition to the deployment and management of the native Kubernetes resources. It also shows how to use GitOps to perform cluster management activities (e.g. provisioning and bootstrapping a new cluster, upgrading an existing cluster, deleting a cluster, etc.)

![architecture of multi-cluster gitops](https://github.com/aws-samples/eks-multi-cluster-gitops/blob/main/doc/img/architecture.png?raw=true)

**aws-codepipeline-terraform-cicd-samples**

[aws-codepipeline-terraform-cicd-samples](https://aws-oss.beachgeek.co.uk/1yq) this repo provides a guide and ready to use terraform configurations to setup validation pipelines with end-to-end tests based on AWS CodePipeline, AWS CodeBuild, and AWS CodeCommit. Detail example and documentation covering all the configuration options you need.

**aws-cdk-java-codepipeline-codeartifact-sample**

[aws-cdk-java-codepipeline-codeartifact-sample](https://aws-oss.beachgeek.co.uk/1yk) this repo shows you how to create a pipeline that will automatically publish new Java package versions to private AWS CodeArtifact repository using AWS CodePipeline. All resources in this project are provisioned as IaC with AWS CDK in Java, making it easy for you to get up and running.

**aws-cdk-python-codepipeline-codeartifact-sample**

[aws-cdk-python-codepipeline-codeartifact-sample](https://aws-oss.beachgeek.co.uk/1yo) similar to the previous project, this repo shows you how to create a pipeline that will automatically publish new Python package versions to private AWS CodeArtifact repository using AWS CodePipeline. All resources in this project are provisioned as IaC with AWS CDK in Python, making it easy for you to get up and running.

**az-fail-away**

[az-fail-away](https://aws-oss.beachgeek.co.uk/1ys) This project provides a serverless infrastructure for updating the availability zones of autoscaling groups en masse.

![architecture of az-fail-away](https://github.com/aws-samples/az-fail-away/blob/main/images/architecture.drawio.png?raw=true)

### AWS and Community blog posts

**Smithy**

Smithy is an open source protocol-agnostic Interface Definition Language (IDL) and set of tools for generating clients, servers, documentation, and other artefacts. Smithy is Amazon’s next-generation API modelling language, based on our experience building tens of thousands of services and generating SDKs. In the post, [Introducing Smithy IDL 2.0](https://aws-oss.beachgeek.co.uk/1zb) Kevin Stich takes a look at this new release that focuses on improving the developer experience of authoring Smithy models and using code generated from Smithy models. Essential reading for this super cool project.

**Steampipe**

Regular readers will know about this project, Steampipe, an open source tool for querying cloud APIs in a universal way and reasoning about the data in SQL. In a follow on post, [Dashboards as code: A new approach to visualizing AWS APIs](https://aws-oss.beachgeek.co.uk/1z3),  Bob Tordella and Jon Udell collaborate to show how Steampipe’s can help you apply an infrastructure as code to managing your dashboards. [hands on]

![demo of steampipe dashboards](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2022/08/05/68747470733a2f2f6a6f6e7564656c6c2e696e666f2f737465616d706970652f7063692d62656e63686d61726b2d64617368626f6172642d76322d6c6f6f702e676966.gif)  

**Apache Spark**

In the post [Design patterns to manage Amazon EMR on EKS workloads for Apache Spark](https://aws-oss.beachgeek.co.uk/1z5), Jamal Arif shares four design patterns to manage EMR on EKS workloads for Apache Spark. Manage Spark jobs by pod template, Turn on Dynamic Resource Allocation (DRA) in Spark, Fully control cluster autoscaling by Cluster Autoscaler, and Group-less autoscaling with Karpenter. Check out the post for more details of each. Nice post. [hands on]

![architecture of solution for Apache Spark on EKS](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2022/07/25/BDB-1890-Walkthrough-1.png)

**Kubernetes**

A couple of posts this week. First up we have, [Blue/Green deployments for SAP Commerce applications on Amazon EKS](https://aws-oss.beachgeek.co.uk/1z6) from Francesco Bersani that covers common issues that customers are experiencing in on-premises SAP Commerce deployments. It gives a concrete way to achieve blue/green deployments on Amazon Elastic Kubernetes Service to have faster and more secure implementations of SAP Commerce applications.

![architecture of blue/green deployment](https://d2908q01vomqb2.cloudfront.net/17ba0791499db908433b80f37c5fbc89b870084b/2022/07/08/Screenshot-2022-01-12-at-23.09.40-2.png)

I have been exploring Kubernetes for some upcoming new talks and demos, and as part of that process (I am completely new to Kubernetes, but not new to containers) one of the things I had to try and figure out was the various different IAM roles, permissions, policies that I needed to ensure that I try and follow good practices on least privilege. So it was great to read this post from Waleed [Amazon EKS IAM roles and policies with Terraform](https://aws-oss.beachgeek.co.uk/1z0), who has put together a checklist of things you should look out for.

![eks cluster authentication diagram ](https://i0.wp.com/cloudly.engineer/wp-content/uploads/2022/05/eks-cluster-auth.drawio.png?w=860&ssl=1)

**AWS Amplify**

If you are looking to automate your AWS Amplify projects, and you are using GitLab then you are going to want to check out this post from Lee Tickett.  In [Deploy to AWS Amplify from GitLab CI/CD Self Managed](https://aws-oss.beachgeek.co.uk/1yz) he shares how was able to workaround a current limitation of GitLab SaaS not being supported, and get it to work. Nice!

![screenshot of successful deployment](https://tickett.files.wordpress.com/2022/08/image.png)

**AWS CDK**

AWS Container Hero Philipp Garbe has written this post, [Hey CDK, how do cross-account deployments work?](https://aws-oss.beachgeek.co.uk/1yy) that dives deep and breaks down how AWS CDK works from a permissions perspective, what you need to think about to ensure you minimise the permissions you grant, and then provides you with some options to suit different scenarios. Well worth reading.

![how aws cdk cross accounts illustration](https://garbe.io/assets/cdk-multi-account-options.png)

**Cello & AWS CDK**

Brett Weaver and Jerome Kuptz from at Intuit have put together this post, [Running Enterprise Workloads at Scale with a Next-Gen Infrastructure-as-Code Platform](https://aws-oss.beachgeek.co.uk/1ym) that shows how they use AWS CDK together with an open source tool they created called Cello, that helps them orchestrate infrastructure as code (IaC) at scale following GitOps principals. 

**Other posts you might like from the past week**

* [Announcing CDK for Terraform on AWS](https://aws-oss.beachgeek.co.uk/1z1) covers the CDK for Terraform (CDKTF) news that it is now generally available (GA)
* [Fine-grained access control in Amazon Managed Grafana using Grafana Teams](https://aws-oss.beachgeek.co.uk/1z2) demonstrates how Amazon Managed Grafana enables you to organise users, resources, and permissions

![grafana user management architecture](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2022/08/05/Picture1-2-1024x502.png)

* [Reduce security risks from IaC drift in multi-Region AWS deployments with Terraform](https://aws-oss.beachgeek.co.uk/1z4) provides a [hands on] guide that shows how to reduce security risks from IaC drift using the open source tool, Driftctl
* [Build a GNN-based real-time fraud detection solution using Amazon SageMaker, Amazon Neptune, and the Deep Graph Library](https://aws-oss.beachgeek.co.uk/1za) shows how to use the Deep Graph Library (DGL), among other AWS services, to construct an end-to-end solution for real-time fraud detection using GNN models [hands on]

![architecture for DGL solution](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2022/08/02/image003.jpg)

### Quick updates

**Kubernetes**

The Amazon Elastic Kubernetes Service (Amazon EKS) announced support for Kubernetes 1.23. Amazon EKS and Amazon EKS Distro can now run Kubernetes version 1.23, with support in Amazon EKS Anywhere launching soon after. To find out more about this update, and learn about some important changes, check out the post, [Amazon EKS now supports Kubernetes 1.23](https://aws-oss.beachgeek.co.uk/1z9)

**OpenSearch**

Check out v1.0.0 of the OpenSearch clients for .NET available on nuget. Find them on the [opensearch](https://aws-oss.beachgeek.co.uk/1zc) page

**AWS IoT Greengrass v2**

AWS IoT Greengrass is an Internet of Things (IoT) edge runtime and cloud service that helps customers build, deploy, and manage device software. Version 2.7 released last week with the following features: System Telemetry Enhancements, local Deployment Improvements, and additional Support for Client Certificates. Read more about these new features in the announcement, [AWS IoT Greengrass v2 updates Stream Manager to report new telemetry metrics and more](https://aws-oss.beachgeek.co.uk/1yi)

**PostgreSQL**

Amazon Aurora Serverless v1 now supports PostgreSQL major version 11. PostgreSQL 11 includes improvements to partitioning, parallelism, and performance enhancements such as faster column additions with a non-null default.

Aurora Serverless v1 also supports in-place upgrade from PostgreSQL 10 to 11. Instead of backing up and restoring the database to the new version, you can upgrade with just a few clicks in the AWS Management Console or using the latest AWS SDK or CLI. No new cluster is created in the process which means you keep the same endpoints and other characteristics of the cluster. The upgrade completes in minutes and can be applied immediately or during the maintenance window. Your database cluster will be unavailable during the upgrade. 

### Videos of the week

**EKS Anywhere**

Sai Vennam invites his brother Ram Vennam (solo.io) to talk multi-cluster Kubernetes with Istio. In this video you will learn the basics of running Kubernetes across on-premises, edge and public cloud infrastructure with EKS Anywhere. Together with Istio, we open up a number of cloud use-cases such as app modernisation, cloud bursting, data sovereignty and more.

{{< youtube -HyQByKUJsg >}}


**cdk8s**

From the AWS Container Days at Kubecon EU 2022, join the Containers from the Couch crew as they show you how you can manage your Kubernetes manifests without YAML with cdk8s, using general purpose languages to create and manage Kubernetes resources. Check the project out at [https://cdk8s.io](https://aws-oss.beachgeek.co.uk/1yh)

{{< youtube gGT7cPe2JvE >}}


**Karpenter**

Another session from AWS Container Days at Kubecon EU 2022, this time they take a look at what is new with Karpenter, an open source node autoscaler for Kubernetes that helps you scale your clusters faster with workload native node provisioning.

{{< youtube qawuLEMyeEw >}}



### Events for your diary

**OpenSearch**
**Every other Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting](https://aws-oss.beachgeek.co.uk/1az)

**Data Science on AWS**
**August 15th, 9am PST**

Join your hosts Antje and Chris for two talks. Talk #1: Ray Overview, Ray AI Runtime on AWS using Amazon SageMaker, EC2, EMR, EKS by Chris Fregly, Principal Specialist Solution Architect, AI and Machine Learning @ AWS. Talk #2: Deep-dive Blueprints for Amazon Elastic Kubernetes Service (EKS) including Ray and Spark by Apoorva Kulkarni, Sr. Specialist Solution Architect, Containers and Kubernetes @ AWS

Find out more and register via this meetup link, [Ray AI Runtime on AWS + Amazon EKS Blueprints for Ray, EMR, and Spark!](https://aws-oss.beachgeek.co.uk/1zd)


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

