---
title: 'AWS open source news and updates #10'
date: '2020-03-09'
tags : [ oss-newsletter ]
---
## March 9th - Instalment #10

Another bumper packed edition of everything new and interesting in the world where open source and AWS comingle. I have been asked a few times as to how do I choose the articles that go into these posts, so I thought I would very quickly share that; what does and does not go into these posts.

The idea of this series is to provide a curated list of open source projects that are either created by AWS, by the builders within AWS and open source projects that are created by customers and builders that either help other customers use AWS services and open source projects. The common thing across all these is that there will be source code and an open source license that you can get to. 

In addition to that, open source technologies that AWS make available through services such as the AWS Marketplace, I will also share as this is often a great way to get started with many open source applications.

Finally, I will share general open source articles and news that I think are useful and helpful in understanding how to maximise the impact of open source within business and society.

### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created.

So thank you Jimmy Dahlqvist, Andrew Goldis, Gabriel Kardonski, Luis Cañas-Díaz, Kapil Thangavelu, Yan Cui, Prasad Alle, Francisco Oliveir, Gyuho Lee, Rashmi Dwaraka, Michael Hausenblas, Lee Packham, Rachael Wang and Patrick Donnelly


### OSI elections - vote if you have not already

Just a reminder, OSI elections are currently running and if you are an OSI member and have not voted, you have until March 13th to do so. Watch out of the email that provides you with your voting credentials.


### Latest from open source projects

**Linux**

