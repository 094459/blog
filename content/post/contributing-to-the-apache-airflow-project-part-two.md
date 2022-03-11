---
title: 'Contributing to the Apache Airflow project - Part Two'
date: '2022-03-11'
tags: [ blog, Apache Airflow]
---

*This is the second and concluding post providing an overview of the experience and journey contributing to the Apache Airflow project. You can catch [Part One here](https://dev.to/aws/contributing-to-the-apache-airflow-project-37mf).*

### Contributing to Apache Airflow - Part Deux

In [Part One](https://dev.to/aws/contributing-to-the-apache-airflow-project-37mf) of this series, we took our first steps in contributing to the Apache Airflow project. With a little bit more knowledge and experience, our first interactions with the Airflow community, we are ready to start exploring how the code works and see how we might go about fixing this.

#### Making sense of the code

**Bootstrapping my test DAG**

The first thing I wanted to do was make sure that my test DAG works in my development setup. This is going to make everything easier later on, as I have a good starting point. I start Breeze (using ./breeze start-airflow"), and then when started, I eventually figure out I need to copy my DAG into the "/files/dags" folder (for some reason I had just assumed it would automatically get loaded from the /opt/airflow/dags folder, but it was simple enough to just copy it).

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
    test = ECSOperator(
    task_id="test",
    dag=dag,
    aws_conn_id="aws_default",
    cluster="test-hybrid",
    task_definition="test",
    launch_type="EC2",
    overrides={
        "containerOverrides": [ ],
    },
    awslogs_group="/ecs/test",
    awslogs_stream_prefix="ecs",
    )

    test
```

It didn't work straight away, as I needed to create a new "aws_conn" connection (called aws_default) from the Apache Airflow UI. I added my ACCESS and SECRET ID, and then in the extras I added region info - [this is all well covered in the Apache Airflow documentation](https://airflow.apache.org/docs/apache-airflow/1.10.11/howto/connection/aws.html). Once I had completed that, I triggered the DAG and could see that I could execute a task on Amazon ECS and everything was working as expected.

> Note! Within the Breeze environment, I realised /root/airflow/logs were were the various Apache Airflow processes were writing files, and this helped me figure out what was going on when I encountered problems deploying this DAG. You can use "airflow info" to get useful information when trying to figure things out. For example, it told me that apache-airflow-providers-amazon was v3.0.0 and I am pretty sure that might be important later on
> 

**Making a small change**

To make sure I understand all the moving parts, my initial plan is to make a small change and just change the text message that is returned by the ECS operator. As this should not be a breaking change, it just help me understand how to package up and then run the changed code in the dev setup so that when I make a potentially breaking change, I can spend less time chasing red herrings.

First of all, back to the docs the section in the CONTRIBUTION doc around [Provider packages](https://github.com/apache/airflow/blob/main/CONTRIBUTING.rst#provider-packages) seems pretty key and tells me that I should just be able to make changes and they will be updated in my dev environment. Let's see if this works...

**ECSOperator**

Under the airflow/providers/amazon/aws/operators/ folder, we have the only file that appears to be specific to Amazon ECS, called "ecs.py". Opening this file up in Cloud9, I make a quick change (changing the text on line 281) from

```
'Running ECS Task - Task definition: %s - on cluster %s', self.task_definition, self.cluster
```
to
```
'Running ECS Task XX - Task definition: %s - on cluster %s', self.task_definition, self.cluster
```
And then go back to the Apache Airflow UI and trigger the DAG. I am very grateful when I see the following appear in the log:

```
AIRFLOW_CTX_EXECUTION_DATE=2022-02-10T17:24:52.961479+00:00
AIRFLOW_CTX_DAG_RUN_ID=manual__2022-02-10T17:24:52.961479+00:00
[2022-02-10, 17:24:53 UTC] {ecs.py:281} INFO - Running ECS Task XX - Task definition: test - on cluster test-hybrid
[2022-02-10, 17:24:53 UTC] {ecs.py:283} INFO - EcsOperator overrides: {'containerOverrides': []}
[2022-02-10, 17:24:53 UTC] {base_aws.py:190} INFO - Credentials retrieved from login
```
We are looking good. We know we can make changes and they will be picked up. Another step forward.

#### Unexpected results

**When is a fix, not a fix**

In part one, I shared how I had raised this issue as a result of my tests running the ECS Operator task using a launchtype of "EXTERNAL". It was only at the previous stage that I realised something, something that was important. In the original, failing DAG, I can specified the ECS logging as follows

```
    awslogs_group="/ecs/test",
    awslogs_stream_prefix="ecs",
```

It was during some tests, unrelated to this work, that I realised that if this information was not configured correctly, and the IAM permissions not done properly, the tasks would fail from within the Amazon ECS console (i.e. nothing related to Apache Airflow, or the ECS Operator). It was only when kicking off the above, that I realised that I had incorrectly configured the logs.

I changed the DAG to as follows:

```
from airflow import DAG
from datetime import datetime, timedelta
from airflow.providers.amazon.aws.operators.ecs import ECSOperator


default_args = {
    'owner': 'ubuntu',
    'start_date': datetime(2019, 8, 14),
    'retry_delay': timedelta(seconds=60*60)
}

with DAG('airflow_dag_test_external', catchup=False, default_args=default_args, schedule_interval=None) as dag:
    test = ECSOperator(
    task_id="test",
    dag=dag,
    cluster="test-hybrid",
    task_definition="test-external",
    launch_type="EXTERNAL",
    overrides={
        "containerOverrides": [ ],
    },
    awslogs_group="/ecs/test-external",
    awslogs_stream_prefix="ecs",
    )

    test
```

With the launchtype set to EXTERNAL, but crucially (and what I had failed to do when I had tested it the first time) setting the logging to the correct AWS CloudWatch logs group and stream prefix. From within Breeze, and uploaded this DAG, and kicked it off.....and it worked! To be 100% sure, I take this DAG and upload it into my Managed Workflows for Apache Airflow (MWAA) DAGs folder, wait a few seconds and then trigger that DAG. Yup, it definitely works. The script runs, does its ETL stuff and records everything in the AWS CloudWatch log group.

Oh dear, all this time, the issue was not that the ECS Operator did not support the launchtype of "EXTERNAL" but that I had incorrectly configured the logging within the ECS Task.

**Improving the ECS Operator**

Ok, so whilst we now realise we do not need to "fix" this issue, what we can do is make some minor changes to help document that this new launchtype is supported and working.

The first thing to do is update the ecs.py line 172 so that it now reads

```
    :param launch_type: the launch type on which to run your task ('EC2', 'EXTERNAL', or 'FARGATE')
```

We want to add a new test as well, and so looking at the tests in the tests folder, we find that "test_ecs.py" is a good candidate. From line 100, we make a small change so that it includes a test run for the EXTERNAL launch type

```
   @parameterized.expand(
        [
            [
                'EC2',
                None,
                None,
                None,
                {'launchType': 'EC2'},
            ],
            [
                'EXTERNAL',
                None,
                None,
                None,
                {'launchType': 'EXTERNAL'},
            ],
            [
                'FARGATE',
                None,
                'LATEST',
                None,
                {'launchType': 'FARGATE', 'platformVersion': 'LATEST'},
            ],
...
```

We validate this by running

```
./breeze tests tests/providers/amazon/aws/operators/test_ecs.py
```

And we get the following output

```
(94 durations < 0.005s hidden.  Use -vv to show these durations.)
===== 43 passed, 33 warnings in 10.93s 
```

> Note! We know this new test has been accepted, as before adding the test, when you run this command you only get 42 passed tests.
> 

The final improvement we can make is to add an example DAG that shows this working. We already have an example_ecs_fargate.py, so I create a new one called example_ecs_ec2.py. This example can be used for both EC2 and EXTERNAL launch types.

**Static code check**

One final thing that needs to be done for contributions is to run and fix all the static checks. Whilst I do not think that this minor change will need to run these, I wanted to follow through the standard process. The [Static code checks](https://github.com/apache/airflow/blob/main/STATIC_CODE_CHECKS.rst) doc provides everything you need to know.

In my Cloud9 environment I first install the required tool

```
pip install pre-commit
```
and then run it manually via
```
pre-commit run
```

> **Note!** The first time I ran this it generated an error which was easily fixed as I had been using Python 2.7, by changing to pip3 it installed the latest version.
> 
> ```
> [ERROR] The hook `black` requires pre-commit version 2.9.2 but version 1.21.0 is installed.  Perhaps run `pip > install --upgrade pre-commit`.
> ```

Which will generate output and take approx 10-15 minutes to complete.

```
pre-commit run --all-files
```

When I ran this, you will get a lot of output. Some of the more interesting ones I saw from the files that I submitted included the following:

```
Add license for all Python files.........................................................Failed
- hook id: insert-license
- exit code: 1
- files were modified by this hook

reformatted airflow/providers/amazon/aws/example_dags/example_ecs_ec2.py
reformatted dags/ecs-external-test.py
All done! ✨ 🍰 ✨
2 files reformatted, 2727 files left unchanged.
All done! ✨ 🍰 ✨
491 files left unchanged.

trim trailing whitespace.................................................................Failed
- hook id: trailing-whitespace
- exit code: 1
- files were modified by this hook

Fixing airflow/providers/amazon/aws/example_dags/example_ecs_ec2.py

```

The main thing for me was that all tests PASSED, and I just needed to review and accept the changes above which led to a new local commit.

So, we now have our "change" ready - one new file, and two updates to the existing code base. We now commit these to our local working fork of Apache Airflow, making sure that our commit message provides a link to the issue raised in GitHub.

```
git add .
git commit -m "https://github.com/apache/airflow/issues/21321 - add additional documentation and test cases"
git push
```

Next step, moving through the process to get these included upstream.

#### Submitting the Pull Request (PR)

If we review the Apache Airflow Contributor doc, we can see the next step is [Step 4. Prepare PR](https://github.com/apache/airflow/blob/main/CONTRIBUTING.rst#step-4-prepare-pr).

Following these steps leads us to the first thing we need to do, [rebase our fork](https://github.com/apache/airflow/blob/main/CONTRIBUTING.rst#how-to-rebase-pr). As the doc says, this is the approach used within the Apache Airflow project. Whilst I understand the concepts behind rebasing the fork, this is the bit I probably struggled with the most. 

From my local repo, I first sync my local fork with Apache Airflow main. The doc provides [a link which shows you how you can do this from the GitHub UI](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/syncing-a-fork#syncing-a-fork-from-the-web-ui).

Once synced I committed my local changes and then from the GitHub UI [submitted my PR](https://github.com/apache/airflow/pull/22093). The Apache Airflow maintainers are super responsive, and I quickly got contacted about the PR with some suggestions on how to improve it. I had also noticed that one of the automated tests had failed (the Documentation tests, it turns out in my new example DAG, I had used the deprecated ECSOperator rather than EcsOperator - good catch!).

**Documentation**

I somehow missed the [Apache Airflow documentation guide](https://github.com/apache/airflow/blob/main/docs/README.rst) which aside from sharing how documentation works, provides commands that allow you to build the docs locally so you can check your changes by running:

```
./breeze build-docs
```

It was at this point that I saw lots of errors. Apache Airflow uses Sphinx to generate the documentation, and I had assumed it was going to be in markdown format. A lot of the markdown I added was generating errors. To save time, you can get the docs to rebuild just the provider package you were working on (this is covered in the [Apache Airflow documentation guide](https://github.com/apache/airflow/blob/main/docs/README.rst), and I found running this command provided me with a full list  ./breeze build-docs -- --help)

```
./breeze build-docs -- --package-filter apache-airflow-providers-amazon
```

To check the document is looking good, you can run the documentation server by using this command:

```
docs/start_doc_server.sh
```

and then accessing it via a browser. I highly recommend you try this out, as the first few attempts what I thought my doc update would look like vs what actually appeared was very different!

> **Note!** There is a dedicated channel in the Apache Airflow community for documentation, and they pointed me towards [this guide on Sphinx](https://www.sphinx-doc.org/en/master/usage/restructuredtext/index.html).

One thing I would say, is ALWAYS run ```pre-commit run --all-files``` before you commit your docs. The docs are very fussy (which is a good thing), and even a space or tab will cause the build to fail.

**Submitting the PR**

After fixing the issue and updating the [ECS Operator "How to" guide](https://github.com/apache/airflow/blob/main/docs/apache-airflow-providers-amazon/operators/ecs.rst), and then testing I pushed my changes and this triggered the automatic build process.

As this was my first PR, whilst all the checks ran through OK, it was good to have one of the maintainers go through and make sure everything was up to standard.


#### Conclusion

So what did I learn going through the process of contributing this update to the Apache Airflow project? I would summarise the key things as:

* The Apache Airflow project is well organised and has comprehensive documentation that makes it easy to know what is expected when contributing to this project.
* Joining some of the mailing lists made me appreciate how much collaboration is going on within the project across a very diverse set of developers.
* Engaging with the Apache Airflow via the online forums (Slack in my case) was a great way to ask for help, and I found the various channels very welcoming and helpful.
* The journey from issue to pull request may not take you where you think, but that all contributions are valuable.
* From a tooling perspective, Cloud9 really worked well for me and I have kept my Apache Airflow "contribution" workspace hibernated - I am sure I will be back soon, so it is good to have everything already set up and ready to go. I really though Breeze made it as...well breeze to do a lot of the heavy lifting, and it certainly made my life easier so well worth taking the time to get to know it.
* Running the static tests would have saved me a lot of time, and reduced the burden on the Apache Airflow maintainers and build servers, and something I will focus more attention in future contributions.
* I struggled with the documentation, and it took much longer than I thought. I probably spent 2-3 times longer, and it has definitely made me think twice about how I should approach this in the future. I guess I struggled with the cognitive load of moving from markdown to sphinx. 
* The mechanism for testing and checking the documentation is really good, and you get a high degree of certainty that your documentation changes are going to be good.