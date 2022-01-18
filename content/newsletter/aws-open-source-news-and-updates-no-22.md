---
title: 'AWS open source news and updates No. 22'
date: '2020-06-01'
tags : [ oss-newsletter ]
---
## June 1st - Instalment #22

Episode 22, and another great collection of open source stories, updates and projects. Whether it learning about new open source application run times like Deno, impactful projects  like AutoSpotting that might help you reduce your costs or those simple but every so useful projects that you just could not get by without, such as ssosync or EKStender.

Please contact me with your AWS related open source projects. I have prizes for the best contributions...so look forward to seeing what you send.

**Must watch**

Fresh from DockerCon Live, this theCube interview with AWS's own Deepak Singh (VP of compute services at AWS) is well worth checking out. You can read the post on Sillicon Angle, [Containers 101: AWS, Docker and how to choose a container service](https://siliconangle.com/2020/05/29/containers-101-aws-docker-and-how-to-choose-a-container-service-dockercon/).


{% youtube jUT1wSbUXTg %}

### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created.

So thank you to Lee Packham, Rani Lian, Taha Zafar, Christian Măgherușan-Stanciu, Ryan Graham, Andrew Hughes, Massimo re Ferre (@mreferre), Ali Haydar, John Rotenstein, Piotr Mionskowskih, Jonas Birmé, Joel Lutman, Austen Collins, Rob Sutter, Jared Nielsen, Aditya Bindal, Derya Cavdar, Robert Zhu, David Gibb, Matt Asay and Hari Pachuveetil

### Latest from open source projects

**ssosync**

If you are using G-Suite and have been looking to see how you can integrate your users with AWS Single Sign on, then look no more. **ssosync** is an open source project that allows you to synchronise (one way) from your G-suite directory to AWS SSO, making it super easy to manage your users that you provide access to AWS resources to.