This week [Debian 10 'Buster'](https://9to5linux.com/debian-gnu-linux-10-buster-now-officially-available-in-the-aws-marketplace) available now via marketplace.


**Running Cypress dashboards on AWS**

Are you running [Cypress](https://www.cypress.io) within your CI/CD for end to end testing? Andrew Goldis put together this project that allows you to quickly get [Cypress up and running within your AWS environment](https://github.com/agoldis/sorry-cypress/wiki/AWS-Tutorial). Follow [Andrew on dev.to](https://dev.to/agoldis).


**Ruby developers**

[Stelligent cfn_nag](https://github.com/stelligent/cfn_nag) is an open source command-line tool that performs static analysis of AWS CloudFormation templates. The tool runs as a part of your pre-flight checks in your automated delivery pipeline and can be used to prevent a CloudFormation update from occurring that would put you in a compromised state. [Read the blog to see how to get started](https://stelligent.com/2019/05/07/extending-cfn_nag-with-custom-rules/).

**AWS Easy Credentials**

Love projects that people create and then share, such as this one from Jimmy Dahlqvist. If you were looking for a way to help you manage all your AWS profiles while working with the CLI, why not check out this project and see if it helps. If you use it, be sure to let Jimmy know and thank him. Project can be found here - [https://github.com/JimmyDqv/easy-aws-credentials](https://github.com/JimmyDqv/easy-aws-credentials)

**Super Easy Froms**

If you love serverless web development, then you will love this post from [Gabriel Kardonski, Super Easy Forms introduction: The easiest way to create a serverless web form](https://hackernoon.com/super-easy-forms-introduction-the-easiest-way-to-create-a-serverless-contact-form-u25g3yzq). Super easy forms is an open source and easy to use solution that uses services from the AWS cloud to help you generate your own fully customizable server-less contact forms (front-end and back-end). Check out the github repo [here](https://github.com/gkpty/super-easy-forms). Thank you Gabriel

### Open Distro for Elasticsearch

Regular readers of this blog will know that I am a big fan of the Open Distro for Elasticsearch distribution, and love it when I find cool projects or posts that explore this open source project. This week, [Luis Cañas-Díaz shares why he thinks you should take a look at Open Distro for Elasticsearch](https://sanacl.wordpress.com/2020/03/05/why-you-should-have-a-look-at-open-distro-for-elasticsearch/).


### AWS Open Source projects

**AWS API changes**

How do you keep up with the changes to the AWS SDKs? Well, you may be aware that one of my colleagues put this together a while ago, [AWS API changes](https://awsapichanges.info), the place to go to keep an eye on all the latest changes to the APIs in the SDKs you love and use. Check out the [source code here](https://github.com/awslabs/aws-sdk-api-changes) if you want to host your own. Top work [Kapil](https://twitter.com/kapilvt), follow him on Twitter and check out his [github project repositories](https://github.com/kapilt) too.

**Smithy**

[Smithy](https://awslabs.github.io/smithy/index.html) is a protocol-agnostic interface definition language and set of tools for building clients, servers, and documentation for any programming language.

Smithy is based on an interface definition language that has been widely used within Amazon and AWS for over a decade. We decided to release Smithy publicly to let other developers use Smithy for their own services and benefit from our years of experience with building tens of thousands of services. By releasing the Smithy specification and tooling, we also hope to make it easier for developers to maintain open source AWS SDKs.

Check out the github project [here](https://github.com/awslabs/smithy).

**HPC**

AWS ParallelCluster is a fully supported and maintained open source cluster management tool that makes it easy for scientists, researchers, and IT administrators to deploy and manage High Performance Computing (HPC) clusters in the AWS cloud. HPC clusters are collections of tightly coupled compute, storage, and networking resources that enable customers to run large scale scientific and engineering workloads. 

[AWS ParallelCluster 2.6 was released last week](https://github.com/aws/aws-parallelcluster/releases), and among the features of this release are support for Amazon Linux 2, FSx Lustre support in Ubuntu 18.04 and 16.04, additional validators supported, new AWS CloudWatch logging capabilities and much much more. 

**Migrating workloads using open source**

Open source is one of the ways many customers are migrating from legacy environments and proprietary technologies. In [this blog post](https://aws.amazon.com/blogs/publicsector/escape-unfriendly-licensing-practices-by-switching-enterprise-workloads-to-linux/), Rachael Wang and Patrick Donnelly share some practical steps on how to approach this. 

**Serverless Tools for developers**

Are you a Serverless developer? You need this then; Yan Cui walks us through the essential open source tools you need to develop serverless applications. So good, it comes in two parts: [Part One covers deployment frameworks, plugins for the serverless framework and CLI tools](https://aws.amazon.com/blogs/opensource/24-open-source-tools-for-the-serverless-developer-part-1), and in [Part Two will cover libraries and look at the Serverless Application Repository (SAR) ](https://aws.amazon.com/blogs/opensource/24-open-source-tools-for-the-serverless-developer-part-2). Make sure you follow [Yan](https://twitter.com/theburningmonk) via twitter.

**Amazon MSK**

In a new blog post, Prasad Alle and Francisco Oliveir show how you can use [Amazon Managed Streaming for Kafka (Amazon MSK) for ingesting IoT data using API gateway](https://aws.amazon.com/blogs/big-data/govern-how-your-clients-interact-with-apache-kafka-using-api-gateway/) to limit the need for the Kafka client libraries.

**AWS CodeCommit introduces open source remote helper**

AWS CodeCommit now supports an open-source remote helper for Git, git-remote-codecommit. This package extends Git and supports using authentication for CodeCommit repository access using profile information configured through the AWS CLI. This method supports both IAM users and access through assumed roles, identity providers, and federated access. The [AWS CodeCommit team have updated the documention](https://docs.aws.amazon.com/codecommit/latest/userguide/setting-up-git-remote-codecommit.html) to show you how to get started with this.

This is [open source and you can view and contribute to the project](https://github.com/aws/git-remote-codecommit).


**Using EKS encryption provider**

Gyuho Lee, Rashmi Dwaraka, and Michael Hausenblas walk us through an in depth post on "[Using EKS encryption provider support for defense-in-depth](https://aws.amazon.com/blogs/containers/using-eks-encryption-provider-support-for-defense-in-depth/)". EKS support for the encryption provider, is a vital defense-in-depth security feature. You can now use envelope encryption of Kubernetes secrets in EKS with your own master key. In this post we explain the background and walk you through how to get started. Read the blog post and then check out the [github repo here](https://github.com/kubernetes-sigs/aws-encryption-provider) too.

**AWS CDK and Kubernetes**

More container goodness, this time from [Lee Packham](https://twitter.com/Joolz). [cdk8s](https://github.com/awslabs/cdk8s) is a software development framework for defining Kubernetes applications and reusable abstractions using familiar programming languages and rich object-oriented APIs. [cdk8s](https://github.com/awslabs/cdk8s) generates pure Kubernetes YAML - you can use [cdk8s](https://github.com/awslabs/cdk8s) to define applications for any Kubernetes cluster running anywhere. This is an early-stage, experimental project so please jump in, try it out and provide feedback. Remember, AWS is powered by customer obsession.

**Amazon SageMaker**

When we launched AWS DeepRacer, we wanted to make it interesting and fun to learn reinforcement learning. One of my colleagues, [Xavier Raffin](https://twitter.com/xavierraffin) has taken this and created a fun project using Amazon SageMaker. This project shows how to build and deploy an [AI for the platform Battlesnake on AWS with Amazon Sagemaker](https://github.com/awslabs/sagemaker-battlesnake-ai). It is ready to deploy and contains learning materials for AI enthusiasts.

### Deep Dive of the week

**Firecracker**

Make sure you have a big mug of tea before reading this post (and follow the link to the paper) - a deep dive on Firecracker by Adrian Colyer. Really in depth article on everything you ever wanted to know (probably). https://blog.acolyer.org/2020/03/02/firecracker/


**What are your open source principals**

This week Uber shared their open source principles that help their internal communities understand how to think about open source. This is well worth sharing, so read about the principles here - [https://eng.uber.com/open-source-principles/](https://eng.uber.com/open-source-principles/)


### Tweets of the week

Quite a few tweets to get stuck into this week;

First up, this tweet thread that echoes some of the stuff in the Uber's open source principles - remember, freedom zero is the right to [choose whether to open source or not](https://twitter.com/_msw_/status/1234548576765636608?s=20).

Open source and cloud, how [cloud is enabling open source companies to thrive](https://twitter.com/mjasay/status/1234540927101755393) and Matt shares his thoughts in a [blog post on this topic](https://www.itworld.com/article/3530071/open-source-companies-are-thriving-in-the-cloud.html).

CNCF metrics on Kubernetes deployments are always interesting. In this tweet [Arun Gupta shares](https://twitter.com/arungupta/status/1235365557400002560?s=11) some stats: 84% are using containers in production, 78% use Kubernetes in production. Read through the report and find lots of really useful information about adoption of cloud native tools. 


---
### Do you use AWS and love open source? 

Do you have some content you want to share with a broader audience? We are always looking for guest content for the AWS Open blog. Please get in touch (via comments below) and I would love to speak with you about what you are doing in open source. We are always looking for interesting new content.

### We are hiring

We are hiring, so if you love open source, then why not check out the current openings. We would love to hear from you and if you want to chat and ask me anything, connect to me via LinkedIn or Twitter and always happy to talk.

[Open Source jobs at Amazon and AWS](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) - scroll to bottom, on left.

### Stay in touch with open source at AWS

I hope this summary has been useful. I have looked for all the session videos that have been uploaded to date, but if I have missed anything, please get in touch and I will update this summary. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on @AWSOpen.
