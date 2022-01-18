---
title: 'AWS open source news and updates No. 25'
date: '2020-06-22'
tags : [ oss-newsletter ]
---
## June 22nd - Instalment #25

No.25 is another packed edition with plenty of interesting projects and stories for you to read, whether you are into machine learning, robots, cutting your teeth on code or looking at how to automate and secure your deployments, there is something for you.

As we past the summer equinox and very close to the half way point of the year, I wanted to share some of the data I have collected over the past six months when putting together this digest and speaking with the builders and business' using open source.

I have been tracking the impact of these weekly digests and wanted to share some quantitate and qualitative data with you.

**Stats**

* Over 487 articles shared authored by over 194 different authors
* Over 80K social engagements and 8000 unique page views with an average of 8.6% engagement
* Most articles cover third party open source projects (23%) with AWS open source projects (like Firecracker) next with 15%
* 11% of the articles cover security topics, the most popular topic
* Majority of people viewing these updates are coming from UK, US, China, India and Germany

I will share more detailed data and stats at the end of the year. 

### Please complete this short survey

I have put together a short feedback survey, which I would ask you to take - it will take no more than 2 minutes. You can access [here](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn). Many thanks!

[Take the survey](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn)

### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created.

So thank you to Soji Adeshina, Mohamed Zenadi, Saša Savić, Benjamin Crozat, Marc Brooker, Tommaso Visconti, Martin Wie, Michael Hart, Gabe Hollombe, Shreyas Subramanian, Thiago de Faria, Kyle Fazzari, Ken Collins, Bojan Zivic, Sreejith Munthikodu, Ashish Kurmi, Kaibo Ma, Ankit Kumar, Ben Smith, James Saryerwinnie, Anuj Singh, Steven David, Brad Porter, Xuejiao Zhang and Daniele Stroppa

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

**AWS Lambda Powertools goes GA**

