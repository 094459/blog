---
title: 'Automating AWS SSO and G-Suite synchronisation with SSO Sync'
date: '2020-06-03'
tags: [g-suite, sso, aws sso]
---
# update-July 28th

> The ssosync tool has had a lot of interest and the community has updated the tool. This means that you should refer to the project home page https://github.com/awslabs/ssosync and check out the README.md for what changes you might need to make to get this tool working.


### Next level ssosync
In a [previous post](https://dev.to/aws/draft-setting-up-g-suite-aws-sso-and-ssosync-5fbc), I talked about setting up AWS Single Sign On (AWS SSO) with G-Suite, and then using an open source project called ssosync to syncronise users and groups from G-Suite into AWS SSO. You can take a look at that post here.

In this post, I want to look at some recent work that **[Lee Packham](https://twitter.com/Joolz)** has done to make running that sync job super easy to do. We will automate the running of ssosync using a schedule AWS Lambda function, and we will set that up using infrastructure as code (IaC) using AWS CDK.

When you finish this walk through, you will have setup ssosync to run on a schedule you define, with logging sent to AWS CloudWatch.

### What you need before you begin.

**NOTE: Using Lambda may incur costs in your AWS account. Please make sure you have checked the pricing for AWS Lambda and CloudWatch before continuing.**


**[1]** You need to have followed the steps in the first blog, which means you will have a number of important configuration files: **credentials.json**, **token.json** and **aws.toml** files that you used for the configuration of ssosync.

**[2]** You also need the right binary file for ssosync. If like myself, you originally ran this on your local machine, you might be using a different binary to what is needed when running on AWS Lambda. As per the GitHub README.md, you require the **AMD64 binary** for AWS Lambda. Thia can be downloaded from the [Releases page](https://github.com/awslabs/ssosync/releases) - (ssosync_Linux_x86_64), but the README.md file provides alternate options.

**[3]** You will need to [install AWS CDK](https://aws.amazon.com/cdk/) before you can begin. 

> This will not take you long, but it will require that you have a NodeJS environment. You might want to consider using AWS Cloud9 as a good way of running this if you do not have this immediately available.

Once you have these to hand and setup, you can begin.

### Clone the repository

You will need to clone the project repository. From your working directory, you can 

``` 
$ git clone https://github.com/awslabs/ssosync.git

```

Which will clone the project and this should leave you with a file structure that looks a little like this (remember, those others files were created as part of the initial setup, and the first blog post)

![Structure](https://ricsuepublicresources.s3-eu-west-1.amazonaws.com/images/sso-2-1.png)

### Setup the environment variables

The next step is to set some environment variables. I am running this on my Mac so this is how I would set these, (if you are using Windows/Powershell, follow the README.md) 

**Note!** When setting the environment variables, you may need to adjust the path to where your files are. These settings work for my layout, but they may need to be adjusted for yours.

I copied the environment  variables and the ssosync binary to the ssosync folder before running the installation, and I ended up with the following file structure. This might be helpful if you run into errors when running the cdk deploy command.

![deployment structure](https://ricsuepublicresources.s3-eu-west-1.amazonaws.com/images/sso-2-10.png)

With that structure setup, I set the environment variables as follows:

```
AWS_TOML=../../aws.toml
GOOGLE_CREDENTIALS=../../credentials.json
GOOGLE_TOKEN=../../token.json
SSOSYNC_PATH=../../dist/ssosync_linux_amd64
```

### Deploy via CDK

Once the variables have been set, all you now need to do to deploy the function into AWS Lambda is run 'cdk deploy'. Make sure you are in the right folder and then run the command.

```
$ cd deploymnets/cdk
$ cdk deploy
```



> Note! If when you run 'cdk deploy' you get errors, like this one, you may need to do an npm update and then re-run
> npx: installed 8 in 2.443s Cannot find module 'typescript'
Require stack:
- /Users/ricsue/.npm/_npx/61409/lib/node_modules/ts-node/dist/index.js
- /Users/ricsue/.npm/_npx/61409/lib/node_modules/ts-node/dist/bin.js
Subprocess exited with error 1

You should see the following screen if all is ok, so press Y to kick off the deployment

![start of install](https://ricsuepublicresources.s3-eu-west-1.amazonaws.com/images/sso-2-2.png)

If all is successful, you should see output like the following:

![success install](https://ricsuepublicresources.s3-eu-west-1.amazonaws.com/images/sso-2-6.png)

If you get an error, then check the next section before trying again.

#### Bootstrap error

When you run the cdk deploy command, you may get the following error:

![error](https://ricsuepublicresources.s3-eu-west-1.amazonaws.com/images/sso-2-3.png)

To resolve this, from the command line enter

```
$ cdk bootstrap aws://{yourawsaccount}/{aws-region}
```
And you should get the following output. Once completed, re-run the cdk deploy command.

![bootstrap](https://ricsuepublicresources.s3-eu-west-1.amazonaws.com/images/sso-2-4.png)

### Post deployment

Once the deployment has been successful we can have a look at what has been deployed.

If we check out AWS Secrets Manager, we can see that the configuration files that we needed to ensure were kept safe are now being managed by AWS Secrets Manager - one less thing for us to worry about how we manage and keep secure.

![secrets manager](https://ricsuepublicresources.s3-eu-west-1.amazonaws.com/images/sso-2-7.png)

We can see the AWS Lambda application list and we will see our application, SsoSyncStack

![AWS SAR](https://ricsuepublicresources.s3-eu-west-1.amazonaws.com/images/sso-2-8.png)

From here we can check how the function is running by checking out the monitoring tab and then diving down into the AWS CloudWatch logs.

![Monitoring](https://ricsuepublicresources.s3-eu-west-1.amazonaws.com/images/sso-2-9.png)

So, this all looks great, now  let us test it out.

### Testing and checking the logs

When this is deployed, the default schedule is set to 1 hour. You can change that if you want by going into the AWS CloudWatch events and editing the schedule.

When the function is triggered, it will output to a CloudWatch log group as you can see from this screenshot.

![logs](https://ricsuepublicresources.s3-eu-west-1.amazonaws.com/images/sso-2-11.png)

When you open the logs you should see output that looks like the following:

![logs](https://ricsuepublicresources.s3-eu-west-1.amazonaws.com/images/sso-2-12.png)

And you should be able to see the completion of the ssosync process (and also captures the Lambda metrics from a billing perspective as well)

![completion](https://ricsuepublicresources.s3-eu-west-1.amazonaws.com/images/sso-2-13.png)

Now I am going to add a new user to G-Suite. I add Jay Dee Salinger

![add user](https://ricsuepublicresources.s3-eu-west-1.amazonaws.com/images/sso-2-14.png)

and in a few minutes we see the following:

![new user added](https://ricsuepublicresources.s3-eu-west-1.amazonaws.com/images/sso-2-15.png)

And finally, when we look in AWS SSO, we can now see the new user and then go on to assign them AWS resources.

![finish](https://ricsuepublicresources.s3-eu-west-1.amazonaws.com/images/sso-2-16.png)

### Conclusion

The ssosync project has provided some additional options on how to run and keep your G-Suite and AWS SSO user and groups in sync.

Using AWS Lambda, AWS CloudWatch events and AWS Secrets Manager allows you to automate this task and ensure that you keep the configuration files safely managed.

Check out the ssosync project, the GitHub repository can be found at [https://github.com/awslabs/ssosync](https://github.com/awslabs/ssosync)



