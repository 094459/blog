---
title: 'AWS open source news and updates #2 '
date: '2020-01-17'
tags : [ oss-newsletter ]
---
This is update #2 of open source at AWS ([#1 here](https://dev.to/aws/open-source-update-1-5d4o)), the regular update where I will share updates and interesting content from stuff we are doing as well as sharing interesting projects our customers are working on.

This post has a bit of a Security theme, with a number of interesting open source related projects and content. But dont worry, there is lots more cool stuff on machine learning and AWS open source projects too, So lets dive straight on in.


### AWS service related open source updates

[Automating security using step functions](https://aws.amazon.com/blogs/compute/orchestrating-a-security-incident-response-with-aws-step-functions/) is a cool post and repo that shows how you can automate security response using AWS Step Functions.

Follow Ben Smith, one of the developer advocats for serverless.

If you a container fan, love Kubernetes, then you will love this. We announced the beta release of the [Amazon EKS CSI driver for fsx lustre.](https://aws.amazon.com/about-aws/whats-new/2019/12/amazon-eks-announces-beta-release-amazon-fsx-lustre-csi-driver/) Check out the repo at this link -  
https://github.com/kubernetes-sigs/aws-fsx-csi-driver

When I go and speak at events, I always find customers who use and love AWS Elastic Beanstalk. I was very happy to see that the team have open sourced the [AWS Elastic Beanstalk CLI](https://aws.amazon.com/about-aws/whats-new/2020/01/aws-elastic-beanstalk-command-line-interface-now-open-source/)
Check out the github repo at [https://github.com/aws/aws-elastic-beanstalk-cli](https://github.com/aws/aws-elastic-beanstalk-cli)

Finally, a cool little project from one of my colleagues. One of the things I love most about the open source community is the small projects they release that provide useful functionality that you will find useful. This one is a great little project that allows you to both construct and deconstruct ARNs. https://github.com/mhausenblas/arn.services

Thanks Michael, and be sure to follow him on [github](https://github.com/mhausenblas) and via [Twitter](https://twitter.com/mhausenblas).

### Machine Learning

**AutoGluon**

Building machine learning apps that rely on such data isn’t an easy task. For example, developers need to know how to tune the “hyperparameters” that represent the choices made when constructing an AI model. They also need to grapple with issues such as neural architecture search, which enables them to find the best architecture design for their machine learning models.

AutoGluon automates many of these complicated tasks and can create a new machine earning model with as little as three lines of code by automatically tuning choices within default ranges that are known to perform well for a given task. All the developer has to do is specify how quickly they want their model to be trained, and AutoGluon will come up with the strongest model in the given timeframe.

https://www.amazon.science/amazons-autogluon-helps-developers-get-up-and-running-with-state-of-the-art-deep-learning-models-with-just-a-few-lines-of-code

### Open Source projects of the week

This project provides a bootstrap framework for a complete offensive, defensive, reverse engineering, & security intelligence tooling in a private research lab using the AWS Cloud.It simply provides a researcher with a disposable offensive / defensive AWS-based environment in less than 5 minutes.

https://haxf4rall.com/2019/12/14/cyberrange-the-open-source-aws-cyber-range/

A [list of useful tools](https://github.com/toniblyx/my-arsenal-of-aws-security-tools) that you can use to ensure your environments are as secure as they should be. Thank you Tony for sharing this.

More security stuff, this time from [design99](https://99designs.com.au/tech-blog/blog/2015/10/26/aws-vault/) a neat project focused around protecting credentials on local developer laptops/machines - check out the repo here - https://github.com/99designs/aws-vault/releases/tag/v5.0.0/

Final security open source project, policy sentry from Salesforce. This project helps users to create least-privilege IAM policies in a matter of seconds. Read the [blog post](https://engineering.salesforce.com/salesforce-cloud-security-automating-least-privilege-in-aws-iam-with-policy-sentry-b04fe457b8dc) and then check out the project - https://github.com/salesforce/policy_sentry/ 

**Bug Bounty for open source projects**

Interesting new concept; Huntr which is a bug bounty program specifically for open source projects. You need to sign up via the link, and it opens up on Feb 1st. One to check out for sure. There are nearly 1000 people on the wait list when I signed up, so it is going to be interesting to see this when it launches.

https://huntr.dev/

**Machine Learning**

Cortex caught my eye this week. Not had a chance to kick the tyres, but it looks pretty slick. You can read the [blog post](https://medium.com/pytorch/how-to-build-production-software-with-pytorch-9a8725382f2a) and then head over to the github repo, detailed docs and some great examples - https://github.com/cortexlabs/cortex


### Tweets of the week

I enjoyed this [tweet from Pablo Saavedra](https://twitter.com/gasaapa/status/1217225651327045632) sharing a medium post by Sedat Kapanoglu that takes a light hearted look at how programming and development has evolved over the past 20 years, including open source. It made me smile and was a good read at the end of the day. 

And this one from [@chrismunns]() caught my eye. New version of SAM ([v1.20.0 release](https://github.com/awslabs/serverless-application-model/releases/tag/v1.20.0)) and check out the 26 community contributors for this project. 

### Deep Dive topic - the history of open source

Kind of related to this was a video that someone shared with me recently about the history of [Gnu, Linux and Free and Open Source software](https://www.youtube.com/watch?time_continue=3&v=vjMZssWMweA&feature=emb_logo). It is a bit of an epic at a little over two hours, so have the pop corn ready, but I found it very enjoyable and provided some great moments. I especially loved Eric Raymonds opening, so check this out.


### Stay in touch with open source at AWS

I hope this summary has been useful. I have looked for all the session videos that have been uploaded to date, but if I have missed anything, please get in touch and I will update this summary. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on @AWSOpen.

### We are hiring

We are hiring, so if you love open source, then why not check out the current openings. We would love to hear from you and if you want to chat and ask me anything, connect to me via LinkedIn or Twitter and always happy to talk.

[Open Source jobs at Amazon and AWS](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) - scroll to bottom, on left.