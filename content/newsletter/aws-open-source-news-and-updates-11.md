---
title: 'AWS open source news and updates #11'
date: '2020-03-16'
tags : [ oss-newsletter ]
---
## March 16th - Instalment #11

Another packed weekly instalment of open source goodness for you, including a very hot announcement we made this week on Bottlerocket. Whether you are interested in security, devOps or the latest open source projects that run on AWS or make your life easier, then read on as there is something for you.

### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created.

So thank you Jungyoul Yu, the AWS Bottlerocket team, Dan Mangum, Toni Solarin-Sodara, Adrian Steele, Adrian Hornsby, Martin Thwaites, Cyrus Wong, Chanwit Kaewkasi, Shashank Prasanna, Toni de la Fuente, Heitor Lessa


### Latest from open source projects

**Chaos**

As many of you may know, Adrian Hornsby is our resident 'master of disaster' and he has put together a set of excellent posts that walk you through this topic. What you may not know however, is he has also put together a number of open source projects that can help you. Read on in [Adrian's Chaos engineering collection](https://medium.com/@adhorn/the-chaos-engineering-collection-5e188d6a90e2).

**Envoy**

Another Adrian, this time Adrian Steele (@__steele) shares news that a PR to Envoy to enable Lambda functions as targets in App Mesh, enabling frictionless transition to and from containers, instances, etc. Check out the pull request here - https://github.com/envoyproxy/envoy/pull/10260

**cloud-nuke**

Optimising your AWS bill is something that should be front of mind for all users of Cloud services. This open source project provides a mechanism to help, by enabling you to shutdown services based on criteria you select. This sounds like it will be very useful, so check out their blog post - [how we reduced our AWS bill by 85%](https://blog.gruntwork.io/cloud-nuke-how-we-reduced-our-aws-bill-by-85-f3aced4e5876)

**AWS CodeDeploy, .net Core and Linux**

I love it when I get .net related open source news and projects, so was very happy when Martin shared this blog post on [Deploying .NET Core to Linux using CodeDeploy](https://martinjt.me/2020/03/08/deploying-net-core-to-linux-using-codedeploy/). If you use .NET core and been looking for some writing on how to deploy this via AWS CodeDeploy, then you are in luck. Thank you Martin.

**Crossplane**

[Guest post on the AWS open source blog from Dan Mangum, a software engineer at Upbound](https://aws.amazon.com/blogs/opensource/connecting-aws-managed-services-to-your-argo-cd-pipeline-with-open-source-crossplane/). Crossplane, which is released under the Apache 2.0 license, enables complex applications and infrastructure to be defined, deployed, and managed all from kubectl. Crossplane uses the Kubernetes API to declaratively define, deploy, and manage cloud infrastructure, including SaaS services. Crossplane’s functionality can be included in your CI/CD pipeline, giving a singular approach to defining and deploying any resource, whether that resource is Kubernetes-native or a component of a managed service.

**DeepRacer-sim**

AWS DeepRacer has a brilliant community that create some amazon open source projects. Here is yet another one, this time a project form [Jungyoul Yu called Deepracer-Sim](https://github.com/nalbam/deepracer-sim/blob/master/README.md), that allows you to test your reward functions in this simulator.

If you want to keep up to speed with the open sourcery going on within the AWS DeepRacer community, check out the https://deepracing.io site and join the community (and say hello!)

**flutterAmplify**

Short and sweet this one, if you are looking for an [authentication Flutter plugin for AWS Amplify SDK](https://pub.dev/packages/flutter_aws_amplify_cognito), then look no more.

**Using containers for machine learning development**

My colleague Shashank Prasanna writes about [why you should use Docker containers for machine learning development](https://aws.amazon.com/blogs/opensource/why-use-docker-containers-for-machine-learning-development/). This is a great introductory post and walk through on why you should consider the use of various open source technologies such as Docker containers when undertaking machine learning development.

**Security tools**

[Toni shares his security toolbox list](https://github.com/toniblyx/my-arsenal-of-aws-security-tools), and with over 4K starring this repo and 20 contributors, you should definitely check out the list of security tools to make sure you are securing your workloads. Some of these tools I have mentioned in previous posts, but there are plenty of new ones that I have not seen or used before. The curated list is broken down into Defensive (hardening, security assessment and inventory), Offensive, Continuous security auditing, digital forensics and incident response, development security and training.

This should definitely be in your saved bookmarks. Be sure to add your own tools and send a PR if you think there are some essential open source tools you use that are missing from this list. 


### AWS Open Source projects

**Bottlerocket**

So, the big news this week was the [launch](https://aws.amazon.com/blogs/aws/bottlerocket-open-source-os-for-container-hosting/) of [Bottlerocket](https://aws.amazon.com/bottlerocket/) that we announced this week. So what is Bottlerocket? 

>Bottlerocket is a new Linux-based open source OS that is purpose-built to run containers. With Bottlerocket, you can improve the availability of your containerised deployments and reduce operational costs by automating updates to your container infrastructure. Bottlerocket includes only the essential software to run containers, which improves resource usage, reduces security attack surface, and lowers management overhead. It also integrates with container orchestrators (such as Amazon EKS) to further reduce management and operational overhead while updating container hosts in a cluster. We are aiming for Bottlerocket to be Generally Available later in 2020.

Essential reading is the [Bottlerocket FAQ](https://aws.amazon.com/bottlerocket/faqs/) document that accompanied this launch announcement.

Tweets about the launch worth mentioning. First up is [Manrique](https://twitter.com/jsmanrique) who shared the [CHAOSS dashboard of the Bottlerocket project](https://twitter.com/jsmanrique/status/1237526294465613824?s=11). Deepak Singh added this [tweet](https://twitter.com/mndoci/status/1237505259880079362?s=11) where he noted:
>Bottlerocket encapsulates lessons that we (and our customers and partners) have learned over the past 5 years or so from running containers at scale. Bottlerocket focuses on security and maintainability and shines when you couple it with a container orchestrator.

Finally, Matt Wilson then shared this tweet about the [partners that are already onboard with supporting this distribution](https://twitter.com/_msw_/status/1237551362423943173?s=11). Chanwit Kaewkasi from Weaveworks also posted [Bottlerocket with Fork, Clone, Run! - A Container Optimised OS with a GitOps model](https://www.weave.works/blog/bottlerocket-with-fork-clone-run) which you can follow to see how you can perform GitOps operations on an EKS cluster backed by these Bottlerocket images.

**AWS EKS**

Kubernetes is rapidly evolving, with frequent feature releases and bug fixes. The Kubernetes 1.15 release focuses on stability and maturity of the core feature set. Additional 1.15 highlights include support configuring TLS termination on NLB load balancers, improved support for CustomResourceDefinitions, as well as NodeLocal DNSCache graduating to beta. Learn more about Kubernetes version 1.15 in the Kubernetes project release notes.

Read more in the official [whats-new blog post](https://aws.amazon.com/about-aws/whats-new/2020/03/amazon-eks-now-supports-kubernetes-version-1-15/).


**AWS CDK patterns**

I have shared before about the CDK Patterns project, looking to collect re-usable and repeatable patterns that can be used by customers. This week we see a new contribution around [The Simple GraphQL service](https://github.com/cdk-patterns/serverless/blob/master/the-simple-graphql-service/README.md). Interested? Hop on over and have a browse.

**Machine Learning AMI updates**

The [AWS Deep Learning AMIs](https://aws.amazon.com/about-aws/whats-new/2020/03/new-aws-deep-learning-amis-with-updated-framework-support-tensorflow-pytorch-mxnet-elastic-inference-with-pytorch/) are available on Ubuntu 18.04, Ubuntu 16.04, Amazon Linux 2, and Amazon Linux with TensorFlow (1.15.2 & 2.1.0), PyTorch 1.4.0, MXNet 1.6.0. The PyTorch EI environment has been updated to 1.3.1.

AWS Deep Learning AMIs also support other interfaces such as Keras, Chainer, and Gluon — pre-installed and fully-configured for you to start developing your deep learning models in minutes while taking advantage of the computation power and flexibility of Amazon EC2 instances. When you activate a Conda environment, the Deep Learning AMIs automatically deploy higher-performance builds of frameworks, optimised for the EC2 instance of your choice.

### Deep Dive

https://writing.kemitchell.com/2020/03/07/No-Posse.html

An epic project to walk through, this great project and post by Cyrus Wong (AWS Machine Learning hero) on **[How to use AWS AI, AWS Amplify and Amazon Sumerian to save online class!](https://www.linkedin.com/pulse/how-use-aws-ai-amplify-amazon-sumerian-save-online-wong/)** which walks you through how to pull together a number of AWS services to provide an online classroom and learning experience.

From the post, additional shout outs to the following:
>This project has been developed in collaboration with my students Mike Ng (Technical Program Intern at AWS), Lam Pak Yin, and Pearly Law from the IT114115 Higher Diploma in Cloud and Data Centre Administration. Also, thanks to the AWS Educate, which helps my students learn how to use AWS services in depth!

### AWS Workshops

We open source many workshops, and I shared a post with some resources to help find some of those here, and from time to time there are updates that are worth sharing.
If you are a serverless developer, or wanting to get started with serverless development, then the [Serverless Airline Booking workshop](https://github.com/aws-samples/aws-serverless-airline-booking) is for you. Heitor tweeted this week about a major update, so now is a good time to find some time and walk through this workshop. There are plenty of online recorded videos to help walk you through this, and in my opinion, this is essential viewing.

Thanks for the update Heitor.


---
### Do you use AWS and love open source? 

Do you have some content you want to share with a broader audience? We are always looking for guest content for the AWS Open blog. Please get in touch (via comments below) and I would love to speak with you about what you are doing in open source. We are always looking for interesting new content.

### We are hiring

We are hiring, so if you love open source, then why not check out the current openings. We would love to hear from you and if you want to chat and ask me anything, connect to me via LinkedIn or Twitter and always happy to talk.

[Open Source jobs at Amazon and AWS](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) - scroll to bottom, on left.

### Stay in touch with open source at AWS

I hope this summary has been useful. I have looked for all the session videos that have been uploaded to date, but if I have missed anything, please get in touch and I will update this summary. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on @AWSOpen.
