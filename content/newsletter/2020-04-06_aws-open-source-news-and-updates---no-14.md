---
title: 'AWS open source news and updates - No. 14'
date: '2020-04-06'
tags : [ oss-newsletter ]
---
## April 6th - Instalment #14

Episode 14, and yet more abundance of open source to share with you. Fourteen is an interesting number, and very quickly googling this, I learnt that the number fourteen has a number of interesting facts: the moon waxes for fourteen days and then wanes for fourteen days, a golf player can have no more than fourteen clubs in their caddy, it is the atomic number for silicon and for those who enjoy their open source with the literature, 14 is also the number of lines in a sonnet. So, I am hoping you will equally enjoy this sonnet of open source goodness.

**Job Highlight**

Occasionally I like to highlight jobs at AWS that people in the open source community might be interested in, and this is one such posting. Read the post, but in this role, you will be positioning AWS as a thought leader in related open source projects by collaborating and influencing the open source community and contributing to open source projects. 

[Senior Software Design Engineer - AWS Observability](https://www.amazon.jobs/en/jobs/1092234/senior-software-design-engineer-aws-observability)

Feel free to contact me directly if you want any insights or further information about the role or working at AWS.

### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created.

So thank you Johnathan Henson (@JonathanMHenson), Optum, F-Secure Labs, Shashank Prasanna, TheOdo UK (@SlsDevTools), Lorenzo Vanthillo (@LorenzVth), Philip Basford (philipbasford), Luis Frazati and Alix Axel. 

### Latest from open source projects


###Security

**awspx**

**awspx** is a visualising aid to help you understand and manage effective access and resource relationships in your AWS environments. [This blog post](https://securityonline.info/awspx-visualizing-aws-environments/) outlines how to get started with the project, but you can find the source code at the [FSecureLabs Github repo](https://github.com/FSecureLABS/awspx). From the readme;

>awspx is a graph-based tool for visualising effective access and resource relationships within AWS. It resolves policy information to determine what actions affect which resources, while taking into account how these actions may be combined to produce attack paths. Unlike tools like Bloodhound, awspx requires permissions to function. It is not expected to be useful in cases where these privileges have not been granted.

![Video in action](https://github.com/FSecureLABS/awspx/blob/master/images/awspx.gif?raw=true)

**dce**

What does 'dce' stand for? Disposable Cloud Environments. This is a great open source project that you should have a look at if you want to implement (or lease) temporary cloud environments. What I like about this project is that it allows you to:

>At the end of the lease, or if the lease's budget is reached, the account is wiped clean and returned to the account pool so it may be leased again.
>

The project is [well documented](https://dce.readthedocs.io) so read more on the [README.md at the GitHub repository](https://github.com/Optum/dce/blob/master/README.md). Great project from [Optum](https://github.com/Optum), make sure you check out their other projects too.


### Serverless

**sls-dev-tools**

There are many open source tools that help you understand what is going on in your serverless applications throughout their lifecycle. I try and share these on this newsletter as I find them, and whilst I have tweeted about [sls-dev-tools](https://theodo-uk.github.io/sls-dev-tools/) project before, am including it in this weeks round up so that others can check it out in case you missed this.

I love the single plane of glass UI that sls dev tools provides you, so take a look at this screen shot and if that piques your interest, head on to the [GitHub repository for sls dev tools](https://github.com/Theodo-UK/sls-dev-tools).

![sls dev tools console
](https://github.com/Theodo-UK/sls-dev-tools/blob/master/demo.png?raw=true)

**Grabbing screenshots during tests - serverless style**

Interesting thread on HackerNews about how to create tests using AWS Lambda let to some interesting responses and of course, open source projects.

The first one is from [Luis Frazati, and this project is called Chromda](https://github.com/luisfarzati/chromda) which is an AWS Lambda function that captures screenshots of websites. Your input event has a payload of the time and the url you want to grab a screenshot of, and you will receive a response if successful of the screen image delivered via a URL to an S3 bucket.

The second project is from Alix Axel, is an AWS Lambda layer that allows you to have available in your functions, the latest release of Puppeteer which you can then use in your function. Grab the project via the [Chrome-aws-lambda gitHub repository](https://github.com/alixaxel/chrome-aws-lambda).

Thank you [Luis](https://github.com/luisfarzati) and [Alix Axel](https://github.com/alixaxel).

### DevOps

Very happy that Philip Basford from Inawisdom combined a couple of my favourite things in his [blog post, 'Infrastructure as code and code quality'](https://www.inawisdom.com/amazon/infrastructure-as-code-and-code-quality/) where he combines a number of AWS services via AWS CDK to deploy an instance of SonarQube. For those new to SonarQube, it is a static analysis tool that is well proven and well used, so am guessing this is going to be of interest to lots of folk.

Thanks Philip for taking the time of writing this up and [sharing your gitHub repository](https://www.inawisdom.com/amazon/infrastructure-as-code-and-code-quality/).


### AWS Open Source projects

**Open Distro for Elasticsearch**

Open Distro for Elasticsearch 1.6.0 is now available for download and use. [Alolita Sharma announced this release via a blog on the Open Distro for Elasticsearch blog](https://opendistro.github.io/for-elasticsearch/blog/odfe-updates/2020/04/Open-Distro-for-Elasticsearch-1.6.0-released/) and this version consists of Elasticsearch 7.6.1, Kibana 7.6.1 as well as plugins for alerting, index management, performance analyser, security, SQL and machine learning with k-NN. Also included are a SQL JDBC driver and PerfTop, a client for Performance Analyser.

Release highlights include security plugin optimisation for a faster version of the implied permission type, memoization of results for batch requests, implementation of lazy loading for efSearch parameter in the k-NN plugin, improved exception handling and report date handling using standard formats for the SQL plugin.

Go get it now, [download link here](https://opendistro.github.io/for-elasticsearch/downloads.html).

**.NET Core 3.1**

Hot news for .NET core lovers, with support for .NET Core 3.1 in AWS Lambda. James Beswick shared the news this week via this blog post, [Announcing AWS Lambda support for .NET Core 3.1](https://aws.amazon.com/blogs/compute/announcing-aws-lambda-supports-for-net-core-3-1/) so you can read all about it. Aside from support for C# 8.0 and .NET Standard 2.1, there is news on a new feature that will help you with cold starts. Curious? Read on.

**AutoGluon**

In a previous edition of this newsletter I shared news about AutoGluon ([check out my original post back in January](https://dev.to/aws/open-source-news-and-updates-2-44b2)) Shashank Prasanna shares a great post on how we are making data scientists lives simpler, in his words:
>Part of what makes the machine learning process difficult is that there are a lot of best practices that experienced practitioners know to use. If you’re just getting started in data science, you may spend a significant amount of time on an approach you thought was right, which an expert practitioner would have told you is a dead end.
>
>What if you could codify these best practices into one simple and easy-to-use software package that any developer could use? A library that can automatically prepare your dataset, try different machine learning approaches, and combine their results to deliver high-quality models—and all of that with a few lines of code?

So, without further haste, read Shashank's post, [Machine learning with AutoGluon, an open source AutoML library](https://aws.amazon.com/blogs/opensource/machine-learning-with-autogluon-an-open-source-automl-library/).

**AWS C Cal**

So this [tweet thread](https://twitter.com/rjurney/status/1244443387312238592) brought this onto my horizon. Johnathan Henson shared the following on a twitter thread (paraphrasing a little)

**aws-c-cal (Crypto Abstraction Layer)** is part of the AWS Common Runtime, a collection of pure C99 libraries doing everything in the software stack at/above glibc to Layer-7 network protocols, cryptographic protocols, and operational tooling necessary to write an AWS client. There's lots of them, aws-c-common (basically a stdlib level library), aws-c-io (green threads, TLS, pki management, channels etc...), aws-c-http, aws-c-mqtt, aws-c-compression, aws-checksums (crc32c and crc32), and finally aws-c-auth. 

The common runtime avoids dependencies that aren't completely necessary. The only non-OS dependency currently is libcrypto on unix platforms, and this is only because it would be incredibly unsafe for us to implement our own cryptography primitives. On windows and mac os however, we just call into the OS provided crypto stacks (BCrypt and SecurityFramework respectively). 

It's a generic API that you can use however you would like. There's nothing AWS specific about it, other than the algorithms that are there are ones we needed. You'll notice that each of the libs I mentioned are generic to the task they are for. For example, aws-c-http is just a plain ole http library. It does Http 1.1, and H2 is almost completed. It will even do Http 3 when we have enough customers asking for it.

Finally all of these libs are then statically linked into a final "language bindings" for each of the programming languages AWS SDKs support - for example https://pypi.org/project/awscrt/

Check out the [GitHub repository for AWS C Cal here](https://github.com/awslabs/aws-c-cal).


### Hot blogging posts you must read

Max Brenner walks you through the new AWS CDK for Kubernetes framework that is available via the [AWS Labs github repository](https://github.com/awslabs/cdk8s) in his [blog post, CDK8s The future of k8s application deployments](https://brennerm.github.io/posts/cdk8s-the-future-of-k8s-application-deployments.html).

Muchas gracias Max!


If you are using **SAM** then you should check out this [blog post from Lorenzo Vanthillo, How to deploy a local serverless application with AWS SAM](https://medium.com/better-programming/how-to-deploy-a-local-serverless-application-with-aws-sam-b7b314c3048c). In his own words;

>The main goal of this article is to familiarise you with AWS SAM so you can test your lambdas on your local machine without the need to (re)deploy them every time on AWS. I’ll discuss different integrations and examples with SAM and lambda.

Thank you Lorenzo!

Finally, cannot leave this week without sharing Matt Asay's blog on '[Open source companies are thriving in the cloud](https://www.infoworld.com/article/3530071/open-source-companies-are-thriving-in-the-cloud.html)' post. Read how you don't need to mess about with open source licensing or business models, you just need to 'get smarter about cloud computing'. Short post with excellent data points. 

Thank you Matt!

---

### Do you use AWS and love open source? 

Do you have some content you want to share with a broader audience? We are always looking for guest content for the AWS Open blog. Please get in touch (via comments below) and I would love to speak with you about what you are doing in open source. We are always looking for interesting new content.

### We are hiring

We are hiring, so if you love open source, then why not check out the current openings. We would love to hear from you and if you want to chat and ask me anything, connect to me via LinkedIn or Twitter and always happy to talk.

[Open Source jobs at Amazon and AWS](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) - scroll to bottom, on left.

### Stay in touch with open source at AWS

I hope this summary has been useful. I have looked for all the session videos that have been uploaded to date, but if I have missed anything, please get in touch and I will update this summary. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on @AWSOpen.