I have mentioned this project from colleague Heitor Lessa a few times (in [No. 18](https://dev.to/094459/aws-open-sources-news-and-updates-no-18-3a9g) and [No. 23](https://dev.to/aws/aws-open-source-news-and-updates-no-23-p0a)) but the tool was still in preview during this time. [AWS Lambda Powertools](https://github.com/awslabs/aws-lambda-powertools-python/releases/tag/v1.0.0) is a suite of utilities for AWS Lambda Functions that makes tracing with AWS X-Ray, structured logging and creating custom metrics asynchronously easier. Watch out later this week on the AWS open source blog as we hope to have a great post from Tom McCarthy that will help you get started.

Congratulations to Heitor for getting this over the line, and keep watching for more news on this project.

**Barberousse**

[Barberousse - Remote Secrets Editor](https://github.com/zeapo/barberousse) is a project I heard about via the AWS Reddit channel, and comes from [Mohamed Zenadi](https://github.com/zeapo). It is still at the early stages and Mohamed is looking to get more people having a look at providing feedback, but this tool allows you to view,edit and copy secrets in files without having to download/store those files locally. Currently supports AWS Secret Manager and supports yaml and json formats.

Now all I need to know is where the name came from :)

**CredoPy**

Martin Wie's first open source project on GitHub, [CredoPy](https://github.com/MartinWie/CredoPy), looks to make you more secure by adopting the "troy password credo", the company where he works. What is this manifesto? Well, it is simple - It's very simple: Never store credentials unencrypted!

This project provides you with a python based command line tool to help you do this. (Cre)Pydo is a tool that injects aws parameter store strings and secure strings into your memory as an environment variable.

Lots of detailed documentation to get you going, including how to install and configure. Thank you Martin. [GitHub repository here](https://github.com/MartinWie/CredoPy).

**cmda**

[Michael Hart](https://twitter.com/hichaelmart/status/1272985191787778048) has been busy again, this time with a project called **[cmda](https://github.com/lambci/cmda)** (that you can also find this in the Serverless Application Repository [here](https://serverlessrepo.aws.amazon.com/applications/arn:aws:serverlessrepo:us-east-1:553035198032:applications~cmda))

So what does cmda do? A command line tool for copying files to/from AWS Lambda, which given the release this week of AWS EFS for AWS Lambda, is especially useful with EFS. Michael provides great installation instructions and usage guidance.

Thanks Michael.

**saml2aws**

[saml2aws](https://github.com/Versent/saml2aws) is an open source project that provides a CLI tool which enables you to login and retrieve AWS temporary credentials using with ADFS or PingFederate Identity Providers. This project provides details instructions and documentation on how to use it. It supports a broad range of identity providers too.

**cfn-guard**

Cloudformation Guard, or [cfn-guard](https://github.com/aws-cloudformation/cloudformation-guard), is a set of tools to check AWS CloudFormation templates for policy compliance using a simple, policy-as-code, declarative syntax and helps enterprises keep their AWS infrastructure and application resources in compliance with their company policy guidelines. 

Cfn-guard provides compliance administrators with a simple, policy-as-code language to define rules that can check for both required and prohibited resource configurations. It enables developers to validate their CloudFormation templates against those rules.

Cfn-guard helps enterprises minimize risks related to overspending on operating costs, security vulnerabilities, legal issues, and more. For example, administrators can create rules to ensure that developers always create encrypted Amazon S3 buckets. Cfn-guard has a lightweight, declarative syntax that allows administrators to define rules quickly without needing to learn a programming language.

Developers can use cfn-guard either locally while editing templates or automatically as part of a CI/CD pipeline to stop deployment of non-compliant resources. If resources in the template fail the rules, cfn-guard provides developers information to help identify non-compliant resources. 

GitHub repository [here](https://github.com/aws-cloudformation/cloudformation-guard).

**cfn-rulegen**

cfn-guard-rulegen, is a related project to cfn-guard, that lets administrators extract rules from existing compliant CloudFormation templates which means they don’t have to create rules from scratch which speeds up the rules authoring process. The rules become a consistent record of compliant resource configurations that administrators can check into a source control such as GitHub to share across teams.  

GitHub repository [here](https://github.com/aws-cloudformation/cloudformation-guard/tree/master/cfn-guard-rulegen).

**Multiplayer slider AWS AppSync demo**

An AWS AppSync demo from my colleague [Gabe Hollombe](https://twitter.com/gabehollombe), to showcase how you can use an AWS AppSync Local Resolver (also known as a NONE Data Source type) to get simple broadcast pub/sub over websockets. The client code is built in React.

![demo](https://raw.githubusercontent.com/gabehollombe-aws/appsync-for-pubsub-demo/gh-pages/docs/MultiplayerSlidersDemo.gif)

Get the source code [here](https://github.com/gabehollombe-aws/appsync-for-pubsub-demo/), and make sure you follow Gabe for more updates on social and GitHub.

[RoboRover](https://github.com/sasasavic82/roborover) from Saša Savić is a two-wheeled robot equipped with a pan/tilt camera and sensors, controlled via REST APIs through AWS IoT infrastructure and integrated into AWS Rekognition (object detection & classification) service.

![diagram](https://github.com/sasasavic82/roborover/raw/master/docs/roborover-architecture.png)

Nice project Saša

**ecs-composeX**

First mentioned in [No. 13](https://dev.to/aws/aws-open-source-news-and-updates-no-13-46fg), [No. 16](https://dev.to/aws/aws-open-source-news-and-updates-no-16-3bp5) and then [No. 21](https://dev.to/aws/aws-open-sources-new-and-updates-no-21-3if8), John has released a new version of this project, [v0.3.0](https://pypi.org/project/ecs-composex/0.3.0/). What does ECS Compose X do? ECS ComposeX translates the services definition in the docker compose file into the ECS definitions to allow the service to run on AWS. It will, doing so, create all the necessary elements to ensure a successful and feature rich deployment into ECS.

Super clear documentation, so if you are looking Build your infrastructure and deploy your services to AWS services using docker-compose file format

Thanks John!

### Blog posts you should check out

**Baker**

Tommaso Visconti from NextRoll walks us through this in depth post around how NextRoll were able to reduce the overall costs of delivering one service, called OMFG (one minute file generator), using an in house technology developed in Go called Baker. 

NextRoll were looking to reduce costs and increase stability of their existing solution (based on Apache Storm), and this led to them using Baker, an in house data processing tool that they developed.

![baker](https://tech.nextroll.com/images/post_images/omfg_new_infra.jpg)

So, where can I get hold of Baker? Well, you are going to have to wait a short time. The post tells us that whilst Baker is not currently open source..
>We are actively working to make Baker an open source software. It will be publicly available over the next months, so stay tuned!

Check out the full post, [How we saved with spot market](https://tech.nextroll.com/blog/dev/2020/06/16/how-we-saved-with-spot-market.html).

**Setting up your Hugo website**

In this great post, [Hugo website with SSL on S3 is straightforward, right? Errrrm…](https://itnext.io/hugo-website-with-ssl-on-s3-is-straightforward-right-errrrm-369c0f19ab07), from Thiago de Faria, he walks you through this deep dive of everything you need to know and think about when deploying your static hugo based sites on AWS. Lots of great learnings here, from distributing the site using CloudFront, setting up certificates and configuring DNS, this post should cover everything you need to know.


**freeBSD 11.4**

Quick update from the freeBSD folk who announced 11.4, the fifth and final release of the stable/11 branch. Find out more about the release [here](https://www.freebsd.org/releases/11.4R/announce.html), and if you want to get going and start running it, check it out on the AWS Marketplace [here](https://aws.amazon.com/marketplace/pp/B01LWSWRED/).


**ROS 2 Security**

Last week we had a couple of posts around ROS 2, so this week we have Kyle Fazzari who writes in his post, [ROS 2 Foxy Fitzroy and its Enhanced Security Monitoring](https://ubuntu.com/blog/ros-2-foxy-fitzroy-and-its-enhanced-security-monitoring) about some of the security related topics of this update.

This is a great post to get a deeper understand of the security architecture and layers that underpin ROS 2 security.

**Gazebo resources**

If you are looking for some Gazebo worlds in which to run your simulations and test your robotics, then this post will be useful. Matt Hansen shares some of the AWS RoboMaker resources you can use: Small Warehouse, Bookstore and Small House. 

![world1](https://aws1.discourse-cdn.com/business7/uploads/ros/optimized/2X/7/7915f5097c99c507c69f6a988e7afa72e2ee400f_2_690x394.jpeg)

You can find the post [here](https://discourse.ros.org/t/gazebo-small-warehouse-bookstore-and-small-house-worlds-available-for-simulation/14915), and the resources in the [GitHub repository here](https://github.com/aws-robotics/aws-robomaker-small-warehouse-world).

Check the comments too, as there are some additional resources and updates there, including this one [here](https://github.com/mlherd/gazebo_worlds_models_maps_for_testing_navigation) from Melih Erdogan.

![world2](https://github.com/mlherd/gazebo_worlds_models_for_testing_navigation/raw/master/worlds/bookstore/bookstore.jpg?raw=true)

Thanks Melih and Matt!

**AWS Lambda and Ruby workshop**

From AWS Serverless Hero Ken Collins, [AWS Lambda Microservice Workshop using S3, Libvips, & Ruby](https://dev.to/aws-heroes/aws-lambda-microservice-workshop-using-s3-libvips-ruby-4o96) provides a step by step workshop that will show you how to use AWS SAM to develop your Ruby application and deploy on AWS Lambda. This is pretty neat and I am going to try and give this one a go this week.

**Keycloak, open source identity federation**

Keycloak, developed by Redhat, is an open solution to identity federation, and one that works with AWS. In this post by  Bojan Zivic, [Keycloak: A case for open-source IDP](https://www.ac3.com.au/resources/keycloak-a-case-for-open-source-idp) he shares his experience in implementing Keycloak, and how he and his team approached the decision making process and how they looked at all the alternative before settling on this. If you are currently looking at iDP solutions, worth a read to see if his approach might help you.

**Python Dashboards**

Data Scientist Sreejith Munthikodu's blog post, [Deploy a Python Dashboard on AWS](https://www.linkedin.com/pulse/deploy-python-dashboard-aws-sreejith-munthikodu/) shows you how to quickly get up and running with the open source [plotly dash](https://plotly.com/dash/) project, and he shows you how to build a COVID-19 dashboard using data from the COVID-19 Data Repository by the Center for Systems Science and Engineering (CSSE) at Johns Hopkins University.

**Monitoring at Uber with CMON and Hammer**

Ashish Kurmi, Kaibo Ma, and Ankit Kumar, from Security Engineering at Uber have put together a great post on how they approach monitoring cloud native applications across all their environments, on-premises and public cloud. In [AWS Continuous Monitoring](https://medium.com/@ubersecurity/part-1-aws-continuous-monitoring-f39f81ea6801) they talk about CMON (Cloud Monitoring), a service they built to help this and discuss how they are using an open source monitoring tool developed at Dow Jones called Hammer, that integrates with CMON.

If you want to read the follow on part two, you can get that [here](https://medium.com/@ubersecurity/part-2-aws-monitoring-case-studies-9fbc613aff28).

**Deep Graph Library**

The [Deep Graph Library (DGL)](https://www.dgl.ai/) is an easy-to-use, high performance and scalable open source Python package for deep learning on graphs. DGL is framework agnostic, meaning if a deep graph model is a component of an end-to-end application, the rest of the logics can be implemented in any major frameworks, such as PyTorch, Apache MXNet or TensorFlow.

![architecture](https://camo.githubusercontent.com/c90495a9407f6f21a5ed133355d5d6693699af97/687474703a2f2f646174612e64676c2e61692f61737365742f696d6167652f44474c2d417263682e706e67)

A couple of posts this week relating to the Deep Graph Library. The first is a collaboration between Amazon Shanghai AI Lab and AWS Deep Engine Science team working along with academic collaborators from the University of Minnesota, The Ohio State University, and Hunan University. This collaboration has led to the creation of the [Drug Repurposing Knowledge Graph (DRKG)](https://github.com/gnn4dr/DRKG) and a set of machine learning tools, DGL-KE, that can be used to prioritise drugs for repurposing studies.

![drugs](https://github.com/gnn4dr/DRKG/raw/master/connectivity.png)

DRKG is a comprehensive biological knowledge graph that relates human genes, compounds, biological processes, drug side effects, diseases and symptoms. DRKG includes, curates, and normalizes information from six publicly available databases and data that were collected from recent publications related to Covid-19. You can read more by checking out this blog post, [Fighting COVID-19 with Deep Graph](https://www.dgl.ai/news/2020/06/09/covid.html).

The second is a post from Soji Adeshina, [Detecting fraud in heterogeneous networks using Amazon SageMaker and Deep Graph Library](https://aws.amazon.com/blogs/machine-learning/detecting-fraud-in-heterogeneous-networks-using-amazon-sagemaker-and-deep-graph-library/), that shows how to construct a heterogeneous graph from user transactions and activity and use that graph and other collected features to train a GNN model to predict which transactions are fraudulent.

Today businesses use rule-based filters to prevent malicious activity in their systems, these filters are often brittle and may not capture the full range of malicious behavior and solutions, that leverage graph techniques, are especially suited for detecting fraudsters and malicious users.

Nice post Soji.

### Request for Comment

**AWS Amplify CLI**

The Amplify team have posted the initial design for proposed tagging support in the Amplify CLI. You can find that [here](https://github.com/aws-amplify/amplify-cli/issues/4607) and this is your chance to have your say, provide your requirements and influence the direction of the project.
 
### AWS updates

**Firecracker**

In February you had the chance to hear Marc Brooker talks about Firecracker. If you want to learn why it was built and how it’s used inside AWS Lambda, then it is worth checking out. This is a deep dive and covers a lot of the decision making, challenges and solutions that led to the creation of Firecracker, and the end covers lessons learned which I found very useful as well. The video just hit the Inside Amazon YouTube channel, so enjoy.

{% youtube H9a2VbeiY8E %}

**ezsmdeploy**

In this post, [Deploy machine learning models to Amazon SageMaker using the ezsmdeploy Python package and a few lines of code](https://aws.amazon.com/blogs/opensource/deploy-machine-learning-models-to-amazon-sagemaker-using-the-ezsmdeploy-python-package-and-a-few-lines-of-code/),  Shreyas Subramanian introduces the open source SDK ezsmdeploy and how you can use this to deploy your machine learning models with the minimum of effort.

Ezsmdeploy is a Python based SDK helps you easily deploy machine learning models and provides a rich set of features, such as the ability to pass one or more model files, to automatically choose an instance based on model size or based on a budget, and to load-test endpoints using an intuitive API. ezsmdeploy lets users deploy a model by passing in one or more model files for deployment, an inference script, and any other additional requirements used by the inference script.

This post walks you installing and the creating your first ezsmdeploy script, and you will find lots of details and further examples in the GitHub repository [here](https://github.com/aws-samples/easy-amazon-sagemaker-deployments) for TensorFlow, PyTorch, MXNet, and scikit-learn

**AWS Data Wrangler**

Quick update from this project, which [released 1.5](https://github.com/awslabs/aws-data-wrangler/releases/tag/1.5.0) this week. What is AWS Data Wrangler? It is an open-source Python package that extends the power of Pandas library to AWS connecting DataFrames and AWS data related services (Amazon Redshift, AWS Glue, Amazon Athena, Amazon EMR, Amazon QuickSight, etc). It is built on top of other open-source projects like Pandas, Apache Arrow, Boto3, s3fs, SQLAlchemy, Psycopg2 and PyMySQL, and provides abstracted functions to execute usual ETL tasks like load/unload data from Data Lakes, Data Warehouses and Databases.

In this update, they have now added Amazon Quicksight support as well as provided some general improvements. You can get started [here](https://aws-data-wrangler.readthedocs.io/en/latest/).

**LAMP part two**

So last week I introduced a number of PHP based articles, and I am delighted that Ben Smith has created a follow up post, [Introducing the serverless LAMP stack – part 2 relational databases](https://aws.amazon.com/blogs/compute/introducing-the-serverless-lamp-stack-part-2-relational-databases/). In this post he concentrates on the data side, and looks at using Amazon RDS MySQL as the data store as well as RDS Proxy as a way of managing the connections from the PHP Lambda functions.

![flow](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2020/06/12/rdsTokenexchange.png)

Check out the post as well as the [GitHub samples page](https://github.com/aws-samples/php-examples-for-AWS-Lambda).

**AWS Chalice Now Supports YAML Templates**

James Saryerwinnie writes in [AWS Chalice Now Supports YAML Templates](https://aws.amazon.com/blogs/developer/aws-chalice-now-supports-yaml-templates/) about an update to **AWS Chalice**, a framework for writing serverless applications in Python, and how it now adds support for YAML when generating and merging AWS Serverless Application Model (SAM) templates. This allows additional AWS resources to be added to Chalice application.

Get access to AWS Chalice via the GitHub repository [here](https://github.com/aws/chalice).

**Calico on Amazon EKS Windows Containers**

In the post, [Using Calico on Amazon EKS Windows Containers](https://aws.amazon.com/blogs/containers/using-calico-on-amazon-eks-windows-containers/) Anuj Singh and Steven David provide a detailed, step by step guid on how to use Calico for Windows containers.

Calico is an open source networking and network security solution for containers, virtual machines, and native host-based workloads and Tigera Calico for Windows is a networking and network security solution for Kubernetes-based Windows workloads allowing you to move Windows workloads like .NET applications into an EKS environment and Calico can help you manage network policy enforcement.

**Distance Assistant**

Brad Porter [blogs](https://blog.aboutamazon.com/operations/amazon-introduces-distance-assistant) about the use of machine learning to provide real time social distancing feedback which we plan to open source. From the post:

>One early solution we developed applies artificial intelligence and machine learning to the camera footage in our buildings to help site leaders identify high traffic areas and implement additional measures to improve social distancing.

You can see the solution in action here:

{% youtube FexuGnXVkvE %}

Once this project is open sourced I will share more details.

**Creating serverless applications with the AWS Cloud Development Kit**

Daniele Stroppa's post, [Creating serverless applications with the AWS Cloud Development Kit](https://aws.amazon.com/blogs/compute/creating-serverless-applications-with-the-aws-cloud-development-kit/) walks you through creating a serverless application using AWS CDK. You will create the code to create the application and configure the pipeline to automatically deploy changes to the code.

**Policy as Code with AWS CDK and Open Policy Agent**

In [Realize Policy-as-Code with AWS Cloud Development Kit through Open Policy Agent](https://aws.amazon.com/blogs/opensource/realize-policy-as-code-with-aws-cloud-development-kit-through-open-policy-agent/), Xuejiao Zhang introduces the CNCF incubating project Open Policy Agent, and shows you how to integrate this using AWS CDK to create Policy as Code.

Many organizations use baselines that are used to ensure compliance requirements are met and set criteria to define operational readiness and keep security baselines to ensure that the infrastructure changes don’t cause problems. Open Policy Agent (OPA), a Cloud Native Computing Foundation incubating project, is designed to automate policy tests. OPA provides a unified framework and language for declaring, implementing, and controlling the policies of various components in cloud native solutions.

As Xuejiao concludes, adopting this will move you one step closer to DevSecOps.

### Quick updates

**AWS App Mesh**

A couple of updates this week on AWS App Mesh. [App Mesh](https://github.com/aws/aws-app-mesh-examples) makes it easy to run microservices by providing consistent visibility and network traffic controls for every microservice in an application. App Mesh separates the logic needed for monitoring and controlling communications into a proxy that runs next to every microservice. App Mesh uses Envoy, an open source proxy, making it compatible with a wide range of AWS partner and open source tools for monitoring microservices.

**AWS App Mesh introduces timeout configuration support**

You can now configure timeouts on your AWS App Mesh virtual nodes and individual routes. Configuring timeouts will allow you to add resiliency to your system with no changes to your services. AWS App Mesh is a service mesh that provides application-level networking to make it easy for your services to communicate with each other across multiple types of compute infrastructure. App Mesh standardizes how your services communicate, giving you end-to-end visibility and ensuring high-availability for your applications. 

AWS App Mesh supports two types of timeouts: per-request, which controls the amount of time that a requester will wait to complete a response, and idle, that controls the time at which the connection will be terminated if there are no active streams. Now you can control these timeouts on the virtual node listener level, or at each individual route.

**AWS App Mesh controller for Kubernetes is now generally available**

AWS App Mesh controller for Kubernetes provides a way to integrate AWS App Mesh with Kubernetes. It offers a Kubernetes-native experience to creating and updating the mesh. AWS App Mesh is a service mesh that provides application-level networking to make it easy for your services to communicate with each other across multiple types of compute infrastructure. App Mesh standardizes how your services communicate, giving you end-to-end visibility and ensuring high-availability for your applications. 

Now you can use AWS App Mesh controller for Kubernetes to create new services connected to the mesh, define traffic routing and configure security features like encryption. Additionally, it allows you to automatically register your Kubernetes pods in AWS Cloud Map for service discovery. 

**Amazon Corretto for Alpine Linux**

Amazon Corretto, a no-cost, multi-platform, production-ready distribution of OpenJDK, is now in preview for Alpine Linux.  

Our customers have requested the ability to take full advantage of Corretto on a lightweight Linux distribution such as Alpine Linux, enabling faster boot times, embedded devices and more efficient space utilization in container scenarios. Corretto’s performance enhancements and patches, which have proven useful in running our own services at Amazon, are now available on a small form-factor operating system for these scenarios.  

Try Amazon Corretto for Alpine Linux now with docker images or directly download either Corretto 11 or Corretto 8. 

**Amazon RDS for PostgreSQL - Minor version support**

Amazon RDS for PostgreSQL has been updated to support PostgreSQL minor versions 12.3, 11.8, 10.13, 9.6.18, and 9.5.22. This release contains bug fixes and improvements done by the PostgreSQL community.  This release updates the pg logical and pg hint plan extensions. Please see the list of supported extensions in the Amazon RDS User Guide for specific versions.

**AWS Amplify Console and monorepos**

With this release, Amplify Console makes it easy to deploy projects managed in monorepos. A monorepo is a single repository containing source code for multiple web or mobile apps that share common assets. Amplify Console now automatically detects build settings for monorepos by allowing developers to pick a root directory for their app when connecting their repository. Once the app is built and deployed, new builds are triggered only if commits contain changes within the app root directory. 

**FreeRTOS OTA update**

FreeRTOS is an MIT licensed open source, real-time operating system for microcontrollers that makes small, low-power edge devices easy to program, deploy, secure, connect, and manage. You can use AWS IoT Device Management with FreeRTOS devices for an integrated OTA update solution. You can download source code from FreeRTOS.org, GitHub, or the FreeRTOS console.  

FreeRTOS offers support for new over-the-air update (OTA) job configurations. Using the job rollout configuration, you can now add all of your IoT devices to the same OTA update job, and update these devices in phases. Using job abort and job execution timeout configurations, you have better control over your OTA update process. Get started by logging into the AWS IoT console, and learn more about the OTA feature here.


### In other news

**Piranha**

Whilst not related to AWS, this open source project from Uber, [Piranha](https://www.infoq.com/news/2020/06/uber-piranha/), looks very interesting. Released this week, Piranha is a tool that helps automate the process of finding and cleaning stale code across a number of different languages (Java, Swift and Objective C).

Read the post, its not too long. [Uber Open-Sources Tool to Automatically Clean Up Stale Code
](https://www.infoq.com/news/2020/06/uber-piranha/)

**Kick starting the open source culture in your company**

Really great post from Niko Heikkila on [how to kick start the open source culture in your comapny](https://dev.to/nikoheikkila/kickstarting-the-open-source-culture-in-your-company-27jk). This is ten minutes well worth your time, and he covers a lot of important areas that often get overlooked. Niko talks about how to go about cultural transformation from a closed-source organization to open-source advocacy sharing some of his personal experiences driving the change at his current employer.

Nice post Niko!

---

### Share your open source projects 

Do you have some content you want to share with a broader audience? We are always looking for guest content for the AWS Open blog. Please get in touch (via comments below) and I would love to speak with you about what you are doing in open source. We are always looking for interesting new content.

The best submissions will get some AWS Credit codes as a thank you.


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)