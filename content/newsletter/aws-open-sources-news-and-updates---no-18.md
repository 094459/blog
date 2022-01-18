---
title: 'AWS open sources news and updates - No. 18'
date: '2020-05-04'
tags : [ oss-newsletter ]
---
## May 4th - Instalment #18

Episode 18, is the open source Force strong in you? 

A post from colleague Matt Asay this week, [Remembering when open source is fun](https://www.infoworld.com/article/3539234/remember-when-open-source-was-fun.html) made me think about the first open source projects I got my hands on (Apache httpd server, back in 1998). Good times indeed, but it wasn't until later that I did my first contribution (a security module for Atlassian's Confluence to enable SSO).

What was your first project and what made you cross from user to contributor? I am going to be running some video interviews of open source developers telling their story, so if you are interested in taking part, then let me know. I will share the Open Source Builders videos in the coming weeks and hope it will inspire many more builders to start their open source journeys.

### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created.

So thank you to Weaveworks, Cole (@OwnThe_Cloud), Jeremy Daly (@jeremy_daly), Ramon Postulart (@ramonpostulart), Riccardo Padovani (@rpadovani93),  Sito Ruíz-Bravo, Andy Hopper , Norm Johanson, Heitor Lessa (@heitor_lessa), Randall Hunt (@jrhunt), Amit Mukherjee, Georges Leschener 


### Latest from open source projects

**eksctl 0.18.0**

![eksctl logo](https://github.com/weaveworks/eksctl/blob/master/logo/eksctl.png?raw=true)
If you are running containers on AWS, then you will most likely be using this open source project that Weaveworks put together. eksctl is a simple CLI tool for creating clusters onEKS, the managed Kubernetes service for Amazon EC2 and Fargate.

This week saw the [latest release (0.18.0](https://github.com/weaveworks/eksctl/releases/tag/0.18.0))

**Raspberry Pi on Cloud 9**

I am a huge fan of the Raspberry Pi single board computers, and have lots of them around my house and they are my go to board for tinker projects. I have also standardised on AWS Cloud 9, a Cloud based integrated development environment. So when I saw this project, I was very happy indeed.

Find out how to run [AWS Cloud9 on your Raspberry Pi](https://ownthe.cloud/posts/) - it is an old post, but new to me and one I just had to share. There are a good selection of other posts on using AWS with your Raspberry Pi so I shall be bookmarking this blog.

Thank you Cole (@OwnThe_Cloud)!

**Amazon DynamoDB**

Jeremy Daly, AWS Serverless Hero and publisher of the excellent [offbyone](https://www.jeremydaly.com/newsletter/?utm_source=offbynone.io) (if you haven't already you should subscribe - you can thank me later) has a number of open source projects but a Tweet this week caught my eye. DynamoDB Toolbox is a simple collection of tools that you will find useful if you work with DynamoDB on a day to day (or even infrequent for that matter basis). From the project repo:

>The DynamoDB Toolbox is a simple set of tools for working with Amazon DynamoDB and the DocumentClient. It lets you define your data models (with typings and aliases) and map them to your DynamoDB table. You can then generate parameters to put, get, delete, and update data by passing in a JavaScript object. The DynamoDB Toolbox will map aliases, validate and coerce types, and even write complex UpdateExpressions for you.
>

[v2 is still in development](https://github.com/jeremydaly/dynamodb-toolbox), and Jeremy has put stated that this contains breaking changes to v1 ([which you can find here](https://github.com/jeremydaly/dynamodb-toolbox)).

As always, Jeremy is looking for feedback and contributions, so why not check it out and let Jeremy know what you think.

Thank you Jeremy (@jeremy_daly)!

**Amplify**

This [post on dev.to from Ramon Postulart](https://dev.to/rpostulart/build-a-serverless-quiz-in-days-with-react-and-aws-amplify-datastore-53kb) on how to build a simple Quiz using AWS Amplify is something I am going to be trying out this week. You can actually check out the demo of the application at https://www.kwizz.guru - it has a admin part that allows you to build the actual questions and then the user part which is where you take part in the quiz. Looks like this could be a fund project for you to try out and maybe built upon. Let Ramon know what you think either way.

![Architecture diagram ](https://res.cloudinary.com/practicaldev/image/fetch/s--OiDklYr9--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/ukkl0jdxf1000h6fjnp6.jpg)

You can find the [Github repo for kwizz](https://github.com/alowa-apps/kwizz) here.

Thank you Ramon (@ramonpostulart)!

**Daintree**

Daintree is a very interesting early project from Riccardo Padovani (@rpadovani93), an open source alternative to the AWS Console. In his blog post announcing the project, [Introducing Daintree](https://rpadovani.com/introducing-daintree), Riccardo talks about the motivation for this project:

>Daintree has born wanting to fix one particular problem of the AWS Console: the impossibility to see resources from multiple regions in the same view.
>

![Link to demo](https://www.daintree.app/assets/features/multiple-regions.gif)

As this is a very early release, Riccardo has [documented](https://www.daintree.app/#/about) what it can do and what features are missing. This is where you lot all come in - if this is something that you think is useful, then Riccardo is looking for users to provide feedback and [contributors](https://www.daintree.app/#/contribute) too. Development is active, so keep an eye on the [changelog](https://www.daintree.app/#/changelog) to see what new has been added since I wrote this.

Read the document and give it a test drive. You only need to provide it with your AWS access/secret key to login and then you can start. You select the regions you are interested in and then that is it, straight to the console. It allows you to see Networking and EC2 resources at the moment, but I still found that useful. I will be keeping an eye out for this project going forward, so thank you Riccardo (@rpadovani93)!

**Wazuh**

This was a completely new project for me, Wazuh is an open source security stack, that does the usual stuff you would expect (SEIM, IDS, Analytics and lots lots more) to help protect your applications and infrastructure. Sito Ruíz-Bravo put together a post on how to install the stack on Amazon EKS, [Deploying Wazuh on Kubernetes using Amazon EKS](https://wazuh.com/blog/deploying-wazuh-on-kubernetes-using-aws-eks/).

Thank you Sito Ruíz-Bravo!


### AWS Open Source projects and quick updates

**Amazon EKS now support 1.16**

A very quick post on the announcement this week that [Amazon EKS now supports 1.16](https://aws.amazon.com/about-aws/whats-new/2020/04/amazon-eks-now-supports-kubernetes-version-1-16/).


**AWS AppSync enables support for generic WebSockets clients with GraphQL real-time subscriptions**

AWS AppSync is a managed GraphQL service that simplifies application development by letting you create a flexible API to securely access, manipulate, and combine data from one or more data sources. AppSync allows to easily make any of its supported data sources real-time, with connection management, scaling, fan-out and data broadcasting handled automatically between the service and the clients, enabling developers to focus on the business differentiators for their real-time applications instead of WebSockets operations and infrastructure management.

Today we’re publishing our real-time WebSockets protocol so developers have a choice to use their favourite WebSockets client in any language to connect, register and receive GraphQL real-time subscriptions from their AppSync APIs, in addition to the optimised clients and SDKs readily available and provided by AppSync and Amplify. Dive deep by [reading this post by Steve Johnson](https://aws.amazon.com/blogs/mobile/appsync-websockets-python/),  which will walk you through the creation of an AppSync subscription client (subscription_client.py) using the new WebSocket protocol.

**Amplify**

The Amplify team posted a new resource to help you get started with Amplify. Well worth the time if you are looking for a curated set of content to help you on your Amplify journey - check out the content at [https://amplify.aws/community/resources](https://amplify.aws/community/resources)

**.NET Core 3.1 and Amplify**

Following on from that, another Amplify related post ([Introducing .NET Core support for AWS Amplify Backend Functions](https://aws.amazon.com/blogs/developer/introducing-net-core-support-for-aws-amplify-backend-functions/))but this time from Andy Hopper at AWS.  This post shows you how to wire up your Amplify applications to backed functions written in .NET Core, and will walk you through the process for creating a REST API backend written in C# and deployed to your AWS environment by Amplify.

Thank you Andy!

**.NET Core 3.1 on AWS Lambda**

Listening to customers and using the feedback to improve services and open source projects is one of the key tenets we have at Amazon - see how this looks in action with this post, [One month update to .NET Core 3.1 Lambda](https://aws.amazon.com/blogs/developer/one-month-update-to-net-core-3-1-lambda/). In this post, Norm Johanson talks about using IHostBuilder for ASP.NET, a new JSON serialisation library Amazon.Lambda.Serialization.SystemTextJson, which is based on .NET Core's new System.Text.Json library, using Amazon API Gateway's HTTP APIs and more. This post dives deep into those areas and is something that you .NET developers will appreciate.

Thank you Norm!

**Lambda Power-tools - python**

If you are into Serverless and use Python with your AWS Lambdas, then you need to be aware of [AWS Lambda Powertools](https://github.com/awslabs/aws-lambda-powertools/blob/develop/python/README.md). This project that has been put together by colleague and all round Serverless good guy Heitor Lessa (@heitor_lessa) is a suite of utilities for AWS Lambda Functions that makes tracing with AWS X-Ray, structured logging and creating custom metrics asynchronously easier. Sounds pretty useful right.

Keep watching this project or even better, follow Heitor on social media as he regular posts when he find cool new open source projects or when he updates this one. Thank you Heitor!

**Amazon Connect**

Nice project for those using Amazon Connect, our cloud based contact centre service (if you were not aware of it, check it out as it is so easy to get your own call centre setup in minutes). Randall Hunt provides some sample code across a number of different languages to get you started. So if you want to know how to do outbound dialling or do a holiday check in your flows, then you are going to find these useful. Check out the [Amazon Connect snippets here](https://github.com/amazon-connect/amazon-connect-snippets).

If you have your own you want to share, why not contribute? Details of how to do that are found on that page too.

Thank you Randall! 


**AWS DeepLens and the Smart Garage**

I have not posted about the AWS DeepLens for a while, so was glad when I came across this project after reading a post by Amit Mukherjee and Georges Leschener on [Building a smart garage door opener with AWS DeepLens and Amazon Rekognition](https://aws.amazon.com/blogs/machine-learning/building-a-smart-garage-door-opener-with-aws-deeplens-and-amazon-rekognition/). This walkthrough and source code will help you start your own automation project, so let me know if you use this project in your own garage automation - would love to see some pictures.

![Architecture diagram for Smart Garage](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2020/04/29/building-smart-garage-16.gif)

You will find the code to this project as well as detailed installation and configuration guides on the[ GitHub repo at AWS-Samples](https://github.com/aws-samples/aws-deeplens-smart-garage)


**Live Kernel patching on Amazon Linux 2**

Amazon Web Services (AWS) announced Kernel Live Patching for Amazon Linux 2, enabling customers to patch security vulnerabilities and bugs in the Linux kernel without reboots and disruptions to running applications. As a result, Amazon Linux 2 customers benefit from improved service availability and better security posture, while keeping their infrastructure secure and up-to-date with ease. This feature is offered to Amazon Linux 2 users at no cost. 

For more details, [read the announcement, Kernel Live patching is now available in preview for Amazon Linux 2](https://aws.amazon.com/about-aws/whats-new/2020/04/kernel-live-patching-now-available-in-preview-for-amazon-linux-2/)


---

### Do you use AWS and love open source? 

Do you have some content you want to share with a broader audience? We are always looking for guest content for the AWS Open blog. Please get in touch (via comments below) and I would love to speak with you about what you are doing in open source. We are always looking for interesting new content.

### We are hiring

We are hiring, so if you love open source, then why not check out the current openings. We would love to hear from you and if you want to chat and ask me anything, connect to me via LinkedIn or Twitter and always happy to talk.

[Open Source jobs at Amazon and AWS](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) - scroll to bottom, on left.

### Stay in touch with open source at AWS

I hope this summary has been useful. I have looked for all the session videos that have been uploaded to date, but if I have missed anything, please get in touch and I will update this summary. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on @AWSOpen.
