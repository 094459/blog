---
title: 'AWS open source news and updates No. 38'
date: '2020-10-05'
tags : [ oss-newsletter ]
---
## October 5th - Instalment #38

Week No.38 and following on from the very first CDK Day, there is plenty of AWS CDK stuff including a link to the recording of the event if you missed it. Aside from that, there is the usual round up of blog posts, including another excellent post featuring honeycomb.io doing some benchmarks on running AWS Graviton2 instance types on a number of open source projects, the latest new AWS related open source projects, events, case studies and we also have a workshop for you, covering how to get started with TorchServe.

### Events for your diary

**The New Playbook**
**Oct 7, 2020, 8:00 PM - 9:30 PM BST**

Given the importance of community in open source, this event is something you will want to register for and check out. Mark Birch is seasoned and experienced when it comes to community building, and he recently wrote a how-to book about creating communities, full of nuts and bolts advice along with case studies. This is your chance to listen and ask him questions you might have on this topic.

**All Things Open**
**October 19th|20th**

All Things Open is one of the must attend events for open source folks. 

**AWS Copilot**
**October 19, 2020, 1:00 PM (PT) | 4:00 PM (ET)**

AWS Copilot is a command line interface tool that helps customers develop, release, and operate containerized applications on AWS. AWS Copilot creates all the infrastructure and artifacts required to run a production-ready service on Amazon ECS and AWS Fargate, including task definitions, image repositories, and AWS resources like load balancers and deployment pipelines. In this tech talk, you will learn how to leverage AWS Copilot to containerize applications and deploy production ready micro-services faster on Amazon ECS, with code demos.

**KubeFlow**
**October 23, 2020, 1:00 PM (PT) | 4:00 PM (ET)**

Distributed training on Kubernetes is both hard to set up and optimize for ML jobs. In this tech talk, you'll learn how to do distributed training in a Kubeflow Pipelines workflow with a Mask-RCNN model in PyTorch. We'll set up an end to end training job for a computer vision use case on multiple GPU nodes and then deploy that model onto a production endpoint using Kubeflow Pipelines for orchestration and Amazon Sagemaker Components for Kubeflow Pipelines. Our model is a Mask-RCNN model from the Detectron2 model zoo trained on the COCO2017 dataset and further fine-tuned on a custom dataset with aerial imagery.

**cdk8s**
**October 27, 2020, 11:00 AM (PT) | 2:00 PM (ET)**

The new CDK for Kubernetes (cdk8s) is an open-source project that lets you define Kubernetes applications and reusable components using familiar programming languages. In this tech talk, learn how csk8s works locally on your machine and generates standard Kubernetes YAML data, so you can use it with any Kubernetes cluster running anywhere, including on-premises and the cloud.

#### CDK Day

