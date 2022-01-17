---
title: 'AWS open source news and updates - No.12'
date: '2020-03-23'
tags : [ oss-newsletter ]
---
## March 23rd - Instalment #12

Episode 12 in the series of open source news and updates on AWS brings you another mixed bag of treats. I wanted to start this instalment however with some of the projects that are looking to help respond to the current COVID-19 situation. You can read more about some of the initiatives at Amazon in the [blog post that shows how we are helping researchers and scientists accelerate diagnostics, research and testing.](https://blog.aboutamazon.com/innovation/aws-launches-initiative-to-accelerate-covid-19-diagnostics-research-and-testing) 


**Folding@Home**

Folding@home is a project focused on disease research, using computers and distributed processing to perform the millions of calculations needed to find cures. If you are not aware of this project, it had a lot of attention this week on social, specifically in how they are currently accelerate finding a cure for COVID-19. My colleague [Julien Simon wrote a blog post about how you can put your EC2 instances](https://medium.com/@julsimon/running-folding-home-on-amazon-ec2-instances-ce6bb8f84218) to work helping, and [Ric Harvey](https://twitter.com/ric__harvey) has put together a containerised version which you can find at [here](https://github.com/richarvey/FoldingAtHome). If you want a link to the source repository on GitHub, check that out at
[https://github.com/FoldingAtHome/coronavirus/blob/master/README.md](https://github.com/FoldingAtHome/coronavirus/blob/master/README.md)

**CovidTest**

The need to be manage and collect patient test data has emerged as one of the critical ways in which health authorities can manage outbreaks. [Gabriel Kardonski](https://github.com/gkpty) shared on Twitter a new project that in his own words:
>This platform is meant to be deployed and maintained by local governments and/or non-profit organizations that can provision covid19 tests and the mobile administration of these tests.

You can find the repository here at [https://github.com/gkpty/covidtest](https://github.com/gkpty/covidtest) so if you want to help Gabriel improve this project, have a look and then get in touch. Muchas gracias Gabriel!


**Jitsi - your open source solution to enable teams to work remotely**

If you have not already heard of Jitsi, then hopefully this post will rectify that. With increasing demands for teams to work and collaborate together, using the right tools is more important than ever. I put together a short walkthrough that will be able to get you up and running with one of these tools, Jitsi, that can help.

Find out more about Jitsi and how to get it up and running in this blog post, [Running your own open source web conferencing applications](https://dev.to/aws/running-your-own-open-source-web-conferencing-application-5aa2).

It is not the only one however, and there are other open source projects that might also be of use to remote teams. Let me know what you think -> [openvidu](https://openvidu.io/docs/deployment/deploying-aws/) and [BigBlueButton](https://bigbluebutton.org/) (open source project [here](https://github.com/bigbluebutton/bigbluebutton))


**Sharing best practices**

With people increasingly having to work remotely, the software conservancy shared how they have been doing this. Follow this link to read more[ https://sfconservancy.org/blog/2020/mar/17/remotetools/](https://sfconservancy.org/blog/2020/mar/17/remotetools/)


### Latest from open source projects

**CI/CD with Tekton and the Serverless framework**

The Linux Foundation announced the Continuous Delivery Foundation (CDF) early last year it provides a neutral home to collaborate on the development of the next generation continuous delivery systems. Tekton, which provides Kubernetes-like API resources to describe CI/CD pipelines, is an open source project hosted by the CDF.

Sebastien, co-founder of TriggerMesh, writes in this post ([Deploying an AWS Lambda function with the serverless framework and Tekton](https://aws.amazon.com/blogs/opensource/deploying-an-aws-lambda-function-with-the-serverless-framework-and-tekton/)) how to use Tekton to automate the deployment of AWS Lambda functions using the serverless framework. 

**S3 Streaming**

Via this [tweet](https://twitter.com/adamant_nz/status/1240569270028906496) from Adam Gibson, an old open source project by Samarth Gahire that provides tail like functionality. As Adam says, it is projects like these that really are one of the powerful foundations of open source and how it super charges developer productivity. Thank you Samarth Gahire and check out [s3streamcat here](https://github.com/samarthg/s3streamcat).


**Security**

A couple of new security related projects came up on my radar this week;

**Checkov.io**

[This project from Checkov is a static code analysis tool](https://www.checkov.io/documentation.html) for infrastructure-as-code and looks pretty comprehensive and easy to use. If python is your language of choice you will be right at home here. From the checkov.io folks:
>simplify and increase the adoption of security and compliance best practices that prevent common cloud misconfigurations. Its scans adhere and implement common industry standards such as the Center for Internet Security (CIS) Amazon Web Services (AWS) Foundations Benchmark.
https://www.checkov.io/3.Scans/Credentials%20Scans.html

**Electric Eye**

[Electric Eye](https://github.com/jonrau1/ElectricEye) is an open source project that looks to keep you safe by monitoring your AWS environments, and looking at specific configurations and how the match up to best practice. This looks super nice and very comprehensive. 

![AWS Architecture diagram](https://github.com/jonrau1/ElectricEye/blob/master/screenshots/ElectricEye-Architecture.jpg?raw=true)


**Machine Learning**

**Horovod** - not something that you might find in Harry Potter, but actually is a super useful open source framework for distributed deep learning training that works for TensorFlow, Keras, PyTorch and Apache MXNet. The goal is to make distributed deep learning fast and easy to use. Whilst some of the frameworks are already exploring distributed training, Horovod creates an abstraction layer and means this is framework agnostic. It also takes a similar approach to how HPC and parallel computing works. 

To get started, my colleuge [Shashank Prasanna](https://twitter.com/shshnkp) wrote a [quick guide to distributed training with Tensorflow and Horovod on Amazon SageMaker](https://towardsdatascience.com/a-quick-guide-to-distributed-training-with-tensorflow-and-horovod-on-amazon-sagemaker-dae18371ef6e). Follow [Shashank](https://twitter.com/shshnkp) on Twitter to keep up to speed with all things machine learning.

**Deep Pens**

As we are in lock down I was fortunate that a colleague who lives near me shared this great project that was show at the reInvent 2019 builders fair, and is now open sourced. Using this open source project you can say a word and then it will the draw something using the plotter that you build.

Find details for the project [here](https://github.com/aws-samples/aws-builders-fair-projects/tree/master/reinvent-2019/deeppens), but you will need to buy stuff for this project (but they have provided everything you need).

![Deeppens](https://github.com/aws-samples/aws-builders-fair-projects/blob/master/reinvent-2019/deeppens/images/deeppens-architecture.png?raw=true)

**Anonymising data**

Starting off on your open source journey is always something to be encouraged, so am very happy to share a project that I heard about recently, from [Jon Russell](https://twitter.com/Jonopoly). Open source has often been the story about developers solving problems they had and then sharing the solutions so others could benefit, and in this project Jon share's one such problem he had around working with data and creating a solution to anonymise/scrub that data so that developers could work on it without compromising access to the data. 

This is Jon's first adventure into open source and so check out his project repository at [https://github.com/Jonopoly/AnonyPy](https://github.com/Jonopoly/AnonyPy) and see if this might be useful to you. Thanks Jon!


### AWS Open Source projects

### Deep Dive

A couple of great posts from colleague and general open source good guy [Matt Asay ](https://twitter.com/mjasay)for you to wrap your thinking caps around.

* Looking at how "open source is at its most innovative and sustainable when maintained by a community", read more in [Why the best open source is community led open source](https://thenewstack.io/why-the-best-open-source-is-community-led-open-source/)

* Open source software and cloud are better together, but making sure that open source projects have the right building blocks to build their cloud based offerings means more are coming to AWS and benefitting from the widest range of products and services enabling these open source projects to innovate faster. Read on in this blog, [To get the most from open source software run it where it works best](https://aws.amazon.com/blogs/modernizing-with-aws/to-get-the-most-from-open-source-software-run-it-where-it-works-best/).


### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created.

So thank you Ric Harvey, Julien Simon, Gabriel Kardonski, Sebastien Goasguen, Shashank Prasanna, Jonathan Rau, Bridgecrew, Jon Russell and Samarth Gahire


---
### Do you use AWS and love open source? 

Do you have some content you want to share with a broader audience? We are always looking for guest content for the AWS Open blog. Please get in touch (via comments below) and I would love to speak with you about what you are doing in open source. We are always looking for interesting new content.

### We are hiring

We are hiring, so if you love open source, then why not check out the current openings. We would love to hear from you and if you want to chat and ask me anything, connect to me via LinkedIn or Twitter and always happy to talk.

[Open Source jobs at Amazon and AWS](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) - scroll to bottom, on left.

### Stay in touch with open source at AWS

I hope this summary has been useful. I have looked for all the session videos that have been uploaded to date, but if I have missed anything, please get in touch and I will update this summary. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on @AWSOpen.
