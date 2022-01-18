---
title: 'AWS open source news and updates #63'
date: '2021-04-12'
tags : [ oss-newsletter ]
---
## April, 12th, 2021 - Instalment #63

Newsletter #63. 

No newsletter last week due to the holidays, which means that this week we have a bumper edition. Check out the AWS CDK content this week, as there is both lots of it, but also all if it is great. We then have some great content if you are into containers, and the usual round up of other open source posts from AWS and the community covering topics such as Selenium, Apache Airflow, Apache Flink, GraphQL, Java and much more. On top of that we have some great new open source projects, including the latest from Amazon Research that provides tools to help data scientists fine tune language models.

Not signed up for the CDK Day yet? Don't worry, there is still time - head down to the Events section for links. Remember this is a free event, with a fantastic line up (schedule was published last week) and already has over 1000 folks signed up from across the world. This is one event you do not want to miss.

**Rust Foundation**

First up this week is news that Shane Miller is taking on the role of the Rust Foundation chair. Shane heads up the Rust platform team at AWS, and you can read more about this announcement in the post over at ZDNet, [AWS's Shane Miller to head the newly created Rust Foundation](https://aws-oss.beachgeek.co.uk/do). Congratulations Shane.

**Open Treatments**

Read about how open source is helping to give patients the tools and technology to build treatments in this post,
[Software engineer bets on technology to help speed rare disease treatments](https://aws-oss.beachgeek.co.uk/d1). The post talks about Open Treatments which is an open source platform, that is intended to accelerate collaboration and provide the tools needed to accelerate research and find new treatments. Inspiring stuff, and well worth 5 minutes of your time.

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Isabel Groves, Matt Hansen, Kyle Davis, Kyle Lee, Jonah Jones, Loris Degioanni, Christian Weber, Ishan Bhanuka, Eric Z. Beard, Rico Huijbers, Mitchell Valine, Nader Dabit, Mark Sailes, Re Alvarez-Parmar, Elamaran Shanmugam, Vivek Singh, Sagar Patel, Praveen Kumar, Anand Shah, Masudur Rahaman Sayem, Benjamin Gardiner, Olly Pomeroy, Massimo Re Ferre, Jeremy Cowan, Jimmy Ray, Yoni Leitersdorf, Manish Dhawaria, Hari Ohm Prasath, Jonah Jones, Prakash Palanisamy, Benjamin Meyer, Phillip Ninan, Rehan van der Merwe, Luc van Donkersgoed, Eric Meisel, Maria Sokolova, Masudur Rahaman Sayem, Karl Platz, Vadim Dabravolski and Paolo Irrera.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

**datatuner**

[datatuner](https://aws-oss.beachgeek.co.uk/ds) this new open source project was developed in the Alexa AI team, and is an end-to-end, data-to-text generation system called DataTuner, which can be used for a variety of data types and topics to generate fluent and accurate texts. You can read the published paper, [Automatically generating text from structured data](https://aws-oss.beachgeek.co.uk/dt) written by Isabel Groves that introduces the topic and covers the techniques used to improve natural language understanding.

![arch](https://assets.amazon.science/dims4/default/c5d113e/2147483647/strip/true/crop/1377x773+0+0/resize/1200x674!/quality/90/?url=http%3A%2F%2Famazon-topics-brightspot.s3.amazonaws.com%2Fscience%2Ff8%2Fbb%2Fbd2103fc48e98225e578e021aa73%2Fdatatuner.png)

**aws-tmux**

[aws-tmux](https://aws-oss.beachgeek.co.uk/dh) my colleague Darko has been sharing his love of his favourite tools, and one of them tmux, he has added some nice new *beta* features, allowing you to have easy access to useful information such as the AWS region you are in, the status of any Cloudformation stacks that are in the process of deploying and the version of the AWS cli you are using.

![screenshot](https://raw.githubusercontent.com/darko-mesaros/aws-tmux/main/img/header.png)

**sns-sqs-big-payload**

[sns-sqs-big-payload](https://aws-oss.beachgeek.co.uk/di) this open source library from aspecto-io that provides you with an Amazon SNS/SQS client library that enables sending and receiving messages with payload larger than 256KiB via Amazon S3. The project has detailed examples of how you can use this, so if you are looking to use SNS/SQS with larger payloads, this is just what you need.

**sam-patterns-cli**

[sam-patterns-cli](https://aws-oss.beachgeek.co.uk/dj) from the lovely people at mhlabs, we have another open source tool, this time a command line tool for importing patterns from https://serverlessland.com/patterns into your SAM template. It is an early version, so if you try it out make sure to provide feedback to the project.

![demo](https://raw.githubusercontent.com/mhlabs/sam-patterns-cli/main/images/demo.gif)

**kinesis-mock**

[kinesis-mock](https://aws-oss.beachgeek.co.uk/dk) Eric Meisel has put together this nice little project that provides a mock for the Kinesis API, that you might use for local testing.

**steampipe-plugin-aws**

[steampipe-plugin-aws](https://aws-oss.beachgeek.co.uk/dl) if you are using steampipe, then this is a very nice open source plugin from Turbot that you can use to use SQL to query infrastructure including servers, networks, identity and more from AWS. Make sure you check out the documentation that provides everything you need to know including some examples.

**meta-aws**

[meta-aws](https://aws-oss.beachgeek.co.uk/dm) this project is the metadata layer for baking AWS device software to Embedded Linux distributions built by the Yocto Project build system.  It provides recipes for building in AWS edge software capabilities to Embedded Linux built with OpenEmbedded and Yocto Project build frameworks.

**amazon-ecs-bestpractices-guide**

[amazon-ecs-bestpractices-guide](https://aws-oss.beachgeek.co.uk/dp) published last week, this is the open source version of the Amazon ECS best practices guide. You can submit feedback & requests for changes by submitting issues in this repo or by making proposed changes & submitting a pull request.

###AWS CDK

With CDK Day approaching (check out the events section, and sign up if you have not already) it is not surprising we are seeing some great new content appear, both from AWS and the community so this week I thought I would round up the posts that I have been reading and think are worth sharing.

First up we have Phillip Ninan who writes not one but TWO posts, [A No-Nonsense Guide To AWS Cloud Development Kit (CDK)](https://aws-oss.beachgeek.co.uk/de) is a follow up to a previous post I shared in an earlier newsletter. This time he is back with a nice guide in how you can get started. So get your AWS and your Typescript skills to the ready. In [Insider Secrets Of AWS CDK - The Base Stack](https://aws-oss.beachgeek.co.uk/dq) he dives deep into the concept of the "base stack", one of the essential AWS CDK building blocks.

Next up we have Rehan van der Merwe with [CDK Shorts #1 – Consistent asset hashing](https://aws-oss.beachgeek.co.uk/df) something that I came across whilst reading an interesting discussion on Reddit/aws around how to minimise the amount of redeploys of asset resources when doing a CDK deploy. It is super interesting, and the post provides a workaround that works for Rehan, and might be a good fit for you if you have this concern.

The final community post this week is from a regularly featured writer, Luc van Donkersgoed, who writes [Why I love the CDK](https://aws-oss.beachgeek.co.uk/dg). Luc starts off this post "If the CDK was a band, I’d be a groupie. If it was a football team I’d buy a season pass. If the CDK was a movie star I’d wait in line for an autograph." and so how could you resist reading with a start like that? Find out more by reading the four reasons why Luc loves CDK and will almost certainly be attending CDK Day :-) 

We have some great AWS posts covering AWS CDK, so lets start off with Christian Weber with another [CDK Corner](https://aws-oss.beachgeek.co.uk/cu). In this March edition, he covers some of the community updates, CDK updates you need to know about and some videos for those that prefer to consume content that way.

Following that we have the post [Using strong typing practices to declare a large number of resources with AWS CDK](https://aws-oss.beachgeek.co.uk/ct) from Ishan Bhanuka, where he shares lessons learned from using AWS CDK to manage the complexity when declaring large numbers of resources. Ishan covers how you can dynamically declare those resources at scale whilst still getting compile time checks and auto-completion in the IDE, reducing errors and improving your development experience.

Next we have Eric Z. Beard and Rico Huijbers collaborating on [Best practices for developing cloud applications with AWS CDK](https://aws-oss.beachgeek.co.uk/cv) discussing strategies for organising the development of complex cloud applications with large teams when using AWS CDK. This is a deep dive post, going beyond simple tutorials on basic AWS CDK concepts. This post covers how developers write and test code locally, how it gets deployed to production and various staging accounts, and how to organise a team’s apps to fit into a larger company-wide structure. Essential reading.

Finally, we have the eagerly anticipated (if social media is anything to go about) launch of being able to use Go with AWS CDK. In the post, [Getting started with the AWS Cloud Development Kit and Go](https://aws-oss.beachgeek.co.uk/cw), Mitchell Valine writes about the developer preview of Go support for AWS CDK. The post will walk you through creating your first CDK applications using Go. If you are a Gopher, give it a try and be sure to feedback via the various channels mentioned in the post.

### Community open source posts

**GraphQL on a Graph database**

[Building a GraphQL API on AWS with Amazon Neptune Graph Database and CDK](https://aws-oss.beachgeek.co.uk/cy) Nader Dabit with another great combo post/video (link to the video in the post) where he shows you very quickly how to build a simple application that combines a Graph database (in this instance, using Amazon Neptune) with GraphQL. Nader provides full source code and you can follow along in the video.

**DevSecOps**

[Catching Privilege Escalation in CI](https://aws-oss.beachgeek.co.uk/d8) Yoni Leitersdorf takes a look at how you can use a number of open source tools such as Cloudsplaining, checkov, Parliment and more to help you build better IAM policies for your applications, by using those tools to review your policies as they pass through your development pipelines. 

**Open Distro for Elasticsearch**

[Open Distro for Elasticsearch 1.13.2 is now available](https://aws-oss.beachgeek.co.uk/dr) Kyle Davis with a post announcing the launch of Open Distro for Elasticsearch 1.13.2 covering the key things you need to know around the general availability of Trace Analytics, as well as other pieces of this release including bug fixes.

![trace](https://opendistro.github.io/for-elasticsearch/assets/media/blog-images/2021-04-07-release-blog-1-13-2/trace-analytics-screenshot.png)

### AWS open source posts

**Detectron2**

[Object detection with Detectron2 on Amazon SageMaker](https://aws-oss.beachgeek.co.uk/dw) Vadim Dabravolski and Paolo Irrera discuss Detectron2, an object detection and segmentation framework released by Facebook AI Research (FAIR), and its implementation on Amazon SageMaker to solve a dense object detection task for retail. This post includes an associated sample notebook, available via the GitHub repo. 

**OpenTelemetry**

As more architectures become distributed, how you address operational challenges around how to application issues such as performance problems, having the visibility across that distributed architecture as well as being able to understand the health of the components is where the use of observability data can help. In this post, [Tracing AWS Lambda functions in AWS X-Ray with OpenTelemetry](https://aws-oss.beachgeek.co.uk/d9) Manish Dhawaria shows you how you can take your existing code, in this instance using code in an AWS Lambda function, and setup AWS Distro for OpenTelemtry to collect and send trace data to AWS X-Ray.

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/03/26/awsmani_XRay-Lambda-OpenTelemetry_f11.png)

**Selenium**

This week we have a couple of posts related to Selenium, the open source suite of automation testing tools based on the JavaScript framework.

First up we have Hari Ohm Prasath and Jonah Jones with [Run Selenium tests at scale using AWS Fargate](https://aws-oss.beachgeek.co.uk/da) which does as it says on the tin, and shows you a neat way of running Selenium tests at scale for low cost by utilising AWS Fargate Spot to run tests without having to manage and orchestrate their containers. They provide source code, and because it has been packaged up as an AWS CDK application, you should be able to get this up and running very quickly.

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/03/11/jonahjo_run-selenium_f1.png)

Following that we have Prakash Palanisamy with a post and detailed walkthrough on how to use AWS Developer Tools to build a continuous delivery pipeline that automatically deploys a test environment that runs a UI test. In, [Serverless UI testing using Selenium, AWS Lambda, AWS Fargate, and AWS Developer Tools](https://aws-oss.beachgeek.co.uk/db) Prakash shows how you can build a solution using a number of open source tools such as Chromium browser, Firefox browser, and Selenium. This is a great post, so make sure you check it out.

![arch](https://d2908q01vomqb2.cloudfront.net/7719a1c782a1ba91c031a682a0a2f8658209adbf/2021/03/20/SolutionDesign.jpg)

**Apache Airflow**

[Running Airflow Workflow Jobs on Amazon EKS with EC2 Spot Instances](https://aws-oss.beachgeek.co.uk/cz) Re Alvarez-Parmar and Elamaran Shanmugam with a great post that shows you how you can deploy and run your own, self managed Apache Airflow instance, taking advantage of Amazon EKS and EC2 Spot instances to help you optimise the costs of running your worker nodes. If you are running Apache Airflow this is a must read post.

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2021/04/06/image-2021-04-05T202759.145.png)

**Apache Flink**

A couple of Apache Flink posts this week, starting off with [Build a real-time streaming application using Apache Flink Python API with Amazon Kinesis Data Analytics](https://aws-oss.beachgeek.co.uk/d2) where Praveen Kumar, Anand Shah, and Masudur Rahaman Sayem walk you through how to build a stateful stream processing pipeline using the Apache Flink Python API on Kinesis Data Analytics. Apache Flink is a popular open-source framework and distributed processing engine for stateful computations. Customers using Kinesis Data Analytics for Apache Flink want to be able to write and run code against streaming sources to perform time series analytics, feed real-time dashboards, and create real-time metrics without managing the complex distributed Apache Flink environment. Whilst this has principally been done in Java, this new capability allows you to now use Python. If you want to know more about these concepts or about Apache Flink, this is a good post to read.

![arch](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2021/03/25/bdb1289-pyflink-kda-1-1.jpg)

Following that (and winner of this weeks longest blog post title) is [How Isentia improves customer experience by modernizing their real-time media monitoring and intelligence platform with Amazon Kinesis Data Analytics for Apache Flink](https://aws-oss.beachgeek.co.uk/du) co written by Maria Sokolova, and Masudur Rahaman Sayem from AWS and Karl Platz, Chief Architect at Isentia (a media monitoring, intelligence and insights solution provider in Asia Pacific) where they look at how Isentia updated their data processing pipeline with Amazon Kinesis Data Analytics for Apache Flink to replace the previous Apache Storm based pipeline.

![upgrade](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2021/04/06/isentia-flink-1-1.jpg)

**PostgreSQL**

With so many options for how you can deploy open source databases, especially popular and well loved ones such as PostgreSQL, wouldn't it be good to get some help in knowing what to think about as I explore the options. In this post, [Is Amazon RDS for PostgreSQL or Amazon Aurora PostgreSQL a better choice for me?](https://aws-oss.beachgeek.co.uk/d0) Vivek Singh and Sagar Patel provide some great information on that should help you to determine the best option between Amazon RDS for PostgreSQL and Aurora PostgreSQL for your workloads and business requirements. They take a look at the differences in performance, scalability, failover, storage, high availability, backup, and database versions.

![arch](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2021/04/07/Screen-Shot-2021-04-07-at-09.04.41.png)

**kaniko**

[Building container images on Amazon ECS on AWS Fargate](https://aws-oss.beachgeek.co.uk/d4) Re Alvarez-Parmar and Olly Pomeroy take a look at building container images that you can use on Amazon ECS on AWS Fargate, taking a look at how you can use the open source tool kaniko, that builds container images from a Dockerfile, much like the traditional Docker does, but unlike Docker, it doesn’t require root privileges. It executes each command within a Dockerfile entirely in userspace. If you build docker images, perhaps have automated pipelines that do this, and want to reduce the need to run privilege processes, take a look at this post.

![userspace](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2021/03/31/image-2021-03-31T175201.446.png)

**dex**

[dex](https://aws-oss.beachgeek.co.uk/d6) is a popular OpenID Connect (OIDC) provider that provides connectors for a variety of different OAuth providers. This lets dex defer authentication to LDAP servers, SAML providers, or established identity providers like GitHub, Google, and Active Directory (check out the project to see the current list) to obtain an identity. With that in mind, Jeremy Cowan and Jimmy Ray have put together this post, [Using Dex & dex-k8s-authenticator to authenticate to Amazon EKS](https://aws-oss.beachgeek.co.uk/d7) describing how to use dex with Amazon EKS, walking you through an example of using GitHub as your Identity Provider (IdP).

**Docker Compose**

Sticking with the building of containers, we have Olly Pomeroy and Massimo Re Ferre writing on this topic in, [Automated software delivery using Docker Compose and Amazon ECS](https://aws-oss.beachgeek.co.uk/d5). Using a nice simple application that changes from green to blue (or is it blue to green) find out how to build an automated deployment pipeline using Docker Compose. This is a really nice post, very well presented and explained and shows you how easy it can be to set up these automated software delivery processes.

![pipeline](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2021/04/06/image-2021-04-06T102401.314.png)

**Wordpress**

[Launching a WordPress Website using Amazon Lightsail Containers](https://aws-oss.beachgeek.co.uk/d3) Benjamin Gardiner writes and shows you how you can setup and run your own Wordpress installation using the recently launched Amazon Lightsail Containers service. Amazon Lightsail was a really great and easy way to quickly get started in the cloud, and you can do the same thing now with your container applications, providing a migration path to other AWS container services if you need to.

**AWS ParallelCluster**

I enjoyed this post from Benjamin Meyer, [Simplify HPC cluster usage with AWS Cloud9 and AWS ParallelCluster](https://aws-oss.beachgeek.co.uk/dc), where he shows you how easy it is to get started with HPC on AWS. In this post he shows you how to configure AWS ParallelCluster and explains how to set up an AWS Cloud9 IDE on the head node of the cluster. AWS Cloud9 automatically saves the state from the previous work done, which is super nice as this will help new users of AWS ParallelCluster’s environment get started quickly with the cluster and enable easy collaboration with their peers and colleagues.

![hpc on cloud9](https://d2908q01vomqb2.cloudfront.net/e6c3dd630428fd54834172b8fd2735fed9416da4/2021/03/30/Picture1-11.png)

**Robotics**

Two posts this week for those interested in this space. First up we have [Roomie uses AWS RoboMaker to scale custom robotics development](https://aws-oss.beachgeek.co.uk/dd) where Camilo Buscaron and Grace Reed from AWS and Alfredo Polito, Chief Technology Officer of Roomie collaborate on this post that shows how you can use AWS and open source tools to build and deploy a wide variety of custom robot solutions. In this post we look at Roomie, a fast-growing robotics startup based in Mexico City, who has taken on the challenge to build interactive utility robots.

![arch](https://d2908q01vomqb2.cloudfront.net/a9334987ece78b6fe8bf130ef00b74847c1d3da6/2021/04/01/roomie-architecture-3.png)

Next we have [Improving control of diagnostic tools in simulations with AWS RoboMaker tool configuration](https://aws-oss.beachgeek.co.uk/dv) from Matt Hansen, who takes a look at a tool configuration feature that allows customers to improve control of diagnostic tools with their simulations.

**Java**

[Open-sourcing the AWS Java Runtime Interface Client](https://aws-oss.beachgeek.co.uk/cx), in this post Mark Sailes takes a closer look at one of the announcements made at re:Invent around the new packaging format (container images) for AWS Lambda functions, exploring the AWS Lambda runtime API and what this means in the context of some of the things that were open sourced. Mark dives deeper into the Java runtime interface, aws-lambda-java-runtime-interface-client, and what this means to developers. This is an essential post for Java developers, and well worth 5 minutes of your time.

### Quick updates

**Apache Cassandra**

Amazon Keyspaces (for Apache Cassandra), a scalable, highly available, and fully managed Cassandra-compatible database service, now offers Federal Information Processing Standards (FIPS) 140-2 compliant endpoints to help you run highly regulated workloads more easily.

FIPS 140-2 is a US and Canadian government standard that specifies the security requirements for cryptographic modules that protect sensitive information. Now, you can run Cassandra workloads that require FIPS 140-2 compliance more easily by using a fully managed and serverless solution. You can configure applications to use a FIPS-compliant endpoint when connecting to Keyspaces by specifying it as the service endpoint in your client configuration. You can migrate existing workloads to Keyspaces that require FIPS compliance by using open-source tools such as cqlsh.

**RabbitMQ**

You can now launch RabbitMQ 3.8.11 brokers on Amazon MQ. This patch update to RabbitMQ contains several fixes and new features compared to the previously supported version, RabbitMQ 3.8.6.

**AWS Amplify**

AWS Amplify iOS can now be installed through the Swift Package Manager. iOS developers can interface with AWS services through Amplify iOS, which is a use case based client library. Developers have been importing Amplify iOS through dependency management tools like CocoaPods. With Swift 3.0, Apple introduced a native package management tool called Swift Package Manager that allows developers to manage these dependencies within their Swift project.

Swift Package Manager has been the preferred method for including third-party libraries in Swift projects, and support for Swift Package Manager has been a highly requested feature from the developer community for Amplify iOS. As of April 7th, 2021, developers can include Amplify iOS in their projects via Swift Package Manager. In cases where Amplify iOS does not address a use case entirely, developers can also directly include the low level AWS iOS SDKs via Swift Package Manager.

AWS Dev Advocate Kyle Lee put together a blog post so you can find out more on how to get started, so make sure you check out [Swift Package Manager Support for Amplify](https://aws-oss.beachgeek.co.uk/cs)

**Kubernetes**

Amazon Elastic Kubernetes Service (EKS) clusters running in the AWS GovCloud (US) Regions are now compliant with the Federal Risk and Authorization Management Program (FedRAMP) High baseline. With FedRAMP-High compliance, customers that operate under FedRAMP guidelines can use Amazon EKS to run their Kubernetes clusters in both AWS GovCloud (US) regions using Amazon EC2 or Fargate compute types. The security and compliance of Amazon EKS is assessed as part of multiple AWS compliance programs. In addition to FedRAMP High and Moderate baselines, Amazon EKS is compliant with SOC, IRAP, K-ISMS, ENS High, OSPAR, HITRUST CSF, and is a HIPAA eligible service.

### Video of the week

This week we have another video from the Containers from the Couch crew, this time inviting Jonah Jones and Loris Degioanni from Sysdiag to talk about the role OSS will play in the future of security, and lateral movements from containers to cloud. Compelling stuff.

{% youtube 6z1Pz1vArCI %}

### Events for your diary

**CDK Day**
**April 30th**

Announced this week was the second [CDK Day](https://sessionize.com/cdkday/), which will be on April 30th. Check out [the web page](https://sessionize.com/cdkday/) to find out more about the first CDK Day, which was incredible. This second event promises to be even better. The CFP is open until the 19th of March. Check out this supporting blog post, [CDK Day CFP Is Open!!!!](https://aws-oss.beachgeek.co.uk/4v) from Matt as to what to expect and what they are looking for when it comes to sessions.

**Cloud Native Rust Day**
**May 3rd**

Rust is a language empowering everyone to build secure, reliable, and efficient software. Rust is becoming more widely used in cloud native, powering everything from lightning-fast service meshes and powerful developer tools to internet-scale distributed databases.

Come explore what makes Rust a fantastic choice for new cloud native development, and learn about how the community uses Rust today. 

**Container Day**
**May 4, 2021 | 10:00AM - 6:00PM CEST**

Container Day x KubeCon is a fully live, virtual day of sessions all about Amazon EKS and Kubernetes at AWS, hosted by Brent Langston and Adam Keller of Containers from the Couch. At this Day Zero KubeCon event, the AWS Kubernetes team will be revealing new launches, demoing products and features, covering best practices, and answering your questions live on Twitch! If you have a question before the event, you can email the team at awscontainerday@amazon.com and maybe get them answered.


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen).