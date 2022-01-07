---
title: 'AWS open source news and updates No. 39'
date: '2020-10-12'
tags : [ oss-newsletter ]
---
## October 12th - Instalment #39

Week No.39 - The 39 Steps is a pretty famous film, a spy thriller if you are into those types of films and I recently found out that the name came from a [location](https://en.wikipedia.org/wiki/The_Thirty-Nine_Steps) not too far from me. I am pleased to say that episode 39 of this newsletter is equally thrilling, combining the usual mix of new open source projects (including one so fresh, it is still warm to the touch), blog posts, case studies and events for you to check out. An old friend, JMeter, is also covered this week under the quick updates section so if you are using JMeter, don't miss that. Finally, make sure you check out the Diagram Maker post, which seemed to grab a lot of attention last week, as well as my favourite topic, AWS Graviton2.

**Appsmith**

Last week it was great to speak with Arpit Mohan, CTO and co founder of [Appsmith](https://github.com/appsmithorg/appsmith), an amazing open source project that provides very rich low/no code tooling to enable you to quickly create applications within your organisation. Will try and get it published for the next episode.

**Share your open source project or blog post**

As always, I am always keen to hear from you about what you are working on in open source so please get in touch and let me feature your project or post in this newsletter. 

### Events for your diary

**AWS Community Day, Dublin**
**October 13th, 10:00am BST**

AWS Community in Ireland is running a fully immersive virtual event, covering the hottest AWS topics of the day including Serverless, Machine Learning, AI, AWS Outposts and lots more. Red Hat are one of the sponsors and they will be cover Open Shift, but there are bound to be more sessions covering many of the open source projects you see in this newsletter. This is one of the most vibrant and energising community events, so you should try and make it if you can. Tomorrow, so you still have time today to register... Register via[ this link](https://bit.ly/aws2020dub). Places are limited so grab them while you can.

**Amazon ElastiCache Day**
**October 16th, 9:00am PT**

If you want to know more about this service, from an intro to what it is, and overview of Redis and the chance to join in on Q&A with on of the Redis core team members, Madelyn Olson, then take a look at this one day event and sign up. More details [here](https://pages.awscloud.com/AmazonElasticacheDay.html).

**All Things Open**
**October 19th|20th**

All Things Open is one of the must attend events for open source folks. Check out the event, the speakers and the tracks, you can find the link [here](https://2020.allthingsopen.org/).

**AWS Copilot**
**October 19, 2020, 1:00 PM (PT) | 4:00 PM (ET)**

AWS Copilot is a command line interface tool that helps customers develop, release, and operate containerised applications on AWS. AWS Copilot creates all the infrastructure and artefacts required to run a production-ready service on Amazon ECS and AWS Fargate, including task definitions, image repositories, and AWS resources like load balancers and deployment pipelines. In this tech talk, you will learn how to leverage AWS Copilot to containerise applications and deploy production ready micro-services faster on Amazon ECS, with code demos.

Sign up [here](https://pages.awscloud.com/AWS-Online-Tech-Talks_October-2020.html?webinar=2020_1003-CON).

**KubeFlow**
**October 23, 2020, 1:00 PM (PT) | 4:00 PM (ET)**

Distributed training on Kubernetes is both hard to set up and optimise for ML jobs. In this tech talk, you'll learn how to do distributed training in a Kubeflow Pipelines workflow with a Mask-RCNN model in PyTorch. We'll set up an end to end training job for a computer vision use case on multiple GPU nodes and then deploy that model onto a production endpoint using Kubeflow Pipelines for orchestration and Amazon Sagemaker Components for Kubeflow Pipelines. Our model is a Mask-RCNN model from the Detectron2 model zoo trained on the COCO2017 dataset and further fine-tuned on a custom dataset with aerial imagery.

Sign up [here](https://pages.awscloud.com/AWS-Online-Tech-Talks_October-2020.html?webinar=2020_1015-MCL).

**cdk8s**
**October 27, 2020, 11:00 AM (PT) | 2:00 PM (ET)**

The new CDK for Kubernetes (cdk8s) is an open-source project that lets you define Kubernetes applications and reusable components using familiar programming languages. In this tech talk, learn how csk8s works locally on your machine and generates standard Kubernetes YAML data, so you can use it with any Kubernetes cluster running anywhere, including on-premises and the cloud.

Sign up [here](https://pages.awscloud.com/AWS-Online-Tech-Talks_October-2020.html?webinar=2020_1020-CON).

### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to Gunnar Grosch, Satya Vajrapu, Eric Hsueh, Sid Ilangovan, Sameer Goyal, Nizar Tyrewalla, Imaya Kumar Jagannathan, Benjamin Smith, Sudhir Reddy Maddulapally, Soumya Vanga, Nathan Stornetta, Anh Tran, Asser Moustafa, Matt Ulinski, Channy Yun, Deepu Mathew, Fernando Gonzalez, Kireet Kokala, Albert Niderhofer, Rohan Sawant, Jessie Metcalf, Erik Lundevall-Zara, Bradly Ahrens, Chaim Rand, Rick Cao and Adam Ruka.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

**circuitbreaker-lamda**

[circuitbreaker-lambda](https://github.com/gunnargrosch/circuitbreaker-lambda) is a fresh project from AWS Hero Gunnar Grosch providing a sample Circuit Breaker implementation for your AWS Lambda functions. Detailed instructions are provided together with a sample application to show how you can put this to work. For those who want to know more about what the circuit breaker pattern is and why it is useful in building resilient systems, [check out this post](https://martinfowler.com/bliki/CircuitBreaker.html) from Martin Fowler, and for further reading, Adrian Hornsby has covered this in his extensive posts on building resilient architecture. Check out this post [here](https://medium.com/@adhorn/patterns-for-resilient-architecture-part-2-9b51a7e2f10f) which specific covers circuit breakers.

**lambda-secrets-prefetch**

[lambda-secrets-prefetch](https://github.com/square/lambda-secrets-prefetch) this project is a Lambda extension that pre-fetches secrets from AWS SecretsManager. The developers have put together a nice blog post, [Using AWS Lambda Extensions to Accelerate AWS Secrets Manager Access](https://developer.squareup.com/blog/using-aws-lambda-extensions-to-accelerate-aws-secrets-manager-access/). This is as fresh as it comes, and this collaboration between Michael Weissbacher and Michele Titolo explores a feature that was announced last week, AWS Lambda Extensions, and how they used this to create a new open source project that allows you to more effectively manage your secrets in your function code. The posts talks about barriers that existed before and how this new feature of Lambda as well as their project, will help overcome those challenges.

**aws-eks cdk8s charts**

[aws-eks](https://github.com/aws/aws-cdk/tree/master/packages/%40aws-cdk/aws-eks#cdk8s-charts) fresh from Pahud Hsieh is news of an update to the aws-eks cdk construct library that now comes with native integration with cdk8s. Check out the documentation for more details, which you can find [here](https://github.com/aws/aws-cdk/tree/master/packages/%40aws-cdk/aws-eks#cdk8s-charts).

**aws-cloudformation-resource-providers-sso**

[aws-cloudformation-resource-providers-sso](https://github.com/aws-cloudformation/aws-cloudformation-resource-providers-sso) the AWS SSO CloudFormation resource provider has been open sourced. 

**aws-iamctl**

[aws-iamctl](https://github.com/aws-samples/aws-iamctl/) is a new open source tool that you can use to extract the IAM roles and policies from two accounts, compare them, and report out the differences and statistics. We will explain how to use the tool, and will describe the key concepts so you can configure it to programmatically run against all of your AWS accounts. Sudhir Reddy Maddulapally and Soumya Vanga also put together this blog post, [New IAMCTL tool compares multiple IAM roles and policies](https://aws.amazon.com/blogs/security/new-iamctl-tool-compares-multiple-iam-roles-and-policies/) to help you get started on how you can use it. It is a nice deep dive and should cover use cases and how to configure and use this tool.

![arch](https://d2908q01vomqb2.cloudfront.net/22d200f8670dbdb3e253a90eee5098477c95c23d/2020/09/30/IAM-Role-Comparison-Figure-3.png) 

### AWS open source posts

**Diagram Maker**

[Diagram Maker: Open sourcing IoT visualization](https://aws.amazon.com/blogs/opensource/diagram-maker-open-sourcing-iot-visualization/) by Sid Ilangovan and Sameer Goyal announce a new open source project, [Diagram Maker](https://github.com/awslabs/diagram-maker) which is a library that you can use in your own projects to create interactive visualisation. The project provides detailed documentation on how you can get started; from exploring various demos of this in action, a look at some of the different plugins as well as showcasing it is production use.  If you are looking for an open source library to visualise your data, you should check this project out.

The architecture documentation covers the core components you need to think about, which are nicely summarised in this diagram.

![demo](https://awslabs.github.io/diagram-maker/assets/Architecture.png)

Whilst the post and documentations cover the IoT space, this library can be used for much broader use cases and they provide some examples around how you might build a workflow visualisation layer using something like Diagram Maker. Anyone who is familiar with Node Red will be very at home with this library and UI, and i look forward to seeing how other people are going to use or extend this project.

Vishal Chawla from Analytics India online magazine also featured this project in their post, [Why AWS Recently Open Sourced A GUI Library For IoT Developers](https://analyticsindiamag.com/why-aws-recently-open-sourced-a-gui-library-for-iot-developers/)



**LAMP stack**

[The serverless LAMP stack part 6: From MVC to serverless microservices](https://aws.amazon.com/blogs/compute/the-serverless-lamp-stack-part-6-from-mvc-to-serverless-microservices/) in the latest instalment of the serverless LAMP stack, Benjamin Smith shows you how to build serverless PHP applications using micro services. From using a single Lambda function as scalable web host with an MVC framework, to a decoupled micro service model, Ben provides examples and code, all of which you will find in this [GitHub repository](https://github.com/aws-samples/php-examples-for-aws-lambda/tree/master/0.6-MVC-to-microservice).

![arch](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2020/06/12/Screenshot-2020-06-12-at-16.11.54.png)

**Grafana**

[Analyze and debug applications using AWS X-Ray trace data with Grafana](https://aws.amazon.com/blogs/mt/analyze-debug-applications-aws-x-trace-data-grafana/) by Nizar Tyrewalla and Imaya Kumar Jagannathan announce the open sourcing of the AWS X-Ray data source plugin for Grafana which you can use to visualise your AWS X-Ray traces within your dashboards when you are doing things like troubleshooting or triaging issues. 

This blog posts also covers some of the typical use cases showing how to use it and how to get started. As long as you are using Grafana 7.2 or later you can use this plugin, and you can find it [here](https://grafana.com/grafana/plugins/grafana-x-ray-datasource).

![dash](https://d2908q01vomqb2.cloudfront.net/972a67c48192728a34979d9a35164c1295401b71/2020/10/02/image.png)

**OpenTelemetry Prometheus Exporter**

[Testing the OpenTelemetry C++ Prometheus Exporter](https://aws.amazon.com/blogs/opensource/testing-the-opentelemetry-c-prometheus-exporter/) a follow on post from Eric Hsueh (see No.37) describe engineering contributions to the popular open source observability project OpenTelemetry. OpenTelemetry aims to develop an open standard and provides implementation in multiple programming languages for collecting telemetry data, including metrics, tracing, and logs. In this post, Eric talks about how they learned about testing and how it was critical to ensure that the components of the exporter worked in tandem with other components. Eric talks about the different kinds of testing they used and shares the lessons they learned along the way. 

**AWS ParallelCluster**

[Using multiple queues and instance types in AWS ParallelCluster 2.9](https://aws.amazon.com/blogs/opensource/using-multiple-queues-and-instance-types-in-aws-parallelcluster-2-9/) Nathan Stornetta and Anh Tran share some of the new features available in the latest release of the open source project, AWS ParallelCluster. AWS ParallelCluster has made it simple for high performance computing (HPC) customers to set up easy-to-use environments with compute, storage, job scheduling, and networking in the cloud in one cohesive package. In version 2.9, two new features covered in this post are around how this new release support multiple job queues and multiple instance types.

* Multiple job queues - a common setup inside many traditional HPC environments is to use multiple queues that have varying levels of priority and different compute resources associated with them. This helps ensure that the most urgent workloads have prioritised access to any resources they require, whereas other workloads can wait longer or run on resources with lower costs.
* Multiple instance types - allows you to separate workflows into either multiple queues or multiple instance types within the same queue and select distinct compute resources optimised for the price/performance or memory/CPU of each step in our workflow or for different workload types. 

These new features enable customers to have more complex and varied HPC workflows that can be used to optimise costs and help with things like prioritisation.

**Jenkins**

[Integrating Jenkins with AWS CodeArtifact to publish and consume Python artifacts](https://aws.amazon.com/blogs/devops/using-jenkins-with-codeartifact/) Matt Ulinski shows you how you can manage/publish your software packages and then consume these within your Jenkins projects. The walkthrough takes you through the package/publish and consume/deploy process, ending up with the sample application deployed on AWS Fargate. You will learn everything you need to set up your own environment, and to make it even easier, Matt provides you with a CloudFormation template that will deploy the solution.

![arch](https://d2908q01vomqb2.cloudfront.net/7719a1c782a1ba91c031a682a0a2f8658209adbf/2020/08/29/jenkins-ca-python.png)

**AWS CDK**

[Migrating CloudFormation templates to the AWS Cloud Development Kit](https://aws.amazon.com/blogs/developer/migrating-cloudformation-templates-to-the-aws-cloud-development-kit/) from Adam Ruka writes how using a new feature of AWS CDK, you can now import your existing CloudFormation templates into your CDK stack. Once loaded, you can then modify objects defined in your templates directly within your CDK code, or reference existing template resources when creating new CDK constructs. The **CfnInclude** class is what makes this happen. Adam covers some use cases and where you might find this useful and there are some things you need to watch out for. So, now that you have an idea, check out the blog post for the deep dive with examples.

**Amazon Redshift**

[Building high-quality benchmark tests for Redshift using open-source tools: Best practices](https://aws.amazon.com/blogs/big-data/building-high-quality-benchmark-tests-for-redshift-using-open-source-tools-best-practices/) in the first of a series of posts, Asser Moustafa talks about how open source tools are often the preferred choice when customers look to profile and benchmark workloads, and shares some best practices and things to look out for. So if you have been using tools like SQLWorkbench, psql, and Apache JMeter then you should check out what Asser has to say.

![test](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2020/09/16/bemchmarking-redshift-2.jpg) 

**Redis**

[New – Redis 6 Compatibility for Amazon ElastiCache](https://aws.amazon.com/blogs/aws/new-redis-6-compatibility-for-amazon-elasticache/) Channy Yun walks you through some of the key features introduced with this update, including managed role based access control (RBAC), client side caching and operational improvements to the managed service. Also, make sure you check out the Amazon ElastiCache Day, a free virtual event - see above in the Events section.

In further news, Amazon ElastiCache for Redis and Memcached are now supported to run on Graviton2 M6g and R6g instance types, which is great for customers who will now be able to enjoy better price/performance characteristics that these instance types provide. To read more about this, check the release note [here](https://aws.amazon.com/about-aws/whats-new/2020/10/amazon-elasticache-now-supports-m6g-and-r6g-graviton2-based-instances/).

**Elasticsearch**

[Automating Index State Management for Amazon ES](https://aws.amazon.com/blogs/big-data/automating-index-state-management-for-amazon-es/) Satya Vajrapu's post show you how to use policies that have been introduced with [Index State Management (ISM)](https://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/ism.html) to implement a sample policy to automate routine index management tasks and apply them to indexes and index patterns. Maintaining multiple indexes for diverse data workloads, typically means the setting up of custom solutions to manage the indexes’ lifecycle which can quickly become tedious as the indexes grow and result in housekeeping overheads. ISM allows you to automate those tasks via policies and you can use a variety of criteria when defining those policies. Take a peek for more details on what those might be.

![index](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2020/10/05/index-state-es-12-1.jpg)

**.NET Core**

This great demo from Steve Roberts walks you through how you can use Porting Assistance for .NET to modernise your .NET applications and move them to .NET Core.  You will see how to install and configure the assistant, followed by how you use it to analyse and assess both the effort required, and the optimal places to start, when porting a typical .NET Framework application to .NET Core.  The video also shows how you can use the Porting Assistant to safely update project files, determine NuGet package version upgrades, and locate API calls in the source code that need to be resolved to make the application's projects compatible with .NET Core.

{% youtube mMu7qahc9-0 %}

**TorchServe**

[Using TorchServe to list PyTorch models at scale in AWS Marketplace](https://aws.amazon.com/blogs/awsmarketplace/using-torchserve-to-list-pytorch-models-at-scale-in-aws-marketplace/) Rick Cao walks you through how you can publish your TorchServe models in the AWS MarketPlace. TorchServe is collaboration between AWS and Facebook that allows you to deploy your PyTorch models  without your data scientists or engineers needing to write any custom code. This post shows how you can use a feature of this framework to deploy those models on the AWS Marketplace. This might be useful if you wanted an easy way to make your models available to a wider set of users.

![image](https://d2908q01vomqb2.cloudfront.net/761f22b2c1593d0bb87e0b606f990ba4974706de/2020/09/18/listing_on_marketplace.png)

### Case Study

**Public Sector**

[Bridging data silos to house and serve the homeless](https://aws.amazon.com/blogs/publicsector/bridging-data-silos-house-serve-homeless) by Jessie Metcalf shows how an open source project developed by Green River, [Open Path](https://www.openpath.host/) is being used to tackle how to identify chronically homeless individuals. Open Path is a data integration platform that supports care coordination, coordinated entry processes, and in-depth analysis of homeless services and being open source it has allowed the application code to be available at no cost to any community to adopt, and that any enhancements made by other communities will benefit all adopters. In this post you will see how a few states such as Texas, Virginia and Boston are working in concert to coordinate activities and help those individuals.

### AWS Partner Network

**Apache Hudi and nClouds**

[How nClouds Helps Accelerate Data Delivery with Apache Hudi on Amazon EMR](https://aws.amazon.com/blogs/apn/how-nclouds-helps-accelerate-data-delivery-with-apache-hudi-on-amazon-emr/) a collaboration between Deepu Mathew, Fernando Gonzalez, (Sr. DevOps Engineers) and Kireet Kokala, (VP Big Data & Analytics) at nClouds who share how they are helping their customers with the challenges of data latency, data quality, system reliability, and data privacy compliance. They take a look at how they are using Apache Hudi on Amazon EMR to build large-scale and near real-time applications that require incremental data pipelines and processing, and walk you through how you can build a quick PoC environment.

Apache Hudi is an open source data management framework used to simplify incremental data processing and data pipeline development. It was originally developed at Uber in 2016 to enable faster data for petabyte-scale data analytics, low latency database ingestion, and high efficiency and is often used for simplified data pipelines into data lakes and analytics services, Change Data Capture (CDC) with record-level granularity, and near real-time analytics of data sets by SQL query engines like Apache Hive and Presto.

![arch](https://d2908q01vomqb2.cloudfront.net/77de68daecd823babbb58edb1c8e14d7106e83bb/2020/10/06/nClouds-Hudi-EMR-1.jpg)

**Okta Access Tokens in PHP**

[Validating Okta Access Tokens in PHP using AWS API Gateway and Lambda Authorizers](https://developer.okta.com/blog/2020/10/05/validating-okta-access-tokens-php-aws-api-gateway-lambda) nice post from David Mavin for those who are using Okta as part of your authentication/authorisation layer, and how you can validate access tokens using a Lambda authoriser in PHP. The post will walk you through what Lambda authorisers are, how to generate JWT tokens with some simple commands and then put together your PHP authoriser function.

### Latest blog posts

**TensorFlow**

[Debugging in TensorFlow](https://towardsdatascience.com/debugging-in-tensorflow-392b193d0b8) is another excellent post from Chaim Rand from MobileEye, walks you through the process of debugging your TensorFlow training programs. From a nice intro on exactly what is debugging (very nice quote, "If debugging is the process of removing software bugs, then programming must be the process of putting them in." /Edsger Dijkstra.) Chaim shares some best practices to help save your sanity when the inevitable bug comes your way.

**RASA**

[Deploying RASA on AWS EC2 and using the model stored on S3](https://medium.com/graymatrix/deploying-rasa-on-aws-ec2-and-using-the-model-stored-on-s3-9edfcfb15ffe) this post from Simran Kaur Kahlon is just what you will need if you are looking into RASA, an open source machine learning framework that is used in automated text and voice-based conversation use cases. You can use it to do things like build chatbots and this post will walk you through how to get your RASA environment up and running.


**Laravel**

What to know how to host your Laravel 8 application on AWS? Want to go further and integrate them into a CI/CD pipeline and maybe integrate with some services? That and more is covered in this video from Bradly Ahrens.

{% youtube KtpiF3SUCkA %}

**AWS Kinesis Video Streaming on Linux**

[How to stream video using AWS Kinesis Video Streaming - Docker on Linux?](https://dev.to/rohansawant/how-to-stream-video-using-aws-kinesis-video-streaming-with-docker-on-linux-14e9) Rohan Sawant shares how we managed to stream video from his machine to AWS using the AWS Kinesis Video Streaming service. Make sure you check out his other post, [The story of how I (kinda') fixed AWS Kinesis Producers, helped a student, and saved humanity hundreds of man-hours!](https://dev.to/rohansawant/the-story-of-how-i-kinda-fixed-aws-kinesis-producers-helped-a-student-and-saved-humanity-hundreds-of-man-hours-17e8) about the work that he did behind the scenes. Nice work Rohan.

**AWS Encryption SDK**

[AWS Encryption SDK in Baby Steps](https://medium.com/cyberark-engineering/aws-encryption-sdk-in-baby-steps-a2a5a99cea24)
from Albert Niderhofer at CyberArk introduces the open source AWS Encryption SDK, what it is and how you can use it, and then provides a simple walkthrough to show you this in action. If you wanted to know more about this SDK, this is the perfect post and make sure you check out the Top Ten Key Facts too.

![arch](https://miro.medium.com/max/2000/1*SZR4mu1dVwRLNkVJ0_7KOA.png)

**AWS CDK and F#**

[F# for the Cloud Worker - Part 5 - AWS Cloud Development Kit](https://elz.cloud/post/fsharp-for-cloud-worker-part5/) Erik Lundevall-Zara dives deep at how you can use AWS CDK with .NET and F#, but provides a good starting point if you want to know more about AWS CDK too and Erik does a great job is explaining the interactions and components and how they all work together.


### Quick updates

**Fluent Bit v1.6**

[Fluent Bit v1.6](https://fluentbit.io/announcements/v1.6.0/) was announced over the weekend, with major contributions from AWS in both new features and improvements. New new plugins were created (for Amazon S3 and Amazon Kinesis) as well as some other improvements to AWS integration.

**New open datasets available**

Thirty-two new or updated datasets from the Massachusetts Institute of Technology, the First Street Foundation, Ookla, and others are available on the Registry of Open Data. [Check out the release note](https://aws.amazon.com/about-aws/whats-new/2020/10/new-aws-public-datasets-available/) for more info, but if you are looking for the latest open data covering COVID-19, Life sciences, Geospatial, climate and weather, machine learning or networking datasets, there is something for you in this list. 


**Apache Flink**

Apache Flink Kinesis Consumer now supports Enhanced Fan Out (EFO) and the HTTP/2 data retrieval API for Amazon Kinesis Data Streams. EFO allows Amazon Kinesis Data Streams consumers to scale by offering each consumer a dedicated read throughput up to 2MB/second. The HTTP/2 data retrieval API reduces latency of data delivery from producers to consumers to 70 milliseconds or better. In combination, these two features allow you to build low latency Apache Flink applications that utilize dedicated throughput from Amazon Kinesis Data Streams.

Amazon Kinesis Data Analytics is the easiest way to transform and analyze streaming data in real time with Apache Flink. Apache Flink is an open source framework and engine for processing data streams. Amazon Kinesis Data Analytics reduces the complexity of building and managing Apache Flink applications. Amazon Kinesis Data Analytics for Apache Flink integrates with Amazon Managed Streaming for Apache Kafka (Amazon MSK), Amazon Kinesis Data Streams, Amazon Elasticsearch Service, Amazon DynamoDB streams, Amazon S3, custom integrations, and more using built-in connectors. You can learn more about Amazon Kinesis Data Analytics for Apache Flink here.

**Redis**

Amazon ElastiCache for Redis now supports Redis 6. This release brings several new and important features to Amazon ElastiCache for Redis.

* Managed Role-Based Access Control – Amazon ElastiCache for Redis 6 now provides you with the ability to create and manage users and user groups that can be used to set up Role-Based Access Control (RBAC) for Redis commands. You can now simplify your architecture while maintaining security boundaries by having several applications use the same Redis cluster without being able to access each other’s data. You can also take advantage of granular access control and authorization to create administration and read-only user groups. Amazon ElastiCache enhances the new Access Control Lists (ACL) introduced in open source Redis 6 to provide a managed RBAC experience, making it easy to set up access control across several Amazon ElastiCache for Redis clusters.
* Client-Side Caching - Amazon ElastiCache for Redis 6 comes with server-side enhancements to deliver efficient client-side caching to further improve your application performance. Redis clusters now support client-side caching by tracking client requests and sending invalidation messages for data stored on the client. In addition, you can also take advantage of a broadcast mode that allows clients to subscribe to a set of notifications from Redis clusters.
* Significant Operational Improvements - This release also includes several enhancements that improve application availability and reliability. Specifically, Amazon ElastiCache has improved replication under low memory conditions, especially for workloads with medium/large sized keys, by reducing latency and the time it takes to perform snapshots. Open source Redis enhancements include improvements to expiry algorithm for faster eviction of expired keys and various bug fixes.

**JMeter**

[Distributed Load Testing](https://aws.amazon.com/solutions/implementations/distributed-load-testing-on-aws/) on AWS helps you easily simulate thousands of users connecting to your application so that you can better understand your application performance under load. The solution launches and configures containers on AWS Fargate to generate a specified number of transactions per second without having to provision servers. 

This update adds support for JMeter test scripts. JMeter is a popular open source application for testing functional behavior and performance, and this update allows customers to use JMeter scripts to test the robustness of their applications. This update also introduces AWS Step Functions to reduce solution complexity.

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen).

### Your feedback matters!

I have put together a short feedback survey, which I would ask you to take - it will take no more than 2 minutes. You can access [here](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn). Many thanks!

[Take the survey](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn)
