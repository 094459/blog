---
title: 'AWS open source news and updates #60'
date: '2021-03-15'
tags : [ oss-newsletter ]
---
## March 15th, 2021 - Instalment #60

Newsletter #60. 

This week is packed with posts for data lovers, with posts covering Presto, Apache Airflow and Apache Hudi, we have some Java goodies in the form of a nice deep dive on Heapothesys and a couple of posts on Kotlin, a couple of great whitepapers - the first will help you move your workloads (and open source projects) to Arm based AWS Graviton instance types, and the other is an update to the Redis whitepaper, and the usual round up of community and AWS related posts. Make sure you check out this weeks Video from the DataEng Uncomplicated that will help you know your AWS Data Wrangler from your Amazon SageMaker Data Wrangler too! 

Finally, we have a few events happening this week including one later today, so make sure you check those out too. Before anything though, take a quick look at the cdk.dev news coming next...

### cdk.dev

This week news that the CDK Weekly newsletter was moving to [cdk.dev](https://aws-oss.beachgeek.co.uk/a2), a community driven project governed by the “Open Construct Foundation” (OCF). The OCF is a US based non-profit organisation managed by CDK community members, many of whom you will be familiar with from previous posts I have shared in this newsletter (Matthew Bonig, Matt Coulter, Thorsten Hoeger, Edwin Radtke & Sebastian Korfmann). The sole purpose of the OCF is to foster the ecosystem around the CDK, and so the newsletter moving to this makes sense.

A reminder too that with CDK Day coming soon, the CFP closes later this week - 19th - so hurry up, there is still time to submit your AWS CDK related talk. Find out more on the [CDK Day website](https://www.cdkday.com/).

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Julien Goux, Anshul Agarwal, Florian Valéry, Trevor Sullivan, Sigit Priyanggoro, Sudhi Kandi, Jameson Williams, Varun Jewalikar, Marcos Arranz, Udit Mehrotra, Richard Mei, Chauncy McCaughey, Jessie Metcalf, Kelvin Nilsen, Dzenan Softic, Tim Berger, David Greenshtein, Riccardo Bassetto, Ryan Peterson, Santiago Cardenas, Dmitry Gulin, Joy Wang, Ora Lassila, Stephen Mallette, Veliswa Boya, Curtis Castrapel, Patrick Sanders, Hee Won Kim, Jochem Lugtenburg and Karl Cardenas.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

**Open Source job of the week**

[Open Source Solutions Architect, Amplify Framework](https://aws-oss.beachgeek.co.uk/aa) If you are looking for a fresh challenge, are based in the Southern California region, then take a look at this great opportunity to join the AWS Amplify team to help support the open source Amplify Libraries. The open source Amplify Framework team is continuously innovating and expanding our mobile and web framework to enable developers to quickly build, deploy, and manage native, web, and hybrid apps. 

### Latest from open source projects

**go-lambda-cleanup**

[go-lambda-cleanup](https://aws-oss.beachgeek.co.uk/ao) this open source project from Karl Cardenas, is a handy tool for anyone working with AWS Lambda. It is a Golang based CLI for removing unused versions of AWS Lambdas. One binary, no additional dependencies required. Clear documentation with provided examples help make it easy to get started with this project.

![demo](https://raw.githubusercontent.com/karl-cardenas-coding/go-lambda-cleanup/main/static/demo.gif)

Remember, it is good security hygiene to not have old versions of unused functions lying around, so this tool may help you with that process. The tools is configurable, so whether it is the default number of versions to keep or some other number you prefer, this tool could come in very handy.

**elgato-streamdeck-awscosts**

[elgato-streamdeck-awscosts](https://aws-oss.beachgeek.co.uk/aq) interesting open source project from Trevor Sullivan for anyone running Windows and using the elgato Stream Deck. This project creates a custom icon that displays your AWS bill. Trevor has written a supporting blog post, [Monitor Monthly AWS Spend on Elgato Stream Deck](https://aws-oss.beachgeek.co.uk/ar) and I really wanted to run this but sadly am using a Mac. 

### Community open source posts

**Open Telemetry**

[OpenTelemetry Observes International Women’s Day 2021](https://aws-oss.beachgeek.co.uk/aj) last week we had a celebration of International Women's Day from the OpenTelemetry project. OpenTelemetry shared how they were proud to support the goals and activities of IWD, giving the opportunity to help women learn and grow technically and professionally.

![iwd](https://miro.medium.com/max/1400/1*VBHZxCac2OD4NwiE41kw0A.jpeg)

**ConsoleMe**

[ConsoleMe: A Central Control Plane for AWS Permissions and Access](https://aws-oss.beachgeek.co.uk/ak) Curtis Castrapel, Patrick Sanders, and Hee Won Kim from Netflix provided a great detailed post on a project they open sourced towards the end of last year. This post talks about the motivation for creating and then open sourcing ConsoleMe, as well as showing you how to get started, some of the problems it can help you with and wraps up with how to get involved. ConsoleMe is a self-service tool for AWS that provides an easier way of managing permissions and access across multiple accounts, while encouraging least-privilege permissions. Security is job zero, so make sure you put this on your reading pile.

**AWS DeepRacer**

[Announcing: the AWS DeepRacer Community race data repository](https://aws-oss.beachgeek.co.uk/al) it has been a while since I have posted anything about the amazing DeepRacer community, so I was very happy when I saw this post from Jochem Lugtenburg announcing the release of the AWS DeepRacer Community race data repository. What is it? The community has produced a vast amount of data over the year that have helped folk accelerate their knowledge of the underlying technologies that power AWS DeepRacer, such as Reinforcement Learning. This [archived data](https://aws-oss.beachgeek.co.uk/am) can be found on [Github](https://aws-oss.beachgeek.co.uk/am) and is updated every hour. The post provides more details on what data is available and how you might use it. This is going to be very handy with all the other open source projects and tools the community has released. Whilst I was browsing, I had also totally missed this project, [deepracer-for-cloud](https://aws-oss.beachgeek.co.uk/an) that enables you to take the DeepRacer and run it anywhere you want - your local setup, AWS or somewhere else.

**openVPN**

[Connecting your Homelab to a VPC using OpenVPN](https://aws-oss.beachgeek.co.uk/as) a nice post from Florian Valéry that uses the openVPN project to connect directly with your AWS VPC networks from your home network. I actually started to have a look at this a few weeks ago as part of some work to connect my home router (an ASUS which comes with openVPN built in) to a private subnet in a VPC, so I am going to come back to this post in the near future as it looks like it has everything you need to get this up and running.

![arch](https://documents.lucid.app/documents/565937be-aca5-4ec8-a4a6-7372967eebed/pages/0_0?a=485&x=-1384&y=158&w=1408&h=484&store=1&accept=image%2F*&auth=LCA%201fcf81c7f94e2430c4f2cf777c2ce119700af240-ts%3D1615564448)

**AWS CDK**

[Preview environments per Pull Request using AWS CDK and Github Actions](https://aws-oss.beachgeek.co.uk/ay) first up we have Julien Goux with a post on how to setup preview environments in your Pull Requests on Github, using AWS CDK and Github Actions. What is a preview environment? Preview environments can be used to share your work before it goes to production or to perhaps to run end-to-end tests to increase confidence in your deployment or perhaps to have a mirror of your production infrastructure to play with. Nice shout outs at the end of the post too, great stuff Julien.


[Deploy your first app on AWS with AWS CDK - Part 1](https://aws-oss.beachgeek.co.uk/ai) AWS CDK features heavily in these weekly updates, but if you wanted to know how to get started, then my colleague Veliswa Boya 🇿🇦 has written up this post just for you. Part one, so keep an eye out for future instalments.

### Open Distro for Elasticsearch updates

First up we have a new blog post from Anshul Agarwal, [Introducing Asynchronous Search in Open Distro for Elasticsearch](https://aws-oss.beachgeek.co.uk/at) announcing the release of Asynchronous Search APIs in Open Distro for Elasticsearch. This feature is really great if you are running large searches that would otherwise take a long time to run synchronously, and can start using results as they become available and monitor the progress of the request as it continues to run in background. The results from the query can also be stored in an index for retrieval at a later time. The post shows you how you can get started with this new feature.

A few updates this week on the Elasticsearch fork that are worth sharing. First up we have Kyle Davis with a thread on the [Guiding principles for the forks of Elasticsearch and Kibana](https://aws-oss.beachgeek.co.uk/au) which as Kyles notes in the post, as the project prepares to make the repos for the new forks of Elasticsearch and Kibana available, they are seeking feedback on the initial principles of the project. So take a look and feel free to comment/feedback your thoughts. There are already some good suggestions and comments, so make sure to go through those. Related to that is a separate thread kicked off by Dawn Foster on [Governance for the Forks](https://aws-oss.beachgeek.co.uk/av), which takes a look at the really important business of the governance of the project. Some good suggestions put forward, so take a look - it is a quick read that I would hate to spoil.  

### AWS open source posts

**Heapothesys**

[Heapothesys benchmark suite adds end-to-end timeliness metrics](https://aws-oss.beachgeek.co.uk/ac) Kelvin Nilsen dives deep into Heapothesys, an open source tool developed by Amazon’s JDK team for the purpose of identifying existing JVM weaknesses and performance bottlenecks. The tool also can quantify the degree to which proposed changes to the JVM may improve upon the existing implementation. Using the metrics produced by the tool, operations teams can more reliably predict the CPU and memory requirements for new JVM versions and different GC configurations, resulting in more consistent, reliable, and efficient services. The post walks you through the project and provides some example workloads you can use for testing, as well as providing source via the linked GitHub repo. If you run Java workloads with an OpenJDK JVM, then you need to check this post out. This is my post of the week for sure!

![graph](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/03/01/kdnilsen_Heapothesys_f1.jpg)

**.NET Core**

[Building single binary file extensions for AWS Lambda with .NET](https://aws-oss.beachgeek.co.uk/af) nice post from Santiago Cardenas and Dmitry Gulin that will be of interest to anyone who is on an application modernisation journey with .NET code. Santiago and Dmitry show how you can create an AWS Lambda extension using C#, packaged as a self-contained binary file with no external dependency on the .NET runtime that you can then use as an extension for any Lambda runtime. All source code for this walkthrough is provided so you can try it out yourself before taking a look at how you might use this yourselves.

**graph-notebook**

[Getting started with open source graph notebook for graph visualization](https://aws-oss.beachgeek.co.uk/ag) Joy Wang, Ora Lassila, and Stephen Mallette show you how you can get started with an open source project that I shared towards the end of 20202, [graph-notebook #46](https://aws-oss.beachgeek.co.uk/ah). The graph notebook provides an easy way to interact with graph databases using Jupyter notebooks. Using this open-source Python package, you can connect to any graph database that supports the Apache TinkerPop or the RDF SPARQL graph model. These databases could be running locally on your desktop or in the cloud. Graph databases can be used to explore a variety of use cases including knowledge graphs and identity graphs. In this post, they share how to get started with graph notebook. Graph notebook connects to any database that supports either the RDF open standard or the open source Apache TinkerPop framework. This makes graph notebook accessible to open sourced graph databases that provide a SPARQL 1.1 endpoint or a TinkerPop-enabled graph hosted inside Gremlin Server.

![demo](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2021/03/04/jueamzn_graph-visualization_f2.png)

**Kotlin**

We have a number of posts if you are interested in [Kotlin](https://aws-oss.beachgeek.co.uk/a6). If you have heard the name, but are not sure what Kotlin is, it is a cross-platform, statically typed, general-purpose programming language developed by JetBrains and the open source community. It is open sourced under the Apache-2.0 license, and over the past few years Kotlin programming language has become the preferred language for Android app developers - more of that in a moment.

First up, we have [Adopting Kotlin at Prime Video for higher developer satisfaction and less code](https://aws-oss.beachgeek.co.uk/a5) from Varun Jewalikar and Marcos Arranz who take a look at Amazon Prime Video’s software development culture, followed by a deep dive into the team’s adoption of Kotlin. The posts shares examples of Kotlin language features, such as coroutines and data classes, are also detailed and also, as a goodie, shares how adopting Kotlin has helped make happier developers. Happier developers are more productive developers. No spoilers, check the post to find out more.

Following that we have news from last week where we announced first-class support for Kotlin in Amplify Android. Amplify Android is part of AWS Amplify, a set of libraries, tools, and services that help frontend web and mobile developers build secure, scalable, full-stack applications. Kotlin is a popular programming language commonly used by Android developers, among others. This release brings together Amplify Android and Kotlin by providing a “façade” module that Kotlin developers can include in their apps. The façade simplifies asynchronous programming, improves API ergonomics, yields better hints in Android Studio, and integrates with Android architecture components. The new module supports all the feature categories in Amplify Android, including Authentication, DataStore, and Storage. Developers can use Amplify Android with Amplify-created backends, as well as existing AWS backends. Find out more in the [GitHub repository](https://github.com/aws-amplify/amplify-android).

In the blog post, [Focusing on Amplify’s Kotlin Experience](https://aws-oss.beachgeek.co.uk/a4), Jameson Williams dives deep into this announcement, exploring the “façade” architecture, with some sample code and a walk through.

![arch](https://d2908q01vomqb2.cloudfront.net/0a57cb53ba59c46fc4b692527a38a87c78d84028/2021/03/08/amplify-facade-architecture.png)

**Presto**

[Top 9 performance tuning tips for PrestoDB on Amazon EMR](https://aws-oss.beachgeek.co.uk/a8) Richard Mei and Chauncy McCaughey share their thoughts on common architecture patterns when using Presto on an Amazon EMR cluster as a big data query engine and goes on to provide practical performance tuning tips for common performance challenges faced by large enterprise customers. Presto is an open source (Apache 2.0 license) distributed SQL query engine for interactive data analytics, and has become popular SQL query engine for big data analytics.

![presto](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2021/03/09/bdb492-prestodb-emr-1.jpg)

**Apache Hudi**

[New features from Apache Hudi available in Amazon EMR](https://aws-oss.beachgeek.co.uk/a7) Udit Mehrotra takes a look at some of the new features from Apache Hudi that you can now use in Amazon Elastic Map Reduce. Apache Hudi is an open-source data management framework used to simplify incremental data processing and data pipeline development by providing record-level insert, update and delete capabilities. Some of the new capabilities that you can now leverage your existing Parquet datasets within Apache Hudi (something we worked with the Apache Hudi to contribute that change), general performance updates as well as a number of other optimisations. If you work with Apache Hudi or data in general, this post is for you.

![arch](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2021/03/09/hudi-emr-5.jpg)

**Apache Airflow**

[Build a DataOps platform to break silos between engineers and analysts](https://aws-oss.beachgeek.co.uk/ad) Dzenan Softic, Tim Berger, David Greenshtein, and Riccardo Bassetto have collaborated on this post, where they take a look at how to build a data platform that fosters effective collaboration between engineers and analysts. The post explores how data analysts can transform data via software engineering practices such as DataOps, and how you can apply CI/CD practices within your data analytics transformation workflows, using tools like Apache Airflow as orchestrators and schedulers. Another great post if working with data is what you do.

![arch](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2021/03/03/bdb870-build-dataops-platform-4.jpg)

**Kibana**

[Export and import Kibana dashboards with Amazon ES](https://aws-oss.beachgeek.co.uk/ae) Ryan Peterson with a nice quick post around how you can use of the features of Kibana, Dashboards - a collection of visualisations from the underlying data with Elasticsearch, and export to re-use or share those dashboards. This might be handy if you have lots of different Elasticsearch environments with similar data and you want to have a common dashboard to visualise that data across all those instances. 

### Quick updates

**PostgreSQL**

Customers can now enable multiple authentications protocols at the same time for an Amazon Aurora PostgreSQL-Compatible Edition cluster. Amazon Aurora with PostgreSQL compatibility supports both Kerberos authentication with Microsoft Active Directory (AD) and IAM database authentication, but in the past you could choose only one for a given cluster. Now, Amazon Aurora with PostgreSQL compatibility supports enabling Kerberos and IAM authentication for a cluster simultaneously. For example, customers can enable IAM for authenticating AWS Lambda and enable Kerberos for other authentication situations.

**Elasticsearch**

Amazon Elasticsearch Service now publishes events to Amazon CloudWatch and Amazon EventBridge to provide better visibility into the service. Events to indicate the availability of a service software update for a domain, the start of an update, and the completion of an update will be included in the initial release. You will also be able to view these events under the new ‘Notifications’ view in the Amazon Elasticsearch Service console. Previously, you could see the availability of a service software update in the domain overview page of the Amazon Elasticsearch Service console. With this release, you can monitor the availability, start, and completion of an update with ease through CloudWatch or EventBridge events. You can also acknowledge these notifications on the Amazon Elasticsearch Service console for tracking.

### Case Studies

[Addressing housing barriers with the cloud: Baltimore launches My Digital Data Locker](https://aws-oss.beachgeek.co.uk/a9) Jessie Metcalf takes a look at how Balitmore is addressing some important social challenges using open source and AWS. [My Digital Data Locker](https://aws-oss.beachgeek.co.uk/ab), an innovative cloud-based platform that gives people who are experiencing homelessness a secure place to manage digital copies of vital documents. Learn more about the mission as well as links to the GitHub repository and the code by reading this post.

### WhitePapers

**Redis**

[Database Caching Strategies Using Redis](https://aws-oss.beachgeek.co.uk/ax) this is a freshly updated Whitepaper that describes some of the caching strategies and implementation approaches that address the limitations and challenges associated with disk-based databases, and how the use of in-memory data caching technologies can be one of the most effective strategies for improving your overall application performance and reducing your database costs.

**Arm**

[How AWS Graviton helps Independent Software Vendors accelerate growth and improve their margins on AWS](https://aws-oss.beachgeek.co.uk/a3) is a new WhitePaper covering the topic of how you can move your codebase to Arm, and optimise them for the AWS Graviton2 instance types. The WhitePaper provides a very handy checklist for software architects and developers, and whilst it is focused on the ISV (Independent Software Vendor) space, it will prove useful for anyone looking to see how they can leverage these instance types to optimise their software.

![overview](https://docs.aws.amazon.com/whitepapers/latest/aws-graviton2-for-isv/images/image3.png)

### Videos of the week

**AWS Data Wrangler**

Want to know the difference between AWS Data Wrangler and Amazon SageMaker Data Wrangler? This great video from DataEng Uncomplicated talks about AWS Data Wrangler, an open-source python library that makes it easier to work with data from AWS services and a project I have featured over the past year. From how is this different to the Amazon SageMaker Data Wrangler project, what services you can use with this project and the typical use cases you might use it for. Great video, and on 8 minutes of your time.

{% youtube 5pVpFnvRDW4 %}

**Magma**

Magma is an open-source software platform that gives network operators an open, flexible and extendable mobile core network solution. Their mission is to connect the world to a faster network by enabling service providers to build cost-effective and extensible carrier-grade networks using open source software. This video on the Open Infrastructure Foundation You Tube channel from Sigit Priyanggoro and Sudhi Kandi at AWS, shows you how you can deploy and configure Magma on AWS.

{% youtube sWZoopmEJrM %}

### Events for your diary

We have a couple of these events happening later this week, so check it out and register before it is too late.

**AWS SaaS Boost: An Open-Source Tool for Accelerating SaaS Migration**
**March 15, 2021, 1:00 PM (PT) | 4:00 PM (ET)**

Moving solutions to a SaaS delivery can be daunting for some organisations. The complexity and overhead of refactoring your solution, automating tenant on boarding, introducing new operational tooling, and a host of other factors can make it challenging or impossible for organisations to move to SaaS. The investment and time is just too long. In this tech talk, we’ll dig into the details of AWS SaaS Boost, a new tool that streamlines your ability to move a monolith into a SaaS delivery model. The goal of AWS SaaS Boost is to provide a pre-built SaaS environment that enables organisations to begin to operate as a SaaS business without absorbing all the complexity that comes with building, operating, and managing a SaaS solutions. We’ll explore the fundamentals of this open source environment, describing both the experience and the underlying architecture.

[Sign up here](https://aws-oss.beachgeek.co.uk/aw), there is still time to catch this event later today.


**Embracing Observability in Distributed Systems**
**March 16th, 9:00am EST**

Michael Hausenblas is your speaker and he will look at the motivation for observability in distributed systems such as containerized microservices. We discuss good practices and current developments around CNCF open source projects and specifications including OpenTelemetry and FluentBit.

This is not a free event, but part of the InfoQ event. You can find out more details and register here](https://live.infoq.com/ve2021/presentation/observability).

**Bottlerocket: Community Meetup**
**March 18, 11:00am PST**

Have questions for the Bottlerocket team? Want to talk about a particular feature you'd like to see, or want more insight into how Bottlerocket works? Join the Bottlerocket community on Thursday, March 18th at 11am Pacific US time. If you have any particular topics you want to discuss, then feel free to add them to the discussion (see the link below)

Find out more [via this link](https://aws-oss.beachgeek.co.uk/ap), which includes how to add your discussion topics and how to attend.

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