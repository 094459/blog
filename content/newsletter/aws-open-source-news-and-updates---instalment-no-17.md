---
title: 'AWS open source news and updates - Instalment No. 17'
date: '2020-04-27'
tags : [ oss-newsletter ]
---
## April 27th - Instalment #17

Episode 17, and as we leave April and head into May, we have a bumper edition with some very interesting new open source projects that AWS launched this week, TorchServe and Amazon Keyspaces as well as the usual round up of interesting projects, blog posts and other essential reading materials to keep you up to speed with the world of AWS and open source.

### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created.

So thank you to Romain Decker (@woueb), Nader Dabit (@dabit3), Ben Ellerby, Nimrod Kor and Bridgecrew (@KorNimrod, @bridgecrewio), Vigya Sharma, Julien Simon, Shashank Prasanna, Jon Handler, Mike Stefaniak, Jiaxin Shanthen,  Viji Sarathy, Francis Ginther, Kai Herings, Matt Asay, the folks at Strudel and Gregor Hohpe.


### Latest from open source projects


**Migrate from Wordpress to Hugo**

If you are currently hosting sites on Wordpress and perhaps looking at your options, then you might find this post and walkthrough interesting from Romain Decker. Hugo is a very popular open source static site generator, and Romain talks about how he approached moving from Wordpress to using Hugo in his post, [Wordpress to Hugo migration - hosting](https://cloudmaniac.net/wordpress-to-hugo-migration-2-hosting/).

![wordpress to hugo architecture](https://cloudmaniac.net/uploads/2020/04/aws-static-website-s3-cloudfront-lambda-workflow-terraform-github.png)

Stay tuned for the third post where he will outline the migration from Wordpress to Hugo. Thanks for putting this together Romain.

**JAMstack CMS**

Have you heard about [JAMstack](https://jamstack.org/)? If not, take time to read that link but TL;RL JAMstack is where you take "J"avascript code, us "A"PI's and use "M"arkup. The thing that they all have in common is that they don’t depend on a web server.

My colleague Nader Dabit put together this [JAMstack CMS](https://github.com/jamstack-cms/jamstack-cms/blob/master/README.md) project for your enjoyment. It is an end to end serverless blogging & CMS system,  built with GraphQL, Gatsby & AWS Amplify. 


**Serverless open source tools**

Post from Ben Ellerby that highlights a number of open source tools to improve the developer experience for serverless developers and when building serverless solutions. I have to say that a couple of these were new to me, so I suspect you will find something new in this post too.

From tool to help you with your IAM permissions, a tool to help you ensure that you keep your AWS Lambda functions clean and focused on just the business logic you need to a couple of general purpose tools and libraries that all serverless developers should be aware of, check out [5 Open Source Tools to Improve Your Serverless Development Experience](https://medium.com/serverless-transformation/5-open-source-tools-to-improve-your-serverless-development-experience-8f2eaa89a2b5).

**Security**

I seem to post lots of really cool open source security related projects, and this week is no exception.

**AirIAM**

If you are using Terraform, then this project will allow you to take your existing IAM usage patterns and migrates these to produce least privileged code that you can deploy in your Terraform deployments.

![AirIAM diagram](https://github.com/bridgecrewio/AirIAM/raw/master/images/ComponentDiagram.png)

Check out the [AirIAM GitHub repository](https://github.com/bridgecrewio/AirIAM). They provide great documentation, tutorials and examples to get you started.

Why AirIAM? From the tweet that I read that made me aware of this project

> The first name was - "AWS IAM Security engineering-as a service-as a code as-an open source".  But AirIAM was a bit more catchy.

Thanks Nimrod Kor and Bridgecrew.


### AWS Open Source projects

**PyTorch model serving with TorchServe**


One of the big announcements this week was the launch of TorchServe - an open-source model serving library for PyTorch. The official [Introducing Torchserve post](https://aws.amazon.com/about-aws/whats-new/2020/04/introducing-torchserve/) is where you should start.

A more detailed post from Julien Simon, [Torchserve - An open source model server for PyTorch](https://aws.amazon.com/blogs/aws/announcing-torchserve-an-open-source-model-server-for-pytorch/), walks you through installing this and getting started as well as covering some customers who are already enjoying the benefits of TorchServe.

Shashank Prasanna did another technical walk though to get you started on how you can [Deploy your PyTorch models at scale using TorchServe](https://aws.amazon.com/blogs/machine-learning/deploying-pytorch-models-for-inference-at-scale-using-torchserve/).

![TorchServe diagram](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2020/04/20/deploying-pytorch-torchserve-1-2.gif)

If that was not enough, Mike Stefaniak and Jiaxin Shanthen posted on a collaboration between the Kubernetes team at AWS and the PyTorch team at Facebook, helping customers to understand how you can [Build fault tolerant, distributed machine learning training with a new project, TorchElastic Controller for Kubernetes](https://aws.amazon.com/blogs/containers/fault-tolerant-distributed-machine-learning-training-with-the-torchelastic-controller-for-kubernetes/).

**General availability of managed Cassandra - Amazon Keyspaces**

When it was announced at reInvent 2019, Amazon Managed Apache Cassandra Service (MCS) generated a lot of interest and [this week](https://twitter.com/shawnbice/status/1253463491345670144), together with a brand new name, [we launched the general availability of Amazon Keyspaces (for Apache Cassandra)](https://aws.amazon.com/blogs/aws/new-amazon-keyspaces-for-apache-cassandra-is-now-generally-available/).

Amazon Keyspaces is built on Apache Cassandra, and you can use it as a fully managed, serverless database. Your applications can read and write data from Amazon Keyspaces using your existing Cassandra Query Language (CQL) code, with little or no changes. For each table, you can select the best configuration depending on your use case:

* With on-demand, you pay based on the actual reads and writes you perform. This is the best option for unpredictable workloads.
* With provisioned capacity, you can reduce your costs for predictable workloads by configuring capacity settings up front. You can also further optimise costs by enable auto scaling, which updates your provisioned capacity settings automatically as your traffic changes throughout the day.

Check out the [launch post from Danilo](https://aws.amazon.com/blogs/aws/new-amazon-keyspaces-for-apache-cassandra-is-now-generally-available/) where he walks you through a quick example to get you started.

**related**

You might also find this project, [AWS Sigv4 Auth Cassandra java driver example](https://github.com/aws-samples/aws-sigv4-auth-cassandra-java-driver-examples), when creating credentials to access Amazon Keyspaces programatically. You can find more details in the docs [here](https://docs.aws.amazon.com/keyspaces/latest/devguide/programmatic.credentials.html#signaturev4) and [here](https://docs.aws.amazon.com/keyspaces/latest/devguide/programmatic.drivers.html#using_java_driver).


**Open Distro for Elasticsearch**

This week we had a super deep dive from Vigya Sharma and Jon Handler, in the published [blog post on the Open Distro for Elasticsearch weight function](https://opendistro.github.io/for-elasticsearch/blog/odfe-updates/2020/04/The-Elasticsearch-Weight-Function/).

From the post:

> Distributed systems scale by coordinating and distributing their workloads horizontally, across several machines. In Elasticsearch, this is done by partitioning indexes into shards and distributing them across data nodes in the cluster.
> 
> In this post, I will dive into the default weight function implementation to weigh the pros and cons of the default algorithm and look at some of the considerations in making shard allocation more responsive to transient signals. You will gain a deeper understanding of shard placement in your clusters, why Elasticsearch chose a particular node for a shard, and how future placement decisions will be evaluated. Knowing this will help you design for future workloads and scaling requirements.

### Other quick updates from AWS 

**AWS CDK Public Roadmap**

Big news over in CDK Land with the [announcement of the AWS CDK public roadmap](https://aws.amazon.com/blogs/developer/introducing-the-aws-cdk-public-roadmap/)

![CDK roadmap](https://d2908q01vomqb2.cloudfront.net/0716d9708d321ffb6a00818614779e779925365c/2020/04/10/CDKRoadmap.png).

One thing that is worth knowing that you may not know, is that there are a number of related open source projects. You may know about aws-cdk repo (the CDK core framework) and the AWS Construct Library. But there’s also the aws/jsii repo, the technology that enables the CDK to deliver polyglot libraries from a single codebase. And last but not least, the aws/aws-cdk-rfcs repo where we conduct our feature design in the open, and request comments from customers like you.

Never a better time to check it out.

**Amazon SageMaker NEO**

Amazon SageMaker Neo enables developers to train machine learning models once and run them anywhere in the cloud and at the edge. Amazon SageMaker Neo optimises models to run up to twice as fast, with less than a tenth of the memory footprint, with no loss in accuracy.

DLR is a compact, common runtime for deep learning models and decision tree models compiled by AWS SageMaker Neo, TVM, or Treelite. DLR uses the TVM runtime, Treelite runtime, NVIDIA TensorRT™, and can include other hardware-specific runtimes. DLR provides unified Python/C++ APIs for loading and running compiled models on various devices. DLR currently supports platforms from Intel, NVIDIA, and ARM, with support for Xilinx, Cadence, and Qualcomm coming soon.

[v1.1.0 of Neo AI DLR was released](https://github.com/neo-ai/neo-ai-dlr), so if you are working with machine learning and IoT or edge devices, check out this project out.


**Managing secrets in your Kubernetes clusters**

Check out the blog post, [Managing secrets deployment in Kubernetes using sealed secrets.](https://aws.amazon.com/blogs/opensource/managing-secrets-deployment-in-kubernetes-using-sealed-secrets/) where Viji Sarathy walks through using tools from the Sealed Secrets open source project to manage the deployment of sensitive information to their Kubernetes clusters, and to store them securely in a Git repository and to integrate them into their continuous delivery pipelines.

Sealed Secrets open source project addresses this challenge by providing a mechanism to encrypt a Secret object so that it is safe to store in a private or public repository. These encrypted Secrets can also be deployed to a Kubernetes cluster using normal workflows with tools such as kubectl.

![managing secrets](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2020/04/09/Screen-Shot-2020-04-09-at-6.54.55-PM.png)


### Time machine - the retro projects that you might not know about


One of the cool things about my job is that in speaking with developers and architects, I often unearth open source projects that I was not aware of but might be super interesting for people to know about.

This week whilst chatting with folk about build hybrid applications and how open source software plays in this space, I found an AWS project called [AWS Service Broker](https://github.com/awslabs/aws-servicebroker/).

The AWS Service Broker allows native AWS services to be exposed directly through application platforms that implement the Open Service Broker API, and provides simple integration of AWS Services directly within the application platform.

![AWS Service Broker](https://github.com/awslabs/aws-servicebroker/raw/master/docs/images/architecture.png)

I would love to hear from anyone who is using this project to integrate AWS services from within their own platform, either using one of the providers listed or their own customer service platforms.

### Roundup of the latest open source blog posts

I have been running Ubuntu at home (and pretty much everywhere else) for many years, and this is still my day to day distro of choice. This week in a [blog post called, Introducing the Ubuntu AWS rolling kernel](https://ubuntu.com/blog/introducing-the-ubuntu-aws-rolling-kernel-2), Francis Ginther talked about Ubuntu 18.04 LTS moving to a rolling kernel model. What is a rolling kernel model? Well, I am glad you asked, as the blog post covers this:

>A rolling kernel model transitions the default linux-aws kernel from one base version to the next as part of its regular patching cycle

If you are using Ubuntu on AWS, make sure you read the post which provides further details and how you can prepare for this change.

**AWS RoboMaker**

In an excellent blog post, [Kai Herings writes about how you apply and automate the process of regression testing with physical products using computer vision  and robotics](https://blog.codecentric.de/en/2020/04/thermomix-physical-regression-testing/).

What I love about this post is that it shows how increasingly the mechanisms used in software development are increasingly cross the physical boundary with technologies such as computer vision, robotics and the supporting open source software such as ROS. It is great that customers are using AWS RobotMaker to get started with ROS, so thanks for sharing this post Kai.

![testing physical products](https://blog.codecentric.de/files/2020/03/Bildschirmfoto-2020-03-27-um-13.43.20-1536x756.png) 







### Startups love open source

Startups love open source software, and in this short video, meet one startup, Alluxio, who are powering innovation with an open sourced data orchestration product. 

[You can watch the video here.](https://www.youtube.com/watch?v=3RzTktCZMNE)

**Securing open source**

In this guest post by by [Marten Mickos, CEO of HackerOne, talks about innovation by community](https://aws.amazon.com/blogs/startups/hackerone-ceo-on-innovation-by-community/
). It will only take you 5 minutes to read, but could be the best use of five minutes today.  


### Online events for your diary

I posted this last week, so just a reminder to take a look and put this event in your diary.

**May 12th, Tuesday**

https://opensource101.com/events/at-home/

Let me know if you have any events you want me to share, please drop me a mail or add it to the comments - I watch these so will be sure to add it in the following roundup.


### Some posts to make your grey cells work

So, these posts are outside the normal selection for this blog, but I wanted to share them as I found them very thought provoking and useful if you are working day to day with open source.

Now this first post is not a new one, but came up again on the social media recycling round that tosses up the good posts from time to time. A detailed assessment of open source in the context of lock in, plenty to think about. Read on in D[on't get locked up into avoiding lock-in](https://martinfowler.com/articles/oss-lockin.html).

Following that is an empirical study of donations in open source. This research paper, which is well worth reading, opens up with "we also find no clear evidence that donations influence the activity level of a project.." (my edit) so, no spoilers and check out the paper over [here](https://cmustrudel.github.io/papers/overney20donations.pdf). Brought to you by [Strudel](https://cmustrudel.github.io/), make sure you check out their other projects and research papers for a data driven assessment of all things around distributed software development.

Finally, Matt Asay has been on fire this month, with plenty of activity but I love this post on the topic of competing in the open, with a detailed look at Instaclustr, a company that offers a managed Open Distro for Elasticsearch service, competing with Amazon's Elasticsearch service. Read the post, [The instraclustr sign of open success](https://aws.amazon.com/blogs/opensource/the-instaclustr-sign-of-open-source-success/).


---

### Do you use AWS and love open source? 

Do you have some content you want to share with a broader audience? We are always looking for guest content for the AWS Open blog. Please get in touch (via comments below) and I would love to speak with you about what you are doing in open source. We are always looking for interesting new content.

### We are hiring

We are hiring, so if you love open source, then why not check out the current openings. We would love to hear from you and if you want to chat and ask me anything, connect to me via LinkedIn or Twitter and always happy to talk.

[Open Source jobs at Amazon and AWS](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) - scroll to bottom, on left.

### Stay in touch with open source at AWS

I hope this summary has been useful. I have looked for all the session videos that have been uploaded to date, but if I have missed anything, please get in touch and I will update this summary. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on @AWSOpen.
