---
title: 'AWS open source news and updates No. 33'
date: '2020-08-31'
tags : [ oss-newsletter ]
---
## August 31st - Instalment #33

Week No.33, and as we come to the end of the summer season with people returning back from holiday, it is good to see that there has been no slow down in open source activities. This week we have plenty of blog posts, projects for you to check out and customer stories. 

We also have a growing list of events to add to your diary, so make sure you check these out too. Again, if you have any open source events you want me to share on this newsletter, then please let me know. 

### Something to read

First up is a blog post from Daniele Scasciafratte announcing [An Open-Source Book About the Open Source World](https://hackernoon.com/an-open-source-book-about-the-open-source-world-2h6r3unz), which I am currently working through (the pdf version) and is a kind of hybrid book in such that it reads like an autobiography about Daniele's open source journey. Along the way he shares what he has learnt, and it kind of works as it makes it easier to read than many of the books on this subject. You can start reading via this link [here](https://github.com/mte90/contribute-to-opensource-the-right-way/releases). Nice work Daniele!

### Your feedback matters!

I have put together a short feedback survey, which I would ask you to take - it will take no more than 2 minutes. You can access [here](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn). Many thanks!

[Take the survey](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn)

### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to Arpit Mohan, Aram Alipoor, Philipp Garbe, Yoni Augarten, Xiaoyan Zhang, Praveen Kumar Jeyarajan, Viyoma Sachdeva, Iftikhar Khan and Kiran Sahoo, Michael Neil, Polar Squad, Stelligent, Sudhir Jonathan, Pratip Bagchi, Henner Dierks, Angus McAllister, Shubhra Deshpande and Michael Hausenblas

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Events for your diary

Check out these events happening over the coming weeks. If you have an event you want me to share with readers, please drop me a message.


**End-to-End Computational Fluid Dynamics**
**2nd September, 4PM BST**

[AWS Automotive Webinar](https://pages.awscloud.com/GLOBAL-event-OE-e2e-cfd-webinar-2020-reg-event.html) - The focus of this webinar will be how to run a complete end-to-end CFD workflow for a realistic road-car model. Starting with CAD and pre-processing we will firstly show how these steps can be done remotely on AWS with minimal data transfer. Secondly we will solve a high-fidelity case using the open-source code OpenFOAM to demonstrate how AWS can improve turn-around time for large cases

**DockTalk: From Docker Straight to AWS**
**3rd September, 6PM BST**

If you want to hear/learn what we are cooking up with Docker and the integration with #ECS and #Fargate on AWS then this is going to be a great talk!

[Register for this event here.](https://goto.docker.com/From-Docker-Straight-to-AWS.html)

**State of the Source**
**9th September, 3PM BST**

The State of the Source Summit invites open source communities of practice from around the world to organize and contribute to a global conversation on the current state of open source software: non-technical issues that foster development and community, the licenses that enable collaboration, the practices that promote contribution, and the issues confronting cooperation.

[Register via this link](https://eventyay.com/e/8fa7fd14).

**Machine Learning workshop**
**September 10th, 2PM BST**

[Unifying Data Pipelines and Machine Learning with Apache Spark™ and Amazon SageMaker](https://awsmldevdayeast.splashthat.com/?utm_source=bambu&utm_medium=social&utm_campaign=advocacy&blaid=748357) a databricks and Immuta workshop to learn how Unified Data Analytics can bring Data Science, Business Analytics and engineering together to accelerate your Data and ML efforts.

**MLops Best Practices with Amazon SageMaker and KubeFlow**
**September 15th, 9am Singapore TZ**

This webinar will present best practice deployment of Machine Learning workloads using Amazon Sagemaker and Kubeflow (the open source toolkit for Kubernetes). Details and registration can be found [here](https://pages.maxkelsen.com/mlops).

**CDK Day**
**September 30th, 3PM BST**

Now this is an event you should put in your diaries, an event that has been put together by the AWS CDK community (and a lot of familiar faces from posts I have shared in this weekly newsletter), has a fantastic line up of speakers and promises to be an unmissable event if you are thinking of or looking at AWS CDK. Find more details, including speaker line up and registration, at the link -> https://www.cdkday.com/

### Latest from open source projects

**aws-cost-saver**

[aws-cost-saver](https://github.com/aramalipoor/aws-cost-saver) a project from Aram Alipoor that provides a CLI tool to help save costs in development environments when you're asleep and don't need them. Aram provides some nice documentation, including some best practices or 'Tricks' to make sure you can reduce the cost of running your development environments. There is also a great thread on HN where Aram answers many questions that people had on this project. [Check out the thread here](https://news.ycombinator.com/item?id=24245166).

**cdk-ecr-sync**

[cdk-ecr-sync](https://github.com/pgarbe/cdk-ecr-sync) a project from Philipp Garbe, that provides a CDK Construct to synchronizes Docker images from Docker Hub to ECR. The project provides some examples to get you going, and this [Tweet from Philipp Garbe](https://twitter.com/pgarbe/status/1298280715575087108) provides some additional background to this.

**Mutato**

[Mutato](https://github.com/stelligent/mutato) this open source project from Stelligent is an open-source framework for building containerized micro-services on the AWS ecosystem, and making it easier to do deployments. You can find documentation on how to get started with examples [here](https://stelligent.github.io/mutato/). Look out for the rather unusual project mascot/logo (can't decide which it is). If you like what you read, then why not check out Michael Neil on this podcast, [DevOps on AWS Radio: Mutato and Open Source at Stelligent (Episode 27)](https://stelligent.com/2020/05/12/devops-on-aws-radio-mutato-and-open-source-at-stelligent-episode-27/)

**REDIMO**

[Redimo](https://github.com/dbProjectRED/redimo.go) this open source project from Sudhir Jonathan that provides a library that allows you to use the Redis API on DynamoDB and bridges the two and translates the Redis API operations into space / time / cost-efficient DynamoDB API calls. Redimo is especially well suited to serverless environments, since there is no pool of connections to handle and DynamoDB is purpose-built for near-zero management use. Read the detailed README.md file to understand the nuances of this project.


**AppSmith**

[Appsmith](https://github.com/appsmithorg/appsmith) 

Check out Appsmith, an open source (Apache 2.0) low-code application that lets you start building dashboards, workflows, or internal tools. Check out [the project repository](https://github.com/appsmithorg/appsmith) ([great docs!](https://docs.appsmith.com/)) and this walk through from CTO Arpit Mohan, [One open source project for admin panels, CRUD apps, & internal tools](https://dev.to/mohanarpit/show-dev-open-source-tool-to-build-admin-panels-crud-apps-internal-tools-13fh)

![demo](https://res.cloudinary.com/practicaldev/image/fetch/s--1CisxFLS--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_66%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/vl9dz1ketugmtx1qte2g.gif)

**eks-auth-sync**

[eks-auth-sync](https://gitlab.com/polarsquad/eks-auth-sync) is an open source project from Polar Squad to help manage EKS cluster authentication configuration. This project will help you automate the ConfigMap updates, you can use eks-auth-sync to automatically pull changes from various sources and update the ConfigMap. Check out their blog post, [Announcing a new open source tool: eks-auth-sync](https://polarsquad.com/blog/announcing-a-new-open-source-tool-eks-auth-sync) for more details on what this is and how you can use it.

![arch](https://gitlab.com/polarsquad/eks-auth-sync/-/raw/master/diagram.png)

**Amazon S3 Encryption Client for .NET**

[Amazon S3 Encryption Client for .NET](https://github.com/aws/amazon-s3-encryption-client-dotnet) The Amazon S3 Encryption Client for .NET provides an easy-to-use Amazon S3 encryption client that allows you to secure your sensitive data before you send it to Amazon S3. The AmazonS3EncryptionClientV2 client automatically encrypts data on the client when uploading to Amazon S3, and automatically decrypts it when data is retrieved. You can use the client just like the regular S3 client, working with things like multipart uploads and the Transfer Utility with no additional code changes required besides swapping out the client used. Code samples and API documentation are available at the following https://aws.github.io/amazon-s3-encryption-client-dotnet/index.html

**evb-cli**

[evb-cli](https://github.com/mhlabs/evb-cli) - an open source project from Lars that is a pattern generator for CloudWatch Events / EventBridge. You might recall a project a few weeks ago called evb-local. This new open source project from Lars which supersedes and incorporates the functionality from that project. [Check out this thread from Lars](https://twitter.com/lajacobsson/status/1299821134796460033?s=11) which covers some of the key things you can do with evb-cli.

**Service Workbench on AWS**

[Service Workbench on AWS](https://github.com/awslabs/service-workbench-on-aws) is an open source project aimed at providing researchers with one-click access to collaborative workspace environments operating across teams, universities, and datasets while enabling university IT stakeholders to manage, monitor, and control spending, apply security best practices, and comply with corporate governance.

**Thingpress**

[Thingpress](https://github.com/awslabs/thingpress) this open source project from AWS provides a way for customers to simplify and automate the provisioning of thousands/millions of certificates for IoT devices. If you are looking for a solution to simplify how you vend certificates to your devices, look no further.

 

### Fresh blog posts for your reading pleasure

**Apache Hive vs AWS Glue**

[Metadata Management: Hive Metastore vs AWS Glue](https://lakefs.io/2020/08/24/metadata-management-hive-metastore-vs-aws-glue/) this post from Yoni Augarten compares two popular metadata catalogs: Hive Metastore and Amazon Glue. Metadata management tools like these provide a metadata layer, containing the information that identifies and describes the data and are important when building data lakes so you have a mechanisms where you can query to find out information about your data. You can find out more information about [Apache Hive here](https://cwiki.apache.org/confluence/display/Hive/GettingStarted).

**Gov UK on AWS**

[Architectural decisions](https://github.com/alphagov/govuk-aws/tree/master/docs/architecture/decisions) found this link via Corey's weekly newsletter, and it provides a detailed set of design documents that are made publicly available on how they setup and deploy services on AWS. There is an old blog post dating back to 2011 that shares some of the rational and thinking behind this, which you can read at [Documenting Architecture Decisions](https://cognitect.com/blog/2011/11/15/documenting-architecture-decisions)

**Flutter and Amplify**

[First Look at AWS Amplify Flutter (Developer Preview)](https://dev.to/swyx/first-look-at-aws-amplify-flutter-developer-preview-2jbh) great post (and YT Video) from AWS Hero shawn swyx wang, where he walks you through creating a sample photo sharing application using Flutter.

{% youtube 0NgR-Qa5GPE %}

**Robotics resources**

Some more resources that you can use when creating your simulation worlds to test your robots and robotic applications. [Welcome to PUCRS Campus on Gazebo](https://pucrs-campus-on-gazebo.readthedocs.io/en/latest/index.html) provides some excellent resources to create a Gazebo simulation of the [Pontifical Catholic University](https://en.wikipedia.org/wiki/Pontifical_Catholic_University_of_Rio_Grande_do_Sul) campus. Then we have some suburban/house objects you can put into your worlds, which you can find [here](https://app.ignitionrobotics.org/athackst/fuel/collections/suburb_sim) and [here](https://github.com/osrf/citysim). These can be useful if you are planning autonomous vehicles or robots that need to navigate these kinds of environments, as you can see in these [videos](http://gazebosim.org/blog/car_sim).

Finally, a short video sent to me via Camilo Buscaron, that is a great ROS2 & Navigation2 demo in Gazebo by Shreyas Gokhale and JdeRobot that uses the AWS Robotics open source warehouse world. Check it out.

{% youtube wmAeoyiUyh4 %}

### AWS open source posts

**.NET Core**

[Modernizing and containerizing a legacy MVC .NET application with Entity Framework to .NET Core with Entity Framework Core: Part 2](https://aws.amazon.com/blogs/devops/modernizing-and-containerizing-a-legacy-mvc-net-application-with-entity-framework-to-net-core-with-entity-framework-core-part-2/) this post from Pratip Bagchi is the follow on post from one I shared a few weeks ago, showing you how you can modernise your ASP.NET MVC legacy applications and port them to .NET Core. This post continues the theme but this time deploys on AWS Fargate.

![net migration](https://d2908q01vomqb2.cloudfront.net/7719a1c782a1ba91c031a682a0a2f8658209adbf/2020/08/26/Architecture-Diagram.png)

**Fast Healthcare interoperability Resources (FHIR)**

[Using open source FHIR APIs with FHIR Works on AWS](https://aws.amazon.com/blogs/opensource/using-open-source-fhir-apis-with-fhir-works-on-aws/)  Henner Dierks and Angus McAllister walk you through this new open source project from AWS that helps customers build FHIR ready applications, and this software toolkit can be used to add capabilities of a FHIR interface to existing healthcare software. FHIR Works aims to help software engineers at independent software vendors, system integrators or healthcare customers to enhance their own products to provide access to data in those systems to mobile devices and web portals through integrating the FHIR standard APIs. 

![arch](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2020/07/27/dierks-FHIR-f1.png)

**AWS Copilot**

[Automatically deploying your container application with AWS Copilot](https://aws.amazon.com/blogs/containers/automatically-deploying-your-container-application-with-aws-copilot/) this nice walkthrough from Nathan Peck shows you how you can start automating your application releases using AWS Copilot, and builds from his previous post which I shared a few weeks ago that showed you how to get started. 


**OCI Support in Amazon ECR**

[OCI Artifact Support In Amazon ECR](https://aws.amazon.com/blogs/containers/oci-artifact-support-in-amazon-ecr/) this post from Shubhra Deshpande and Michael Hausenblas dives into this recent launch announcement, where AWS now supports pushing and pulling Open Container Initiative (OCI) artefacts in Amazon ECR, addressing customer needs that wanted us to support artefacts beyond container images. Read this post to understand more about what this means and about the OCI artefacts and how these are now supported.


**KwizzBit**

[Making virtual quiz games more accessible with KwizzBit and AWS](https://aws.amazon.com/blogs/gametech/making-virtual-quiz-games-more-accessible-with-kwizzbit-and-aws/) I have posted earlier in the year about Kwizzbit's open source quiz platform that leverages AWS Amplify. This blog post talks to the founds and found out how their journey has been so far, some interesting data points and what the future holds.

**Subversion**

[Migrating Subversion repositories AWS CodeCommit](https://aws.amazon.com/blogs/devops/migrating-subversion-repositories-aws-codecommit/) a post from Iftikhar Khan and Kiran Sahoo that shows you how you can migrate your Subversion source control repositories to AWS CodeCommit. It has been a while since I have used svn, but when I speak with enterprise customers, there are still plenty of legacy code repositories that have been kept as is, so this post shows you how you can migrate those repositories.

**OpenSSL**

[How to import PFX-formatted certificates into AWS Certificate Manager using OpenSSL](https://aws.amazon.com/blogs/security/how-to-import-pfx-formatted-certificates-into-aws-certificate-manager-using-openssl/) by Praveen Kumar Jeyarajan and Viyoma Sachdeva have collaborated to show you how to import PFX-formatted certificates into AWS Certificate Manager (ACM) using OpenSSL tools, specifically PFX-encoded SSL/TLS certificate into ACM. A handy reference guide for when you might need to do this. 

**Render Farm Deployment Kit**

[Announcing Render Farm Deployment Kit on AWS](https://www.awsthinkbox.com/blog/announcing-render-farm-deployment-kit) is a blog post that introduces a new open source project, Render Farm Deployment Kit (RFDK) for those working in 3D animation, motion graphics, and VFX.  The Render Farm Deployment Kit, lets you use languages like Python and NodeJS to automate the deployment of render farm resources in the cloud. 

RFDK provides constructs for the AWS CDK that deploy and configure components of your cloud-based render farm, making it faster to manually deploy for your farm on AWS by reducing ten thousand of lines of AWS CloudFormation code to two hundred lines in Python. Read the post for all the details including links to the documentation, and you can find the [project repository here](https://github.com/aws/aws-rfdk).

### Case Study

**TalkingData and Deep Java Library - DJL**

[How TalkingData uses AWS open source Deep Java Library with Apache Spark for machine learning inference at scale](https://aws.amazon.com/blogs/opensource/how-talkingdata-uses-aws-open-source-deep-java-library-with-apache-spark-for-machine-learning-inference-at-scale/) this post via Xiaoyan Zhang, a Data Scientist at TalkingData, looks at how you can use this open source project to simplify and reduce cost when approaching machine learning. TalkingData is a data intelligence service provider that offers data products and services to provide businesses insights on consumer behaviour, preferences, and trends. Deep Java Library (DJL) is a Deep Learning Framework written in Java, supporting both training and inference. DJL is built on top of modern Deep Learning engines (TenserFlow, PyTorch, MXNet, etc.). This post walks you through a machine learning model that TalkingData used to showcase their solution of using DJL to run inference for PyTorch models on Apache Spark, and shows how this approach provided an end-to-end solution to run everything on Apache Spark without involving additional services, and reducing running time by 66% and reduced maintenance costs.

![diagram](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2020/08/25/qingla_f4.png)

### Quick updates

**Amazon Corretto 8 & 11 support extended**

Amazon is extending long-term support (LTS) for Amazon Corretto 8 from June 2023 to May 2026 and for Amazon Corretto 11 from August 2024 to September 2027. Long-term support (LTS) for Corretto includes security updates and specific performance enhancements released at least quarterly. Amazon Corretto is a no-cost, multi-platform, production-ready distribution of OpenJDK. 


**Seamlessly join an Amazon EC2 for Linux instance to AWS Directory Service**

You can now join your Amazon EC2 for Linux instances to a domain configured with AWS Directory Service seamlessly. The new capability automates the previously manual approach for integrating Linux-based EC2 instances to your  AWS Directory Service for Microsoft Active Directory (AWS Managed Microsoft AD), or to an existing on-premises Active Directory (AD) using AD Connector. This makes it easier for you to launch and manage your Amazon EC2 for Linux instances, reducing deployment time and administration effort.


### Share your open source projects 

Do you have some content you want to share with a broader audience? We are always looking for guest content for the AWS Open blog. Please get in touch (via comments below) and I would love to speak with you about what you are doing in open source. We are always looking for interesting new content.

The best submissions will get some AWS Credit codes as a thank you.


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)	