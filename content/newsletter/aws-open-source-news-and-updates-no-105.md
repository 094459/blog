---

title: 'AWS open source news and updates #105'
date: '2022-03-20'
tags : [ oss-newsletter, aws open source, Jobs, Hummingbird, PostgreSQL, OpenSearch, GraphQL, Apache Kafka, Qovery, AWS IoT Greengrass,  Kubernetes, Hugging Face, AWSTerminator, Moodle, Forem, Steampipe, Apache Airflow]

---

## March 21st, 2022 - Instalment #105

Newsletter #105. 

Welcome to edition #105 of the AWS open source news and updates, where we bring you the latest open source projects, posts, events, and much more. This weeks new projects include the latest work in progress from AWS Hero Ian Mckay, "iamfast" is an AWS IAM policy generation tool that is in early stages but promises to be very useful indeed. "iasql-engine" is a tool that models cloud infrastructure as data, "ssm-patch-portal" provides a nice gui front end to simplify patching with AWS System Manager, a new crowdsource guide that contains learning resources for AWS, a business intelligence platform built using open source technologies from the NHS, and many more. If you prefer reading, then this weeks AWS and Community builders have posts, walk throughs and tutorials covering Hummingbird, PostgreSQL, OpenSearch, GraphQL, Apache Kafka, AWS IoT Greengrass, Hugging Face, Forem, Steampipe, and many more. This weeks featured videos include a great overview of preview environments in Qovery and a great beginners video on Kubernetes, and we finish off as always with a round up of community meet-ups and events for open source technologies.

This week I am also sharing a short list of some of the open source roles currently open across Amazon and AWS, covering a broad range of open source technologies. If you are currently looking for your next challenge, love open source, then take a look. If you want to know more about what it is like working here, feel free to reach out to me directly (ricsue@amazon.com, or via social media)

**Open Source Jobs at Amazon**

