---
title: 'AWS open source news and updates #7 - networking, data analytics, security and more '
date: '2020-02-17'
tags : [ oss-newsletter ]
---
Episode #7 of the open source news and updates for AWS. More security posts in this weeks updates, together with some other cool updates from machine learning, networking and data analytics. I am always looking for interesting open source projects that run on AWS, so if you are working on or know about any, please let me know as I would love to make more people aware.

### Open Distro for ElasticSearch

This [tweet](https://twitter.com/AWSOpen/status/1227330467659161603) announced that the AWS managed Amazon Elasticsearch service had now incorporated the security features that have been available on the Apache 2.0 Open Distro for Elasticsearch distribution. This made me revisit the workshop that from re:Invent, [OPN-302 Getting Started with Open Distro](https://reinvent.aesworkshops.com/opn302/) and I found a bug with this workshop. If you want to do the workshop, then use the following as the source link for your CloudFormation template, replacing the current link in the Deploy Cloudformation stack section. This should resolve your problems. Here is the updated [link](https://ricsuepublicresources.s3-eu-west-1.amazonaws.com/cf/od4es.json)

>https://ricsuepublicresources.s3-eu-west-1.amazonaws.com/cf/od4es.json


### Security with open source

If you are looking for a tool to help evaluate your Terraform scripts, then **[Regula](https://github.com/fugue/regula)** is the open source project you have been looking for. Regula evaluates Terraform infrastructure-as-code for potential AWS security misconfigurations and compliance violations prior to deployment. Should work with all your favourite CI/CD tools such as AWS CodePipeline, Circle CI and there is plenty of info in the documentation to get you started.

Wanting to have a good grasp of what your environments sounds like something a lot of people will find useful. This open source project from **[duo-labs, Cloudmapper](https://github.com/duo-labs/cloudmapper)** does just that. It looks pretty meaty, has been going for a while and has a lot of fans (currently at 3.3K stars). There are some demo videos as well as this [intro post](https://duo.com/blog/introducing-cloudmapper-an-aws-visualization-tool) from the authors. Happy mapping folks!

On a related note is this python project, [AWS Report by Haking](https://hakin9.org/aws-report-a-tool-for-analyzing-amazon-resources/). Check out the repo [here](https://github.com/gmdutra/aws-report), and let me know what you think.

And for the lover of lists, then a new one from the [Linux Security Expert](https://linuxsecurity.expert/security-tools/aws-security-tools) site. From AWS hardening, scanning, modeling and benchmarking, you will find something. These are open source and whilst I have shared some of these before, you can never have enough lists.

The day before valentines day is the perfect time to release a [7 open source cloud security tools you should know blog post](https://blog.runpanther.io/open-source-cloud-security-tools/). Any post where I get to hear about new open source projects is fine by me, and this one has more than one I didn't know about. Nice touch adding the stats for the different projects, so thank you Panther. (and check out the rest of their site, lots of other interesting content too)

### AWS related Open Source projects

**Networking**

If you are looking to automate how you manage and syncronise route tables across your Amazon Virtual Private Cloud (VPC) then this is going to interest you. The primary use case is for VMware Cloud on AWS (VMC) software-defined datacenter (SDDC) managed routes, but this could also be used as-is for any scenario where syncing AWS VPC routes to custom route tables is desired. This blog posts covers how it works under the cover, so if this sounds useful, then read on in the blog post, [syncronise route tables across VPCs](https://aws.amazon.com/blogs/opensource/sync-routes-across-route-tables-with-aws-sync-routes-a-serverless-open-source-project/). Project documentation can be found here in the [AWS Labs github repo for aws-sync-routes](https://awslabs.github.io/aws-sync-routes/)

**Amazon EKS VPC CNI**

Another networking related update, but this time for Kubernetes users, this project is a [networking plugin for pod networking in Kubernetes using AWS Elastic Network Interfaces (ENIs)](https://github.com/aws/amazon-vpc-cni-k8s). Version 1.6 has been released of the open source Amazon VPC CNI plugin includes a new MINIMUM_IP_TARGET parameter that can be used to reduce pod start time while minimizing IP addresses allocated to nodes. Support for peered VPCs is improved with a new parameter AWS_VPC_K8S_CNI_EXCLUDE_SNAT_CIDRS that allows CIDR ranges to be excluded from Source Network Address Translation (SNAT). Additionally, v1.6 includes a number of bug fixes around ENI allocation and EC2 API call rates to improve overall reliability and performance. **[Click here for the full breakdown of release 1.6.](https://github.com/aws/amazon-vpc-cni-k8s/releases/tag/v1.6.0)**

**Machine Learning**

Back in November, we launched an open source project called the [AWS Step Functions Data Science SDK for Amazon SageMaker](https://aws.amazon.com/about-aws/whats-new/2019/11/introducing-aws-step-functions-data-science-sdk-amazon-sagemaker/). In a brand new post, you can follow a sample project and notebook that was published on the [AWS Machine Learning blog will be of use to a lot of people who want to automate the training and deployment of models](https://aws.amazon.com/blogs/machine-learning/automating-model-retraining-and-deployment-using-the-aws-step-functions-data-science-sdk-for-amazon-sagemaker/). This is a long post but with the effort comes great rewards.

**Amazon SageMaker MXNet**

[SageMaker MXNet Serving Container is an open-source library for making Docker images](https://pypi.org/project/sagemaker-mxnet-inference/1.2.0/) for serving MXNet on Amazon SageMaker. This library provides default pre-processing, predict and postprocessing for certain MXNet model types, and this week [v1.2.0](https://github.com/aws/sagemaker-mxnet-serving-container/releases) was released. Check the release notes for the updates and bug fixes.

**AWS DeepRacer**

Do you like AWS DeepRacer? Some of you know that I have been known to run a workshop or two, and during my journies I speak to customers doing some cool things with AWS DeepRacer. This open source project, or rather [collection of utilities, by Cahya Wirawan](https://github.com/cahya-wirawan/deepracer-tools/tree/master/auto-submission) is super useful and a great way to give your RL and DeepRacer competitions a turbo boost.


**AWS Amplify**

The [AWS Amplify team announced the pre-release of DataStore React Native](https://github.com/aws-amplify/amplify-js/issues/4527?sc_channel=sm&sc_campaign=Mobile_Campaign&sc_publisher=TWITTER&sc_country=Mobile&sc_outcome=awareness&trk=sm-mobile-community_TWITTER&linkId=82274998#issuecomment-585524466). Checkout the github link [here](https://github.com/aws-amplify/amplify-js/issues/4527?sc_channel=sm&sc_campaign=Mobile_Campaign&sc_publisher=TWITTER&sc_country=Mobile&sc_outcome=awareness&trk=sm-mobile-community_TWITTER&linkId=82274998#issuecomment-585524466) and feedback what you think.

**AWS MSK**

Fresh off the press today is this blog post from [Maikel Penz, the first of a three part series on building a Kafka playground](https://medium.com/@maikelpenz/building-a-kafka-playground-on-aws-part-1-setting-the-foundation-3065ecf51c19). Kafka is an open-source streaming platform and we launched the managed service back in 2018. This series looks like a good way of getting started to know more about this service.


### Deep Dive

This [Cumulus project ](https://nasa.github.io/cumulus/docs/cumulus-docs-readme)seeks to address creating a cloud-based data ingest, archive, distribution, and management system that can be used for all future Earth Observing System Data and Information System (EOSDIS) data streams. Aside from the interesting use case, this open source project could be used as a reference architecture for many other big data use cases. Check out the [Architecture](https://nasa.github.io/cumulus/docs/architecture) page for details of the components that make up the solution.


### Tweet of the week

This one from [Matt Asay](https://twitter.com/mjasay) on the increasing trend for open source projects to [build services on Cloud](https://twitter.com/mjasay/status/1227326249481142272) so that their customers can get started and focus on using the technology.


---
### Do you use AWS and love open source? 

Do you have some content you want to share with a broader audience? We are always looking for guest content for the AWS Open blog. Please get in touch (via comments below) and I would love to speak with you about what you are doing in open source. We are always looking for interesting new content.

### We are hiring

We are hiring, so if you love open source, then why not check out the current openings. We would love to hear from you and if you want to chat and ask me anything, connect to me via LinkedIn or Twitter and always happy to talk.

[Open Source jobs at Amazon and AWS](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) - scroll to bottom, on left.

### Stay in touch with open source at AWS

I hope this summary has been useful. I have looked for all the session videos that have been uploaded to date, but if I have missed anything, please get in touch and I will update this summary. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on @AWSOpen.