---
title: 'AWS open source news and updates No.51'
date: '2021-01-11'
tags : [ oss-newsletter ]
---
## January 11th, 2021 - Instalment #51

Welcome to Newsletter #51. This week we have a carefully selected group of blog posts, projects and more. Make sure you check out this weeks must read post on how to prepare and plan for migrating your existing .NET workloads to .NET Core. We have a couple of new projects that you need to take a look at; first of we have Querypal, essential for Amazon Athena users, and following that make sure you check out the preview of the MySQL JDBC driver (in Quick updates section). Finally, check out the events page and sign up to reserve your place.

**Check this out**

In this weeks thought leadership piece, Matt Asay writes, [Who gets credit for open source success?](https://aws-oss.beachgeek.co.uk/17) where he takes a look at the often meandering path that some open source projects taken in their path to adoption and innovation, how this affects and feeds into open source contributions and ultimately the success for those projects and stakeholders. 


### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following superstars:  Kyle Lee, Varun Rao Bhamidimarri, Niko Matsakis, Serge Velikan, Michael Raney, David Musicant, Francisco Oliveira, Ben Kehoe, Adam Števko, Olalekan Fuad Elesin, Florent Brosse, Saurabh Shrivastava, Sameer Goel, and Pratik Patel.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest from open source projects

**aws-gate**

[aws-gate](https://aws-oss.beachgeek.co.uk/w) is a new project from Adam Števko that looks to simplify the developer experience by improving the cli experience when connecting to AWS instances via the command line. Adam had a couple of drivers for creating this project which he outlines in the README.md, so check that out and give this project a go. It might help improve your developer productivity too.

**Querypal**

[Querypal](https://aws-oss.beachgeek.co.uk/x) is a new open source (Apache 2.0 license) from Olalekan Fuad Elesin, AWS ML Hero. Querypal is a web-based, query execution tool which leverages Amazon Athena to make authoring queries and retrieving results simple for users. Querypal provides the ability to find tables, see metadata, browse sample rows, write and edit queries, then submit queries all in a web interface. Once queries are running, users can track query progress and when finished, get the results back through the browser as a table.

He has also put together a nice blog post, [Querypal web-UI for Amazon Athena is now Open Source](https://aws-oss.beachgeek.co.uk/y) that will help you get started. For anyone using Amazon Athena, this has got to be a must read post/project.

**SLaM**

[SLaM](https://aws-oss.beachgeek.co.uk/16), a new open source project from Kyle Lee is a CLI tooled used for creating and packaging AWS Lambda function written in Swift. It can create a new executable Swift Package where you can start coding your Lambda as well as package that Lambda as a zipped Docker image.

**opensource-candies**

[opensource-candies](https://aws-oss.beachgeek.co.uk/10) Serge Velikan has put this nice curated list of resources that open source projects should check out. Lots of tools that are made to open source maintainers/projects at preferred rates and sometimes free.

### Blog posts from the community and customers

**Rust**

In case you missed this post from Niko Matsakis, [The more things change](https://aws-oss.beachgeek.co.uk/13), Niko has put this post to introduce that he move to Amazon as the tech lead of their new Rust team. If you are interested or curious about Rust, Niko has been there from the beginning so this post is well worth reading to understand how is looking to work with the community to make Rust the best it can be.

**boto3**

[boto3 Sessions, and Why You Should Use Them](https://aws-oss.beachgeek.co.uk/v) if you use Python then there is a good chance you are using or have come across boto3. boto3 is the name of the AWS Python SDK. In this post, AWS Serverless Hero Ben Kehoe has put together his thoughts on his approach to writing application and library code that came from a Twitter poll he ran a while back. He also shares as a bonus, the origins of boto3 and why it is called what it is.

**AWS Graviton2**

[How to optimize cost with AWS Graviton and Spot in Amazon Elastic Kubernetes Service (EKS)](https://aws-oss.beachgeek.co.uk/z) nice post from AWS Solution architect Florent Brosse, where he takes a look at how to approach building a multi architecture (x86 and ARM) Docker image running some sample test applications, and then deploying them on Amazon EKS (and for good measure, using Spot instance pricing). You might find this post useful when thinking about how you can optimise your own environments: moving to AWS Graviton2 has been covered in my newsletters beforehand, but combine this with Spot pricing then you can further improve how you optimise.  Florent provides all the source code via his repository on Github (link in the post).

**Open data**

[10 Open-Source Dataset Finders For Your Next ML Project](https://aws-oss.beachgeek.co.uk/11), this is a great post from Kessie Zhang, and whilst not technically open source, these open data set resources are invaluable resources to be aware of if you are embarking on machine learning. Included in this list are the data sets available from Amazon's Open Data registry as well as a few others you might not be familiar with. 

### AWS open source posts

**.NET Core**

[Modernizing legacy .NET applications: DraftKings’ principles for success](https://aws-oss.beachgeek.co.uk/r), this is a guest post from David Musicant, Director of Architecture from DraftKings - a digital sports entertainment and gaming company. In this post David talks about how to approach modernising your existing .NET workloads, migrating them to .NET Core and then being able to apply application modernisation approaches. This post covers a set of principals that you can apply and modify for your own needs to help you plan and execute your own migration.

 ![arch](https://d2908q01vomqb2.cloudfront.net/8effee409c625e1a2d8f5033631840e6ce1dcb64/2021/01/07/2-1.png)

**Amazon Keyspaces (for Apache Cassandra)**

[How to set up command-line access to Amazon Keyspaces (for Apache Cassandra) by using the new developer toolkit Docker image](https://aws-oss.beachgeek.co.uk/o) in this post from Michael Raney, Michael shows you how to set up command-line access to Amazon Keyspaces. Amazon Keyspaces (for Apache Cassandra) is a fully managed Cassandra-compatible database service. Apache Cassandra is an open-source  distributed, NOSQL, wide column database that came out of Facebook that is designed to handle large amounts of data across many servers, providing high availability with no single point of failure. 

Michael takes you through some of the command line tools that you can use to automate database activities, including tools such as cqlsh, the Cassandra Query Language Shell. This has been packaged up in an open source container which you can use against your Amazon Keyspaces environments or your own Apache Cassandra 3.x instances too.

![arch](https://d2908q01vomqb2.cloudfront.net/887309d048beef83ad3eabf2a79a64a389ab1c9f/2020/12/08/DBBLOG-1235-5.jpg)

If you are just starting out in Apache Cassandra, this is a good post to get started with some of the tooling. Michael provides a good intro and walkthrough as well as providing a handy reference sheet of useful commands.

**Apache Ranger**

[Introducing Amazon EMR integration with Apache Ranger](https://aws-oss.beachgeek.co.uk/15) Varun Rao Bhamidimarri takes a look at how to set up Amazon EMR to use Apache Ranger for data access controls for Apache Spark and Apache Hive workloads on Amazon EMR. Apache Ranger is an open-source project that provides authorisation and audit capabilities for Hadoop and related big data applications like Apache Hive, Apache HBase, and Apache Kafka. In this post Varun has provided all the resources you need to reproduce the setup, including a Cloudformation template to accelerate your deployment.

![arch](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2020/12/23/BDB-1113-4.jpg)

**Apache Flink**

[Building a real-time notification system with Amazon Kinesis Data Streams for Amazon DynamoDB and Amazon Kinesis Data Analytics for Apache Flink](https://aws-oss.beachgeek.co.uk/12) in this collaboration between Saurabh Shrivastava, Sameer Goel, and Pratik Patel take a look at a real use case of how real time data can be used to ensure the appropriate action is taken. Using an example of how to protect wind turbines from wind speed, this post shows how you can use Kinesis Data Analytics for Apache Flink (Data Analytics for Flink) and Amazon Simple Notification Service (Amazon SNS) to send a real-time notification when wind speed is greater than 60 mph so that the operator can take action to protect the turbine.

![arch](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2020/12/16/BDB1052-1.jpg)

The code for this solution is available [in the GitHub repository](https://aws-oss.beachgeek.co.uk/14) for you to use and extend.

**Apache Hudi**

[Multi-tenant processing pipelines with AWS DMS, AWS Step Functions, and Apache Hudi on Amazon EMR](https://aws-oss.beachgeek.co.uk/t) in this post, Francisco Oliveira introduces how you can use open source tools like Apache Hudi to build and simplify how you build pipelines that loads data and its ongoing changes (change data capture) from multiple source databases to your data lake. Apache Hudi is an open-source data management framework used to simplify incremental data processing and data pipeline development. 

This post introduces a solution that you can use, explaining how to use a number of AWS services with Apache Hudi on Amazon EMR to convert a single-tenant pipeline to a multi-tenant pipeline. Francisco provides a detailed walkthrough as well as all the necessary scripts to get it up and running.

![arch](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2020/11/13/Multi-tenant-processing-pipelines-1.jpg)

**Apache Hudi workshop**

Check out [this Apache Hudi workshop](https://aws-oss.beachgeek.co.uk/u) if you want to dive deeper. 

### Quick updates

**MySQL JDBC Driver**

The Amazon Web Services (AWS) Java (JDBC) Driver for MySQL is now available in preview. This open source database driver helps applications take advantage of clustered databases, such as Amazon Aurora with MySQL compatibility, reducing failover times from minutes to seconds. The driver is based on MySQL Connector/J and is compatible with all MySQL deployments. The driver can be added to applications without any code changes as it is backwards compatible with the latest versions of existing drivers. Support for JDBC driver for PostgreSQL and more programming languages are coming soon.

The AWS JDBC Driver for MySQL uses the General Public License v2. To get started, [visit the driver’s GitHub project page](https://aws-oss.beachgeek.co.uk/q). You can use the GitHub project to download the driver, file issues, view the roadmap, and open feature requests.

**FreeRTOS**

FreeRTOS now includes pre-configured projects that emulate real micro controller (MCU) cores in software using the QEMU open source emulator. Running FreeRTOS in an emulator makes it easier to test applications using the actual binary code that will run on your MCU device, without having physical access to the MCU device. MCU emulations reduce development time by giving you access to enhanced debugging capabilities and the flexibility to run design experiments on multiple MCUs before you make the final MCU selection. This release includes a QEMU demo project for the Arm Cortex-M3 based MPS2+ FPGA. You can get started by downloading demo code from [GitHub](https://aws-oss.beachgeek.co.uk/p)

### Events for your diary

**Projen Community Meeting**
**January 20th, 5-6pm GMT**

Projen is a code-first approach for managing software project configuration. This is the first meeting of the projen community.
The event will mostly be an unstructured conversation about current and future plans for projen. Any topics are welcome!

[Register for the event here.](http://aws-oss.beachgeek.co.uk/n)


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen).

### Your feedback matters!

I have put together a short feedback survey, which I would ask you to take - it will take no more than 2 minutes. You can access [here](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn). Many thanks!

[Take the survey](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn)