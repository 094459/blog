---
title: 'AWS open source news and updates #8'
date: '2020-02-24'
tags : [ oss-newsletter ]
---
Another episode of the open source news and updates from AWS, and in this installmant I talk a little about the recent trip to Lagos, Nigeria where I talked about why developers should care about open source at the Open Source Festival, as well as more of the usual updates from around the AWS services catalog as well as some interesting customer projects.

### Open Source Fesitval - Lagos, Nigeria

Last week I was invited to speak at the Open Source Festival in Lagos, Nigeria. You can follow up the events by checking out the [hashtag of tweets here, **#oscafest**](https://twitter.com/hashtag/oscafest?src=hashtag_click&f=live). I did a couple of sessions about why open source matters to developers and a really fun session about the Robotics Operating System (ROS) which really got the local developers interest.

It was good to see the diversity of sessions, and also surprising (in a good way) that PHP was one of the dominant technologies that developers were most passionate about. There was a lot of love for PHP, and I was constantly being asked about PHP support for the various technologies I was talking about.

I met some amazing builders who had come along to find out more about open source. Here are a few of the video interviews I did (they are all short)

* [Amalla,](https://twitter.com/094459/status/1230497175001608193) front end developer
* [Promise](https://twitter.com/094459/status/1230500355710103557), embedded software developer
* [Agiri](https://twitter.com/094459/status/1230493558894997506), open source developer and advocate

One of the bulders, [Emmanuel Martins](https://twitter.com/emmamartinscode), was looking to promote his open source python MVC framework, **Pytonik**. Specifically he is looking to get more contributors. I asked him to say a few words about his project:
>Pytonik is a python framework built to enhance web development, also helps web developers to build more apps with less https://codes.It uses expressive architectural patterns, structured on Model View Controller (MVC) and bundles of component to reuse while deploying the framework.

>The purpose of this project is to change the way python developers build or create web applications. Pytonik improves web development and eradicates vulnerabilities, it will attract more developers to the python community, or this will increase the number of developers activities for both old and new in the python community as well as capturing companies' attention.

>In the python world, web development has never been easy, pytonik’s vision is to make development easier and faster. 

>With pytonik, python developers will have a comfortable platform to improve their skills, which will increase job opportunities both freelancing and full-time jobs.  More so, problems will be solved in our society, pytonik gives developers the flexibility and freedom to turn their ideas into an amazing projects, hence achieving their set goals.

Check out the project on PyPi [here](https://pypi.org/project/pytonik/). I also did a short interview with him which you can check out [here](https://twitter.com/094459/status/1230499571081543680).


So thank you to the team that put together this three day event. It is not easy to sustain the level of energy to bring this to life, so hats off to the organisers and I would like to personally thank [Samson Goddy](https://twitter.com/Samson_Goddy) for all the time and dedication he put in to make this a success. Follow him on Twitter and LinkedIn to make sure you keep up to date with all the open source stuff happening in the region.

### Interesting open source projects

First up is [Varna, an open source project that allows you to use Event Query Language (EQL) to query CloudTrail logs](https://github.com/endgameinc/varna). If that was not already cool enough, its implemented as a serverless solution using AWS Lambda. The github project contains installation instructions, but who knows, maybe this might make it to the Serverless Application Repository some time (hint hint!)

I have previous talked about the **Metaflow** project that Netflix released. Last week a new  [blog post by Ryan Brady](https://www.experoinc.com/post/metaflow-rapid-reaction) had a look at this. It is a good post to understand how Metaflow fits into your data science and machine learning workflow.

### AWS related Open Source projects

**AWS RoboMaker**

In this blog post [Building a ROS-Application CI Pipeline with AWS RoboMaker](https://aws.amazon.com/blogs/robotics/building-a-ros-application-ci-pipeline-with-aws-robomaker/), **Jeremy Wallace** and **Andrew Lafranchise** talk and demonstrate how to bring modern application development techniques to the business of developing Robots.

**FreeRTOS**

FreeRTOS is an open source, real-time operating system for microcontrollers that makes small, low-power edge devices easy to program, deploy, secure, connect, and manage. AWS IoT Device Management makes it easy to securely register, organize, monitor, and remotely manage IoT devices at scale, and provides an OTA Update Manager service to securely create and manage updates across a fleet of devices. The ability to perform secondary processor over-the-air (OTA) updates is just as critical as updating the connectivity processor. Find out more about how to do this in this blog post, [How to perform secondary processor over-the-air updates with FreeRTOS](https://aws.amazon.com/blogs/iot/how-to-perform-secondary-processor-over-the-air-updates-with-freertos/) by **Manish Talreja**.

**AWS Fargate**

[Massimo re Ferre](https://twitter.com/mreferre) has been busy again, this time creating a Container insights custom dashboard; in his own words...
>The metrics collected by Containers Insights for ECS (which includes support for Fargate) isn't granular enough to allow tracking single tasks. The metrics available (i.e. CpuReserved, CpuUtilized, MemoryReserved, MemoryUtilized) are all aggregated and averaged at the task definition family level. The assumption here is that all running tasks within the same task definition family are only onced once and when they scale out they are evenly balanced (so averaging their configuration and consumption is acceptable). This holds true in many situations but it doesn't always happen. Here are some scenarios that challenge that assumption:

>* The same task definition being used for both dev and prod environments: often times the load on development environments is much lower than that of production environments. Averaging these inputs may provide a balanced number which doesn't allow to capture if the dev environment is way under-utilized and/or if the prod environment is way over-utilized
* The same task definition being used for batch type of workloads with different resource consumption profiles. Again, averaging these inputs may provide a misleading number which doesn't allow to capture the need to have different task definitions for different workloads profiles
* There could be situations where the running tasks part of an ECS service behind a load balancer are not evenly utilized. This could be because of a particular application pattern or because of some configuration issues. This dashboard isn't meant to be a problem determination tool but it could be a way to spot problems other than inefficiencies

>How can we go one level down deep from the task definition family into each single running Fargate task? Enter the Fargate right sizing dashboard.

Check out the [repo here.](https://github.com/mreferre/container-insights-custom-dashboards/tree/master/fargate-right-sizing)


**Apache Flink**

A new blog post by **Steffen Hausmann** ([Streaming ETL with Apache Flink and Amazon Kinesis Data Analytics](https://aws.amazon.com/blogs/big-data/streaming-etl-with-apache-flink-and-amazon-kinesis-data-analytics/)) this week that looks at how to use Apache Flink as a basis for sophisticated streaming extract-transform-load (ETL) pipelines. Apache Flink is a framework and distributed processing engine for processing data streams. AWS provides a fully managed service for Apache Flink through Amazon Kinesis Data Analytics, which enables you to build and run sophisticated streaming applications quickly, easily, and with low operational overhead.

This post contains a stack you can launch so you can experiment with yourself.

**AWS CDK**

I frequently share posts about the AWS Cloud Development Kit (CDK) but this time I want to share a couple of posts from [Alexander Fortin](https://cv.l3x.in/), who has a couple of excellent deep dive posts that you should check out.

* First, an [introduction to AWS CDK using a real life example of using AWS CDK with AWS Lambda and Amazon API Gateway](https://a.l3x.in/2020/02/04/migrating-from-terraform-to-cdk.html)
* The second, is a [fun tutorial on automating social media updates with AWS Lambda, Amazon SNS and AWS CDK](https://a.l3x.in/2020/02/17/serverless-publish-to-multiple-social-media.html).

As he puts in the posts, he is lookinf for feedback. Did you agree with his pros/cons? How would you do this different? Have you used this to create something else? Make sure you share with Alexander.

Thank you Alexander.

### Deep Dive

This weeks deep dive, in a blog post, [Matt Asay talks about Open Source and sustainability](https://www.techrepublic.com/article/new-study-throws-the-open-source-sustainability-debate-into-question/). It is a short piece, but well worth reading. What do you think? Share your thoughts below in the comments, or reach out directly to Matt via Twitter.


---
### Do you use AWS and love open source? 

Do you have some content you want to share with a broader audience? We are always looking for guest content for the AWS Open blog. Please get in touch (via comments below) and I would love to speak with you about what you are doing in open source. We are always looking for interesting new content.

### We are hiring

We are hiring, so if you love open source, then why not check out the current openings. We would love to hear from you and if you want to chat and ask me anything, connect to me via LinkedIn or Twitter and always happy to talk.

[Open Source jobs at Amazon and AWS](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) - scroll to bottom, on left.

### Stay in touch with open source at AWS

I hope this summary has been useful. I have looked for all the session videos that have been uploaded to date, but if I have missed anything, please get in touch and I will update this summary. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on @AWSOpen.