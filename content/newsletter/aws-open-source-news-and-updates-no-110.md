---

title: 'AWS open source news and updates #110'
date: '2022-04-29'
tags : [ oss-newsletter, aws open source, AWS CloudFormation Guard, KubeFlow, Semgrep, Steampipe, Terraform, Apache Spark, Kubernetes, Karpenter, PostgreSQL, Linux, Istio, Apache Airflow, Hugging Face, Amazon EMR, ROS]

---

## April 29th, 2022 - Instalment #110

Newsletter #110. 

Welcome to edition #110 of the AWS open source newsletter. It has been a busy week, with the AWS Summit London happening this week (where I was lucky enough to do a session on Apache Airflow) meaning I am publishing this a little later than I had planned. We have more great new projects this week, including a project that helps make it easier to deploy your static and dynamic applications, a tool that provides help in managing the long term health of your AWS Data Lake, a cool project to help you replicate data from a Kinesis Data Stream across regions, a nice CloudWatch dashboard widget that summarises your CloudFormation stacks, and many more - so check them out.

This week also features content covering a broad range of open source topics, including AWS CloudFormation Guard, KubeFlow, Semgrep, Steampipe, Terraform, Apache Spark, Kubernetes, Karpenter, PostgreSQL, Linux, Istio, Apache Airflow, Hugging Face, ROS and many more. There a strong theme of security compliance in some of the topics, so if this is something you are looking at how open source can help, you will find these helpful.

Video content this week includes a detailed look at AWS EKS Blueprints for Terraform, as well as an updated on the latest AWS CDK release and a zero to hero workshop if you want to get started (and its in Python, yay!). Finally, don't forget to check out the events. KubeCon is just around the corner, but we are also in the AWS Summit season, and we will have plenty of great open source content so hope to see you.

**Do you have an interesting open source project you want to share?**

As always, if you are working on anything interesting you would like me to include in this weekly round up, please drop me a line at ricsue@amazon.com.


### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Mahalingam Sivaprakasam, Abhinav Krishna Vadlapatla, Matthew Bonig, Ed Miller, Melody Yang, Kinnar Kumar Sen, Dakota Riley, David Boeke, Bob Tordella, Jon Udell, Nathan Wallace, Kanwaljit Khurmi, Meghna Baijal, Suraj Kota, Joaquin Manuel Rinaudo, Laimonas Sutkus and Hassan Tahhan.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest open source projects

#### Community

**content-delivery-demo**

