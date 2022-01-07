---
title: 'AWS open source news and updates #6 - keep up to date with everything that is happening.'
date: '2020-02-10'
tags : [ oss-newsletter ]
---
With still so much to digest post FOSDEM, SustainOSS and CHAOSS, this weeks updates are a little more lightweight and easy to consume. I am going to work on some tutorials/coding posts so would be interested (use comments) on what open source AWS projects you would like to see material on.

### Modernising with open source

Following on from the previous post on the essential open source tools for serverless, I came across this blog post by Matt Billock called "[Essential Open Source Serverless Tools](https://lumigo.io/blog/essential-open-source-serverless-tools/)" - it is a great reference guide, so check it out. 

And whilst I am talking about that previous post, you can watch this recording of the session ->
[AWS Community Day Nordics 2020 - Essential open source tools for a serverless developer](https://www.youtube.com/watch?time_continue=7&v=ausu6z4bcI8&feature=emb_logo) - **Yan Cui (@theburningmonk)**_Recorded Friday, 31 January 2020 at Nalen in Stockholm._

### Security with open source

Ephemeral email addresses to protect your inbox, sounds interesting right? Well read this post on ["How I built Heimdall, an open source personal email guardian" by Fabian Terh](https://medium.com/swlh/how-i-built-heimdall-an-open-source-personal-email-guardian-68e306d172d1) and then check out his code and implement this for yourself.

Security is job zero and everyones job, and there are many useful open source projects that can help you automate security tasks. [In this project by BishopFox, they created a tool called Dufflebag](https://know.bishopfox.com/research/dufflebag-uncovering-exposed-ebs?utm_campaign=190900_Research_Dufflebag_Influencers_Global&utm_content=114956258&utm_medium=social&utm_source=twitter&hss_channel=tw-1376153113) that helps you to identify potential information that might be exposed. [The project repo is here](https://github.com/bishopfox/dufflebag?__hssc=24978341.1.1580911422477&__hstc=24978341.36c1e0978fe852cb52f7cf107b288c6d.1580911422477.1580911422477.1580911422477.1&__hsfp=155284130&hsCtaTracking=2dcbd7ca-d02e-4b02-95d7-974a6e29ed84%7Ce2150983-d952-4b19-8443-754af9e42003).

### AWS related Open Source projects

**AWS CDK under the covers**

Have you ever wondered what happens under the covers when you are using AWS CDK? - [Massimo shares his first experiences.](http://www.it20.info/2020/02/my-first-cdk-experience-under-the-hood/).

**AWS CodeBuild**

GitHub Actions are a cool feature that allows you automate workflows within Github (you can see some cool AWS related Actions [here](https://github.com/aws-actions)). If you are using AWS CodeBuild, then this action might be of interest to you. It runs a AWS CodeBuild project as a step in a GitHub Actions workflow job. [The action builds the CodeBuild project, collects the build logs, and prints them as they are written](https://github.com/aws-actions/aws-codebuild-run-build). This allows you to share logs of the build process with your external community on GitHub for a better community experience.

**AWS IoT and ESP32**

One of my colleagues [Moheeb Zara](https://twitter.com/virgilvox) has been having way too much fun with the M5stick dev kits. He has put together some [really cool workshops](https://github.com/aws-samples/aws-iot-esp32-arduino-examples/tree/master/m5stick-examples) for you to bootstrap your experimentation. If you want to get hold of these M5stick dev kits, then you can get them from [here](https://m5stack.com/collections/m5-core/products/m5stickc-development-kit-with-hat) or [here](https://www.adafruit.com/product/4289?gclid=CjwKCAiA1L_xBRA2EiwAgcLKA_XNkkETIgRMBl4ifk777Y03jZoNNBYzmzwckhZ59c5mtGW32FxZwRoCRrcQAvD_BwE). You can also get these from Amazon.

**FreeRTOS**

[FreeRTOS blog post on The New Stack](https://thenewstack.io/why-aws-support-for-freertos-is-good-for-open-source/) takes a look at AWS support for the FreeRTOS open source project. If you want some good data points on why AWS and open source makes sense, then this post talks about how we are approaching security in this project. Read on...

**AWS Amplify**

If you have heard about AWS Amplify, but want to know more then you will love this curated list of resources to help you get started. [AWEsome Amplify](https://github.com/dabit3/awesome-aws-amplify/blob/master/README.md) has everything; workshops, loads of tutorials and videos and example projects. 

### Podcast of the week

[Podcast of the week - Grey Beards on Storage](https://silvertonconsulting.com/gbos2/2020/02/07/097-greybeards-talk-open-source-s3-object-store-with-ab-periasamy-ceo-minio/?utm_content=115614286&utm_medium=social&utm_source=twitter&hss_channel=tw-3017977255) - if you have not heard of MinIO, then this is an open source project that provides storage tools which are S3 API compatible.

### Tweets of the week

Well, not sure if this is allowed, but this time it is one of mine. If you are using [CentOS on AWS](https://twitter.com/094459/status/1225521488666726407) and want to have faster updates and reduce your transfer costs you need to read the post.


---
### Do you use AWS and love open source? 

Do you have some content you want to share with a broader audience? We are always looking for guest content for the AWS Open blog. Please get in touch (via comments below) and I would love to speak with you about what you are doing in open source. We are always looking for interesting new content.

### We are hiring

We are hiring, so if you love open source, then why not check out the current openings. We would love to hear from you and if you want to chat and ask me anything, connect to me via LinkedIn or Twitter and always happy to talk.

Here is a sneak at some of the current open roles;

Open roles in open source include:

* [Principal Evangelist, Open Source](https://www.amazon.jobs/en/jobs/990374/principal-evangelist-open-source)
* [Senior Product Manager, .NET libraries and open source](https://www.amazon.jobs/en/jobs/1043043/senior-product-manager-net-libraries-and-open-source) – Bay Area
* [Senior Software Development Engineer, Firecracker] (https://www.amazon.jobs/en/jobs/1002846/senior-software-dev-engineer-firecracker) – Bucharest, Romania 
* [Manager, Open Source Program Office] (https://www.amazon.jobs/en/jobs/990377/manager-open-source-program-office) – Seattle
* [Senior Software Development Engineer, Open Source Programs] (https://www.amazon.jobs/en/jobs/914312/senior-software-development-engineer-open-source-programs) – Seattle
* [Software Development Engineer, Open Source Programs] (https://www.amazon.jobs/en/jobs/908711/software-development-engineer-open-source-programs) – Seattle 
* [Open Source Engineer] (https://www.amazon.jobs/en/jobs/998335/open-source-engineer) – Seattle
* [Principal Specialist Solutions Architect - Open Source Software] (https://www.amazon.jobs/en/jobs/963278/principal-specialist-solutions-architect-open-source-software-oss) – Palo Alto
* [Partner Solutions Architect - Linux] (https://www.amazon.jobs/en/jobs/1014503/partner-solutions-architect-linux) – Seattle
* [Partner Solutions Architect - Linux] (https://www.amazon.jobs/en/jobs/1008397/partner-solutions-architect-linux) – Seattle
* [Principal Product Manager] (https://www.amazon.jobs/en/jobs/836429/principal-product-manager-for-a-new-aws-service-amazon-msk), [Amazon MSK] (https://aws.amazon.com/msk/) – Seattle
* [Principal Developer Advocate (EU)] (https://www.amazon.jobs/en/jobs/987815/principal-developer-advocate-eu), [Amazon MSK] (https://aws.amazon.com/msk/) – Cambridge, UK 
* [Software Development Engineer] (https://www.amazon.jobs/en/jobs/977448/software-development-engineer) [AWS Cloud Development Kit] (https://aws.amazon.com/cdk/) – Seattle
* [Software Development Engineer] (https://www.amazon.jobs/en/jobs/946512/software-development-engineer) [AWS Cloud Development Kit] (https://aws.amazon.com/cdk/) – Seattle
* [Software Development Engineer] - [AWS Lambda ](https://www.amazon.jobs/en/jobs/789084/software-development-engineer-aws-lambda) – Seattle 
* [Senior Software Development Engineer, Distributed Systems, Amazon EMR] (https://www.amazon.jobs/en/jobs/759159/senior-software-development-engineer-distributed-systems-amazon-emr) – New York

and many many more....

[Open Source jobs at Amazon and AWS](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) - scroll to bottom, on left.

### Stay in touch with open source at AWS

I hope this summary has been useful. I have looked for all the session videos that have been uploaded to date, but if I have missed anything, please get in touch and I will update this summary. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on @AWSOpen.
