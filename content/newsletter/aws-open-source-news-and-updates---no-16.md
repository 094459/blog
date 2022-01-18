---
title: 'AWS open source news and updates - No. 16'
date: '2020-04-20'
tags : [ oss-newsletter ]
---
## April 20th - Instalment #16

Episode 16, and like most folk confining myself to my home has provided me with lots of time to search the four corners of the internet to bring you all the latest news, updates and interesting things happening where open source meets AWS. This week I want to share a couple of posts in which both Amazon and open source developers and communities are helping to tackle the COVID pandemic.

In his post, [When scaling your workloads is a matter of saving lives, Amazon and AWS CTO Werner Vogels ]()writes how we helped DJ Patil, former White House Chief Data Scientist run an open source project that DJ and his team have been working with one that had been primarily developed by the world renowned Johns Hopkins Bloomberg School of Public Health (JHSPH). 

![Architecture for scalable COVID scenario pipeline using AWS Batch](https://www.allthingsdistributed.com/images/covid2.png)

The end result? As the blog post concludes;

>DJ’s team has reduced the time to on-board the model pipeline and generate a full report from one week for one scenario to under 12 hours for multiple scenarios. Now, the new model created by JHSPH is being rolled out on AWS to all 50 states and internationally to help with making decisions that directly impact the global spread of COVID-19.
>

From running one open source project to another one from Adam Barnhard, who has put together a [project to help you sift through all the thousands of projects that the open source development community](https://towardsdatascience.com/building-a-covid-19-project-recommendation-system-4607806923b9
) have been working on during the COVID-19 pandemic. According to a GitHub published stat, over 36K open source projects related to this area have been created, so the question is how do you find projects that might help you or that you might want to contribute to? Well, Adam's project should help you so go check out his post and see if it helps you to sift through and find something that will help you or that you can contribute to.

### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created.

So thank you to John Preston, Amir Szekely (@virtuajack), Rene Brandel, the folks at codezri, Rafael Lopes, Ran Ribenzaft, Adam Barnhard, Shivansh Singh, Omer Tsarfati


### Latest from open source projects

**Serverless framework - Lovage**

Fresh from Amir Szekely, comes news of a new serverless framework called Lovage. In his [blog post, Lovage](https://kichik.com/2020/04/11/lovage/), Amir talks about the motivation for creating this, namely some limitations which he found when using the Serverless Framework. So after checking out the blog, you can head over to the [GitHub repository for Lovage](https://github.com/CloudSnorkel/lovage) and check it out. I love the introduction:

>Kind of like Celery, but simpler and with more Lambda

Thank you Amir!


**ECS ComposeX**

A few weeks ago in [No.13](https://dev.to/aws/aws-open-source-news-and-updates-no-13-46fg) I mentioned this neat project, ECS ComposeX that John Preston had created. Well, following on from that I wanted to share his new blog post and walkthrough of how to use this. In 'CICD Pipeline for multiple services on AWS ECS with ECS ComposeX.' John provides a great walkthrough of how to use ECS ComposeX using some sample applications integrated with AWS services.

![Diagram of architecture.](https://blog.ecs-composex.lambda-my-aws.io/images/cicd-pipeline/cicd-structure.jpg)

Thanks again John!

**TermClicker**

Very happy to share this project from colleague and general all round awesome guy, Rafael Lopes (@deploytoprod). This little project will be indispensable if you spend any time talking in front of folks, doing demos and being at the mercy of the demo gods and goddesses. Use this project to script what you want to happen and then with just a click, see your commands come out perfect every time.

![Demo of TermClicker](https://github.com/deploytoprod/TermClicker/raw/master/images/TermClicker.gif)

As Rafael says, no more copy paste woes, just less stress and great demos. We like that a lot - head over to the [GitHub repo for TermClicker](https://github.com/deploytoprod/TermClicker) and give it a go.

Thank you Rafael!

**LAMG**

From LAMP to MEAN to LAMG, just when you thought it was safe from someone releasing a new stack, comes a new one to make you realise that there is life in those stacks yet. Now there is no code in this project by the folks at [codezri](https://codezri.org), but more a breakdown of what a L[AMG stack would look like and a walkthrough of creating your first LAMG project](https://github.com/codezri/lamgstack). So, what does LAMG stand for? L is for AWS Lambda, A for Angular, M for MongoDB and G is for GitHub. I think there was a missed opportunity here for calling it GLAM, but who knows, maybe that might be out there somewhere.

**openSUSE Tumbleweed**

SUSE was the first Linux distribution that I started to use in anger, and whilst I slowly moved my own away onto other distributions, it is still a great Linux distribution (and I still kind of miss YaST if I am being completely honest). If you are a fan of the SUSE distribution, then great news as Tumbleweed is now available via the AWS Marketplace. Check out the announcement [blog post, openSUSE Tumbleweed](https://news.opensuse.org/2020/04/14/openSUSE-Tumbleweed-available-on-AWS/).

**Security**

This week we have a couple of fantastic security projects.

**SkyWrapper** 

From the folks at Cyberark, Omer Tsarfati wrote a detailed blog post introducing a new open source project called SkyWrapper, a tool that help you to understand the behaviour of temporary credentials within your AWS accounts. allowing you to observe and address any potentially misconfigured IAM roles you might have. Read the detailed blog post that [Omer put together, Wild temporary tokens and where to find them](https://www.cyberark.com/threat-research-blog/wild-temporary-tokens-and-where-to-find-them-aws-edition/), and then check out the repository at[ Cyberark's GitHub page here](https://github.com/cyberark/SkyWrapper
).

**AutoMirror** 

Next up is a neat little tool that allows you to perform traffic analysis on your AWS networks. If you are fans of tools like Wireshark that allow you to record and then analyse your network traffic, then you will be interested in this project from the folks at [3CORESec announcing version 1.0 of AutoMirror](https://blog.3coresec.com/2020/04/automirror-100.html). Available via the AWS Serverless Application Repository, you can quickly get started with this project. Check out the [GitHub project pages for AutoMirror](https://github.com/3CORESec/AWS-AutoMirror) and if you are interested, you will notice that they are running a webinar on how to use this so make sure you sign up.




**AWS KMS and OpenSSL**

In this blog post understand how you can [verify the authenticity of a digital signature generated by a KMS asymmetric key pair on your local machine using the open source tool, OpenSSL](https://aws.amazon.com/blogs/security/how-to-verify-aws-kms-asymmetric-key-signatures-locally-with-openssl/). 

The post provides a sample workflow for generating a digital signature within AWS Key Management Service (KMS) and then verifying that signature on a client machine using OpenSSL. From the post itself;

>The support for asymmetric keys in AWS KMS has exciting use cases. The ability to create, manage, and use public and private key pairs with KMS enables you to perform digital signing operations using RSA and Elliptic Curve (ECC) keys. You can also perform public key encryption or decryption operations using RSA keys.

>For example, you can use ECC or RSA private keys to generate digital signatures. Third parties can perform verification outside of AWS KMS using the corresponding public keys. Similarly, AWS customers and third parties can perform unauthenticated encryption outside of AWS KMS using an RSA public key and still enforce authenticated decryption within AWS KMS. This is done using the corresponding private key.


### AWS Open Source projects


**AWS Data Wrangler**

[AWS Data Wranger is an open source project](https://github.com/awslabs/aws-data-wrangler) that can be found on the AWS Labs GitHub repository, is a useful project that provides helper libraries to handle data on AWS, amd helps you integrate AWS Analytics Services (Glue, Athena, EMR, Redshift) with Python data libraries (Pandas, Apache Spark). 

A python library that you can deploy/install in a number of different ways (from pip in your python environments, to others such as Conda, source code, AWS Lambda Layer, AWS Glue Wheel, SageMaker notebook and EMR cluster)

The documentation provides lots of great [tutorials](https://github.com/awslabs/aws-data-wrangler/tree/master/tutorials) you can follow along and see how you might be able to use it with a number of different AWS services such as Amazon Athena, Amazon Redshift, Amazon S3 and more.


**Bottlerocket**

[How to get started with Bottlerocket OS is a new blog post by Ran Ribenzaft at epsagon](https://epsagon.com/blog/tools/how-to-get-started-with-bottlerocket-os/), which provides a nice introduction to Bottlerocket OS.

**Amplify CLI**

Rene Brandel wrote a fun blog post, [How to Schedule recurring Lambda functions using the Amplify CLI](https://aws.amazon.com/blogs/mobile/how-to-schedule-recurring-lambda-functions-using-the-amplify-cli/) that I know many of you will find useful in more ways than just sending cat facts! This quick walkthrough should hopefully inspire you on how you can use a similar approach for scheduling or executing functions periodically based on your use case. Look forward to hearing what you do with this.

**Amplify RFC - Importing existing AWS resources**

The request for comment (RFC) mechanism is one of the standard ways in which open source projects seek to get valuable feedback from the community when looking ahead at future work. You can find lots of great posts about this, but this one from [Juan Pablo Buritica over at opensource.com](https://opensource.com/article/17/9/6-lessons-rfcs) ticked the boxes for me, so read it if you want to know more about why RFCs are important.

That leads me on to this RFC from the Amplify team which you can [find on the GitHub project repository](https://github.com/aws-amplify/amplify-cli/issues/3977), but to summarise in this RFC they are looking at address:
>Currently, the CLI provisions new AWS resources based on the categories that you add to your Amplify project. This RFC is to gauge community interest and hear more thoughts around the CLI being able to import existing resources into an Amplify project.
>
>As an MVP, we’re planning to support importing of resources in the following categories:
>
>* Auth
>* Storage (S3 & DynamoDB)
>* API - REST and GraphQL (to use existing data sources and auth resources)

There are already some comments, so if you use and love Amplify and are interested in sharing your feedback, you know what to do.

**Open Distro for Elasticsearch**

In [No. 14](https://dev.to/aws/aws-open-source-news-and-updates-no-14-492g) I talked about a new release of Open Distro for Elasticsearch (ODES) and mentioned a new plugin for machine learning allowing you to use k-NN similarity search features. If you were curious how to get started, then you need to check out this blog post, [Build K-Nearest Neighbor (k-NN) similarity search engine with Elasticsearch](https://opendistro.github.io/for-elasticsearch/blog/odfe-updates/2020/04/Building-k-Nearest-Neighbor-(k-NN)-Similarity-Search-Engine-with-Elasticsearch/).

Why might this be useful to you? Well, extracting from the blog post:
>A k-nearest neighbors (k-NN) algorithm is a technique for performing similarity search: given a query data point, what are the k data points in an index that are most similar to the query? k-NN is largely popular for its use in content-based recommendation systems. For example, in a music streaming service, when a user generates an on-demand playlist, the recommendation system adds the songs that match the attributes of that playlist using k-NN.

**s2n and Hybrid Post-Quantum TLS Benchmarks**

In the second of a two part blog post, [Alex Weibel shares details about upcoming performance differences between classical and hybrid post-quantum TLS](https://aws.amazon.com/blogs/security/round-2-hybrid-post-quantum-tls-benchmarks/) (Transport Layer Security). The post-quantum TLS is a proposed extension that is implemented in Amazon's open sourced [s2n library](https://github.com/awslabs/s2n) and this diagram helps explain the this.

![Hybrid post-quantun TLS diagram](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2020/04/13/Post-quantum-TLS-Figure-1.png)

This post has everything you you need to know on hybrid post quantum TLS. I can't say that I fully understood everything in this post, but if you are a cryptographer or security researcher, you are going to like the level of detail and benchmarks. 


### Online events for your diary

**May 12th, Tuesday**

https://opensource101.com/events/at-home/

If you have any events you want me to share, please drop me a mail or add it to the comments - I watch these so will be sure to add it in the following roundup.


### Hot blog posts you must read

Some good blog posts this week if you missed them, check them out or bookmark for later.

**Hugo: Integrating a CI/CD pipeline for Hugo websites**

If you are looking at static site generators or have been looking to optimise your Hugo setup on AWS, then you need to check out this post, [Building a CD/CD pipeline for Hugo](https://aws.amazon.com/blogs/infrastructure-and-automation/building-a-ci-cd-pipeline-for-hugo-websites/). Thanks Shivansh Singh!

**Unlocking data with AWS and open source**

I love customer stories, so when I find one that shows how customers are building open source to make a difference within their business I get super excited. [Read how Fred Hutchinson Cancer Centre were able to unlock data by creating an open source tool](https://aws.amazon.com/blogs/publicsector/how-fred-hutch-unlocks-siloed-data-open-source-software/) called Motuz. You to can use this tool, and it is very easy to get up and running in the well documented [GitHub repository which you can find here.](https://github.com/FredHutch/motuz)

---

### Do you use AWS and love open source? 

Do you have some content you want to share with a broader audience? We are always looking for guest content for the AWS Open blog. Please get in touch (via comments below) and I would love to speak with you about what you are doing in open source. We are always looking for interesting new content.

### We are hiring

We are hiring, so if you love open source, then why not check out the current openings. We would love to hear from you and if you want to chat and ask me anything, connect to me via LinkedIn or Twitter and always happy to talk.

[Open Source jobs at Amazon and AWS](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) - scroll to bottom, on left.

### Stay in touch with open source at AWS

I hope this summary has been useful. I have looked for all the session videos that have been uploaded to date, but if I have missed anything, please get in touch and I will update this summary. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on @AWSOpen.
