---
title: 'Interacting with Amazon Managed Workflows for Apache Airflow via the command line'
date: '2021-02-01'
tags: [Apache Airflow, mwaa, cli]
---

![innovate](https://raw.githubusercontent.com/094459/innovateaiml-airflow/main/images/banner.png)

Part of a series of posts to support an up-coming online event, the Innovate AI/ML on February 24th, from 9:00am GMT - you can sign up [here](https://aws.amazon.com/events/aws-innovate/machine-learning/online/emea/?sc_channel=em&sc_campaign=EMEA_FIELD_WEBINAR_innovate-AIML_20210224_7014z000001MJbu&sc_medium=em_&sc_content=REG_t1_field&sc_geo=emea&sc_country=mult&sc_outcome=reg&sc_publisher=aws&trkCampaign=emea21_innovatemlq1&trk=em_emea21_innovatemlq1_ricardosueiras)

* **Part 1** - [Installation and configuration of Managed Workflows for Apache Airflow](https://aws-oss.beachgeek.co.uk/3h)
* **Part 2** - [Working with Permissions](https://aws-oss.beachgeek.co.uk/3n)
* **Part 3** - [Accessing Amazon Managed Workflows for Apache Airflow environments](https://aws-oss.beachgeek.co.uk/3o)
* **Part 4** - Interacting with Amazon Managed Workflows for Apache Airflow via the command line  < this post
* **Part 5** - [A simple CI/CD system for your development workflow](https://aws-oss.beachgeek.co.uk/4t)
* **Part 6** - [Monitoring and logging](https://aws-oss.beachgeek.co.uk/5r)
* **Part 7** - Automating a simple AI/ML pipeline with Apache Airflow 

In this post I will be covering Part 4, how you can interact and access the Apache Airflow via the command line. Specifically I will cover a couple of things:

1. How does Amazon Managed Workflows for Apache Airflow work with and support command line or programatic access
2. A walkthrough and some examples of how to do this.

**What will you need**

* An AWS account with the right level of privileges
* An environment with the AWS CLI tools configured and running
* Access to an AWS region where Managed Workflows for Apache Airflow is supported
* An environment of Amazon Managed Workflows for Apache Airflow already setup - you should ideally have followed [part one here](https://aws-oss.beachgeek.co.uk/3h).

**Apache Airflow cli**

Apache Airflow offers a comprehensive cli (you can read about the details [here](https://airflow.apache.org/docs/apache-airflow/stable/usage-cli.html)) but it is important to know that when working with MWAA, both the way you access the cli as well as the options available are different. If you are coming from a self installed/managed Apache Airflow, it is worth spending some time understanding the differences - you can read about that [here](https://aws-oss.beachgeek.co.uk/3p). We will see later on how to use these in your MWAA environments.

**Permissions**

Whilst I was putting this blog together I ran into permission errors (Access Denied) as I was ensuring that I only configured the minimum permissions needed and following the principal of least privilege.

I create a new IAM policy called MWAA-CLI-Access-{Env} with the following details which were specific to each environment. You could use wildcards if you wanted to enable this across your environments, but that was too permissive for me.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": "airflow:CreateCliToken",
            "Resource": [
                "arn:aws:airflow:{region}:{aws-account-no}:environment/{env}"
            ]
        }
    ]
}
```
Once created, you can attach this policy to a group, and then add any IAM users to that group that you want to enable with access to run these command line tools that I outline below.

**Apache Airflow via the command line**

You have a number of options open when you want to interact with your MWAA environment via the command line or programatically. Some of these you will have touched upon in previous posts. The approach you take will be affected by what you are trying to achieve. For example, some of the approaches are better suited for building/configuring and managing MWAA environments whereas other options provide better capabilities for working with Apache Airflow functionality.

Let us look at the options and what capabilities they provide.
 
* aws cli - the first option you have is to use the standard aws cli to be able to interact with MWAA. You can do a broad range of things, from inspecting/interrogating your MWAA environments to be able to create and update them. These are well documented in the official documentation pages which you can see [here](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/mwaa/index.html). You might be thinking could I use these to create MWAA environments rather than using something like CloudFormation as in an earlier post. The short answer is yes, however, you will need to use a number of different aws cli commands to provision all the other components (the networking, the security roles, S3 buckets, etc) so you may find it a better option to use this in conjunction with CloudFormation provisioned environments. This will depend on your preference and what you are already using.

* shell scripts - the next option you have is to interact via the shell, and here you can use standard bash scripts to interact directly with your Apache Airflow cli in an environment you have up and running. You can use the Apache Airflow cli to do things like starting/pausing your workflows, listing the workflows you have, checking the state of your workflows and more. 

* boto3 - the final option you have is to write some python code using the boto3 library, which is the AWS SDK for Python. This provides you with the ability to combine the functionality of both the aws cli and interacting with the Apache Airflow cli but in the context of your python application

Lets take a look at examples of all of these now. 

**Example via the AWS cli**

From the aws cli, you can use the following command to access the aws mwaa cli

```
aws mwaa help
```

Will output the commands available, and you can then issue the following command to get more detailed help on how to use a specific command.

```
aws mwaa {command} help
```

If we wanted to list the current MWAA environments in a given AWS region, we can use the following command:

```
aws mwaa list-environments
```

Which will show us something like this (assuming you have created an environment from an earlier post)

```
{
    "Environments": [
        "apache-airflow-aimlinnovate",
        "apache-airflow-innovate",
        "airflow-blogpost-dublin"
    ]
}
```

And if we wanted to get details of that environment - perhaps we wanted to see the worker sizes, get hold of the Apache Airflow UI or perhaps something else, we could use:

```
aws mwaa get-environment --name {an environment}
```

Which will give you something like this.

```
{
    "Environment": {
        "AirflowConfigurationOptions": {},
        "AirflowVersion": "1.10.12",
        "Arn": "arn:aws:airflow:eu-west-1:xxxxxxxxxxxx:environment/airflow-blogpost-dublin",
        "CreatedAt": 1610632127.0,
        "DagS3Path": "dags",
        "EnvironmentClass": "mw1.medium",
        "ExecutionRoleArn": "arn:aws:iam:: xxxxxxxxxxxx:role/airflow-demo-mwaa-eks-iamrole",
        "LastUpdate": {
            "CreatedAt": 1611137820.0,
            "Status": "SUCCESS"
        },
        "LoggingConfiguration": {
            "DagProcessingLogs": {
                "CloudWatchLogGroupArn": "arn:aws:logs:: xxxxxxxxxxxx:log-group:airflow-ricsue-dublin-DAGProcessing",
                "Enabled": true,
                "LogLevel": "INFO"
            },
            "SchedulerLogs": {
                "CloudWatchLogGroupArn": "arn:aws:logs:: xxxxxxxxxxxx:log-group:airflow-ricsue-dublin-Scheduler",
                "Enabled": true,
                "LogLevel": "INFO"
            },
            "TaskLogs": {
                "CloudWatchLogGroupArn": "arn:aws:logs:: xxxxxxxxxxxx:log-group:airflow-ricsue-dublin-Task",
                "Enabled": true,
                "LogLevel": "INFO"
            },
            "WebserverLogs": {
                "CloudWatchLogGroupArn": "arn:aws:logs:: xxxxxxxxxxxx:log-group:airflow-ricsue-dublin-WebServer",
                "Enabled": true,
                "LogLevel": "INFO"
            },
            "WorkerLogs": {
                "CloudWatchLogGroupArn": "arn:aws:logs:: xxxxxxxxxxxx:log-group:airflow-ricsue-dublin-Worker",
                "Enabled": true,
                "LogLevel": "INFO"
            }
        },
        "MaxWorkers": 5,
        "Name": "ricsue-dublin",
        "NetworkConfiguration": {
            "SecurityGroupIds": [
                "sg-0c88ef4755c295zzz"
            ],
            "SubnetIds": [
                "subnet-0493dffd0282f4xxx",
                "subnet-08f416023356ffyyy"
            ]
        },
        "RequirementsS3Path": "requirements/requirements.txt",
        "ServiceRoleArn": "arn:aws:iam:: xxxxxxxxxxxx:role/aws-service-role/airflow.amazonaws.com/AWSServiceRoleForAmazonMWAA",
        "SourceBucketArn": "arn:aws:s3:::airflow-mybucket",
        "Status": "AVAILABLE",
        "Tags": {},
        "WebserverAccessMode": "PUBLIC_ONLY",
        "WebserverUrl": "aaaaaaaa-bbbb-cccc-dddd-eeeeeeeeeeee.c5.eu-west-1.airflow.amazonaws.com",
        "WeeklyMaintenanceWindowStart": "SUN:14:00"
    }
}
```

We can then use tools such as jq to access certain parts of this information. Useful in some of the scripts later on is knowing the url of the Apache Airflow UI. We can easily get this using the following command:

```
aws mwaa get-environment --name {name of your environment} | jq -r '.Environment.WebserverUrl'
```

**Example via the command line**

Now let us take a look at how we would interact with Apache Airflow itself. As the documentation covers, [here](https://aws-oss.beachgeek.co.uk/3p) there are lots of the Apache Airflow commands we can use to do things like view the current workflows (DAGs), trigger or even delete DAGs and view the status of them. Many of the ones unavailable don't necessarily make sense for a managed service so it should not be too much of an inconvenience.

Let's say we wanted to use the Apache Airflow to list the current DAGs. We know that the cli command is list_dags, so we can put together a shell script that will interact with the Apache Airflow cli of a particular environment as follows.

```
#!/bin/bash
[ $# -eq 0 ] && echo "Usage: $0 MWAA environment name " && exit

if [[ $2 == "" ]]; then
    dag="list_dags"

elif [ $2 == "list_tasks" ] && [[ $3 != "" ]]; then
    dag="$2 $3"
    
elif [ $2 == "list_dags" ] || [ $2 == "version" ] || [ $2 == "variables" ]; then
    dag=$2

else
    echo "Not a valid command"
    exit 1
fi

CLI_JSON=$(aws mwaa create-cli-token --name $1) \
    && CLI_TOKEN=$(echo $CLI_JSON | jq -r '.CliToken') \
    && WEB_SERVER_HOSTNAME=$(echo $CLI_JSON | jq -r '.WebServerHostname') \
    && CLI_RESULTS=$(curl --request POST "https://$WEB_SERVER_HOSTNAME/aws_mwaa/cli" \
    --header "Authorization: Bearer $CLI_TOKEN" \
    --header "Content-Type: text/plain" \
    --data-raw "$dag" ) \
    && echo "Output:" \
    && echo $CLI_RESULTS | jq -r '.stdout' | base64 --decode \
    && echo "Errors:" \
    && echo $CLI_RESULTS | jq -r '.stderr' | base64 --decode
```

Now this is a pretty crude script, and you can extend it to support other commands other than list_dags or version (just edit line 4 to add the other commands you want to check for) but hopefully you get the idea.

When you run this command as follows (the airflow-cli.sh is just the same of the script I have created from the above file, and what I have put in the GitHub repo)

```
./airflow-cli.sh {environment} list_dags
```

You should get the following output

```
-------------------------------------------------------------------
DAGS
-------------------------------------------------------------------
bakery_sales
db_cleanup
multiple_steps
spark_pi_example
```

You can repeat the same, this time using the version command.

```
Output:
1.10.12
```

Remember, this does assume you have the AWS cli installed and configured as per your user account.

Some of the Apache Airflow cli commands take two rather than a single value. The script above shows you how you can extend this to cater for this. In the above example, the list_tasks command expects a DAG id. When we run the following command:

```
./airflow-cli.sh {environment} list_tasks bakery_sales
```

We get the following output

```
Output:
[2021-02-01 15:05:40,386] {{__init__.py:50}} INFO - Using executor CeleryExecutor
[2021-02-01 15:05:40,386] {{dagbag.py:417}} INFO - Filling up the DagBag from /usr/local/airflow/dags
add_steps
create_job_flow
watch_step
```

You should have enough to get started with your own, improved scripts to interact with the Apache Airflow commands.

**Example via python**

We can also use boto3, the AWS Python SDK if we preferred that approach. Here is a sample script that again takes multiple parameters (the environment, and the command) and then using the same technique as in the bash script, posts to the Apache Airflow command interpreter and then returns a response.

```
import requests
import boto3
import base64
import argparse


def parse_args():
    """Parse argument values from command-line"""

    parser = argparse.ArgumentParser(description='Arguments required for script.')
    parser.add_argument('-e', '--env', required=True, help='The name of your Mwaa environment')
    parser.add_argument('-c', '--command', required=True, help='The name of the Apache Airflow command you want to run.')
    args = parser.parse_args()
    return args


def main():
    args = parse_args()

    print("Connecting to MWaa environment" + ": " + args.env)
    client = boto3.client('mwaa')
    response = client.create_cli_token(Name=str(args.env))
    
    print("Using this command" + ": " + args.command)

    auth_token=response.get('CliToken')
    hed = {'Content-Type': 'text/plain', 'Authorization': 'Bearer ' + auth_token}
    data = str(args.command)
    url = 'https://{web_server}/aws_mwaa/cli'.format(web_server=response.get('WebServerHostname'))
    r = requests.post(url, data=data, headers=hed)
    print_output(r)


def print_output(r):
    output = base64.b64decode(r.json()['stdout']).decode('utf8')
    print(output)

if __name__ == '__main__':
    main()
```

When you run this with sample input like the following (I have called my script mwaa-python.py, but you can create your script to whatever name you prefer and you will change {environment to your own MWAA environment name):

```
python mwaa-eg-python.py -e {environment} -c version
```

You should get something similar to this:

```
Connecting to MWaa environment: ricsue-dublin
Using this command: version
1.10.12
```

You will find these scripts in the repository that supports these posts.

**Triggering via AWS Lambda**

The next thing you could do is then take code like this and then configure a function via AWS Lambda to potentially integrate event sources to trigger certain DAGs (say for example, a new data drop in an Amazon S3 bucket) 

These are the steps I followed to set this up.

**[1]** Create a new Python function within AWS Lambda (Python/3.7). You can use the basic execution role but you will then need to create and attach an IAM policy to this function that allows it to create an authentication token. This is what mine looked like (with the { } changed for my environment)

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": "airflow:CreateCliToken",
            "Resource": [
                "arn:aws:airflow:{region}:{aws-account-no}:environment/{name of your env}"
            ]
        }
    ]
}
```

For the code of the function, I used the same example as above but changed it to what AWS Lambda expects:

```
import json
import requests
import boto3
import base64

print('Loading function')


def lambda_handler(event, context):

    print("Connecting to MWaa environment" + ": " +  event['environment'])
    client = boto3.client('mwaa')
    response = client.create_cli_token(Name=str( event['environment']))
    
    print("Using this command" + ": " +  event['command'])

    auth_token=response.get('CliToken')
    hed = {'Content-Type': 'text/plain', 'Authorization': 'Bearer ' + auth_token}
    data = str(args.command)
    url = 'https://{web_server}/aws_mwaa/cli'.format(web_server=response.get('WebServerHostname'))
    r = requests.post(url, data=data, headers=hed)
    output = base64.b64decode(r.json()['stdout']).decode('utf8')
    print(output)

    return event['environment']  # Echo back the first key value
    
```

**[2]** You will need to create an AWS Lambda Layer that contains the libraries that this function uses (boto3, requests), and so to do this I used the following process (but feel free to use your own way of doing this if you are familiar with building Layers):

* create and setup an AWS Cloud9 IDE
* when started, create a new folder called mwaa-layers
* from this directory, use the command "pip install requests -t ./python" and "pip install boto3 -t ./python" which will use pip to download the python library files
* package up the zip file using the command "zip -r mwaa-layer.zip python" which will create a zip file called mwaa-layer.zip which just packages up all those libraries you downloaded into the Python folder
* use the command "aws lambda publish-layer-version --layer-name mwaa-dag-layer --zip-file fileb://mwaa-dag.zip --compatible-runtimes python3.7" to then create the layer.
* you can now attach this layer to the function you created in the first step.

**[3]** You can now create your test json file to check this function works. Using the AWS Lambda console, create a new Test action in the following format:

```
{
  "environment": "{your environment}",
  "command": "{airflow command}"
}
```

So mine looked like:

```
{
  "environment": "ricsue-dublin",
  "command": "version"
}
```

**[4]** You can now test your function by invoking it via the Test button and using the test action you just created. You should see output that looks like this:

```
START RequestId: 2f9b423e-1097-4e7f-bbc5-b1ff394c504e Version: $LATEST
Connecting to MWaa environment: ricsue-dublin
Using this command: version
1.10.12

END RequestId: 2f9b423e-1097-4e7f-bbc5-b1ff394c504e
REPORT RequestId: 2f9b423e-1097-4e7f-bbc5-b1ff394c504e	Duration: 2717.00 ms	Billed Duration: 2717 ms	Memory Size: 128 MB	Max Memory Used: 36 MB	

```

Note! As we are using the defaults, if your execution times out then try again or just increase the function timeout period.

**Conclusion**

This concludes the fourth post. You will now understand how you can interact with Apache Airflow via the command line, programatically and where to find the information regarding what is and what is not supported. 

Be sure to check out [this page on the MWAA documentation](https://docs.aws.amazon.com/mwaa/latest/userguide/access-airflow-ui.html) site which provides additional details on this topic. If there is a feature that you need and is missing, please get in touch. We are driven by our customer obsession.

In the next post we will look at setting up a simple CI/CD pipeline that will allow you to simplify life for your workflow development lifecycle.

If there is specific content you want to see, please get in touch.
