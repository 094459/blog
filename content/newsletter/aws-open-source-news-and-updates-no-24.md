---
title: 'AWS open source news and updates No. 24'
date: '2020-06-15'
tags : [ oss-newsletter ]
---
## June 15th - Instalment #24

Another expansive instalment in No. 24, as we approach the half way point of the year. In this episode we have a number of PHP related posts, fitting as it rapidly approaches its 25th anniversary. If you are a PHP builder, then keep your eyes/ears posted, as we have something special for you soon. Aside from PHP, we have some great new projects as well as important new releases for existing ones that you need to know about. So enough of the introduction, please get stuck in and read on...

### Feedback

A small ask this week for people who are reading this on a regular basis. I am looking to collect data to see how we are doing and whether these weekly updates help increase awareness of open source projects that AWS as well as our customers, builders and communities are working on.

I have put together a short feedback survey, which you can access [here](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn), and would be grateful if you could spare the 2 minutes it takes to complete. Many thanks!

[Take the survey](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn)

### Submit contributions, win prizes

I am always looking for exclusive open source projects that I can share with the community. Please contact me with your AWS related open source projects as I have prizes for the best contributions...so look forward to seeing what you send.

### Growing contributions

This post from [Brian Douglas](https://twitter.com/bdougieYO) (@bdougieYO) on dev.to, [A path for open source contributions](https://dev.to/opensauced/a-path-for-open-source-contributions-2oa2) is well worth reading.

Aside from some excellent data points, he shares with us his journey and tips to get started, as well as a project he put together to help him manage his own contributions. You can find this[ project here](https://opensauced.pizza/), and he provides the source code and details on how to put this together if you want to host your own.

Thanks Brian!


### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created.

So thank you to Patryk Orwat, Jim Jackson, Itzik Jan, Avi Ben Yossef,  Kpicaza, Francisco Gonzalez, Ben Smith, Viraj Phanse, Dmitriy, Taufek Johar, Sergio Matone (@sw360cab), Michael Weibel (@mweibel), Moez Ali, David de Torres Huerta, Ido Nissim, Brian Caffey, Sigit Priyanggoro, Alex Casalboni, Jan-Christoph Küster and Pahud Hsieh

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

**[Note! these projects are shared on the basis of awareness and raising the visibility. I do no warrant these and you should always take care when experimenting and testing these out.]**


**evb-local**

So last week we had the eventbridge-cli project from Matteo, this week we have the [evb-local ](https://github.com/mhlabs/evb-local)project from the [mhlabs tech team](https://github.com/mhlabs).

Tool that lets you subscribe locally to events matching EventBridge rules in a given deployed stack. This is to help with debugging of complex flow of events raised in your application.

This tool provides a listen and test function, allowing you to create a local consumer of all deployed EventBridge rules in a stack (events will be output to your console with the option to pass them on to sam-local for local debugging) and quickly test rules from you SAM/CloudFormation template before deploying.

![evb-local](https://raw.githubusercontent.com/mhlabs/evb-local/master/demo.gif)

Go grab this project from the [GitHub repository here](https://github.com/mhlabs/evb-local).

 **cloudiscovery**
 
A nice project from Patryk Orwat, **[cloudiscovery](https://github.com/Cloud-Architects/cloudiscovery)** a tool to help you visualise your AWS environments so you can better understand them. This is a python bases script, that is easy to install and get up and running. Currently supports VPC, IoT and IAM policies.

![diagram](https://github.com/Cloud-Architects/cloudiscovery/raw/develop/clouddiscovery/docs/assets/aws-policy.png)

Nice job Patryk!


**awscdk-jsii-template**

This project, [awscdk-jsii-template](https://github.com/pahud/awscdk-jsii-template), from Pahud Hsieh provides you with a quick template and instructions to enable you to quickly put together your own AWS CDK constructs.

Thank you Pahud. Make sure you check out his videos on You Tube in Mandarin

**awsweeper**

There have been a few times when I have been messing about, experimenting with a new project and I run into an error around exceeding the soft limits - typically VPCs for example. I then need to spend some time cleaning it all up and trying again. Other times it is cleaning up after installing and configuring a project that you want to understand in more detail.

awsseepers is a tool from Jan-Christoph Küster (@jckuester) that is definitely going to help me, and allows you to quickly remove/delete AWS resources from within your AWS account.

![usage](https://github.com/jckuester/awsweeper/raw/master/img/asciinema-tutorial.gif)

**USE WITH CARE**

As Jack writes at the bottom of this project:

> You are using this tool at your own risk! I will not take responsibility if you delete any critical resources in your production environments.
> 

**awsls**

Not content with **awsweeper**, Jan has his second project, called **[awsls](https://github.com/jckuester/awsls)** a command line tool that is super fast and allows you to show your AWS resources. The tool supports hundreds of AWS resource types, and Jan provides some ready to roll binaries so you can download to start using this tool.

![awsls tool](https://github.com/jckuester/awsls/raw/master/img/instance.gif)

Thanks Jan, these will come in handy for sure.


**AWS Lambda Power Tuning**

Hot off the press is Alex Casalboni's [tweet announcing v3.3.0 ](https://twitter.com/alex_casalboni/status/1270765001775689728)of his incredibly useful and much loved open source project, AWS Lambda Power Tuning. If you did not already know, this project helps you make more informed choices of how to optimise your AWS Lambda settings and balance cost vs performance, and provides nice visualisations and data to help you.

What is new in v3.3? Well some good stuff:

* Pre/Post-processors - great to power-tune functions with side effects
* Correct regional pricing
* Customisable timeouts

Want to know more or contribute, then head on over to the [GitHub repository here](https://github.com/alexcasalboni/aws-lambda-power-tuning).

**Simple S3 Upload with React and Amplify**

A quick 10 minute project from Sigit Priyanggoro, [Simple S3 Upload](https://dev.to/sigitp/s3-image-video-upload-react-component-with-aws-amplify-4ej4), source code in his [GitHub repository here](https://github.com/sigitp-git/s3fileupload-react-amplify), that will walk you through creating a simple picture and video uploader using Amplify and React.

Thanks Sigit!

**Building Django + Vue.js applications with AWS CDK and GitLab CI**

Deep dive from Brian Caffey and this project is an overview of a Proof-of-Concept web application called [django-postgres-vue-gitlab-ecs](https://gitlab.com/briancaffey/django-postgres-vue-gitlab-ecs). This project aims demonstrate local development, CI/CD and production setup for a full stack web app using Django, Django REST Framework, Django Channels, Postgres, VueJS, Redis, Celery, GitLab CI and AWS technologies deployed with CDK.

Check out the [project overview docs here](https://verbose-equals-true.gitlab.io/django-postgres-vue-gitlab-ecs/start/overview/).

![architecture](https://gitlab.com/briancaffey/django-postgres-vue-gitlab-ecs/-/raw/develop/architecture.png)

If this impressive architecture does not motivate you to read more, then I am not sure what will! Thanks Brian.


### Blog posts you should check out

**MLFlow on AWS**

Data Engineer Ido Nissim writes in [ML-Ops, Part 1: Organise your ML experiments with ML-Flow on AWS](https://allcloud.io/blog/organise-your-ml-experiments-with-mlflow-on-aws/) what Machine Learning Operations, or ML-Ops is and goes on to show you how to use an open source project called MLFlow to track your machine learning experiments.

If you want to dip your toes in ML-Ops or MLFlow, then try this post out first.

Thanks Ido!

**Prometheus**

According to Greek mythology, Prometheus gave us fire. but it is also an open source project that sheds light into applications, providing event monitoring and alerting. This week, there are a couple of posts this week on this topic.

In this first post, [Monitoring AWS Fargate with Prometheus and Sysdig](https://sysdig.com/blog/monitor-aws-fargate-prometheus/), David de Torres Huerta walks us through setting up how to monitor AWS Fargate with Prometheus.

![monitor fargate](https://478h5m1yrfsa3bbe262u7muv-wpengine.netdna-ssl.com/wp-content/uploads/fargate-sysdig-golden-signals-1930x1072.png)

The second post is one that somehow slipped under my radar, [David de Torres Huerta writes in Improving the Prometheus exporter for Amazon CloudWatch](https://sysdig.com/blog/improving-prometheus-cloudwatch-exporter/), how they worked with an existing open source project ([YACE](https://github.com/ivx/yet-another-cloudwatch-exporter), Yet Another CloudWatch Exporter) and contributed back to this project in order to optimise and improve it so they could create a production grade Prometheus CloudWatch exporter.

![sysdiag](https://478h5m1yrfsa3bbe262u7muv-wpengine.netdna-ssl.com/wp-content/uploads/03_Improving-the-Prometheus-CloudWatch-exporter_metrics_proxy.png)

This is a great deep dive that goes into and assess existing approaches, so you will learn lots.

**Machine learning pipelines on AWS Fargate**

In [Deploy Machine Learning Pipeline on AWS Fargate](https://towardsdatascience.com/deploy-machine-learning-pipeline-on-aws-fargate-eb6e1c50507), Moez Ali provides a walk through of developing a machine learning pipeline with **[PyCaret](https://towardsdatascience.com/announcing-pycaret-an-open-source-low-code-machine-learning-library-in-python-4a1f1aad8d46)**, an open source machine learning library in Python to train and deploy supervised and unsupervised machine learning models in a low-code environment, with Flask and look at containerising and deploying that via AWS Fargate.

This is a super detailed walkthrough and you will dive deep into PyCaret. Moez is looking at growing the community around [this project](https://www.github.com/pycaret/pycaret) and looking for people to get involved. Why not take a look and provide feedback.

Thanks Moez.

### dev.to round up

There are some great posts on dev.to, so here is a round up of last week's posts that I felt was worth sharing.

**next.js on AWS ElasticBeanstalk**

Michael Weibel (@mweibel) walks you through[ deploying this React application framework on AWS ElasticBeanstalk](https://dev.to/mweibel/deploying-next-js-on-aws-elasticbeanstalk-ab4). You will be up and running in no time at all.

**ImageMagick**

Sergio Matone (@sw360cab) shows you how to create your own Layer on AWS Lambda, in his post [Creating custom AWS Lambda Layers from scratch: obtaining ImageMagick with Freetype support](https://dev.to/sw360cab/creating-custom-aws-lambda-layers-from-scratch-obtaining-imagemagick-with-freetype-support-4fn7), showing you how to create a layer that incorporates a couple of open source image related projects, ImageMacgick and freetype.

**Reduce costs when running Kubernetes**

If you are running and managing your own Kubernetes environments on AWS, then you probably want to read this post by Taufek Johar on [How to reduce your Kubernetes Cluster costs](https://dev.to/taufek/reduce-kubernetes-cluster-costs-on-aws-7b1).

**AWS EBS storage volume and your Docker container**

Staying with the container theme, we have this post from Dmitriy at appfleet on [How to attach an AWS EBS storage volume to your Docker container](https://dev.to/appfleet/how-to-attach-an-aws-ebs-storage-volume-to-your-docker-container-5920). If you want to understand more about storage on AWS and containers, then I suggest you take a look at this post.


### Workshop

**Amplify Social Network App**

In this workshop, you will use the open source project AWS Amplify to build twitter-like social media application. Along the way you will also get the chance to use some other open source projects too, such as Cyprus.

![This is what you will build](https://amplify-sns.workshop.aws/images/10_getting_started/final_architecture.png)

You can access the workshop clicking on the link below:

[AMPLIFY SOCIAL NETWORK APP WORKSHOP](https://amplify-sns.workshop.aws/en)

### AWS updates

**Open Distro for Elasticsearch**

In [An overview of the SQL Engine in Open Distro for Elasticsearch](https://opendistro.github.io/for-elasticsearch/blog/odfe-updates/2020/06/An-overview-of-the-SQL-Engine-in-Open-Distro-for-Elasticsearch/), Viraj Phanse provides an overview of the SQL engine that is one of the very nice features of Open Distro for Elasticsearch, including the new SQL CLI.

![show sql](https://opendistro.github.io/for-elasticsearch-docs/docs/images/workbench.gif)

![cli](https://opendistro.github.io/for-elasticsearch-docs/docs/images/cli.gif)

One of the neat things is the provision of both ODBC and JDBC drivers which mean you can treat Open Distro for Elasticsearch as just another target data source for your applications, including your BI applications like Tableau. When I have done workshops on Open Distro for Elasticsearch, this has been one of the most well received capabilities.

Thanks Viraj!

**LAMP is back**

In this post, [Introducing the new serverless LAMP stack](https://aws.amazon.com/blogs/compute/introducing-the-new-serverless-lamp-stack/), Benjamin Smith provides a treat for PHP developers everywhere. After a quick reminder/recap of the elements of the LAMP stack, Ben walks us through some of the challenges running that stack and how Serverless provides you with a compelling approach to solving those issues.

![architecture](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2020/06/01/Screenshot-2020-06-01-at-17.59.43.png)

This promises to be a great series, so keep posted I will share more as and when it's published. Better still, why not follow the @AWSOpen twitter handle and be notified.

**Wordpress**

Wordpress is an open source blogging/content project that has been around for some time and super popular. In fact, looking at Wikipedia I noticed that as of June 2019, it accounted for over 60% of all sites where a content management system was being used. When I speak with developers, Wordpress and PHP are still technologies that they start with or work on a regular basis.

If you run Wordpress on AWS, then [Optimising Wordpress performance with Amazon EFS](https://aws.amazon.com/blogs/storage/optimizing-wordpress-performance-with-amazon-efs/) from Francisco Gonzalez should be the top of your reading list. In this deep dive Francisco walks you through how you can optimize your architecture and improve your scalability and performance. No spoilers, so you will have to read the post.

Thanks Francisco!

**laravel-bridge**

**[bref](https://github.com/brefphp/bref)** is an open source project that provides tools to help easily deploy and run serverless PHP applications, and allows PHP developers to take advantage of modern application operational models like AWS Lambda, so they can focus more on writing PHP code and worry less about the underlying infrastructure.

Laravel is a popular PHP web application framework, and I have used this over the years so was delighted to see that this has been brought to AWS Lambda via bref in this project, [laravel-bridge](https://github.com/brefphp/laravel-bridge).

If you had not already, are a fan or have used PHP, then you should check this out.

**Going serverless with PHP**

Wow, a final post from Kpicaza on [Going serverless with PHP](https://medium.com/php-fad/going-serverless-with-php-f5a67cb3d67b), provides you with an overview of what your options are for running serverless PHP, some suggest use cases where it works well and then some interesting open source projects to help you.

**OpenFOAM**

[OpenFOAM](https://openfoam.org/) is the leading free, open source software for computational fluid dynamics (CFD), has become a key part of many engineering design processes. From aircraft design to modelling the blood flow inside our bodies, the ability to understand the behaviour of fluids has enabled countless innovations and improved the time to market for many products.

In this post, [OpenFOAM on Amazon EC2 C6g Arm based Graviton2 instances](https://aws.amazon.com/blogs/compute/c6g-openfoam-better-price-performance/), Neil Ashton (AWS), Karthik Raman (AWS) and Oliver Perks (Arm) walk you through in more detail what OpenFOAM is and then do some benchmark experiments to show the impact of running these workloads using these ARM based instance types.

No spoilers, but safe to say that you should check this post out if you are curious about how moving to these ARM based instances might help you improve your price/performance.
 

**Apache Arrow**

[Apache Arrow](https://arrow.apache.org/) is a cross-language development platform for in-memory data. It specifies a standardised language-independent columnar memory format for flat and hierarchical data, organised for efficient analytic operations on modern hardware.

Being columnar in memory, Apache Arrow manages memory more efficiently than row storage and takes advantage of modern CPU and GPU. 

![diagram](https://d2908q01vomqb2.cloudfront.net/77de68daecd823babbb58edb1c8e14d7106e83bb/2020/06/02/ML-Spark-Apache-2.jpg)

Itzik Jan and Avi Ben Yossef show you in [Training Multiple Machine Learning Models Simultaneously Using Spark and Apache Arrow](https://aws.amazon.com/blogs/apn/training-multiple-machine-learning-models-simultaneously-using-spark-and-apache-arrow/), how to integrate Apache Arrow with Amazon EMR when using code that you might have written in Python.

**ROS 2**

In last week's update I had a couple of items around the announcement of ROS 2 Foxy Fitzroy. This week I have a post from colleagues Matt Hansen, Aaron Blasdel, and Camilo Buscaron on [ROS 2 Foxy Fitzroy: Setting a new standard for production robot development](https://aws.amazon.com/blogs/robotics/ros-2-foxy-fitzroy-robot-development/).

![ros](https://d2908q01vomqb2.cloudfront.net/a9334987ece78b6fe8bf130ef00b74847c1d3da6/2020/06/10/image-2.png)

This is a great primer post if you wanted to get to understand in more detail they key differences and improvements with this release of ROS 2 over previous versions, and also provides a good summary of ROS vs ROS2.

**Part Two of Building a local based app**

[Last week](https://aws.amazon.com/blogs/compute/building-a-location-based-scalable-serverless-web-app-part-2/) I shared James Beswick's post around building a location based, scalable serverless web application. Well, [part two](https://aws.amazon.com/blogs/compute/building-a-location-based-scalable-serverless-web-app-part-2/) is out, so you can carry on where you left off.

This episode goes deep on using http api's, pub/sub and geohasing.

![architecture](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2020/06/09/ask-2-a.png)

Watch out for the final and concluding post.

**Amazon Linux 2 and FIPS**

Federal Information Processing Standard (FIPS) 140-2 specifies the security requirements for cryptographic modules that protect sensitive information. Industry standards such as the Payment Card Industry Data Security Standard (PCI DSS) also depend on FIPS 140-2 certified cryptographic modules to protect cardholder data or sensitive authentication data during storage, processing and transmission.

Ashneet Gujral and James Armitage's post, [Enabling FIPS mode in Amazon Linux 2](https://aws.amazon.com/blogs/publicsector/enabling-fips-mode-amazon-linux-2/), demonstrate how to enable FIPS mode in Amazon Linux 2 and verify that unauthorised cryptographic functions are not being used in OpenSSL or the OpenSSH server.

**Live Patching Linux on AWS Graviton2**

Keeping your Linux system up to date with the latest operating system and application software patches is one of the most effective ways to strengthen system security. 

KernelCare is a live patching system that patches Linux kernel vulnerabilities automatically, with no reboots. It maintains your kernel security without any service interruption or degradation. It promptly delivers the latest security patches for different Linux distributions and applies them automatically to the running kernel in nanoseconds.

KernelCare, which is available on AWS Marketplace, can live patch Amazon Elastic Compute Cloud (Amazon EC2) instances based on AWS Graviton2 Arm64 processors. This post explains, and demonstrates with a video, exactly how KernelCare live patches these new Amazon EC2 instances.

![how](https://d2908q01vomqb2.cloudfront.net/77de68daecd823babbb58edb1c8e14d7106e83bb/2020/06/03/KernelCare_Graviton2_HowPatchingApplied_Fig1.jpg)

To read the detailed walkthrough and watch the video, read on in [Live Patching Linux Without Downtime on AWS Graviton2 Instances](https://aws.amazon.com/blogs/apn/live-patching-linux-without-downtime-on-aws-graviton2-instances/) by Jim Jackson, president and CRO for KernelCare at CloudLinux.


**Case study: Stedi**

Open source projects are critical in building most software solutions these days, and in this case study, Stedi talk about their business, a commercial trading network to automate the trillions of dollars in B2B transactions exchanged by every company on Earth.

Stedi relies on two key open source AWS projects, AWS CDK and AWS Amplify, and this post talks about their business and how they are using AWS and open source to win.

![architecture](https://d2908q01vomqb2.cloudfront.net/cb4e5208b4cd87268b208e49452ed6e89a68e0b8/2020/06/04/Stedi-Diagram.png)


### Quick updates

**SQL Tools in Amazon Elasticsearch**

Amazon Elasticsearch Service now supports SQL Workbench and SQL CLI to run queries on Elasticsearch indexes with the conventional and familiar database language. SQL Workbench, a popular open source visual tool used to manage database environments, is now integrated in Kibana to view the results of SQL queries executed on Elasticsearch indexes. SQL CLI provides the flexibility to run ad-hoc or predefined queries from client applications written in different programming languages. New SQL features are supported on all domains running Elasticsearch 7.4.

All SQL support features are powered by Open Distro for Elasticsearch, an Apache 2.0-licensed distribution of Elasticsearch. To learn more about Open Distro for Elasticsearch, visit the website. 

Read more in the full announcement [here](https://aws.amazon.com/about-aws/whats-new/2020/06/improve-productivity-interactive-sql-tools-amazon-elasticsearch-service/).


### Open source builders

#### Are you an open source builder?

If you are an open source builder and want to share your project or your open source story please get in touch. I am always looking to talk with people and write these up or video them.

---

### Share your open source projects 

Do you have some content you want to share with a broader audience? We are always looking for guest content for the AWS Open blog. Please get in touch (via comments below) and I would love to speak with you about what you are doing in open source. We are always looking for interesting new content.

The best submissions will get some AWS Credit codes as a thank you.


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)8