---
title: 'Exploring Shell Launch Scripts on Managed Workflows for Apache Airflow (MWAA) and mwaa-local-runner'
date: '2023-04-17'
tags: [ Apache Airflow, mwaa, mwaa-local-runner ]
---

Managed Workflows for Apache Airflow (MWAA) recently launched a new feature that a lot of folk had been asking for, which was the ability to add additional libraries, binaries, or environment variables when launching Airflow workers. If you missed the announcement, [Amazon MWAA now supports Shell Launch Scripts](https://aws-oss.beachgeek.co.uk/2pm), this new capability allows you to easily do this by creating a script and then configuring your MWAA environments to use that script during the start-up phase. The MWAA documentation has been updated to show you how you can use this, and you can read about that in the page, [Using a startup script with Amazon MWAA](https://aws-oss.beachgeek.co.uk/2pn). This is essential reference material for understanding more about what you can do with this new feature.

In this post, I wanted to share how you can use this and also how you can use mwaa-local-runner to validate/test your startup scripts. The latest versions of mwaa-local-runner (2.4.3 and 2.5.1) have been updated to support this.

I assume that you have already got [mwaa-local-runner](https://aws-oss.beachgeek.co.uk/gd) up and running, so if you have not, it is the perfect time to do that now ;-).

**The need for startup scripts**

Before we update out environment, we can take a quick look at an example which will show you how this works. Imagine that you have some standard environment variables you need to set when your tasks are running. This is a common requirement, and so in this example let's say we need to access a new environment variable (called BUILD_ON_OPEN_SOURCE="awesome!"). Will will create a simple DAG that will print out this new environment variable, and see what output we get. What about if we had some java code we wanted to run and we needed a specific Java version. We will have another DAG that will output the details of the Java version, and then look to install the latest version of Amazon Corretto.

This is our sample DAG.

```
from datetime import datetime
from airflow import DAG
from airflow.operators.bash_operator import BashOperator
from airflow.operators.python_operator import PythonOperator
import os


def print_hello():
 print(os.environ['BUILD_ON_OPEN_SOURCE'])
 return 'os.environ["BUILD_ON_OPEN_SOURCE"]'

dag = DAG('startup_script_demo', description='Showing Startup Scripts', schedule_interval=None, start_date=datetime(2017, 3, 20), catchup=False)

java_env = BashOperator(
 task_id="java_env",
 bash_command="java --version",
 dag=dag)

env_variable = PythonOperator(
 task_id='env_variable',
 python_callable=print_hello,
 dag=dag)

java_env >> env_variable
```

When we upload this DAG and execute it, we get the following output.

For the Python environment variables we see

```
  File "/usr/local/airflow/dags/simple-dag.py", line 9, in print_hello
    print(os.environ['BUILD_ON_OPEN_SOURCE'])
  File "/usr/lib/python3.10/os.py", line 680, in __getitem__
    raise KeyError(key) from None
KeyError: 'BUILD_ON_OPEN_SOURCE'
[2023-04-14, 13:13:04 UTC] {{taskinstance.py:1401}} INFO - Marking task as FAILED. 
```

and for the Java task

```
[2023-04-14, 13:12:29 UTC] {{subprocess.py:75}} INFO - Running command: ['/usr/bin/bash', '-c', 'java --version']
[2023-04-14, 13:12:29 UTC] {{subprocess.py:86}} INFO - Output:
[2023-04-14, 13:12:29 UTC] {{subprocess.py:93}} INFO - Unrecognized option: --version
[2023-04-14, 13:12:29 UTC] {{subprocess.py:93}} INFO - Error: Could not create the Java Virtual Machine.
[2023-04-14, 13:12:29 UTC] {{subprocess.py:93}} INFO - Error: A fatal exception has occurred. Program will exit.
[2023-04-14, 13:12:29 UTC] {{subprocess.py:97}} INFO - Command exited with return code 1
[2023-04-14, 13:12:29 UTC] {{taskinstance.py:1851}} ERROR - Task failed with exception
Traceback (most recent call last):
  File "/usr/local/airflow/.local/lib/python3.10/site-packages/airflow/operators/bash.py", line 196, in execute
    raise AirflowException(
airflow.exceptions.AirflowException: Bash command failed. The command returned a non-zero exit code 1.
```

As we can see, the tasks fail. We will use startup scripts to help address both issues. Before we do that though, I will show you how you create that script.

**How does startup scripts work with mwaa-local-runner**

When using MWAA, you can now specify a startup script via the environment configuration screen. It is good practice however, to use mwaa-local-runner to test this out before you make your changes. mwaa-local-runner has been updated to include some new scripts that mimic how the MWAA managed service works. We can see a new folder in the root of the mwaa-local-runner directory (called startup) and in here there is a script called startup.sh. It is this script we need to modify. When you check out mwaa-local-runner for the first time, this will be empty with just a placeholder.

![simple workflow of how startup scripts work](https://ricsuepublicresources.s3.eu-west-1.amazonaws.com/images/airflow-variables.png)

With this new capability being released, there is a new command to the mwaa-local-env command called "test-startup-script" which will allow you to validate your startup scripts in your mwaa-local-runner setup. 

**Updating your existing mwaa-local-runner**

As of writing, there is a small ["feature"](https://github.com/aws/aws-mwaa-local-runner/issues/244) with mwaa-local-runner, which means we have to make s small change to our mwaa-local-runner before we can use this. We will need to modify the "entrypoint.sh" script in the docker/scripts folder, and update it by adding a new line " source stored_env" between the execute_start_script and the ariflow db init, as follows:

```
    install_requirements
    execute_startup_script
    source stored_env    <-- added this
    airflow db init
```

We need to rebuild our mwaa-local-runner image, but as we are just changing the entrypoint.sh this should not take too long

```
./mwaa-local-env build-image
```

Our new version should now be read to go.

**Testing a startup script**

We are now ready to create and then test our first startup script. We have already created a folder and empty script (above) so we open and edit the "startup_script/startup.sh" file.

The mwaa-local-runner is using an Amazon Linux base image, so we can use the [guidance for Amazon Corretto here](https://docs.aws.amazon.com/corretto/latest/corretto-17-ug/amazon-linux-install.html) on the right steps to install this.

```
#!/bin/sh

echo "Running sample startup script."

export BUILD_ON_OPEN_SOURCE="awesome"

sudo yum install java-17-amazon-corretto-headless -y

```

We save this file, and now we can use the new "mwaa-local-runner test-startup-script" command to see if this is ok

```
./mwaa-local-env test-startup-script
```
which we will see the following output

```
Container amazon/mwaa-local:2_4 exists. Skipping build
Running sample startup script.
awesome
Loaded plugins: ovl, priorities
amzn2-core                                                                                                                                                                       | 3.7 kB  00:00:00     
(1/3): amzn2-core/2/x86_64/group_gz                                                                                                                                              | 2.5 kB  00:00:00     
(2/3): amzn2-core/2/x86_64/updateinfo                                                                                                                                            | 586 kB  00:00:00     
(3/3): amzn2-core/2/x86_64/primary_db                                                                                                                                            |  71 MB  00:00:24     
Resolving Dependencies
--> Running transaction check
---> Package java-17-amazon-corretto-headless.x86_64 1:17.0.6+10-1.amzn2.1 will be installed
--> Processing Dependency: dejavu-sans-mono-fonts for package: 1:java-17-amazon-corretto-headless-17.0.6+10-1.amzn2.1.x86_64
--> Processing Dependency: dejavu-serif-fonts for package: 1:java-17-amazon-corretto-headless-17.0.6+10-1.amzn2.1.x86_64
--> Running transaction check
---> Package dejavu-sans-mono-fonts.noarch 0:2.33-6.amzn2 will be installed
---> Package dejavu-serif-fonts.noarch 0:2.33-6.amzn2 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

===============================================================================================================================================================================
 Package                                                        Arch                                 Version                                             Repository                                Size
===============================================================================================================================================================================
Installing:
 java-17-amazon-corretto-headless                               x86_64                               1:17.0.6+10-1.amzn2.1                               amzn2-core                                94 M
Installing for dependencies:
 dejavu-sans-mono-fonts                                         noarch                               2.33-6.amzn2                                        amzn2-core                               433 k
 dejavu-serif-fonts                                             noarch                               2.33-6.amzn2                                        amzn2-core                               777 k

Transaction Summary
===============================================================================================================================================================================
Install  1 Package (+2 Dependent packages)

Total download size: 95 M
Installed size: 240 M
Is this ok [y/d/N]: ^C/entrypoint.sh: line 70: stored_env: No such file or directory
(base)  @094459  ~/Projects/airflow/cicd/demos/local-airflow-dev/mwaa-local  ./mwaa-local-env test-startup-script
Container amazon/mwaa-local:2_4 exists. Skipping build
Running sample startup script.
Loaded plugins: ovl, priorities
amzn2-core                                                                                                                                                                       | 3.7 kB  00:00:00     
(1/3): amzn2-core/2/x86_64/group_gz                                                                                                                                              | 2.5 kB  00:00:00     
(2/3): amzn2-core/2/x86_64/updateinfo                                                                                                                                            | 586 kB  00:00:00     
(3/3): amzn2-core/2/x86_64/primary_db                                                                                                                                            |  71 MB  00:00:22     
Resolving Dependencies
--> Running transaction check
---> Package java-17-amazon-corretto-headless.x86_64 1:17.0.6+10-1.amzn2.1 will be installed
--> Processing Dependency: dejavu-sans-mono-fonts for package: 1:java-17-amazon-corretto-headless-17.0.6+10-1.amzn2.1.x86_64
--> Processing Dependency: dejavu-serif-fonts for package: 1:java-17-amazon-corretto-headless-17.0.6+10-1.amzn2.1.x86_64
--> Running transaction check
---> Package dejavu-sans-mono-fonts.noarch 0:2.33-6.amzn2 will be installed
---> Package dejavu-serif-fonts.noarch 0:2.33-6.amzn2 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

Installing:
 java-17-amazon-corretto-headless                               x86_64                               1:17.0.6+10-1.amzn2.1                               amzn2-core                                94 M
Installing for dependencies:
 dejavu-sans-mono-fonts                                         noarch                               2.33-6.amzn2                                        amzn2-core                               433 k
 dejavu-serif-fonts                                             noarch                               2.33-6.amzn2                                        amzn2-core                               777 k

Transaction Summary
===============================================================================================================================================================================
Install  1 Package (+2 Dependent packages)

Total download size: 95 M
Installed size: 240 M
Downloading packages:
(1/3): dejavu-sans-mono-fonts-2.33-6.amzn2.noarch.rpm                                                                                                                            | 433 kB  00:00:00     
(2/3): dejavu-serif-fonts-2.33-6.amzn2.noarch.rpm                                                                                                                                | 777 kB  00:00:00     
(3/3): java-17-amazon-corretto-headless-17.0.6+10-1.amzn2.1.x86_64.rpm                                                                                                           |  94 MB  00:00:30     
                                               

Complete!
Finished running startup script. Execution time: 75.612s.
Running verification
Verification completed
```

As we can see, the startup script has been processed with no errors. Note the output of "awesome" at the beginning as well as the output of the package installation.

What if we sabotage the script, and add an addition "s" at the end to simulate a typo. If we do that we can see that we get different output

```
No package java-17-amazon-corretto-headlesss available.
Error: Nothing to do
Finished running startup script. Execution time: 29.105s.
Running verification
Verification completed
```
Which means we can then fix this before we make that change to our MWAA environments. Phew, that is a good catch.

**Running our DAG and see our startup script changes**

We can now run mwaa-local-runner locally, and re-run those DAGs. As it starts you should notice that the script is executed and you will see (in this instance) Amazon Corretto being installed.

```
./mwaa-local-env start
..
..
aws-mwaa-local-runner-2_4-local-runner-1  | Requirement already satisfied: anyio==3.* in ./.local/lib/python3.10/site-packages (from httpcore<0.16.0,>=0.15.0->httpx->apache-airflow>=2.3.0->apache-airflow-providers-amazon==7.3.0->-r /usr/local/airflow/requirements/requirements.txt (line 4)) (3.6.2)
aws-mwaa-local-runner-2_4-local-runner-1  | Requirement already satisfied: h11<0.13,>=0.11 in ./.local/lib/python3.10/site-packages (from httpcore<0.16.0,>=0.15.0->httpx->apache-airflow>=2.3.0->apache-airflow-providers-amazon==7.3.0->-r /usr/local/airflow/requirements/requirements.txt (line 4)) (0.12.0)
aws-mwaa-local-runner-2_4-local-runner-1  | Running sample startup script.
aws-mwaa-local-runner-2_4-local-runner-1  | Loaded plugins: ovl, priorities
aws-mwaa-local-runner-2_4-local-runner-1  | Resolving Dependencies
aws-mwaa-local-runner-2_4-local-runner-1  | --> Running transaction check
aws-mwaa-local-runner-2_4-local-runner-1  | ---> Package java-17-amazon-corretto-headless.x86_64 1:17.0.6+10-1.amzn2.1 will be installed
..
```

If we now wait until it finishes its boot sequence, when we re-try our DAGS we get the following output.

For the Python environment variables we see

```
[2023-04-17, 18:13:29 UTC] {{logging_mixin.py:137}} INFO - awesome
[2023-04-17, 18:13:29 UTC] {{python.py:177}} INFO - Done. Returned value was: os.environ["BUILD_ON_OPEN_SOURCE"]
[2023-04-17, 18:13:29 UTC] {{taskinstance.py:1401}} INFO - Marking task as SUCCESS. dag_id=startup_script_demo, task_id=env_variable, execution_date=20230417T181324, start_date=20230417T181328, end_date=20230417T181329
[2023-04-17, 18:13:29 UTC] {{local_task_job.py:159}} INFO - Task exited with return code 0
[
```

and for the Java task

```
[2023-04-14, 13:56:05 UTC] {{subprocess.py:75}} INFO - Running command: ['/usr/bin/bash', '-c', 'java --version']
[2023-04-14, 13:56:05 UTC] {{subprocess.py:86}} INFO - Output:
[2023-04-14, 13:56:05 UTC] {{subprocess.py:93}} INFO - openjdk 17.0.6 2023-01-17 LTS
[2023-04-14, 13:56:05 UTC] {{subprocess.py:93}} INFO - OpenJDK Runtime Environment Corretto-17.0.6.10.1 (build 17.0.6+10-LTS)
[2023-04-14, 13:56:05 UTC] {{subprocess.py:93}} INFO - OpenJDK 64-Bit Server VM Corretto-17.0.6.10.1 (build 17.0.6+10-LTS, mixed mode, sharing)
[2023-04-14, 13:56:05 UTC] {{subprocess.py:97}} INFO - Command exited with return code 0
```

**Conclusion**

This short post reminded you of the new feature of MWAA that allows you to tailor the tools, libraries, and environment configuration details you need for your Airflow workers. You can use mwaa-local-runner as a great development tool to help you test your startup scripts, and this post showed you how you can set this up by using a simple example.  Make sure you check out the MWAA documentation. [Using a startup script with Amazon MWAA](https://aws-oss.beachgeek.co.uk/2pn), to dive deeper into this capability. This is essential reference material for understanding more about what you can do with this new feature.

If you have found this blog post helpful, please give me some feedback by completing [this very short survey here](https://pulse.buildon.aws/survey/D4L9Y3II)