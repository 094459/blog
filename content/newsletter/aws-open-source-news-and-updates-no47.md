---
title: 'AWS open source news and updates No.47'
date: '2020-12-07'
tags : [ oss-newsletter ]
---
## December 7th - Instalment #47

Week No.47 and with the first week of re:Invent over, it was good to see so many great open source related announcements. You can expected detailed coverage of those in this weeks roundup, including links to the various sessions and blog posts that have been published this week to support those announcements. If that was not enough, this week still has a great round up of other open source blog posts, some really interesting open source projects and of course, more posts from the community. You should also check out the new design for the [AWS open source webpage](https://aws.amazon.com/opensource/). Looking rather nice I think, and you can expect more improvements over the coming months.

So, let's crack on and start with what you can expect during week two of re:Invent.

**re:Invent 2020**

After a great opening week, we have even more great open source related sessions. I have listed these in chronological order and sessions are typically repeated three times to accommodate the different time zones you might be in. These are all in CET so remember to add or subtract time depending on where you are.

**DEC 8th**

* AIM402 Fast distributed training and near-linear scaling with PyTorch on AWS
* AIM405 Train large models with billions of parameters in TensorFlow 2.0
* CON207 Define AWS service resources with AWS Controllers for Kubernetes 
* FMW202 Empower front-end web and mobile app development with AWS Amplify

**DEC 9th**

* AIM402 Fast distributed training and near-linear scaling with PyTorch on AWS  (repeat)
* AIM405 Train large models with billions of parameters in TensorFlow 2.0 (repeat)
* CON202 AWS Copilot: Simplifying container development
* CON207 Define AWS service resources with AWS Controllers for Kubernetes  (repeat)
* DAT314 Running Apache Cassandra workloads with Amazon Keyspaces
* DOP202 AWS CDK: What’s new and what’s next
* FWM201 Power modern serverless applications with GraphQL and AWS AppSync*
* FMW202 Empower front-end web and mobile app development with AWS Amplify (repeat)
* FMW303 Build iOS & Android mobile apps in record time with Flutter and AWS Amplify

**DEC 10th**

* ADM301 Running ultra-high throughput ad tech workloads on Aerospike*
* CON201 Getting an insight into your Kubernetes applications
* CON202 AWS Copilot: Simplifying container development (repeat)
* DAT314 Running Apache Cassandra workloads with Amazon Keyspaces (repeat)
* FWM201 Power modern serverless applications with GraphQL and AWS AppSync (repeat)
* FMW303 Build iOS & Android mobile apps in record time with Flutter and AWS Amplify (repeat)
* NFX302 Simplifying delivery as code with Spinnaker and Kubernetes 

**DEC 11th**

* CON201 Getting an insight into your Kubernetes applications (repeat)
* NFX302 Simplifying delivery as code with Spinnaker and Kubernetes (repeat)

### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to Mohamed Radwan, Lee Packham, Ben Kehoe, Pahud Hsieh, Nader Dabit, Azfaar Qureshi, Shovnik Bhattacharya, Akshay Ram, Prithvi Ramesh, Michael Hausenblas, Mithun Mallick, Sam Dengler, Matt Asay, Kirk Davis, Peter Gvozdjak, Al MS, Chris Downing, Wilbert Guo, Claudio Acquaviva, Morgan Davies, Marcia Villalba, Celete Blackwell, Alex Casalboni, Martin Beeby, Allan Naim, Chandler Hoisington, Raja Jadeja, Micah Hausler, Norm Johanson, Matthieu Napoli, Abhishek Ray, Adam Ruka and David Blevins.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

**aws-lambda-runtime-interface-emulator**

[aws-lambda-runtime-interface-emulator](https://github.com/aws/aws-lambda-runtime-interface-emulator) this open source project is a proxy for Lambda’s Runtime and Extensions APIs, which allows customers to locally test their Lambda function packaged as a container image. It is a lightweight web-server that converts HTTP requests to JSON events and maintains functional parity with the Lambda Runtime API in the cloud. It allows you to locally test your functions using familiar tools such as cURL and the Docker CLI (when testing functions packaged as container images).

As a bonus, [check out this repo](https://github.com/kelseyhightower/lambda-on-cloud-run) from Kelsey Hightower where he has some fun with this project to do something interesting.

**sg-agent**

[sg-agent](https://github.com/maradwan/sg-agent) this open source utility from Mohamed Radwan that gets your public IP depending on a schedule (default 5 minutes) and updates all aws security groups rules and ports in different regions. The Agent checks the Security Groups and revokes all rules then adds the new public ip and ports, which you might find useful when using EC2, Redshift and RDS from Public ip that changes so often. 

**aws-sso-util**

[aws-sso-util](https://github.com/benkehoe/aws-sso-util) from AWS Community Hero Ben Kehoe, continuing on his mission to make AWS SSO a better place for everyone, with this open source project that contains utilities for the following: Configuring .aws/config, logging in/out, AWS SDK support, looking up identifiers and CloudFormation. Detailed info in the README.md, so check it out.

**ecr-public-action**

[ecr-public-action](https://github.com/pahud/ecr-public-action) is a Github Action from AWS developer advocate Pahud Hsieh that allows you to docker build, tag and publish to Amazon ECR Public in the Github Action workflow.  Documentation and samples provided, if you are looking to do this, make sure you check this out.

**homebrew-aws**

[homebrew-aws](https://github.com/aws/homebrew-aws) Homebrew is a package manager for macOS which provides easy installation and update management of additional software. This Tap (repository) contains the Formulae that are used in the macOS AMI that AWS offers. These EC2-optimized macOS AMIs are for developer use, and the Tap providies a simple way to get these tools and updates to them.

**next.js-amplify-datastore**

[next.js-amplify-datastore](https://github.com/dabit3/next.js-amplify-datastore) Nader Dabit shares another great project/walkthrough, this time providing an example app using Amplify DataStore with Next.js for static site generation, pre-rendering, and Server Side Rendering (SSR). The project is also integrated with the recently launched Admin UI component as well. A link to the video walkthrough completes this already awesome project.

**trollpurse-ops**

[trollpurse-ops](https://github.com/trollpursepublishing/trollpurse-ops) this project provides a low server management model (commonly known as "serverless") for managing Continuous Integration (CI) and Continuous Deployment (CD) for common source control management services, popular game engines, and well known storefronts for video games and game related products. This has been put together by the community behind https://trollpurse.com/

**red-detector**

[red-detector](https://github.com/lightspin-tech/red-detector) is an open source tool from [Lightspin](https://lightspin.io/) that lets you scan your EC2 instance to find its vulnerabilities using another open source tool called [Vuls](https://vuls.io/en/).

**serverless-express**

[serverless-express](https://github.com/vendia/serverless-express) this is not a new project but this has now moved to a new home. If you were using this project to build your serverless web applications or services, check out the new home. From the GitHub repo:

>Brett, the original creator of the Serverless Express library, will continue maintaining the repository and give it the attention and care it deserves. At the same time, we will be looking for additional contributors to participate in the development and stewardship of the Serverless Express library. AWS and the SAM team will remain involved in an administrative role alongside Vendia, Brett, and the new maintainers that will join the project.
>
>We believe this is the best course of action to ensure that customers using this library get the best possible support in the future. To learn more about this move or become a maintainer of the new Serverless Express library, reach out to us through a GitHub issue on this repository.
>

**buildx**

If you are looking to do cross architecture builds using AWS CodeBuild, then this [handy Gist](https://gist.github.com/leepa/260a7f8765a48db094f5cbf2fb45ea48) from Lee Packham might be useful. As he says in this [tweet](https://twitter.com/Joolz/status/1334535765120970757), "I could not find a previous example for doing amd64/arm64 builds with "buildx" rather than trying to manage multiple jobs."

### AWS open source posts

**Cortex**

[Migrating Cortex CI/CD workflows to GitHub Actions](https://aws.amazon.com/blogs/opensource/migrating-cortex-ci-cd-workflows-to-github-actions/) in this blog post, intern engineers Azfaar Qureshi and Shovnik Bhattacharya talk about their experience working with Cortex, a popular open source observability project that provides scalable, highly available, and multi-tenant storage of time-series metrics. They share the challenges they faced and how they applied lessons learned to improve the development experience for other contributors in the Cortex Project.

![comparison](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2020/11/25/alolitas_migrating-cortex_table1.png)

**Fluent Bit**

[Fluent Bit for Amazon EKS on AWS Fargate is here](https://aws.amazon.com/blogs/containers/fluent-bit-for-amazon-eks-on-aws-fargate-is-here/) Akshay Ram, Prithvi Ramesh and Michael Hausenblas share with you how it is now easier to get logs from your containers now that we support CNCF Fluent Bit-based log router. Where previously you had to run a sidecar to route container logs from Amazon EKS pods running on AWS Fargate, you can now use a built-in log router which means there are no sidecars to install or maintain. You simply select where you want to send your data and logs are routed to a destination of your choice, including the ability to ship logs directly to CloudWatch with a few configuration steps.

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2020/11/27/firelens-eks-fargate-overview-1024x534.png)

**Amazon S3 and S3A**

[Community collaboration: The S3A story](https://aws.amazon.com/blogs/opensource/community-collaboration-the-s3a-story/) Matt Asay talks about the collaboration to improve the [S3A adapter](https://archive.cloudera.com/cdh6/6.0.0/docs/hadoop-3.0.0-cdh6.0.0/hadoop-aws/tools/hadoop-aws/index.html#Introducing_the_Hadoop_S3A_client.) for Hadoop. The S3A adapter enable Apache Hadoop to directly read and write Amazon S3 objects. As some of you might have already heard/read, there were a number of enhancements announced last week during re:Invent, with one of the most anticipated being the introduction of strong consistency. In anticipation of this, a number of AWS engineers got involved with the S3A community and Matt describes some of the contributions that they made and how as a community effort, that collaboration has resulted in a great outcome for the project.

**RabbitMQ**

[Migrating message driven applications to Amazon MQ for RabbitMQ](https://aws.amazon.com/blogs/compute/migrating-message-driven-applications-to-amazon-mq-for-rabbitmq/) Mithun Mallick and Sam Dengler take a look at some of the common integration patterns using RabbitMQ, migrating from self-managed RabbitMQ to Amazon MQ, and using plugins like Federation to build hybrid architectures. The post also explores the architectural details of Amazon MQ for RabbitMQ for its different deployment models. See the re:Invent section below a link to Sam's session which I recommend you check out.

![arch](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2020/12/04/private-cluster.png)

**.NET Core**

[Powering .NET 5 with AWS Graviton2: Benchmarks](https://aws.amazon.com/blogs/compute/powering-net-5-with-aws-graviton2-benchmark-results/) following on from the last two weeks sharing AWS Graviton benchmarks running .NET Core workloads, we have Kirk Davis that writes about some benchmarks he ran to determine the impact of the recently announced .NET Core 5 running on AWS Graviton2 instances. As this is a benchmark post no spoilers, but you will be pleasantly surprised by the numbers. That should pique your interest, so read on...

**Amazon EMR**

[Amazon EMR now provides up to 30% lower cost and up to 15% improved performance for Spark workloads on Graviton2-based instances](https://aws.amazon.com/blogs/big-data/amazon-emr-now-provides-up-to-30-lower-cost-and-up-to-15-improved-performance-for-spark-workloads-on-graviton2-based-instances/) Peter Gvozdjak and Al MS bring you this weeks blog post with the longest title, but also another AWS Graviton2 benchmark, this time measuring the impact of running Apache Spark on these ARM based instance types. Again, no spoilers but a quick read so check it out.

**AWS ParallelCluster**

[Managing AWS ParallelCluster SSH users with AWS OpsWorks](https://aws.amazon.com/blogs/opensource/managing-aws-parallelcluster-ssh-users-with-aws-opsworks/) Chris Downing is back with another instalment of helping customers with managing their AWS ParallelCluster deployments. This time, he walks you through creating an OpsWorks Stack for the purposes of managing SSH user access to AWS ParallelCluster. AWS OpsWorks is primarily a configuration management service integrated with Chef and Puppet but for user management, Chris leverages an AWS OpsWorks Stacks capability that allows IAM users to be assigned SSH keys and provisioned as POSIX user accounts on a registered instance.

**AWS Distro for OpenTelemetry**

[Launching the AWS Distro for OpenTelemetry developer site with Gatsby and GraphQL](https://aws.amazon.com/blogs/opensource/launching-the-aws-distro-for-opentelemetry-developer-site-with-gatsby-and-graphql/) every open source project needs clear documentation and a well thought out web site is a really good way to encourage uptake of the project, drive community growth and more. So great to see this post from AWS intern Wilbert Guo as he shares his experience in building the AWS Distro for OpenTelemetry developer site using Gatsby and GraphQL. The developer site aims to provide a place where customers can find out more information about the project, as well as get involved and download the distribution.

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2020/11/19/alolitas_OpenTelemetry-Gatsby_f3.jpg)

**Kong**

[Running microservices in Amazon EKS with AWS App Mesh and Kong](https://aws.amazon.com/blogs/containers/running-microservices-in-amazon-eks-with-aws-app-mesh-and-kong/) this post from Claudio Acquaviva and Morgan Davies at Kong, share this solution on how to incorporate the [Kong for Kubernetes Ingress Controller](https://github.com/Kong/kubernetes-ingress-controller) a project to protect your service mesh running side by side with your application services, leveraging Kubernetes capabilities like HPA, self-healing, RBAC, and cert-manager, among others. The post will explore how to use Amazon EKS, AWS App Mesh, and Kong for Kubernetes to implement and protect your service mesh.

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2020/11/20/K4K8S-and-AWS-App-Mesh-blog3.png)

### re:Invent

**Announcements and Keynotes**

Whilst not exclusively open source, if you did miss the re:Invent keynote from Andy Jassy, then check out Jeff Barr's realtime blogging of the event, [re:Invent 2020 Liveblog](https://aws.amazon.com/blogs/aws/reinvent-2020-liveblog-andy-jassy-keynote/). He expertly captures everything you need to know, including the stuff I am going to talk about below.

There were a number of great announcements around enhancements to AWS Lambda, which quickly prompted updates to a couple of open source projects in this space. Alex Casalboni updated his [AWS Lambda Power Tuning tool](https://github.com/alexcasalboni/aws-lambda-power-tuning) to incorporate the millisecond billing and new higher limits, and it was great to welcome a new contributor to the project as well. Congratulations Celete Blackwell on your [contributions](https://twitter.com/alex_casalboni/status/1334543668615720967). You know have even more ways to deploy AWS Lambda Power Tuning, so if you are using Terraform then this new update from Celete is going to be very handy indeed. The AWS Serverless Application Model (AWS SAM) also had a [new release, v1.13.1](https://github.com/aws/aws-sam-cli/releases/tag/v1.13.1) which you should check out. 

**EKS Anywhere**

EKS Distro is a distribution of the same version of Kubernetes deployed by Amazon EKS, which you can use to manually create your own Kubernetes clusters anywhere you choose. This generated a lot of buzz on Tuesday, so want to share some of what has been written and no doubt will add to that over the coming weeks.

[Amazon EKS Distro: The Kubernetes Distribution Used by Amazon EKS](https://aws.amazon.com/blogs/aws/amazon-eks-distro-the-kubernetes-distribution-used-by-amazon-eks/) from Martin Beeby is an intro and walks you how to get started including what you need to know, pricing and support information as well as what is coming soon. Allan Naim, Chandler Hoisington, Raja Jadeja, Micah Hausler, and Michael Hausenblas collaborate on [Introducing Amazon EKS Distro (EKS-D)](https://aws.amazon.com/blogs/opensource/introducing-amazon-eks-distro/) taking a closer look at what EKS Distro really is, the different ways to get started with EKS Distro and a look at some of the partner ecosystem you can already work with.

In the post [Introducing Amazon EKS add-ons: lifecycle management for Kubernetes operational software](https://aws.amazon.com/blogs/containers/introducing-amazon-eks-add-ons/) Nathan Taber and Jesse Butler share with you how you can easily add within your Amazon EKS clusters new add-ons that provide key functionality to support your Kubernetes applications. These add-ons include critical tools for cluster networking like the Amazon VPC CNI, as well as operational software for observability, management, scaling, and security. This looks at this in detail, how to set it up and how it works and then shares what you can expect early next year.

A related session which will be important for folks who running Amazon EKS is how to make sure you understand and follow security best practices. In this session, [Securing your Amazon EKS applications: Best practices](https://virtual.awsevents.com/media/1_fqz5r4ul) Jeremy Cowan walks you through the onion defence in depth model of how to approach this. Good session that if you are using containers you should be familiar with.

With EKS Anywhere, the containers team were excited to share an update to the Amazon EKS console. In [Introducing the new Amazon EKS console](https://aws.amazon.com/blogs/containers/introducing-the-new-amazon-eks-console/) Nathan Taber and Jesse Butler provide an breakdown of what the new experience looks like, which will work with your EKS clusters whether they are in the cloud or you are deploying them somewhere else as part of the EKS-Distro (EKS-D)

Make sure you check out the Containers from the Couch folk with their unboxing video which you can find on their You Tube page, 
[Unboxing EKS Distro](https://www.youtube.com/watch?v=YUS_LrlctHI) which is airing on December 7th.

At AWS we are customer obsessed and we work back from the customer and invent on their behalf. We use mechanisms like Working Backwards and we start by writing a press release before we begin the hard technical work. If you are interested in reading the Press Release for these new releases, check them out on the Amazon Day One blog, [AWS Announces Four New Container Capabilities](https://press.aboutamazon.com/news-releases/news-release-details/aws-announces-four-new-container-capabilities)

Looking for a link to the GitHub repo? Head on over to [eks-distro](https://github.com/aws/eks-distro)

**AWS Partner keynote**

If you missed this session, then Doug Yeum announced during the [AWS Partner Keynote](https://virtual.awsevents.com/media/1_503r0prg) the launch of the open source AWS SaaS Boost, which will provide a prescriptive framework to help you build your own SaaS based solutions. If you want to know more, then this week you can check out [Open source meets SaaS: Accelerating the path to SaaS adoption](https://virtual.awsevents.com/media/1_qg3dkb6g) where Tod Golding will show you how this open-source solution can jump-start your path to SaaS .

Check out the home page for [AWS SaaS Boost](https://aws.amazon.com/partners/saas-boost/) as well as read Todd's super deep dive on [Transforming Your Monolith to SaaS with AWS SaaS Boost](https://aws.amazon.com/blogs/apn/transforming-your-monolith-to-saas-with-aws-saas-boost/).

![saasboost](https://d2908q01vomqb2.cloudfront.net/77de68daecd823babbb58edb1c8e14d7106e83bb/2020/11/23/AWS-SaaS-Boost-Monolith-2.1.jpg)

**Babelfish for Aurora PostgreSQL**

How do you help shift the inertia and generate momentum when it comes to moving from proprietary to open source databases? When  enterprises have spent years building data models in something like Microsoft SQL Server that change can feel hard. Matt Asay's post offers a ray of hope and might be the catalyst you are looking for in [Want more PostgreSQL? You just might like Babelfish](https://aws.amazon.com/blogs/opensource/want-more-postgresql-you-just-might-like-babelfish/). This was probably my favourite announcement from Andy's keynote, and make sure you check out the sessions below that talk in more detail as well as provide a pretty cool demo of this in action.

**AWS Amplify**

[New AWS Amplify Admin UI Helps You Develop App Backends, No Cloud Experience Required](https://aws.amazon.com/blogs/aws/aws-amplify-admin-ui-helps-you-develop-app-backends-no-cloud-experience-required/) Marcia Villalba writes about a great new feature that I think a LOT of AWS Amplify developers are going to love. The introduction of a new capability to provide an admin screen/section feature to the applications you develop. Marcia uses a great example of a restaurant app where you might want to give the owner the ability to add/change new items to the menu. Whilst there are many ways you can achieve this, you can now uses the Admin UI in AWS Amplify to easily incorporate this. Find out more by reading Marcia's walkthrough.

![adminui](https://d2908q01vomqb2.cloudfront.net/da4b9237bacccdf19c0760cab7aec4a8359010b0/2020/11/24/06_content-1024x370.png)

**.NET Core**

[.NET 5 AWS Lambda Support with Container Images](https://aws.amazon.com/blogs/developer/net-5-aws-lambda-support-with-container-images/) Norm Johanson talks about the announced support for publishing Lambda functions as container images. As part of that release, the AWS Lambda .NET tooling to support building Lambda functions as container images for .NET Core 2.1 and 3.1, as well as full support for .NET 5 has been updated. This posts brings you up to speed and shows you how to package up your .NET Core applications using this new container packaging format, either from Visual Studio with the AWS Toolkit for Visual Studio or the .NET CLI using Amazon.Lambda.Tools.

**Sessions**

[Data Pipelines with Amazon Workflows for Apache Airflow](https://virtual.awsevents.com/media/1_067u2mc4) session from John Jackson that introduces the recently launched service, starting with some of the typical use cases before walking you through the AWS console experience, a demo of Amazon Workflows for Apache Airflow.

In the Developer Lounge, we had AWS Data Hero Manrique Lopez presenting on [Using Open Distro for Elasticsearch for developer analytics](https://virtual.awsevents.com/media/t/1_b18lgss7/186983763) where he takes a look under the covers of Cauldron.io and how it uses open source projects such as Open Distro for Elasticsearch. Nice demo too, with a quick look at the dashboard and some of the visualisations available. After you check the demo out why not try this on your own GitHub repo. Great stuff from Manrique.

[Red Hat OpenShift Service on AWS](https://virtual.awsevents.com/media/1_5i777zvz) Jeremy Eder, Distinguished Engineer at Red Hat and Ike Arias from AWS jointly present to share with you an over view of what is Red Hat Openshift and then talks about Red Hat Openshift on AWS (ROSA) and some of the ways that make this the best way to run Openshift on AWS. Jeremy then shows you what this will actually look like including a look at the command line interface, **rosa**.

Want to know more about Babelfish for Aurora PostgreSQL? Of course you do, well starting off with the database leadership session, [Building for the future with AWS databases](https://virtual.awsevents.com/media/1_7agzctza) Tobias Ternström does a great demo of some of the capabilities sticking with the tooling that many Microsoft SQL developers might be using. This is in the first 20 mins of this presentation so stick with it and check out the perfect pronunciation of the Hitchhikers Guide elements during the demo. #douglasadamnerd

Tobias ran his own session a little later, [Introducing Babelfish for Aurora PostgreSQL](https://virtual.awsevents.com/media/1_dli4b1vw) where he expanded upon the demo with a deeper look at exactly what is Babelfish including a look at what that means from an open source perspective and the design tenets which cover the no compromises to correctness, wire protocol compatibility and interoperability. Tobias is a great presenter so I urge you to seek this session out.

Whilst not strictly open source, AWS Proton was a new launch last week that generated a lot of interest. One of the key artefacts within this service however are templates, and these can be open sourced if you want, with samples provided for you. Find out more about AWS Proton in the session from Rafa Alvarez, [AWS Proton: Automating infrastructure provisioning & code deployments](https://virtual.awsevents.com/media/1_4y7w5alh). Check out the GitHub repository [here](https://github.com/aws-samples/aws-proton-sample-templates), [more here](https://github.com/aws-samples/aws-proton-sample-fargate-service). AWS Proton has also published a public roadmap on GitHub which you can view [here](https://github.com/aws/aws-proton-public-roadmap).

Rust is a popular language and increasingly being used within AWS and Amazon, and if you missed it then check out Matt Asay's post on Rust at AWS, [Why AWS loves Rust, and how we’d like to help](https://aws.amazon.com/blogs/opensource/why-aws-loves-rust-and-how-wed-like-to-help/). In his session, [Building technology standards at Amazon scale](https://virtual.awsevents.com/media/1_l9b33y2d), Marc Brooker walks us through how we approach moving to a new language like Rust. Covering the tenets and thinking on how we think about this within Amazon, this is definitely a session to bookmark and watch.

Nader Dabit's session [Accelerate that app with AWS Amplify open-source framework](https://virtual.awsevents.com/media/1_fdw4lekh)  provided a great introduction into AWS Amplify if you have yet to take a look at this open source framework for developing web and mobile applications.

If you use or care about Apache Kakfa, then Kai Waehner from Confluent did a great session, [App modernization on AWS with Apache Kafka and Confluent Cloud](https://virtual.awsevents.com/media/1_ywj8pqay) where you will learn more about Kafka and see how it is relevant when it comes to application modernisation. This session covers how you can benefit from the open-source Apache Kafka ecosystem by connecting your legacy, on-premises systems to the cloud and he also walks you through real customer stories about timely insights gained from event-driven applications built on an event streaming platform from Confluent Cloud running on AWS.

If you use and love Redis, then you need to watch Yossi Gottlieb and Madyln Olson take a look at the Redis timeline, road map as well as the background and update on the new Redis governance model that is shaping the future of the open source database technology that everyone loves. Watch their session, [Redis 2020: Creating a community-driven project](https://virtual.awsevents.com/media/1_g9yt482o).

If you missed the AWS on Air session covering EKS Everywhere, then Raja Jadeja and Allan Naim, product managers in EKS and colleague Cobus talked about the EKS Anywhere launch announcement which you can replay [here](https://virtual.awsevents.com/media/1_1kc6g3dk?nc2=reinv20_m_aoa). Also on AWS on Air was the team behind the AWS Amplify UI, so if you missed that session check out the session, including demo [here](https://t.co/Rgr4B5qico?amp=1).

If you are looking to learn more about the RabbitMQ capabilities added to Active MQ, then Sam Dengler's session [Application migration & hybrid cloud with RabbitMQ](https://virtual.awsevents.com/media/1_bya5r2v9) is just what you need. Sam will take you through the history of Active MQ including why business are increasingly looking for message brokers as part of application modernisation, and then rolls his sleeves up to walk you through exactly what get with the ActiveMQ for RabbitMQ service. If you are new to RabbitMQ then this is a good session to learn more about the core concepts and components, and this session also covers migration and hybrid architectures that are supported and you can build.

Michael Hausenblas' session on [Open-source observability at AWS](https://virtual.awsevents.com/media/1_xztncttn) is your must watch session if you want a good primer into what exactly is observability and the important open source projects that you need to know about including taking a look at the CNCF landscape around this space. Find out more about some of the challenges around this space and how the OpenTelemtry set of standards is your first step in addressing your observability needs.

Allan Naim's session [Amazon EKS Anywhere: Manage your Kubernetes clusters on premises](https://virtual.awsevents.com/media/1_aiv3ukrd) provided the first peek at what Amazon EKS Anywhere looks like, covering the current "as is" and how Amazon EKS Anywhere will help customers reduce complexity and provide a consistent experience for managing and deploying your kubernetes clusters. Whilst Allan did cover the Amazon EKS Distro during this talk, for a more comprehensive look at Amazon EKS Distro then you need to check out Raja Jadeja's session [Amazon EKS Distro: An open-source distribution of Kubernetes](https://virtual.awsevents.com/media/1_rfg6oyit). Starting with what EKS means to us at AWS, how it fits in with Amazon EKS to covering how we approach building the Amazon EKS Distro, this session is packed with essential information to help inform your decision making. I stayed up late for this session and was happy I did.

### Other open source blog posts

**PHP**

[AWS Lambda can now run PHP using Docker Containers](https://mnapoli.fr/aws-lambda-php-docker-containers/) Matthieu Napoli shares even more ways to run PHP on Lambda, taking a look at how to use the announcements from last week as he compares runtimes vs containers. No spoilers, read the post as Matthieu's posts are always worth reading.

**Mock and PyTest on AWS**

[How to test your AWS code using Moto and Pytest](https://www.learnaws.org/2020/12/01/test-aws-code/) Abhishek Ray shares a blog post on how to use a couple of open source tools to help do local testing of your AWS code. Moto is a python library that makes it easy to mock AWS services and PyTest is a testing framework. Combine them both, and you have something you can use to get started and Abishek shows you how.

**AWS CDK**

[CDK tips, part 4 – how to migrate from CloudFormation to CDK](https://www.endoflineblog.com/cdk-tips-04-how-to-migrate-from-cloudformation-to-cdk) Adam Ruka shares this post and video on how to migrate an existing CloudFormation Stack to be managed through the AWS CDK. With handy links to Parts 1, 2 and 3, make sure you check this out for your weekly CDK fix.

**TCK**

[Introducing TCK.work](https://www.tomitribe.com/blog/introducing-tck-work/) David Blevins shares in this post, a system they have setup to speed up projects getting their [TCK](https://en.wikipedia.org/wiki/Technology_Compatibility_Kit) results. The TCK is important as it is the set of tests that you need to pass in order to ratify you EE status. Running on AWS, David walks you through the details of how this is setup and how you it works. Take a look as there is a call to action at the end.

**Hugo**

[Deploying a Hugo Site to AWS Lightsail Containers](https://www.jeremymorgan.com/tutorials/golang/how-to-deploy-hugo-aws-lightsail-containers/) there are many different ways I have shared in this newsletter that you can use/deploy Hugo, an open source markdown based static site generator, but Jeremy Morgan takes you through how you can get this up and running when using AWS Lightsail Containers. This was recently launched, so if you wanted to check it out, then try this out.

### Quick updates

**AWS Security Hub**

AWS Security Hub can now automatically receive findings from the open source tool Kube-bench Kube-bench checks whether your Kubernetes cluster is configured in accordance with the recommendations from the Center for Internet Security (CIS), supporting both the CIS Kubernetes Benchmark and the CIS Amazon Elastic Kubernetes Service (Amazon EKS) Benchmark. Kube-bench’s findings about non-compliant configuration settings can be viewed within Security Hub. In addition, Security Hub’s integration with Cloud Custodian is now available in the AWS China (Beijing) Region operated by Sinnet and in the AWS China (Ningxia) Region operated by NWCD. The open source tool Cloud Custodian can both send and receive findings to/from Security Hub. This brings the total number of AWS service and AWS Partner Network (APN) Technology Partner integrations available in Security Hub to 61.

**Elasticsearch**

You can now use Amazon Elasticsearch Service as a target data store with AWS Glue Elastic Views. Now in limited preview, AWS Glue Elastic Views is a new capability of AWS Glue that makes it easy to combine and replicate data across multiple data stores without you having to write custom code. With AWS Glue Elastic Views, you can use familiar Structured Query Language (SQL) to quickly create a virtual table—called a view—from multiple different source data stores. Based on this view, AWS Glue Elastic Views copies data from each source data store and creates a replica—called a materialized view—in a target data store. AWS Glue Elastic Views monitors for changes to data in your source data stores continuously, and provides updates to your target data stores automatically, ensuring data accessed through the materialized view is always up-to-date.

With AWS Glue Elastic Views, you can now create views over data in Amazon DynamoDB and materialize these views in Amazon Elasticsearch Service. This enables you to use DynamoDB to as a key-value and document database with single-digit millisecond performance, and seamless integrate it with Amazon Elasticsearch Service to provide fast and relevant search experiences for your customers–without writing any code. AWS Glue Elastic Views is serverless and scales capacity up or down automatically based on demand, so there’s no infrastructure to manage.

### Events for your diary

**re:Invent 2020**
**November 30th to December 18th**

Now in full swing, use this list to help you find the sessions you are interested in. Some of these will now be in on-demand view (the sessions that ran last week)

**Open source track**

* OPN 203: Redis 2020: Creating a Community-Driven Project
* OPN 305: Build real-time apps with Apache Flink
* OPN 206: Building End-To-End ML Workflows with Kubeflow Pipelines
* OPN 301: Open Source Observability at AWS
* OPN 302: The Serverless LAMP stack
* OPN 303: Open Source Meets SaaS: Accelerating the Path to SaaS Adoption
* OPN 304: Open source failure injection on AWS
* OPN 201: Introduction to GraphQL
* OPN 204: Accelerate that App! with Amplify opensource framework
* OPN 202: App modernization on AWS with Apache Kafka & Confluent Cloud

**Other open source sessions**

* ADM 301 Running ultra-high throughput ad tech workloads on Aerospike
* AIM 313 Scaling MLOps on Kubernetes with Amazon SageMaker Operators
* AIM 402 Fast distributed training and near-linear scaling with PyTorch on AWS
* AIM 404 Productionizing R workloads using Amazon SageMaker, featuring Siemens 
* AIM 405 Train large models with billions of parameters in TensorFlow 2.0
* ARC 307 Going global in minutes: Multi-Region expansion simplified
* CMP 206 HPC on AWS: Innovating without infrastructure constraints 
* CON 201 Getting an insight into your Kubernetes applications
* CON 202 AWS Copilot: Simplifying container development
* CON 207 Define AWS service resources with AWS Controllers for Kubernetes 
* CON 211 Red Hat OpenShift Service on AWS
* DAT 314 Running Apache Cassandra workloads with Amazon Keyspaces
* DOP 202 AWS CDK: What’s new and what’s next
* FWM 201 Power modern serverless applications with GraphQL and AWS AppSync
* FMW 202 Empower front-end web and mobile app development with AWS Amplify
* FMW 303 Build iOS & Android mobile apps in record time with Flutter and AWS Amplify
* FMW 304 Unify access to siloed data with AWS AppSync GraphQL resolvers
* FMW 306 Best practices to securely operate GraphQL at scale with AWS AppSync
* IOT 303 Developing and deploying modern edge applications at scale
* NFX 302 Simplifying delivery as code with Spinnaker and Kubernetes

**Virtual ROS-Industrial Conference 2020**
**December 15 - 16, 2020**

The 8th edition of ROS-Industrial Conference will be held as a virtual event. It is not only the annual community meeting for the European ROS-Industrial community but this years event is also the final event of the H2020 ROSIN project. The conference gives you the chance to see the newest technical developments and to meet people and companies, which are active in the ROS community.

Learn more and sign up [here](https://rosindustrial.org/rosindustrial-conference-2020).

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen).

### Your feedback matters!

I have put together a short feedback survey, which I would ask you to take - it will take no more than 2 minutes. You can access [here](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn). Many thanks!

[Take the survey](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn)