---
title: 'Working with parameters and variables in Amazon Managed Workflows for Apache Airflow'
date: '2021-07-27'
tags: [Apache Airflow, mwaa, variables, scripts]
---
**Maximising the re-use of your DAGs in MWAA**

During some recently conversations with customers, one of the topics that they were interested in was how to create re-usable, parameterised Apache Airflow workflows (DAGs) that could be executed dynamically through the use variables and/or parameters (either submitted via the UI or the command line). This makes a lot of sense, as you may find that you repeat similar tasks in your workflows, and so this approach allows you to maximise the re-use of that work.

Looking at some of the threads in the Apache Airflow slack channel, as well as some of the internal channels we use, it became clear that some guidance on how to do this when using Managed Workflows for Apache Airflow (MWAA) would help those, either new to MWAA or coming to MWAA from self managed Apache Airflow.

As I looked into this area, I noticed that there was also more interest in the integration of MWAA with AWS Secrets Manager as a way of storing and retrieving those variables securely. 

To address these, I thought I would put together this post to dive a little deeper into some of your options when looking to create parameterised and re-usable workflows (DAGs) that you can run on MWAA. This is by no means an exhaustive list, and welcome feedback on other ways that I might have missed or are improvements on what is listed below.

All the source code in this blog post can be found in [this GitHub repository](https://github.com/094459/blog-mwaa-variables)

Please let me know if you find this post useful. I have a very short survey which you [can complete here](https://eventbox.dev/survey/0R1JFG1), and the first 20 will receive $25 AWS credit codes.

**What will you need**

* An AWS account with the right level of privileges
* An environment with the AWS CLI tools configured and running
* Access to an AWS region where Managed Workflows for Apache Airflow is supported, as well as an environment of Amazon Managed Workflows for Apache Airflow already setup - [you can follow my previous link here](https://aws-oss.beachgeek.co.uk/3h) or check out the instructions in the GitHub repo which will walk you setting up an environment

### Using Variables in Apache Airflow

In this particular post I want to look at how you can use variables in Apache Airflow, and more specifically MWAA to do a few things:

* first, a look at the different options you have when working with variables and parameters in your workflows
* second, how you can work with variables and parameters either via the Apache Airflow UI, the Airflow clip or in your DAGs
* third, how you can alter how your workflows behave by using parameters during runtime
* finally, some additional ideas with example code, that provide some alternative approaches you can experiment with


There are some thing to be aware of when working with variables and parameters in MWAA.

* If you have been used to using the Apache Airflow cli to work with variables, then some of the Airflow commands may or may not be available to you. You can check out the summarised list of Airflow commands that work [here](https://docs.aws.amazon.com/mwaa/latest/userguide/airflow-cli-command-reference.html) and you will notice that this does vary between Airflow 1.x and 2.x

* You cannot use the Apache Airflow REST API within MWAA. Instead, use the Apache Airflow cli either via the MWAA API or via the bash and python operators within a DAG

> **Note! Further reading**
> There are lots of great blog posts that dive into detail on how to work with variables in Apache Airflow. I can recommend these ones to get started (on top of the documentation you will find at airflow.apache.org)
> https://marclamberti.com/blog/variables-with-apache-airflow/
> https://www.applydatascience.com/airflow/airflow-variables/

**Good practices**

When working with variables in your workflows (DAGs), then consider some of these good practices:

*Careful you do not reveal your secrets*

When you define variables within the Apache Airflow UI (via the Admin tab) they are stored securely (encrypted) within the Apache Airflow metastore. If you store your variables in other places, then it will depend. For example, if you use AWS Secrets Manager, your variables will also be encrypted.

This helps you to improve your security by reducing the need to store sensitive information (such as passwords, shared keys, etc) that your DAGs might need when connecting to downstream services.

There are some gotcha's you should be aware of and you should test.

The first, and something that I found out when using some of the Airflow operators, is that sometime passwords may be printed as part of the log files that are produced by your Tasks. You should therefore check those Task logs, and importantly ensure that you lock down access and encrypt these if any sensitive information is output. If you are creating your own operators, think about this when you look at how your operator will generate output.

The second is that you can potentially see those passwords in the Admin UI (again, lock that down to reduce this risk). You can mitigate this by naming your variables to contain a key string that will make Airflow hide the string. For example, if you create a variable called "myconnection_secret" the value will be hidden. You can read more about this [here](https://airflow.apache.org/docs/apache-airflow/stable/security/secrets/index.html) with the values set to : ‘password’, ‘secret’, ‘passwd’, ‘authorization’, ‘api_key’, ‘apikey’ and ‘access_token’

The third is to be wary of using environment variables when setting/retrieve secret values. This is not a good idea and those values may be exposed and will not be protected.

*Optimise your code when working with variables* 

The way that Apache Airflow works under the covers means that where you locate the code that reads/writes variables within your DAGs can have an impact on the overall performance of your MWAA environment. Your DAG is parsed by the MWAA schedulers every second

```
processor_poll_interval = 1
```

So when thinking about overall scalability and performance of your workflows, you should look to:

* Keep variables that you store in the metastore inside of the task/operator rather than in the main body of your DAG. This will stop the scheduler polling the metastore
* Use a single variable with a JSON value. This will allow you to minimise calls to the metastore
* Use Jinja templates as placeholders for your variables. When you do this, the call to the metastore will only be done during execution of the workflow. The caveat here is that you need to make sure that the operators you are working with support passing variables this way.

> Note! The quickest way of knowing what parameters your operators support for passing in these Jinja templates is to either check the documentation of the operator, and/or review the source code of the operator and look for the "templated" value which tells you which parameters are supported.
> If we look at the source code for the bash operator we can see the following lines in the code
> 
```
template_fields = ('bash_command', 'env')
template_fields_renderers = {'bash_command': 'bash', 'env': 'json'}

```
>
> Which show that this supports templating when using either the bash_command or env argument within the Bash operator as follows
> 
```
param = BashOperator(task_id="demo", bash_command="echo {{ params.my_param }}", 
```
>

*System Environment variables*

If you have been using environment variables within your DAGs then you need to be aware of the ephemeral workers in MWAA that execute your tasks, which mean that tasks may not execute on the same host. 

Using environment variables in your DAGs may generate unpredictable results

You can explore the environment variables that are available and that might be useful for you using a simple DAG such as:

```
from airflow import DAG
from airflow.operators.bash_operator import BashOperator
from airflow.utils.dates import days_ago
with DAG(dag_id="info-mwaa-env", schedule_interval=None, catchup=False, start_date=days_ago(1)) as dag:
    env_cli_command = BashOperator(
        task_id="env_cli_command",
        bash_command="env"
    )
```

*Overwrite*

One thing to take note is that when importing/setting variables in the Apache Airflow metastore, you will overwrite any existing value that might already be set.

**Where is my Admin tab gone?**

When working with the Apache Airflow UI, depending on how your access has been set up, you may or may not have full admin access to Apache Airflow. I covered this in an earlier post, Working with Managed Workflows for [Apache Airflow Permissions](https://aws-oss.beachgeek.co.uk/3n).

If in your set up you only have user access, you will not be able to define/set variables via the UI. In the examples below, this may mean you need to take one of the other approaches to defining/setting variables you want to use.

> MWAA uses the [standard Apache Airflow roles](https://airflow.apache.org/docs/apache-airflow/1.10.6/security.html?highlight=ldap#default-roles); Admin, User, Ops, etc - Admin and Ops both enable the Admin tab within the UI but you may not want to provide that to your Airflow users, and just provide them with the level of access needed to view/trigger their workflows (User)

**Example variables we want to set**

To help put all of this together, let us run through some examples of the different ways we can work with variables in MWAA. We start with our variables. In our scenario, we want to define these set of variables that our DAG will use.

```
{
    "cli_test": "newvalue/",
    "cli_test2": "12341234",
    "cli_test3": "https://grouplens.org/datasets/movielens/latest/"
}
```
We can save this in a file which we will call "variables.json".

We will run through some examples and see how we can cover a number of use cases that should help simplify and cover how you can do this for yourself.

### Setting variables in AWS Secrets Manager

**Setting up MWAA to use AWS Secrets Manager**

We can use AWS Secrets Manager to store variables that we want to use within our DAGs. We need to make a change to our MWAA environment however before we can do that.

We need to modify the MWAA environment and add the following Airflow configurations (within MWAA this is done via the MWAA environment configurations, which you can read about [here](https://docs.aws.amazon.com/mwaa/latest/userguide/configuring-env-variables.html#configuring-env-variables-customizing)). The change is also version specific, so depending on whether you are using MWAA 1.x or 2.x, you need to use the correct configuration option. 

*MWAA 1.x*

```
secrets.backend: airflow.contrib.secrets.aws_secrets_manager.SecretsManagerBackend

secrets.backend_kwargs: '{"connections_prefix" : "airflow/connections", "variables_prefix" : "airflow/variables"}'  
```

*MWAA 2.x*

```
secrets.backend : airflow.providers.amazon.aws.secrets.secrets_manager.SecretsManagerBackend,

secrets.backend_kwargs: '{"connections_prefix" : "airflow/connections", "variables_prefix" : "airflow/variables"}' 
            
```
Making this change will cause your MWAA environment to update, so it will be unavailable for approx. 20-25 minutes.

Before you do this however, you will need to update the IAM execution role that your MWAA environment is running to be able to access the secrets you create. 

You can add the "SecretsManagerReadWrite" managed policy to your role, but this will provide very broad access to your secrets. You should lock that down to just the secrets that you want your MWAA to have access to. 

> Note! In the GitHub repo you will find a example CDK application that deploys a MWAA environment with the minimum permissions scoped down to just the variables you want MWAA to access.

After you have made the update and your MWAA environment is back, it is time to review what you have done. You have created a hook that will now do a look up in AWS Secrets Manager when you do a 'Variable.get("{my_variable}")' within your DAG, looking for a secret key of "airflow/variables/my_variable" in AWS Secrets Manager.

>Note! Remember to ensure that these are both in the same AWS region, as MWAA will look in the current region it is deploy into for those secrets

So now all you have to do is store your variables in AWS Secrets Manager in the right forward and key, and they will be picked up automatically in your DAGs.

> Check out the blog from John Jackson, [Move your Apache Airflow connections and variables to AWS Secrets Manager](https://aws.amazon.com/blogs/opensource/move-apache-airflow-connections-variables-aws-secrets-manager/) where he dives deep into this.

**Storing our variables via AWS Secrets Manager**

Lets put our variables in AWS Secrets Manager

```
{
    "cli_test": "newvalue/",
    "cli_test2": "12341234",
    "cli_test3": "https://grouplens.org/datasets/movielens/latest/"
}
```

We are going to use the AWS cli to do this. 

```
aws secretsmanager create-secret --name airflow/variables/cli_test --description "Cli variable 1" --secret-string "newvalue/" --region={your region}"
aws secretsmanager create-secret --name airflow/variables/cli_test2 --description "Cli variable 2" --secret-string "007007" --region={your region}"         
aws secretsmanager create-secret --name airflow/variables/cli_test3 --description "Cli variable 3" --secret-string "https://grouplens.org/datasets/movielens/latest/" --region={your region}
```
This will generate output similar to the following:

```
{
    "ARN": "arn:aws:secretsmanager:eu-central-1:704533066374:secret:airflow/variables/cli_test-OsNI9S",
    "Name": "airflow/variables/cli_test",
    "VersionId": "988f7bd5-b0fb-47ca-ab0b-343c665b0d24"
}
```

And we can view any of these defined variables using the describe-secret option

```
aws secretsmanager describe-secret --secret-id airflow/variables/cli_test
```
Which outputs the metadata, and does not expose the secret.

```
{
    "ARN": "arn:aws:secretsmanager:eu-central-1:704533066374:secret:airflow/variables/cli_test-OsNI9S",
    "Name": "airflow/variables/cli_test",
    "Description": "Cli variable 1",
    "LastChangedDate": 1627293097.284,
    "VersionIdsToStages": {
        "988f7bd5-b0fb-47ca-ab0b-343c665b0d24": [
            "AWSCURRENT"
        ]
    },
    "CreatedDate": 1627293097.25
}
```
We can also see this via the AWS console

![screen](https://github.com/094459/blog-mwaa-variables/blob/main/images/airflow-console-secret.png?raw=true)

### Using variables in AWS Secrets Manager in our DAGs

Now we can use these variables in our DAG as follows. Here I am showing two methods, the first by assigning it directly with the workflow, and the second (preferred) way is to use the Jinja templates. In the DAG below, when we reference the variable "cli_test", the integration between MWAA and AWS which we have configured via the "secrets.backend/secrets.backend_kwargs" configuration within MWAA, MWAA will look for a variable in AWS Secrets manager called "airflow/variables/cli_test"

```
from airflow import DAG
from airflow.operators.bash_operator import BashOperator
from airflow.utils.dates import days_ago
from airflow.models import Variable

demo =  Variable.get("cli_test", default_var="undefined")

with DAG(
    dag_id="aws_secrets_variables",
    schedule_interval=None,
    catchup=False,
    start_date=days_ago(1)) as dag:

    get_var_sec1 = BashOperator(
        task_id="disp_aws_secret_variable_1",
        bash_command='echo "The value of the variable is: {var}"'.format(var=demo),
    )

    get_var_sec2 = BashOperator(
        task_id="disp_aws_secret_variable_2",
        bash_command='echo "The value of the second variable is: {{var.value.cli_test2}}"',
    )
```

And when we trigger this DAG, we can see the following output

```
[2021-07-26 11:31:40,040] {{bash.py:158}} INFO - Running command: echo "The value of the variable is: newvalue/"
[2021-07-26 11:31:40,078] {{bash.py:169}} INFO - Output:
[2021-07-26 11:31:40,113] {{bash.py:173}} INFO - The value of the variable is: newvalue/
...
...
[2021-07-26 11:31:40,089] {{bash.py:158}} INFO - Running command: echo "The value of the second variable is: 123456"
[2021-07-26 11:31:40,185] {{bash.py:169}} INFO - Output:
[2021-07-26 11:31:40,273] {{bash.py:173}} INFO - The value of the second variable is: 123456
```

Now lets move onto the next method, using the Apache Airflow UI and metastore.

### Setting variables via the Apache Airflow UI

Assuming we have the right level of access (Admin or Ops) then from the Apache Airflow UI, we will see the ADMIN tab and from that we can select VARIABLES, which will show us variables we can use.

![blank_variable](https://github.com/094459/blog-mwaa-variables/blob/main/images/var_ui_blank.png?raw=true)

We can add variables either one at a time (by clicking on the + next to the ACTIONS button) or via a parameterised file by first browsing to our file and then clicking on the IMPORT VARIABLES at the top of the screen. (See above for the file variables.json) Which will show up now in the UI

![ui_var_show](https://github.com/094459/blog-mwaa-variables/blob/main/images/var_ui_imported.png?raw=true)

When you do this those variables are being stored in the Apache Airflow metastore. They are encrypted so the values you set are safe.

At this stage I have not disabled the AWS Secrets Manager integration with MWAA, so what happens if we choose variable names that DUPLICATE of the ones we have stored in AWS Secrets Manager? Lets find out, as one of the variables has different values (cli_test2, when we set this in AWS Secrets Manager we used the value 007007, but in the variables.json file, it is 12341234) 

When we run the DAGs again, we can see from the output

```
[2021-07-26 11:56:45,329] {{bash.py:158}} INFO - Running command: echo "The value of the second variable is: 123456"
[2021-07-26 11:56:45,402] {{bash.py:173}} INFO - The value of the second variable is: 123456

```
Which is what we would expect. If a variable exists in both AWS Secrets Manager AND is defined via the Airflow UI, AWS Secrets Manager will be used. If I delete the secret from AWS Secrets Manager and re-run the DAG, you will see the following error in the log

```
An error occurred (InvalidRequestException) when calling the GetSecretValue operation: You can't perform this operation on the secret because it was marked for deletion.
```
This is normal, and as expected. Once AWS Secrets manager has cleared the secret (which you define when you delete it) this error will go away and it will pick up the value from the Apache Airflow metastore. Make sure you are aware of this as you think about how you will use variables in your workflows.

**What happens if we define a variable that doesn't exist?**

If we use a variable in our DAGs that have not been defined, either directly within the DAG itself, via something like AWS Secrets Manager or Apache Airflow Variables, then the Task will fail with an error. I modified the DAG as follows:

```
    get_var_sec2 = BashOperator(
        task_id="disp_aws_secret_variable_2",
        bash_command='echo "The value of the second variable is: {{var.value.cli_test4}}"',
    )
```

But I did not yet create this variable. When I run the DAG, it generates a Task failure with the following error:

```
KeyError: 'Variable cli_test4 does not exist'
```
If I now use the Apache Airflow UI to add a new variable called "cli_test4" with a value "I am feeling better now" and then re-run the DAG, we now get:

```
[2021-07-26 12:28:18,320] {{bash.py:158}} INFO - Running command: echo "The value of the second variable is: I am feeling better now"
[2021-07-26 12:28:18,399] {{bash.py:173}} INFO - The value of the second variable is: I am feeling better now
```

### Setting variables when launching/triggering DAGs

So far we have set the variables we wanted to use either directly within Apache Airflow (in the metastore via the Apache Airflow UI) or via the integration with AWS Secrets Manager. 

We might want to set variables every time we run our workflow. When we trigger our workflows via the Apache Airflow UI, we get the opportunity to provide a configuration json file (which is optional) which you will have seen via this screen:

![ui-param](https://github.com/094459/blog-mwaa-variables/blob/main/images/trigger_var.png?raw=true)

You will notice that it says you can access these values via ```"{{ dag_run.conf }}"```

We can use this within our DAGs in MWAA as follows:

```
from airflow import DAG
from airflow.operators.bash_operator import BashOperator
from airflow.utils.dates import days_ago

with DAG(
    dag_id="airflow_variables_atruntime",
    schedule_interval=None,
    catchup=False,
    start_date=days_ago(1)) as dag:

    get_var_filename = BashOperator(
        task_id="get_var_filename",
        bash_command='echo "You are running this DAG with the following variable file: \'{{ dag_run.conf["cli_test"] if dag_run.conf else "" }}\'"',
    )
    get_var_filename = BashOperator(
        task_id="get_var_filename2",
        bash_command='echo "You are running this DAG with the following variable file: \'{{ dag_run.conf["cli_test2"] if dag_run.conf else "" }}\'"',
    )
    get_var_filename = BashOperator(
        task_id="get_var_filename3",
        bash_command='echo "You are running this DAG with the following variable file: \'{{ dag_run.conf["cli_test3"] if dag_run.conf else "" }}\'"',
    )

```

When you trigger this DAG and do not submit any parameters, in the logs you should see that all the task have output 


```
[2021-07-26 12:54:57,278] {{bash.py:158}} INFO - Running command: echo "You are running this DAG with the following variable file: ''"
[2021-07-26 12:54:57,379] {{bash.py:173}} INFO - You are running this DAG with the following variable file: ''
```

> Note! If when you trigger the DAG and leave the blank, you  get errors such as

```
jinja2.exceptions.UndefinedError: 'dict object' has no attribute 'cli_test'
```
> check to make sure you are using dag_run.conf and not just dag_run. You will see in the examples below the correct format that allows you to combine a number of different sources for your variables.

When we submit the following into the the parameter form and kick off the DAG 

```
{
    "cli_test": "newvalue/",
    "cli_test2": "12341234",
    "cli_test3": "https://grouplens.org/datasets/movielens/latest/"
}
```

We can now see that the DAG processes fine and we see the following in the logs (just showing one of the task outputs)

```
[2021-07-26 12:54:57,278] {{bash.py:158}} INFO - Running command: echo "You are running this DAG with the following variable file: '12341234'"
[2021-07-26 12:54:57,379] {{bash.py:173}} INFO - You are running this DAG with the following variable file: '12341234'
```

**Overiding variables**

You can combine all the techniques above so that you can store variables, either in Apache Airflow's metastore or AWS Secrets Manager, but also then over-ride them when you trigger the workflows.

Assuming we have the variables we have been using (cli_test, cli_test2, etc) already setup in Apache Airflow, in the following DAG:

```
from airflow import DAG
from airflow.operators.bash_operator import BashOperator
from airflow.utils.dates import days_ago

with DAG(
    dag_id="airflow_variables_atruntime",
    schedule_interval=None,
    catchup=False,
    start_date=days_ago(1)) as dag:

    get_var_filename = BashOperator(
        task_id="get_var_filename",
        bash_command="""echo 'You are running this DAG with the following variable file: "{{ dag_run.conf["cli_test"] if dag_run.conf else var.value.cli_test }}"'""",
    )
    get_var_filename = BashOperator(
        task_id="get_var_filename2",
        bash_command='echo "You are running this DAG with the following variable file: \'{{ dag_run.conf["cli_test2"] if dag_run.conf else var.value.cli_test2 }}\'"',
    )
    get_var_filename = BashOperator(
        task_id="get_var_filename3",
        bash_command='echo "You are running this DAG with the following variable file: \'{{ dag_run.conf["cli_test3"] if dag_run.conf else var.value.cli_test3 }}\'"',
    )
```

When we trigger this workflow and submit this parameter/variable file:

```
{
    "cli_test": "override/",
    "cli_test2": "007007",
    "cli_test3": "https://bbc.co.uk"
}
```

When we look at the logs from the task, we can see that the values are as follows (I am just showing the log for the first task, for cli_test):

```
[2021-07-26 15:54:34,309] {{bash.py:158}} INFO - Running command: echo 'override/'
[2021-07-26 15:54:34,374] {{bash.py:173}} INFO - override/
```
and if we re-run the task, this time not submitting anything, we get what we have stored in the Apache Airflow metastore

```
[2021-07-26 15:54:04,899] {{bash.py:158}} INFO - Running command: echo 'newvalue/'
[2021-07-26 15:54:04,967] {{bash.py:173}} INFO - newvalue/
```

We can extend this and combine all three techniques for passing in variables: passing a set of parameters when triggering the DAG, using the Apache Airflow metastore and the AWS Secrets Manager. 

I delete all the variables in Apache Airflow metastore, but create a new one called cli_test4 with a value of "This rocks!". We update our DAG as follows:

```
from airflow import DAG
from airflow.operators.bash_operator import BashOperator
from airflow.utils.dates import days_ago

with DAG(
    dag_id="airflow_variables_atruntime",
    schedule_interval=None,
    catchup=False,
    start_date=days_ago(1)) as dag:

    get_var_filename = BashOperator(
        task_id="get_var_filename",
        bash_command="""echo 'You are running this DAG with the following variable file: "{{ dag_run.conf["cli_test"] if dag_run.conf else var.value.cli_test }}"'""",
    )
    get_var_filename = BashOperator(
        task_id="get_var_filename2",
        bash_command='echo "You are running this DAG with the following variable file: \'{{ dag_run.conf["cli_test2"] if dag_run.conf else var.value.cli_test4 }}\'"',
    )
    get_var_filename = BashOperator(
        task_id="get_var_filename3",
        bash_command='echo "You are running this DAG with the following variable file: \'{{ dag_run.conf["cli_test3"] if dag_run.conf else var.value.cli_test3 }}\'"',
    )
```

When we trigger the DAG, if we submit the following parameter file:

```
{
    "cli_test": "override/"
}

```

When the DAG executes this is what we would expect:

* cli_test value is been obtained from when we you the DAG
* cli_test3 value is been obtained from AWS Secrets Manager (this is because I deleted cli_test2 in a previous step)
* cli_test4 value is been obtained from the Apache Airflow metastore

However, when we I run this, we get an error. What has happened? 

When we trigger the DAG now, in effect the value of dag_run.conf becomes true, and the 2nd and 3rd Tasks expect the values to be available in dag_run.conf. To fix this, we make one more tweak to our DAG:


```
from airflow import DAG
from airflow.operators.bash_operator import BashOperator
from airflow.utils.dates import days_ago

with DAG(
    dag_id="airflow_variables_atruntime",
    schedule_interval=None,
    catchup=False,
    start_date=days_ago(1)) as dag:

    get_var_filename = BashOperator(
        task_id="get_var_filename",
        bash_command="""echo 'You are running this DAG with the following variable file: "{{ dag_run.conf["cli_test"] if dag_run.conf.get("cli_test") else var.value.cli_test }}"'""",
    )
    get_var_filename = BashOperator(
        task_id="get_var_filename2",
        bash_command='echo "You are running this DAG with the following variable file: \'{{ dag_run.conf["cli_test2"] if dag_run.conf.get("cli_test2") else var.value.cli_test3 }}\'"',
    )
    get_var_filename = BashOperator(
        task_id="get_var_filename3",
        bash_command='echo "You are running this DAG with the following variable file: \'{{ dag_run.conf["cli_test3"] if dag_run.conf.get("cli_test3") else var.value.cli_test4 }}\'"',
    )

```
And when we now run the DAG, either with or without parameters, we get the expected behaviour. Our DAG is now grabbing variables from the Apache Airflow metastore, AWS Secrets Manager and from parameters supplied when triggered.

### Importing variables without the UI

What if you do not have access to the Apache Airflow Admin UI? Apache Airflow does provide a cli and an API that allows you to do a number of things with variables. You can use the following command

```
airflow variables {command}
```
and then provide a number of different commands that allow you to set, get, import variables into the Apache Airflow metastore.

Some things to be aware of when working with MWAA.

* We cannot access the Airflow cli in MWAA directly, but we can access a subset of them via a DAG
* Not all the Apache Airflow commands are supported, so [check out the following page on the MWAA documentation](https://docs.aws.amazon.com/mwaa/latest/userguide/airflow-cli-command-reference.html) that lets you know what does and does not work
* The Apache Airflow commands are different between versions (and the same goes for what does and does not work with MWAA)
* We cannot use the Airflow RESTful API

So this can make working with the Apache Airflow via the cli something you need to understand and may require some getting used to if you have some existing scripts and automation that relies heavily on accessing the Apache Airflow commands.

In the following I provide a couple of options that might work for you.

**Using a DAG to import/create variables**

Whilst we cannot access the Airflow cli in MWAA directly, we can access it via a DAG. One approach then to using the Airflow cli is to create a DAG that runs the "airflow variables" command to do with it what we want. The caveat here is that we cannot do in MWAA what the vanilla Apache Airflow provides, so lets see what we can do.

These are broken down here by different versions of Apache Airflow/MWAA.

*MWAA 1.x*

We can import a set of variables (in this case, our variables.json file above) by creating a DAG which takes that file and then uses the Apache Airflow import command to bulk import this. This is what the DAG looks like.


```
from airflow import DAG
from airflow.operators.bash_operator import BashOperator
from airflow.utils.dates import days_ago

with DAG(
    dag_id="import_airflow_variables",
    schedule_interval=None,
    catchup=False,
    start_date=days_ago(1)) as dag:

    get_var_filename = BashOperator(
        task_id="get_var_filename",
        bash_command='echo "You are importing the following variable file: \'{{ dag_run.conf["var_filename"] if dag_run.conf else "variables.json" }}\'"',
    )
    task1 = BashOperator(
        task_id="create_variables",
        bash_command='airflow variables --import /usr/local/airflow/dags/{{ dag_run.conf["var_filename"] if dag_run.conf else "variables.json"}}'
   )

```
We upload the variables.json file with our DAG file to the defined MWAA DAG S3 bucket. 

The DAG defaults to variables.json if no parameters are provided, but it does allow you to provide a runtime parameter that overrides the filename. For example, if I wanted to use a different file called my_vars.json, I would upload that file to the DAGS folder and then trigger the DAG and submit a parameter of {"var_filename":"my_vars.json"}. 

This is what my DAGS folder looks like

```
.
├── import-var-dag.py
└── variables.json
```

MWAA takes care of deploying it into the following location (/usr/local/airflow/dags) so we can then access it as a standard file. The DAG itself invokes the Apache Airflow command via a bash operator, running the "airflow variables --import" command, which is supported in MWAA 1.x

When we trigger the DAG, you should see that the variables now appear in the Apache Airflow metastore (you can use the UI to check this). If you delete the variables and re-run the DAG, you should see they appear back.

When we look at the logs, we can see that when we do not supply any parameters, the default of "variables.json" is used and imported.

```
[2021-07-27 08:29:13,721] {{bash_operator.py:146}} INFO - Running command: echo "You are importing the following variable file: 'variables.json'"
[2021-07-27 08:29:13,761] {{bash_operator.py:153}} INFO - Output:
[2021-07-27 08:29:13,790] {{bash_operator.py:157}} INFO - You are importing the following variable file: 'variables.json'
[2021-07-27 08:29:13,818] {{bash_operator.py:161}} INFO - Command exited with return code 0
[2021-07-27 08:29:13,858] {{taskinstance.py:1070}} INFO - Marking task as SUCCESS.dag_id=import_airflow_variables, task_id=get_var_filename, execution_date=20210727T082909, start_date=20210727T082912, end_date=20210727T082913
```

when we supply a parameter of ```{"var_filename":"my_vars.json"}``` and upload a file with some variables we get the following output:

```
[2021-07-27 08:33:19,467] {{bash_operator.py:146}} INFO - Running command: echo "You are importing the following variable file: 'my_vars.json'"
[2021-07-27 08:33:19,499] {{bash_operator.py:153}} INFO - Output:
[2021-07-27 08:33:19,523] {{bash_operator.py:157}} INFO - You are importing the following variable file: 'my_vars.json'
[2021-07-27 08:33:19,547] {{bash_operator.py:161}} INFO - Command exited with return code 0
[2021-07-27 08:33:19,589] {{taskinstance.py:1070}} INFO - Marking task as SUCCESS.dag_id=import_airflow_variables, task_id=get_var_filename, execution_date=20210727T083312, start_date=20210727T083318, end_date=20210727T083319

```

*MWAA 2.x*

We can take the same approach with MWAA 2.x, the only difference being is that the DAG is slightly different (the --import becomes just import)

```
from airflow import DAG
from airflow.operators.bash_operator import BashOperator
from airflow.utils.dates import days_ago

with DAG(
    dag_id="import_airflow_variables",
    schedule_interval=None,
    catchup=False,
    start_date=days_ago(1)) as dag:

    get_var_filename = BashOperator(
        task_id="get_var_filename",
        bash_command='echo "You are importing the following variable file: \'{{ dag_run.conf["var_filename"] if dag_run.conf else "variables.json" }}\'"',
    )
    task1 = BashOperator(
        task_id="create_variables",
        bash_command='airflow variables import /usr/local/airflow/dags/{{ dag_run.conf["var_filename"] if dag_run.conf else "variables.json"}}'
   )
```

**Using the Airflow CLI to create/import variables**

The next way we can import variables into MWAA is via scripts. You can take a look at the MWAA documentation for the script that this is based on here, [Creating an Apache Airflow CLI token](https://docs.aws.amazon.com/mwaa/latest/userguide/call-mwaa-apis-cli.html) that covers how to access MWAA via both bash and Python. As mentioned above, these vary between MWAA versions.

The bash scripts assume you are running on either Linux or OSX (which is what I am using) and that you have the AWS cli installed and configured as well as jq installed.
 
*MWAA 1.x*

```
#!/bin/bash


[ $# -eq 0 ] && echo "Usage: $0 MWAA environment name " && exit

if [[ $2 == "" ]]; then
    dag="variables"

elif [ $2 == "--set" ] || [ $2 == "-s" ] || [ $2 == "--get" ] || [ $2 == "-g" ] || [ $2 == "-x" ] || [ $2 == "--delete" ]; then
    dag="variables $2 $3 $4 $5"

else
    echo "Not a valid command"
    exit 1
fi

CLI_JSON=$(aws mwaa --region $AWS_REGION create-cli-token --name $1) \
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

With this script, we can get, set and delete variables that are stored in the Apache Airflow metastore in MWAA. We use this script providing the name of a MWAA environment we want to run against. In this example, we delete the cli_test variable, set it to a new value of "test" and then retrieve this.

```
./mwaa-v1-variables.sh ricsue-dublin --delete cli_test
./mwaa-v1-variables.sh ricsue-dublin --set cli_test "test"
./mwaa-v1-variables.sh ricsue-dublin --get cli_test
```

Those familiar with Apache Airflow may wonder why we are not using the --import option as well? This is not one of the Airflow command options that MWAA supports, and whilst we can set, delete and get variables, we cannot do use this for bulk importing of our variables. For that, we can create a script that iterates on the values within the variable file we want to import. Here is an example:


```
import boto3
import json
import requests 
import base64
import getopt
import sys

argv = sys.argv[1:]
mwaa_env=''
aws_region=''
var_file=''

try:
    opts, args = getopt.getopt(argv, 'e:v:r:', ['environment', 'variable-file','region'])
    #if len(opts) == 0 and len(opts) > 3:
    if len(opts) != 3:
        print ('Usage: -e MWAA environment -v variable file location and filename -r aws region')
    else:
        for opt, arg in opts:
            if opt in ("-e"):
                mwaa_env=arg
            elif opt in ("-r"):
                aws_region=arg
            elif opt in ("-v"):
                var_file=arg

        boto3.setup_default_session(region_name="{}".format(aws_region))
        mwaa_env_name = "{}".format(mwaa_env)

        client = boto3.client('mwaa')
        mwaa_cli_token = client.create_cli_token(
            Name=mwaa_env_name
        )
        
        with open ("{}".format(var_file), "r") as myfile:
            fileconf = myfile.read().replace('\n', '')

        json_dictionary = json.loads(fileconf)
        for key in json_dictionary:
            print(key, " ", json_dictionary[key])
            val = (key + " " + json_dictionary[key])
            mwaa_auth_token = 'Bearer ' + mwaa_cli_token['CliToken']
            mwaa_webserver_hostname = 'https://{0}/aws_mwaa/cli'.format(mwaa_cli_token['WebServerHostname'])
            raw_data = "variables -s {0}".format(val)
            mwaa_response = requests.post(
                mwaa_webserver_hostname,
                headers={
                    'Authorization': mwaa_auth_token,
                    'Content-Type': 'text/plain'
                    },
                data=raw_data
                )
            mwaa_std_err_message = base64.b64decode(mwaa_response.json()['stderr']).decode('utf8')
            mwaa_std_out_message = base64.b64decode(mwaa_response.json()['stdout']).decode('utf8')
            print(mwaa_response.status_code)
            print(mwaa_std_err_message)
            print(mwaa_std_out_message)

except:
    print('Use this script with the following options: -e MWAA environment -v variable file location and filename -r aws region')
    print("Unexpected error:", sys.exc_info()[0])
    sys.exit(2)
```

This Python script with three values: 

* -e the name of the MWAA environment,
* -r the AWS region
* -v the local file that we want to parse and create variables from

The script takes each item in the file and then treats them as a single "airflow variable --set" command, iterating through all of them.

Using our variables.json file, we run this against my MWAA 1.x environment as follows:

```
python mwaa-v1-vars.py -e ricsue-dublin -r eu-west-1 -v variables.json
```
Which generates the following output

```
cli_test   newvalue/
200


cli_test2   12341234
200


cli_test3   https://grouplens.org/datasets/movielens/latest/
200
```

So that provides you with a couple of options with MWAA 1.x, now lets look at how we can do this with MWAA 2.x


*MWAA 2.x*

In MWAA 2.x the Airflow commands have changed, so we have updated the script.

```
#!/bin/bash

[ $# -eq 0 ] && echo "Usage: $0 MWAA environment name " && exit

if [[ $2 == "" ]]; then
    dag="variables list"

elif  [ $2 == "get" ] ||  [ $2 == "delete" ] ||  [ $2 == "set" ]; then
    dag="variables $2 $3 $4 $5"

else
    echo "Not a valid command"
    exit 1
fi

CLI_JSON=$(aws mwaa --region $AWS_REGION create-cli-token --name $1) \
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

If we run this as before, you will notice the commands have changed slightly

```
./mwaa-v2-variables.sh ricsue-dublin delete cli_test
./mwaa-v2-variables.sh ricsue-dublin set cli_test "test"
./mwaa-v2-variables.sh ricsue-dublin get cli_test
```

Again, we cannot use the import command, so we can create a python script that will iterate for us. The script is the same as the previous one with the following difference (which is due to the different Airflow command)

```
            raw_data = "variables set {0}".format(val)
```

When we run this python script,

```
python mwaa-v2-vars.py -e ricsue-dublin -r eu-central-1 -v variables.json
```
We get the following output

```
cli_test   newvalue/
200

Variable cli_test created

cli_test2   12341234
200

Variable cli_test2 created

cli_test3   https://bbc.co.uk
200

Variable cli_test3 created
```

**Using the Airflow CLI to view variables**

We might want to check what variables exist in our environment. We can display the current variables within the MWAA metastore using the following scripts. Again, the scripts are version dependant, and this time we are using bash scripts.


*MWAA 1.x*


```
#!/bin/bash


[ $# -eq 0 ] && echo "Usage: $0 MWAA environment name " && exit

if [[ $2 == "" ]]; then
    dag="list_dags"

elif [ $2 == "list_tasks" ] && [[ $3 != "" ]]; then
    dag="$2 $3"
    
elif [ $2 == "list_dags" ] || [ $2 == "version" ]; then
    dag=$2

elif [ $2 == "variables" ] ; then
    dag="$2 $3 $4"

else
    echo "Not a valid command"
    exit 1
fi

CLI_JSON=$(aws mwaa --region $AWS_REGION create-cli-token --name $1) \
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

>Note! If you want to run this in a different region to your AWS cli's default profile, set the AWS_REGION variable to the region you want to run this in

If you run this script with your MWAA environment and then one of the supported options (in this case "variables")

```
./mwaa-cli-v1.sh ricsue-dublin variables
```

We then get the following output, which is as I would have expected as in the previous steps we have created these variables.

```
cli_test
cli_test2
cli_test3
```

We can also retrieve the variables from a MWAA environment using the --get

```
./mwaa-cli-v1.sh ricsue-dublin variables --get cli_test
```
Which returns

```
Output:
newvalue/
Errors:
```

*MWAA 2.x*

The script is very similar to the 1.x script, but has some different default options to take into consideration the differences in what is supported.

```
#!/bin/bash

[ $# -eq 0 ] && echo "Usage: $0 MWAA environment name " && exit

if [[ $2 == "" ]]; then
    dag="cheat-sheet"

elif [ $2 == "version" ] ; then
    dag="version"
    
elif [ $2 == "list_dags" ] ; then
    dag="dags list"

elif [ $2 == "variables" ] ; then
    dag="$2 $3 $4"

else
    echo "Not a valid command"
    exit 1
fi

CLI_JSON=$(aws mwaa --region $AWS_REGION create-cli-token --name $1) \
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

When we run the script as before, using the "variables" options

```
./mwaa-cli-v2.sh ricsue-dublin variables
```

We then get the following output, which is as I would have expected as in the previous steps, we created these variables.

```
cli_test
cli_test2
cli_test3
```

We can also retrieve the variables from a MWAA environment using the get

```
./mwaa-cli-v2.sh ricsue-dublin variables get cli_test
```
Which returns

```
Output:
newvalue/
Errors:
```

### Triggering workflows with parameters via the command line

What if we wanted to trigger our workflows (DAGs) via the command line AND submit a parameter file, either to override existing values or provide inputs to it?

Re-using the following DAG, the DAG either takes values from the existing metastore or are overridden by a supplied set of parameters (for example {"param1":"param1value"}) when triggered.

```
from airflow import DAG
from airflow.operators.bash_operator import BashOperator
from airflow.utils.dates import days_ago

with DAG(
    dag_id="airflow_variables_atruntime",
    schedule_interval=None,
    catchup=False,
    start_date=days_ago(1)) as dag:

    get_var_filename = BashOperator(
        task_id="get_var_filename",
        bash_command="""echo 'You are running this DAG with the following variable file: "{{ dag_run.conf["cli_test"] if dag_run.conf else var.value.cli_test }}"'""",
    )
    get_var_filename = BashOperator(
        task_id="get_var_filename2",
        bash_command='echo "You are running this DAG with the following variable file: \'{{ dag_run.conf["cli_test2"] if dag_run.conf else var.value.cli_test2 }}\'"',
    )
    get_var_filename = BashOperator(
        task_id="get_var_filename3",
        bash_command='echo "You are running this DAG with the following variable file: \'{{ dag_run.conf["cli_test3"] if dag_run.conf else var.value.cli_test3 }}\'"',
    )
```

To trigger a DAG via the cli in MWAA is version specific, so let us take a look at how we would supply and override the variables we have been using. We are going to override cli_test3 with a new value of "http://aws.amazon.com", so will provide the parameter file '{"cli_test3":"http://aws.amazon.com"}'

*MWAA 1.x*

Using the following script, we can submit a parameter file to a specific DAG using the standard airflow trigger_dag command.

```
#!/bin/bash


[ $# -eq 0 ] && echo "Usage: $0 MWAA environment name, name of the DAG and runtime parameters " && exit

if [[ $2 == "" ]]; then
    dag="list_dags"

elif [ $2 == "trigger_dag" ] && [[ $3 != "" ]]; then
    dag="$2 $3 $4 $5"
    
elif [ $2 == "list_dags" ] || [ $2 == "version" ]; then
    dag=$2

elif [ $2 == "variables" ] ; then
    dag="$2 $3 $4 $5"

else
    echo "Not a valid command"
    exit 1
fi

echo $dag

CLI_JSON=$(aws mwaa --region $AWS_REGION create-cli-token --name $1) \
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

We can now run this script with the following command (note how we have to escape "\" the " as this is passed into the script and will otherwise generate a decoding error):

```
./mwaa-v1-run-param.sh ricsue-dublin trigger_dag -c '{\"cli_test3\":\"http://aws.amazon.com\"}' airflow_variables_atruntime
```
And when we look at the output in the logs, we can see that we have successfully triggered the DAG and overridden the parameter

```
[2021-07-27 12:01:07,421] {{bash_operator.py:146}} INFO - Running command: echo "You are running this DAG with the following variable file: 'http://aws.amazon.com'"
[2021-07-27 12:01:07,461] {{bash_operator.py:153}} INFO - Output:
[2021-07-27 12:01:07,494] {{bash_operator.py:157}} INFO - You are running this DAG with the following variable file: 'http://aws.amazon.com'
```

We can apply the same approach when using Python - I have not included a script, but you can modify one of the scripts in the repo.

*MWAA 2.x*

What happens when we try the same approach with MWAA 2.x?

```
#!/bin/bash

AWS_REGION=eu-central-1
[ $# -eq 0 ] && echo "Usage: $0 MWAA environment name, name of the DAG and runtime parameters " && exit

if [[ $2 == "" ]]; then
    dag="dags list"

elif [ $2 == "trigger_dag" ] && [[ $3 != "" ]]; then
    dag="dags trigger $3 $4 $5"
    
elif [ $2 == "list_dags" ] || [ $2 == "version" ]; then
    dag=$2

elif [ $2 == "variables" ] ; then
    dag="$2 $3 $4 $5"

else
    echo "Not a valid command"
    exit 1
fi

echo $dag

CLI_JSON=$(aws mwaa --region $AWS_REGION create-cli-token --name $1) \
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

This time, when we run the script

```
./mwaa-v2-run-param.sh ricsue-dublin trigger_dag -c '{\"cli_test3\":\"http://aws.amazon.com\"}' airflow_variables_atruntime

```

We get a a slightly different response, 
 
```
[2021-07-27 12:17:57,315] {{__init__.py:38}} INFO - Loaded API auth backend: <module 'airflow.api.auth.backend.deny_all' from '/usr/local/lib/python3.7/site-packages/airflow/api/auth/backend/deny_all.py'>
Created <DagRun airflow_variables_atruntime @ 2021-07-27 12:17:57+00:00: manual__2021-07-27T12:17:57+00:00, externally triggered: True>
Errors:
```

but the outcome is still the same

```
[2021-07-27 12:32:25,428] {{bash.py:158}} INFO - Running command: echo 'http://aws.amazon.com'
[2021-07-27 12:32:25,501] {{bash.py:173}} INFO - http://aws.amazon.com
```

Right, we are nearly at the end of this post now. Before finishing, let me introduce another way you can parameterise your DAGs which may be useful for some use cases.

### Other approaches

Another approach that might work for you is incorporating variable changes as part of a CI/CD setup. In a [previous post](https://aws-oss.beachgeek.co.uk/4t), I walked you through creating a simple CI/CD environment for your workflow deployments. In that post, the build stage has a single build task

```
phases:
  build:
    commands:
       - aws s3 sync . s3://{your airflow s3 bucket}/dags/ --delete
```

You can expand upon that and you could pass variables into the build stage in a number of different ways and run a pre-build step before the workflows are deployed. 

In this example we take variables stored in AWS Secrets Manager. 

![secret](https://github.com/094459/blog-mwaa-variables/blob/main/images/airflow-var-secrets.png?raw=true)

Here we can see that the secret blog/airflow/variables/codebuild is storing the name of my variable which is "airflow_secret_variable" and has the value of  "airflow_secret_value".

I can use this in conjunction with CodeBuild to add a step that does a substitution. If I use the following in my DAG

```
demo = "{variable_placeholder}"
```

During the build stage, we can use sed to go through the DAGs (you can change the filter, in this example, I am just going through them all) and it will then substitute the placeholder in the DAG for the value in the AWS Secrets Manager. I can repeat this as many times as I need.

```
version: 0.2

env:
  secrets-manager:
    VARIABLE: "arn:aws:secretsmanager:eu-central-1:704533066374:secret:blog/airflow/variables/codebuild-iIvHYf:airflow_secret_variable"

phases:
  build:
    commands:
      - for file in *.py; do sed -i "s|{variable_placeholder}|${VARIABLE}|g" $file ; done
      - aws s3 sync . s3://{your-airflow-s3}/dags/ --delete
```
Within your DAG, you will have created placeholders (using {variable_placeholder} ) which will then get changed via the sed command. This is the sample DAG that I have locally, in my developer environment.

```
from airflow import DAG
from airflow.operators.bash_operator import BashOperator
from airflow.utils.dates import days_ago

demo = "{variable_placeholder}"

with DAG(
    dag_id="display_changed_variables",
    schedule_interval=None,
    catchup=False,
    start_date=days_ago(1)) as dag:

    get_var_filename = BashOperator(
        task_id="disp_variable",
        bash_command='echo "The value of the variable is: {var}"'.format(var=demo),
    )
```
When I check this in, the pipeline deploys this to the DAGs S3 bucket after processing it. When I check within the Apache Airflow UI, I can see that the transformation has occured

```
...
from airflow.models import Variable
demo = "airflow_secret_value"
with DAG(
...
```
And we can see this in the output of the DAG
```
[2021-07-23 16:35:34,205] {{bash.py:158}} INFO - Running command: echo "The value of the variable is: airflow_secret_value"
[2021-07-23 16:35:34,246] {{bash.py:169}} INFO - Output:
[2021-07-23 16:35:34,276] {{bash.py:173}} INFO - The value of the variable is: airflow_secret_value
```

> **Note!** If you get the following error when trying this approach:
```
[Container] 2021/07/23 14:44:33 Phase context status code: Secrets Manager Error Message: AccessDeniedException: User: arn:aws:sts::704533066374:assumed-role/codebuild-deploy-dags-service-role/AWSCodeBuild-7a8ab216-7c74-4cc6-91d4-f48bcdb99a09 is not authorized to perform: secretsmanager:GetSecretValue on resource: arn:aws:secretsmanager:eu-central-1:704533066374:secret:blog/airflow/variables/codebuild-awsaws
```
> Remember to add the "secretsmanager:GetSecretValue" permission to the CodeBuild execution role. In the above example, this is what I added (yours will be similar, but with different resource names)

```
        {
            "Effect": "Allow",
            "Resource": [
                "arn:aws:secretsmanager:eu-central-1:704533066374:secret:blog/airflow/variables*"
            ],
            "Action": [
                "secretsmanager:GetSecretValue"
            ]
        },
```

This approach might be useful as it in effect localises the variables within the DAG, putting less of a load on the metastore. From Apache Airflow's perspective, these are "hard coded" DAGs, thanks to the build step during deployment that maps the value placeholders with what we want deployed via AWS Secrets Manager. You could of course just use Parameter store as well if you wanted to, or your own codebuild system as most of them provide a capability to do this.

### Conclusion

In this post I showed you how the different options you have when both defining/setting variables within your workflows (DAGs) and how these might be different to your self hosted Apache Airflow. Understanding what you can and cannot do when working in MWAA will help you plan what changes you need to make if you are considering how to run your Apache Airflow workflows.

This is one of the core capabilities within Apache Airflow, and you should look at leveraging these so you can create standardised, re-usable workflows (DAGs).

Please let me know via the comments of any additional questions or perhaps requirements that you have that cannot be met with the approach outlined above.

