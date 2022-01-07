---
title: 'AWS open source news and updates No. 32'
date: '2020-08-24'
tags : [ oss-newsletter ]
---
## August 24th - Instalment #32

Week No.32 and after two weeks taking some time off visiting sunny Scotland, I return refreshed with a bumper edition with the pick of posts from the past few weeks. As always, some great posts and projects as well as some events you might want to add to your diary and a few customer case studies for you to check out.

### Your feedback matters!

I have put together a short feedback survey, which I would ask you to take - it will take no more than 2 minutes. You can access [here](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn). Many thanks!

[Take the survey](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn)

### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to Vincent Voyer, Chris Downing, Michael Ferguson, Satoshi Kuramitsu, Igor Tavares, Brian Caffey, James Beswick, Ben Ellerby, Ben Smith, Efe Karakus, Eric Johnson, Kunal Ghosh, Gagan Brahmi, Anand Krishna, Ryan Niksch, Adrian Hornsby, Varun Jewalikar, Trevor Sullivan, Ken Collins, Cami Williams, Moheeb Zara, Adrian Hornsby, Varun Jewalikar, Derek Tan, Fei Lang, Kinnar Sen, Josiah Davis, Charles Frenzel, Chen Wu, James Saryerwinnie, Phi Nguyen, Xiang Song, Muhyun Kim, Hussain Karimi, Jiyang Kang, Kyle Lee, Luis Colon, Raisa Hashem, Josh Joy, Jay Pipes, Michael Hausenblas, Nathan Taber,  Turgay Özgür, Onuralp Taner and Prasad Rao.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Events for your diary

Check out these events happening this week and later on.

**Cloud Data Lake**
**August 27th, 5PM BST**

[Cloud Data Lake](https://pages.databricks.com/202009-US-EV-VirtualWorkshop-CDLDevDay-Nationwide_04.Live-Registration-page.html?utm_source=bambu&utm_medium=social&utm_campaign=advocacy&blaid=758480) a virtual workshop where you will learn best practices for organisations to use powerful open source technologies to build and extend your AWS investments to make your data lake analytics ready.


**End-to-End Computational Fluid Dynamics**
**2nd September, 4PM BST**

[AWS Automotive Webinar](https://pages.awscloud.com/GLOBAL-event-OE-e2e-cfd-webinar-2020-reg-event.html) - The focus of this webinar will be how to run a complete end-to-end CFD workflow for a realistic road-car model. Starting with CAD and pre-processing we will firstly show how these steps can be done remotely on AWS with minimal data transfer. Secondly we will solve a high-fidelity case using the open-source code OpenFOAM to demonstrate how AWS can improve turn-around time for large cases

**Machine Learning workshop**
**September 10th, 2PM BST**

[Unifying Data Pipelines and Machine Learning with Apache Spark™ and Amazon SageMaker](https://awsmldevdayeast.splashthat.com/?utm_source=bambu&utm_medium=social&utm_campaign=advocacy&blaid=748357) a databricks and Immuta workshop to learn how Unified Data Analytics can bring Data Science, Business Analytics and engineering together to accelerate your Data and ML efforts.

**Robotics Keynote**

For those that missed the Cloud Robotics summit this week, you can check the keynote video from Roger Barga and Brian Gerkey.

{% youtube LYWVF4bGHjs %}

### Open source builders

[How to become a Redis maintainer one contribution at a time](https://aws.amazon.com/blogs/opensource/how-to-become-a-redis-maintainer-one-contribution-at-a-time/) this post from Matt Asay, he talks with Madelyn Olson, a long time contributor and now maintainer of Redis. If you want a great insight into the journeys that developers have trodden on the path to becoming open source contributors and maintainers, or if you want to know a little more about the Redis community, or how AWS is contributing upstream changes to projects like this, then you need to read this post. 

### Latest from open source projects

**cloud-sniper**

[cloud-sniper](https://github.com/cloud-sniper/cloud-sniper) this open source project is a platform to help security operations teams by aggregating, correlating and analysing the various infrastructure logs that they can then use to respond to security incidents. This increase in visibility allows those security operations teams to manage security incidents across the organisation and help improve their security posture.

![architecture](https://github.com/cloud-sniper/cloud-sniper/raw/master/images/deployment.png)

**http-desync-guardian**

[http-desync-guardian](https://github.com/aws/http-desync-guardian) is a new open source library from AWS that provides a way for you to analyse HTTP requests to minimize risks of HTTP Desync attacks. HTTP/1.1 went through a long evolution since 1991 to 2014, which means there is a variety of servers and clients, which might have different views on request boundaries, creating opportunities for desynchronisation attacks (a.k.a. HTTP Desync). **http_desync_guardian** library is designed to analyze HTTP requests to prevent HTTP Desync attacks, balancing security and availability. It classifies requests into different categories and provides recommendations on how each tier should be handled.

Check out [this Twitter thread](https://twitter.com/colmmacc/status/1295461636241854469?s=11) from [Colm MacCárthaigh](https://twitter.com/colmmacc) for additional details, as well as this post from Jessica Haworth [AWS launches open source tool to protect against HTTP request smuggling attacks](https://portswigger.net/daily-swig/aws-launches-open-source-tool-to-protect-against-http-request-smuggling-attacks).

**SpaceSiren**

[SpaceSiren](https://github.com/spacesiren/spacesiren) is an open source project that provides a honey token management and alert system for AWS. It allows you to create these honey tokens at scale, managing tens of thousands with close to no cost (they provide some cost guidelines, at approx $1-$5 per month). The project provides an an API Gateway to create no-permission AWS IAM users and access keys for those users. You sprinkle the access keys wherever you like, for example in proprietary code or private data stores, and if one of those sources gets breached, an attacker is likely to use the stolen key to see what they can do with it. You will receive an alert via email, PagerDuty, Slack and Pushover that someone attempted to use the key.

![honey](https://github.com/spacesiren/spacesiren/raw/master/docs/images/screenshots/token-api.png)

Great documentation and installation instructions (as well as automated deployment via Terraform) makes this a project you should check out.

**Serverless Video Processing**

[Serverless Video Processor](https://github.com/cbttrevor/aws-serverless-video-processor) is an open source project from Trevor Sullivan that helps you build a solution to perform video conversions using AWS Fargate, triggered by uploads to an Amazon S3 Bucket. Trevor provides a video to help you build this, so you can use this as the base for your own projects or applications.

**Pulse Oximetry tracker**

[Pulse Oximetry tracker](https://github.com/aws-samples/aws-serverless-oxygen-monitor-web-bluetooth.git) is a new open source project from Moheeb Zara that allows you to build an example solution for collecting, tracking, and sharing pulse oximetry data for multiple users. It takes oxygen saturation measurements as manual input or a BerryMed pulse oximeter connected to a browser using Web Bluetooth. You can read the supporting blog post, [Building a Pulse Oximetry tracker using AWS Amplify and AWS serverless](https://aws.amazon.com/blogs/compute/building-a-pulse-oximetry-tracker-using-aws-amplify-and-aws-serverless/).

![architecture](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2020/08/07/om-app-deployed-1024x993.png) 

**Amplify Flutter**

[Amplify Flutter](https://github.com/aws-amplify/amplify-flutter) allows you to extend your Flutter projects to include AWS Amplify, and leverage the plugins that integrate into AWS. AWS Amplify provides a declarative and easy-to-use interface across different categories of cloud operations. Our default implementation works with Amazon Web Services (AWS), but AWS Amplify is designed to be open and pluggable for any custom backend or service. Amplify for Flutter currently supports iOS and Android platforms, is in preview, and is not recommended for production use at this time. You can read the blog post, [Announcing AWS Amplify Flutter (Developer Preview)](https://aws.amazon.com/blogs/mobile/announcing-aws-amplify-flutter-developer-preview/) from Ashish Nanda that walks you through getting started with this project.

![arch](https://d2908q01vomqb2.cloudfront.net/0a57cb53ba59c46fc4b692527a38a87c78d84028/2020/08/19/AmplifyFlutterDesignArchitecture.jpg)

**dr-sven**

[dr-sven](https://github.com/MeStrak/dr-sven) this open source tool is a data health checker which performs a checkup on your data to give you a simple indication of whether it's in good shape or not. You define some rules, and then you use this to query/check a data set and the tool will produce a report and output that you can check. This is a simple project that does not provide extensive rules, but might be useful if you are looking for a simple and easy to use data validation tool. MeStrak also put together a nice blog post on getting started, which you can check out [here](https://dev.to/mestrak/introducing-dr-sven-14m9).

### Fresh blog posts for your reading pleasure

**Lamby**

[Full Stack Serverless with Rails & AWS SAM/Lambda](https://dev.to/aws-heroes/full-stack-serverless-with-rails-aws-sam-lambda-1jcm) post from Ken Collins, AWS Hero, announcing some major updates to the open source [Lamby](https://lamby.custominktech.com/) project, that allows you to run Ruby on Rails with AWS Lambda via AWS SAM. The posts walks you through these three key updates: RDS Proxy support, Event driven Active Job with SQS and observability updates. Check out the full post for details.

**Modern Django**

[Deploying serverless Django applications to AWS with CDK on a tiny budget using Lambda, API Gateway, awsgi and the Lambda proxy pattern](https://briancaffey.github.io/2020/08/01/django-and-lambda-with-cdk-and-api-gateway.html) - another cracking post from Brian Caffey, on how to approach deploying Django application son AWS Lambda. Brian outlines the rationale for taking this specific approach by showing you how he typically deploys web applications. Throw in a bit of Zappa, AWS CDK to make sure everything is written as infrastructure as code, a sprinkle of AWS services and you have a blog post that the "Mothers of invention"* would be proud of.

![arch](https://briancaffey.github.io/static/djambda.png)

*fans of Frank Zappa will get this reference, but if this is new to you, get onto YouTube, plug in some headphones and enjoy!

**ROS**

A couple of blog posts from Michael Ferguson this week.

[5 Things ROS2 Needs in 2020](https://www.robotandchisel.com/2020/07/29/five-things-ros2/) this is an excellent post from Michael where he shares his thoughts on what is holding back ROS2 from being production ready. Michael lists the five things he thinks are essential before this can happen, so take a look and let him know your thoughts.

[Mapping and Localization in ROS2](http://www.robotandchisel.com/2020/08/19/slam-in-ros2/) another post from Michael, this time covering mapping and localisation in ROS2.

![ros2](http://www.robotandchisel.com/assets/images/2020-08-10-rviz2.png)


**MLOps with Cortex**

[Serve Your ML Models in AWS Using Python](https://medium.com/@aiteamglami/serve-your-ml-models-in-aws-using-python-9908a4127a13) post from GLAMI, walks you through how they are using the open source project Cortex (a command-line utility that orchestrates the creation of Amazon EKS cluster (Kubernetes), deployment, scaling, serving, and load balancing of the model endpoints in the cluster) and created an open source wrapper called [Cortex Serving Client](https://github.com/glami/cortex-serving-client) to simplify the automation and use of Cortex. The project tackles a number of things such as providing a mechanisms to remove unused or expired models from a cluster or how you roll back deployments. You can get the [source code for Cortex Serving Client here](https://github.com/glami/cortex-serving-client).

![arch](https://miro.medium.com/max/700/0*2BdQSrgrkFs-PzP_.png)

**PyTorch**

[Connecting a web app to your PyTorch model using Amazon SageMaker](https://developers.facebook.com/blog/post/2020/08/03/connecting-web-app-pytorch-model-using-amazon-sagemaker) is a blog post from Cami Williams, Open Source advocate at Facebook, that shows you how to connect your Web Apps to a PyTorch model using AWS SageMaker. Along side this post there is a series of videos where she walks you through this. If you missed this a couple of weeks back, then you can catch it now.  

{% youtube 0EhwUaqDibI %}


**ReportPortal**

[Deploy ReportPortal in AWS with AWS CloudFormation](https://medium.com/@chhatbarjignesh/deploy-reportportal-in-aws-with-aws-cloudformation-cd6553e27f74) is a post from Jignesh Chhatbar that shows you how to deploy the open source report dashboard project, [Report Portal](https://github.com/reportportal/reportportal) on AWS. You are probably using a number of different tools that generate output of some kind, and this project helps you manage that output, and integrates into a wide range of applications and systems. If you are looking for a way to manage that, certainly worth a read.

![arch](https://miro.medium.com/max/2000/1*xTXIQI4LyQRV5SaSScmgOA.png)


### If you missed these

Here are a few posts over the past weeks that might be of interest

**Flask on AWS**

[How to deploy a Python Flask app to AWS Elastic Beanstalk](https://medium.com/seamless-cloud/how-to-deploy-a-python-flask-app-to-aws-elastic-beanstalk-c7de7f146eea) post from Andrey that is the first in a series and shows you how to get your Flask apps running/deployed on AWS ElasticBeanstalk.


### AWS open source posts

**AWS ParallelCluster**

[Managing AWS ParallelCluster SSH users with OpenLDAP](https://aws.amazon.com/blogs/opensource/managing-aws-parallelcluster-ssh-users-with-openldap/) this post from Chris Downing is a walk through of a simple mechanism for provisioning multiple users within AWS ParallelCluster using a locally installed OpenLDAP server on the controller. With minimal complexity, we configured the directory structure to provide SSH access for HPC users.

**AWS Controllers for Kubernetes**

[Introducing the AWS Controllers for Kubernetes (ACK)](https://aws.amazon.com/blogs/containers/aws-controllers-for-kubernetes-ack/) by Jay Pipes, Michael Hausenblas, and Nathan Taber introduce one of the biggest announcements last week, the open source project AWS Controllers for Kubernetes. This project lets you directly manage AWS services from Kubernetes. ACK makes it simple to build scalable and highly-available Kubernetes applications that utilise AWS services. This post walks you through the back story and how ACK works, and whilst this is still a very new project, they are looking for feedback to help guide the development going forward.

**Chaos Engineering**

[Building resilient services at Prime Video with chaos engineering](https://aws.amazon.com/blogs/opensource/building-resilient-services-at-prime-video-with-chaos-engineering/) post from my colleague Adrian Hornsby and Varun Jewalikar that shows you how you can use the open source project, [AWSSSMChaosRunner](https://github.com/amzn/awsssmchaosrunner) and dives deep into failure injection, using this project to help you with some example integrations. The post also shows you how the Amazon Prime Video team are using this library to prevent potentially customer impacting outages.

**AWS Data Wrangler**

[Optimize Python ETL by extending Pandas with AWS Data Wrangler](https://aws.amazon.com/blogs/big-data/optimize-python-etl-by-extending-pandas-with-aws-data-wrangler/) by Satoshi Kuramitsu and Igor Tavares shows how you can use an open source project called AWS Data Wrangler to help you orchestrate your ETL (Extract, Transform and Load) tasks against multiple data sources and services. AWS Data Wrangler is an open-source Python library that enables you to focus on the transformation step of ETL by using familiar Pandas transformation commands and relying on abstracted functions to handle the extraction and load steps and you can use AWS Data Wrangler in different environments on AWS and on premises.

**sls-dev-tools**

[Improving the serverless developer experience with sls-dev-tools](https://aws.amazon.com/blogs/opensource/improving-the-serverless-developer-experience-with-sls-dev-tools/) a guest post from AWS Serverless Hero Ben Ellerby, showing you in more depth how you can use sls-dev-tools to help developers be more productive, delivering rich metrics directly to your terminal. I have written about this project before, so it is nice to get a deep dive on this tool to help you get started.

**Amazon MSK**

[Using Amazon MSK as an event source for AWS Lambda ](https://aws.amazon.com/blogs/compute/using-amazon-msk-as-an-event-source-for-aws-lambda/)from James Beswick is a nice primer to help you understand how you can integrate AWS Lambda with the managed Apache Kafka that is provided by Amazon MSK. Apache Kafka is a distributed streaming platform that it is similar to Amazon Kinesis. Amazon MSK simplifies the setup, scaling, and management of clusters running Kafka, is fully compatible with Kafka and supports familiar community-build tools such as MirrorMaker, Apache Flink, and Prometheus. This posts walks you through setting up a sample cluster and then integrating this with AWS Lambda.

![architecture](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2020/08/14/msk2.png)

**Modern LAMP**

A couple of posts from Ben Smith to keep the PHP developers happy.

[Introducing the CDK construct library for the serverless LAMP stack](https://aws.amazon.com/blogs/compute/introducing-the-cdk-construct-library-for-the-serverless-lamp-stack/) follows up his series of the new modern LAMP stack with a post on the new CDK construct library that helps you build these using AWS CDK. The AWS Cloud Development Kit (AWS CDK) is an open source software development framework for defining cloud application resources in code. It allows developers to define their infrastructure in familiar programming languages such as TypeScript, Python, C# or Java. 

The AWS Construct Library provides a broad set of modules that expose APIs for defining AWS resources in CDK applications, allowing you to extend and add new capabilities as needed. The CDK construct library for the serverless LAMP stack is an abstraction created by AWS Developer Advocate, Pahud Hsieh. It offers a single high-level component for defining all resources that make up the serverless LAMP stack.

So read on to find out more how to get started and use AWS CDK to create your first PHP serverless application.

[The serverless LAMP stack part 4: Building a serverless Laravel application](https://aws.amazon.com/blogs/compute/the-serverless-lamp-stack-part-4-building-a-serverless-laravel-application/) is the final instalment from Ben of the series that shows how you can build a modern LAMP stack, with episode four focusing on Laravel.

![show](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2020/08/03/LampStackwebPage.png)

**AWS CoPilot**

[AWS Copilot: an application-first CLI for containers on AWS](https://aws.amazon.com/blogs/containers/aws-copilot-an-application-first-cli-for-containers-on-aws/) is a great post from Efe Karakus that explores the four tenets that guided the team when creating this open source tool (currently in preview phase), a command line interface (CLI) to build, release, and operate production ready containerised applications on Amazon Elastic Container Service (Amazon ECS) and AWS Fargate. I do not want to give too much away as I think this is a post that everyone should read.

As Efe concludes, "Copilot is fully open source! Checkout out [GitHub repository](https://github.com/aws/copilot-cli) for discussion via issues and contribution via pull requests. You can learn more about how to install and get started with Copilot from our [documentation](https://aws.github.io/copilot-cli/)."

**Container DevSecOps**

[Container DevSecOps with AWS CodePipeline using Hadolint and Anchore Engine](https://aws.amazon.com/blogs/containers/container-devsecops-with-aws-codepipeline-using-hadolint-and-anchore-engine/) in this post from Anand Krishna, you will learn how to integrate some open source tools, Hadolink and Anchore Engine, to create a simple DevSecOps pipeline using AWS CodePipeline.

![arch](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2020/08/12/Screenshot-2020-08-12-at-11.52.42-AM.png)

These tools provide Docker linting and container static analysis scanning tools that help you secure the container life cycle management, container image hardening and end-to-end security checks. The post explores this in more detail before going to to help you put this into practice by building a DEvSecOps pipeline.

**OpenShift, Koku on AWS**

[Cost tracking for OpenShift on AWS](https://aws.amazon.com/blogs/opensource/cost-tracking-for-openshift-on-aws/) from Ryan Niksch shows you how you can manage costs when running RedHat OpenShift using a number of AWS services and mechanisms as well as an open source project called Koku. Koku, which is integrated into OpenShift, is an open source solution for cost management of cloud and hybrid cloud environments. Koku exposes resource consumption and cost data in easily digestible and filterable views.

![cost image](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2020/08/05/niksch_f14-openshift-cost-save.png)

**Prometheus, Grafana and Amazon EMR**

[Monitor and Optimize Analytic Workloads on Amazon EMR with Prometheus and Grafana](https://aws.amazon.com/blogs/big-data/monitor-and-optimize-analytic-workloads-on-amazon-emr-with-prometheus-and-grafana/) is a piece from Derek Tan and Fei Lang that shows how you can install and configure Prometheus and Grafana on AWS and then integrate these with Amazon EMR so you can capture logging events and then create rich dashboards.

![diagram](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2020/07/16/EMRPrometheusGrafana1.png)

**TensorFlow and Amazon EC2 Spot**

[TensorFlow Serving on Kubernetes with Amazon EC2 Spot Instances](https://aws.amazon.com/blogs/compute/tensorflow-serving-on-kubernetes-spot-instances/) contributed by Kinnar Sen that helps you understand how you can deploy TensorFlow Serving using Kubernetes via Amazon EKS and Spot Instances to build a scalable, resilient, and cost optimised machine learning inference service. To cost optimise the TF serving workloads, you can use Amazon EC2 Spot Instances, which are spare EC2 capacity available at up to a 90% discount compared to On-Demand Instance prices.

![image](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2020/08/06/TF1.1.jpg)

**TorchServe on Amazon EKS**

[Running TorchServe on Amazon Elastic Kubernetes Service](https://aws.amazon.com/blogs/opensource/running-torchserve-on-amazon-elastic-kubernetes-service/) is a collaboration between Josiah Davis, Charles Frenzel, and Chen Wu that shows how to deploy TorchServe on an Amazon EKS cluster for inference. This allows you to quickly deploy a pre-trained machine learning model as a scalable, fault-tolerant web service for low latency inference.

TorchServe is a model serving library that makes it easy to deploy and manage PyTorch models at scale in production environments. TorchServe removes the heavy lifting of deploying and serving PyTorch models with Kubernetes and is built and maintained by AWS in collaboration with Facebook, and is available as part of the PyTorch open source project.

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2020/07/29/wu-fig.1-1024x502.jpg)

Whilst this post focuses on a single model and on a single node cluster, this type of deployment is scalable to multiple nodes and extrapolates to more advanced deployments.

**Deep Graph Library**

[Training knowledge graph embeddings at scale with the Deep Graph Library](https://aws.amazon.com/blogs/machine-learning/training-knowledge-graph-embeddings-at-scale-with-the-deep-graph-library/) Phi Nguyen and Xiang Song share news of  the Deep Graph Knowledge Embedding Library (DGL-KE), a knowledge graph (KG) embeddings library built on top of the Deep Graph Library (DGL). 

Graphs can be found in many domains, such as chemistry, biology, financial services, and social networks, and allow us to represent complex concepts intuitively using entities and relations. DGL is an easy-to-use, high-performance, scalable Python library for deep learning on graphs. You can now create embeddings for large KGs containing billions of nodes and edges two-to-five times faster than competing techniques.

![dgl](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2020/08/05/ml1084-training-knowledge-graph-embeddings-2-2.jpg)

**Horovod**

[Multi-GPU and distributed training using Horovod in Amazon SageMaker Pipe mode](https://aws.amazon.com/blogs/machine-learning/multi-gpu-and-distributed-training-using-horovod-in-amazon-sagemaker-pipe-mode/) from Muhyun Kim, Hussain Karimi, and Jiyang Kang introduces what Horovod is and how you can run this in a number of different scenarios to provide efficient mutli-GPU and multi-node distributed training on Amazon SageMaker.

Horovod is Uber’s open-source framework for distributed deep learning, and it’s available for use with most popular deep learning toolkits like TensorFlow, Keras, PyTorch, and Apache MXNet. Why do you need this? When you train a model with a large amount of data, you should distribute the training across multiple GPUs on either a single instance or multiple instances. Deep learning frameworks provide their own methods to support multi-GPU training or distributed training, and Horovod emerged as an open source way to do this.

This post walks you through how to set this up and provide a GitHub repo with the resources you need to get started.


**AWS Chalice**

A couple of posts on AWS Chalice this week from by James Saryerwinnie.

[Introducing the AWS Chalice test client](https://aws.amazon.com/blogs/developer/introducing-the-new-test-client-for-aws-chalice/) introduces the latest release of AWS Chalice, v1.17.0, that now includes a test client that enables you to write tests for your Chalice applications using a concise and simplified API. The test client handles all the boilerplate setup and teardown logic that you’d previously have to write yourself when testing your Chalice applications. This posts shows you how to get started with this new update. In the second post,

[Using AWS Lambda Layers with AWS Chalice](https://aws.amazon.com/blogs/developer/using-aws-lambda-layers-with-aws-chalice/) James looks at version 1.18.0 of Chalice, which now has support for Chalice to automatically manage a shared Lambda layer that contains all your third-party and vendor code. Lambda layers are a way to pull in additional dependencies in code that are separate from the deployment package for a Lambda function. These Lambda layers can be reused by multiple Lambda functions, which allows you to keep your deployment packages small as well as reduce the total storage space needed for all your Lambda functions.

![arch](https://d2908q01vomqb2.cloudfront.net/0716d9708d321ffb6a00818614779e779925365c/2020/08/17/ChaliceLambdaLayers.001.png)

**.NET Core Lambda**

[Automated CI/CD pipeline for .NET Core Lambda functions using AWS extensions for dotnet CLI](https://aws.amazon.com/blogs/devops/automated-ci-cd-pipeline-for-net-core-lambda-functions-using-aws-extensions-for-dotnet-cli/) by Sundar Narasiman provides an overview of how you can implement an automated CI/CD for .NET Core Lambda functions using two stages of CodePipeline: CodeCommit and CodeBuild that you can apply as the base for your own use cases.

**AWS SAM**

[Season One of Sessions with SAM](https://aws.amazon.com/blogs/compute/icymi-season-one-of-sessions-with-sam/) - check out this curated set of Eric Johnson's sessions covering how to easily build and manage serverless applications using AWS Serverless Application Model (SAM). From starting from the beginning to what is SAM, through to building a number of demo applications, you will quickly learn how to master AWS SAM and apply it within your own applications. All in all, twelve sessions to get through that cover everything from machine learning to .NET Core. Eric is working on Season Two, so make sure you catch those too.

**cfn-guard**

[Write preventive compliance rules for AWS CloudFormation templates the cfn-guard way](https://aws.amazon.com/blogs/mt/write-preventive-compliance-rules-for-aws-cloudformation-templates-the-cfn-guard-way/) from  Luis Colon, Raisa Hashem, and Josh Joy helps you get started with creating some compliance rules using the open source tool cfn-guard. 

CloudFormation helps customers model and provision their AWS and third-party application resources, with features such as rollback to provide automation and safety. Together with tools such as AWS CodeBuild, AWS CodePipeline, and AWS CodeDeploy, CloudFormation helps customers automate processes that implement popular practices like GitFlow , allowing for incremental testing and automated guardrails for fast releases. Emerging best practices, such as DevSecOps, shift-left testing and low-code tools, are further enabling security leaders to embed preventive compliance rules earlier in the development lifecycle.

These best practices inspired us to build CloudFormation Guard (cfn-guard) as an open-source tool that helps you write compliance rules using a simple, policy as code language. It will help you validate CloudFormation templates against those rules to keep your AWS resources in compliance with your company policy guidelines.

**Swfit and AWS Amplify**

[Using Swift Combine with AWS Amplify](https://aws.amazon.com/blogs/mobile/using-swift-combine-with-aws-amplify/) this post from Kyle Lee introduces the support included in AWS Amplify 1.1 release for IOS of Combine. [Combine](https://developer.apple.com/documentation/combine) is a first party reactive framework that makes it easy to deal with asynchronous events in a declarative way. 

The previous 1.0 version of Amplify iOS (launched in May 2020) supported only a standard '“callback” model for handing asynchronous calls. While this is a common pattern for iOS developers, it leads to a well-known condition known as “callback hell”, where dependent asynchronous calls are nested within callbacks. For anything beyond simple dependency cases, this quickly becomes difficult to follow and maintain. With Amplify iOS 1.1, developers can now flatten this nest of callbacks using the built-in integration with the Combine framework. Support is included for all the asynchronous APIs in Amplify iOS, including Auth (sign up, sign in, observing session status), DataStore (CRUD operations, observing changes), and Storage (uploading and downloading files), among others.

In this post Kyle helps you get started and walks you through some use cases and sample code.

**WorldForge**

[AWS announces WorldForge in AWS RoboMaker](https://aws.amazon.com/blogs/aws/aws-announces-worldforge-in-aws-robomaker/) post from self proclaimed Robot fan Alejandra Quetzalli that introduces a new feature in AWS RoboMaker that makes it super easy to create simulation environments to test your ROS powered robots. In previous episodes I have shared posts and resources of 3D environments, object artefacts and more. You can now access these kinds of resources directly from within the AWS RoboMaker UI.

**Exploring AWS CDK and Terraform via CDKTF**

If you have not checked out Darko and Cobus' Twitch sessions, then fear not, these are recorded and here I share a recent episode where they do a getting started with the Terraform construct library for AWS CDK. I recently talked about the cdktf module, and so in this video, Darko and Cobus do Infrastructure as Code but this time with Terraform.

{% youtube VPqJoDhHkS4 %}

### Case Study

**Open Source in Government**

[How open source helps governments respond to COVID-19 with speed, scale, and agility](https://aws.amazon.com/blogs/publicsector/how-open-source-government-respond-covid-19-speed-scale-agility/) this short write up from Lauren Dawson and Maryclaire Abowd introduces how public sector customers are using open source tools to fight COVID-19, highlighting the Open Government Solutions that was launched by AWS earlier in the year that aggregates open source solutions and projects. This post then links to a panel discussion and talks to a number of government leaders and AWS open source and government leaders.  Make sure you check out this post and watch the AWS Institute panel, lots of great insights from these leaders.

**Absa**

[Absa Transforms IT and Fosters Tech Talent Using AWS](https://aws.amazon.com/solutions/case-studies/absa-case-study/?did=cr_card&trk=cr_card) this case study shows how the Absa Group is leveraging open source and AWS to drive their digital transformation. A great quote from Craig Du Troit, Head of Technology:

> "Open source and AWS services are the ingredients the bank needs to turn our techies into development chefs."

A must read post.

**EposNow and Kloia**

[How Kloia used Porting Assistant for .NET to accelerate EposNow API modernization](https://aws.amazon.com/blogs/modernizing-with-aws/how-kloia-used-porting-assistant-for-net-to-accelerate-eposnow-api-modernization/) a joint post between Turgay Özgür and Onuralp Taner from Kloia and Prasad Rao from AWS, walks you through how this partner helped their customer EposNow modernise by migrating .NET applications to .NET Core and move those to Linux, using the Porting Assistant for .NET tool. This real world example will be useful if you are looking to do something similar.


### Quick updates

**Amazon SageMaker notebooks now available with pre-installed R kernel**

Amazon SageMaker notebooks now support R out-of-the-box, without needing you to manually install R kernels on the instances. Also, the notebooks come pre-installed with the reticulate library that offers an R interface for the Amazon SageMaker Python SDK enabling you to invoke Python modules from within an R script. 

In the post, [Accessing data sources from Amazon SageMaker R kernels](https://aws.amazon.com/blogs/machine-learning/accessing-data-sources-from-amazon-sagemaker-r-kernels/) by Kunal Ghosh and Gagan Brahmi, they explore how you can use this to access data sources, such as Hive and PrestoDB on Amazon EMR, Amazon Athena, Amazon Redshift, and Amazon Aurora MySQL-compatible cluster, to analyse, profile, run statistical computations using R from Amazon SageMaker.

![architecture](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2020/08/10/sagemaker_r_datasources-001.jpg)

**Amazon ElastiCache for Redis**

Amazon ElastiCache for Redis now allows you to scale your Redis Clusters up to 500 nodes. Redis (cluster mode enabled) configuration allows you to partition your data across multiple shards and offers better scalability, performance, and availability. With this announcement, you can double your cluster size from 250 nodes to 500 nodes, thereby supporting larger memory storage capacity of up to 340 TB of memory and improved throughput per cluster. You can choose to configure a 500-node cluster that ranges between 83 shards (one master and five replicas per shard) and 500 shards (single master and no replicas). 

Support for 500-node cluster is available with Amazon ElastiCache for Redis starting with Redis version 5.0.6, in all AWS regions. You can create a new cluster or scale your existing cluster to add shards using online cluster resizing.

**Amazon Linux 2 on AWS Lambda**

You can now develop your AWS Lambda functions using custom runtimes on Amazon Linux 2, the latest generation of Amazon Linux. To get started, upload your code through the AWS Lambda console and select provide your own bootstrap on Amazon Linux 2 runtime. You can also use the AWS CLI, AWS Serverless Application Model (SAM) and AWS CloudFormation to deploy and manage your serverless application authored in custom runtimes. Also, Lambda Runtime API and Lambda Layers can be used to enable developers to build custom runtimes on Amazon Linux 2. To migrate existing AWS Lambda functions running in custom runtimes on Amazon Linux 1 to Amazon Linux 2, update your code to be compatible with Amazon Linux 2, and then update the function runtime.

**Amazon Corretto on AWS Lambda**

You can now develop AWS Lambda functions using Java 8 (Corretto). Amazon Corretto 8 is a no-cost, production-ready distribution of OpenJDK 8 that comes with long-term support. Lambda functions written in Java 8 (Corretto) run on Amazon Linux 2, the latest generation of Amazon Linux. You can read more about the Java programming model in the AWS Lambda documentation. 



### Share your open source projects 

Do you have some content you want to share with a broader audience? We are always looking for guest content for the AWS Open blog. Please get in touch (via comments below) and I would love to speak with you about what you are doing in open source. We are always looking for interesting new content.

The best submissions will get some AWS Credit codes as a thank you.


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)	