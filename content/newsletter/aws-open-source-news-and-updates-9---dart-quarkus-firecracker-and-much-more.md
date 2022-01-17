---
title: 'AWS open source news and updates #9 - Dart, Quarkus, Firecracker and much more'
date: '2020-03-02'
tags : [ oss-newsletter ]
---
As we head into March and instalment #9 of AWS open source news and updates, over the past two months I have shared eight posts covering over 100 unique articles on open source and AWS. It is great to see so much activity and across such a broad spectrum of interests. This instalment is representative of that, with everything from security, machine learning, big data and analytics to new programming runtimes. 

As always, please get in touch if you have some interesting open source projects or stories to share, and I am always looking for authors who are interested in sharing their story on the AWS Open source blog.


### Latest from open source projects

**Spinnaker**

Spinnaker is an exciting open source project from Netflix, it is a cloud-based continuous delivery platform for releasing software changes rapidly and reliably. It enables developers to focus on writing code and deploying their applications without having to worry about the underlying infrastructure. In this [blog post, Sai Madineni, a devops architect at AWS talks about the contributions we made to the project to enable integration with AWS Lambda.](https://aws.amazon.com/blogs/opensource/how-to-integrate-aws-lambda-with-spinnaker/)

**GluonCV**

GluonCV provides implementations of the state-of-the-art deep learning models in computer vision. It is designed for engineers, researchers, and students to fast prototype products and research ideas based on these models. There are some great demos and code samples in the project, and works nicely with Amazon SageMaker. 
[GluonCV version 0.6](https://github.com/dmlc/gluon-cv/releases) was released, and directly from the release notes:
>GluonCV v0.6.0 added more video classification models, added pose estimation models that are suitable for mobile inference, added quantized models for video classification and pose estimation, and we also included multiple usability and code improvements. 

**kubenav**

Have you ever had the urge to navigate your Kubernetes clusters via your mobile device? If so, then this [open source project, **kubenav**](https://github.com/kubenav/kubenav), is just the thing you have been looking for and it supports AWS EKS. Thank you [Rico Berger](https://ricoberger.de/) for creating this project. 

**ResourceSpace**

The ability to find useful open source projects that you can quickly download, setup and run was one of the ways that businesses started to understand and unlock the innovation potential of open source. So, I was delighted when I came across this post by [Code CG](https://codecg.com/) on setting up an open source project on [AWS to facilitate the management of digital assets](https://codecg.com/2020/02/26/setup-an-open-source-digital-asset-management-system-for-your-studio-on-aws-cloud/) (videos, pictures, etc). This is an easy to follow workflow that should get you up and running in no time. If this is too much effort for you, then one of the great things that AWS provides open source projects is the ability to make their software available to millions of customers via the [**AWS Marketplace**](https://aws.amazon.com/marketplace/search/results?x=0&y=0&searchTerms=resourcespace). There are two current listings for ResourceSpace on **AWS Marketplace**, so if you want to check this project out but want someone else to do the heavy lifting, check them out [here](https://aws.amazon.com/marketplace/search/results?x=0&y=0&searchTerms=resourcespace).

**Rhino Security Labs: Pacu**

A number of open source projects exist to help customers with security. Whether it is providing tooling to help with security testing, or projects that provide audit and reporting to help make sense of your environments, these projects can help you improve your overall security posture. [Rhino Security Labs Pacu](https://rhinosecuritylabs.com/aws/pacu-open-source-aws-exploitation-framework/) is such a project, and it also has a series of blog posts that help educate you on best practices for security. You can find the [Github repo here](https://github.com/RhinoSecurityLabs/pacu).

>**Note!**
>
>Depending on what AWS services you use, the security tooling that you use and what you plan to test, have a think whether you need to request authorization from Amazon beforehand. Determining whether or not you such authorization is needed is your responsibility. Read the [**AWS Customer Policy for Penetration Testing for more details**](https://aws.amazon.com/security/penetration-testing/).


### Partner spotlight

**Open source in Life sciences**

Hail is an open-source, python-based data analytics library with extra genomic data types and methods for working with genomic data. Hail sees wide use in the life sciences community, but is requires time to setup and manage. [AWS Partners like Privo](https://www.privoit.com/) are helping life science customers who want to analyse the vast amounts of genome data. Check out one of their webinars on how they are doing this [here](https://www.privoit.com/videos/scaling-up-genome-analysis), and check out the GitHub repo with everything you need to get started [here](https://github.com/privoit/emr-hail).


### AWS Open Source projects

**AWS MSK**

I shared Maikel Penz's [part 1](https://medium.com/@maikelpenz/building-a-kafka-playground-on-aws-part-1-setting-the-foundation-3065ecf51c19) of [Building a Kafka playground on AWS](https://medium.com/@maikelpenz/building-a-kafka-playground-on-aws-part-2-the-aws-architecture-f9190fa00bb7), so was delighted to see that he has posted [part 2](https://medium.com/@maikelpenz/building-a-kafka-playground-on-aws-part-2-the-aws-architecture-f9190fa00bb7). In this post, Maikel dives deep into the architecture and setting up the various components of the AWS MSK cluster.

**AWS Amplify - Have your say**

One of the great things that open source projects enable is transparency around the roadmap and of the design process. The [AWS Amplify team listed a Request for comment (RFC) for AWS Amplify UI components.](https://github.com/aws-amplify/amplify-js/issues/3279#issuecomment-589909938) Have a look and then provide feedback.

**Dart on AWS Lambda**

My colleague Sebastian Doell put together a nice blog on how you can use custom AWS Lambda runtimes to run Dart. I was new to Dart before I got involved with this, so if anything, you will learn what it is and how it is being used in some interesting open source projects like Flutter. Check out the [blog post, Introducing a Dart runtime for AWS Lambda](https://aws.amazon.com/blogs/opensource/introducing-a-dart-runtime-for-aws-lambda/).

**Running Quarkus on ECS**

During [FOSDEM Carlos Sanchez](https://fosdem.org/2020/schedule/event/progressive_delivery/) gave a great presentation during which I noticed he was using Quarkus in his demo, Croc Hunter. Quarkus is a really interesting project, my colleague Frank Munz wrote about it a while ago, [In the fast lane: Microservices with Quarkus and managed kubernetes](https://medium.com/swlh/microservices-on-kubernetes-quarkus-eks-e4fac1efbef5) and so happy that another colleague, **Sascha Mollering** has put together a new post on [Optimizing java applications for Amazon ECS with Quarkus](https://aws.amazon.com/blogs/field-notes/optimize-your-java-application-for-amazon-ecs-with-quarkus/). So three posts to get you bootstrapped onto this cool open source project.

**Using Grafana and InfluxDB with AWS IoT**

If you are passionate about internet of things, then there is a good chance you have already come across how to capture, store and visualise your telemetry data. Back in the day I used InfluxDB and Grafana in my homebrew projects, and these provided a solid and reliable base. A colleague **Syed Rehan** just wrote about how to use these two open source projects with [AWS IoT to visualise timestream data](https://aws.amazon.com/blogs/iot/influxdb-and-grafana-with-aws-iot-to-visualize-time-series-data/), and I will leave with Syed's own words:
>Visualizing time series data with AWS IoT Core, InfluxDB, and Grafana provide an effective architecture to generate, collect, persist, and develop rich real-time dashboards with IoT generated data

Go check this post out now.

**AWS CI/CD Pipeline**

Fresh new blog post from [**Jay Yeras** on the DevOps blog](https://aws.amazon.com/blogs/devops/identifying-and-resolving-vulnerabilities-in-your-code/) that uses a number of AWS CI/CD services together with **[Snyk](https://snyk.io/product/)** to help manage all the open source software you are using in your proeject. Most software uses open source components (according to various reports, this could be as high as 97% of projects based on an audit of enterprise IT done by BlackDuck) and so making sure you are able to manage this is critical - making sure you have known, good versions of the software, understanding the dependency trees, making sure you comply with your licensing obligations and other things are what tools like Snyk can help you with. This blog post walks you setting this up and signing up for a free account. It is worth noting that there are other providers that you can try out as well, and the AWS Marketplace is a good starting point. 


### Deep Dive of the week

**Firecracker**

Firecracker is the lightweight micro virtualisation manager (VMM) that is used to power AWS Lambda under the covers. In this blog post, [Firecracker: lightweight virtualization for serverless applications](https://blog.acolyer.org/2020/03/02/firecracker/), Adrian Colyer dives deep into the design of Firecracker looking through the [research paper](https://www.usenix.org/system/files/nsdi20-paper-agache.pdf) presented at the NSDI'20 event 



### Tweet of the week

This week’s tweet is from [Devon (@devonzuegel)](https://twitter.com/devonzuegel) and it is an interesting one; when applying for a new role in a company, would how that company supports, contributes or accepts open source be a factor for you considering that company/role? Quite a few discussions already, [so join in the debate](https://twitter.com/devonzuegel/status/1232746077725458432?s=11) and data points.


### Discovery of the week

Every now and then you find a gem of a project. Something that you think, wow this is really going to save a lot of effort or solve a really annoying problem. So, via Reddit, I found this really cool open source project, [LambStatus](https://lambstatus.github.io/). What does it do I can hear you all crying out. I remember back in the day when I would ask developers/architects to include test harness' within their application so we could use tools like ipMonitor and BMC to track whether applications were healthy, degraded or just failing. So LambStatus enables you to build and maintain status pages with the least effort and utilizing the efficient cost model of AWS Lambda. Check out the [repo here](https://github.com/ks888/LambStatus).

---
### Do you use AWS and love open source? 

Do you have some content you want to share with a broader audience? We are always looking for guest content for the AWS Open blog. Please get in touch (via comments below) and I would love to speak with you about what you are doing in open source. We are always looking for interesting new content.

### We are hiring

We are hiring, so if you love open source, then why not check out the current openings. We would love to hear from you and if you want to chat and ask me anything, connect to me via LinkedIn or Twitter and always happy to talk.

[Open Source jobs at Amazon and AWS](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) - scroll to bottom, on left.

### Stay in touch with open source at AWS

I hope this summary has been useful. I have looked for all the session videos that have been uploaded to date, but if I have missed anything, please get in touch and I will update this summary. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on @AWSOpen.

--

## Get in touch

I am always looking out for new and interesting stories, projects, demos and ideas where open source meets AWS. Get in touch, I would love to hear from you.
