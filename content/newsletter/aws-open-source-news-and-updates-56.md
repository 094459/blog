---
title: 'AWS open source news and updates #56'
date: '2021-02-15'
tags : [ oss-newsletter ]
---
## February 15th, 2021 - Instalment #56

Newsletter #56. 

This week we have the latest update on the Elasticsearch/Kibana fork, events for your diary, the usual round up of blog posts and new open source projects as well as white papers, a nice selection of videos, workshops and case studies. Make sure you read the Rust Foundation blog post this week and check out Didier's post on running a serverless mainframe...well kind of! As always, I am always eager to hear from you about your projects or blogs/solutions you have been working on so please get in touch if you would like me to share your projects here.

**Elasticsearch fork updates**

Kyle Davis has been sharing progress on the Elasticsearch and Kibana forks. In [Feb 10th update](https://aws-oss.beachgeek.co.uk/6f) and [Feb 12th update](https://aws-oss.beachgeek.co.uk/6g), shares some great data points with the community including news that the the group is about 93% done with the work. Exciting times and getting closer to a fully open source Elasticsearch and Kibana fork.

**Contributing to open source**

Not related to AWS, this post from Piotr Gaczkowski, [The Definitive Guide to Contributing to Open Source](https://aws-oss.beachgeek.co.uk/6j) provides some solid guidance and well worth reading if you are both just starting out or a seasoned contributor.


### Events for your diary

**Innovate AI/ML**
**Feb 24th**

Last week I shared that I have been putting together some blog posts to support my session at the [Innovate AI/ML event](https://aws.amazon.com/events/aws-innovate/machine-learning/online/emea/?sc_channel=em&sc_campaign=EMEA_FIELD_WEBINAR_innovate-AIML_20210224_7014z000001MJbu&sc_medium=em_&sc_content=REG_t1_field&sc_geo=emea&sc_country=mult&sc_outcome=reg&sc_publisher=aws&trkCampaign=emea21_innovatemlq1&trk=em_emea21_innovatemlq1_ricardosueiras) happening on Feb, 24th. I have been working on more posts, and this week I managed to complete the fourth and fifth posts which you can find below. Use the [sign up link here](https://aws.amazon.com/events/aws-innovate/machine-learning/online/emea/?sc_channel=em&sc_campaign=EMEA_FIELD_WEBINAR_innovate-AIML_20210224_7014z000001MJbu&sc_medium=em_&sc_content=REG_t1_field&sc_geo=emea&sc_country=mult&sc_outcome=reg&sc_publisher=aws&trkCampaign=emea21_innovatemlq1&trk=em_emea21_innovatemlq1_ricardosueiras) to register for this event.

**Apache Kafka**
**Feb 25th**

[Building ML-driven streaming applications with Apache Kafka](https://aws-oss.beachgeek.co.uk/4y) join Joseph Morais from Confluent and Kanchan Waikar from AWS in this webinar to learn how to build Apache Kafka®-based streaming applications backed by machine learning models. The event is across three time zones so whether you are in Asia, Europe or the Americas, there will be a time you can attend.

**CDK Day**
**April 30th**

Announced this week was the second [CDK Day](https://sessionize.com/cdkday/), which will be on April 30th. Check out [the web page](https://sessionize.com/cdkday/) to find out more about the first CDK Day, which was incredible. This second event promises to be even better. The CFP is open until the 19th of March. Check out this supporting blog post, [CDK Day CFP Is Open!!!!](https://aws-oss.beachgeek.co.uk/4v) from Matt as to what to expect and what they are looking for when it comes to sessions.

**Cloud Native Rust Day**
**May 3rd**

Rust is a language empowering everyone to build secure, reliable, and efficient software. Rust is becoming more widely used in cloud native, powering everything from lightning-fast service meshes and powerful developer tools to internet-scale distributed databases.

Come explore what makes Rust a fantastic choice for new cloud native development, and learn about how the community uses Rust today. Find out [more and register here](https://aws-oss.beachgeek.co.uk/5y).

### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Jan Bauer, Ryan Green, Jimmy Dahlqvist, Didier Durand, Nader Dabit, Marcin Cuber, Eddie Zaneski, Kilo Loco, Neel Sendas, Christopher Spruell, Jeff Strickland, Azfaar Qureshi, Shovnik Bhattacharya, Leah Siddall, Maxime Boulin, Sofian Hamiti, Othmane Hamzaoui, Stefano Sandrini, Shane Miller, Kyle Davis, Eric Johnson, Piotr Gaczkowski, Alessandro Aiezza, Abhinav Dhasmana,  Rashmi Dwaraka, Mike Stefaniak, and Paavan Mistry

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

**lambda-cobol**

[lambda-cobol](https://aws-oss.beachgeek.co.uk/5u) this is a very interesting project from Didier Durand, that you will be interested in if you have any legacy Mainframes or Cobol applications you still need to keep running. Find out how you can modernise those applications using GnuCobol, AWS SAM and Serverless computing. Didier has also put together a comprehensive README.md and this [short blog post on LinkedIn](https://aws-oss.beachgeek.co.uk/5v).

**aws-allowlister**

[aws-allowlister](https://aws-oss.beachgeek.co.uk/63) this is a new project from Salesforce, that will automatically compile an AWS Service Control Policy that ONLY allows AWS services that are compliant with your preferred compliance frameworks. AWS Service Control Policies (SCPs) allow you to control which AWS Service APIs are allowed at the AWS Account level - so local administrators (not even the account's root user) can perform prohibited actions in a child account.

![demo](https://raw.githubusercontent.com/salesforce/aws-allowlister/main/examples/media/aws-allowlister.gif)

**react-p2p-messaging**

[react-p2p-messaging](https://aws-oss.beachgeek.co.uk/64) is a new open source project and walkthrough from Nader Dabit showing you how to build a peer to peer demo application using Gun.js & React. If you are unfamiliar with Gun.js, it is a effecient data sync and storage system that runs in Javascript. Check out the walk through in his post, [How to Build a Decentralized Peer-to-peer Network in JavaScript](https://aws-oss.beachgeek.co.uk/65)

**amazon-ivs-feed-web-demo**

[amazon-ivs-feed-web-demo](https://aws-oss.beachgeek.co.uk/6a) is a demo web application intended as an educational tool for demonstrating how you can build a very simple scrolling feed app, load and auto-play Amazon IVS live streams as users scroll down the page. In this new blog post, [How to: Build an engaging feed app with React and Amazon IVS](https://aws-oss.beachgeek.co.uk/6b) Leah Siddall and Maxime Boulin show you how to use this project and walk you through building that demo.

**AWS SAM Gist**

Not a full blown repo but Eric Johnson shared [this Github Gist](https://aws-oss.beachgeek.co.uk/6h) to show you how you can now use standard Linux package commands to install AWS SAM. This is certainly going to make my life easier and I suspect others too.

### Community open source posts

**kube-bench**

[AWS EKS and kube-bench](https://aws-oss.beachgeek.co.uk/5x) Marcin Cuber shows you the simplest way to run kube-bench tests against EKS worker nodes. I have talked about Kube-bench before, which is an open source project from the lovely folks at Aqua Security.

**Amazon Corretto**

[Are you seriously not using Java 15 yet?](https://aws-oss.beachgeek.co.uk/6m) Alessandro Aiezza takes a frank and detailed look at Java 15, a look at some of the things to watch out for as you think about the migration. Great post.

**Apache Kakfa**

[How to setup Kafka cluster for 15K events per second on AWS using Docker](https://aws-oss.beachgeek.co.uk/6n) Abhinav Dhasmana with a detailed post and supporting code on how to setup and run your own Apache Kafka and Zookeeper setup on AWS. 

![arch](https://miro.medium.com/max/1202/1*dqJRHZSM9ORxS1sVow_7bQ.png)

**Former2**

[A tale of an CloudFormation import](https://aws-oss.beachgeek.co.uk/6r) Jimmy Dahlqvist shares an approach you can take to automate the provisioning of AWS resources that you might have created manually, using the open source tool Former2. I recently had need to use this tool as part of some recent posts on Amazon Managed Workflows for Apache Airflow, and found it super simple to use. This is a post you should read if you are doing any kind of automation.

### AWS open source posts

**Rust**

[Congratulations, Rustaceans, on the creation of the Rust Foundation!](https://aws-oss.beachgeek.co.uk/6e) Shane Miller shares a short post on the announcement last week of the creation of the Rust Foundation, which helps creates a neutral place for the diverse Rust community to innovate together. Read the post to find out more details, including the formal announcement on the Rust Foundation website.

**Prometheus**

[Building a Prometheus Remote Write Exporter for the OpenTelemetry Python SDK](https://aws-oss.beachgeek.co.uk/69) Azfaar Qureshi and Shovnik Bhattacharya talk about their experience building the OpenTelemetry Prometheus Remote Write Exporter for Python. They share their experiences in tackling challenges they faced while building this tool, which is used for sending metrics to Prometheus protocol-based service endpoints.

**Apache Airflow**

[Monitoring and logging with Amazon Managed Workflows for Apache Airflow](https://aws-oss.beachgeek.co.uk/5r) this is the latest instalment of a series of posts I have been putting together on Apache Airflow. In this post I look at logging, monitoring, dashboards and alerting within Amazon Managed Workflows for Apache Airflow. I show you how you can  set these up and configure metrics in CloudWatch as well as how you can use these within other services such as Grafana Cloud.

**AWS Amplify**

A couple of posts this weeks to satisfy AWS Amplify aficionados. First up we have [Super Easy Automated Scraping with AWS Amplify](https://aws-oss.beachgeek.co.uk/66) AWS DA Shawn Wang Yue Xian (swyx) with a new post/tutorial on data scraping with AWS Amplify. In this demo, Shawn will show you how this demo project is going to be scraping Twitter follower counts on a periodic basis and storing it in a database for later analysis.

![arch](https://dev-to-uploads.s3.amazonaws.com/i/bb0tj9h29rrs2iw25g8j.png)

To follow that, we have [Real-time live sports updates with AWS AppSync](https://aws-oss.beachgeek.co.uk/6d) from Stefano Sandrini, who provides a detailed walk through of a sample reference architecture on how to leverage AWS AppSync real-time capabilities to address delivering real-time live updates (in this case, using a specific example from  the Media and Entertainment industry, but you could adapt for your own needs).

![arch](https://d2908q01vomqb2.cloudfront.net/0a57cb53ba59c46fc4b692527a38a87c78d84028/2019/11/06/image-1.png)

**AWS CDK**

[Manage Amazon CloudWatch agent deployment at scale using the AWS Cloud Development Kit to optimize AWS usage](https://aws-oss.beachgeek.co.uk/68) Neel Sendas, Christopher Spruell, and Jeff Strickland talk about how to programmatically deploy the Amazon CloudWatch agent using the AWS Cloud Development Kit (AWS CDK) as you create your Amazon Elastic Compute Cloud (Amazon EC2) instances. These are two open source projects from AWS, and this is a hands on tutorial/walkthrough on how to setup, deploy and then clean up your CloudWatch agents programatically.

**PyTorch**

[Using container images to run PyTorch models in AWS Lambda](https://aws-oss.beachgeek.co.uk/6q) Jan Bauer shows you how to use any PyTorch model with Lambda for scalable inferences in production with up to 10 GB of memory. This allows us to use ML models in Lambda functions up to a few gigabytes, and in this particular walkthrough Jan uses the Huggingface Transformers, open-source library to build a question-answering endpoint.

![arch](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2021/02/03/ML-2181-PyTorch-1-WHITE.png)

**TensorFlow**

[Training and deploying models using TensorFlow 2 with the Object Detection API on Amazon SageMaker](https://aws-oss.beachgeek.co.uk/6c) Sofian Hamiti and Othmane Hamzaoui have put together this post to show you how you can build, train, and deploy an EfficientDet model using the TensorFlow Object Detection API. It’s built on top of TensorFlow 2, which makes it easy to construct, train, and deploy object detection models.

![arch](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2021/01/14/ML-1262-7.jpg)

**ElastiCache**

[Amazon ElastiCache at AWS re:Invent 2020](https://aws-oss.beachgeek.co.uk/67) if you wanted a single place to go to for all the ElastiCache content from re:Invent, then this is the post for you. Covering four different sessions that ran over the three weeks of re:Invent, check this out if you if want the latest news.

**Kubernetes**

[Introducing OIDC identity provider authentication for Amazon EKS](https://aws-oss.beachgeek.co.uk/6o)  Rashmi Dwaraka, Mike Stefaniak, and Paavan Mistry have come together to walk you through how you can now enable authentication for Amazon EKS clusters from an OpenID Connect (OIDC) Identity Provider. This has been a long requested feature as you can see from this [project issue #166](https://aws-oss.beachgeek.co.uk/6p) raised a while back, and this post walks you through setting this up using Amazon Cognito as the OIDC identity provider, but you could use another. 

### WhitePapers

A couple of white papers this week. First up we have this [new white paper on AWS Amplify DataStore](https://aws-oss.beachgeek.co.uk/5z), covering the architecture, use cases and implementation.

Following that we have this paper from the Amazon Alexa team, [Optimal Subarchitecture Extraction For BERT](https://aws-oss.beachgeek.co.uk/60) and this blog post [A version of the BERT language model that’s 20 times as fast](https://aws-oss.beachgeek.co.uk/61) that takes a look at a new open source project, Bort, a highly optimised language model (LM) extracted from the BERT architecture.

![arch](https://assets.amazon.science/dims4/default/9898d05/2147483647/strip/true/crop/951x534+0+0/resize/1200x674!/quality/90/?url=http%3A%2F%2Famazon-topics-brightspot.s3.amazonaws.com%2Fscience%2F4a%2Fa5%2Fdd99dd5b4b5599ec3ab958a979bb%2Fbort-models.png)

One final piece of news on this, [Hugging Face Transformers release v4.3.0](https://aws-oss.beachgeek.co.uk/62) shared the news that Bort had been incorporated in this release.

### Workshops

[Build an Authenticated GraphQL API on AWS with CDK](https://aws-oss.beachgeek.co.uk/6k) another new workshop from Nader Dabit, building an authenticated GraphQL API using AWS CDK. To go with this workshop Nader has put together this supporting video, and you can find the [source code here](https://aws-oss.beachgeek.co.uk/6l).

{% youtube DOGadkjV7Hs %}

### Case Studies

[How Vendia leverages the AWS CDK to dynamically provision cloud infrastructure](https://aws-oss.beachgeek.co.uk/5w) Ryan Green from Vendia explains how they use the AWS Cloud Development Kit (AWS CDK) and AWS CloudFormation to dynamically provision cloud infrastructure on behalf of their customers. Vendia enables organisations to securely share data and code across regions, accounts, and clouds at scale. Ryan shares how AWS CDK is instrumental in helping Vendia move fast, maintain high operational standards, and support modern cloud-native architectures.

![arch](https://d2908q01vomqb2.cloudfront.net/0716d9708d321ffb6a00818614779e779925365c/2021/02/01/Vendia_figure_2.png)

### Videos of the week

Some great new videos from last week.

In the first vide, Nader Dabit walks you through building an authentication flow with Next.js, TailwindCSS, and AWS Amplify, implementing an email and password flow as well as sign in with Facebook and Google.

{% youtube 4P2jJRbtTck %}

Following that more AWS Amplify goodness, this time taking a look at AWS Amplify DataStore. Kilo Loco goes over the CRUD (Create, Read, Update, Delete) operations for working with Amazon DynamoDB by using AWS Amplify DataStore with Android and Kotlin.

{% youtube o8cUMz38K1Q %}

Finally this week we have the always awesome and fellow DA, Eddie Zaneski with a short video on getting started with Kubernetes client-go.

{% youtube jiKwjnlc7Wk %}

### Quick updates

**Open Telemetry**

News last week that the specification has reached the [1.0.0 specification milesetone](https://aws-oss.beachgeek.co.uk/6i). Check out the release notes for all the details.

**PartiQL**

DynamoDB local now supports PartiQL (a SQL-compatible query language) so that you can query, insert, update, and delete DynamoDB table data. PartiQL is supported for all DynamoDB data-plane operations, and it helps improve the productivity of developers as they use this familiar, structured query language to perform operations. Developers can use PartiQL to develop applications, and test them offline before deploying them to production.

**MySQL/MariaDB**

Amazon Relational Database Service (Amazon RDS) now supports replication filters for MySQL and MariaDB instances. Replication filters specify which databases and tables are replicated in a read replica. Customers create lists of databases and tables to include or exclude for each replica.  

Replication filtering can reduce the size of read replicas by excluding unnecessary databases or tables, or can benefit security and compliance by excluding databases or tables from a replica. Customers can also use replication filtering to create replicas tailored to specific use cases like analytics or sharding, or to create replicas with different tables or databases in different AWS Regions.

**Serverless Image Handler**

The [Serverless Image Handler solution](https://aws-oss.beachgeek.co.uk/5t) enables fast and cost-effective image manipulation in the cloud by combining highly available, trusted AWS Services with the open-source imaging processing suite, Sharp. The solution automatically deploys and configures a serverless architecture optimised for dynamic image manipulation. It uses Amazon CloudFront for global content delivery and Amazon Simple Storage Service (Amazon S3) for reliable and durable cloud storage at low costs.

This update includes the ability to crop an image as an ellipse, supports images without file extensions, and adds a cache policy and origin request policy in CloudFront to replace the legacy default policies. It also includes several quality-of-life updates, such as improved error handling for cropping and resizing.

**Visual Git support in AWS Cloud9**

AWS Cloud9 now includes visual source control integration for Git (Git panel) built in to Cloud9. Prior to this release Git could only be used on the command line of the integrated Cloud9 terminal. Today’s release gives you the option to use a visual tool, built in to the IDE, to clone, push, pull, add, and commit files to your Git repositories on Cloud9 environments. Cloud9’s visual Git panel will show you the status of files in your Cloud9 environment and let you selectively stage, add, and commit files to your local or remote repository from within the IDE.

**Amazon Keyspaces (for Apache Cassandra)**

Amazon Keyspaces (for Apache Cassandra), a scalable, highly available, and fully managed Apache Cassandra–compatible database service, now helps you automate table creation by supporting point-in-time recovery (PITR) and tag settings in AWS CloudFormation.

With CloudFormation, you can model a collection of related AWS and third-party resources, provision them quickly and consistently, and manage them throughout their lifecycles by treating infrastructure as code. Now, you can use CloudFormation to manage PITR and tag settings for Keyspaces tables. PITR gives you continuous backups of your table data, and you can use it to restore table data to any second in time since PITR was enabled within the preceding 35 days. Tags help you manage, identify, organize, search for, and filter resources. You can create tags to categorise resources by purpose, owner, environment, or other criteria. You also can create detailed cost allocation reports based on tags, and you can use tags in your AWS Identity and Access Management (IAM) policy conditions to control access to resources.

### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen).
