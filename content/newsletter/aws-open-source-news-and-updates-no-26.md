---
title: 'AWS open source news and updates No. 26'
date: '2020-06-29'
tags : [ oss-newsletter ]
---
## June 29th - Instalment #26

No.26 and officially the half way point of the year. There has been no let up in open source projects and posts. This week we have machine learning deep dives and projects, including a reinforcement learning project that might help you win at Poker, security, serverless and modern application posts.

It was really good to catch up this week with **Arpit Mohan**, CTO and co-founder of Appsmith about the topic of open source, growing awareness and different licensing models. Appsmith looks like a very interesting project, which they are planning to open source so watch this space. Make sure you check out the project too. Arpit wrote about this on dev.to, and you can check out his post [here](https://dev.to/mohanarpit/show-dev-i-built-a-frontend-as-a-service-product-for-developers-to-build-custom-apps-29o0).

### Project of the Week

[Anton Babenko](https://www.linkedin.com/in/antonbabenko/), AWS Community Hero, got in touch to tell me about some of the open source projects he has been working on. If you use Terraform then you will almost certainly be using some of these [Terraform AWS modules](https://github.com/terraform-aws-modules) that are created and supported by the community. One project that Anton wanted to highlight though, was [Terraform AWS Lambda](https://github.com/terraform-aws-modules/terraform-aws-lambda). This Terraform module takes care of a lot of AWS Lambda/serverless tasks (build dependencies, packages, updates, deployments) in countless combinations and helps reduce the complexity of doing this in Terraform.

Anton is also working on **serverless.tf** - an opinionated open-source framework for developing, building, deploying, and securing serverless applications and infrastructures on AWS using Terraform. I will admit that my first thought when Anton shared this was Why? Well, Anton has this covered in the README.md, where he responds:

> Most likely, the first question you are wondering - Why do you do this? Or, if you know me and have been following my projects for some time, you may think: Yes, we can do a lot with Terraform, but wrong is with existing solutions available already?
> 
> Before answering what is wrong, let's set the stage by highlighting the good parts of existing toolset available for serverless developers.

I will leave it on that cliff hanger, but suggest you read the clear introduction and thinking behind serverless.tf.

Find out more on the GitHub repository [here](https://github.com/antonbabenko/serverless.tf).

### Feedback!!

I have put together a short feedback survey, which I would ask you to take - it will take no more than 2 minutes. You can access [here](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn). Many thanks!

[Take the survey](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn)

### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created.

So thank you to Capetta, Dan Blanco, Sebastian Doell, CyberArk, Kyle Lee, Saša Savić, [Nathaniel Beckstead](https://twitter.com/scriptingislife), [Martin Haynes](https://twitter.com/dotmhio), z0ph, elpy, bluematador, Ian Mckay, Norm Johanson, Sanjeet Sahay, Danilo Poccia, Jeremy Cowan, Rohan Mangal, Umair Ishaq, John Formento, Jr ,Adam Cerini, Moheeb Zara, Re Alvarez-Parmar, Jaswanth Kumar Jonnalagadda, Dave Bechberger, Tom McCarthy, John Dusaitis, Emily Shea, Julie Lerman,  The Consulting CTO, Marvin Ferber, Andrea Scuderi, Chaim Rand, Skyscanner, [Anton Babenko](https://www.linkedin.com/in/antonbabenko/) and [Eric Steinberger](https://twitter.com/EricSteinb) 

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

**s3eker**

This project from [Nathaniel Beckstead](https://twitter.com/scriptingislife), helps you uncover and find open S3 buckets, and it does this by looking through your code and leverages an external site, ulrscan.io, as a way of understanding whether a found S3 bucket that is public may be legitimate.

GitHub repository is [here](https://github.com/becksteadn/s3eker) and Nathaniel provides some Terraform scripts to help you deploy this.

**dyn-o-might**

[Martin Haynes](https://twitter.com/dotmhio) shares his experimental project, dyn-o-might, which is a wrapper around AWS DynamoDB for Node developers. If you are a Node developer working with AWS DynamoDB, then check this out.

The GitHub repository can be [found here](https://github.com/dotmh/dyn-o-might).

**mockingbird**

Last week I shared RoboRover from Saša Savić, and this week I want to share his [mockingbird](https://github.com/sasasavic82/mockingbird/blob/master/README.md) project, an open source project that is a distributed and programable fault simulation mocking service. It provides capabilities that allows you to simulate a number of different faults. This means that you can assess how your applications or services will work under unexpected situations under load.

GitHub repository [here](https://github.com/sasasavic82/mockingbird/blob/master/README.md).

To get started with Chaos Engineering, check out [Adrian Hornsby](https://twitter.com/adhorn)'s [collection of blog posts here](https://dev.to/aws/the-chaos-engineering-collection-5gdm).

**Instance Watcher**

If are looking for a project that sends you daily reminders of the list of AWS instances you have running across you AWS regions, then look no further. This project from **z0ph** will do this across not only EC2 instances, but RDS, SageMaker, Redshift and more. This project integrates with email, Microsoft Teams or Slack and provides an easy to follow set of steps to get you up and running. Check out the [GitHub repository here](https://github.com/z0ph/instance-watcher).

**swurl**

This project from **elpy** provides similar functionality to curl, except allows you to make signed HTTP requests to AWS over socks5. The README.md provides a detailed breakdown of different approaches of connected to AWS resources and some of the limitations that these had for when elpy was trying to do. The end result was a tool to communicate with an endpoint in a private VPC over SOCKS proxy. Check out the GitHub repository [here](https://github.com/elpy1/swurl).

**Cloud CORE**

There are a number of useful projects to help customers reduce their AWS bill, and Cloud CORE from bluematador is another one. Cloud CORE is an open source tool that helps you calculate real-time, resource-specific costs in your AWS accounts, and they have put together a video of how this works (it is short, check it out [here](https://www.youtube.com/watch?v=Gfw6kMlHouA)). To get the code, head over to the GitHub repository [here](https://github.com/bluematador/cloud-core/).

**Former2**

[Former2](https://github.com/iann0036/former2) from Ian Mckay is an open-source project that lets you create CloudFormation templates from existing resources. If you are familiar with or have used the Console Recorder, then you will kind of know what this tool does. Check out the GitHub repository [here](https://github.com/iann0036/former2). You can run your own instance of Former2 or use the one linked in the repo.

**distance-assistant**

Last week I shared the post from Brad Porter at Amazon, on the use of machine learning to provide real time social distancing feedback. That project, distance assistant has now been open sourced and you can find the source code [here](https://github.com/amzn/distance-assistant). Along with the code you have a detailed kit list of what you need to try this project out for yourself.

**lambda-web-scraper**

This open source project is an example of a web scraper running on AWS Lambda and Lambda Layers. GitHub repository link [here](https://github.com/aws-samples/lambda-web-scraper-example). You can also read the post that talks about this in more depth here, [Serverless Architecture for a Web Scraping Solution](https://aws.amazon.com/blogs/architecture/serverless-architecture-for-a-web-scraping-solution/) from Dzidas Martinaitis.

**DREAM**

[DREAM](https://arxiv.org/abs/2006.10410) stands for Deep Regret minimisation with Advantage baselines and Model-free learning, and [Eric Steinberger](https://twitter.com/EricSteinb) shared details of this project over Linkedin this week, with the aim of 1)helping researchers, 2) anyone wanting to learn about Deep RL in imperfect information games and 3) enabling reproducibility of results (from the research paper linked). Eric provides all you need to get this up and running on AWS too.
 
![DREAM](https://github.com/EricSteinberger/DREAM/raw/master/DREAM_plots.png)

**cirrus**

[Cirrus](https://github.com/blueseph/cirrus) is an open source project from Dan Blanco that is a simple CLI tool to easily handle deploying and deleting CloudFormation stacks. Cirrus is primarily meant to be used while developing templates. It is still in early stages of development, so if this sounds useful give it a go and feedback your experience to Dan.

![cirrus](https://raw.githubusercontent.com/blueseph/cirrus/master/cirrus.gif)

### Retro machine

**LambaGuard**

A project that came up this week that is worth sharing in case you were not aware of it is Lambguard, from the Skyscanner engineering team. LambdaGuard is an AWS Serverless Security auditing tool to help you identify potential security weakness or policy deviations by providing greater visibility, showing the dependencies and configurations from a security perspective.

Check out the GitHub repository [here](https://github.com/Skyscanner/LambdaGuard), and the Skyscanner team also shared details in an in depth blog post, [Introducing LambdaGuard — a security scanner for AWS Lambda](https://medium.com/@SkyscannerEng/introducing-lambdaguard-a-security-scanner-for-aws-lambda-f5c6e23f8345) which I encourage you to read.


### Blog posts you should check out

**TensorFlow deep dive with Mobileye, an Intel Company**
 
[Deep Dive on TensorFlow training with Amazon SageMaker and Amazon S3](https://medium.com/@julsimon/deep-dive-on-tensorflow-training-with-amazon-sagemaker-and-amazon-s3-12038828075c)
 by Chaim Rand, Machine Learning Algorithm Developer at Mobileye, Chaim talks about how they train their TensorFlow neural networks in the Cloud and how they were able to reduce training time and cost by using some specific Amazon SageMaker functionality. If you are currently working with TensorFlow then this is a must read post.
 
**Swift API's using Serverless**

[How to Create an AWS Serverless REST API in Swift](https://t.co/Qe1TAF2AAB?amp=1) from Andrea Scuderi walks you through how to implement a basic REST API using the new Swift runtime to implement a serverless stack (with the Serverless Framework) with API Gateway, AWS Lambda and AWS DynamoDB. I have covered the Swift runtime on AWS in previous episodes, so make sure you look back and have a read of those if you want to dive deep into Swift on AWS.

Read the post and then check out the GitHub repository [here](https://github.com/swift-sprinter/aws-serverless-swift-api-template).

**Amplify DataStore and SwiftUI**

[Building a Cash Flow App with Amplify DataStore and SwiftUI ](https://aws.amazon.com/blogs/mobile/building-a-cash-flow-app-with-amplify-datastore-and-swiftui/), is Kyle Lee's first post and in this tutorial, you will use SwiftUI and DataStore’s local persistence to create an app called Cash Flow. This will be a simple app that allows you to keep track of your transactions by adding and subtracting inputted amounts to and from the account balance.


**Robotics: Gazebo**

[Using Sweethome3D models in the Gazebo Simulator Part 1](https://marvinferber.net/?p=128) Marvin Ferber provides a post on how to get started with creating your own 3D scenes using Gazebo.
![image](https://marvinferber.net/wp-content/uploads/2017/05/doors.png)
This is one of the things I have been playing with, specifically how do you get started with Gazebo and what are the best tools to get started with creating models or understanding the library of models you can use which you can then use within Gazebo. This will help provide you a much clearer view on this.


**Bastions on demand**

[Bastions on Demand](https://theconsultingcto.com/posts/bastions-on-demand/), this is an interesting post from The Consulting CTO blog that provides a walk through and source code on how to build a more secure bastion host solution, leveraging AWS Fargate to create on demand bastions which means you can reduce your attack surface and reduce the maintenance burden of having those permanent bastion hosts.

GitHub repository [here](https://github.com/jdhollis/bastions-on-demand/blob/master/README.md).

**Modernising .NET applications**

[Transform Your ASP.NET Core API into AWS Lambda Functions](https://www.codemag.com/Article/2008041/Transform-Your-ASP.NET-Core-API-into-AWS-Lambda-Functions) a post from Julie Lerman, which is a good post to get started if you are a .NET developer and looking to go serverless with .NET on AWS. Julie walks you through taking your .NET Core application and using the AWS Serverless Application Model (SAM) to deploy that onto AWS Lambda and all from within Visual Studio too.

**CI/CD Pipeline for serverless applications**

[A basic CI/CD pipeline for serverless apps](https://emshea.com/post/serverless-cicd?utm_source=newsletter&utm_medium=email&utm_content=offbynone&utm_campaign=Off-by-none%3A%20Issue%20%2395) a post from Emily Shea, shows you how to move from the console when deploying your serverless applications (built on SAM) to building your first CI/CD pipeline. This post will walk you through the concepts, terms as well as step by step instructions of how to get going.

![pipeline](https://emshea.com/static/images/serverless-cicd/pipeline-diagram-1280.png)

**CyberArk conjur**

If you are looking for an open source secrets manager, then this project from CyberArk should be of interest. In this post by Joe Garica, [AWS IAM Authenticator Tutorial For Conjur Open Source](https://www.conjur.org/blog/aws-iam-authenticator-tutorial-for-conjur-open-source/), Joe walks you through setting up Conjur on AWS, integrating this with AWS IAM and then showing you how you can then store and access secrets which you can access from your AWS EC2 instances or Lambda functions.

**serverless deployments with GitHub actions**

[Simple automate deployment Lambda with Serverless framework and Github Action](https://medium.com/@pyaephyoeshein/simple-automate-deployment-lambda-with-serverless-framework-and-github-action-ddd5b065e953) post from Pyae Phyoe Shein, walks you through automating your serverless application deployments using the Serverless framework and the use of GitHub actions.

**AWSCyberRange — CommandCenter**

This is the second Cyber range post this week, and this post from Capetta, [AWSCyberRange — CommandCenter (c2) released to DockerHub](https://medium.com/aws-cyber-range/awscyberrange-commandcenter-c2-released-to-dockerhub-4f398a25b36d), he introduces CommandCentre, a container available on DockerHub that provides everything you need to get started. If Cyber range looks like something might find useful (read post later) then this is a great way to bootstrap your effort.

**AWS CodePipeline via AWS CDK**

[AWS CodePipeline: Setup And Maintenance From Scratch](https://hackernoon.com/aws-codepipeline-setup-and-maintenance-from-scratch-gz2x3uvt?source=rss) Mark Avdi shows you how to build an AWS CodePipeline stack using AWS CDK. This is a detailed walkthrough and he shares some of the issues he encountered and how he overcame them. Nice post Mark!	

### AWS updates

**Lambda Powertools**

In [Simplifying serverless best practices with Lambda Powertools](https://aws.amazon.com/blogs/opensource/simplifying-serverless-best-practices-with-lambda-powertools/), Tom McCarthy introduces the open source project Lambda Powertools and then walks you through how you would use this, using one of the serverless application examples.

![architecture](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2020/06/18/image2-1.png)

If you are building serverless applications, then Lambda Powertools is a project you will find very handy indeed.

A[utomatically create and delete custom sub-domains for your branch deployments with Amplify Console](https://aws.amazon.com/blogs/mobile/automatically-create-and-delete-custom-sub-domains-for-your-branch-deployments-with-amplify-console/) a post by Nikhil Swaminathan, talks you through  two new pattern-based branch deployment features that enable teams to automatically create and delete sub-domains every time a new branch or pull-request is added or removed from a Git repository. This allows teams practicing feature branch or GitFlow workflows to spin up ephemeral branch or pull-request deployments tied to their custom domain on the fly without any extra configuration.

**Migrating from Blazegraph to Amazon Neptune**

During the lifespan of a graph database application, the applications themselves tend to only have basic requirements, namely a functioning W3C standard SPARQL endpoint. However, as graph databases become embedded in critical business applications, both businesses and operations require much more. Critical business infrastructure is required not only to function, but also to be highly available, secure, scalable, and cost-effective.

Blazegraph is an open source graph database that many organisations have deployed and manage themselves, and in this post, [Moving to the cloud: Migrating Blazegraph to Amazon Neptune](https://aws.amazon.com/blogs/database/moving-to-the-cloud-migrating-blazegraph-to-amazon-neptune/), Dave Bechberger walks you through how you can migrate those workloads to Amazon Neptune.

**Grafana and Prometheus**

[Monitoring Amazon EKS on AWS Fargate using Prometheus and Grafana](https://aws.amazon.com/blogs/containers/monitoring-amazon-eks-on-aws-fargate-using-prometheus-and-grafana/) from  Re Alvarez-Parmar and Jaswanth Kumar Jonnalagadda shows you how you can monitor your Kubernetes pods running on Fargate using Prometheus and then view that information using Grafana.
![dash](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2020/06/24/image-1.jpg)

**Polly and PyPortal**

[Adding voice to a CircuitPython project using Amazon Polly](https://aws.amazon.com/blogs/compute/adding-voice-to-a-circuitpython-project-using-amazon-polly/), this post from Moheeb Zara shows you how to leverage the cloud to add voice to an off-the-shelf micro controller, using an Adafruit PyPortal. This post will help you build that, so check out the GitHub repository [here](https://github.com/aws-samples/aws-serverless-pyportal-polly).

![architecture](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2020/06/23/image003-1-1024x290.png)

**cyber range**

I have mentioned this project in a previous episode ([No.2](https://dev.to/aws/open-source-news-and-updates-2-44b2)) so was pleased when I saw this post, [What is a cyber range and how do you build one on AWS?](https://aws.amazon.com/blogs/security/what-is-cyber-range-how-do-you-build-one-aws/) from John Formento, Jr. and Adam Cerini.

This project provides a bootstrap framework for a complete offensive, defensive, reverse engineering, & security intelligence tooling in a private research lab using the AWS Cloud.It simply provides a researcher with a disposable offensive / defensive AWS-based environment in less than 5 minutes. In this post, John and Adam provide advice on how you can build a current cyber range using AWS services.

**.NET Core on Beanstalk**

[AWS Elastic Beanstalk adds .NET Core on Linux platform](https://aws.amazon.com/blogs/developer/aws-elastic-beanstalk-adds-net-core-on-linux-platform/) post from Norm Johanson shows how we have made it easy to get ASP.NET Core applications deployed, extending the .NET support with the creation of the new .NET Core on Linux platform. If you are already running a .NET Core application with the existing .NET on Windows Server platform migrating to the new platform can be as simple as creating a new environment with the new .NET Core on Linux platform.

**Jenkins and Blue/Green deployments with ECS**

[Blue Green Deployments with the ECS External Deployment Controller](https://aws.amazon.com/blogs/containers/blue-green-deployments-with-the-ecs-external-deployment-controller/) a collaboration between  Jeremy Cowan, Rohan Mangal, and Umair Ishaq, talks about the introduction of “external controller,” teams using other CI/CD tools (in this example, Jenkins) had to introduce an additional ECS service to achieve the same goal, giving teams the flexibility to use their existing CI/CD tools.

**AWS CDK Solutions Constructs**

[AWS Solutions Constructs – A Library of Architecture Patterns for the AWS CDK](https://aws.amazon.com/blogs/aws/aws-solutions-constructs-a-library-of-architecture-patterns-for-the-aws-cdk/) a post from Danilo Poccia introduces the launch of the [AWS Solutions Constructs](https://aws.amazon.com/solutions/constructs/), an open source extension library for the CDK that provides well-architected patterns to help you build your unique solutions. CDK constructs mostly cover single services. This is available now for TypeScript and Python AWS Solutions Builders team is working to make these constructs also available when using Java and C#.

AWS Solutions Constructs provide multi-service patterns that combine two or more CDK resources, and implement best practices such as logging and encryption. Danilo walks you through using some of these to help you get started.

**Neo4j to Neptune capture and replication**

After you migrate from an existing graph database to Amazon Neptune, you might want to capture and process changed data in real time. Continuous replication of databases using the change data capture technique allows you to unlock your data and make it available to other systems for use cases such as distributed data processing. In this post, [Change data capture from Neo4j to Amazon Neptune using Amazon Managed Streaming for Apache Kafka](https://aws.amazon.com/blogs/database/change-data-capture-from-neo4j-to-amazon-neptune-using-amazon-managed-streaming-for-apache-kafka/), Sanjeet Sahay provides a solution for existing users of Neo4j to easily automate streaming CDC to Neptune using Amazon MSK in a few simple steps and explains how to scale, extend, and monitor it.

![neo](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2020/05/29/Change-data-capture-from-Neo4j-A.png)

Check out the GitHub project too for [cdc-neo4j-msk-neptune](https://github.com/aws-samples/cdc-neo4j-msk-neptune).

**Kafka**

[Streaming web content with a log-based architecture with Amazon MSK](https://aws.amazon.com/blogs/big-data/streaming-web-content-with-a-log-based-architecture-with-amazon-msk/) blog post from Sebastian Doell looks at an interesting approach to deliver real time news and content updates to your applications using Kafka. Whilst you might typically associate streaming log data with technology such as Kafka, this post shows how you can use the same technology stack to deliver real time news and content updates to your applications and leverage the realtime and scalability that Kafka brings. Source code is provided too, so you can use this as the basis of your own projects. GitHub repository [here](https://github.com/aws-samples/aws-msk-content-streaming).

![daigram](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2020/06/26/StreamingWebBasedMSK_1.gif)

### Quick updates

**MySQL**

* Amazon RDS for MySQL has been updated to support release 5.6.48 and release 5.7.30 of the MySQL database. These releases include a number of bug fixes as well as functionality improvements.
* Amazon Aurora Serverless is now available with MySQL 5.7 compatibility. MySQL 5.7-compatible Aurora offers enhancements such as JSON support, spatial indexes, and generated columns, and is up to 5X faster than MySQL 5.7

**PostgreSQL**

* PostgreSQL 13 Beta 1 is now available in the Amazon RDS Database Preview Environment, allowing customers to test the beta version of PostgreSQL 13 on Amazon RDS.  

### In other news

**MLflow joins Linux Foundation**

Databricks has announced that the MLflow project is joining the Linux Foundation. You can check out the full announcement on the Linux Foundation site, [The MLflow project joins the Linux Foundation](https://www.linuxfoundation.org/press-release/2020/06/the-mlflow-project-joins-linux-foundation/).

**Open source business**

This post that I found via Hacker News is well worth your time. [How to sell open source software](https://opensource.com/article/20/6/sell-open-source-software) is a post from the folks at Glyptodon who created Guacamole, a very much loved open source project.

---

### Share your open source projects 

Do you have some content you want to share with a broader audience? We are always looking for guest content for the AWS Open blog. Please get in touch (via comments below) and I would love to speak with you about what you are doing in open source. We are always looking for interesting new content.

The best submissions will get some AWS Credit codes as a thank you.


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)