[content-delivery-demo](https://aws-oss.beachgeek.co.uk/1mw) this project from Hassan Tahhan demonstrates how to accelerate distribution of your static and dynamic content in a secure, scalable, and repeatable way using Amazon CloudFront, Amazon S3, Amazon EC2, Application Load Balancer (ALB), Amazon VPC, and AWS CloudFormation. Other AWS services used are Amazon CloudWatch, AWS Lambda, AWS IAM, and AWS SDK for Python (Boto3).

![architecture of solution](https://github.com/hassantahhan/content-delivery-demo/blob/main/architecture.jpg?raw=true)

#### Tools

**aws-dataset-ingestion-metrics-collection-framework**

[aws-dataset-ingestion-metrics-collection-framework](https://aws-oss.beachgeek.co.uk/1mv) this open source framework helps you to enforce long term health of your AWS Data Lake by providing visibility into operational, data quality and business metrics.

**aws-stf**

[aws-stf](https://aws-oss.beachgeek.co.uk/1mt) The Smart Territory Framework - STF - is a set of tools and standardized modules that our partners and customers can assemble together to build and operate sustainable and highly effective solutions, in line with global industry standards and based on the open-source offering of the FIWARE ecosystem. Check out the detailed README for more info, including some helpful videos that go into more detail about FIWARE and how this project aligns.

![architecture of stf](https://github.com/aws-samples/aws-stf/blob/main/docs/images/referencearch.png?raw=true)

#### Demos, Samples and Workshops

**kinesis-data-streams-replication-using-kinesis-data-analytics-studio**

[kinesis-data-streams-replication-using-kinesis-data-analytics-studio](https://aws-oss.beachgeek.co.uk/1ms) It can be desirable to replicate data from a Kinesis Data Stream in Region A to Region B for many reasons including Disaster Recovery Resiliency, migration to another region, or simply making data available in both regions for separation of concerns. In this repository, we showcase how to replicate data between regions using Kinesis Data Analytics Studio, a managed Apache Flink SQL interactive environment using Apache Zeppelin.

![architecture of cross region kinesis data](https://github.com/aws-samples/kinesis-data-streams-replication-using-kinesis-data-analytics-studio/blob/main/img/cross-region-kda-studio.png?raw=true)

**cfn-stack-summary-widget**

[cfn-stack-summary-widget](https://aws-oss.beachgeek.co.uk/1mp) This repository demonstrates how to create a CloudWatch dashboard widget that provides an HTML summary of one or more CloudFormation stacks. The summary lists important resources along helpful links to the AWS console.

![example dashboard ysing project](https://github.com/aws-samples/cfn-stack-summary-widget/blob/main/DashboardScreenshot.png?raw=true)

**aws-iot-thingworx**

[aws-iot-thingworx](https://aws-oss.beachgeek.co.uk/1mq) This open source solution is designed to allow Things connected to AWS IotCore publishing MQTT messages to connect to an instance of Thingworx server.

![architecture of thingworx solution](https://github.com/aws-samples/aws-iot-thingworx/blob/main/aws_cloud-connector-diagram-final.jpg?raw=true)

**end-to-end-workshop-for-computer-vision**

[end-to-end-workshop-for-computer-vision](https://aws-oss.beachgeek.co.uk/1mr) this is an end-to-end CV MLOps workshop aimed to help Machine Learning (ML) and Data Science (DS) teams build relevant AWS and SageMaker competencies for an enterprise scale solution. The content is derived from a real world CV use case where an image classification model is developed and trained on SageMaker and then deployed to an edge computing devices.

![architecture of workshop solution](https://github.com/aws-samples/end-to-end-workshop-for-computer-vision/blob/main/statics/cv-workshop-overview.png?raw=true)

### AWS and Community blog posts

**Steampipe**

Steampipe is an open source tool under the AGPLv3 license for querying cloud APIs in a universal way and reasoning about the data in SQL. David Boeke, Bob Tordella, Jon Udell, and Nathan Wallace have come together to pen the post, [Compliance auditing with Steampipe and SQL](https://aws-oss.beachgeek.co.uk/1mf). This is a follow up to a previous post that explored how to use Steampipe to query your AWS environments, and in this post they share how Steampipe’s Compliance “mod” enables you to query your AWS infrastructure to check against a number of compliance with regulatory frameworks. This is a really cool project, so you should check this out. [hands on]

**Semgrep**

Semgrep (short for Semantic Grep) is a fast, lightweight, and open-source static analysis tool for finding bugs and automating code reviews. In the blog post, Using SemGrep to find security issues and misconfigurations in AWS Cloud Development Kit projects, Dakota Riley, Principal Security Engineer at Aquia, explores how you can apply static code analysis with Semgrep to the AWS Cloud Development Kit to find security misconfigurations. This is a great post, and I am going to try out some of these against my own CDK stacks to see how well they faire. [hands on]

**AWS CloudFormation Guard**

AWS CloudFormation Guard is an open-source general-purpose policy-as-code evaluation tool. It provides developers with a simple-to-use, yet powerful and expressive domain-specific language (DSL) to define policies and enables developers to validate JSON or YAML formatted structured data with those policies. In the post, [Extend your pre-commit hooks with AWS CloudFormation Guard](https://aws-oss.beachgeek.co.uk/1ml), Joaquin Manuel Rinaudo shows you how to extend your Git hooks to validate your AWS CloudFormation templates against policy-as-code rules by using AWS CloudFormation Guard. This can help you verify that your code follows organisational best practices for security, compliance, and more by preventing you from commit changes that fail validation rules. [hands on]

**BearCam Project**

AWS Community Builder Ed Miller has put together his first post in the AWS Community Builder channel on Dev.to, looking at a new project that he is going to open source that certainly got my attention. The [BearID project](https://aws-oss.beachgeek.co.uk/1mc) is an initiative to explore how noninvasive technologies can help identify and monitor bears, facilitating their conservation. Ed has laid out some of his thinking for his idea, but is looking for feedback and potentially collaborators. If you love bears, and have some spare cycles, why not get in touch. Read the post, [BearCam Companion](https://aws-oss.beachgeek.co.uk/1md). 

**Apache Spark**

Melody Yang and Kinnar Kumar Sen share how you can run Apache Spark workloads faster and cheaper with Amazon EMR on EKS when compared to Apache Spark on Amazon EKS, without making any application changes, in their post, [Amazon EMR on Amazon EKS provides up to 61% lower costs and up to 68% performance improvement for Spark workloads](https://aws-oss.beachgeek.co.uk/1me). Using the TPC-DS datasets at 3 TB scale to benchmark, this is worth while reading if you are running any Apache Spark workloads on AWS.

![graph of performance improvements](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2022/04/21/BDB-2132-image001-500.png)

**Kubeflow**

Kubeflow is the open-source machine learning (ML) platform dedicated to making deployments of ML workflows on Kubernetes simple, portable and scalable. In the post, [Build and deploy a scalable machine learning system on Kubernetes with Kubeflow on AWS](https://aws-oss.beachgeek.co.uk/1mi), Kanwaljit Khurmi, Meghna Baijal, and Suraj Kota demonstrate [Kubeflow on AWS](https://aws-oss.beachgeek.co.uk/1mj) (an AWS-specific distribution of Kubeflow) and the value it adds over open-source Kubeflow through the integration of highly optimised, cloud-native, enterprise-ready AWS services. [hands on]

![architecture of kubeflow on aws](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2022/04/26/ML-8280-image003.jpg)

**Istio**

[Addressing latency and data transfer costs on EKS using Istio](https://aws-oss.beachgeek.co.uk/1mz) takes a look at data transfer charges in your Amazon EKS clusters. Mahalingam Sivaprakasam and Abhinav Krishna Vadlapatla explore one approach using Itsio that might help reduce costs while operating your workloads on Amazon EKS at production scale. [hands on]

![architecture of itsio and data transfer costs](https://d2908q01vomqb2.cloudfront.net/fe2ef495a1152561572949784c16bf23abb28057/2022/04/20/istio-2.png)

**Other posts worth checking out**

* [Simplifying Kubernetes Observability with Amazon EKS Blueprints](https://aws-oss.beachgeek.co.uk/1mg) walks you through building an EKS Blueprint cluster containing the New Relic EKS Blueprints add-on for Kubernetes observability [hands on]
* [Automatically create customized AppStream 2.0 Linux images](https://aws-oss.beachgeek.co.uk/1mu) shows how you can set up a serverless automation pipeline to create a customised AppStream 2.0 Amazon Linux 2 (AL2) based images

![architecture of appstream linux image](https://d2908q01vomqb2.cloudfront.net/827bfc458708f0b442009c9c9836f7e4b65557fb/2022/04/25/as2-automation-lnx-diagram.png)

* [Disaster recovery: 3 failover scenarios for your Amazon Aurora global database with Terraform (Part 2)](https://aws-oss.beachgeek.co.uk/1mh) walks you through three failover scenarios available for the Aurora global database using the Terraform Amazon Aurora module [hands on]
* [PostgreSQL psql client tool commands equivalent to Oracle SQL*Plus client tool](https://aws-oss.beachgeek.co.uk/1mk) is a handy cheat sheet to help you adjust from SQL\*Plus to psql
* [Build a custom Java runtime for AWS Lambda](https://aws-oss.beachgeek.co.uk/1mn) will show you how you can create your own optimised Java runtime for AWS Lambda, allowing you to tailor your Java runtime to your application needs
* [Build and Simulate Robotics Applications in AWS Cloud9](https://aws-oss.beachgeek.co.uk/1mo) covers how to use AWS Cloud9 for Robot Operating System (ROS) based robotics development and testing (including tools like Rviz, Gazebo, etc)
* [Identify paraphrased text with Hugging Face on Amazon SageMaker](https://aws-oss.beachgeek.co.uk/1my) is a hands on guide on how to build a paraphrase identification model using Hugging Face transformers

**Case Studies**

* [How SailPoint solved scaling issues by migrating legacy big data applications to Amazon EMR on Amazon EKS](https://aws-oss.beachgeek.co.uk/1mm) looks at how SailPoint updated its platform for big data operations, and solved scaling issues by migrating legacy big data applications to Amazon EMR on Amazon EKS
* [How Moovit turns data into insights to help passengers avoid delays using Apache Airflow and Amazon SageMaker](https://aws-oss.beachgeek.co.uk/1mx) explores how Moovit built an automated pipeline to train and deploy BERT models which classify public transportation service alerts in multiple metropolitan areas using Apache Airflow to orchestrate the different steps

![moovit apache airflow architecture](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2022/04/19/ai_lake_architecture-800.png)

### Quick updates

**Amazon Linux 2022**

Amazon Elastic Container Service (Amazon ECS) today announced the public preview of the Amazon ECS-optimized Amazon Linux 2022 Amazon Machine Image (AMI). Amazon Linux 2022 (AL2022) is the next generation of Amazon Linux from Amazon Web Services (AWS) that is designed to provide a secure, stable, and high-performance execution environment to develop and run your cloud applications. Starting with AL2022, a new Amazon Linux major version will be available every two years and each major version will be supported for five years. Amazon ECS will publish Amazon ECS-optimized AMIs to support the same 2-year release and 5-year support cycle for every new major Amazon Linux version. The two-year major release cycle helps you keep your software up-to-date while the five year support commitment for each major release gives you the stability you need to manage long project lifecycles.

AL2022 is based on the Fedora project and provides frequent and flexible quarterly updates. AL2022 also locks to a specific version of the Amazon Linux package repository, which gives you control over how and when you absorb updates. In addition, AL2022 also comes with Security-Enhanced Linux (SELinux) policies for additional isolation. Furthermore, the Amazon ECS-optimized AL2022 AMI now uses cgroupsV2 as the default kernel setting for managing Task and container resources, which enables improved memory management.

**Karpenter**

Amazon Elastic Kubernetes Service (EKS) is announcing v0.9.0 of the Karpenter open-source cluster autoscaling project. Karpenter is a flexible, high-performance Kubernetes cluster autoscaler that helps improve application availability and resource utilisation. Karpenter v0.9.0 adds supports for Kubernetes podAffinity and podAntiAffinity scheduling constraints, which increases its compatibility with popular third-party Helm charts and expands support for high-availability use cases.

Karpenter v0.9.0 is the latest release since the project’s launch at re:Invent 2021. On January 7, 2022, Karpenter v0.5.4 added support for volume topology aware scheduling, enabling its use with stateful Kubernetes workloads. On March 14, 2022, Karpenter v0.7.0 made it easier to customise the compute provisioned by removing the need for custom EC2 launch templates, including when using Bottlerocket as the OS. With the v0.9.0 release, Karpenter fully supports workloads that use Kubernetes podAntiAffinity to achieve better availability by spreading pods across multiple hosts or availability zones.

**AWS CDK**

Matthew Bonig has put together a short video to share news about release 2.21 of AWS CDK, covering highlights and showing examples of some of the new features in the AWS CDK.

{{< youtube GxXKJDYnpDY >}}

### Videos of the week

**AWS EKS Blueprints for Terraform**

The Containers from the Couch crew take a look at the new Amazon EKS Blueprints for Terraform modules and how they can help you manage your Kubernetes clusters.

{{< youtube TXa-y-Uwh2w >}}

**AWS CDK Workshop - From Zero to Hero**

This online workshop is presented by Laimonas Sutkus, the CTO of Biomapas and he shows you how to get started with AWS CDK. It is a long session, but covers a lot of topics and uses Python which makes me happy as I typically see TypeScript workshops, so if you are a Python developer, this becomes a must watch.

{{< youtube ubhnzRI_FMs >}}

### Events for your diary

**AWS Berlin Summit**
**May 11th/12th**

Aside from the AWS open source sessions (including me again, talking about Apache Airflow) we will have our very own Spot and myself manning the open source booth. Really looking forward to this and would love to see you come down and share your open source projects on our booth.

[AWS Berlin Summit registration page](https://aws.amazon.com/events/summits/berlin/)

**KubeCon**
**May 16th-20th, Valencia Spain**

The Cloud Native Computing Foundation’s flagship conference gathers adopters and technologists from leading open source and cloud native communities in Valencia, Spain from 16 – 20 May 2022. I will be there with many of the open source team and other AWS colleagues, so if you are going, make sure you swing by the AWS Booth.

Find out more about the [event here](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/).

**GitOpsCon Europe**
**May 17th, Valencia Spain**

GitOpsCon Europe is designed to foster collaboration, discussion, and knowledge sharing on GitOps. This event is aimed at audiences that are new to GitOps as well as those currently using GitOps within their organisation. Get connected with others that are passionate about GitOps. Learn from practitioners about pitfalls to avoid, hurdles to jump, and how to adopt GitOps in your cloud native environment.

The event is vendor-neutral and is being organised by the CNCF GitOps Working Group. Topics include getting started with GitOps, scaling and managing GitOps, lessons learned from production deployments, technical sessions, and thought leadership.

Read more about this from the official page [here](https://events.linuxfoundation.org/gitopscon-europe/).

**CDK Day**
**May 26th - Virtual**

This is a community organised event about AWS CDK, cdktf, projen and cdk8s. This will be third year they run this event, and if the previous two are anything to go by, this will be essential viewing - live streamed via You Tube. Check out and register for the event over at their home page at [https://www.cdkday.com/](https://www.cdkday.com/)

**BOSC 2022**
**July 13-14, Madison, Wisconsin, USA**

The Bioinformatics Open Source Conference (BOSC) has been held annually since 2000, and this year AWS is proud to be a platinum sponsor for this event. BOSC covers all aspects of open source bioinformatics software and open science, including (but not limited to) these topics, Open Science and Reproducible Research, Open Biomedical Data, Citizen/Participatory Science, Standards and Interoperability, Data Science Workflows, Open Approaches to Translational Bioinformatics, Developer Tools and Libraries, Inclusion, and Outreach and Training. This is a hybrid event (in person/virtual) and you find out more by checking out the event page, [BOSC 2022](https://aws-oss.beachgeek.co.uk/1li)

**OpenSearch**
**Every Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting - Feb2022](https://aws-oss.beachgeek.co.uk/1az)

**OpenSearchCon 2022**
**Sept 21st, 2022 Seattle**

Come to the first annual OpenSearchCon!

This day-long conference will be packed with presenters who build and innovate with OpenSearch. It doesn’t matter if you’re just getting started on your OpenSearch journey, running giant clusters, or contributing tons of code; the event is for everyone. Join us to celebrate the progress and look into the future of the project. Admission is free, and registration will be open in the next few weeks. All you will need to do is sign up, and get to Seattle!

Check out the full details, including signing up and location, at the [meetup page here](https://aws-oss.beachgeek.co.uk/1n1).


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)