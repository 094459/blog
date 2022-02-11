---
title: 'Contributing to the Apache Airflow project - Part One'
date: '2022-02-10'
tags: [ blog, Apache Airflow]
---

### Contributing to Apache Airflow

#### Introduction

In this series of posts, I am going to share what I learn as embark on my first upstream contribution to the Apache Airflow project. The purpose is to show you how typical open source projects like Apache Airflow work, how you engage with the community to orchestrate change and hopefully inspire more people to contribute to this open source project. I will post regular updates as a series of posts, as the journey unfolds.

But as always, we need to set the stage and start with our reason for doing so.

**The problem**

In a previous post ([Creating a multi architecture CI/CD solution with Amazon ECS and ECS Anywhere](https://dev.to/aws/creating-a-multi-architecture-ci-cd-deployment-for-amazon-ecs-and-ecs-anywhere-15o3)) I set up a typical environment that you might come across with customers that are looking at a Hybrid approach to managing and deploying their workloads. This allows you to run container images anywhere where you can deploy the ECS Anywhere agent, and uses a specific configuration parameter (launchtype="EXTERNAL") in order to know where to run your container "Tasks". More of this in a moment. 

In this environment, I have various data silos that reside in both my AWS environment, and on my local network. In this instance, it is a MySQL database, and the MySQL database contains different data across the two environments. 

As part of building out my data lake on Amazon S3, I am pulling data from both these environments. However, in my particular use case, I want to be able to control what data is moved to the data lake.

My solution was to use Apache Airflow and create a new workflow to orchestrate this. I planned to [create an ETL script](https://github.com/094459/blogpost-airflow-hybrid/blob/main/docker/app/read-data-q.py), and ensure the script can take parameters, to maximise reuse and flexibility.

```
FROM  public.ecr.aws/docker/library/python:latest

WORKDIR /app

COPY requirements.txt requirements.txt
RUN pip3 install -r requirements.txt

COPY . .

ENTRYPOINT [ "python3", "app/read-data-q.py" ]
```

Before testing this in Apache Airflow, I package up the container image, push it up to Amazon ECR and then test that it runs from the command. You can [find the code here](https://github.com/094459/blogpost-airflow-hybrid/tree/main/docker). 

Now that I have my ETL script, I can use an Apache Airflow operator that integrates with Amazon ECS to orchestrate this. That operator is called the ECS Operator. The ECS Operator takes a number of parameters. One of the key ones is "launchtype" (as mentioned before, this is how the ECS control plane knows where to run your tasks. Reading the docs, the two supported launchtypes for this Apache Airflow operator are "EC2" and "FARGATE". We know that there is a third launchtype of "EXTERNAL", but that does not appear to be listed in the docs.

This is the simple workflow we create just to test how it works.

```
from airflow import DAG
from datetime import datetime, timedelta
from airflow.providers.amazon.aws.operators.ecs import ECSOperator


default_args = {
    'owner': 'ubuntu',
    'start_date': datetime(2019, 8, 14),
    'retry_delay': timedelta(seconds=60*60)
}

with DAG('airflow_dag_test', catchup=False, default_args=default_args, schedule_interval=None) as dag:
    query_db = ECSOperator(
    task_id="airflow-hybrid-ecs-task-query",
    dag=dag,
    cluster="test-hybrid",
    task_definition="airflow-hybrid-ecs-task:3",
    launch_type="EXTERNAL",
    overrides={
        "containerOverrides": [
            {
                "name": "public.ecr.aws/a4b5h6u6/beachgeek:latest",
                "command" : ["ricsue-airflow-hybrid", "temp.csv", "select 1 from customers", "rds-airflow-hybrid", "eu-west-2"],
            },
        ],
    },
    awslogs_group="/ecs/hyrid-airflow",
    awslogs_stream_prefix="ecs"
    )

    test = ECSOperator(
    task_id="test",
    dag=dag,
    cluster="test-hybrid",
    task_definition="test",
    launch_type="EXTERNAL",
    overrides={
        "containerOverrides": [ ],
    },
    awslogs_group="/ecs/test",
    awslogs_stream_prefix="ecs",
    )

    test
```

I first create an ECS Cluster running on EC2, set the launchtype to "EC2" and the trigger the DAG. As expected, the ECS task takes the parameters and runs the script, exporting a file to my Amazon S3 bucket. All good, I know this works.

Next I change the DAG, setting the launchtype of "EXTERNAL" results in an error when triggering the workflow as follows:

```
[2022-02-01, 19:59:35 UTC] {{taskinstance.py:1280}} INFO - Marking task as FAILED. dag_id=airflow_dag_test, task_id=test, execution_date=20220201T195932, start_date=20220201T195934, end_date=20220201T195935
[2022-02-01, 19:59:35 UTC] {{standard_task_runner.py:91}} ERROR - Failed to execute job 34 for task test
...
airflow.providers.amazon.aws.exceptions.ECSOperatorError: {'tasks': [], 'failures': [{'arn': 'arn:aws:ecs:eu-west-2:704533066374:container-instance/cc99805fa0024cc1a17416dfd7b8198c', 'reason': 'LAUNCH_TYPE'}], 'ResponseMetadata': {'RequestId': 'dec18db7-9fd7-471f-bfd7-1a88fc9dda89', 'HTTPStatusCode': 200, 'HTTPHeaders': {'x-amzn-requestid': 'dec18db7-9fd7-471f-bfd7-1a88fc9dda89', 'content-type': 'application/x-amz-json-1.1', 'content-length': '145', 'date': 'Tue, 01 Feb 2022 19:59:35 GMT'}, 'RetryAttempts': 0}}
[2022-02-01, 19:59:35 UTC] {{local_task_job.py:154}} INFO - Task exited with return code 1

```
We can see that the LAUNCH_TYPE is the reason for the failure.

So, it looks like the ECS Operator currently does not support the "launchtype" value of "EXTERNAL". Oh well, at least we tried.

**Workaround**

Using Apache Airflow operators is my preferred way of interacting with downstream applications and services when building my workflows. They remove a lot of the differentiated heavy lifting, but they can also improve the performance and stability of your workflows.

Given we cannot use the ECS Operator, I fall back to creating a simple Python operator which uses boto3 to do the same thing.

```
from airflow import DAG
from datetime import datetime, timedelta
from airflow.operators.python import PythonOperator
import boto3
import json

default_args = {
    'owner': 'ubuntu',
    'start_date': datetime(2019, 8, 14),
    'retry_delay': timedelta(seconds=60*60)
}


client = boto3.client("ecs", region_name="eu-west-2")

# Function that will take variables and create our new ECS Task Definition
def create_task(ti):
    response = client.register_task_definition(
        containerDefinitions=[
            {
                "name": "airflow-hybrid-boto3",
                "image": "public.ecr.aws/a4b5h6u6/beachgeek:latest",
                "cpu": 0,
                "portMappings": [],
                "essential": True,
                "environment": [],
                "mountPoints": [],
                "volumesFrom": [],
                "command": ["ricsue-airflow-hybrid","period1/temp.csv", "select * from customers WHERE location = \"China\"", "rds-airflow-hybrid","eu-west-2"],
                "logConfiguration": {
                    "logDriver": "awslogs",
                    "options": {
                        "awslogs-group": "/ecs/test-external",
                        "awslogs-region": "eu-west-2",
                        "awslogs-stream-prefix": "ecs"
                    }
                }
            }
        ],
        taskRoleArn="arn:aws:iam::704533066374:role/ecsTaskExecutionRole",
        executionRoleArn="arn:aws:iam::704533066374:role/ecsTaskExecutionRole",
        family= "test-external",
        networkMode="bridge",
        requiresCompatibilities= [
            "EXTERNAL"
        ],
        cpu= "256",
        memory= "512") 

        # we now need to store the version of the new task so we can ensure idemopotency

    new_taskdef=json.dumps(response['taskDefinition']['revision'], indent=4, default=str)
    print("TaskDef is now at :" + str(new_taskdef))
    return new_taskdef
    #ti.xcom_push(key='new_taskdef', value=new_taskdef)

# Function that will run our ECS Task
def run_task(ti):
    #new_taskdef=ti.xcom_pull(key='new_taskdef', task_ids=['create_taskdef'][0])
    new_taskdef=ti.xcom_pull(task_ids=['create_taskdef'][0])
    print("TaskDef passed is :" + str(new_taskdef))
    response2 = client.run_task(
        cluster='test-hybrid',
        count=1,
        launchType='EXTERNAL',
        taskDefinition='test-external:{taskdef}'.format(taskdef=new_taskdef)
)

with DAG('airflow_ecsanywhere_boto3', catchup=False, default_args=default_args, schedule_interval=None) as dag:
    first_task=PythonOperator(task_id='create_taskdef', python_callable=create_task, provide_context=True, dag=dag)
    second_task=PythonOperator(task_id='run_task', python_callable=run_task, provide_context=True, dag=dag)

    first_task >> second_task
```
**Ownership**

Whilst this works, I begin to think that maybe I can fix the ECS Operator and add the new "launchtype" of "EXTERNAL". I mean, how hard can it be?

> One of the underpinning principals that makes open source tick is that when you identify a problem (like the one I have just described) that you don't just look for someone else to fix it. If you are getting value out of that software, then you need to take ownership of the issue, and look for a resolution. It maybe that you are not a coder, and perhaps do not have the technical skills needed, but that is not an excuse. Whether it is in helping to describe and help triage the issue, providing support and resources for those more technical that can do a fix, through to your involvement in the end resolution - you need to take ownership.

Why mention this? I want sure that any (my) contribution is anchored in a strong foundation. In this instance, improving how the current ECS operator works will optimise how I can use and integrate ETL tasks that I want to run via Amazon ECS.

> **Plan**
> I work best when I have a plan, and I am not sure if this is the best or right plan (please let me know) but the plan I have is to initially get the latest stable code of Apache Airflow up and running in my development environment. Once that is working, the next step is to understand in more detail how the ECS Operator code works, and then make some minor changes to make sure I understand the flow from making a change to then how that changes flows into the final build. Once I have got there, I will hopefully have a better understanding of how to make changes, and how to incorporate those within the parameters of this project.
> 
> 

#### Am I allowed to contribute?

**Organisational policies**

(I am assuming you work for a company, but if you are an individual contributor I guess this does not apply so you can skip this section)

Before jumping into looking at how I fix this issue, the first step was for me to understand how my organisation feels about me doing so. Many organisations now have an open source usage and contribution policy, and these are typically created by and owned/managed by the Open Source Program Office (or OSPO).

In my case, we have clearly defined policies and guidance that helps our technical communities understand how and what they can do. You should use this as an opportunity to understand more about your own organisations policies. If you find these hard to find, or perhaps you do not yet have an OSPO, then maybe you should explore whether the time is right for you do look into this - when you look at the various data points, it is very likely you are using open source software within your business. Make sure that you have the right setup to make open source work for you - something an OSPO will absolutely help you with.

Anyway, a small diversion, but an important one. If you work for a business, being able and supported in how you contribute to the open source software you use is critical to the long term sustainability of the open source commons.

#### Contribution - the first step

**Reviewing the Contribution file**

With permission granted, the first step is to head over to the Apache Airflow project and look for information on how to contribute. It is a good practice to create a [CONTRIBUTING](https://github.com/apache/airflow/blob/main/CONTRIBUTING.rst) document in your project to help guide new contributors as well as ensure consistency for those who might already be familiar. 

Apache Airflow has a detailed [CONTRIBUTING](https://github.com/apache/airflow/blob/main/CONTRIBUTING.rst) guide, as well as a guide for new contributors. This is actually great as there is a lot of stuff in here, and it looks like it is the product of lots of lessons learned so I did take some time to review this.

**Reaching out to the project**

The contributors page also mentions about getting support from the existing Apache Airflow community. I am already part of the Apache Airflow slack channel (if you have not joined this, then please do - it is a really great community of like minded builders helping each other out) and so reached out to Jarek Potiuk, one of the maintainers. He was quick to respond and encourage me on this adventure, ensuring that if I run into any problems he would be happy to help. Internally, I reached out within our own Apache Airflow community, and had another builder, Mark Richman reach out to join in this adventure. We were provided some useful guidance from existing internal contributors to the project, and this is even before we have made any code changes. 

**Creating our issue**

The first step, as with many open source projects is to create an issue within the GitHub repository. Here is the issue I created,[ ECS Operator does not support launch type "EXTERNAL"](https://github.com/apache/airflow/issues/21321). Some observations from this:

* When writing the issue, I tried to put as much context about the problem as possible. I spend a lot of time reading other issues, and I find it helpful when people provide the problem as well as the context.
* The issue is kind of an audit log of all the conversations and discussions around the problem you have raised. Often, the CONTRIBUTING guides will provide additional info on what they expect you to include here.
* Once the issue was created, I reached out to Jarek, who assigned the issue to Mark and myself. We are now owners of this issue.

The project provides an [overview of the contribution workflow](https://github.com/apache/airflow/blob/main/CONTRIBUTING.rst#contribution-workflow), which makes it very easy to understand how you are expected to work.

![workflow](https://github.com/apache/airflow/blob/main/images/workflow.png?raw=true)

Having created the issue, the next step is to fork the project and build locally.

> I did skip ahead a little, and joined the devlist (as I already was part of the Slack channel). To do this, incase it is not obvious (it was not to me) you just send a blank email to that address, and then when they send you a reply, you just need to confirm with a final response. Once done, you will now be part of the Apache Airflow dev mailing list. You can find out more [here](https://aijamalnk.github.io/airflow-website/community/contact-us/).

#### Forking the project 

**Forking**

Forking Apache Airflow is simple enough, as GitHub makes this as simple as a couple of clicks. I now have my own [Apache Airflow fork](https://github.com/094459/airflow) for for this work. The only thing I needed to make sure was that it was the right branch (latest, main) and not any of the other branches (I have made that mistake before!)

**Getting my local development environment ready**

The next step is to setup my local developer environment so I can actually build the project from source. The documentation provides some guidance here, and it looks like there are [two approaches](https://github.com/apache/airflow/blob/main/CONTRIBUTING.rst#development-environments). The doc provides some nice guidance here, with some of the differences to be aware of. This is where I found out having the discussion with existing contributors to the project was super helpful as they provided more opinionated guidance to what is in the docs. I am going to go with [setting up the Breeze environment](https://github.com/apache/airflow/blob/main/BREEZE.rst#docker-community-edition).

This also got me thinking more practically - where am I actually going to do the development? I have my trusty Macbook, which certainly has enough grunt to do the job. But do I really want to do that there?  What other options do I have? I try and do all my work in my AWS Cloud9 environment, as I find it a really nice way to have everything I need centred around a specific activity. I could also potentially spin up a virtual desktop, I have an Amazon Linux virtual desktop, which provides a much more flexible environment and would allow me to deploy a lot of the standard tools I use on my Macbook. It is probably worth thinking before you proceed about what will work best for your workflow.

In the end I decided that I would experiment with the AWS Cloud9 environment, so am going to try that out. I have set myself up a custom instance type, as I notice that in the doc it says that the Breeze setup uses "uses GBs of disk and many CPUs" - I am going to start off with m5.xlarge which will give me 16GB ram and 4 vCPUs. I also noticed that a lot of the documentation and the docker files are using the debian package format, so will go with Ubuntu for the OS rather than the default of Amazon Linux 2. The only thing I need to do is increase the disk space for my Cloud9 environment, which is easy enough with this script (which will increase the volume size to 50GB).

```
pip3 install --user --upgrade boto3
export instance_id=$(curl -s http://169.254.169.254/latest/meta-data/instance-id)
python3 -c "import boto3
import os
from botocore.exceptions import ClientError 
ec2 = boto3.client('ec2')
volume_info = ec2.describe_volumes(
    Filters=[
        {
            'Name': 'attachment.instance-id',
            'Values': [
                os.getenv('instance_id')
            ]
        }
    ]
)
volume_id = volume_info['Volumes'][0]['VolumeId']
try:
    resize = ec2.modify_volume(    
            VolumeId=volume_id,    
            Size=50
    )
    print(resize)
except ClientError as e:
    if e.response['Error']['Code'] == 'InvalidParameterValue':
        print('ERROR MESSAGE: {}'.format(e))"
if [ $? -eq 0 ]; then
    sudo reboot
fi
```

This only took a few minutes to provision and now I have a blank canvas on which to proceed. I took a look at the pre-req's and needed to install jq, docker-compose, coreutils (which for some reason didn't create the sym link for gstat) and I was ready to go.

> To install docker-compose, I originally used apt-get but this installed an older version (1.17) so ran the following command 
> ```sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose```
> and then ensured that it was earlier in the path so this newer version was picked up

The final thing I did to complete my AWS Cloud9 setup was to update the AWS cli to v2 using the following

```
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
```

And then update the credentials that AWS Cloud9 uses, and then using my standard .aws credentials. (either by copying your .aws config files or running aws configure)

> **Virtual Desktop**
> 
> Whilst I was troubleshooting an issue with running the tests above, I tried using Amazon Workspaces to spin up a virtual desktop (Amazon Linux 2) and tried the same process as above. It worked pretty much the same, except that it uses yum vs apt. Also, a lot of the stuff is already installed, so the only thing I needed to do was
> 
> * Install the aws cli v2 (same as above)
> * Install docker-compse (same as above, although I needed to set the executable bit - chmod +x)
> * I needed to start docker by changing to root and then using "service docker start"
> * Still as root, I could then start Breeze as normal


**Running Breeze for the first time**

The next step was to actually clone the repo (my forked one) into my Cloud9 IDE, and then run the ./breeze command.

I got an error as follows

```
error: failed to solve: failed to solve with frontend dockerfile.v0: failed to create LLB definition: rpc error: code = Unknown desc = error getting credentials - err: exit status 1, out: `GDBus.Error:org.freedesktop.DBus.Error.ServiceUnknown: The name org.freedesktop.secrets was not provided by any .service files`
```

It turns out thatI needed to install a new package, and this then fixed the error.

```
sudo apt install gnome-keyring
```

When I run ./breeze again, it all works and I am now sitting within the Breeze container, sitting at the bash shell. I exit, and then add the autocomplete option which is recommended within the doc (just running ./breeze setup-autocomplete) and looks like we are good to go.

There is a lot of details in the doc, and I will admit that I was not sure where to begin. I found this video from Jarek was much more helpful and recommend folk view it. I actually had it running and tried to follow along once I had everything up and running.

{{< youtube 4MCTXq-oF68 >}}

**Get local builds running**

Reviewing the [quick start guide](https://github.com/apache/airflow/blob/main/CONTRIBUTORS_QUICK_START.rst), it advices to run the following commands to get Apache Airflow up and running within Breeze

```
./breeze --python 3.8 --backend mysql
./breeze start-airflow
```

After a few minutes of downloading various images, it launches a tmux terminal and I could see the Apache Airflow processes start. As I was using AWS Cloud9, I could not access the preview URLs (it was listening out for *:28080) so I needed to modify the inbound security rule for my AWS Cloud9 rule so that my specific IP could access this instance on this port. Once I did that, using the public IP of the AWS Cloud9 instance, I could now access this Apache Airflow instance (and login using the default admin/admin user).

The quick start also suggests setting up MySQL Workbench and connecting to the local MySQL database. As I am using JetBrains DataGrip, I open another port on my AWS Cloud9 instance, create a new connection profile for this instance (connecting to port 23306),and validate I can access this too. So far looking good.

From the active terminal, I can stop this by running, which I can validate has killed all the processes as I can no longer access it via the browser.

```
stop_airflow
```

And I can exit from Breeze by entering "exit" from the container shell, and then stop Breeze by running "./breeze stop"

**Tests**

You run tests from within the Breeze environment. Having gone through the video above, I wanted to run some just to sanity check the setup. Aside from some wonky paths, running the following worked fine:

```
pytest tests/core
...
<hidden output>
...

= 147 passed, 10 skipped, 62 warnings in 26.65s  =
```
You can also run the tests from the AWS Cloud9 terminal. It took me a while trying to make sense of this, but by running

```
./breeze tests tests/core
```
I actually went through the [Testing](https://github.com/apache/airflow/blob/main/TESTING.rst) doc which provides a lot of good instructions on the various scenarios, and ran lots of these to sanity check my setup.

Given that the ECS Operator is part of the providers package, and there is some specific guidance around the testing [Apache Airflow providers packages](https://github.com/apache/airflow/blob/main/TESTING.rst#running-tests-with-provider-packages). We know that the ECS Operator is in the Amazon provider package, so we run the following (from within Breeze):

```
pytest tests/providers/amazon

```

or from the host, we can run

```
./breeze tests tests/providers/amazon
```

If you want to run all the provider tests, you can run "pytest tests/providers"

> **Troubleshooting**
> While running these, the tests did not complete and I got an error as follows:
> ```
>_______________________________________________________________________ TestAwsS3HookNoMock.test_check_for_bucket_raises_error_with_invalid_conn_id _______________________________________________________________________
>
>self = <tests.providers.amazon.aws.hooks.test_s3.TestAwsS3HookNoMock object at 0x7feaa492ce80>, monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fead706a3d0>
>
>    def test_check_for_bucket_raises_error_with_invalid_conn_id(self, monkeypatch):
>        monkeypatch.delenv('AWS_PROFILE', raising=False)
        monkeypatch.delenv('AWS_ACCESS_KEY_ID', raising=False)
        monkeypatch.delenv('AWS_SECRET_ACCESS_KEY', raising=False)
        hook = S3Hook(aws_conn_id="does_not_exist")
        with pytest.raises(NoCredentialsError):
>           hook.check_for_bucket("test-non-existing-bucket")
>           Failed: DID NOT RAISE <class 'botocore.exceptions.NoCredentialsError'>
>
>tests/providers/amazon/aws/hooks/test_s3.py:47: Failed
>-------------------------------------------------------------------------------------------------- Captured stderr call ---------------------------------------------------------------------------------------------------
>WARNI [airflow.providers.amazon.aws.hooks.s3.S3Hook] Unable to use Airflow Connection for credentials.
>ERROR [airflow.providers.amazon.aws.hooks.s3.S3Hook] Not Found
>---------------------------------------------------------------------------------------------------- Captured log call ----------------------------------------------------------------------------------------------------
>WARNING  airflow.providers.amazon.aws.hooks.s3.S3Hook:base_aws.py:431 Unable to use Airflow Connection for credentials.
>ERROR    airflow.providers.amazon.aws.hooks.s3.S3Hook:s3.py:162 Not Found
>```
>
> If you see this, then it is likely the issue is caused by an IAM role that is attached to your EC2 instance. At least, that is what it was in my case. I could run these tests locally on my Macbook, on my Virtual Desktop without issue, but it was always this test that failed. When you review the test code, it kind of makes sense as the test case is actually removing AWS credentials, so expects to fail. The attached IAM role at the EC2 instance is kind of invisible to the test, and so whilst the test case expects to fail (with no credentials) the IAM role "helpfully" provides credentials, therefore failing the test! Lost about a day with this issue, so I hope this help some who sees a similar problem.


It will take several minutes to complete, but then you should get something like

```
866 passed, 16 skipped, 1 xfailed, 67 warnings in 141.00s (0:02:20) 
```

#### Summary and next steps

Now that we have our developer environment setup, we have the Apache Airflow source code forked and integrated with our developer tooling, made sure that everything runs and that the tests all complete successfully, we are good to go.

In the next blog post, I will take the next step of trying to explore the packages around the ECS Operator to try and understand how it works. I will look at the tests for this operator, a look at the end to end flow for changes, which will set up us for being able to start working on a fix for our problem.

**Postscript**

As I was writing this, I stumbled upon fellow Developer Advocate Damon Cortesi
 who also blogged about his journey contributing to Apache Airflow. This is a great read, and I wish I had know about this before starting. Check out the post, [Building and Testing a new Apache Airflow Plugin](https://dacort.dev/posts/building-and-testing-a-new-apache-airflow-plugin/)