If you missed it last week, CDK was a huge success. Matt Coulter shared [this tweet](https://twitter.com/094459/status/1311756173549461505?s=11) of where the 1000+ participants attended from. If you want to see what you missed, Matt provided a link to the recording of the session, which I have included here. 5 hours of amazing content, and a new mascot? Welcome Pancakes, and I can't wait for my laptop sticker of you.

{% youtube qJutZqXMdgM %}

**projen**

[projen](https://github.com/eladb/projen) is an (alpha currently) open source project from Elad Ben-Israel called Projen, which you can think of as a CDK for software projects which you will be able to check out in the CDK Day video (50min into the video in the link above). Elad is looking for contributors and also maintainers, so if this is a project you are really enjoying, get in touch.

**CDK Weekly**

Want to keep up with the latest news from AWS CDK? Well, Sebastian Korfmann has you covered with his [CDK Weekly newsletter](https://www.cdkweekly.com/). Sign up to his weekly newsletter and let all that news and cool info come to you. Seriously good stuff in here. Thanks Seb.

**Other CDK news**

Prior to CDK Day, Amazon and AWS Global CTO Werner talked about AWS CDK extensively during the keynote, and when that video is available I will share in a future version of this newsletter. You can also read about it in this post from[ Why Amazon Is Bullish on AWS Cloud Development Kit](https://www.datacenterknowledge.com/amazon/why-amazon-bullish-aws-cloud-development-kit) which provides a nice summary of the key talking points.

### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to Ravi Itha, Sara Miteva, Ali Spittel, Viraj Phanse, Dave Bechberger, Moises Hernandez Fernandez, Anish Mohan, Haibin Lin, Przemyslaw Tredak, Joseph Keating, Charles Gibson, Sean McGrail, Chirag Oswal, Anchit Nishant, Preenesh Nayanasudhan, Shreyas Subramanian, Andrew Packer, Vidhi Kastuar, Julie Dam, Vijay Injam, Kevin Fallis, Irshad Buchh and Efe Karakus, Petro Kashlikov, Campion Fellin, Jason Cutrer, Elad Ben-Israel, Tobias Haindl, Didier Durand, Sang Jin Lee, Aram Alipoor, James Weakley, Paul Micheli, Mark Birch and Liz Fong-Jones.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

**flaker**

[flaker](https://github.com/jamesweakley/flaker) this tool from James Weakley is perfect for those customers who are using SnowFlake looking to generate fake test data. He wrote up a nice walkthrough too, [Generating realistic looking fake data in Snowflake](https://medium.com/@jamesweakley/generating-realistic-looking-fake-data-in-snowflake-aab18cc95c7). Nice work James.

![image](https://miro.medium.com/max/1338/1*49gfmEwuTQc8FGx4gI37rQ.png)

**DynamoQuery**

[DynamoQuery](https://github.com/altitudenetworks/dynamoquery) this open source project from Altitude Networks provides and Object-Relational-Mapper (ORM) for interacting with Amazon DynamoDB, and fills a hole for Python developers who might have been looking for this. They have been using this project in house for a while now, so you know that it should be good to go. How will you use it and perhaps contribute to this project? Check out the blog, [Introducing DynamoQuery: Python AWS DynamoDB ORM](https://blog.altitudenetworks.com/dynamoquery-python-dynamodb-orm/) for more details. 

**tagger**

[tagger](https://github.com/IT-EXPERTS-AT/tagger) is an open source tool from Tobias Haindl that will help you to stay on top of your AWS resource tagging. Tobias has also written this great post that shows you how you can use this tool to report/audit on your current tagging coverage, and then use it to update/apply tags to your resources. I think this is going to be a very popular tool, as good tagging hygiene is foundational to good Cloud governance and management.

**kms-issuer**

[kms-issuer](https://github.com/Skyscanner/kms-issuer) this open source tool from the lovely folks at Skyscanner is a cert-manager Certificate Request controller that uses AWS KMS to sign the certificate request.

**aws-cost-saver**

[aws-cost-saver](https://www.npmjs.com/package/aws-cost-saver) is a useful tool for developers who want to make sure they are only keeping services up they need. Using this cli, you will be able to view and then shutdown resources. Aram Alipoor provides a disclaimer, so use at your own discretion/risk.

**amictl**

[amictl](https://github.com/brunopadz/amictl) this tool from Bruno Padilha is a super simple cli app to control your AMIs and Images. One of the nice features of this tool is the ability to quickly list costs for the different instance types. Nice.

**GitHub Actions**

[AWS SDK workflows on Github CI/CD](https://github.com/didier-durand/aws-workflows-on-github/) this collection of GitHub Actions and Workflows from Didier Durand provide common re-usable components that you can use in the automation of the setup of various AWS Services. These scripts are based on CLI commands of the AWS SDK to allow complete automation, basis of best DevOps practices.

**kconnect**

[kconnect](https://github.com/fidelity/kconnect/) is a project from Fidelity that provides you with a way to find and connect to your Kubernetes clusters, with the tool works across a number of different developer setups but also supports Amazon EKS as well as others.

**Microtica**

Microtica is an open source automation platform that helps accelerate the configuration of your cloud environments whilst maintaining consistency by using templates that are then executed via AWS Cloud Formation. There are a number of samples components provided, and the project is looking for more. Sara Miteva has also written a very clear post on dev.to on how to get started, so make sure you check out [Microtica—the DevOps automation platform with open-source components](https://dev.to/microtica/microtica-the-devops-automation-platform-with-open-source-components-2gdh)  

**Amazon Interactive Video Service**

Last week we had [Enhance your Android ecommerce app with Amazon Interactive Video Service](https://aws.amazon.com/blogs/media/enhance-your-android-ecommerce-app-with-amazon-interactive-video-service/) from Sang Jin Lee, this week he is back with [Build an Android App with a scrollable feed of live streams](https://aws.amazon.com/blogs/media/build-an-android-app-with-a-scrollable-feed-of-live-streams/). This post and project will get you up and running with creating an application to provide multiple live stream feeds, which you can use as the base for your own projects.

![aivs](https://d2908q01vomqb2.cloudfront.net/fb644351560d8296fe6da332236b1f8d61b2828a/2020/09/30/Picture9-2.png)

**Scaling Game Servers**

[Game Server Hosting on AWS Fargate](https://github.com/aws-samples/fargate-game-servers) This repository contains an example solution on how to scale a fleet of game servers on AWS Fargate on Elastic Container Service and route players to game sessions using a Serverless backend. Game Server data is stored in ElastiCache Redis. All resources are deployed with Infrastructure as Code using CloudFormation, Serverless Application Model, Docker and bash/powershell scripts. By leveraging AWS Fargate for your game servers you don't need to manage the underlying virtual machines.

![arch](https://github.com/aws-samples/fargate-game-servers/raw/master/Architecture_small.png)

### Open Distro for Elasticsearch 1.10

[Open Distro for Elasticsearch 1.10.1 is now available](https://opendistro.github.io/for-elasticsearch/blog/odfe-updates/2020/09/Open-Distro-for-Elasticsearch-1.10.1-is-released/) Viraj Phanse writes about the general availability of the latest release of Open Distro for Elasticsearch, version 1.10.1.

Open Distro for Elasticsearch 1.10.1 includes version 7.9.1 of Open Source Elasticsearch and Kibana, plus Apache-2.0-licensed extensions that provide alerting, anomaly detection, index management, performance analysis, security, SQL, and k-NN features. Other components, including ODBC and JDBC drivers, a command-line SQL client, and a command-line performance visualisation tool (“PerfTop”) are also available to download.

From the release highlights, we can see:

> * Anomaly Detection supports three different types of sample detectors and corresponding indices that allow users to detect sample anomalies using logs related to HTTP response codes, eCommerce orders, and CPU and memory of a host.
> * The Alerting feature supports email destinations to send notifications without using a web hook.
> * The updated Kibana Security Plugin streamlines security workflows, improves usability and adds audit and compliance logging configuration.
> * Anomaly Detection supports a command line interface that allows users to create, start, stop and delete detectors, and work with multiple clusters using named profiles.
> * K-NN supports warmup API that allows users to explicitly load indices’ graphs used for approximate k-NN search into memory before performing their search workload. With this API, users no longer need to run random queries to prevent initial latency penalties for loading graphs into the cache.

Read more about it on the Open Distro for Elasticsearch [blog here](https://opendistro.github.io/for-elasticsearch/blog/).

**Elastcisearch**

[Normalize data with Amazon Elasticsearch Service ingest pipelines](https://aws.amazon.com/blogs/big-data/normalize-data-with-amazon-elasticsearch-service-ingest-pipelines/) this post brought to you from  Vijay Injam and Kevin Fallis explores ingest pipelines and how to use a number of different open source tools to help move data from different sources into Amazon Elasticsearch.

![ingest](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2020/07/27/NormalizeDataElasticsearch1.png)

This post provides three solutions/patterns that will help you design your own ingest pipelines, thinking about how you normalise data, fix ingestion issues and look at different pre-processors for the data.

### Workshops

**TorchServe on AWS**

The TorchServe on AWS Workshop walks you through the necessary information and AWS hands on learning experience to further your understanding of PyTorch model serving on AWS.

This is the perfect way to get started with this, going from an introduction into what is TorchServe to helping you get up and running in around 3 hours. You will need an AWS Account to get the most from this workshop, and the workshop will walk you through how to set everything you need to get started.

Check out the workshop at the following link: [https://torchserve-on-aws.workshop.aws/en/](https://torchserve-on-aws.workshop.aws/en/)

### AWS open source posts

**cdk8s**

[Announcing Java support for cdk8s](https://aws.amazon.com/blogs/containers/announcing-java-support-for-cdk8s/)  Campion Fellin introduces Java support for cdk8s, the Cloud Development Kit for Kubernetes, which means you can now use cdk8s in Java, Python and Typescript. The post takes you through a sample Springboot application and how you can use cdk8s to configure and deploy that application effortlessly. Make sure you check out the Events section above for a webinar later this month on cdk8s.

**k3s**

[Using the K3s Kubernetes distribution in an Amazon EKS CI/CD pipeline](https://aws.amazon.com/blogs/opensource/using-the-k3s-kubernetes-distribution-in-an-amazon-eks-ci-cd-pipeline/) by Petro Kashlikov introduces what K3s is and then shows you how this fits in/use cases within your own AWS environments. So what is K3s? K3s is an open source, lightweight, and fully compliant Kubernetes distribution that is less than 100 MB in size and designed for IoT, Edge, and CI/CD environments and being small, the startup time is about 40 seconds. So read on to find out in this particular example, adding unit and integration testing.

**Copilot**

[Developing an application based on multiple microservices using AWS Copilot and AWS Fargate](https://aws.amazon.com/blogs/containers/developing-an-application-based-on-multiple-microservices-using-the-aws-copilot-and-aws-fargate/) this duet from Irshad Buchh and Efe Karakus show you how you can use Copilot, a tool I have talked about in previous newsletters that is (an open source) command line interface (CLI) to build, release, and operate production ready containerised applications on Amazon Elastic Container Service (Amazon ECS) and AWS Fargate, to deploy a sample application. What will you build? Well check the post to find out...

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2020/09/26/Figure1.png)

Make sure you check out the Events section as we are running a webinar covering Copilot later in October.

**Chalice**

[AWS Chalice now supports Amazon Kinesis and Amazon DynamoDB Streams](https://aws.amazon.com/blogs/developer/aws-chalice-now-supports-amazon-kinesis-and-amazon-dynamodb-streams/) James Saryerwinnie is back again with another AWS Chalice post, this time some of the new features in 1.21 release including how to integrate Amazon Kinesis and Amazon DynamoDB into your application. As always, James walks you through how with an example.

**Apache Active MQ**

[Implementing FIFO message ordering with Amazon MQ for Apache ActiveMQ](https://aws.amazon.com/blogs/compute/implementing-fifo-message-ordering-with-amazon-mq-for-apache-activemq/) Ravi Itha's post talks about the role of messaging and how this plays a crucial part on modern application design patterns, introducing some open source tools that play in this space, such as Apache ActiveMQ, and then goes on to explore a topic that often comes up when architecting solutions in this space: how to manage use cases where message ordering is critical. Ravi looks at this in detail and also shares how Amazon MQ can simplify your setup and operations of Apache ActiveMQ.

![activemq](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2020/09/30/utilization-test-1024x331.png)

**Amazon Timestream and Grafana**

[Store and Access Time Series Data at Any Scale with Amazon Timestream – Now Generally Available](https://aws.amazon.com/blogs/aws/store-and-access-time-series-data-at-any-scale-with-amazon-timestream-now-generally-available/) great post from Danilo Poccia that introduces Amazon Timestream. Amazon Timestream is a time series database that makes it easy to collect, store, and process trillions of time series events per day up to 1,000 times faster and at as little as to 1/10th the cost of a relational database. Time series are a very common data format that describes how things change over time. Some of the most common sources are industrial machines and IoT devices, IT infrastructure stacks (such as hardware, software, and networking components), and applications that share their results over time. Time series information is often integrated with open source tools, and in the past I have used tools like Grafana or Kibana to dashboard this data in a way that you can begin to use to provide actionable insights. In this post, Danilo shows how you can integrate this with open source dashboard tools like Grafana, and provides a bunch of open source tools to get you going. GitHub repository [here](https://github.com/awslabs/amazon-timestream-tools). 

![dashbiard](https://d2908q01vomqb2.cloudfront.net/da4b9237bacccdf19c0760cab7aec4a8359010b0/2020/09/25/amazon-timestream-plugin-grafana-1024x568.png)

[Now you can add Amazon Timestream to your Grafana observability dashboard](https://grafana.com/blog/2020/09/30/now-you-can-add-amazon-timestream-to-your-grafana-observability-dashboard/) post from Julie Dam at Grafana Labs provides some more details and sample dashboards.

**Apache Spark**

[Running on-demand, serverless Apache Spark data processing jobs using Amazon SageMaker managed Spark containers and the Amazon SageMaker SDK](https://aws.amazon.com/blogs/machine-learning/running-on-demand-serverless-apache-spark-data-processing-jobs-using-amazon-sagemaker-managed-spark-containers-and-the-amazon-sagemaker-sdk/)  Shreyas Subramanian, Andrew Packer, and Vidhi Kastuar win the prize for longest blog post title this week, but don't worry, the post is just the right size to show you how you can use Spark containers within Amazon SageMaker for data preparation, training models and running model inference. They share how you can take advantage of the built-in Spark container on Amazon SageMaker to focus on more important aspects of preparing and preprocessing data instead of spending time tuning, scaling, or managing Spark infrastructure, developers can focus on core implementation.

**BERT**

[BERT inference on G4 instances using Apache MXNet and GluonNLP: 1 million requests for 20 cents](https://aws.amazon.com/blogs/machine-learning/bert-inference-on-g4-instances-using-apache-mxnet-and-gluonnlp-1-million-requests-for-20-cents/) this collaboration from Moises Hernandez Fernandez, Anish Mohan, Haibin Lin, and Przemyslaw Tredak will help you understand how to architect an efficient solution for performing BERT inference tasks on EC2 G4 GPU instances, showing MXNet optimizations that boost GPU performance that can achieve speeds up to twice as fast in both question answering and classification tasks. They go onto show how g4dn.xlarge instances offer lower latency than EC2 CPU instance, and how g4dn.xlarge is 3.8 times better than c5.24xlarge on average. When it comes to optimisation of your production models, then this is a must read post.

**Altimeter**

[Graph your AWS resources with Amazon Neptune](https://aws.amazon.com/blogs/database/graph-your-aws-resources-with-amazon-neptune/) by Dave Bechberger shows you how you can use Altimeter, an open-source project from Tableau Software, LLC that scans AWS resources and links these resources into a graph which you can then store, query, and visualize in Amazon Neptune. You can query the graph to examine the AWS resources and their relationships in your AWS account, so for example, you can query for resources or pathways that expose a cluster with a public IP address to check for security and compliance.

![arch](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2020/09/23/GraphingResourcesNeptune7.png)

**BigBlueButton**

[Deploying open source web conferencing solution BigBlueButton on AWS](https://aws.amazon.com/blogs/opensource/deploying-an-open-source-web-conferencing-solution-bigbluebutton-on-aws/)  Chirag Oswal, Anchit Nishant, and Preenesh Nayanasudhan huddle together to bring you this awesome post on how to deploy the open source web conference solution BigBlueButton. BigBlueButton is an open source web conferencing system designed for online learning. It offers a pure HTML5 client. It has the core features you would expect in a commercial web conferencing system, but under an open source license. The features include real-time sharing of audio, video, presentation, and screen, along with collaboration tools such as a whiteboard, shared notes, public/private chat, and polling. If you are looking for an open source tool like this, then check this out. They provide scripts to help make the deployment process painless so you should be up and running in second to no time.
 
**AWS SDK**

[Client Updates in the Preview Version of the AWS SDK for Go V2](https://aws.amazon.com/blogs/developer/client-updates-in-the-preview-version-of-the-aws-sdk-for-go-v2/) by Sean McGrail provides an update on the performance improvements, better error handling and extensibility of the AWS SDK for GO project but also provide insights on how they are using [Smith](https://awslabs.github.io/smithy), although open source project from AWS as part of that rewrite.

**Stacker, InSpec, cfn-python-lint**

[Multi-environment CI/CD pipelines with AWS CodePipeline and open source tools](https://aws.amazon.com/blogs/opensource/multi-environment-ci-cd-pipelines-with-aws-codepipeline-and-open-source-tools/) by Joseph Keating and Charles Gibson show you how to use popular open source tools (Stacker, InSpec and cfn-python-lint) in conjunction with AWS Developer Tools services to build, validate, and deploy infrastructure stacks across multiple accounts in a secure manner. cfn-lint is used to validate the templates, InSpec for testing, and stacker to perform the deployment of the CloudFormation stacks. This post will walk you through building this solution, which you can use as the foundation for your own integrations and application automation.

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2020/09/01/gibscnch_Multi-Env-CD_F1-resize.jpg)

### Case Study

**honeycomb.io & AWS Graviton2**

[Observations on ARM64 & AWS’s Amazon EC2 M6g Instances](https://www.honeycomb.io/blog/observations-on-arm64-awss-amazon-ec2-m6g-instances/) this post from By Liz Fong-Jones at [Honeycomb.io](https://www.honeycomb.io/why-honeycomb/) is my favourite post this week and is a takedown of how engineering teams can start looking at AWS Graviton2 processor architecture to start looking at the impact of recompiling their software might be able to achieve. I don't want to give any spoilers otherwise you will not read the post, but you will not be surprised to hear that they give it the big thumbs up. In this post they talk about the process of testing on this architecture including the need to re-compile many open source tools and software projects. The good news though, the overall work only took them a few weeks. So read on and then ask yourself what could you do with AWS Graviton2 instance types....

![diag](https://www.honeycomb.io/wp-content/uploads/2020/03/Screenshot-2020-03-11-at-12.49.53-PM-1.png)

### AWS Partner Network

**Amazon FSx for Lustre**

[Breaking Down High Performance Computing Barriers with Amazon FSx for Lustre](https://aws.amazon.com/blogs/apn/breaking-down-high-performance-computing-barriers-with-amazon-fsx-for-lustre/) Jason Cutrer, CEO at Six Nines talks about Lustre, a powerful open source, Linux-compatible, parallel file system that is popular in the high performance computing (HPC) community and a range of industry verticals. In this post Jason covers some of the recent improvements to this project as well as some common use cases that benefit from Lustre high performance filesystems. Whether you are interested in HPC, Bioinformatics, AI or perhaps one of the industry verticals such as manufacturing or the semiconductor industry, if you need fast access to data with high throughput, check Jason's post out.

**Datastax**

Check out [this podcast](https://www.datastax.com/resources/podcast/open-source-sustainability) featuring the always very listenable Matt Asay, talking about his journey through open source and behind-the-scenes stories on what gives these communities their strength: its people and their voices.

**Indigo**

Indigo and Amazon released last week a new source for analysis ready radar data. This data set is the entire processed Sentinel-1 ARD imagery record for the continental United States that is updated daily and provides 40 TB+ source for open radar data that is ready for use. David Potere from Indigo said:

> Last month we used this same feed to cover the Derecho storm that damaged more than 3 million acres of Iowa corn and beans.
> 
Check it out [here](https://registry.opendata.aws/sentinel-1-rtc-indigo/).

### Latest blog posts

**AWS Amplify**

[Enforcing attribute uniqueness in Cognito with AWS Amplify and React](https://dev.to/andthensumm/enforcing-attribute-uniqueness-in-cognito-with-aws-amplify-and-react-263f) Matt Marks provides this walkthrough on how create an email validation mechanisms for your AWS Amplify applications that are using Congnito, which will  trigger a check to search Cognito for users who are already signed up with that email attribute.

**How Kubernetes development works**

Ever wondered how development on Kubernetes takes place? Well wonder no more. Hat tip to Michael Hausenblas for pointing me in the general direction of this. Check out the Github workflow page [here](https://www.kubernetes.dev/docs/guide/github-workflow/). 

![workflow](https://www.kubernetes.dev/docs/guide/git_workflow.png)

**AWS Serverless Application Model (SAM)**

[AWS Serverless Application Model : Guide to writing your first AWS SAM Application](https://www.rajanpanchal.net/complete-guide-to-writing-your-first-aws-sam-application/) a short tutorial from Rajan Panchal that will guide you through installing and then creating your first application using AWS SAM.

**AWS Amplify: A beginners guide**

[Building a Full Stack Application with AWS Amplify: A Beginner-Friendly Guide](https://dev.to/aws/build-your-first-fullstack-application-on-aws-4gh5) Ali Spittel, Senior Dev Advocate over in the AWS Amplify team has brought her passion of tech and art together in this walkthrough guide to creating a project I know everyone needs: a tool to view, create and manage your gifs!

**AWS Elastic Beanstalk and PHP**

[Upgrade AWS Elastic Beanstalk PHP Major version](https://dev.to/paulmicheli/upgrade-aws-elastic-beanstalk-php-major-version-5do) Paul Micheli shares a very quick how to upgrade the major PHP versions for your Elastic Beanstalk applications. 

### Quick updates

**AWS CloudFormation Guard**

AWS CloudFormation announces the general availability (GA) of AWS CloudFormation Guard (cfn-guard), which enhances the preview release of cfn-guard (June 2020) with new features. Cfn-guard is an open-source command line interface (CLI) that checks CloudFormation templates for policy compliance using a simple, policy-as-code, declarative language. I have covered this project in earlier editions of this newsletter, so the GA announcement is very welcome.

**Bonus** 

Check out Rahul Garg, Senior Product Manager in the CloudFormation team talk in this [Twitch Whats New E12](https://www.twitch.tv/videos/758603506?filter=all&sort=time) episode about AWS CloudFormation Guard. It starts in at 24 mins. Also, if you haven't watched these videos before then defo check them out. There is always great content and interesting talks with a variety of guests.

**AWS AppSync**

You can now enable AWS WAF integration for your GraphQL APIs in AWS AppSync, making it easier to protect your APIs against common web exploits. AWS AppSync is a managed GraphQL service that simplifies application development by letting you create a flexible API to securely access, manipulate, and combine data from one or more data sources with less network calls. With AppSync, you can build scalable applications, including those requiring real-time updates, on a range of data sources such as NoSQL data stores, relational databases, HTTP APIs, and your custom data sources with AWS Lambda.

AWS WAF is a web application firewall that helps to protect your web applications from common web exploits that could affect application availability, compromise security, or consume excessive resources. AWS WAF gives you control over which traffic to allow or block to your web applications by defining customisable web security rules. To learn more visit the product page here.

You can use AWS WAF to protect your AppSync GraphQL APIs against attacks such as SQL injection and cross-site scripting (XSS). AWS WAF gives you the flexibility to define rule statements anywhere within the web request, such as HTTP headers or body, allowing you to filter requests based on IP address, country, field size length, requests, and/or strings or regular expression patterns. You can also implement rate-based rules, which can be used to slow down brute force attacks and limit API usage based on IP addresses. Furthermore, AWS Managed Rules for AWS WAF help you protect your applications without the need to create or manage the rules directly.

Read the blog post here, [AppSync adds support for AWS WAF](https://aws.amazon.com/blogs/mobile/appsync-waf/)

**SQL Server on Linux**

With AWS Launch Wizard, you can now easily deploy SQL Server Always On availability groups on Ubuntu Server, making it easier for you to run SQL Server workloads on free Linux-based operating systems, without the need to buy Windows Server licenses. AWS Launch Wizard offers a guided way of sizing, configuring, and deploying AWS resources for third party applications, such as Microsoft SQL Server Always On and HANA-based SAP systems, without the need to manually identify and provision individual AWS resources. Previously, customers could use AWS Launch Wizard to easily perform SQL Server Always On deployments on Windows Server. Now, you are able to leverage the same ease of use to perform SQL Server Always On deployments on Linux and save Windows Server licensing costs.  

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen).

### Your feedback matters!

I have put together a short feedback survey, which I would ask you to take - it will take no more than 2 minutes. You can access [here](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn). Many thanks!

[Take the survey](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn)
