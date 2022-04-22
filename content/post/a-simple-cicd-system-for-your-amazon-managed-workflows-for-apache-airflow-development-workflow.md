---
title: 'A simple CI/CD system for your Amazon Managed Workflows for Apache Airflow development workflow'
date: '2021-02-03'
tags: [Apache Airflow, mwaa, AWS CodePipeline, AWS CodeCommit]
---
**updated Feb 19th**

![innovate](https://raw.githubusercontent.com/094459/innovateaiml-airflow/main/images/banner.png)

Part of a series of posts to support an up-coming online event, the Innovate AI/ML on February 24th, from 9:00am GMT - you can sign up [here](https://aws.amazon.com/events/aws-innovate/machine-learning/online/emea/?sc_channel=em&sc_campaign=EMEA_FIELD_WEBINAR_innovate-AIML_20210224_7014z000001MJbu&sc_medium=em_&sc_content=REG_t1_field&sc_geo=emea&sc_country=mult&sc_outcome=reg&sc_publisher=aws&trkCampaign=emea21_innovatemlq1&trk=em_emea21_innovatemlq1_ricardosueiras)

* **Part 1** - [Installation and configuration of Managed Workflows for Apache Airflow](https://aws-oss.beachgeek.co.uk/3h)
* **Part 2** - [Working with Permissions](https://aws-oss.beachgeek.co.uk/3n)
* **Part 3** - [Accessing Amazon Managed Workflows for Apache Airflow](https://aws-oss.beachgeek.co.uk/3o)
* **Part 4** - [Interacting with Amazon Managed Workflows for Apache Airflow via the command line](https://aws-oss.beachgeek.co.uk/4s)
* **Part 5** - A simple CI/CD system for your development workflow <- this post
* **Part 6** - [Monitoring and logging](https://aws-oss.beachgeek.co.uk/5r)
* **Part 7** - Automating a simple AI/ML pipeline with Apache Airflow 

In this post I will be covering Part 5, how you can setup a very simple CI/CD setup to enable faster development of your Apache Airflow DAGs. Specifically I will cover a couple of things:

1. Setting up the repository and build pipeline
2. Taking a look at the workflow

**What will you need**

* An AWS account with the right level of privileges
* An environment with the AWS CLI tools configured and running
* Access to an AWS region where Managed Workflows for Apache Airflow is supported
* An environment of Amazon Managed Workflows for Apache Airflow already setup - you should ideally have followed [part one here](https://aws-oss.beachgeek.co.uk/3h).

**An example workflow**

If you examine how MWAA picks up DAGs and supporting files, we know that we have a directory structure that will look similar to this. You MWAA environment will have a root Amazon S3 bucket that is prefixed "airflow-" and within that you will have a dags folder into which you will deploy your actual DAGs. You may also be using requirements.txt to load up additional python libraries or maybe have some custom plugins (you can read more about that [here](https://docs.aws.amazon.com/mwaa/latest/userguide/configuring-dag-import-plugins.html)) 


```
.
└── airflow-bucket
    ├── dags
    │   └── example-hello.py
    ├── plugins.zip
    └── requirements.txt
```

As a development lifecycle, we want to simplify the process of moving workflows from developers to MWAA, and we want to minimise manual steps that they should use (such as manually copying the files to S3 either via the console or command line). We also want to ensure that the workflows (which is just python code) is checked into source control. 

Many organisations use CI/CD pipelines to help automate the process of taking code from source code and then after going through defined validation, testing or other steps, is then deployed into the final target destination - in this case, we want the target to be the airflow-bucket that we have defined.

In this post we will walk you through setting this up so you can use this as a basis for your own ideas on how you can do this yourself. I will start off with setting up a source code repository - I am going to assume you want might want a private repo and so will use something like AWS CodeCommit, but you could equally use public repos like GitHub so feel free to adapt/adjust as it should work the same.

We will setup a very simple workflow that takes every commit we do in our source code repository, and then syncs that code to the target DAGs folder where MWAA will pick it up.

**Setting up the pipeline**

I am going to use AWS CloudFormation again to set this up. To help us we need a supporting resource, which will be used to propagate the initial repository. You will find all the resources in the GitHub repository [here](https://github.com/094459/innovateaiml-airflow/tree/main/cf). You will need the following files in this walkthrough:

```
create-cicd-simple.yaml
mwaa-cfn-cici-parameters.json
```

The first step is to create the initial rep initialisation file that we need to provide to CloudFormation so it can create the repository. (You can do this manually via the AWS Console, and you will then not need to do this). Using the above directory structure above we can do:

```
$ cd airflow-bucket
$ zip -r dags.zip dags 
```
which will create a zip with a directory structure as follows

```
 dags
  └── example-hello.py
```

Once we have this file, we can upload this to your MWAA airflow bucket. You can change this when you use this yourself in the CloudFormation script (lines 34/35 in the template)

```
aws s3 cp dags.zip s3://{mwaa-dag-folder}
``` 

We can now modify the parameters file to suit our environment. In this example, I am going to use the following variables which represent my environment: AWS Region is eu-north-1, MWAA environment name is going to be airflow-blog-stock, my MWAA S3 dag folder is airflow-blog-stock-cicd.

In the parameter file you will only use the dag folder being needed. The other values (CodeCommitRepoName, CodePipelineName and CodeBuildProjectName) you can change to values you typically use.

```
[
    {
      "ParameterKey": "s3BucketName",
      "ParameterValue": "airflow-blog-stock-cicd"
    }, 
    {
      "ParameterKey": "CodeCommitRepoName",
      "ParameterValue": "airflow-stock-repo-demo"
    },
    {
      "ParameterKey": "CodePipelineName",
      "ParameterValue": "airflow-stock-pipe-demo"
    },
    {
      "ParameterKey": "CodeBuildProjectName",
      "ParameterValue": "airflow-stock-buildprj-demo"
      }
]
```

Once you have saved that, you are ready to go. You should not need to modify the CloudFormation template. To deploy, use the following command, replacing the values in { } with your preferred values.

```
aws cloudformation create-stack --stack-name {your-cf-stack-name} --template-body file://create-cicd-simple.yaml --parameters file://mwaa-cfn-cicd-parameters.json --capabilities CAPABILITY_IAM --capabilities CAPABILITY_NAMED_IAM --region={MWAA supported AWS region}
```

When you run this, you should see the following output

```
{
    "StackId": "arn:aws:cloudformation:{aws-region}:{aws-account-id}:stack/{your-cf-stack-name}/b7255750-65f6-11eb-b32a-06106702d484"
}
```
And if you go into the AWS CloudFormation console, you should see this stack being created. It should only take around 3-5 minutes to complete. If you run the following command, you should see all the resources that have been created.

```
aws cloudformation describe-stack-resources --stack-name {your-cf-stack-name} --region={MWAA supported AWS region}
```

You should see something like the following:

```
{
    "StackResources": [
        {
            "StackName":{aws-mwaa-region} "{cf stack name}",
            "StackId": "arn:aws:cloudformation:{aws-mwaa-region}:{aws-account-id}:stack/{cf stack name}/b7255750-65f6-11eb-b32a-06106702d484",
            "LogicalResourceId": "ArtifactStoreBucket",
            "PhysicalResourceId": "{cf stack name}-artifactstorebucket-1me3gxwb6p2p",
            "ResourceType": "AWS::S3::Bucket",
            "Timestamp": "2021-02-03T08:06:54.421Z",
            "ResourceStatus": "CREATE_COMPLETE",
            "DriftInformation": {
                "StackResourceDriftStatus": "NOT_CHECKED"
            }
        },
        {
            "StackName": "{cf stack name}",
            "StackId": "arn:aws:cloudformation:{aws-mwaa-region}:{aws-account-id}:stack/{cf stack name}/b7255750-65f6-11eb-b32a-06106702d484",
            "LogicalResourceId": "CodeBuildProject",
            "PhysicalResourceId": "airflow-stock-buildprj-demo",
            "ResourceType": "AWS::CodeBuild::Project",
            "Timestamp": "2021-02-03T08:07:21.691Z",
            "ResourceStatus": "CREATE_COMPLETE",
            "DriftInformation": {
                "StackResourceDriftStatus": "NOT_CHECKED"
            }
        },
        {
            "StackName": "{cf stack name}",
            "StackId": "arn:aws:cloudformation:{aws-mwaa-region}:{aws-account-id}:stack/{cf stack name}/b7255750-65f6-11eb-b32a-06106702d484",
            "LogicalResourceId": "CodeBuildRole",
            "PhysicalResourceId": "{cf stack name}-CodeBuildRole-1LG9K7WF8BICD",
            "ResourceType": "AWS::IAM::Role",
            "Timestamp": "2021-02-03T08:07:17.347Z",
            "ResourceStatus": "CREATE_COMPLETE",
            "DriftInformation": {
                "StackResourceDriftStatus": "NOT_CHECKED"
            }
        },
        {
            "StackName": "{cf stack name}",
            "StackId": "arn:aws:cloudformation:{aws-mwaa-region}:{aws-account-id}:stack/{cf stack name}/b7255750-65f6-11eb-b32a-06106702d484",
            "LogicalResourceId": "CodeCommitRepository",
            "PhysicalResourceId": "cb101164-7647-42a1-a0a1-6c734eee2bfd",
            "ResourceType": "AWS::CodeCommit::Repository",
            "Timestamp": "2021-02-03T08:06:34.719Z",
            "ResourceStatus": "CREATE_COMPLETE",
            "DriftInformation": {
                "StackResourceDriftStatus": "NOT_CHECKED"
            }
        },
        {
            "StackName": "{cf stack name}",
            "StackId": "arn:aws:cloudformation:{aws-mwaa-region}:{aws-account-id}:stack/{cf stack name}/b7255750-65f6-11eb-b32a-06106702d484",
            "LogicalResourceId": "CodePielineEventExeRole",
            "PhysicalResourceId": "{cf stack name}-CodePielineEventExeRole-QZZZ03I2NTFS",
            "ResourceType": "AWS::IAM::Role",
            "Timestamp": "2021-02-03T08:06:53.046Z",
            "ResourceStatus": "CREATE_COMPLETE",
            "DriftInformation": {
                "StackResourceDriftStatus": "NOT_CHECKED"
            }
        },
        {
            "StackName": "{cf stack name}",
            "StackId": "arn:aws:cloudformation:{aws-mwaa-region}:{aws-account-id}:stack/{cf stack name}/b7255750-65f6-11eb-b32a-06106702d484",
            "LogicalResourceId": "CodePipelinePipeline",
            "PhysicalResourceId": "airflow-stock-pipe-demo",
            "ResourceType": "AWS::CodePipeline::Pipeline",
            "Timestamp": "2021-02-03T08:06:57.951Z",
            "ResourceStatus": "CREATE_COMPLETE",
            "DriftInformation": {
                "StackResourceDriftStatus": "NOT_CHECKED"
            }
        },
        {
            "StackName": "{cf stack name}",
            "StackId": "arn:aws:cloudformation:{aws-mwaa-region}:{aws-account-id}:stack/{cf stack name}/b7255750-65f6-11eb-b32a-06106702d484",
            "LogicalResourceId": "PipelineRole",
            "PhysicalResourceId": "{cf stack name}-PipelineRole-1MIR8Y4TZRCTB",
            "ResourceType": "AWS::IAM::Role",
            "Timestamp": "2021-02-03T08:06:53.984Z",
            "ResourceStatus": "CREATE_COMPLETE",
            "DriftInformation": {
                "StackResourceDriftStatus": "NOT_CHECKED"
            }
        }
    ]
}
```

This will set everything up, and if you go to the AWS CodePipeline console, you should be able to see your simple CI/CD pipeline.

![screen](https://raw.githubusercontent.com/094459/innovateaiml-airflow/main/images/cicd-screen.png)

Now the first time you go to this console, you might see the build fail. Don't worry, if you click on the Retry it should complete successfully. (and I will be looking into this to see if I can fix the template to see if this is expected behaviour or a problem with this template)


**Testing this within our developer environments**

Now that we have this setup, lets test this setup using a number of typical developer scenarios you might have.

To get details of the AWS CodeCommit repository details, we use the following command to find the list of repositories.

```
aws codecommit list-repositories --region={region}
```

and then use this command once you know the repository name

```
aws codecommit get-repository --repository-name --region={region}
```
which will display useful information, including the cloneURL

```
{
    "repositoryMetadata": {
        "accountId": "{aws-account-id}",
        "repositoryId": "c4a4ac66-6bfc-419c-a145-bbb0a4606a05",
        "repositoryName": "{repo-name}",
        "defaultBranch": "main",
        "lastModifiedDate": 1612343158.702,
        "creationDate": 1610969080.447,
        "cloneUrlHttp": "https://git-codecommit.{aws-region}.amazonaws.com/v1/repos/{repo-name}",
        "cloneUrlSsh": "ssh://git-codecommit.{aws-region}.amazonaws.com/v1/repos/{repo-name}",
        "Arn": "arn:aws:codecommit:{aws-region}:{aws-account-id}:{repo-name}"
    }
}
```

So now we have the repo URL, we can check out the project into our development environment and begin working.

**Git**

From my developer laptop, I open up my preferred shell and use the following command to check out the repository


```
mkdir airflow-cicd
cd airflow-cicd
git clone https://git-codecommit.eu-north-1.amazonaws.com/v1/repos/airflow-stock-repo-demo

```

I will get the normal output

```
Cloning into 'airflow-stock-repo-demo'...
remote: Counting objects: 8, done.
Unpacking objects: 100% (8/8), done.
```

And you can see that I have the following directory structure

```
└── airflow-stock-repo-demo
    └── dags
        ├── db_cleanup.py
        └── example-params.py
```

I am going to create a test file, using an example dag file that is a simple HelloWorld dag (file called hello-world.py)

```
└── airflow-stock-repo-demo
    └── dags
        ├── db_cleanup.py
        ├── example-params.py
        └── hello-world.py
```

If we look at the current DAGs folder that the MWAA environment has deployed, we can see the following (with my MWAA Airflow dags folder configured to the one here, yours will be different):

```
aws s3 ls s3://airflow-blogpostdemo-stock/dags/
```

And we can see we get the following:

```
2021-02-03 10:06:43       2890 db_cleanup.py
2021-02-03 10:06:43       2222 example_params.py
```

If we now commit the new file using standard git commands.

```
git add .
git commit -m "adding hellow-world.py"
git push
```
Which should show something like this

```
Enumerating objects: 6, done.
Counting objects: 100% (6/6), done.
Delta compression using up to 12 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (4/4), 308 bytes | 308.00 KiB/s, done.
Total 4 (delta 1), reused 0 (delta 0)
To https://git-codecommit.eu-north-1.amazonaws.com/v1/repos/airflow-stock-repo-demo
   f895090..1577b18  main -> main
```

when we re-run the following command

```
aws s3 ls s3://airflow-blogpostdemo-stock/dags/
```

And we can see we get the following:

```
2021-02-03 10:06:43       2890 db_cleanup.py
2021-02-03 10:06:43       2222 example_params.py
2021-02-03 10:06:43       122 hello-world.py

```

What just happened?

The commit in the source code repository triggered an event which in turn triggered the AWS CodePipeline pipeline. That pipeline checks out the code repository locally and then does an aws s3 sync to our target folder, in this case the DAGS target folder.

**Apache Airflow UI**

The new file will now appear in the MWAA environment you have been using, although it might take a minute or two. The process that is going on in the background is that the MWAA S3 bucket is synced on a regular basis with the DAGS folder of your Apache Airflow environment, and this is done typically every 30 seconds.

If your DAG is written correctly and well formed, it should show up. However, when I was developing some test DAGs I would often commit my change, and then I would see various error messages appear on the Apache Airflow UI. If this happens, then make sure that you a) enable logging, and b) check out the CloudWatch logs to find out more information as to the issue. We will look at monitoring and logging in the next post.

**Other developer environments**

I have tested this setup using VSCode (my standard IDE) as well as AWS Cloud9 (my preferred IDE) and these steps works the same way. If you are using the VSCode git plugin it is super easy to work with your AWS CodeCommit repository.

**Other Source Code repositories**

During this demo I used AWS CodeCommit as the source repository, but what about if you were using something different like Bitbucket, GitHub or perhaps GitHub Enterprise.

You can set these up, but you will not be able to use the sample templates I have provided. Some of the integration will need to be done via the AWS console, so check out the documentation around [Bitbucket](https://docs.aws.amazon.com/codepipeline/latest/userguide/connections-bitbucket.html), [GitHub](https://docs.aws.amazon.com/codepipeline/latest/userguide/connections-github.html) and G[itHub Enterprise](https://docs.aws.amazon.com/codepipeline/latest/userguide/connections-ghes.html).

Once you follow these steps, you should still be able to automate the triggering of the "build" stage, which is syncing with your MWAA DAG folder.

**Deleting**

In the above configuration, deletes will not sync to your DAGS folder on Amazon S3. If you want to enable this, then you need to do a couple of things:

First, you need to adjust the permissions policy to allow permissions for the CodePipeline/Build execution role to have s3 Delete privileges.
Second, you need to change the command to append the "--delete" which will delete files that are not in the source. So if we use the example above, your build command would be 

```
- aws s3 sync . s3://${s3BucketName}/ --exclude "plugin-src/* --delete"
```

**Plugins**

One of the really nice things about Apache Airflow is the ability to extend the functionality and cater for anything more specific you might need to do. This could be for example, creating a custom operator for an internal system you need to interact with. You can read more about how MWAA supports this here, [Installing custom plugins](https://docs.aws.amazon.com/mwaa/latest/userguide/configuring-dag-import-plugins.html). 

We can quickly change the setup so that it packages and deploys your plugins.zip file. Lets say you had this layout in your repository, and you have developed your custom plugin within the plugins-src folder

```
└── airflow-stock-repo-demo
    └── dags
        ├── db_cleanup.py
    └─  plugins-src
            		├-__init__.py
						└-my_airflow_plugin.py
						└-hooks/
 						   	|-- __init__.py
						   	|-- my_airflow_hook.py
						└-operators/
 						   	|-- __init__.py
						   	|-- my_airflow_operator.py
						└-sensors/
    							|-- __init__.py
    							|-- my_airflow_sensor.py
	 ├── requirements.txt
	 └── plugins.zip
```

We can modify the build command to include packaging this up as a zip file and then deploying this using the following

```
...
              BuildSpec: !Sub |
                version: 0.2
                phases:
                  build:
                    commands:
                      - cd plugin-src
                      - chmod -R 755 .
                      - zip -r plugins.zip .
                      - aws s3 cp plugins.zip s3://${s3BucketName}/
                      - rm plugins.zip
                      - cd ..
                      - aws s3 sync . s3://${s3BucketName}/ --exclude "plugin-src/*"
...
```

If you have already deployed the template, you can go to the CodeBuild stage and edit the build command directly. (feel free to change the folder structure to whatever suits your needs/requirements)

This will now take the code it finds in the plugin-src, zip it up and then deploy it to the root folder. It specifically excludes the source file when moving the content to the MWAA Dags folders with the --exclude.  With this setup, you would then need to configure the MWAA environment to use this plugin.zip file if you had not already done so. As you update/change the plugin.zip file, this will create a new version of the file rather than replace it. This means that even if you restart your MWAA environment, it will still point to the old file. You will need to update the plugins.zip file that your environment points to.

```
aws s3api list-object-versions --bucket {plugin-folder} --prefix plugins.zip
```

which will give you something like (in this example, I have two versions of the plugins.zip file)

```
{
    "Versions": [
        {
            "ETag": "\"4091a3ef43ca1a5d37353dae745c6eb6\"",
            "Size": 4916,
            "StorageClass": "STANDARD",
            "Key": "plugins.zip",
            "VersionId": "1yzdinP0EnHNLe9LF6zWSpUbiX5aYqhY",
            "IsLatest": true,
            "LastModified": "2021-02-17T18:06:14.000Z",
            "Owner": {
                "DisplayName": "ricsue",
                "ID": "de88fb921565d9a1fb139460924e49f5286d7c2fa6499a685c257f9315db8a7c"
            }
        },
        {
            "ETag": "\"813a3e1b6cb7e750bad322ed09d7426f\"",
            "Size": 5116,
            "StorageClass": "STANDARD",
            "Key": "plugins.zip",
            "VersionId": "fTNV1wTeB9.0HrI9SKo_iR_f751Vs1Ac",
            "IsLatest": false,
            "LastModified": "2021-02-17T17:18:43.000Z",
            "Owner": {
                "DisplayName": "ricsue",
                "ID": "de88fb921565d9a1fb139460924e49f5286d7c2fa6499a685c257f9315db8a7c"
            }
        }
    ]
}
```

To see the current version you are using, use the following command:

```
aws mwaa get-environment --name {mwaa-environment} | jq -r '.Environment | .PluginsS3ObjectVersion'
```

which will get you the current version that is being used, in my example I get the following output.

```
fTNV1wTeB9.0HrI9SKo_iR_f751Vs1Ac
```

Which you can see from the previous output is not the latest version of the plugins.zip file (that is "1yzdinP0EnHNLe9LF6zWSpUbiX5aYqhY"). I can fix that by running the following command:

```
aws mwaa update-environment --plugins-s3-object-version "1yzdinP0EnHNLe9LF6zWSpUbiX5aYqhY" --name {your-mwaa-environment}
```

which will output something like this

```
{
    "Arn": "arn:aws:airflow:eu-west-1:xxxxxxxxxx:environment/{your-mwaa-env}"
}
```

This will update and then update the environment - so this can take around 10-15 minutes to complete. Go and grab a cup of tea. When we run the previous command to see the status of the environment,

```
aws mwaa get-environment --name {mwaa-environment} | jq -r '.Environment | .RequirementsS3ObjectVersion'
```
We should now see the latest version being used.

```
V6.0mTeeI0v4ctTubAgvNrGqIdj3b4LV
```

**Requirements.txt**

As this is a static file, you could use the existing approach and ensure that your directory structure is such that it syncs both the DAGS folder and the requirements.txt file to the target MWAA Dags folder to the corresponding locations.

So for example, if you MWAA environment has something like this:

```
└── airflow-stock-repo-demo
    └── dags
        ├── db_cleanup.py
	 └── requirements.txt
```

You would set your folder structure in the code repository to match this, and the requirements.txt file would sync every time you updated it.

One thing that caught me out here was that because the requirements.txt file is uploaded/overwrites your existing file, and it is a versioned bucket, the process of doing this will not automatically update the configuration within your MWAA environment. You can use the aws cli to output all the versions of the file, using a command like (I am assuming here you have a folder called requirements and your requirements.txt file in located there - if yours is different, adjust accordingly):

```
aws s3api list-object-versions --bucket {your S3 bucket where the requirements.txt is} --prefix requirements/requirements.txt
``` 

Which gives you this output - yours will be different:

```
...

    "Versions": [
        {
            "ETag": "\"20945e5c4596619a7e8c94150b715e60\"",
            "Size": 54,
            "StorageClass": "STANDARD",
            "Key": "requirements/requirements.txt",
            "VersionId": "V6.0mTeeI0v4ctTubAgvNrGqIdj3b4LV",
            "IsLatest": true,
            "LastModified": "2021-02-17T15:04:08.000Z",
            "Owner": {
                "DisplayName": "ricsue",
                "ID": "de88fb921565d9a1fb139460924e49f5286d7c2fa6499a685c257f9315db8a7c"
            }
        },
        {
            "ETag": "\"538aa1a28441582eb0dfff30e76cbae5\"",
            "Size": 48,
            "StorageClass": "STANDARD",
            "Key": "requirements/requirements.txt",
            "VersionId": "glbJdJ06NTvd48pohr9wuUTZ3z7Rg4KC",
            "IsLatest": false,
            "LastModified": "2021-02-17T14:37:53.000Z",
            "Owner": {
                "DisplayName": "ricsue",
                "ID": "de88fb921565d9a1fb139460924e49f5286d7c2fa6499a685c257f9315db8a7c"
            }
        },
...
```

Now it is the versionId that you need to use. In the above example, I have just updated my requirements.rxt file. If I run the following command:

```
aws mwaa get-environment --name {mwaa-environment} | jq -r '.Environment | .RequirementsS3ObjectVersion'
```

I get the following output

```
glbJdJ06NTvd48pohr9wuUTZ3z7Rg4KC
```

Which you can see from the previous output is not the latest version of the requirements.txt file (that is "V6.0mTeeI0v4ctTubAgvNrGqIdj3b4LV"). I can fix that by running the following command:

```
aws mwaa update-environment --requirements-s3-object-version "V6.0mTeeI0v4ctTubAgvNrGqIdj3b4LV" --name {your-mwaa-environment}
```

which will output something like this

```
{
    "Arn": "arn:aws:airflow:eu-west-1:xxxxxxxxxxxx:environment/{mwaa-env}"
}
```

This will update and then update the environment - so this can take around 10-15 minutes to complete. Go and grab a cup of tea. When we run the previous command to see the status of the environment,

```
aws mwaa get-environment --name {mwaa-environment} | jq -r '.Environment | .RequirementsS3ObjectVersion'
```
We should now see the latest version being used.

```
V6.0mTeeI0v4ctTubAgvNrGqIdj3b4LV
```

**Some things to take into consideration**

A couple of things to bear in mind when implementing a simple CI/CD workflow like this in MWAA.

* updates to the requirements.txt and plugin.zip files will require that you update your environment to re-load these changes. They are not automatically re-loaded. You can do this using the "aws mwaa update-environment --name {environment}" command but be aware you will need to update the version of the requirements.txt and plugin.zip file
* with this sample workflow I have simplified the directory layout and structure - you can easily change this to suit your own needs, just update the corresponding template
* this IS a super simple workflow and you probably need to do some more work to make it something you can use. Some suggestions would include adding a build stage to run tests of your workflows, or perhaps staging deployments to different environments. I will come back in a future post and take a look at these

**Deleting the CI/CD setup**

If you are just using this post to understand how this works, and you no longer need the environment then you can easily remove the setup using the following commands. Bear in mind this will destroy all resources, including the CodeCommit environment, so makes copies/backups of anything you want to keep.

```
aws cloudformation delete-stack --stack-name {your stack name} --region={aws-region}
```

This command will not generate any output so you will need to go to the CloudFormation console as this will generate an error - don't worry. You just need to delete the Amazon S3 Artefact bucket, which this process will not do. Once you have done that, re-run the command and it should remove the environment stack from your CloudFormation console.

**Conclusion**

This concludes the fifth post. You will now be able to setup a simple automated workflow that will help you accelerate your developers whilst reducing the permissions and access you need to give those developers to your MWAA environments. I will come back in a future post and look at more complex pipelines and how you can integrate testing and staged deployments.

In the next post we will look at monitoring and logging, which will help you troubleshoot issues with your Apache Airflow environment and the DAGs you are developing. It will also help you understand over time how your environments are running, a look at resources and capacity and help you optimise your costs to make sure you are right-sizing your environment.

If there is specific content you want to see, please get in touch.
