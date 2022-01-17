---
title: 'AWS open source news and updates - No. 13'
date: '2020-03-30'
tags : [ oss-newsletter ]
---
## March 30th - Instalment #13

Episode 13, lucky for some, superstitious for others. I can promise you no superstitious when you read this, nothing but the finest open source news and updates from around the globe and hopefully a few projects that you will find useful. First though, let us celebrate those people that without them, this newsletter would be just an empty vessel. Interesting to see a higher than normal number of new projects and first time projects this week which is awesome. I hope this trend continues.


### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created.

So thank you Yan Cui (@theburningmonk), Mattias Severson (@mattiasseverson), Lee Packham (@Joolz), Joey Triska (@jdtriska), Justin Garrison (@rothgar), John Preston, Ben Whaley (@iAmTheWhaley), Mahdi Azarboon (@m_azarboon), Massimo Re Ferre (@mreferre) and Matt Asay (@mjasay)


### Latest from open source projects

**lumigo-cli - v0.40**

I have shared [Yan Cui](https://twitter.com/theburningmonk)'s open source projects and posts before, but this week he released a new version of the [Lumigo CLI project](https://www.npmjs.com/package/lumigo-cli). In v.0.40.0 you can now auto-optimize a Lambda function with the powertune-lambda command! Check out the original [tweet](https://twitter.com/theburningmonk/status/1242205410314108930) and then head over to find out more in the [lumigo-cli project GitHub repository](https://github.com/lumigo-io/lumigo-cli).


**Jellyfin on AWS**

Do you use the open source project Jellyfin? If you are familiar with or even run a Plex server or client, then Jellyfin provides an open source equivalent and allows you to deploy a media system that allows you to manage your media and streaming files. It is a very active project with a diverse set of contributors.

So if you want to give Jellyfin a try, why not have a look at this repo from [Joey Triska that walks you through setting up Jellyfin on AWS](https://github.com/jdtriska/instant-jellyfin). 

**Security**

AWS_Loot is a small project that helps you ensure you are not exposing your environments. You can use this auditing tool to test against a number of services (Amazon EC2, AWS CodeBuild, AWS Lambda) to make sure you are not accidentally revealing secrets. Find the [repo at Sebastian's Github repository](https://github.com/seb1055/AWS-Loot).


**ssm-helpers**

Sprinkling magic is the next open source project by [Justin Garrison](https://twitter.com/rothgar), a project that provides helpers to manage your systems with AWS Systems Manager. As fresh as it gets, head on over to the GitHub repository [https://github.com/disneystreaming/ssm-helpers](https://github.com/disneystreaming/ssm-helpers) - clear documentation and user guidance always welcome. Thank you Justin!

**ssmsh**

Following on from ssm-helpers is Ben Whaley's project **ssmsh** which provides a shell for the AWS parameter store. If you are not sure what the parameter store is, it provides secure, hierarchical storage for configuration data management and secrets management. You can store data such as passwords, database strings, Amazon EC2 instance IDs, Amazon Machine Image (AMI) IDs, and license codes as parameter values. You can store values as plain text or encrypted data. Ben's project allows you to (take from the README.md file) to:

* Interact with the parameter store hierarchy using familiar commands like cd, ls, cp, mv, and rm
* Supports relative paths and shorthand (..) syntax
* Operate on parameters between regions
* Recursively list, copy, and remove parameters
* Get parameter history
* Create new parameters using put
* Advanced parameters (with policies)
* and more

Sound useful to you? Then check the [ssmsh Github repository here](https://github.com/bwhaley/ssmsh). Thank you Ben.

**ECS ComposerX**

Another new open source project, this time from the prolific hands of [John Preston](https://github.com/JohnPreston). ECS ComposerX is a tool to generate CFN templates that allows you to build and publish their applications running in Docker containers on top of AWS ECS. If that sounds useful to you, then head over to the [ECS ComposerX repository](https://github.com/lambda-my-aws/ecs_composex) and whilst you are there check out the other projects too.

**Serverless Ops Boilerplate**

Most organisations create multiple AWS accounts because they provide the highest level of resource and security isolation. Mahdi Azarboon shared his very first open source project this week, [a production ready serverless Ops boilerplate](https://github.com/eficode/serverless-ops-boilerplate), inspired by an AWS blog post ([Building a secure cross account continuous delivery pipeline](https://aws.amazon.com/blogs/devops/aws-building-a-secure-cross-account-continuous-delivery-pipeline/)) this project uses a number of AWS servers to simplify what is outlined in that post.


### AWS Open Source projects

**Knative on Fargate**

Massimo has been a prolific contributor and I have shared many of his projects, so here is his latest. The industry of OSS projects that abstract a container orchestrator interface and provide the illusion of a FaaS (Function as a Service) experience flourishing. This [knative on fargate repo](https://github.com/mreferre/knative-on-fargate) will outline the instructions on how to setup a similar experience using Knative (a Google owned OSS project) on top of EKS/Fargate.

![Knative on Fargate](https://github.com/mreferre/knative-on-fargate/blob/master/images/knative-on-fargate.png?raw=true)



**AWS CDK**

Great [blog post from Mattias Severson](https://blog.jayway.com/2020/03/23/aws-cdk-mfa/) on how he used [cdk-multi-profile-plugin](https://www.npmjs.com/package/cdk-multi-profile-plugin) to work around MFA not currently being supported and to improve your security posture when working with the AWS CDK.

**Django Amazon Translate**

Fresh from the [Lee Packham's software forge](https://github.com/leepa), comes this project, [Django Amazon Translate](https://django-amazon-translate.readthedocs.io/en/latest/readme.html) that in Lee's own words:
>Utilities for Django to translate both Models and Django gettext files using Amazon Translate.
Written because doing translation ends up getting forgotten and increasing accessibility in projects should be easy for everyone.


Check out the project GitHub repository here -> [https://github.com/leepa/django_amazon_translate](https://github.com/leepa/django_amazon_translate)

**AWS console icons**

I could not help also mention another one of Lee's projects, the AWS iconification project which allows you to identify open browser tabs with the corresponding AWS service icon. Sounds simple, but for those *ahem* like myself, who relishes having many many tabs open, knowing which tab corresponds to which AWS service is great productivity boost. 

When you get it up and running your browser tabs have never looked so fabulous.

![Browser tabs with iconification enabled.
](https://ras-cf-public.s3-eu-west-1.amazonaws.com/images/Screenshot+2020-03-24+at+14.00.31.png)

So that is a double thank you Lee!


**Machine Learning**

Straight from the [AWS Whats New feed](https://aws.amazon.com/new/?nc1=f_cc&whats-new-content-all.sort-by=item.additionalFields.postDateTime&whats-new-content-all.sort-order=desc&wn-featured-announcements.sort-by=item.additionalFields.numericSort&wn-featured-announcements.sort-order=asc&awsm.page-whats-new-content-all=1&awsf.whats-new-year=*all&awsf.whats-new-products=*all), comes news of [updates to the AWS deep learning containers](https://aws.amazon.com/about-aws/whats-new/2020/03/updates-to-aws-deep-learning-containers-for-tensorflow-pytorch-mxnet/). 

Announced and available today are the latest framework versions of TensorFlow 2.1.0 & 1.15.2, PyTorch 1.4.0, and MXNet 1.6.0 . The release includes the addition of Amazon SageMaker Python SDK in the containers, and updates to the Amazon SageMaker Experiments package. Amazon SageMaker Experiments is a feature in Amazon SageMaker that lets you organise, track, compare, and evaluate machine learning (ML) experiments and model versions. The TensorFlow 2.1.0 python3 training containers now also include SageMaker Debugger, which allow data scientists to save and inspect the model tensors during training jobs.


### Researching open source projects

When working with open source software and projects, there are often times when you need to research the project; how established is it, who is using it, how many contributors, etc. There are a number of invaluable resources where you can go to find out information about a project. 

Key data you might want to find is who is using the project, how is it rated or maybe some more technical details around languages or open source license. Other times you might want to know more about the history of the project, perhaps look at the structure and finances. There are resources out there were you can find all this stuff. Here are some, but would love for you to add your own in the comments so I can include/update this post with those.

* https://opensourceprojects.eu/p/
* https://docs.google.com/spreadsheets/d/17nKMpi_Dh5slCqzLSFBoWMxNvWiwt2R-t4e_l7LPLhU/edit#gid=0
* https://www.openhub.net/
* https://wikipedia.org

### Spotlight on

So, I mentioned 418sec in an early edition of this newsletter, and I am very happy to share a blog post they put together on the AWS Open Source blog. If you want to know how [418sec is helping to keep the open source ecosystem secure](https://aws.amazon.com/blogs/opensource/how-a-startup-wants-to-help-secure-the-open-source-ecosystem-with-huntr-a-bug-bounty-board/), then have a read of this.

### Modernising apps with open source

Great read from [Matt Asay](https://twitter.com/mjasay) on how to transform your application stack using open source, in this case, some great examples of moving from .Net to .Net Core. Read on to find out why [customers are moving from .Net Framework to .Net Core on AWS](https://aws.amazon.com/blogs/modernizing-with-aws/why-customers-are-moving-from-net-framework-to-net-core-on-aws/).


---
### Do you use AWS and love open source? 

Do you have some content you want to share with a broader audience? We are always looking for guest content for the AWS Open blog. Please get in touch (via comments below) and I would love to speak with you about what you are doing in open source. We are always looking for interesting new content.

### We are hiring

We are hiring, so if you love open source, then why not check out the current openings. We would love to hear from you and if you want to chat and ask me anything, connect to me via LinkedIn or Twitter and always happy to talk.

[Open Source jobs at Amazon and AWS](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) - scroll to bottom, on left.

### Stay in touch with open source at AWS

I hope this summary has been useful. I have looked for all the session videos that have been uploaded to date, but if I have missed anything, please get in touch and I will update this summary. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on @AWSOpen.
