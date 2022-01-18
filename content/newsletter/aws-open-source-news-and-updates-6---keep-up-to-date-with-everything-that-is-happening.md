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

### Stay in touch with open source at AWS

I hope this summary has been useful. I have looked for all the session videos that have been uploaded to date, but if I have missed anything, please get in touch and I will update this summary. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on @AWSOpen.
