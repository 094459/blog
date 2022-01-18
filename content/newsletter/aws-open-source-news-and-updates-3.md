---
title: 'AWS open source news and updates #3'
date: '2020-01-23'
tags : [ oss-newsletter ]
---
So, welcome to open source updates and news at AWS #3 - I should really try and thing of a more entertaining sequence. Next time perhaps...

This update has been inspired by a recent trip away with some colleagues. On the way home, I started talking to the person next to me. He was an SA working on [HPC, High Performance Computing,](https://aws.amazon.com/hpc/) an area that I had read about a tiny amount but something I really didnt know that much. We had plenty of time and so I received a great education and introduction into this area of computing. What was even better was that open source is very prominent in HPC and so in this edition I want to talk about some of the great open source projects we have and support to better enable our customers to do HPC.

### AWS related Open Source projects

**HPC - Hight Performance Computing**

If you are just starting out learning about what HPC is and [how you might use it](https://aws.amazon.com/getting-started/projects/deploy-elastic-hpc-cluster/), there are some great posts that I can recommend that helped me. I really enjoyed reading this post by Jiawei Zhuang, "[A Scientists Guide to Cloud HPC](https://jiaweizhuang.github.io/blog/aws-hpc-guide/)" - its indepth and detailed, but gives a really great overview of the approach, principals and terminonology. Then this great post from James Strong from one of our partners, Contino, on [HPC in the fiancial services sector](https://www.contino.io/insights/high-performance-computing-for-financial-services).

We also have some [sample workshops](https://github.com/aws-samples/aws-hpc-workshops) where you can know kick the tyres of this stuff if you prefer learning via doing.


**AWS Lambda**

Colleague [Alex Casalboni](https://twitter.com/alex_casalboni) updated the [AWS Lambda Power tuning project](https://github.com/alexcasalboni/aws-lambda-power-tuning). Check out v3.2.0, now with weighted payloads which means you can inject a mix of different workload to get a more representative view of performance. Check out the github repo (see link) or easily deploy via the Serverless Application Repositor (SAR) [here](https://serverlessrepo.aws.amazon.com/applications/arn:aws:serverlessrepo:us-east-1:451282441545:applications~aws-lambda-power-tuning).

**Containers**

Via Michael Hausenblas, a new blog post on [securing EKS ingress with Contur and Lets Encrypt the GitOps way](https://aws.amazon.com/blogs/containers/securing-eks-ingress-contour-lets-encrypt-gitops/) from Stefan Prodan of Weaveworks.

Also this week, from the containers team, a request to vote/comment on a roadmap item on observability. The team are considering expanding FireLens. Go [direct to the issue here](https://github.com/aws/containers-roadmap/issues/701) and have your say. Keep up to date on all things observable by following [Wesley Pettit](https://twitter.com/TheWesleyPettit), an engineer working on container observabiliy.

[Massimo](https://twitter.com/mreferre) shared this sweet project this week, [Fargatecount](https://github.com/mreferre/fargatecount), an OSS project that allows you to track with a custom AWS CloudWatch metric, the total number of ECS and EKS pods deployed in a specific region of a specific account. Make sure to follow Massimo on Twitter and Github, you will thank me I am sure!

**DevOps**

If you use Visual Studio Code, then this [new open source project CDK Explorer](https://aws.amazon.com/about-aws/whats-new/2019/11/aws-toolkit-for-vs-code-adds-new-cdk-explorer-in-preview/?sc_channel=sm&sc_campaign=AWS_Blog&sc_publisher=LINKEDIN&sc_country=Global&sc_outcome=awareness&trkCampaign=pac-edm-2019-NET_developers-product_page&trk=pac-edm-2019-NET_developers-product_page+_LINKEDIN&linkId=80815948) might be something you want to check out. The CDK Explorer, a new preview feature in the AWS Toolkit for Visual Studio Code, allows developers to visualize CDK applications. AWS CDK, launched GA in July this year, is an open source software development framework to model and provision your cloud application resources using familiar programming languages.

To get started, head over to the [documentation page](https://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/cdk-explorer.html). This is a preview release, so if you find anything don't forget to raise an issue in the [github repo](https://github.com/aws/aws-toolkit-vscode).

**Robotics**

AWS RoboMaker is one of my favourite services and appeals to my inner maker/builder. Check out this great post on creating [AWS RoboMaker Robot resources using the CLI](https://www.emilykauffman.com/teaching/creating-robomaker-robot-resources-using-the-cli) from Emily Kauffman. This is a really well written and easy to follow post about a script that she developed to automate the process of setting up a new robot. [Here is a link to the Gist](https://gist.github.com/kauffmanes/0a2dcac87cf71fc6173d2b7b8b2bc001). 

**Other updates**

Envoy 1.13.0 was released this week and included in this releases was [AWS X-Ray support for tracing](https://www.envoyproxy.io/docs/envoy/v1.13.0/intro/version_history).

If you are using [Prometheus](https://prometheus.io/docs/prometheus/latest/getting_started/) to monitor your systems and are using Amazon MSK (Amazon Managed Streaming for Apache Kafka), [you can now enable Open Monitoring property to enable monitoring with Prometheus](https://twitter.com/cfnupdates/status/1219724435395108870).



### Tweet of the week

My favourite tweets this week on the topic of open source...

The first Tweet of the week this time comes from [Mark Terrel](https://twitter.com/MarkTerrel)'s post on the [decline of GPL licenses](https://twitter.com/markterrel/status/1218229248529518592?s=11). It links to a post on theregister.co.uk as in an interesting read. Make sure you check out the full article but also the counter points in the tweet comments.

The scond Tweet of the week is something I would like you to comment on below - [do you think open source software is higher, the same or lower quality than closed source/proprietry](https://twitter.com/FrkCorti/status/1219917325341745152) software? Interested in your views.

The final one shows that from small acorns grow great trees. Thanks for sharing[ Mike Roberts](https://twitter.com/mikebroberts/status/1219290930185953281). This is why we do open source.


### Other interesting open source posts

**OSI Membership and Elections**

Have you considered joining the Open Source Initiative? If you are on Twitter and follow open source, you will have probably seen the push to get new members signed up. If you haven't considered it, then perhaps now might be a good time to think about it. 

The [OSI have elections coming up](https://opensource.org/elections) and they have published a detailed timeline. If you want to get more involved in this community, now is the time. I know I am thinking about it myself, and there are two individual member seats available.

### Interested in Podcasts

The AWS Podcast always has interesting content, including covering our open source projects. In this episode, hear all about our encryption tools including the open source projects such as s2n.(later on in the podcast)

### Do you use AWS and love open source? 

Do you have some content you want to share with a broader audience? We are always looking for guest content for the AWS Open blog. Please get in touch (via comments below) and I would love to speak with you about what you are doing in open source. We are always looking for interesting new content.


### Stay in touch with open source at AWS

I hope this summary has been useful. I have looked for all the session videos that have been uploaded to date, but if I have missed anything, please get in touch and I will update this summary. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on @AWSOpen.

### We are hiring

We are hiring, so if you love open source, then why not check out the current openings. We would love to hear from you and if you want to chat and ask me anything, connect to me via LinkedIn or Twitter and always happy to talk.

[Open Source jobs at Amazon and AWS](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) - scroll to bottom, on left.