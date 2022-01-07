---
title: 'AWS open source news and updates - No. 15'
date: '2020-04-13'
tags : [ oss-newsletter ]
---
## April 13th - Instalment #15

Episode 15, the Easter special and even though this is a holiday in most of Europe, that was not going to stop me posting this weeks latest and greatest updates from the confluence of AWS and open source.

### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created.

So thank you to the folks at deepset, bluematador, Laimonas Sutkus, Olaf Conujn, Thomas Cappetta, Mayur Shetty, Ian Mackay (@iann0036), Ram Dileepan and Santiago Cardenas.


### Startups love open source

Checkout my colleague Rob De Feo's podcast on startup deepset, and how they are using the latest machine learning research and converting those into products their customers love. What's even better is that they are open sourcing this too.
Check out the podcast, [Startup Engineering](https://www.linkedin.com/posts/robdefeo_machinelearning-deeplearning-nlp-activity-6653609302005288960-JgUf/) and check out the open source projects from [deepset](https://deepset.ai/) on their [GitHub repository](https://github.com/deepset-ai).

Some of the projects they have open sourced include [FARM](https://github.com/deepset-ai/FARM) that allows you to do transfer learning within the agri industry, or [Haystack](https://github.com/deepset-ai/haystack), Q&A at scale.


### Latest from open source projects


**Security**

This week has seen some interesting new posts and projects around security. 

The first one up came up in my news finder and is a round up of [four open source cloud security tools](https://opensource.com/article/19/9/open-source-cloud-security) that you should be aware of when using AWS with GitHub. There were three new projects to me on this list, and whilst I have not checked them out yet, it is good to know that these projects have your back. As the posts says thought;

>These tools are by no means silver bullets, but they are just that: tools! So, make sure you work with the rest of your organisation to understand the use cases and usage patterns for your cloud services before trying to implement any of these tools or other controls.

The second one is CyberRange, and you can find the [GitHub repository and excellent documentation here](https://github.com/secdevops-cuse/CyberRange). From the README:

>This project provides a bootstrap framework for a complete offensive, defensive, reverse engineering, & security intelligence tooling in a private research lab using the AWS Cloud.

![CyberRange diagram](https://media.githubusercontent.com/media/secdevops-cuse/CyberRange/master/img/CyberRange-architecture-v2.png)


**AWS SNS Slack Subscriber**


This [project](https://github.com/idenfy/AwsSnsSlackSubscriber) aims to help you provide an alternative destination for your SNS topics - away from email and into your Slack channel. As they say in the project description, it creates a "Slack subscription". ([Here is the project on PyPi](https://pypi.org/project/aws-sns-slack-subscriber/))

Thanks Laimonas Sutkus for this contribution. Laimonas has published this under Idenfy's GitHub repository where you will find more interesting open source projects. [AWSEmptyBucket](https://github.com/idenfy/AwsEmptyBucket) allows you to easily clear out your Amazon S3 buckets - useful for reaping purposes if you are automating your stack, but there are more. AWSGetSecret, AWSCiCdLambda, AWCCiCdFargate, AwsEmptyEcrRepository and more. Check them out at [Idenfy's GitHub repository](https://github.com/idenfy). 

**IAM on Kubernetes**

Are you using Kubernetes on AWS and want to understand how to use AWS Identity and Access Management (IAM) for your pods? Well, **bluematador** has you covered here in a blog post ([IAM Access in Kubernetes: How to install kube2iam](https://www.bluematador.com/blog/iam-access-in-kubernetes-installing-kube2iam-in-production?utm_campaign=Kubernetes&utm_content=125234681&utm_medium=social&utm_source=twitter&hss_channel=tw-764175728552271872)) showing how you can do this using their open source project, [**kube2iam** (GitHub repository here](https://github.com/jtblin/kube2iam)). 

This project enables IAM credentials to be provided to containers running inside a kubernetes cluster. Sound useful? Then read the blog post and check it out.


**OpenShift**

A guest blog post from Mayur Shetty from Red Hat, [Managing hybrid storage in an increasingly agile time with OpenShift Container Storage on AWS](https://aws.amazon.com/blogs/opensource/managing-hybrid-storage-in-an-increasingly-agile-time-with-openshift-container-storage-on-aws/), looking at how to address the challenge of consistency in storage management for Open Shift environments, looking at a new open source solution: OpenShift Container Storage (OCS) operator. Curious? Then read on...


**AWS account controller**

This one is hot off the press and I think you will enjoy. Ian Mackay [tweeted](https://twitter.com/iann0036/status/1249552376240824320) this earlier. I know a lot of folks are going to like this project - a project that allows you to create and delete self service, sandbox  AWS accounts. Make sure you check the project requirements, but if they work for you this is going to be very useful I think. 

![AWS Account controller](https://raw.githubusercontent.com/iann0036/aws-account-controller/master/assets/accountmanager.png)

Here is the GitHub repository for [AWS account controller.](https://github.com/iann0036/aws-account-controller) Thank you Ian!


### AWS Open Source projects

**Amplify**

The Amplify Framework is an open source project for building cloud-enabled mobile and web applications, consisting of libraries, UI components, and a CLI toolchain. In this blog post, ready about the new, [rearchitected Amplify UI component libraries](https://aws.amazon.com/blogs/mobile/amplify-framework-announces-new-rearchitected-ui-component-and-modular-javascript-libraries/) that helps javascript developers to easily add authentication scenarios into their web applications.


**ROS - Robotics Operating System**

If you wanted to find out what is with the open source Robotics Operating System (ROS), with insights from Katherine Scott developer advocate at Open Robotics, then wonder no more. Read the full blog post, [Whats new with the open source Robot Operating system in 2020](https://aws.amazon.com/blogs/opensource/whats-new-with-the-open-source-robot-operating-system-in-2020/).


**Using GitLab to deploy SAM applications**

If you are a serverless developer using SAM, then this might pique your interest. [How to combine SAM and GitLab to create a CI/CD pipeline to deploy your SAM applications](https://aws.amazon.com/blogs/apn/using-gitlab-ci-cd-pipeline-to-deploy-aws-sam-applications/
). This is a complete walkthrough and you will learn how to set this up and use it in your own projects. Thank you Ram Dileepan and Santiago Cardenas.


### Tweet of the week

Last week there was a big announcement around the open sourcing of the Docker Compose specification. You can see the [tweet here](https://twitter.com/Docker/status/1247515727025840128), and check out the [announcement here](https://www.docker.com/press-release/docker-open-sources-compose-specification). Having worked with Docker Compose files recently when creating a build for an open source project, I did run into some limitations that I think will now be addressed with the evolving work that will unfold. Great things ahead I think.


### Hot blogging posts you must read

So happy to see this blog post from Olaf - you may remember that I shared his project a few weeks back. Well he has put his blogging cap on, and dives deep into AWS Organisations and how his open source project can help you.

Read the deep dive blog post, [Off to a great start with AWS Organisations](https://dev.to/oconijn/off-to-a-great-start-with-aws-organizations-1i74).


### Hybrid capabilities - open source as an enabler

Many customers use open source technologies, and open source provides hybrid capabilities allowing customers to make choices based on the level of flexibility and customisation they want, the skills and resources they have, the level of risk they want to take on and whether there are any requirements around data portability. 

Using services such as [DMS, (Database Migration Service](https://aws.amazon.com/dms/)), customers can move off proprietary database platforms and move onto open source databases such as Amazon RDS MySQL or Postgres, which provides them options to where they want to run those workloads moving forward.

AWS provides managed versions of open source technologies that allow customers to focus on being able to use that software rather than the undifferentiated heavy lifting of operating and maintaining it. Customers can use open source technologies against data and data analytics, machine learning, compute and many other areas.

![Diagram of hybrid and open source](https://ras-cf-public.s3-eu-west-1.amazonaws.com/images/ent04-ricsue_accelerating_digital_transformation_with_hybrid_capabilities.pptx.png)

We have customers that are taking this approach, such as[ Globe Telecom (read the full blog post here](https://aws.amazon.com/blogs/modernizing-with-aws/how-globe-telecom-is-modernizing/)) but I am always interested in hearing more about how customers are using open source technologies to provide hybrid capabilities and architectures. Please share in the comments if you have seen or are doing something interesting in this space.


---

### Do you use AWS and love open source? 

Do you have some content you want to share with a broader audience? We are always looking for guest content for the AWS Open blog. Please get in touch (via comments below) and I would love to speak with you about what you are doing in open source. We are always looking for interesting new content.

### We are hiring

We are hiring, so if you love open source, then why not check out the current openings. We would love to hear from you and if you want to chat and ask me anything, connect to me via LinkedIn or Twitter and always happy to talk.

[Open Source jobs at Amazon and AWS](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) - scroll to bottom, on left.

### Stay in touch with open source at AWS

I hope this summary has been useful. I have looked for all the session videos that have been uploaded to date, but if I have missed anything, please get in touch and I will update this summary. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on @AWSOpen.
