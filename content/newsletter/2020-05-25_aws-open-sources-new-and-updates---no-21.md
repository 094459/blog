---
title: 'AWS open sources new and updates - No. 21'
date: '2020-05-25'
tags : [ oss-newsletter ]
---
## May 25th - Instalment #21

Episode 21, another full edition. We have some significant announcements of new projects from Uber, a variety of different posts and code for those interested in containers, plenty of serverless goodness and as always, some great Amplify and AWS AppSync posts. We also have a couple of posts on how to get some open source projects you might be using up and running on AWS. Before you dive in, a couple of things you check out first.

**Contribute and win a prize**

Starting next week I am introducing a "Contribution of the week" prize. Please send me through interesting open source projects, and I will choose a winner and and announce them via the newsletter. I will be providing AWS Credits for the winning contributions, and be looking for submissions that are either directly or indirectly work with open source and AWS. These could be blog posts you have written, new open source projects you have created or new contributions or PRs to your or other projects. I want to hear from you so please get in touch via the comments below, Twitter or you can get me via email at ricsue@amazon.com

Looking forward for the contributions.

**ex_aws project looking for a new maintainer**

Now, listen up a call to arms. If you use or are looking to get more involved in an open source project, or perhaps you are interested or using Elixir and AWS. [ex_aws](https://github.com/ex-aws/ex_aws) is an open source project that provides a set of API's to access AWS services. Ben Wilson the current maintainer is currently looking for someone to hand this over to, so if this looks like the right opportunity for you, then why not get in touch via [the Elixir forum](https://elixirforum.com/t/maintainer-wanted-exaws/31731).


### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created.

So thank you to Henry Fuheng Wu, Raymond Won, Nick Cobb, Mingjie Lai, Matt Ranney, Simon Woldemichael, Josh Jiang, Bhawana Dehran, Nader Dabit, Joonas Laitio, Luis Colon, John Preston, Jan Giacomelli, Alex Casalboni, Brice Pelle, Thai Bui, Bin Fan, Cornell Anthony, Jonah Jones, Muhammad Mansoor, Subin Mathew and Vinod Pulkayath.

### Latest from open source projects

**Uber release Athenadriver**

Hot off the press this week is a new open source project from Uber that provides a database driver for Amazon Athena that supports Go’s built-in database/SQL framework.
You can find details of the launch post, [Introducing Athenadriver: an open source Amazon Athena database driver for Go](https://eng.uber.com/introducing-athenadriver/), and access t[he GitHub repository here](https://uber.github.io/athenadriver/). Excellent documentation, samples code and examples and documented known issues make this is an easy to get started with project.  

![Athenadriver logo](https://1fykyq3mdn5r21tpna3wkdyi-wpengine.netdna-ssl.com/wp-content/uploads/2020/05/image7-2.png)

(diagram from launch post - see link below)

Make sure you read the launch post that outlines what this driver does and why you would want to look at this. From the post:

>Athenadriver can greatly simplify Athena query code by encapsulating  query and access complexities and seamlessly handling various edge cases so engineers can safely replace hundreds of lines of Athena Go SDK code with less than ten lines of code for Athenadriver.

The team is looking for feedback, comments and contributions. They are considering open sourcing some other projects, so please make sure you show this some interest.

Thank you Henry Fuheng Wu, Raymond Won, Nick Cobb, Mingjie Lai, and Matt Ranney

**Kubernetes and Serverless Application Model (SAM)**

Many customers have the need to implement strong controls within their environments, and need to exclusively launch approved resources in their clusters, for example, pushing changes to a production environment that could risk installing an incompatible package or vulnerable dependency that crashes your services. Controlling resource deployments in your Kubernetes cluster can become a difficult challenge. 

In this detailed blog post, [Building serverless admission webhooks for Kubernetes with AWS SAM](https://aws.amazon.com/blogs/containers/building-serverless-admission-webhooks-for-kubernetes-with-aws-sam/), Simon Woldemichael and Josh Jiang walk you through how you might implement controls via custom admission webhooks for Kubernetes that allow you to define strict regulations to exclusively launch approved resources in our cluster.

![Solution architecture](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2020/05/15/webhook-aws-process.png)

Find the [source code for this solution here in the GitHub repository.](https://github.com/aws-samples/amazon-ecr-repository-compliance-webhook)

**ECS ComposeX**

In [Automating your ECS container architecture deployments with ECS ComposeX](https://aws.amazon.com/blogs/opensource/automating-your-ecs-container-architecture-deployments-with-ecs-composex/), John Preston walks us through is project that aims to implement for ECS and Docker Compose what SAM is to serverless for AWS Lambda.

I had a lot of fun writing this with John, so check this post out and take a look at how you might be able to use this project.


**Amplify and AWS Appsync**

Another fun project from Nader Dabit, [This or That](https://github.com/dabit3/this-or-that/blob/master/README.md). Anyone familiar with the early 2K simple voting apps will immediately recognise this format. This project will take you about 5 minutes to deploy, and with Nader providing the source code, I look forward to how folks are going to build on this. Please see the note below about security before you deploy. 

![Example poll](https://ricsuepublicresources.s3-eu-west-1.amazonaws.com/images/Screenshot+2020-05-25+at+11.31.32.png)


**Note!** Thanks to [Ross Williams](https://twitter.com/williamsross) for providing the following security advice when looking at this demo. See comments.


**Bagisto on AWS**

Bagisto is an open-source eCommerce platform, which is built on various open source technologies, such as PHP framework, laravel, Vue.js, MySQL, and [Bhawana Dehran has put together this detailed walkthrough](https://bagisto.com/en/how-to-install-bagisto-on-aws/) on how to get your own instance up and running on AWS.

![Bagisto image](https://bagisto.com/wp-content/uploads/2020/05/oie_4xjXLrrTUcCS.png)

Thank you Bhawana

**Ionic PWA using Amplify Predictions**

In this project by Michael Labieniec, you can combine Ionic using AWS Amplify and ML/AI services to do predictions on images. It is a simple deploy, so head over to the [GitHub repository](https://github.com/mlabieniec/IonicPredictions). Once thing I like about this demo is that it shows you how to store locally and keep in sync settings with the cloud using Amplify DataStore and AWS AppSync.

![Demo of app](https://github.com/mlabieniec/IonicPredictions/raw/master/demo.gif)

Thank you Michael.

**Flux7Labs - creating GitHub repositories from CloudFormation**

Ever wanted to create a GitHub repo directly from CloudFormation?  Check out this new resource provider from [Flux7 on the GitHub repository.](https://github.com/Flux7Labs/cfn-github-3rd-party-resource)
 
This update came via my colleague [Luis Colon on Twitter](https://twitter.com/luiscolon1/status/1262539721462300675?s=11). Make sure you follow him to keep up to date with AWS CloudFormation and more. https://github.com/Flux7Labs/cfn-github-3rd-party-resource

**Shutting down scheduler**

Nice project from [Joonas Laitio](https://twitter.com/jlaitio) that lets you put together a scheduler to shut down and start up AWS infrastructure on a recurring schedule to help you mitigate running costs on off hours. This project currently supports ECS, RDS clusters and Autoscaling group capacity. Head over to the [GitHub repository](https://github.com/jlaitio/aws-infra-shutdown-scheduler) and check it out for yourself. 

**AWS Lambda power tuning**

Alex Casalboni's AWS Lambda power tuning has been featured in this newsletter before, and is an open-source tool that can help you visualize and fine-tune the memory/power configuration of Lambda functions. It runs in your own AWS account - powered by AWS Step Functions - and it supports three optimization strategies: cost, speed, and balanced.

This week, [AWS Lambda Power Tuning v3.2.5 was released](https://github.com/alexcasalboni/aws-lambda-power-tuning) featuring improved logging for Lambda execution errors and some new fancy documentation to deploy the SAR app via AWS CDK. Head over to the [GitHub repository ](https://github.com/alexcasalboni/aws-lambda-power-tuning)and give it a go. You will wonder how you ever managed without it.

Grazie Alex!

**Tesseract on AWS Lambda**

Tesseract is an open source OCR engine, widely used because it’s open-source and in this blog post and walkthrough, [Jan Giacomelli shows you have to deploy Tesseract on AWS Lambda](https://typless.com/2020/05/21/tesseract-on-aws-lambda-ocr-as-a-service/).

Thank you Jan!


### Blog posts you should check out

In[ No.17](https://dev.to/aws/aws-open-sources-news-and-updates-instalment-no-17-137n) I shared a short video from Alluxio, who are powering innovation with an open sourced data orchestration product. In this new post, [Bin Fan who is VP of Open Source and founding member at Alluxio shares a customer case study on accelerating spark and hive jobs on Amazon S3 using Alluxio](https://hackernoon.com/accelerate-spark-and-hive-jobs-on-aws-s3-by-10x-with-alluxio-as-a-tiered-storage-solution-5c3s3yes). Thai Bui describes how Bazaarvoice leverages Alluxio as a caching tier on top of  AWS S3.

![Alluxio architecture](https://hackernoon.com/photos/MEO1Whp7pdbY2Fmqr6xMgItyqS23-0223ywl)

**AWS AppSync**

A few posts on AWS AppSync and Amplify this week.

First is an absolutely essential read if you are [using AWS AppSync, and looking for a way of unit testing during the writing resolver mapping templates](https://mechanicalrock.github.io//2020/04/27/ensuring-resolvers-aren't-rejected.html). Resolver mapping templates, written in Velocity Template Language (VTL) take the GraphQL request as input and produce a JSON document containing the resolver instructions as output.

Very nice post[ Mechanical Rock](https://twitter.com/mechanicalrock_).

Following that is this post from [Rich at Going Serverless](https://www.goingserverless.com/about/) and I love how this post, [How to build an AppSync API using a single table DynamoDB design](https://www.goingserverless.com/blog/single-table-dynamodb-for-appsync) starts;

> If you want to start a flame war in the AWS AppSync community then ask if you should use a single or multiple table design for DynamoDB.

The rest of the post goes onto walk you building a single table solution. Thank you Rich.


Finally we have Brice Pelle, who wrote a blog post and provided source code for [implementing pagination with AWS AppSync](https://dev.to/onlybakam/implementing-pagination-with-aws-appsync-5d08). In this post Brice talks about why you need to think about pagination within your own applications and then offers some alternatives before showing you how to do this easily with Amplify and AWS AppSync.	

![pagination image](https://res.cloudinary.com/practicaldev/image/fetch/s---9CMKuGe--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/g12p61m573zy93mb9rkh.png)

You can find the source code for this in [his GitHub repository here](https://github.com/onlybakam/todo-app-pagination).


### AWS updates

**Open Government solutions**

Governments and public sector organisations across the globe increasingly look for open source solutions first. We have put together a landing page to help you find all the solutions you might need. These resources developed by the public sector can help government agencies at the local, regional, and national levels find solutions that have worked for others so that they can accelerate their digital transformation.

Head over to the [landing page at open government solutions](https://aws.amazon.com/government-education/government/open-government-solutions/).

Following on from that, Laim Maxwell has put this post together, [Open source in the fight against COVID-19](https://aws.amazon.com/blogs/publicsector/open-source-fight-against-covid-19/) that shows some examples of how government agencies are using those open government solutions.

**LAMP on AWS Snowball Edge**

LAMP stacks (Linux, Apache, MySQL and PHP) used to dominate the world, and whilst they may not be as popular as they used to, PHP continues to go from strength to strength and is still hugely popular when I speak with developers. 

AWS Snowball Edge is a ruggedized shippable edge compute solution used for running compute instances in intermittently connected or even disconnected environments. Snowball Edge requires minimal infrastructure to operate, and specifically does not require a dedicated data center.

Vinod Pulkayath writes in [Deploying a LAMP-based multi-tier web application on AWS Snowball Edge](https://aws.amazon.com/blogs/storage/deploying-a-lamp-based-multi-tier-web-application-on-aws-snowball-edge/), how you can launch EC2 instances and bring up a web application on a Snowball Edge, installing Apache, MySQL, PHP (LAMP) as well as and Drupal, a popular content management system (CMS).

![Architecture for LAMP on Snowball](https://d2908q01vomqb2.cloudfront.net/e1822db470e60d090affd0956d743cb0e7cdf113/2020/05/18/Diagram-depicts-the-overall-architecture-of-the-deployment-Snowball-Edge-runs-a-web-server-and-a-database-server..png)

Thank you Vinod Pulkayath.

**EKS and NGINX**

In this post from Cornell Anthony, [Using a Network Load Balancer with the NGINX Ingress Controller on Amazon EKS](https://aws.amazon.com/blogs/opensource/network-load-balancer-nginx-ingress-controller-eks/), find out how to use an NGINX ingress controller on Amazon EKS, and how to front-face it with a Network Load Balancer (NLB).

![Architecture post](https://quip-amazon.com/blob/bGA9AAmviCK/RxIsFh8j-vQYBvmZWBNpOw?a=gc7lDKxZ4JUQcZcn1Ojr4h0axnP0cmkLy1LWdZ3fuDga)

**Monitoring AWS services used by Kubernetes with Prometheus**

In this post, [Monitor AWS services used by Kubernetes with Prometheus and PromCat](https://aws.amazon.com/blogs/opensource/monitor-aws-services-used-by-kubernetes-with-prometheus-and-promcat/), Jonah Jones walks through the recent open source contributions to YACE (Yet Another CloudWatch Exporter) made by Sysdig. YACE is a Prometheus exporter designed to pull in CloudWatch metrics and to enrich your existing Prometheus setup with AWS service metrics. Sysdig is making these enhancements available through PromCat, an open source resource catalog for Prometheus monitoring. 

You will find details on how to set this up as well as links to all the GitHub repositories as well.

Sysdig is an AWS Partner Network (APN) Advanced Technology Partner with AWS competency in containers, and has a strong open source background, with engineers who have co-founded projects such as Wireshark and Falco. Thank you folks!


**Spinnaker and AWS CodeBuild**

Spinnaker is an open-source tool built by Netflix for continuous integration/continuous deployment (CI/CD). The two core features of Spinnaker are application management and application deployment. 

Continuous integration is a DevOps software development practice in which developers regularly merge their code changes into a central repository, then run automated builds and tests. Continuous integration (CI) most often refers to the build or integration stage of the software release process and entails both an automation component (such as a CI or build service) and a cultural component (such as learning to integrate frequently).

In [Using CodeBuild in Spinnaker for continuous integration](https://aws.amazon.com/blogs/devops/using-codebuild-in-spinnaker-for-continuous-integration/), Muhammad Mansoor and Subin Mathew walk you through configuring AWS CodeBuild to provide CI capabilities in Spinnaker.


**Deploying a serverless application using AWS CDK**

Whenever I talk about Serverless, one of the questions I always get asked is how to approach breaking down an existing monolithic architecture into one that leverages serverless services.

In this post, [Deploying a serverless application using AWS CDK](https://aws.amazon.com/blogs/devops/deploying-a-serverless-application-using-aws-cdk/), Georges Leschener and Luis Lopez Soria show you how to transform an application running on Amazon EC2 into serverless architecture by leveraging services such as Amazon API Gateway, Lambda, Cloud 9, AWS CDK, and Aurora Serverless. The benefit of serverless architecture is that it takes away the overhead of having to manage a server and helps reduce costs, as you only pay for the time in which your code executes.

Thank you Georges Leschener and Luis Lopez Soria.

### Quick updates

**AWS announces Deep Learning Containers for TensorFlow 2.2**

The AWS Deep Learning Containers are available today with TensorFlow 2.2 support. You can launch the new versions of the Deep Learning Containers on Amazon SageMaker, Amazon Elastic Kubernetes Service (Amazon EKS), self-managed Kubernetes on Amazon EC2, and Amazon Elastic Container Service (Amazon ECS). [Full announcement here](https://aws.amazon.com/about-aws/whats-new/2020/05/aws-announces-deep-learning-containers-for-tensorflow-2-2/).

**Introducing the Amazon EKS Best Practices Guide for Security**

Amazon Elastic Kubernetes Service (EKS) now makes it easier to implement security best practices for Kubernetes on AWS with the Amazon EKS Best Practices Guide for Security.

Security is a critical component of configuring and maintaining Kubernetes clusters and applications. Amazon EKS provides secure, managed Kubernetes clusters by default, but you still need to ensure that you configure the nodes and applications you run as part of the cluster to ensure a secure implementation. 

The Amazon EKS Best Practices Guide for Security helps you configure every component of your cluster for high security. The guide covers a broad range of topics including pod security, network security, incident response, and compliance.

Check out the full guide via [GitHub](https://github.com/aws/aws-eks-best-practices/) or the live [doc site, Amazon EKS Best Practice Guide for Security](https://aws.github.io/aws-eks-best-practices/).


### Tweet of the Week

This tweet [tweet](https://t.co/VSHkzFKHDf?amp=1) (and video) from Julie Baldwin (of SUSE) speaking on the relationship between SUSE and AWS for open source caught my attention this week. theCube also covered this via their [tweet](https://twitter.com/theCUBE/status/1263149118404296704), and [Mikhail Prudnikov of AWS followed up](https://twitter.com/theCUBE/status/1263145628382769152) speaking on the strength and innovation in the open source community.

---

### Do you use AWS and love open source? 

Do you have some content you want to share with a broader audience? We are always looking for guest content for the AWS Open blog. Please get in touch (via comments below) and I would love to speak with you about what you are doing in open source. We are always looking for interesting new content.


### Stay in touch with open source at AWS

I hope this summary has been useful. I have looked for all the session videos that have been uploaded to date, but if I have missed anything, please get in touch and I will update this summary. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on @AWSOpen.