Great open source project from [Lee Packham](https://twitter.com/Joolz) and a walk through of how to use this project from myself. Check out the blog post, [Setting up G-Suite and AWS SSO with ssosync, which also has links to the GetHub repository](https://dev.to/aws/draft-setting-up-g-suite-aws-sso-and-ssosync-5fbc).


**AutoSpotting**

When I came across this I could not believe I had heard about this before. AutoSpotting is an open source project developed by Christian Măgherușan-Stanciu that help you to potentially reduce to cost of running your EC2 instances by using automation to change the instance types and the use of spot instances.

The project says that it can help you to reduce your costs by 60-80%, which is a very bold statement and probably worth most folks checking out.

The project is implemented all within your account, deployed via a Lambda function and controlled via your own security policies. There are documented IAM policies to get this up and running. To get installed you compile the (Go) binaries and then deploy it (a CloudFormation template is provided).

![Saving image](https://camo.githubusercontent.com/6fa4723f9ceceeb41c741a5857166d05c20d1930/68747470733a2f2f6175746f73706f7474696e672e6f72672f696d672f736176696e67732e706e67)

The project webpage can be found at https://autospotting.org/ and the source code (and evaluation binaries) at the [GitHub repository of AutoSpotting](https://github.com/AutoSpotting/AutoSpotting). You can also read the old blog posts at https://blog.cloudprowess.com/ which are very useful to learn how this project evolved.

Great project Christian!

**credz**

Do you use Okta Identity management products? If so, then this small but incredibly useful project from [Ryan Graham](https://github.com/ryangraham) will allow you to turn your Okta identity into AWS credentials via the command line.

![credz demo](https://github.com/ryangraham/credz/raw/master/images/usage.gif?raw=true)

To get started, head over to the [credz GitHub repository](https://github.com/ryangraham/credz) and the following the install instructions. This project is still in the early stages, so make sure you check out the README and feed back any issues.

Thanks Ryan!

**Okta, Serverless and Java**

Another post at Okta caught my eye, this walkthrough from Andrew Hughes, setting up a very simple API that uses Okta to authenticate valid API requests. GitHub repository link is within the post, which you can find here, [Serverless Java with Amazon Web Services](https://developer.okta.com/blog/2020/05/27/serverless-java-aws).

Thank you Andrew!

**EKStender**

One of the great strengths of open source software is the ability to build on top of or extend your functionality with features that those open source projects provides. 

[Massimo](https://twitter.com/mreferre) tweeted about a new project of his this week that does just that. Massimo's project, [EKStendder](https://github.com/mreferre/ekstender) does just that. From the project page;

>The tool is aimed at bridging the gap that exists between a vanilla K8s deployment (too basic for some operational requirements) and very opinionated platforms built on top of K8s (too opinionated for many use cases).

>EKStender is not intended to be a production tool nor a product per se. It is more of a prototype (or EKSperiment?) that intercept the needs of developers and IT of building something that sits in between a CaaS and a PaaS (for lack of better terminology).

>Without EKStender users of EKS would need to deploy manually the add-on components they need. EKStender automates those tasks by enabling said tools. See below for a list of these add-ons.

![Ekstender deployed](https://github.com/mreferre/ekstender/raw/master/images/ekstender.png)

![RUnning](https://github.com/mreferre/ekstender/raw/master/images/ekstender-setup.gif)

Make sure you check out some of Massimo's other projects too. Thank you!

**Amazon S3 Find and Forget**

Amazon S3 Find and Forget is a solution to the need to selectively erase records from data lakes stored on Amazon Simple Storage Service (Amazon S3). This solution can assist data lake operators to handle data erasure requests, for example, pursuant to the European General Data Protection Regulation (GDPR).

The Amazon S3 Find and Forget solution can be used with Parquet-format data stored in Amazon S3 buckets. Your data lake is connected to the solution via an AWS Glue table and specifying which columns in the table contain user identifiers.

Once configured, you can queue record identifiers that you want the corresponding data erased for. You can then run a deletion job to remove the data corresponding to the records specified from the objects in the data lake. A report log is provided of all the S3 objects modified.

The solution provides a web user interface, and a REST API to allow you to integrate it in your own applications.

**Warning: This project is currently in beta and should not be used for production purposes.**

Interested? Head over to the AWSlabs GitHub repository [here](https://github.com/awslabs/amazon-s3-find-and-forget)


### Blog posts you should check out

**AWS Cloud Development Kit (AWS CDK) for beginners**

If you are wondering what AWS Cloud Development Kit (CDK) is, then wonder no more. AWS CDK is an open source software development framework to model and provision your cloud application resources using familiar programming languages so you can use your existing programming knowledge to write infrastructure as code.

It is an awesome open source project, and this post [AWS CDK For beginners](https://levelup.gitconnected.com/aws-cdk-for-beginners-e6c05ad91895), from [Rani Lian](https://twitter.com/ranilian?lang=en) walks you through a gentle introduction before getting down and installing and writing your first CDK code.

If you want to know how this is different from AWS CloudFormation, get a more detailed overview of what AWS CDK or kick the tyres and see it working, this post is for you.

Nice work Rani!

**Static websites on Amazon S3 with AWS CDK**

In this post by Ali Haydar, find out how you can use AWS Cloud Development Kit (AWS CDK) and Amazon S3 to build your static web sites.

You can read the post [here](https://t.co/Ly912KCc7r?amp=1). Thank you Ali!

**Getting started with AWS Amplify**

In this post [Cooking Serverless with AWS Amplify](https://t.co/nDF3bgEiJp?amp=1) Shehan Wisumperuma offers a quick introduction into Serverless and AWS Amplify. If you are looking for a 5 minute read, then why not check this out.

Thank you Shehan.

**Serverless Express**

Great post from Austen Collins, on taking an existing Express.js application and hosting it via AWS Lambda and AWS HTTP API. Express (or Express.JS as it is sometimes referred to) is a web application framework for Node.js, and is a very popular server framework. Many developers know or have Express based projects, and looking at how you move those onto a serverless operational model sounds interesting. As the post says:

>If you simply want to host a common Express.js Node.js application, have it auto-scale to billions of requests, and charge you only when it's used, we have something special for you...

![Demo image](https://s3.amazonaws.com/assets.github.serverless/components/serverless_express_cli_deploy.gif)

Read on in [Serverless Express - Easy API's on AWS Lambda and AWS HTTP API](https://www.serverless.com/blog/serverless-express-apis-aws-lambda-http-api/). Thank you Austen.

**Installing Moodle on AWS**

Moodle is an open source project that has been around for a while now, and provides a comprehensive set of capabilities for those wanting a learning management system (LMS), useful if you are looking to provide remote online learning and education.


In this post by Taha Zafar on the Cloudways blog, [How to install Moodle on AWS](https://www.cloudways.com/blog/host-moodle-aws/), find out how to quickly get your own instance of Moodle up and running via Cloudways.

**GitOps**

What is GitOps?  GitOps is a set of prescriptive best practices for cloud-native deployment, management, and monitoring. Check out [this page from Weaveworks](https://www.weave.works/technologies/gitops/), which includes the detailed definition as well as tenets.


In [AWS meets GitOps](https://manta-innovations.co.uk/2020/05/20/aws-meets-gitops/) Joel Lutman shares his thoughts on GitOps, Flux and running this on AWS inspired by AWS Solution Architect Jason Umiker’s session at the AWS Summit Online, May 2020, Kubernetes GitOps on AWS.

The post breaks down this session, and how it demonstrate how GitOps with Flux could be achieved on AWS using AWS CodeBuild and CodePipeline, alongside external kubernetes operators to deploy a change running on EKS. Check it out, it is a quick read.

![GitOps pic](https://manta-innovations.co.uk/assets/images/blog/GitOps%20-%20cycles.png)

Thank you Joel!

### dev.to round up

There are some really great posts on dev.to, so here is a quick round up of the ones I checked out this week, and ones I think you should check out too!


**AWS Step Functions and AWS CDK**

[Piotr Mionskowskih](https://dev.to/miensol) on dev.to walks you through an example of getting AWS CDK to create a step function. To read on, check out [Combine AWS Step Functions with CloudWatch events using AWS CDK](https://dev.to/miensol/combine-aws-step-functions-with-cloudwatch-events-using-aws-cdk-d75).


**EC2 Stopinator**

This great project from colleague [John Rotenstein](https://dev.to/aws_john) simplifies the task of how to schedule the hibernation of your EC2 instances. With this project, you can quickly get it up and running and then schedule shutting down your EC2 instances. Keep following John as he has plans to introduce more functionality. [GitHub repo for the EC2 Stopinator can be found here.](https://github.com/aws-john/simple-lambda-stopinator-for-ec2)

**Virtual channels with Consuo**

In this post by Jonas Birmé, [Launching Virtual Channels on AWS with Consuo](https://dev.to/consuo/launching-virtual-channels-on-aws-with-consuo-32en), Jonas walks you how to deploy Consuo onto AWS ECS Fargate. As Jonas himself writes:

> deploy this component to AWS and not having to manage any server instances.

![architecture](https://res.cloudinary.com/practicaldev/image/fetch/s--j1uqLLkg--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/i2drh1xe20pek7o57mmr.png)

### AWS updates

Next up is a series of updates from across AWS teams on some of the areas that touch open source.

**Continuous delivery, Swift and Amazon Linux 2**

Following up from a previous post, David Gibb shows how to build a continuous delivery process that targets Amazon Linux 2 in the post, [Continuous delivery with server side Swift on Amazon Linux 2](https://aws.amazon.com/blogs/opensource/continuous-delivery-with-server-side-swift-on-amazon-linux-2/).The previous post described how to use AWS tools to build, test, and release server-side Swift code on two platforms: Amazon Elastic Container Service (Amazon ECS) and Elastic Compute Cloud (Amazon EC2) running Ubuntu Linux. Recently Swift.org has released official support for the Amazon Linux 2 operating system, so this posts brings everything up to date.

![architecture](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2020/05/21/Swift-Pipeline-AL2-1024x541_wht-bg-1.png)

Thank you David!

**Bonus Content**

If you are interested in what Swift is or learn more about Swift on AWS, then why not check out this post [Introducing Swift AWS Lambda Runtime](https://swift.org/blog/aws-lambda-runtime/), by Tom Doron which provides a great primer.


**jsii**

jsii is one of my favourite open source projects, it is super useful and I think folks are going to love this post. It helps solve the challenge around how to build multiple language specific implementations from a single source. For example, you might need to support multiple target languages for a client library, and you might do that today by writing it n number of times. Using jsii, you can take a single source for that client library and then compile it for different languages.

In the post, [Generate Python, Java, and .NET software libraries from a TypeScript source](https://aws.amazon.com/blogs/opensource/generate-python-java-dotnet-software-libraries-from-typescript-source/), Hari Pachuveetil gives a fantastic overview of this project and how to get started. 

Nice one Hari and look forward to hearing more from you in the future!

**Deno**

Do you know what Deno is? From Wikipedia it says;

>Deno is a runtime for JavaScript and TypeScript that is based on the V8 JavaScript engine and the Rust programming language
> source [wikipedia](https://en.wikipedia.org/wiki/Deno_(software))
 
In this post by Robert Zhu, [What is Deno?](https://aws.amazon.com/blogs/opensource/what-is-deno/), Rob provides a nice summary of the important features as well as a quick demo you can follow to do your first Deno program.

ps we also love the Deno logo!

Thank you Rob!

**From BERT to ALBERT**

BERT is a popular machine learning model for doing natural language processing. At re:Invent in 2019 we shared details of how to setup an optimised training setup that allowed this model to be trained in one hour.

Jared Nielsen, Aditya Bindal, and Derya Cavdar post, [Train ALBERT for natural language processing with TensorFlow on Amazon SageMaker](https://aws.amazon.com/blogs/machine-learning/train-albert-for-natural-language-processing-with-tensorflow-on-amazon-sagemaker/) covers how we have open sourced the optimised training code for ALBERT - A Lite BERT.

![overview diagram](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2020/05/26/albert-nlp-1.gif)

This is a very detailed walkthrough of the project, and is essential reading if you are involved in optimising your machine learning training. As the post concludes, "Optimisations such as accelerated linear algebra and mixed-precision training can speed up training five times faster than baseline". 

Find the code in the [GitHub repo here](https://github.com/aws-samples/deep-learning-models/tree/master/models/nlp/albert).


**SAM and AWS Step Functions**

Good news this week for AWS Serverless Application Model (AWS SAM) fans, as support for AWS Step Functions was added. 

For those not familiar with AWS Step Functions, AWS Step Functions lets you define serverless workflows to orchestrate these services so you can build and update your apps quickly. Step Functions manages its own state and retries when there are errors, enabling you to focus on your business logic.

Rob Sutter's post, [Simplifying application orchestration with AWS Step Functions and AWS SAM](https://aws.amazon.com/blogs/compute/simplifying-application-orchestration-with-aws-step-functions-and-aws-sam/) is all you need to know on how to get started and how this works. This post will walk you through creating your first state machine with AWS SAM.

![AWS Step functions diagram](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2020/05/27/sam-starter-template-docs-1.png)

Thanks Rob!


### Quick updates

A collection of short updates from existing projects to keep your knowledge fresh and up to date.

**Apache Kafka version upgrades**

In a few clicks you can take advantage of new Apache Kafka features and bug fixes by upgrading the version of Apache Kafka deployed on new and existing Amazon Managed Streaming for Apache Kafka (Amazon MSK) clusters. Amazon MSK uses rolling upgrade best practices to maintain high availability and support cluster I/O throughout a version upgrade. 

Read on in [Amazon MSK now supports Apache Kafka version upgrades](https://aws.amazon.com/about-aws/whats-new/2020/05/amazon-msk-supports-apache-kafka-version-upgrades/).


**Amplify IOS and Amplify Android**

Amazon Web Services Inc. (AWS) announces the general availability (GA) of Amplify iOS and Amplify Android, which are part of the open source Amplify Framework. Amplify iOS and Amplify Android include libraries and tools (CLI toolchain and IDE helpers) that enable mobile developers to build scalable and secure cloud-powered applications. You can use the libraries with backends created using the Amplify CLI or with existing AWS backends. It is our recommended way to build native mobile applications powered by AWS services.

Compared to the previous AWS Mobile SDKs for iOS and Android, the Amplify iOS and Android libraries are organized by use case and provide declarative programming interfaces that enable mobile developers to easily add capabilities such as Authentication, Analytics, Predictions (for common AI/ML use cases), API (GraphQL and REST), DataStore (for offline and real-time data), and Storage to their mobile applications in few lines of code. Support for escape hatches in the Amplify libraries further allows you to use low level SDK interfaces for additional use cases. Today’s GA release of Amplify iOS and Android adds new Authentication, Predictions, and DataStore programming interfaces that were unavailable in the Preview.

Read the original post [here](https://aws.amazon.com/about-aws/whats-new/2020/05/announcing-general-availability-amplify-ios-android-authentication-data-ai-ml-support/)

**Serverless Bot Framework now with AWS Amplify goodness**

AWS has updated Serverless Bot Framework, an AWS Solution that automatically sets up a chatbot application with sample interactions for the chatbot. The solution makes use of AWS services such as AWS Lambda to implement the machine learning logic of the chatbot, and uses Amazon Polly to turn text responses into lifelike speech.

The solution now makes use of User Pools to allow users to securely sign in to the chatbot with Amazon Cognito. The web interface is re-implemented using ReactJS and AWS Amplify and uses Amazon CloudFront to securely deliver application web assets from Amazon S3 to the user. Learn more about Serverless Bot Framework on AWS, see the solution webpage.

Read more in [AWS Solutions: Serverless Bot Framework adds a remastered user interface and uses AWS Amplify](https://aws.amazon.com/about-aws/whats-new/2020/05/serverless-bot-framework-adds-remastered-user-interface-uses-aws-amplify/)


**Using Spinnaker and Amazon Elastic Container Service (ECS)**

Amazon Elastic Container Service (ECS) launched support for container health checks and a new user interface for load balancers in Spinnaker v1.20. You can now use container health checks through a Spinnaker deployment pipeline which is integrated with ECS services. You can also view and filter load balancers for ECS services within Spinnaker itself to see load balancers and the deployment pipeline for your ECS services in the same tool.

Read the full update on [Amazon ECS launches container health checks and load balancer views in Spinnaker v1.20](https://aws.amazon.com/about-aws/whats-new/2020/05/amazon-ecs-launches-container-health-checks-and-load-balancer-views-in-spinnaker-v1-20/).

### Open Source Builders

Matt Asay's fingers are still cooling down after a week of prolific writing including these posts. Make sure you check out the whole series of Open Source Builders that he has been putting out.

In [Why Data Scientists love Matplotlib](https://thenewstack.io/open-source-builders-why-data-scientists-love-matplotlib/), Matt talks with the Matplotlib development community is project lead Thomas Caswell. It is a great read about how you can sometimes accidentally end up leading a very influential open source project.

In [How PowerDNS turned 'abysmal failure' into open source success](https://www.techrepublic.com/article/how-powerdns-turned-abysmal-failure-into-open-source-success/), Matt talks with Bert Hubert, founder of PowerDNS and a provider of open source DNS software, services, and support on how to build a successful business with open source software.

Look out for more posts from Matt. Thank you!

#### Are you an open source builder?

If you are an open source builder and want to share your project or your open source story please get in touch. I am always looking to talk with people and write these up or video them.


---

### Share your open source projects 

Do you have some content you want to share with a broader audience? We are always looking for guest content for the AWS Open blog. Please get in touch (via comments below) and I would love to speak with you about what you are doing in open source. We are always looking for interesting new content.

The best submissions will get some AWS Credit codes as a thank you.


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen).