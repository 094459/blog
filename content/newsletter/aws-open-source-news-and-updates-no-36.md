---
title: 'AWS open source news and updates No. 36'
date: '2020-09-21'
tags : [ oss-newsletter ]
---
## September 21st - Instalment #36

Week No.36 and this week have the usual round up of open source goodies, but I do want to call out the Lambda Power Tool UI project and the AWS Graviton2 posts this week as must reads. There is also a a couple of excellent deep dives from Alex Casalboni on optimising Lambda and from Blair Hudson, head of data engineering at Faethm AI. Finally, learn more about how Boston is tackling urban deforestation with the use of open data sets, machine learning and is open sourcing the project.


### Your feedback matters!

I have put together a short feedback survey, which I would ask you to take - it will take no more than 2 minutes. You can access [here](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn). Many thanks!

[Take the survey](https://amazonmr.au1.qualtrics.com/jfe/form/SV_8BsYTwgVY6E6WZn)

### Events for your diary

Have you signed up for these events? Make sure you check them out before they go...

**Optimize your AWS environment**
**September 23rd, 6PM BST**

Mike Elsmore from Logzio is going to talk about using open source observability with AWS Lambda in this online event covering a number of different topics on protecting and optimising your cloud environment. Register to [save your spot here](https://www.awsfest2020.com/?utm_source=logz#lp-pom-block-196).

**AWS controllers for Kubernetes – AWS services, now kubified!**
**September 24th, 6PM BST**

Learn about the design and usage of AWS Controllers for Kubernetes (ACK) from one of its authors and see how you can contribute to its roadmap and development. ACK allows you to use the Kubernetes API to describe not just your Kubernetes objects but also resources on which your applications.

Check out the registration page [here](https://www.cncf.io/webinars/aws-controllers-for-kubernetes-aws-services-now-kubified/).

**CDK Day**
**September 30th, 3PM BST**

Now this is an event you should put in your diaries, an event that has been put together by the AWS CDK community (and a lot of familiar faces from posts I have shared in this weekly newsletter), has a fantastic line up of speakers and promises to be an unmissable event if you are thinking of or looking at AWS CDK. Find more details, including speaker line up and registration, [at the link](https://www.cdkday.com/) -> https://www.cdkday.com/

### Celebrate open source contributors

The articles posted in this series are only possible thanks to contributors and project maintainers and so I would like to shout out and thank those folks who really do power open source and enable us all to build on top of what they have created. 

So thank you to Timothy Spann, Matthew Dorrian, Ben Kehoe, James Beswick, Vadim Dabravolski, Chaitanya Bapat, Corey Barrett, Karan Jariwala, Todd Escalona, Dan Gehred, Nader Dabit, Eric Clemmons, Damodar Shenvi Wagle, Anand, Connor Lindsey, Yegor Shytikov, Conrad Hillairet, Filipe Macêdo, Alex Casalboni, Gerard Sans, Jason Andrews, Nadina Galle, Jaclyn Youngblood, Ray Rogers, Roberto Meda, Michael Hausenblas, Chris Plankey, Gabriel and Lucas Kardonski.

Make sure you find and follow these builders and keep up to date with their open source projects and contributions.


### Latest from open source projects

**Lambda Power Tuning GUI**

[aws-power-tuner-ui](https://github.com/mattymoomoo/aws-power-tuner-ui) is an open source project from Matthew Dorrian at Liberty IT that got me very excited this week, and if you use Alex Casalboni's Lambda Power Tuning tool, then you will be too. AWS Lambda Power Tuner UI is a deployable easy to use website built on a layered technology stack allowing you to optimize your Lambda functions for cost and/or performance in a data-driven way via an easy to use UI. Matthew has crafted a blog post, [Save money and improve performance with the new Lambda power tuner UI](https://t.co/IfMJzOAnp2?amp=1) that will walk you through this project and get you up and running in no time.

![arch](https://miro.medium.com/max/1000/1*uEqSUor7FEJq3YpR0zmQUg.png)

Bravo Matthew!

My colleague Alex Casalboni also wrote a super nice deep dive on Lambda Power Tuning, [Deep dive: finding the optimal resources allocation for your Lambda functions](https://dev.to/aws/deep-dive-finding-the-optimal-resources-allocation-for-your-lambda-functions-35a6) where he looks at optimizing the resource allocation of your Lambda functions. You can read this post, use the Lambda Power Tuning tools and now, thanks to Matthew's project have it in a nice UI.

**aws-export-credentials**

[aws-export-credentials](https://github.com/benkehoe/aws-export-credentials) Ben Kehoe has updated this project and now requires botocore>=1.17 so that it supports loading AWS SSO credentials. If you are not familiar with this library, it allows you to get AWS credentials from a profile to inject into other programs.

**autovpn**

[autovpn](https://github.com/ttlequals0/autovpn) is an open source project that lets you quickly create in a few minutes, on demand OpenVPN Endpoints on AWS. [Autovpn - Create On Demand Disposable OpenVPN Endpoints On AWS](https://hakin9.org/autovpn-create-on-demand-disposable-openvpn-endpoints-on-aws/) is a blog post that shows you how you can get started with this project.

**Amazon CloudWatch agent**

[amazon-cloudwatch-agent](https://github.com/aws/amazon-cloudwatch-agent) this open source project was [announced over the weekend](https://aws.amazon.com/about-aws/whats-new/2020/09/amazon-cloudwatch-agent-now-open-source-and-included-with-amazon-linux-2/), and enables operators to collect metrics and logs from Amazon Elastic Compute Cloud (Amazon EC2), hybrid, and on premises servers. Amazon Cloudwatch Agent uses the open-source project telegraf as its dependency. It operates by starting a telegraf agent with some original plugins and some customised plugins.

**automated-cloud-advisor**

[automated-cloud-advisor](https://github.com/disneystreaming/automated-cloud-advisor) from Disney Streaming Services, this open source project is a extensible tool that aims at facilitating cost optimisation in AWS, by collecting data for resources that are under utilised. To make it easy, the team have made it easy to deploy providing a set of cloudformation stacks that comprise the data collection and the data can be displayed in a Kibana dashboard.

This is the way.

**aws-dev-fabric-for-sql-server**

[aws-dev-fabric-for-sql-server](https://github.com/aws-samples/aws-dev-fabric-for-sql-server) - AWS Dev Fabric for SQL Server is an open-source solution created by Solution Architects and Support Engineers to help customers reduce Amazon EC2 footprint and compute costs up to 77% on development environments running SQL Server. Sounds like a good reason to check it out if you are running SQL Server.

**aws-connect**

[aws-connect](https://github.com/rewindio/aws-connect) this is an open source project from the folks at [Rewind](https://rewind.io/), that provides a wrapper script around AWS session manager to establish remote shell connections or SSH tunnels. This blog post on [Curated AWS SSM Scripts](https://rewind.io/blog/curated-aws-ssm-scripts/) shows how you can use this tool, and is a great read in itself. I have recently immersed myself on AWS Systems Manager and use Session Manager as my go to for connecting to EC2 instances.

**Torus Stack**

[Torus Stack](https://github.com/torus-tools/stack) is an open source project from brothers Gabriel and Lucas Kardonski that takes inspiration from AWS Amplify Console, and makes it super easy to deploy your static websites via the CLI. Gabriel [tweeted](https://twitter.com/gkpty1/status/1307018678341431298) over the weekend, so make sure you check those and comments for more info. Currently it lets you do this to AWS and GoDaddy, but the project is looking to provide more destinations. This is still an alpha project, but why not check it out and provide feedback to Gabriel and Lucas and better yet, get involved in the project.

![arch](https://github.com/torus-tools/stack/raw/master/img/jam_stack_architecture.png)

**nifi-djlqa-processor**

[nifi-djlqa-processor](https://github.com/tspannhw/nifi-djlqa-processor) is a project from Timothy Spann that provides an Apache NiFi plugin so you can use the [Deep Java Library](https://github.com/aws-samples/djl-demo) when creating your workflows. Apache Nifi is an open source tool that helps you automate the flow of information between systems, and Timothy has provided a [blog post](https://www.datainmotion.dev/2020/09/using-djlai-for-deep-learning-bert-q-in.html) to show you how you can use this plugin in a sample Q&A use case.

### Fresh blog posts for your reading pleasure

**AWS Data Wrangler**

[Transform AWS CloudTrail Data using AWS Data Wrangler](https://aprakash.wordpress.com/2020/09/17/transform-aws-cloudtrail-data-using-aws-data-wrangler/) from [Anand](https://twitter.com/anandp86) shows you how you can use the open source project AWS Data Wrangler to easily and efficiently perform extract, transform and load (in this post's case) AWS CloudTrail data. What is AWS Data Wrangler? It is an open-source Python package that extends the power of Pandas library to AWS connecting DataFrames and AWS data related services (Amazon Redshift, AWS Glue, Amazon Athena, Amazon EMR, Amazon QuickSight, etc). It is built on top of other open-source projects like Pandas, Apache Arrow, Boto3, s3fs, SQLAlchemy, Psycopg2 and PyMySQL, and provides abstracted functions to execute usual ETL tasks like load/unload data from Data Lakes, Data Warehouses and Databases.

Also, when you finish reading this, check out Anand's other blog posts on this subject of AWS and data.

**Jupyter and Papermill**

[Scaling Jupyter notebooks across the world with AWS and Papermill](https://dev.to/faethm/scaling-jupyter-notebooks-across-the-world-with-aws-and-papermill-41ic) very nice post from Blair Hudson, head of data engineering at Faethm AI, who talks about how they ensure their data science teams can scale to meet the needs of their rapidly growing and global customer base. You will learn about some of the challenges to scaling and automating data science workflows in a multi-region environment, and see how when it is all put together, the result is an end-to-end serverless git-ops containerised event-driven Jupyter-notebooks-as-code data science workflow execution pipeline architecture. Try saying that in one breath! Luckily, they just call it **notebook-pipeline**

![arch](https://res.cloudinary.com/practicaldev/image/fetch/s--fBi4Drfg--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/nvj0lq2cvd0c5apytb3b.jpg)

**Serverless and AWS CDK**

[Using Serverless Framework and CDK together](https://dev.to/aws-builders/using-serverless-framework-and-cdk-together-12he) from Frank Wang talks about how you can use Serverless Framework and AWS CDK frameworks in concert rather than either/or when building your serverless applications. If you know only one of these, then don't worry as this post provides a good primer before diving into how the combination of both might be just what you are looking for.

**Serverless monitoring and alerting**

[Self-Hosted Lambda Monitoring and Alerting With Slack](https://medium.com/@cplankey/self-hosted-lambda-monitoring-and-alerting-with-slack-95d1b4e3b204) is a look back from Chris Plankey on his open source solution for monitoring and alerting his serverless stacks. Sometimes you might need to keep the logging and monitoring systems within the boundaries of your AWS account, so this post and accompanying GitHut repository might be a good place to start.

![arch](https://miro.medium.com/max/700/1*a1HqNi76rEoELjDx7ETwSg.png)

**Graviton**

A few of AWS Graviton related posts this week. First up is an very excitable post from Yegor Shytikov, [T4g (AWS Graviton 2 burstable EC2) instance PHP performance](https://t.co/pb81SPDECr?amp=1), sharing some benchmarks of PHP workload performance on a number of different instances. If you are running PHP workloads on AWS, then you will want to read this post to see how you might be able to optimise your setup. I will leave you with this comment from Yegor:

>AWS worked together with the PHP community to drive major improvements to the performance of the PHP software stack on the ARM Graviton2-based instances. By using AWS Graviton2 based instances, the latest release of PHP-7.4.9 currently experiences up to 37% faster execution time compared to the previous release PHP-7.3. This significantly lowers the cost of running terrible PHP software such as Magento 2 on Amazon EC2 M6g instances.

In this second post [Assessing Seismic Wave Modelling on AWS Graviton2 with SW4Lite](https://community.arm.com/developer/tools-software/hpc/b/hpc-blog/posts/assessing-seismic-wave-modelling-on-aws-graviton-2-with-sw4lite), Conrad Hillairet shares his views on the readiness of AWS Graviton2 for running [SW4Lite](https://github.com/geodynamics/sw4) workloads. SW4Lite is an open source tool that helps researchers understand and simulate the effects of earthquakes, evaluate seismic hazards and calculate potential damage to buildings. No spoilers, but make sure you check out his conclusion.

![diagram](https://community.arm.com/resized-image/__size/1265x900/__key/communityserver-blogs-components-weblogfiles/00-00-00-38-07/pastedimage1599172081156v2.png)

Lastly we have [AWS Graviton processors expand options for embedded Linux developers](https://dev.to/aws-builders/aws-graviton-processors-expand-options-for-embedded-linux-developers-nc3) from Jason Andrews, who looks at how embedded Linux developers can take advantage of the AWS Graviton instance types to perform many tasks in a shorter time with more flexibility. Jason provides a detailed walkthrough of how to get started. Nice post Jason!

**Prometheus**

[Prometheus Remote Write Exporter](https://connorlindsey.dev/projects/prometheus-remote-write-exporter) - from Connor Lindsey talks about his time spent at AWS as an intern, working on the open source project Open Telemetry. He dives into the details of what he worked on, building a Prometheus Remote Write API Exporter for the Go SDK. The exporter is used in Go applications collecting metrics data (server latency, HTTP status codes, etc.) with OpenTelemetry. These can then be sent (collected metrics) to backends using the Prometheus Remote Write API specification. You can see the GitHub repo with the code Connor wrote too.

![image](https://connorlindsey.dev/static/a6e53dc0ecba78e8aa2a6bacbbc56d01/f3583/grafana-screenshot.png)

**ASP.NET Core**

[ASP.NET Core on AWS Elastic Beanstalk Docker image through GitHub, CodeBuild, and CodePipeline CI/CD.](https://medium.com/@fmacedoo/asp-net-core-on-aws-elastic-beanstalk-docker-image-through-github-codebuild-and-codepipeline-bfe00d8dbec6) from Filipe Macêdo, shows you how to create a CI/CD pipeline for your .NET Core services, and how you can then deploy these onto AWS Elastic Beanstalk. Felipe provides source code too.

**AWS Amplify and Vue**

[Build your first full-stack serverless app with Vue and AWS Amplify](https://medium.com/@gerard.sans/build-your-first-full-stack-serverless-app-with-vue-and-aws-amplify-9ed7ef9e9926) nice post from Gerard Sans, where he shows you how to build a full-stack serverless app using Vue and AWS Amplify, creating a new project and adding a full authorisation flow using the authenticator component. If you are looking for your first AWS Amplify project to work on, this is a perfect project and post.

### AWS open source posts

**AWS SAM**

[Uploading to Amazon S3 directly from a web or mobile application](https://aws.amazon.com/blogs/compute/uploading-to-amazon-s3-directly-from-a-web-or-mobile-application/) this post and project from James Beswick will allow you to quickly get a nice web front end that you can access from your browser or mobile and allow you to upload files which are then stored on Amazon S3. He shows you how to do this using AWS Serverless Application Model or AWS SAM.

![arch](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2020/09/09/s3-2.png)

Code for this project can be [found here](https://github.com/aws-samples/amazon-s3-presigned-urls-aws-sam). As James says in this post:

>Many web and mobile applications allow users to upload data, including large media files like images and videos. In a traditional server-based application, this can create heavy load on the application server, and also use a considerable amount of network bandwidth.
>
>By enabling users to upload files to Amazon S3, this serverless pattern moves the network load away from your service. This can make your application much more scalable, and capable of handling spiky traffic.

**GitHub actions and AWS CDK**

[Cross-account and cross-region deployment using GitHub actions and AWS CDK](https://aws.amazon.com/blogs/devops/cross-account-and-cross-region-deployment-using-github-actions-and-aws-cdk/) - Damodar Shenvi Wagle shows you how to use GitHub Actions to deploy an AWS Lambda-based API. This solution will show you how you can do this to any AWS account and Region using the cross-account deployment strategy. GitHub Actions is a feature on GitHub that helps you automate your software development workflows in the same place you store code and collaborate on pull requests and issues. You can write individual tasks called actions, and combine them to create a custom workflow. Workflows are custom automated processes that you can set up in your repository to build, test, package, release, or deploy any code project on GitHub.

![arch](https://d2908q01vomqb2.cloudfront.net/7719a1c782a1ba91c031a682a0a2f8658209adbf/2020/09/07/design-1.png)

**AWS Amplify**

[SSR Support for AWS Amplify JavaScript Libraries](https://aws.amazon.com/blogs/mobile/ssr-support-for-aws-amplify-javascript-libraries/) by Nader Dabit and Eric Clemmons share how the latest release of the Amplify JavaScript libraries add additional features that further enable developers to build SSR apps using modern web frameworks like Next.js and Nuxt.js. Modern web frameworks like Next.js and Nuxt.js combine hybrid static site generation (SSG) and server-side rendering (SSR) along with traditional client rendering to enable developers to build fast, modern sites while also providing a great developer experience, and these are increasingly popular with developers. Eric and Nader walk you through this new update and show you how to enable SSR in your Next.js application in Amplify.

**Cloud Digital Interface (AWS CDI)**

[AWS debuts Cloud Digital Interface (AWS CDI) to reliably transport uncompressed live video between applications](https://aws.amazon.com/blogs/media/aws-debuts-cloud-digital-interface-cdi-to-reliably-transport-uncompressed-live-video-between-applications/) Dan Gehred writes a post announcing the open source project, AWS Cloud Digital Interface (AWS CDI), of libraries and documentation that enable you to build live video solutions on AWS. This project provides access to the network performance, reliability, and uncompressed video capabilities required to build applications including TV channel playout, live video production switching, motion graphic insertion, multi-viewers, video frame rate and color space conversion, forensic watermarking, and video decoding and encoding. You can find a link to the GitHub repo [here](https://github.com/aws/aws-cdi-sdk) and the documentation covers how to get started if you want to kick the tyres.

There was extensive coverage in the media, and you can read up what others though [here](https://www.sportsvideo.org/2020/09/16/aws-introduces-cloud-digital-interface-for-uncompressed-live-video-transport-between-applications/) and [here](https://www.broadcastprome.com/products/aws-debuts-cloud-digital-interface-to-transport-live-video-between-applications/).

**Horovod and Apache MXNet**

[Reducing training time with Apache MXNet and Horovod on Amazon SageMaker](https://aws.amazon.com/blogs/machine-learning/reducing-training-time-with-apache-mxnet-and-horovod-on-amazon-sagemaker/) this collaboration between Vadim Dabravolski, Chaitanya Bapat, Corey Barrett, and Karan Jariwala share their thoughts about distributed machine learning training, and how you can reduce training time with Horovod (an open-source distributed deep learning framework), Apache MXNet and Amazon SageMaker. Read on to know more about inter-GPU and inter-node communication and why it matters.

**PyTorch**

[Serving PyTorch models in production with the Amazon SageMaker native TorchServe integration](https://aws.amazon.com/blogs/machine-learning/serving-pytorch-models-in-production-with-the-amazon-sagemaker-native-torchserve-integration/) my good friend Todd Escalona has written a nice post and walk through that will help you deploy your PyTorch models with TorchServe. TorchServe is an open-source project that answers the industry question of how to go from a notebook to production using PyTorch, and TorchServe is now natively supported in Amazon SageMaker as the default model server for PyTorch inference. 

![arch](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2020/08/27/serving-pytorch-models-1.jpg)

**Gatekeeper**

[Using Gatekeeper as a drop-in Pod Security Policy replacement in Amazon EKS](https://aws.amazon.com/blogs/containers/using-gatekeeper-as-a-drop-in-pod-security-policy-replacement-in-amazon-eks/) a post from Jason Umiker that shows you how to increase your security posture for your Kubernetes clusters, using [Gatekeeper](https://github.com/open-policy-agent/gatekeeper), part of the Open Policy Agent (OPA) open source project in the Cloud Native Computing Foundation (CNCF). If you are currently using Kubernetes Pod Security Policies (PSP) then you might want to read this and find out how Gateway provides an alternative/better way. Don't want to give too much away, but in this short post you will certainly have a better understanding of your options.

**D3**

[Creating simple AWS Costs and Usage charts with a D3 JavaScript library](https://aws.amazon.com/blogs/opensource/creating-simple-aws-costs-and-usage-charts-with-a-d3-javascript-library/) this post from Roberto Meda show you how you can use the very popular open source charting library, D3, and very quickly export your billing data from AWS to create some nice graphs to help visualise your usage of services over time. This is great for very small, adhoc kinds of requests as Roberto points out.

### Case Study

**Lustre and ParallelCluster**

[The Water Institute of the Gulf runs compute-heavy storm surge and wave simulations on AWS](https://aws.amazon.com/blogs/publicsector/water-institute-gulf-runs-compute-heavy-storm-surge-wave-simulations-aws/) this case study from Ray Rogers shows how the Water Institute of the Gulf (Water Institute) runs its storm surge and wave analysis models, which are critical in forecasting hurricane storm surge event (like Hurricane Laura in August 2020), evaluating flood risk for the Louisiana and other coastal states, helping governments prepare for future conditions, and managing the coast proactively. To do this they use open source software running on AWS, using services such as Amazon FSx for Lustre, and Amazon ParallelCluster that helps them have a faster workflow with reduced costs.

![pic](https://d2908q01vomqb2.cloudfront.net/9e6a55b6b4563e652a23be9d623ca5055c356940/2020/09/18/Water-Institute-2-1-1024x425.jpg)

[Partnering with the City of Boston's New Urban Mechanics to co-explore the application of an open-source tree-detecting algorithm](https://www.linkedin.com/pulse/partnering-city-bostons-new-urban-mechanics-co-explore-nadin%C3%A8-galle/) this post from Nadina Galle and Jaclyn Youngblood talks about the application of open source datasets and software to help with urban forest management, creating an AI-enabled tree identification model which allows them to generate actionable insights about urban trees. For example, how do you detect and manage when people in urban areas are cutting down trees they should not be? This is not a problem limited to the giant forests, but has big impacts in urban areas too. From this post:

>So often, those combating urban deforestation don’t have the tools they need to make a significant impact. Changing this starts with changing the way that cities collect information on their tree inventory. And that’s what we set out to do.

Check out the repository [here](https://github.com/krakchris/TreeTect).

![pic](https://media-exp1.licdn.com/dms/image/C5612AQGYMytzuBPTBg/article-cover_image-shrink_423_752/0?e=1605744000&v=beta&t=9WrwAS3YQJ0P7ICEsTMcZuxC51nuf7GtQYY2Ybw43gA)

### Quick updates

**AWS ParallelCluster 2.9.0**

AWS ParallelCluster is a fully supported and maintained open source cluster management tool that makes it easy for scientists, researchers, and IT administrators to deploy and manage High Performance Computing (HPC) clusters in the AWS cloud. HPC clusters are collections of tightly coupled compute, storage, and networking resources that enable customers to run large scale scientific and engineering workloads.  Significant feature enhancements to this latest release of ParallelCluster include:

* Support for multiple instance types in Slurm: Users can now create multiple job submission queues inside of ParallelCluster and specify multiple instance types within each queue. On job submission, users can specify the instance types they would like to use for their job as well as the queue to which they would like to submit it, simplifying multi-stage workflows and the ability to run multiple workloads with distinct needs from a single cluster.
* Support for DCV on Graviton2 instances: In this release, support for NICE DCV has been extended to AWS Graviton2 instances. This provides more platform choice flexibility for workloads requiring remote visualization.
* Slurm power management plugin: We have rearchitected our integration with Slurm to use the Slurm power management plugin. This integration improves cluster stability and precision in scaling compute resources to match individual jobs’ requirements.

### Share your open source projects 

Do you have some content you want to share with a broader audience? We are always looking for guest content for the AWS Open blog. Please get in touch (via comments below) and I would love to speak with you about what you are doing in open source. We are always looking for interesting new content.

The best submissions will get some AWS Credit codes as a thank you.


### Stay in touch with open source at AWS

I hope this summary has been useful. Remember to check out the [Open Source homepage](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) to keep up to date with all our activity in open source by following us on [@AWSOpen](https://twitter.com/AWSOpen)14