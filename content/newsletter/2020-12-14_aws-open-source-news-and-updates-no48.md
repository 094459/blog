---
title: 'AWS open source news and updates No.48'
date: '2020-12-14'
tags : [ oss-newsletter ]
---
## December 13th - Instalment #48

Week No.48 going into the final week of re:Invent this year (don't worry, we still have more sessions in the 2nd week of 2021) we have another great selection of posts. This week a favourite project of mine gets a lot of love, as well as a roundup of the second week of re:Invent. If that was not enough for you, then I throw in some new open source projects which you will definitely need to check out, with some really great ones including the latest project from Netflix that might make you Weep! Next week will be the last edition of the newsletter this year as I go away for the holidays but I will be back in January to pick up where I left off.

If you missed this last week, we joined a new  GitHub program that will let companies directly fund open-source projects and software developers that are key to their businesses. Read the blog post here - [Amazon, Amex to Fund Software Developers in New GitHub Program](https://www.bloomberg.com/news/articles/2020-12-08/amazon-amex-to-fund-software-developers-in-new-github-program) 

Not AWS related, but last week the Linux Foundation shared their [Report on the 2020 FOSS Contributor Survey](https://www.linuxfoundation.org/wp-content/uploads/2020/12/2020FOSSContributorSurveyReport_V7.pdf) which is well worth a read as it has some interesting data points to think about, including:

* The top three motivations for contributors are non-monetary
* There is a clear need to dedicate more effort to the security of FOSS, but the burden should not fall solely on contributors
* As more contributors are paid by their employer to contribute, stakeholders need to balance corporate and project interests
* Enhance the positive trend of corporate support for employees’ contribution to FOSS

No spoilers though, read the report.

**re:Invent 2020**

The final week of re:Invent in 2020 (we still have more session's in January 2021) and with the Open Source track sessions all finished, I wanted to share some of the other open source sessions this week that are worth while you checking out. I have listed these in chronological order and sessions are typically repeated three times to accommodate the different time zones you might be in. These are all in CET so remember to add or subtract time depending on where you are.

**DEC 15th**

* ARC307 Going global in minutes: Multi-Region expansion simplified (7:30pm CET)
* IOT303 Developing and deploying modern edge applications at scale (8:30pm CET)
* *AIM313 Scaling MLOps on Kubernetes with Amazon SageMaker Operators (10:45pm CET)

**DEC 16th**

* ARC307 Going global in minutes: Multi-Region expansion simplified (repeat, 3:30am/11:30am CET)
* IOT303 Developing and deploying modern edge applications at scale (repeat, 4:30am/12:30pm CET)
* AIM313 Scaling MLOps on Kubernetes with Amazon SageMaker Operators (repeat, 6:45am/2:45pm CET)
* FMW306 Best practices to securely operate GraphQL at scale with AWS AppSync (8pm CET)

**DEC 17th**

* FMW306 Best practices to securely operate GraphQL at scale with AWS AppSync (repeat, 4am/12pm CET)

**DEC 18th**

* FMW304 Unify access to siloed data with AWS AppSync GraphQL resolvers (12am/8am/4pm CET)

### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to Istvan Szukacs, Trivikram Kamat, Rene Brandel, Jonathan Shapiro-Ward, Andy Hopper, Viraj Phanse, Curtis Castrapel, Efe Karakus, Channy Yun, Justin Garrison, David Boyne, Jeremy Warrick, Justin Garrison,  Matt Muller, Darryl Osborne, George Karypis, Dave Bechberger, Karthik Bharathy, Julien Simon, Gillian Armstrong, Brett Andrews, Tim Wagner, Adrian Hornsby, Varun Jewalikar,  Tod Golding, Antje Barth, Steffen Hausman, Ben Smith, Michael Hausenblas, Alolita Sharma, Zhi Chen, Lokesh Gupta, Trevor Morris, Wei Xiao, Akshat Vig, Almann Goo, Arturo Hinojosa, Mihir Desai, Jon Handler and Sajeev Attiyil Bhaskaran.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

**consoleme**

[consoleme](https://github.com/Netflix/consoleme) a new open source project from Netflix that looks to simplify IAM permissions management. ConsoleMe consolidates the management of multiple AWS accounts into a single interface. It allows your end-users and administrators to get credentials for your different accounts, and allows your users/administrators to manage or request cloud permissions. If you want to know more, check out this post [Introducing ConsoleMe!](https://www.linkedin.com/pulse/consoleme-now-open-source-curtis-castrapel/) from Curtis Castrapel to find out more about this exciting new project. You can also check out the talk at re:Invent, [Untangling multi-account management with ConsoleMe](https://virtual.awsevents.com/media/1_2f1bnhai)

**weep**

[weep](https://github.com/Netflix/weep) this is another fresh open source project from the folks at Netflix, weep is the command line tool that you can use with consoleme (See previous) and this utility is for retrieving AWS credentials from ConsoleMe. Weep can run a local instance metadata service proxy, or export credentials as environmental variables for your AWS needs.

**superwerker**

[superwerker](https://github.com/superwerker/superwerker) great new open source project from AWS Advanced Partners kreuzwerker and superluminar that automates the setup of an AWS Cloud environment with prescriptive best practises. If you check out their other OSS project, [aws-organizations-vending-machine](https://github.com/superwerker/aws-organizations-vending-machine) which provides a too still in development that makes managing an AWS organisation, including multi-account, easier. Nice!

**soto**

[soto](https://github.com/soto-project/soto) Soto is a Swift language SDK for Amazon Web Services (AWS), working on Linux, macOS and iOS. This library provides access to all AWS services. The service APIs it provides are a direct mapping of the REST APIs Amazon publishes for each of its services. Soto is a community supported project and is in no way affiliated with AWS.

**eks-distro-build-tooling**

[eks-distro-build-tooling](https://github.com/aws/eks-distro-build-tooling) This repository contains tooling used to build the EKS Distro, and all the projects contained in https://github.com/aws/eks-distro. The **builder-base** contains a Dockerfile and install scripting for building a container image used to run prow jobs in our prow cluster, **eks-distro-base** contains a Dockerfile used to build an up-to-date Amazon Linux 2 base image and will be updated whenever there are any security updates to RPMs contained in the base image and **helm-charts** contains Helm charts used to operate Prow and supporting tooling on the Prow EKS clusters. Check out the repo for more info.

**awstools**

[awstools](https://awstools.dev/) another fantastic resource from David Boyne, this time a site to help you find resources to help you with your AWS Services, listing open source projects (many of which I have talked/shared about here) which you can easily search as well as add your own. Really nice!

**ness**

[ness](https://github.com/nessjs/ness) is a new open source tool to help you deploy static websites on AWS. Using some simple command line options to deploy and remove your assets, this has some nice features such as AWS CloudFront support, custom domains, security headers that follow best practices and much more.

### Workshop

[CDK with Next.js and AWS Amplify Workshop](https://github.com/dabit3/next.js-cdk-amplify-workshop) is a brand new workshop from Nader Dabit. In this workshop he will walk you through building a full stack cloud application with Next.js, AWS CDK, AWS AppSync, & AWS Amplify.

### AWS open source posts

**Kedro**

[Using Kedro pipelines to train Amazon SageMaker models](https://aws.amazon.com/blogs/opensource/using-kedro-pipelines-to-train-amazon-sagemaker-models/) Jeremy Warrick shows you how to build a Kedro pipeline that trains your model on Amazon SageMaker that will help you create reproducible models and save time in the process. Kedro is an Apache 2.0 licensed open source Python framework that applies software engineering best practices to data and machine learning pipelines. You can use it, for example, to optimize the process of taking a machine learning model into a production environment. You can use Kedro to organise a single-user project running on a local environment, or collaborate in a team on an enterprise-level project. This is a great deep dive post that walks you through creating your first Kedro pipeline.

![kedro](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2020/11/20/jewarric_kedro_f2.png)

**Amazon EKS Distro**

First up we have a round up of the AWS Partner network that can help you with Amazon EKS Distro. [How AWS Partners can help you get started with EKS-D](https://aws.amazon.com/blogs/opensource/how-aws-partners-can-help-you-get-started-with-eks-d/) from my good self shares over twenty AWS Partner capabilities and specialisms with links to blog posts sharing their excitement of this launch as well as how they are supporting Amazon EKS Distro.

Following that we have [Unboxing EKS Distro!](https://www.youtube.com/watch?v=YUS_LrlctHI&feature=emb_logo) Justin Garrison takes a first look at EKS Distro - the open source EKS operating system that allows you to run EKS with the same tools as AWS. Warning gratuitous use of Oreo's, liquorish and gummy bears in what might be the most controversial food combination after pineapple on pizza.

{% youtube YUS_LrlctHI %}

**Open Distro for OpenTelemtry**

Michael Hausenblas, Alolita Sharma and Aman from the AWS Observability team join the usual crew of the Containers from the couch crew and got some "couch time" as they took a look at the AWS Distro for Open Telemetry. If you want to know more about observability, our open source work in the observability community as well as a closer look at what AWS Distro for Open Telemtry and how you can get boot-strapped. This is a really good session, so check it out.

{% youtube tnlJeb0rTkw %}

**Open Distro for Elasticsearch**

This week we have a couple of posts. First up we have [Get started with fine-grained access control in Amazon Elasticsearch Service](https://aws.amazon.com/blogs/security/get-started-with-fine-grained-access-control-in-amazon-elasticsearch-service/) and like a superhero duo, Jon Handler and Sajeev Attiyil Bhaskaran combine to thwart the baddies and make sure only the folk you want to access your Amazon Elasticsearch domains are able to. In this post, you will see how to leverage fine-grained access control, powered by the Open Distro for Elasticsearch security plugin. The security plugin adds Kibana authentication and access control at the cluster, index, document, and field levels that can help you secure your data. You now have many different ways to configure your Amazon ES domain to provide access control.

![security](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2020/12/04/Fine-grained-access-control-Figure-1.png)

Following that Viraj Phanse writes [Using pipes to explore, discover and find data in Amazon ES with Piped Processing Language](https://aws.amazon.com/blogs/big-data/using-pipes-to-explore-discover-and-find-data-in-amazon-es-with-piped-processing-language/) where he shares the newly supported Piped Processing Language (PPL) feature, powered by Open Distro for Elasticsearch, which enables you to form complex queries and quickly explore and discover data with the help of pipes.

**Amazon SageMaker JumpStart**

[Amazon SageMaker JumpStart](https://aws.amazon.com/sagemaker/getting-started/) helps you easily and quickly bring machine learning (ML) applications to market using pre-built solutions for common use cases and open source models from popular model zoos. This new capability provides a set of solutions for the most common use cases, such as fraud detection, predictive maintenance, and demand forecasting, that can be deployed readily with just a few clicks. The solutions are fully customisable and showcase the use of AWS CloudFormation templates and reference architectures so you can accelerate your ML journey. Amazon SageMaker JumpStart also provides one-click deployment and fine-tuning of more than 150 pre-trained models from popular model zoos, including PyTorch Hub and TensorFlow Hub. One-click deployment and fine-tuning features are available for natural language processing, object detection, and image classification models, so you can minimise the time to deploy open source models for your own use case. This is a really handy new resource and makes it super easy to get started.

**Amazon SageMaker NEO**

A great selection this week on posts covering Amazon SageMaker NEO. **neo-ai** is the open source project that enables developers to optimise machine learning (ML) models for inference on SageMaker in the cloud and supported devices at the edge. Neo automatically optimises machine learning models for inference on cloud instances and edge devices to run faster with no loss in accuracy. You start with a machine learning model already built with DarkNet, Keras, MXNet, PyTorch, TensorFlow, TensorFlow-Lite, ONNX, or XGBoost and trained in Amazon SageMaker or anywhere else. Then you choose your target hardware platform, which can be a SageMaker hosting instance or an edge device based on processors from Ambarella, Apple, ARM, Intel, MediaTek, Nvidia, NXP, Qualcomm, RockChip, Texas Instruments, or Xilinx.

A good first post to start this week is [Model dynamism Support in Amazon SageMaker Neo](https://aws.amazon.com/blogs/machine-learning/model-dynamism-support-in-amazon-sagemaker-neo/) from Zhi Chen which provides a nice intro as well as going into how Neo supports model dynamism. The perfect follow up from Tingwei Huang and Vin Sharma is [New Amazon SageMaker Neo features to run more models faster and more efficiently on more hardware platforms](https://aws.amazon.com/blogs/machine-learning/new-amazon-sagemaker-neo-features-to-run-more-models-faster-and-more-efficiently-on-more-hardware-platforms/) where you can keep up to date with the latest improvements as well as supported hardware/edge devices.

A big one for mobile developers next, in [Optimizing ML models for iOS and MacOS devices with Amazon SageMaker Neo and Core ML](https://aws.amazon.com/blogs/machine-learning/optimizing-ml-models-for-ios-and-macos-devices-with-amazon-sagemaker-neo-and-core-ml/) Lokesh Gupta shows you how to set up automatic model conversion, add a model to your app, and then deploy and test your new model. Core ML is a machine learning (ML) model format created and supported by Apple that compiles, deploys, and runs on Apple devices. Developers who train their models in popular frameworks such as TensorFlow and PyTorch convert models to Core ML format to deploy them on Apple devices. In this post, Lokesh shows how AWS has automated the model conversion to Core ML in the cloud using Amazon SageMaker Neo.

Next up is [Amazon SageMaker Neo makes it easier to get faster inference for more ML models with NVIDIA TensorRT](https://aws.amazon.com/blogs/machine-learning/amazon-sagemaker-neo-makes-it-easier-to-get-faster-inference-for-more-ml-models-with-nvidia-tensorrt/) with Trevor Morris covering how Amazon SageMaker Neo now uses the NVIDIA TensorRT acceleration library to increase the speedup of machine learning (ML) models on NVIDIA Jetson devices at the edge and AWS g4dn and p3 instances in the AWS Cloud. [NVIDIA TensorRT](https://github.com/NVIDIA/TensorRT) is an open source library that supports a subset of operators commonly used in deep learning models, and Trevor shows how Neo automatically takes advantage of TensorRT to accelerate computation-heavy operations, such as convolutions supported by the accelerator library, while generating highly performant CUDA code for all other operations using Apache TVM.

Finally we have [Speeding up TensorFlow, MXNet, and PyTorch inference with Amazon SageMaker Neo](https://aws.amazon.com/blogs/machine-learning/speeding-up-tensorflow-mxnet-and-pytorch-inference-with-amazon-sagemaker-neo/) from Wei Xiao in a post that shares the resulting model performance improvements in Neo that came from the support more operators and expanded model coverage for TensorFlow, PyTorch, and Apache MXNet (incubating). Neo can now compile nearly all ML models from TensorFlow, PyTorch, and MXNet frameworks for SageMaker CPU and GPU instances.

**AWS Amplify**

[Zero-effort Container deployment for GraphQL and REST APIs and Web Hosting with Amplify CLI](https://aws.amazon.com/blogs/mobile/zero-effort-container-deployment-for-graphql-and-rest-apis-and-web-hosting-with-amplify-cli/) Rene Brandel writes about one of my favourite announcements last week which perhaps didn't get the noise it deserved. In this post Rene goes into more details about how this new capability in the Amplify CLI enables customers to deploy their API (GraphQL & REST) or host their web apps using containers. You can bring your own Dockerfile or Docker Compose and Amplify CLI will automatically build, package and deploy your containers using AWS Fargate. The post demonstrates how you can deploy single and multiple containers using Amplify CLI and the offers up some potential use cases that this opens up for you.

**AWS SDK's**

A couple of posts this week. First up we have [Introducing new features for the aws-sdk-rails gem](https://aws.amazon.com/blogs/developer/introducing-new-features-for-the-aws-sdk-rails-gem/). Matt Muller provides an update from the Ruby SDK team, announcing new features that have been added and sharing how consolidated existing gems into the aws-sdk-rails gem works to make developing Rails applications using AWS easier than ever. The aws-sdk-rails gem is available now on [rubygems.org](http://rubygems.org/). As always, we’d love to hear your feedback, and welcome any Issues or Pull Requests at the [aws-sdk-rails GitHub repo.](http://github.com/aws/aws-sdk-rails)

Trivikram Kamat follows that with [First-class TypeScript support in modular AWS SDK for JavaScript](https://aws.amazon.com/blogs/developer/first-class-typescript-support-in-modular-aws-sdk-for-javascript/) where he takes a look at why the team decided to use TypeScript for building version 3 of JavaScript SDK, providing examples of how TypeScript helped development and debugging.

**HyperLedger Fabric**

[Automating Hyperledger Fabric chaincode deployment on Amazon Managed Blockchain using AWS CodePipeline](https://aws.amazon.com/blogs/database/automating-hyperledger-fabric-chaincode-deployment-on-amazon-managed-blockchain-using-aws-codepipeline/) Jonathan Shapiro-Ward takes you through how you can use tools such as AWS CodePipeline, AWS CodeBuild, and AWS Lambda to perform automated testing and deployment of chaincode to Managed Blockchain. Chaincode is a program that typically handles business logic agreed to by members of the network and is sometimes called a smart contract. Find out more by reading the post...

![chaincode](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2020/11/25/Automating-Hyperledger-Fabric-1.jpg)

### re:Invent

**Launches**

There were a number of new launches this week, including some exciting AI and Machine Learning launches that had some great open source technologies and projects for you to experiment and get to know.

**Amazon Neptune ML**

[Announcing Amazon Neptune ML: Easy, fast, and accurate predictions on graphs](https://aws.amazon.com/blogs/database/announcing-amazon-neptune-ml-easy-fast-and-accurate-predictions-on-graphs/) George Karypis, Dave Bechberger, and Karthik Bharathy announced this new capability which provides an easy, fast, and accurate approach for predictions on graphs. Neptune ML is a new capability that uses graph neural networks (GNNs), a machine learning (ML) technique purpose-built for graphs. Neptune ML uses the Deep Graph Library (DGL), an open-source library to which AWS contributes that makes it easy to develop and apply GNN models on graph data. As a result, you can now create, train, and apply ML on Neptune data in hours instead of weeks without the need to learn new tools and ML technologies. Now, any developer with data in Neptune can easily use ML on their graphs.

![arch-graph](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2020/12/07/DBBLOG-1378-A-2.jpg)

Now you know more about Amazon Neptune ML and the Deep Graph Library, time to see how easy it actually is to get started. In 
[How to get started with Neptune ML](https://aws.amazon.com/blogs/database/how-to-get-started-with-neptune-ml/), they show you how you can easily set up Neptune ML and infer properties of vertices within a graph. Last week I mentioned a new open source project from the Amazon Neptune team, graph-notebooks. Well in this post you will actually use them as part of the walk through.

![notebook](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2020/12/08/Screen-Shot-2020-12-08-at-13.53.58.png)

**Amazon SageMaker Edge Manager**

[Amazon SageMaker Edge Manager Simplifies Operating Machine Learning Models on Edge Devices](https://aws.amazon.com/blogs/aws/amazon-sagemaker-edge-manager-simplifies-operating-machine-learning-models-on-edge-devices/) another post from Julien, this time taking a look at this new service that makes it easier to optimise, secure, monitor, and maintain machine learning models on a fleet of edge devices. If you read above you will see a bunch of new posts around Amazon SageMaker NEO. Starting from a model that you trained or imported in Amazon SageMaker, SageMaker Edge Manager first optimises it for your hardware platform using Amazon SageMaker Neo. Then, SageMaker Edge Manager packages the model, and stores it in Amazon Simple Storage Service (S3), where it can be deployed to your devices. In fact, you can deploy multiple models, loading and predicting with a runtime optimised for your hardware of choice. Make sure you read the post for the full low down on this, including the customer story from Lenovo.

**Amazon SageMaker Clarify**

[New – Amazon SageMaker Clarify Detects Bias and Increases the Transparency of Machine Learning Models](https://aws.amazon.com/blogs/aws/new-amazon-sagemaker-clarify-detects-bias-and-increases-the-transparency-of-machine-learning-models/) this post from Julien Simon introduces this new capability within Amazon SageMaker that helps customers detect bias in machine learning (ML) models, and increase transparency by helping explain model behaviour to stakeholders and customers. As part of this we have open sourced a key part of this capability so that you can use the same approach when you are doing local development.
 
[amazon-sagemaker-clarify](https://github.com/aws/amazon-sagemaker-clarify/) is the GitHub repository for the open source project. Julien has also put together a short video that shows you how to compute bias metrics on your datasets, using this amazon-sagemaker-clarify open source package in Python, running a simple example on his local machine

{% youtube xrGcy6rL9mw %}

or see his demo of how you can use this within Amazon SageMaker too.

Later last week we also had a follow up post on the Amazon Science blog, [How Clarify helps machine learning developers detect unintended bias](https://www.amazon.science/latest-news/how-clarify-helps-machine-learning-developers-detect-unintended-bias) that provided further info on how this works. Well worth a read to get a good grounding in this subject.

**Amazon EMR on Amazon EKS**

[New – Amazon EMR on Amazon Elastic Kubernetes Service (EKS)](https://aws.amazon.com/blogs/aws/new-amazon-emr-on-amazon-elastic-kubernetes-service-eks/) in this post, Channy Yun announces the general availability of Amazon EMR on Amazon EKS, a new deployment option in EMR that allows customers to automate the provisioning and management of open-source big data frameworks on EKS. With EMR on EKS, customers can now run Spark applications alongside other types of applications on the same EKS cluster to improve resource utilisation and simplify infrastructure management.

![arch](https://d2908q01vomqb2.cloudfront.net/da4b9237bacccdf19c0760cab7aec4a8359010b0/2020/12/02/2020-emr-on-eks-diagram-1.png)

**Sessions**

A recap of the sessions last week incase you missed them, all sessions from the Open Source track.

[The serverless LAMP stack](https://virtual.awsevents.com/media/1_gg7st54o) a firm favorite in my newsletter has been the series of posts from Ben Smith where he takes the LAMP (Linux, Apache, MySQL and PHP) and helps you through a number of modernisation approaches you can take on AWS. One of those modernisation techniques involves the adoption of Serverless, and in this session you will learn about the serverless LAMP stack and how to use your favorite open-source frameworks like Laravel to build modern, serverless PHP apps.

[Building real-time applications using Apache Flink](https://virtual.awsevents.com/media/1_zawy3w1x) Steffen Hausman's session shared how to build real-time applications using Apache Flink with Apache Kafka and Amazon Kinesis Data Streams. Apache Flink is a framework and engine for building streaming applications for use cases such as real-time analytics and complex event processing. He covered best practices for building low-latency applications with Apache Flink when reading data from either Amazon MSK or Amazon Kinesis Data Streams, as well as how to run low-latency Apache Flink applications using Amazon Kinesis Data Analytics and discusses AWS’s open-source contributions to this use case.

[Building end-to-end ML workflows with Kubeflow Pipelines](https://virtual.awsevents.com/media/1_p3js9wfp) my colleague Antje Barth did a great session on Kubeflow, a popular open-source machine learning (ML) toolkit for Kubernetes users. In this session she talks about Kubeflow Pipelines, an add-on to Kubeflow that lets you build and deploy portable and scalable end-to-end ML workflows. She covered how to get started with Kubeflow Pipelines and how you can integrate powerful Amazon SageMaker features such as data labelling, large-scale hyperparameter tuning, distributed training jobs, and secure and scalable model deployment using SageMaker Components for Kubeflow Pipelines.

[Open source meets SaaS: Accelerating the path to SaaS adoption](https://virtual.awsevents.com/media/1_qg3dkb6g) Tod Golding introduces you to this new open source solution that was announced last week during the AWS Partner keynote. He shared with you the underlying architecture of this solution as well as how it enables you to leverage the power of an open-source environment to accelerate your path to a SaaS delivery model.

[Open-source failure injection on AWS](https://virtual.awsevents.com/media/1_rvr6ika5) colleague Adrian Hornsby and Varun Jewalikar from the Amazon Prime Video shared with you an open-source approach to failure injection on Amazon EC2 and Amazon ECS using AWS Systems Manager and discusses how Prime Video combines this approach with load testing for higher levels of resiliency. Great session, and Adrian's demo's really bring this to life. Make sure you view this as this is an increasingly important topic and priority for business who increasingly depend on their digital systems. 

Next up was the session on [Running Apache Cassandra workloads with Amazon Keyspaces](https://virtual.awsevents.com/media/1_8j6trb97) where Arturo Hinojosa and Mihir Desai dive into what is Apache Cassandra, a look at Amazon Keyspaces (for Apache Cassandra) looking at the architecture and key features, including data encryption by default, continuous backups using point-in-time recovery, and serverless throughput and storage management. Finally they share how to design and visualise Amazon Keyspaces data models easily by using NoSQL Workbench.

If you are using AWS Copilot, an open source command line tool that makes building, developing, and operating containerized applications on AWS a breeze then you will enjoy [AWS Copilot: Simplifying container development](https://virtual.awsevents.com/media/1_ehfd1geq). Efe Karakus does a great job through the scenario of deploying a new voting application on how AWS Copilot works and how it might help you. Awesome stuff and a great session.

**Other sessions**

In [Deep dive on AWS Glue Elastic Views](https://virtual.awsevents.com/media/1_s3k0eprp) Akshat Vig and Almann Goo introduce this new capability in AWS Glue that makes use of the open source project [PartiQL](https://aws.amazon.com/blogs/opensource/announcing-partiql-one-query-language-for-all-your-data/) a SQL-compatible query language that makes it easy to efficiently query data, regardless of where or in what format it is stored. This is a great session and I can see a lot of developers finding these new capabilities really helpful.

[AWS re:Invent recap: Deep dive on Amazon FSx for Lustre + Amazon S3](https://aws.amazon.com/blogs/storage/supercharge-your-compute-workloads-with-amazon-fsx-for-lustre-and-amazon-s3/) Darryl Osborne provides more info from [his session](https://virtual.awsevents.com/media/1_tso2jrc1) last week. If you missed it and want to know more about how fast, shared file systems can help your compute workloads achieve peak performance and reduce costs. Amazon FSx for Lustre is a fully managed, POSIX-compliant shared file system that provides high-performance storage for Amazon EC2 compute resources without the overhead and complexity of a self-managed file system.

![arch](https://d2908q01vomqb2.cloudfront.net/e1822db470e60d090affd0956d743cb0e7cdf113/2020/12/07/High-performance-storage-prevents-these-system-bottlenecks-so-you-can-reduce-workload-runtimes-accelerate-business-insights-and-save-compute-costs..png)

If you are looking to modernise your existing .NET Framework applications, then Andy Hopper did a great session last week that will help you to take your .NET Framework applications and through the power of the Porting Assistant for .NET, be guided on how to approach this task. [Porting .NET Framework applications to .NET Core on Linux](https://virtual.awsevents.com/media/1_sf86nv88) introduces the open source tool and then Andy walks you through modernising a simple example application to show you how this can really simplify and make the process more straight forward.

### Other open source blog posts

**Firecracker**

[Diving into Firecracker with Alpine](https://dev.l1x.be/posts/2020/12/13/diving-into-firecracker-with-alpine/) Istvan Szukacs brings you the follow up post on getting Firecracker up and running on a Raspberry Pi running Alpine Linux. His first post, [Getting started with Firecracker on Raspberry Pi](https://dev.l1x.be/posts/2020/11/22/getting-started-with-firecracker-on-raspberry-pi/) is where you should start.

**serverless-express**

[AWS Serverless Express Finds a Loving Home at Vendia](https://vendia.net/blog/serverless-express-finds-home-at-vendia) I mentioned this last week but this nice blog post from Vendia's  Brett Andrews and Tim Wagner provide a few more details on the "graduation" of this project from AWS Labs and how this is now being actively supported and sponsored by Vendia.

**AWS re:Invent Machine Learning keynote**

[All the Machine Learning Announcements at AWS re:Invent 2020](https://medium.com/libertyit/all-the-machine-learning-announcements-at-aws-re-invent-2020-ce3b9f917599) AWS Hero Gillian Armstrong put together this very nice summary of all the announcements, both during Andy Jassy's and Shwami Sivasubramanian's keynotes. Plenty of open source stuff in there that I have mentioned above, but take a look at the broader context which this post does a great job in highlighting.

**Kubernetes**

[What’s new for Kubernetes and EKS at AWS re:Invent](https://acloudguru.com/blog/engineering/whats-new-for-kubernetes-and-eks-at-aws-reinvent) Justin Garrison writes up this great summary of the important Kubernetes and Amazon EKS related updates from pre:Invent and re:Invent. If you are into your containers, a must read this week.

**ROS**

[ROS2 Nav2 Go-To-Goal using the low-cost Hadabot Turtle robot kit](https://blog.hadabot.com/ros2-nav2-go-to-goal-low-cost-robot-kit.html) Jack over from the Hadabot team has put together this blog post to talk about a low-cost robot kit for students, software engineers, makers to learn ROS2 and robotics in a hands-on manner. If you are looking to get started but have been put off some of the higher price entry level robots, then check this out.

{% youtube goSqLnv6jhE %}

### Quick updates

**AWS Amplify**

Amplify CLI helps front-end web & mobile developers provision APIs and host websites. Released last week was the ability to deploy the GraphQL & REST APIs and host websites using AWS Fargate in addition to existing AppSync, API Gateway and Amplify console options. The enables you to deploy REST APIs & GraphQL APIs based on Amplify-provided container templates; bring your own containers from other projects - all you need is a Dockerfile or a Docker Compose configuration; and use the out-of-the-box build & deploy pipeline or configure your own custom pipeline.

Amplify’s container-based deployment option is designed to help you focus on your business logic instead of the infrastructure setup as well as the build & deployment pipeline. Run “amplify add api” to create your first container-based API. Just edit the API source code and run “amplify push”. Amplify CLI automatically packages, builds and deploys your container-based API.
One of the key benefits of containers is portability. Amplify CLI also allows you to bring your own containers. The build & deployment options are automatically inferred through your Docker Compose configuration and provides you an escape hatch to do detailed tweaks throughout the build and deployment process. Builds can be completely managed via the Amplify CLI - without requiring Docker to be installed locally - or they can be decoupled and connected to a GitHub repo as source control in team workflows. Multiple environments for development team collaboration are also included.

Amplify libraries can be used to interact with your Fargate-backed APIs when using Amazon Cognito User Pools, giving mobile and web applications secure connectivity and access controls to resources in your VPC. Additionally, existing GraphQL and REST services such as AWS AppSync and Amazon API Gateway can be used in the same project along with Fargate APIs giving flexibility to mix and match for cost optimisation and operational needs.


### Tweet of the week

If you missed these tweets last week from [Eswar Bala](https://twitter.com/bala_eswar) and [Micah Hausler](https://twitter.com/micahhausler) and want to get some great snippets of extra info about Amazon EKS Distro, then check them out. [What is in it? What does that mean? Why might you use it?](https://twitter.com/micahhausler/status/1334279812752424960) and [Amazon EKS goodies](https://twitter.com/bala_eswar/status/1333833318924619776)

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen).

### Your feedback matters!

I have put together a short feedback survey, which I would ask you to take - it will take no more than 2 minutes. You can access [here](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn). Many thanks!

[Take the survey](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn)