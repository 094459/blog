---
title: 'AWS open source news and updates - No. 20'
date: '2020-05-18'
tags : [ oss-newsletter ]
---
## May 18th - Instalment #20

Episode 20, another packed episode with plenty to check out, and some really great announcements and projects to share. With that, let's get started with one of our big announcements last week.

**cdk8s**

The [big news this week though](https://aws.amazon.com/blogs/containers/introducing-cdk-for-kubernetes/) was the launch of [CDK for Kubernetes](https://cdk8s.io), an open-source software development framework for defining Kubernetes applications and reusable abstractions using familiar programming languages and rich object-oriented APIs. From the launch blog announcement:

> At AWS, we’ve seen customers rapidly adopt Kubernetes to deploy applications globally, train machine learning models at scale, and standardise how they deliver innovation across data centres and the cloud. Using Kubernetes, customers are building automated tooling to replace manual processes, implementing operational pipelines for every piece of their infrastructure, and empowering development teams with the ability to get granular control over how their applications run.

> Traditionally, Kubernetes applications are defined with human-readable, static YAML data files which developers write and maintain. Building new applications requires writing a good amount of boilerplate config, copying code from other projects, and applying manual tweaks and customisations. As applications evolve and teams grow, these YAML files become harder to manage. Sharing best practices or making updates involves manual changes and complex migrations.
> 
> YAML is an excellent format for describing the desired state of your cluster, but it is does not have primitives for expressing logic and reusable abstractions. There are multiple tools in the Kubernetes ecosystem (kustomize, jsonnet, jkcfg, kubecfg, kubegen, and Pulumi to name a few) which attempt to address these gaps in various ways.

> We realised this was exactly the same problem our customers had faced when defining their applications through CloudFormation templates, a problem solved by the AWS Cloud Development Kit (AWS CDK), and that we could apply the same design concepts from the AWS CDK to help all Kubernetes users.

cdk8s generates pure Kubernetes YAML - you can use cdk8s to define applications for any Kubernetes cluster running anywhere. cdk8s is based on the design concepts and technologies behind the AWS Cloud Development Kit, and can interoperate with AWS CDK constructs to define cloud-native applications that include both Kubernetes resources and other CDK constructs as first class citizens.

If you want to find out more, then why not check out the [CNCF webinar, End Yaml engineering with cdks](https://www.cncf.io/webinars/end-yaml-engineering-with-cdk8s/) or read the launch blog in full, [Introducing CDK for Kubernetes](https://aws.amazon.com/blogs/containers/introducing-cdk-for-kubernetes/).

**AWS Graviton2 and open source**

This week saw the general availability of the first [sixth generation AWS EC2 instance, the EC2 M6g](https://aws.amazon.com/blogs/aws/new-m6g-ec2-instances-powered-by-arm-based-aws-graviton2/), The 'g' stands for Graviton2, and is AWS' next generation ARM processor developed by Annpurna Labs.

One of the great things about this new instance type is that it allows you to run software blazingly fast and at lower cost. We are beginning to see a number of posts on this, but you can expect to see more. One of the interesting things you can expect to so though, is open source projects begin to compile their source code against ARM architectures.

To help open source projects, there is a [getting started guide](https://github.com/aws/aws-graviton-gettting-started) which provides a great place to begin. There are a number of blog posts ([PyTorch and openCV](https://discuss.pynq.io/t/a-no-cross-compile-of-pytorch-and-opencv-using-aws-a1-instances/717)) showing how some projects have compiled against the original A1 instance types (also ARM based AWS Graviton processor) that might also help you if you are looking to compile and optimise your open source projects on this instance types. 

I will share more of these in the future as I think a lot of customers are going to begin looking more closely at how to leverage these ARM based instances to run their workloads, so if you are a project maintainer, something to think about.


### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created.

So thank you to MinJae Kwon, Cyrus Wong, Andreas Wittig & Michael Wittig, Servais Kimelyne, Carl Meadows, Imaya Kumar Jagannathan, Justin Gu, Marc Chéné, and Michael Hausenblas

### Latest from open source projects

**Amazon Chime**

If you are looking at Amazon Chime and exploring how to integrate this into your workflows, this project might be of interest.

This repository, [Amazon Chime Meeting Broadcast Demo](https://github.com/aws-samples/amazon-chime-meeting-broadcast-demo), contains a Docker container that, when started, will join an Amazon Chime meeting by PIN and broadcast the meeting's audio and video in high definition (1080p at 30fps) to an RTMP endpoint you specify. The broadcast participant joins the meeting in the muted state. The meeting PIN must be unlocked in order for the broadcast participant to join the meeting.
 
**AWS Neuron SDK updates**

AWS Neuron is a software development kit (SDK) enabling high-performance deep learning inference using AWS Inferentia custom designed machine learning chips. With Neuron, you can develop, profile, and deploy high-performance inference predictions on top of Inferentia based EC2 Inf1 instances.

This week, [May 2020 release](https://github.com/aws/aws-neuron-sdk/blob/master/release-notes/README.md), provides additional throughput improvements to running inference on a variety of models; for example BERTlarge throughput has improved by an additional 35% compared to the previous release and with peak thoughput of 360 seq/second on inf1.xlarge (more details here).

In addition to the performance boost, this release adds PyTorch, and MXNet framework support for BERT models, as well as expands container support in preparation to an upcoming EKS launch.

You might also be interested in checking out the [roadmap for this project which can be found here](https://github.com/aws/aws-neuron-sdk/projects/2).


**Machine Learning at Amazon**

If you are looking for material to go deep on deep learning, then this book from a number of Amazon data scientists, [Dive into Deep Learning](https://d2l.ai/), may be just what you are looking for. Augmented through the collaborative power of open source, this is an attempt to make deep learning approachable, teaching the concepts, the context, and the code. Since the initial launch, the repository now has over 100 contributors, and lots of sample notebooks.

You can find the book at this link [https://d2l.ai/](https://d2l.ai/) , and the corresponding code you will need at the [GitHub repository](https://github.com/d2l-ai/d2l-en).


**Serverless fullstack**

This [project from Wizeline, Serverless fullstack](https://github.com/wizeline/serverless-fullstack) provides a structure for you to build out your full stack serverless applications and has everything you need to get started. The project is still in active development and they are iterating fast, so by the time you read this I am sure they have released some new features.


**Visualisation of your AWS Cloud9 environment**

Nice post and project from AWS Machine Learning hero [Cyrus Wong, on how to visualise your AWS Cloud9 environment](https://www.linkedin.com/pulse/how-visualize-your-aws-account-cloud9-wong-chun-yin-cyrus-%E9%BB%83%E4%BF%8A%E5%BD%A5-). Read his write up on LinkedIn and then check out the code on his [GitHub repository](https://github.com/wongcyrus/aws-account-cloud9-visualizer). You will have it up and running in no time at all. I put a short video of me running this which you can [view here](https://www.youtube.com/watch?v=XCHmxfyYhLA).
 
 ![Demo of project](https://media-exp1.licdn.com/dms/image/C5612AQFRCsPB87U5lQ/article-cover_image-shrink_720_1280/0?e=1595462400&v=beta&t=F3KhLwjWv9s5KCe9HORbd3Rxp4LamFuIxfLuXywrFgc)
 
**Note!** I ran this first on Firefox and it didn't work - I got an "OOPS VFS connection does not exist". I turns out this is a limitation of Firefox, and changing to Chrome resolved my problems.

**Python Diagrams**

Continuing on an artistic theme, this cool project from MinJae Kwon called diagrams surfaced this week (the project is not new, but it was new to me). A programatic way of generating diagrams and anyone familiar with graphviz should be at home here. With just a few lines of code you will be creating beautiful technical diagrams.

You can find the [project repository on GitHub](https://github.com/mingrammer/diagrams) here and there is an [excellent documentation site here, with some great examples](https://diagrams.mingrammer.com/docs/getting-started/examples).

Using the following example code:

```
from diagrams import Diagram
from diagrams.aws.compute import EC2
from diagrams.aws.database import RDS
from diagrams.aws.network import ELB

with Diagram("Grouped Workers", show=False, direction="TB"):
    ELB("lb") >> [EC2("worker1"),
                  EC2("worker2"),
                  EC2("worker3"),
                  EC2("worker4"),
                  EC2("worker5")] >> RDS("events")
```

Renders the following diagram.

![Architecture diagram.](https://diagrams.mingrammer.com/img/grouped_workers_diagram.png)

Thank you MinJae Kwon!

**Amazon SageMaker**

The Amazon SageMaker Python SDK v2.0.0 release plans are something you should take a look at if you are currently using this (latest version v1.5.4).

You can find the [v2.0 release plan on the GitHub repo](https://github.com/aws/sagemaker-python-sdk/issues/1459) together with the expected timeline and important changes that are planned to be included. This is your chance to provide input into the roadmap as well as discuss some potential breaking changes they are considering.

**Open source templates for AWS CloudFormation**

From the lovely folk at Cloudonaut and Andreas Wittig & Michael Wittig, comes this collection of Cloudformation templates that you can use to start off with. These are production ready templates, have been peer reviewed and they have run them through automated testing. These templates cover everything from setting up networking, EC2 instances, containers and more.

![Example architecture diagram](https://templates.cloudonaut.io/en/stable/img/vpc-2azs.png)

These templates come with detailed architecture descriptions and links to the yaml files. I am happy that this is one of the projects that is supported by the AWS Promotional credits for open source project, so if you have an open source project that might benefit why not apply too?

### Blog posts you should check out

**Bottlerocket**

If you have not already check this out, then this should go straight to the top of your reading/listening pile. Hear from [Deepak Singh and Peder Ulander on AWS' Bottlerocket and the age of Linux cloud distributions](https://thenewstack.io/aws-bottlerocket-and-the-age-of-the-linux-cloud-distributions/).

Amazon Web Services introduced [Bottlerocket](https://aws.amazon.com/bottlerocket/), a Linux distribution built specifically for cloud use (and tailored even more for EKS). 

In this podcast you will hear more about Bottlerocket, the motivation, some inspirations we drew upon and details on how we built this based on what we had learnt but also what our customers were asking us for. Building Bottlerocket, the AWS team “learned a lot about the operational model, and especially how our customers were managing their fleets. So that played a lot of insight into what Bottlerocket was doing,”

Well worth spending half an hour of your time.

**Prometheus**

Prometheus is a popular open source monitoring tool that graduated as a Cloud Native Compute Foundation (CNCF) project, with a large and active community of practitioners. In No.19 I shared beta support for Prometheus metrics in CloudWatch Container Insights, and following up on that is this [blog post, Using Prometheus metrics in Amazon CloudWatch](https://aws.amazon.com/blogs/containers/using-prometheus-metrics-in-amazon-cloudwatch/), how to use the CloudWatch Container Insights Prometheus metrics in two setups: we start with a simple example of scraping NGINX and then have a look at how to use custom metrics by instrumenting a ASP.NET Core app.

![Prometheu metric dashboard](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2020/05/07/custom_metrics_dashboard_2-1-1024x563.png)



**Deploying Amazon EKS using Terraform**

In this post, [Deploy your Amazon EKS cluster with Terraform, Servais Kimelyne](https://www.padok.fr/en/blog/aws-eks-cluster-terraform) walks you through setting up and deploying an EKS cluster. 

After reading this post, you should be up and running in minutes. Thank you Servais! 


**.NET Core case study**

Great case study from Pavel Vasilyev, on how an AWS Premier Consulting Partner [Clearscale helped customer SF Match modernise legacy .NET applications by migrating them to AWS and .NET Core](https://aws.amazon.com/blogs/modernizing-with-aws/how-clearscale-helped-sf-match-modernize-its-microsoft-application-to-optimize-performance/).

![Diagram of .NET Core](https://d2908q01vomqb2.cloudfront.net/8effee409c625e1a2d8f5033631840e6ce1dcb64/2020/05/13/sfmatch1.png)

The net result of this is SF Match now has a faster, easier, and transparent process for application building and deployment. The infrastructure is more efficient, reliable, and cost effective. Much of the previous maintenance burden has been eliminated, freeing up staff for other projects.

If you have .NET workloads and are looking at options for modernisation, then this is essential reading.


**Open Distro for Elasticsearch**

A couple of updates this week.

First, Carl Meadows announced Open Distro for Elasticsearch 1.7. You can [see the release notes here](https://github.com/opendistro-for-elasticsearch/opendistro-build/blob/master/release-notes/release-notes-odfe-1.7.0.md), but this is a packed release with the anomaly detection plugin moving from preview to GA status, new functionality in the SQL plugin including a new Kibana UI and command line autocomplete, a new SQL ODBC driver and more.

Following from that, Satya Vajrapu wrote a blog post on the Index State Management (ISM) plugin for Open Distro for Elasticsearch, a plugin to help define custom management policies to automate routine tasks and apply them to indices and index patterns. The ISM plugin provides an automated solution for repetitive index management tasks such as set up and management of external custom processes to run your index operations.

In this [blog post, Index State Management in Open Distro for Elasticsearch, Satya ](https://opendistro.github.io/for-elasticsearch/blog/odfe-updates/2020/05/Index-State-Management-in-Open-Distro-for-Elasticsearch/) walks you through using this plugin and provides examples of how to use it to maintain multiple indices for a diverse data workloads and set up an automated solution to periodically perform certain housekeeping index management functions.
 

### Quick updates

**Machine Learning**

A few of updates this week.

**PyTorch and Tensorflow deep learning containers**

The AWS deep learning containers updated the version of [PyTorch to 1.5.0](https://aws.amazon.com/about-aws/whats-new/2020/05/aws-deep-learning-containers-for-pytorch-1-5-0/) and [Tensorflow 1.15.2 with Python 3.7](https://aws.amazon.com/about-aws/whats-new/2020/05/updates-to-aws-deep-learning-containers-for-tensorflow-1-15-2-with-python-3-7/) support.

The AWS Deep Learning Containers for PyTorch include containers for training on CPU and GPU, optimised for performance and scale on AWS. These Docker images have been tested with Amazon SageMaker, EC2, ECS, and EKS, and provide stable versions of NVIDIA CUDA, cuDNN, Intel MKL, and other required software components to provide a seamless user experience for deep learning workloads.

The TensorFlow 1.15.2 python3.7 training containers now also include SageMaker Debugger, which allow data scientists to save and inspect the model tensors during training jobs.

**AWS Deep Learning Containers with Amazon Elastic Inference**

The AWS Deep Learning Containers for Elastic Inference with the framework versions PyTorch 1.3.1, TensorFlow 1.15.0, and TensorFlow 2.0.0. The PyTorch 1.3.1 upgrade includes the newly added SageMaker Inference and SageMaker PyTorch Inference. The TensorFlow 1.15.0 and TensorFlow 2.0.0 upgrades include the latest versions of TensorFlow Model Server for use with Elastic Inference.

The AWS Deep Learning Containers with Amazon Elastic Inference (EI) with PyTorch and TensorFlow allow you to run inference calls on PyTorch 1.3.1, TensorFlow 1.15.0, and TensorFlow 2.0.0 on Elastic Inference Accelerators. Amazon EI allows you to attach low-cost GPU-powered acceleration to Amazon EC2 and Amazon SageMaker instances and Amazon ECS tasks to reduce the cost of running deep learning inference by up to 75%. 

**Amazon Chime**

If you are using Amazon Chime then this week we [announced support for Ubuntu in the Amazon Chime SDK for Javascript](https://aws.amazon.com/about-aws/whats-new/2020/05/amazon-chime-sdk-for-javascript-supported-on-ubuntu/).

**Debian and Oracle Linux**

Patch Manager, a capability of AWS Systems Manager, [now](https://aws.amazon.com/about-aws/whats-new/2020/05/aws-systems-manager-support-patching-debian-oracle-linux-instances/) allows you to deploy patches automatically to instances running Debian 8 (Jessie), Debian 9 (Stretch), and Oracle Linux 7.6, giving you more patching options for your mixed Linux environments.  Patch Manager can also automatically patch Linux instances running Red Hat Enterprise Linux (RHEL), Ubuntu Server, Amazon Linux, Amazon Linux 2, CentOS, and SUSE Linux Enterprise Server (SLES). 

### For your diary

**Firecracker webinar next week - have you signed up yet?** 
 
On May 28th, Amazon Web Services senior principal engineer Marc Brooker will be broadcasting a live discussion about Firecracker. Firecracker is an open source virtualisation technology that's purpose-built for creating and managing secure, multi-tenant container and function-based services.

I've registered, so make sure you reserve your spot for this webinar next week. Sign up [using the registration link](https://www.amazon.science/videos-webinars/firecracker-awss-open-source-minimalist-approach-to-serverless-computing). 

**Percona 24hour open source database conference**

Tomorrow, 19th May sees Percona running a 24 hour open source database conference. Lots of great sessions, with Matt Asay's Moving Beyond Zero Sum Approaches to Open Source a highlight.

Check out and sign up for free here > [https://www.percona.com/live/conferences](https://www.percona.com/live/conferences) and remember to bring plenty of coffee!


### Tweets of the Week

A [discussion of open source and business models](https://twitter.com/adamhjk/status/1260065968530714625) - make sure you follow the threads and have your say.

Recognition of contributions within your community is a critical part of running a successful open source project. Recognising individuals or teams is very powerful, as this [tweet shows](https://twitter.com/cloudkickoff/status/1261528314830712834?s=11)


### Deep dive on open source - The Ethics of unpaid labor and the OSS community

A departure from the usual, I spent the weekend reading this piece from [Ashe Dryden on The Ethics of unpaid labor and the OSS community](https://www.ashedryden.com/blog/the-ethics-of-unpaid-labor-and-the-oss-community).

I encourage you all to read it. Diversity in tech / open source is something I care about, and this post sheds some interesting perspectives on this that I had certainly never considered. The post if a few years old so it would be interesting to see new data points on whether any progress has been made, but certainly a lot of the issues raised and points made resonated with my own experience.

I would love to hear what you think. What are your thoughts on this piece?  

---

### Do you use AWS and love open source? 

Do you have some content you want to share with a broader audience? We are always looking for guest content for the AWS Open blog. Please get in touch (via comments below) and I would love to speak with you about what you are doing in open source. We are always looking for interesting new content.

### We are hiring

We are hiring, so if you love open source, then why not check out the current openings. We would love to hear from you and if you want to chat and ask me anything, connect to me via LinkedIn or Twitter and always happy to talk.

[Open Source jobs at Amazon and AWS](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) - scroll to bottom, on left.

### Stay in touch with open source at AWS

I hope this summary has been useful. I have looked for all the session videos that have been uploaded to date, but if I have missed anything, please get in touch and I will update this summary. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on @AWSOpen.