Prompted by this tweet from colleague [Daniel Doubrovkine](https://aws-oss.beachgeek.co.uk/1go) who shared a number of interesting open source jobs currently open at Amazon. I thought I would list some of them here, but make sure you follow Daniel and keep up to date with any latest roles he might post.

* [Senior Frontend Engineer - Open-Source Jupyter Team at AWS](https://aws-oss.beachgeek.co.uk/1gp) - join existing maintainers and contributors for this open source project working full time on Jupyter
* [Sr. SDE, OpenSearch Security](https://aws-oss.beachgeek.co.uk/1gq) - the OpenSearch Security team is tackling the big goal of making OpenSearch secure by default, making security easy, intuitive and friction-free
* [Software Development Engineer (Open Source) - Amazon MWAA, Amazon MWAA](https://aws-oss.beachgeek.co.uk/1gr) - come work with the existing developers working upstream on Apache Airflow, a super bunch of builders who I have the privilege of collaborating with from time to time
* [Embedded Linux Engineer, IoT](https://aws-oss.beachgeek.co.uk/1gs) - participate in the Yocto Project and Automotive Grade Linux communities, and contribute code and documentation to the projects that make the building of connected devices easier
* [MySQL and MariaDB](https://aws-oss.beachgeek.co.uk/1gt) - if you want to work with MariaDB or MySQL, then there are a selection of open roles that might be perfect for you
* [Kernel Development Engineer , Bottlerocket](https://aws-oss.beachgeek.co.uk/1gu) - for experienced software developer in the Linux Kernel, then this might be the job for you

Daniel has shared some others, so make sure to check those out. Your perfect open source job could be a click away. 


**Do you have an interesting open source project you want to share?**

As always, if you are working on anything interesting you would like me to include in this weekly round up, please drop me a line at ricsue@amazon.com.


### Celebrating open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to the following open source heroes: Daniel Doubrovkine, Utsab Ray, Amir Alavi, Amit Dixit, Vandhana Krishnan, Amir Bahmani, Andrew Hopp, Anirudha Jadhav, Joshua Bright, Yaliang Wu, Adron Hall, Steffen Hausmann, Romaric Philogène, Nils Helset, Katja-Maja Kroedel, Sai Vennam, Philipp Schmid, Jean-Gaël Choppe, Eric Cabrel Tiogo, Anuvindh Sankaravilasam, Hank Ehly, Michael Royal, Richard Fan, and Ian Mckay.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.

### Latest open source projects

#### Community

**iamfast**

[iamfast](https://aws-oss.beachgeek.co.uk/1hn) I am always excited about AWS Hero Ian Mckay's open source projects, and this new "experimental" project is an AWS IAM policy generation from application code. Run the tool against your code, and it will generated some sample IAM policy documents. How cool is that. Very nice indeed, and currently supporting Javascript, Python, Go and Java. 

**iasql-engine**

[iasql-engine](https://aws-oss.beachgeek.co.uk/1hp) this project from IaSQL is an open-source tool that models cloud infrastructure as data by maintaining a two way connection between a AWS account and a hosted PostgreSQL database. Detailed documentation and examples, it currently supports a subset of AWS services. For a good summary of what you can do with this project, check out [this Twitter thread from David Regalado](https://aws-oss.beachgeek.co.uk/1hs). If you like the look of this, why not join the community and contribute to add AWS services you care about. One to watch.

**ssm-patch-portal**

[ssm-patch-portal](https://aws-oss.beachgeek.co.uk/1ho) this project from AWS Community Builder Richard Fan  provides you with a web portal that can help you easily manage instance patching via AWS SSM Patch Manager.

![architecture of ssm patch portal](https://raw.githubusercontent.com/richardfan1126/ssm-patch-portal/master/docs/architecture.jpg)

Scripts and examples should help you get this project up and running in no time.

![demo of ssm patch portal](https://raw.githubusercontent.com/richardfan1126/ssm-patch-portal/master/docs/demo.gif)

**deploy-airflow-on-ecs-fargate**

[deploy-airflow-on-ecs-fargate](https://aws-oss.beachgeek.co.uk/1hr) Hank Ehly has put together this repo that provides an example of how to deploy Apache Airflow on Amazon ECS Fargate if you prefer to run and self manage Apache Airflow. This project uses Terraform to help automate the deployment, and provides plenty of examples including some estimate costs of how much you might spend running up this project.

**NHS Business Intelligence Platform**

[NHS_Business_Intelligence_Platform](https://aws-oss.beachgeek.co.uk/1ht) Stewart Morgan shared this project, the NHS Business Intelligence Platform, a Business Intelligence application suite with a primary focus on Population Health Management. This is developed using open source technologies and deployed on AWS, and you can find out more about this project in the blog post that they wrote last year, [One small team created a cloud-based predictive modeling solution to improve healthcare services in the UK](https://aws-oss.beachgeek.co.uk/1hu)

![architecture for NHS BI app](https://d2908q01vomqb2.cloudfront.net/9e6a55b6b4563e652a23be9d623ca5055c356940/2021/08/19/nexus-intelligence-aws-architecture-compressed-1024x709.png)

**AWS-Guide**

[AWS-Guide](https://aws-oss.beachgeek.co.uk/1hq) this is a markdown guide from Michael Royal containing resources for getting started with AWS including the Tools and Applications that will make you a better and more efficient engineer with AWS. Have a look and if there is anything you want to add, why not send Michael a PR.

#### Tools

**firelens-datajet**

[firelens-datajet](https://aws-oss.beachgeek.co.uk/1h1) this project abstracts test configuration from implementation code, by running tests based on a single JSON file and outputting the results. This allows you to route test data to Fluent Bit flexibly. This system can be run locally with a local Fluent Bit process or compiled to a docker image and run with a sidecar aws-for-fluent-bit container. Example configurations and integration document should help you get this going in no time.

**aws-automated-incident-response-and-forensics**

[aws-automated-incident-response-and-forensics](https://aws-oss.beachgeek.co.uk/1gw) the code within this repo was created to address a specific use-case in the automotive industry. In environments where you are operating a large set of accounts, you may find that your Incident Response and Forensics is a manual process that may be prone to mistakes, time-consuming process with many steps, and/or hard to perform by non-trained personnel. The Automated Incident Response and Forensics framework aims to facilitate automated steps for incident response and forensics based on the [AWS Incident Response White Paper](https://aws-oss.beachgeek.co.uk/1gv) (this is in archived status, but they provide a link to the latest version).

![architecture for solution](https://github.com/awslabs/aws-automated-incident-response-and-forensics/blob/main/Documentation/1.png?raw=true)

**aws-dms-cdc-data-pipeline**

[aws-dms-cdc-data-pipeline](https://aws-oss.beachgeek.co.uk/1gy) this repository provides you cdk scripts and sample code on how to implement end to end pipeline for replicating transactional data from MySQL DB to Amazon OpenSearch Service through Amazon Kinesis using Amazon Data Migration Service(DMS).

![architecture for dmc cdc data pipeline](https://raw.githubusercontent.com/aws-samples/aws-dms-cdc-data-pipeline/8b94884e1b8d89c5c44b73a83810a936f05ec748/aws-dms-cdc-analytics-arch.svg)

**app-server-migration**

[app-server-migration](https://aws-oss.beachgeek.co.uk/1h0) this project will help you migrate code from source server to target server, discovering the changes required. 

#### Demos and Samples

**step-up-auth**

[step-up-auth](https://aws-oss.beachgeek.co.uk/1gx) this project contains code that will show you how you can perform step-up authentication using Amazon API Gateway Lambda Authorizer, Lambda functions, Amazon Cognito and Amazon DynamoDB. Let us first review the architecture in next section.

![architecture for step up auth](https://github.com/aws-samples/step-up-auth/blob/main/documentation/step-up-auth-design.png?raw=true)

**create-react-app-amplify-auth-typescript**

[create-react-app-amplify-auth-typescript](https://aws-oss.beachgeek.co.uk/1gz) if you are looking for a quick sample project on getting AWS Amplify with React on TypeScript, this project implements a new version of Amplify Authenticator from Amplify UI to provide a basic authentication flow for signing up and signing in users as well as protected client side routing using AWS Amplify.

### AWS and Community blog posts

**Steampipe Dashboards**

[Steampipe](https://aws-oss.beachgeek.co.uk/1hm) is a really nice open source project that lets you use SQL to instantly query your cloud services (AWS, as well as other public clouds too). A new "dashboards as code" capability, Steampipe Dashboards, now allows you to visualise your queries which you can find out more about by reading their blog post, [Dashboards as Code with HCL + SQL](https://aws-oss.beachgeek.co.uk/1hk). They provide a detailed breakdown and examples, and you can easily build your own dashboards by referencing the library of examples ([Dashboards in AWS Insights](https://aws-oss.beachgeek.co.uk/1hl)). [hands on]

![demo of steampipe dashboards](https://steampipe.io/images/blog/2022-03-release-0-13-0/live-editing-v2.mp4)

**Forem**

[Forem](https://aws-oss.beachgeek.co.uk/1hi) is an open-source project for building communities that powers some of my favourite blogging sites (including dev.to which is where I post this blog). Eric Cabrel Tiogo shares how you can deploy this project on AWS in his post, [Deploy Forem on AWS and build your tech community](https://aws-oss.beachgeek.co.uk/1hh) [hands on]

**AWSTerminator**

[AWSTerminator](https://aws-oss.beachgeek.co.uk/1hg) is an open source project I shared a while back that allows you to deploy an AWS Lambda function for cleaning up AWS resources. [TrackIt AWS Terminator](https://aws-oss.beachgeek.co.uk/1hf) is a super interesting post from Jean-Gaël Choppe, who shares how they use this project together with a tool they have developed (Tagbot) to help them automate how they prune and automate AWS resources that are running that could be shut down. This is an essential read this week. [hands on]

**Hummingbird**

Hummingbird is a Python framework that gives a variety of optimum instance configurations to run your favorite genomics pipeline on cloud platforms. In a guest post, Utsab Ray, Amir Alavi, Amit Dixit, Vandhana Krishnan, and Amir Bahmani from Stanford University collaborate on [Hummingbird – a tool for effective prediction of performance and costs of genomics workloads on AWS](https://aws-oss.beachgeek.co.uk/1h3). They discuss results from profiling popular genomics tools, like BWA-MEM and GATK HaplotypeCaller on AWS using Hummingbird, and share how to use Hummingbird to estimate optimal resources for other genomics workflows. [hands on]

![graph comparison for hummingbird](https://d2908q01vomqb2.cloudfront.net/c5b76da3e608d34edb07244cd9b875ee86906328/2022/03/09/relative-and-ideal.png)

**Apache Kafka**

Steffen Hausmann explains how the underlying infrastructure can affect Apache Kafka performance in the post [Best practices for right-sizing your Apache Kafka clusters to optimize performance and cost](https://aws-oss.beachgeek.co.uk/1h4). Steffen looks at strategies on how to size your clusters to meet your throughput, availability, and latency requirements. The post shows you how you can use the project I shared in last weeks updates ([#104](https://dev.to/aws/aws-open-source-news-and-updates-104-3idj)) to run your own tests for your specific workload characteristics. These are my favourite kinds of posts, and a must read this week. [hands on]

![kafka load testing graphs](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2022/03/03/bdb-428-fig9-throttling-metrics.png)

**GraphQL**

A resolver is the key architectural component that connects GraphQL fields, graph edges, queries, mutations, and subscriptions to their respective data sources and micro services. In the post, [How to connect your GraphQL API to AWS data sources](https://aws-oss.beachgeek.co.uk/1h8) Adron Hall shares some of the ways you can build GraphQL resolvers for AWS data sources, [hands on]

**AWS IoT Greengrass v2**

AWS IoT Greengrass v2 is an open source edge runtime service that you can use to build, deploy, manage, and locally act on the data that your intelligent IoT devices capture. With AWS IoT Greengrass components, which consist of application and runtime libraries, you can develop custom application code, execute tests, and deploy them on your AWS IoT Greengrass core device. In the post, [5 tips to build AWS IoT Greengrass v2 Components](https://aws-oss.beachgeek.co.uk/1hc) Katja-Maja Kroedel shares five tips for you to consider while developing AWS IoT Greengrass v2 components, that will help you  accelerate and improve your development workflow and get started more quickly with the component development. [hands on]

**Other posts worth checking out**

* [Migrating to AWS ParallelCluster v3 – Updated CLI interactions](https://aws-oss.beachgeek.co.uk/1h5) provides some guidance on mapping between version 2 and version 3 of the ParallelCluster CLI command set, to help you plan your migration
* [Migrating petabytes of data from on-premises file systems to Amazon FSx for Lustre](https://aws-oss.beachgeek.co.uk/1hv) covers how to migrate petabytes of data files from on-premises to Amazon FSx for Lustre

![architecture of Lustre migration architecture solution](https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2022/03/14/Fig1-arch-transfer-fsx.jpg)

* [Profile Amazon RDS for PostgreSQL or Amazon Aurora PostgreSQL PL/pgSQL code using plprofiler](https://aws-oss.beachgeek.co.uk/1h6) will show you how to install and configure the plprofiler extension, that can help you to troubleshoot performance related issues
* [Error Handling in Modular AWS SDK for JavaScript (v3)](https://aws-oss.beachgeek.co.uk/1h7) shares how to use concrete classes for AWS service exceptions and how it improves the error handling experience
* [Building your first e-Learning Platform](https://aws-oss.beachgeek.co.uk/1hj) AWS Community Builder Anuvindh Sankaravilasam shows one way you can quickly get Moodle up and running

**Open Data**

Nils Helset, co-founder and chief executive officer (CEO) of DigiFarm, shares how they use AWS and open data to support DigiFarm’s efforts to make agricultural practices more sustainable and efficient in the post, [Bringing world-class satellite imagery to smallholder farmers with open data](https://aws-oss.beachgeek.co.uk/1ha)

### Tutorials and Workshops

**Hugging Face**

[Accelerate BERT inference with Hugging Face Transformers and AWS Inferentia](https://aws-oss.beachgeek.co.uk/1he) is an end-to-end tutorial from Philipp Schmid, where you will learn how to speed up BERT inference for text classification with Hugging Face Transformers, Amazon SageMaker, and AWS Inferentia. [hands on]

**Open Source Software Development**

Over the past couple of weeks, I have been looking at and attending the [Open Source Software Development: Linux for Developers](https://aws-oss.beachgeek.co.uk/1gn) training provided by the Linux Foundation over at edX. The course is intended to guide developers to understand the ‘rules of the road’ of working with open source software, and is great for folks new to open source or seasoned professionals who might want to refresh their knowledge. I learned quite a few new things going through this, so even when you think you know a topic reasonably well, it is good to be reminded that you may not know it all! 


### Quick updates

**OpenSearch**

Andrew Hopp, Anirudha Jadhav, Joshua Bright, and Yaliang Wu share the news and major and minor feature enhancements that have been included in this latest release of OpenSearch in their post, [OpenSearch 1.3.0 is out now!](https://aws-oss.beachgeek.co.uk/1h2). The OpenSearch community have been very busy and there is lots to check out, so dive in to find out more.

![demo of opensearch features](https://opensearch.org/assets/media/blog-images/2022-03-17-Launch-Announcement-1-3-0/field-insights.gif)

**PostgreSQL**

A couple of updates this week. First up, Amazon RDS for PostgreSQL now supports minor versions 14.2, 13.6, 12.10, 11.15, and 10.20.

Following that is news that Amazon RDS for PostgreSQL has added support for mysql_fdw which allows your PostgreSQL database to connect and retrieve data stored in separate Amazon Aurora MySQL-compatible, MySQL, and MariaDB databases. Foreign Data Wrappers are libraries for PostgreSQL databases that can communicate with an external data source, abstracting the details of connecting to the data source and obtaining data from it. mysql_fdw is a PostgreSQL extension that provides a Foreign Data Wrapper for easy and efficient access to Amazon Aurora MySQL-compatible, MySQL, and MariaDB databases. 

### Videos of the week

**Qovery**

Qovery is a super nice open source project (and Cloud service) that provides one of the simplest ways to deploy your applications onto AWS. CEO Romaric Philogène has been running a number of live videos that show case some of the capabilities (make sure you sign up for them as they are very interactive, hands on and very informative). The last one was on one of the features called Preview Environments. Find out more by watching the stream on demand, [Getting Started with Preview Environment on AWS](https://aws-oss.beachgeek.co.uk/1h9)

**Kubernetes**

Fresh from the reels of the lovely folk from the Containers from the Couch, we have this new video from Sai Vennam that asks the important question of the day - What is Kubernetes and why should you care? In this lightboard explainer, Sai takes us back to the basics with containers and Kubernetes. Scheduling, self-healing, auto-scaling, load balancing and more are covered.

{{< youtube a2gfpZE8vXY >}}

### Events for your diary

If you have an event you want me to publish here, please contact me and I will include it in this listing. 

**AWS Community Day Turkey**
**26 March-Mart 2022 09:00 AM - Hybrid Conference**

AWS Community Day events are community-led conferences where event logistics and content is planned, sourced, and delivered by community leaders. AWS Community Day Turkey is organised by the non profit organisation Cloud and Serverless Turkey community. There are plenty of open source sessions in the line up including Kubernetes and Karpenter, and Terraform so [check out the event and register here](https://aws-oss.beachgeek.co.uk/1hd).


**Building an Open Data Lakehouse with Presto, Hudi, and AWS S3**
**March 29th, 10am PT**

In this 90 minute hands on-virtual lab that will walk you through how to build an Open Data Lakehouse stack with Presto, Apache Hudi, and AWS S3.

If you want to learn more about these open source projects, this looks like the perfect opportunity. Check it out and [register on their registration page](https://aws-oss.beachgeek.co.uk/1ep).

**GitOpsCon Europe**
**May 17th, Valencia Spain**

GitOpsCon Europe is designed to foster collaboration, discussion, and knowledge sharing on GitOps. This event is aimed at audiences that are new to GitOps as well as those currently using GitOps within their organisation. Get connected with others that are passionate about GitOps. Learn from practitioners about pitfalls to avoid, hurdles to jump, and how to adopt GitOps in your cloud native environment.

The event is vendor-neutral and is being organised by the CNCF GitOps Working Group. Topics include getting started with GitOps, scaling and managing GitOps, lessons learned from production deployments, technical sessions, and thought leadership.

Read more about this from the official page [here](https://events.linuxfoundation.org/gitopscon-europe/).

**CDK Day**
**May 26th - Virtual**

This is a community organised event about AWS CDK, cdktf, projen and cdk8s. This will be third year they run this event, and if the previous two are anything to go by, this will be essential viewing - live streamed via You Tube. Check out and register for the event over at their home page at [https://www.cdkday.com/](https://www.cdkday.com/)

**OpenSearch**
**Every Tuesday, 3pm GMT**

This regular meet-up is for anyone interested in OpenSearch & Open Distro. All skill levels are welcome and they cover and welcome talks on topics including: search, logging, log analytics, and data visualisation.

Sign up to the next session, [OpenSearch Community Meeting - Feb2022](https://aws-oss.beachgeek.co.uk/1az)


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)