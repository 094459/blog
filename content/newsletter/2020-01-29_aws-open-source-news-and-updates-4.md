---
title: 'AWS open source news and updates #4'
date: '2020-01-29'
tags : [ oss-newsletter ]
---
Welcome to open source updates and news at AWS #4 the end of January 2020 edition. Keeping you up to speed with all things open source and AWS. Let's dive right in.

> ### Important announcement ###

> If you are using the Amazon Linux AMI (this was launched back in 2010, and then subsequently we released the Amazo Linux 2 AMI in 2017) then you should be aware that this [AMI is now end-of-life](https://aws.amazon.com/blogs/aws/update-on-amazon-linux-ami-end-of-life/). Make sure you read the blog post and find out what the time line is so you can be well prepared.

### AWS Open Source credits program

We are always looking to widen our open source collaboration by sponsoring foundations and events, increasing code contributions, open sourcing our own technology, and helping communities to sustain the overall health of open source. Back in October we launched the [AWS promotional credits for open source projects](https://aws.amazon.com/blogs/opensource/aws-promotional-credits-open-source-projects/), and since launching we have received a great response.
 
I get asked should I apply for these credits and whether my project would be a good candidate. Typically, these credits are used to perform upstream and performance testing, CI/CD, or storage of artefacts on AWS. We hope this program will free up resources for open source projects to further expand and innovate in their communities, as several projects are already doing.

Check out the link above and if you fit the description, why not help your open source project by applying for these credits.


### AWS related Open Source projects

**AWS Cloud Development Kit (CDK)**

The [Open Construct Foundation](http://www.openconstructfoundation.org) is where you want to go to find out more about the ecosystem that is built around the AWS CDK. Think of this as a kind of manefesto (my words, not theirs!) with links to use guides and examples. One of the links takes you to the [library of CDK Patterns](https://github.com/cdk-patterns/serverless) which I found via [Jeremy Daly](https://twitter.com/jeremy_daly) who is one of the AWS Serverless Heroes (make sure you follow him on Twitter as he always has great stuff he shares). There are a few patterns in there and this will surely grow over time.

Next up, [CDK 1.22.0](https://github.com/aws/aws-cdk/releases/tag/v1.22.0) went live, with the headline feature being support of AWS Fargate in Amazon EKS.

If you missed this blog post on [testing AWS Cloudformation templates](https://aws.amazon.com/blogs/infrastructure-and-automation/introducing-taskcat-v0-9/), then I got you covered. This post introduced [TaskCat (github repo)](https://github.com/aws-quickstart/taskcat) which is an open source tool developed in Python that allows you to validate your Cloudformation templates and generates a pass/fail report.

If you want to get involved with the AWS CDK community, they are always looking for new contributors. They ran a [great session at re:Invent](https://www.youtube.com/watch?v=LsYlf7ggyrY) to help people get started, and the open source project is really well laid out and has a good handful of [first issues](https://github.com/aws/aws-cdk/issues?q=is%3Aissue+is%3Aopen+label%3A%22good+first+issue%22) you can get your teeth stuck into.

**ROS**

[This post from Gingko Bioworks](https://twitter.com/Ginkgo/status/1221907299943559168/photo/1) has some great data points on the benefits of combining open source software such as ROS (Robotics Operating System) running on AWS.

**Security**

**Prowler** is an open source project that can be used to automate the auditing and hardening guidance of AWS accountds that are using the CIS (Centre for Internet Security) security benchmark. [Check out the project github repository here.](https://github.com/toniblyx/prowler).You can also follow [Tony](https://twitter.com/ToniBlyx), the author of Prowler, on Twitter.


### Interesting open source posts

**AWS CodePipeline**

If you use AWS CodePipline as part of your CI/CD toolchain, and wanted to have control over the build version numbers then you were out of luck. Well that was until now, this great little project via [Mike Roberts and Symphonia allows you to have greater control of linear release numbers](https://blog.symphonia.io/posts/2020-01-22_code_pipeline_versioner). If you like this, be sure to let Mike know.

[Aaia](https://hakin9.org/aaia-aws-identity-and-access-management-visualizer-and-anomaly-finder/) (the name apparantly means grand mother in Tamil) is an open source project that tries to build a graph databases in neo4j from the output of your AWS account. I have not tried it yet, but looks interesting. The visualisation should help you identify potenital anomolies in your IAM configuration, well that is the intention so check the project out.

Came across [Credstash](https://github.com/fugue/credstash) which is a very simple, easy to use credential management and distribution system that uses AWS Key Management Service (KMS) for key wrapping and master-key storage, and DynamoDB for credential storage and sharing. People clearly love this project (1.9K stars) so why not try this out.

### Snippets of the week

My favourite tweets this week on the topic of open source. This week, the theme is contributions and contributing.

It is important that you celebrate the community for your open source project, and I know some of the AWS open source projects do this. This tweet came up today and I wanted to give a shout out to [Andrzej Komarnicki](https://twitter.com/andrzej_devops/status/1221952628143349760) on the first contribution in open source. Thank you and I hope it is the first of many contributions for projects you care about.

People who have been following these updates will know that I love sharing those tweets and blog posts that talk about the first contribution. Head on over to [Joseph Heyburb's blog](https://jdheyburn.co.uk/posts/on-becoming-an-open-source-software-contributor/) where he talks about his experience. Be sure to follow him at [@jdheyburn](https://twitter.com/jdheyburn/)

And following on from that, another [tweet](https://twitter.com/WebinyPlatform/status/1222174684130750464) that [links to a blog post for Webiny](https://blog.webiny.com/webiny-january-update-%EF%B8%8F-a7b8dc7fcb36) that gives a shout out to the new communinty members. More of this please (and if you have a project and want to share with me good news like this, please get in touch).

From Twitter to [Reddit, this thread](https://www.reddit.com/r/opensource/comments/euzzqv/how_can_i_contribute_to_open_source_software_if_i/) shows that even if you are not a coder, that there are many ways you can contribute to open source communities. From tagging issues to contributing docs, there are many ways to contribute even if you are not a coder.

And finally..

What is the most important thing that you think about before contributing to an open source project? Whether you have never done this before, or whether you are a serial committer, is there something that makes you more likely to want to contribute? Take part in this poll and I will share the results in the next post.

https://twitter.com/094459/status/1222187362362544129

### Deep Dive

Fresh from the pages of WhiteSource is the [Open Source Licenses in 2020; Trends and Predictions](https://resources.whitesourcesoftware.com/blog-whitesource/top-open-source-licenses-trends-and-predictions). With licensing having such a dominant presence during 2019, I think this year will be interesting to see what happens. Make sure you follow the [OSI mailing groups ](https://lists.opensource.org/pipermail/license-review_lists.opensource.org/)and follow the discussions to keep up with the latest from the OSI.

If you like curated lists, then this is for you. An [Awesome AWS list](https://awesomeopensource.com/project/donnemartin/awesome-aws) that has hundreds of links to open source projects and libraries related to AWS. Keep this in you bookmark list for sure.

---
### Do you use AWS and love open source? 

Do you have some content you want to share with a broader audience? We are always looking for guest content for the AWS Open blog. Please get in touch (via comments below) and I would love to speak with you about what you are doing in open source. We are always looking for interesting new content.

### Stay in touch with open source at AWS

I hope this summary has been useful. I have looked for all the session videos that have been uploaded to date, but if I have missed anything, please get in touch and I will update this summary. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on @AWSOpen.

### We are hiring

We are hiring, so if you love open source, then why not check out the current openings. We would love to hear from you and if you want to chat and ask me anything, connect to me via LinkedIn or Twitter and always happy to talk.

[Open Source jobs at Amazon and AWS](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) - scroll to bottom, on left.