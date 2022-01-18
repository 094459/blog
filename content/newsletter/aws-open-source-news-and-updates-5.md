---
title: 'AWS open source news and updates #5'
date: '2020-02-03'
tags : [ oss-newsletter ]
---
So, hello February and welcome to open source updates and news at AWS #5, the FOSDEM edition. Sadly I was unable to attend due to my passport being held to get a VISA, but I have managed to speak with a number of attendees and get some updates from the event.

### CHAOSCON and SustainOSS

The day before FOSDEM we had Sustain Open Source, an event thinking about the sustainability of open source software. Well worth checking out the video shorts on the web site to find out more.

The long term sustainability of open source projects is critical for everyone, and one of the ways we are trying to help is through our AWS promotional credits for open source projects. Launched back in October, the [AWS promotional credits for open source projects](https://aws.amazon.com/blogs/opensource/aws-promotional-credits-open-source-projects/) has received lots of interest so keep a look out on the AWS open souce blog for news.

You can find out more about how the Python Software Foundation thinks about open source sustainability (amongsts many other things) on this podcast with Ewa Jodlowska. If you have not checked out the Sustain podcast, then I highly recommend it. From their site "Sustain is a podcast that showcases resources and systems so as to reward open source contributions." At minute 34, they talk about some of their favourite open source projects. If anyone can tell me (use comments) what the python project is, as I couldnt not transcribe that. I did like however the [FerOSS Thanks project](https://github.com/feross/thanks) - give back to those projects you are using and who have a donations page.

The final piece around sustainability of projects is how projects themselves are able to attract and make it  simple for contributors. This was a [poll](https://twitter.com/094459/status/1222187362362544129) that I created on Twitter, but one of the comments was from Mike Fiedler led me to https://www.codetriage.com/what which tries to help here. From the about page;
> You want to contribute to Open Source, great! But how do you get started? CodeTriage helps by picking a handful of open issues and delivering them directly to your inbox. After you sign up for CodeTriage, you pick the repos you want to help with, and we periodically send you issues. If you get busy we have an algorithm that helps to back off the issue load so that you don't get overwhelmed.

Check it out [here](https://www.codetriage.com/what)

On Friday I enjoyed following the [CHAOSScon](https://twitter.com/hashtag/CHAOSScon?src=hashtag_click) tweets covering all things metrics and measurement in open source communities. Why do we need to do this? We need to understand the health of projects, and **[George Link](https://twitter.com/GeorgLink)**  [ provides a slide with a few reasons why](https://twitter.com/tom_mens/status/1223166614612467713/photo/1). Check out the schedule which has a list of some of the [presentations here](https://chaoss.community/chaosscon-2020-eu/).

This tweet thread is required reading. [The Seven Deadly Sins of Open Source Communities delivered by Brian Proffitt from Red Hat.](https://twitter.com/yoyehudi/status/1223280613974855685)

### FOSDEM weekend

[Sunday](https://fosdem.org/2020/schedule/day/sunday/) and [Saturday](https://fosdem.org/2020/schedule/day/saturday/) was full of sessions, some of which were available via livestream but you can now catch many them on playback.

Some specific sessions that I want to call out however, are the following:

* Really enjoyed the session, and @fossygrl and @DuaneOBrien made a great point about the potential distraction of lots of different things being called out as sustainability. [Here is a link to the session (no recording, but slides available)](https://fosdem.org/2020/schedule/event/foss_sustainability_issues/)
* Building confidence and overcoming insecurity session from 
@jeffmcaffer - [link to session, no recording sadly](https://fosdem.org/2020/schedule/event/building_confidence_in_security/)
* [The pool next to the ocean: How to bring Open Source skills to more people](https://fosdem.org/2020/schedule/event/innersource_skills/) - an interesting look on using innersource as a way to teach open collaboration skills.
* [Building Community for your Company's OSS Projects](https://fosdem.org/2020/schedule/event/corposscommunity/), a great look at how to approach building community. This session was recorded, so defo check this out.

There were many more great sessions, so check out my Twitter feed or even better the #FOSDEM hashtag.

  


**[HawkTracer](https://www.hawktracer.org)**, is low-overhead instrumentation-based profiler built at Amazon Video for platforms with limited capabilities. It's written in C but can be used almost with any other language (we've successfully used it with JavaScript, LUA, Python and Rust). It's highly extensible (at compile time) and portable so it can be run on almost any embedded device. [You might have caught Marcin Kolny during his presentation](https://fosdem.org/2020/schedule/event/debugging_hawktrace/) of HawkTracer during Fosdem. If not, check out the project home page and [repo](https://github.com/hawktracer).

### AWS related Open Source projects

**AWS Elastic Beanstalk**

Following on from the AWS Elastic Beanstalk CLI that I talked about in #2, the team has now published the [roadmap on the github project page](https://github.com/aws/elastic-beanstalk-roadmap/projects/1).

This is an experiement from the service team, and they have [provided an overview, how to get involved and an FAQ](https://github.com/aws/elastic-beanstalk-roadmap). 

**AWS Organisations - devOps**

If you love AWS Organisations, then this open source project is for you. Apply IaC (Infrastructure as Code) for AWS Organisations. The project is well documented and contains some examples, so why not give it a go. [AWSOrganisationFormation is the name, thanks Olaf Conijn](https://github.com/OlafConijn/AwsOrganizationFormation) for your efforts.


### Snippets of the week

**Is there anything left to invent...?**

Do you think the pace of new technology is slowing down? Are there fewer new interesting technologies emerging from open source incubating repositories? Check out this [tweet from Dvir Volk](https://twitter.com/dvirsky/status/1223326166146174976) and join in the conversation.

**AWS Chalice and AWS CDK**

Great post this week on the [AWS Developer Blog on deploying AWS Chalice applications using AWS Cloud Development Kit (CDK)](https://aws.amazon.com/blogs/developer/deploying-aws-chalice-application-using-aws-cloud-development-kit/), both great open source projects from AWS.



### Modernising with open source

In this [blog post, Matt Asay talks about how Globe Telecom ("Globe")](https://aws.amazon.com/blogs/modernizing-with-aws/how-globe-telecom-is-modernizing/) were able to modernise with open source. Read the post to find out how they moved to open source databases to increase agility, move faster and scale faster.

Whilst on the topic of data, have you heard of or use **[deequ](https://github.com/awslabs/deequ)**? This open source project from Amazon is a library built on top of Apache Spark to help with defining unit tests for data. There are easy to follow instructions with examples, so if you need help with your data unit test, why not give it a go.

Many customers are building modern applications using AWS Lambda and moving to a serverless operational model to remove all the undifferentiated heavy lifting and focus on writing just business logic. Fresh from the #awscommunityday , **[Yan Cui](https://twitter.com/theburningmonk)** shared his list of [Essential open source tools for the serverless developer](https://www.slideshare.net/theburningmonk/essential-open-source-tools-for-serverless-developers).

### Building consensus in open source communities

Building consensus among technology vendors is an important objective of any well run open source project. This b[log post by Docker](https://www.docker.com/blog/community-collaboration-on-notary-v2/) showed a peek into how this works, and is an interesting look at the work being done on the CNCF Notary project. Find out more about what this project is and why it is important, as well as how vendors are coming together to make this work.

---
### Do you use AWS and love open source? 

Do you have some content you want to share with a broader audience? We are always looking for guest content for the AWS Open blog. Please get in touch (via comments below) and I would love to speak with you about what you are doing in open source. We are always looking for interesting new content.

### Stay in touch with open source at AWS

I hope this summary has been useful. I have looked for all the session videos that have been uploaded to date, but if I have missed anything, please get in touch and I will update this summary. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on @AWSOpen.

### We are hiring

We are hiring, so if you love open source, then why not check out the current openings. We would love to hear from you and if you want to chat and ask me anything, connect to me via LinkedIn or Twitter and always happy to talk.

[Open Source jobs at Amazon and AWS](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) - scroll to bottom, on left.