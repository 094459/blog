---
title: 'Automating your ELT Workflows with Managed Workflows for Apache Airflow - Part Two'
date: '2021-04-21'
tags: [Apache Airflow, mwaa, elt, Apache Hive, Presto, Amazon EMR]
---
### Part Two - Automating Amazon EMR

In [Part One](https://dev.to/aws/automating-your-elt-workflows-with-managed-workflows-for-apache-airflow-4bjg), we automated an example ELT workflow on Amazon Athena using Apache Airflow. In this post, Part Two, we will do the same thing but automate the same example ELT workflow using Amazon EMR.

Make sure you recap the setup from Part One. All the code so you can reproduce this yourself can be found in the [GitHub repository here](https://github.com/094459/devday-elt-automation).
	
**Automating Amazon EMR**

To recap: We are using the Movielens dataset, loaded it into our data lake on Amazon S3 and we have been asked to a) create a new table with a subset of the information we care about, in this instance a particular genre of films, and b) create a new file with the same subset of information available in the data lake.

As part of the set of manual steps we are trying to automate, we are using Amazon EMR (again as for the previous post, if you want to see those manual steps, refer to the documentation in the GitHub repository) together with some Apache Hive and Presto SQL scripts to create tables and export files . As we are automating this, a lot of the stuff we would not need to do because we absorb that as part of the manual work (for example, I already have a database called XX, so I do not need to re-create that) we need to build into the workflow. So at a high level the steps look like:


* Create our Apache Hive and Presto SQL scripts and upload those to a location on Amazon S3
* Check to see if a database exists and create it if it does not exist
* Create tables to import the movie and ratings data (using the scripts we uploaded)
* Create a new table that just contains the information we are looking for (in this example, films of a particular genre)
* Export the new table as a csv file (again using the scripts we already uploaded)
* Move the export csv file to a new location in the data lake
* Clean up and shut down any resources so we can minimise the cost of running this operation

Not surprisingly, this workflow begins in a very similar way to the previous one. However, this time we are using Amazon EMR and if we look at the available Apache Airflow operators we can see that there is an Amazon EMR operator which will make our life easy. We can take a look at the documentation for this operator at the Apache Airflow website, [Amazon EMR Operators](https://airflow.apache.org/docs/apache-airflow-providers-amazon/stable/operators/emr.html)

As part of our workflow, we want to create an Amazon EMR cluster, add some steps to run some of the Presto and Apache Hive queries, and then terminate the cluster so we need to add those operators (EmrCreateJobFlowOperator, EmrAddStepsOperator, EmrTerminateJobFlowOperator and EmrStepSensor) in our DAG

```
from airflow import DAG, settings, secrets
from airflow.operators.python_operator import PythonOperator, BranchPythonOperator
from airflow.operators.dummy_operator import DummyOperator

from airflow.contrib.operators.emr_add_steps_operator import EmrAddStepsOperator
from airflow.contrib.operators.emr_create_job_flow_operator import EmrCreateJobFlowOperator
from airflow.contrib.operators.emr_terminate_job_flow_operator import EmrTerminateJobFlowOperator
from airflow.contrib.sensors.emr_step_sensor import EmrStepSensor

from airflow.models import Variable
from airflow.utils.trigger_rule import TriggerRule
from airflow.utils.dates import days_ago
import os
import sys
import boto3
import time
```
I next part of our workflow is the same, except this time we have added some more variables. In the previous workflow I had hardcoded the genre so this time I wanted to add it as a variable meaning we could create a single workflow, parameterise it and then run it as many times as we needed, just having to change that variable "genre" and "genre_t"

```
s3_dlake = Variable.get("s3_dlake", default_var="undefined")
emr_db = Variable.get("emr_db", default_var="undefined")
emr_output = Variable.get("emr_output", default_var="undefined")
genre = Variable.get("emr_genre", default_var="undefined")
genre_t = Variable.get("emr_genre_table", default_var="undefined")
```
If we look at the steps we are looking to automate, the first one is to upload our Apache Hive and Presto scripts to a location on Amazon S3 where we can run them from our Amazon EMR steps. We could just create these outside of Apache Airflow and upload them, and this is an option. In this walkthrough however, I am going to create those scripts using the same variables we have defined to make sure that those scripts change dynamically as our needs change.

To do this I am going to define a new task called "create_emr_scripts" using the PythonOperator.

```
create_emr_scripts = PythonOperator (
	task_id='create_emr_scripts',
	provide_context=True,
	python_callable=py_create_emr_scripts,
	dag=dag
	)
```

I need to create a supporting function called "py_create_emr_scripts" so lets take a look at this code. This code writes five files to the Amazon S3 location {s3_dlake}/scripts, each file corresponding to the SQL we created as part of the manual steps. 
```
def py_create_emr_scripts(**kwargs):
    s3 = boto3.resource('s3')
    print("Creating scripts which will be executed by Amazon EMR - will overwrite existing scripts")
    # create create-film-db.hql
    object1 = s3.Object(s3_dlake, 'scripts/create-film-db.hql')
    object1.put(Body=HIVE_CREATE_DB)
    # create create-film-db-tables.hql
    object2 = s3.Object(s3_dlake, 'scripts/create-film-db-tables.hql')
    object2.put(Body=HIVE_CREATE_DB_TABLES)
    # create create-genre-film-table.hql
    object3 = s3.Object(s3_dlake, 'scripts/create-genre-film-table.hql')
    object3.put(Body=HIVE_CREATE_GENRE_TABLE)
    # create create-genre.sql
    object4 = s3.Object(s3_dlake, 'scripts/create-genre.sql')
    object4.put(Body=PRESTO_SQL_GEN_GENRE_CSV)
    # create run-presto-query.sh
    object5 = s3.Object(s3_dlake, 'scripts/run-presto-query.sh')
    object5.put(Body=PRESTO_SCRIPT_RUN_EXPFILE) 
```

These variables (HIVE_CREATE_DB, HIVE_CREATE_DB_TABLES, etc) are just defined as follows in the workflow:

```
HIVE_CREATE_DB = """
create database {database}; 
""".format(database=emr_db)

HIVE_CREATE_DB_TABLES = """
CREATE EXTERNAL TABLE {database}.movies (
    movieId INT,
    title   STRING,
    genres  STRING

) ROW FORMAT DELIMITED FIELDS TERMINATED BY ','
  LOCATION 's3://{datalake}/movielens/movies/';

CREATE EXTERNAL TABLE {database}.ratings (
    userId INT,
    movieId INT,
    rating INT,
    timestampId TIMESTAMP

) ROW FORMAT DELIMITED FIELDS TERMINATED BY ','
  LOCATION 's3://{datalake}/movielens/ratings-alt/';
""".format(database=emr_db,datalake=s3_dlake)

HIVE_CREATE_GENRE_TABLE = """
CREATE EXTERNAL TABLE {database}.{genre_t} (
    title   STRING,
    year    INT,
    rating  INT

) ROW FORMAT DELIMITED FIELDS TERMINATED BY '\t'
  LOCATION 's3://{datalake}/movielens/{genre}/';
""".format(database=emr_db,genre=genre,datalake=s3_dlake,genre_t=genre_t)

PRESTO_SCRIPT_RUN_EXPFILE = """
#!/bin/bash
aws s3 cp s3://{datalake}/scripts/create-genre.sql .
presto-cli --catalog hive -f create-genre.sql --output-format TSV > {genre_t}-films.tsv
aws s3 cp {genre_t}-films.tsv s3://{datalake}/movielens/{genre}/
""".format(database=emr_db,genre=genre,datalake=s3_dlake,genre_t=genre_t)

PRESTO_SQL_GEN_GENRE_CSV = """
WITH {genre}data AS (
SELECT REPLACE ( m.title , '"' , '' ) as title, r.rating
FROM {database}.movies m
INNER JOIN (SELECT rating, movieId FROM {database}.ratings) r on m.movieId = r.movieId WHERE REGEXP_LIKE (genres, '{genre}')
  )
SELECT substr(title,1, LENGTH(title) -6) as title, replace(substr(trim(title),-5),')','') as year, AVG(rating) as avrating from {genre}data GROUP BY title ORDER BY year DESC,  title ASC ;
""".format(database=emr_db,genre=genre)
```
As you can see, we are using standard python to substitute values in the variables so we have dynamically generated scripts which will launch when our Amazon EMR steps start.

If we now add at the bottom of the workflow the dependency/relationship details (we only have one task defined so far, the rest is just supporting functions and code) we end up with:

```
from airflow import DAG, settings, secrets
from airflow.operators.python_operator import PythonOperator, BranchPythonOperator
from airflow.operators.dummy_operator import DummyOperator

from airflow.contrib.operators.emr_add_steps_operator import EmrAddStepsOperator
from airflow.contrib.operators.emr_create_job_flow_operator import EmrCreateJobFlowOperator
from airflow.contrib.operators.emr_terminate_job_flow_operator import EmrTerminateJobFlowOperator
from airflow.contrib.sensors.emr_step_sensor import EmrStepSensor

from airflow.models import Variable
from airflow.utils.trigger_rule import TriggerRule
from airflow.utils.dates import days_ago
import os
import sys
import boto3
import time

default_args = {
    'owner': 'airflow',
    'depends_on_past': False,
    'email': ['airflow@example.com'],
    'email_on_failure': False,
    'email_on_retry': False,
}

DAG_ID = os.path.basename(__file__).replace('.py', '')

dag = DAG(
    dag_id=DAG_ID,
    default_args=default_args,
    description='DevDay EMR DAG',
    schedule_interval=None,
    start_date=days_ago(2),
    tags=['devday','demo'],
)

s3_dlake = Variable.get("s3_dlake", default_var="undefined")
emr_db = Variable.get("emr_db", default_var="undefined")
emr_output = Variable.get("emr_output", default_var="undefined")
genre = Variable.get("emr_genre", default_var="undefined")
genre_t = Variable.get("emr_genre_table", default_var="undefined")

HIVE_CREATE_DB = """
create database {database}; 
""".format(database=emr_db)

HIVE_CREATE_DB_TABLES = """
CREATE EXTERNAL TABLE {database}.movies (
    movieId INT,
    title   STRING,
    genres  STRING

) ROW FORMAT DELIMITED FIELDS TERMINATED BY ','
  LOCATION 's3://{datalake}/movielens/movies/';

CREATE EXTERNAL TABLE {database}.ratings (
    userId INT,
    movieId INT,
    rating INT,
    timestampId TIMESTAMP

) ROW FORMAT DELIMITED FIELDS TERMINATED BY ','
  LOCATION 's3://{datalake}/movielens/ratings-alt/';
""".format(database=emr_db,datalake=s3_dlake)

HIVE_CREATE_GENRE_TABLE = """
CREATE EXTERNAL TABLE {database}.{genre_t} (
    title   STRING,
    year    INT,
    rating  INT

) ROW FORMAT DELIMITED FIELDS TERMINATED BY '\t'
  LOCATION 's3://{datalake}/movielens/{genre}/';
""".format(database=emr_db,genre=genre,datalake=s3_dlake,genre_t=genre_t)

PRESTO_SCRIPT_RUN_EXPFILE = """
#!/bin/bash
aws s3 cp s3://{datalake}/scripts/create-genre.sql .
presto-cli --catalog hive -f create-genre.sql --output-format TSV > {genre_t}-films.tsv
aws s3 cp {genre_t}-films.tsv s3://{datalake}/movielens/{genre}/
""".format(database=emr_db,genre=genre,datalake=s3_dlake,genre_t=genre_t)

PRESTO_SQL_GEN_GENRE_CSV = """
WITH {genre}data AS (
SELECT REPLACE ( m.title , '"' , '' ) as title, r.rating
FROM {database}.movies m
INNER JOIN (SELECT rating, movieId FROM {database}.ratings) r on m.movieId = r.movieId WHERE REGEXP_LIKE (genres, '{genre}')
  )
SELECT substr(title,1, LENGTH(title) -6) as title, replace(substr(trim(title),-5),')','') as year, AVG(rating) as avrating from {genre}data GROUP BY title ORDER BY year DESC,  title ASC ;
""".format(database=emr_db,genre=genre)

def py_create_emr_scripts(**kwargs):
    s3 = boto3.resource('s3')
    print("Creating scripts which will be executed by Amazon EMR - will overwrite existing scripts")
    # create create-film-db.hql
    object1 = s3.Object(s3_dlake, 'scripts/create-film-db.hql')
    object1.put(Body=HIVE_CREATE_DB)
    # create create-film-db-tables.hql
    object2 = s3.Object(s3_dlake, 'scripts/create-film-db-tables.hql')
    object2.put(Body=HIVE_CREATE_DB_TABLES)
    # create create-genre-film-table.hql
    object3 = s3.Object(s3_dlake, 'scripts/create-genre-film-table.hql')
    object3.put(Body=HIVE_CREATE_GENRE_TABLE)
    # create create-genre.sql
    object4 = s3.Object(s3_dlake, 'scripts/create-genre.sql')
    object4.put(Body=PRESTO_SQL_GEN_GENRE_CSV)
    # create run-presto-query.sh
    object5 = s3.Object(s3_dlake, 'scripts/run-presto-query.sh')
    object5.put(Body=PRESTO_SCRIPT_RUN_EXPFILE) 
    
create_emr_scripts = PythonOperator (
	task_id='create_emr_scripts',
	provide_context=True,
	python_callable=py_create_emr_scripts,
	dag=dag
	)

create_emr_scripts
```

The order these are in is important as you might see errors if something you use/call has not been defined in the workflow code.

When we commit this code, a few seconds later we will see just a single task in our workflow, called "create_emr_scripts" which we can enable (turn on) and then trigger. If we now go to the scripts folder of our Amazon S3 data lake, we should see our new scripts ready to go.

![scripts](https://github.com/094459/devday-elt-automation/blob/main/images/blog-3.png?raw=true)

Every time we re-run this task the scripts will be overwritten to make sure they contain the right values.

Now that we have our scripts, then next thing we need to do is to run those scripts via Amazon EMR. We could use an existing Amazon EMR cluster if we wanted, and then submit the steps to that cluster, but in this walk through I will create an auto terminating Amazon EMR cluster, add the steps and then terminate that cluster.

> If you wanted to use an existing Amazon EMR cluster, you would need to change the code to take an input value of the Amazon EMR cluster id. There are lots of ways you could do this: via a configuration value when you trigger the DAG, via a variable you store in something like AWS Secrets manager, or perhaps by using some code within a PythonOperator to find that cluster id.

To kick off our cluster we use the EmrCreateJobFlowOperator operator, which takes just one value, "job_flow_overrides" which is a variable you need to define that contains the configuration details of your Amazon EMR cluster (the applications you want to use, the size and number of clusters, the configuration details, etc)

```
create_emr_database_cluster = EmrCreateJobFlowOperator(
    task_id='create_emr_database_cluster', 
    job_flow_overrides=JOB_FLOW_OVERRIDES,
	dag=dag
    )
```
As we can see we have defined a variable called JOB_FLOW_OVERRIDES which contains our Amazon EMR cluster details. You can also see that we are again substituting variables so that the Amazon EMR cluster uses the correct configuration details based on our use case. This allows us to use a standard template across many different applications.


```
JOB_FLOW_OVERRIDES = {
    'Name': 'devday-demo-cluster-airflow',
    'ReleaseLabel': 'emr-5.32.0',
    'LogUri': 's3n://{{ var.value.s3_dlake }}/logs',
    'Applications': [
        {
            'Name': 'Spark',
        },
        {
            'Name': 'Pig',
        },
        {
            'Name': 'Hive',
        },
        {
            'Name': 'Presto',
        }
    ],
    'Instances': {
        'InstanceFleets': [
            {
                'Name': 'MASTER',
                'InstanceFleetType': 'MASTER',
                'TargetSpotCapacity': 1,
                'InstanceTypeConfigs': [
                    {
                        'InstanceType': 'm5.xlarge',
                    },
                ]
            },
            {
                'Name': 'CORE',
                'InstanceFleetType': 'CORE',
                'TargetSpotCapacity': 1,
                'InstanceTypeConfigs': [
                    {
                        'InstanceType': 'r5.xlarge',
                    },
                ],
            },
        ],
        'KeepJobFlowAliveWhenNoSteps': True,
        'TerminationProtected': False,
        'Ec2KeyName': 'ec2-rocket',
    },
    'Configurations': [
        {
            'Classification': 'hive-site',
            'Properties': {'hive.metastore.client.factory.class': 'com.amazonaws.glue.catalog.metastore.AWSGlueDataCatalogHiveClientFactory'}
        },
        {
            'Classification': 'presto-connector-hive',
            'Properties': {'hive.metastore.glue.datacatalog.enabled': 'true'}
        },
        {
            'Classification': 'spark-hive-site',
            'Properties': {'hive.metastore.client.factory.class': 'com.amazonaws.glue.catalog.metastore.AWSGlueDataCatalogHiveClientFactory'}
        }
    ],
    'VisibleToAllUsers': True,
    'JobFlowRole': 'EMR_EC2_DefaultRole',
    'ServiceRole': 'EMR_DefaultRole',
    'EbsRootVolumeSize': 32,
    'StepConcurrencyLevel': 1,
    'Tags': [
        {
            'Key': 'Environment',
            'Value': 'Development'
        },
        {
            'Key': 'Name',
            'Value': 'Airflow EMR Demo Project'
        },
        {
            'Key': 'Owner',
            'Value': 'Data Analytics Team'
        }
    ]
}
```

In order to achieve my objectives, I have created an Amazon EMR cluster that has the Apache Hive and Presto applications, and for simplicity I am using the AWS Glue data catalog as the metastore (you could easily change this to what your environment uses, something like a MySQL instance perhaps). One thing we do configure in our configuration is the value "KeepJobFlowAliveWhenNoSteps': True" as we want the Amazon EMR cluster running until it has completed all our steps before we terminate it.

So this step will now launch our Amazon EMR cluster. Let us add it to the workflow dependency graph.

```
create_emr_scripts >> create_emr_database_cluster 
```

If we commit the code and then launch this workflow, we should now start to see our Amazon EMR cluster start up. From the UI, take a look at the logs for the "create_emr_database_cluster", you will see something similar to this in the log file:

```
[2021-04-19 14:59:18,888] {{standard_task_runner.py:78}} INFO - Job 116460: Subtask create_emr_database_cluster
[2021-04-19 14:59:18,994] {{logging_mixin.py:112}} INFO - Running %s on host %s <TaskInstance: devday-emr-create.create_emr_database_cluster 2021-04-19T14:58:50.688217+00:00 [running]> ip-10-192-21-41.eu-west-1.compute.internal
[2021-04-19 14:59:19,138] {{emr_create_job_flow_operator.py:66}} INFO - Creating JobFlow using aws-conn-id: s3_default, emr-conn-id: emr_default
[2021-04-19 14:59:19,437] {{emr_create_job_flow_operator.py:73}} INFO - JobFlow with id j-2JRII3WTAD9PG created
```
The Amazon EMR cluster id is displayed (here it is "j-2JRII3WTAD9PG") and this is important as we will see in a minute. Before proceeding, make sure you terminate this cluster manually via the console. We do not want to leave our Amazon EMR cluster running, so we create a new task using a different operator to do this, the EmrTerminateJobFlowOperator.

```
terminate_emr_cluster = EmrTerminateJobFlowOperator(
    task_id='terminate_emr_cluster',
    job_flow_id="{{ task_instance.xcom_pull('create_emr_database_cluster', key='return_value') }}",
    aws_conn_id='aws_default',
    )
```
There are a couple of new things here. First we have the "aws_conn_id" parameter, which is required by this operator and we set to this value when using Managed Workflows for Apache Airflow. If you are hosting/using your own version of Apache Airflow, this will correspond to the name of the Connection you have defined in the Apache Airflow UI. The next thing to notice is the "job_flow_id" which is using another feature of Apache Airflow, xcom. Xcoms is the feature in Apache Airflow that lets tasks exchange information, and in this instance we are "pulling" the details of the Amazon EMR cluster ID (as we saw in the previous task) so that we can terminate the right cluster.

We can now add this task to the workflow:

```
create_emr_scripts >> create_emr_database_cluster >> terminate_emr_cluster

```
Commit and the launch the DAG when it appears in the UI. At this stage, it is not doing anything interesting other than launching and the terminating the Amazon EMR cluster. Next, we need to add the steps we want to execute on that running cluster.

If we look at the task we are trying to automate, the first one is creating the database. We have our script (a simple Apache Hive script) uploaded in the /scripts folder on Amazon S3. But as before in the Amazon Athena walkthrough, we need to add some logic here to skip this creation of the database already exists. Our workflow will be check to see if the database exists, and if not create the database and import the Movielens tables we need, skipping this step if the database already exists.

As we have already covered the branching logic in the previous post, I will just cover the Amazon EMR step this time. To add a step, in this case to run the hive script, we use the EmrAddStepsOperator which will kick off a new step to be executed by the Amazon EMR cluster we want to run this on. When we use the EmrAddStepsOperator operator, we use a corresponding operator called EmrStepSensor, which tracks the status of the task (whether it was successful or failed). Here is the code for these two new tasks. 

```
create_emr_database_step = EmrAddStepsOperator(
    task_id='create_emr_database_step',
    job_flow_id="{{ task_instance.xcom_pull(task_ids='create_emr_database_cluster', key='return_value') }}",
    aws_conn_id='aws_default',
    on_failure_callback=cleanup_emr_cluster_if_steps_fail,
    steps=CREATE_DATABASE,
    )
create_emr_database_sensor = EmrStepSensor(
    task_id='create_emr_database_sensor',
    job_flow_id="{{ task_instance.xcom_pull('create_emr_database_cluster', key='return_value') }}",
    step_id="{{ task_instance.xcom_pull(task_ids='create_emr_database_step', key='return_value')[0] }}",
    on_failure_callback=cleanup_emr_cluster_if_steps_fail,
    aws_conn_id='aws_default',
    )
```
In the "create_emr_database_step" task you can see we are using Xcoms again, to get the name of the Amazon EMR cluster id when we use the EmrAddStepsOperator. In the "create_emr_database_sensor" task you can see we are using XComs to additionally get the name of the task we need to keep a track of - in this case, the "create_emr_database_step" task. This will ensure that this task is monitoring the right step.

The next thing to notice is the "steps=" parameter in the "create_emr_database_step" task. This is where we define the actual step to submit to Amazon EMR, and we define this in a variable, in this case called CREATE_DATABASE. Here is the code.

```
CREATE_DATABASE = [
    {
        'Name': 'Create Genre Database',
        'ActionOnFailure': 'CONTINUE',
        'HadoopJarStep': {
            'Jar': 'command-runner.jar',
            'Args': [
                'hive-script',
                '--run-hive-script',
                '--args',
                '-f',
                's3://{{ var.value.s3_dlake }}/scripts/create-film-db.hql'
            ]
        }
    }
]
```
This is the same process we would follow if we were manually submitting the task via the Amazon EMR console. You will notice that we are using variables again in order to ensure that we do not hardcode anything.

We are not quite ready to submit this yet. When submitting steps to be executed by the Amazon EMR cluster, there is the possibility that sometimes these will fail. If that happens, the workflow will stall/stop, and this will leave our Amazon EMR cluster running (which we have to pay for). We need a way of short circuiting this, and for this we use the "on_failure_callback" feature of Apache Airflow that allows us to call a function we define in the case where this task has failed. In the example above, we have defined a cleanup function called "cleanup_emr_cluster_if_steps_fail" which looks like:

```
def cleanup_emr_cluster_if_steps_fail(context):
    print("This is invoked when a running EMR cluster has a step running that fails.")
    print("If we do not do this, the DAG will stop but the cluster will still keep running")
    
    early_terminate_emr_cluster = EmrTerminateJobFlowOperator(
        task_id='terminate_emr_cluster',
        job_flow_id=context["ti"].xcom_pull('create_emr_database_cluster'),
        aws_conn_id='aws_default',
        )
    return early_terminate_emr_cluster.execute(context=context)
```
As you can see, we are using Xcoms to grab the Amazon EMR cluster ID and then terminate this. Now, if our scripts go rogue, we will still terminate the cluster.

If we now take these new tasks, together with the branching logic we now have this additional code:

```
CREATE_DATABASE = [
    {
        'Name': 'Create Genre Database',
        'ActionOnFailure': 'CONTINUE',
        'HadoopJarStep': {
            'Jar': 'command-runner.jar',
            'Args': [
                'hive-script',
                '--run-hive-script',
                '--args',
                '-f',
                's3://{{ var.value.s3_dlake }}/scripts/create-film-db.hql'
            ]
        }
    }
]

def check_emr_database(**kwargs):
    ath = boto3.client('athena')
    try:
        response = ath.get_database(
            CatalogName='AwsDataCatalog',
            DatabaseName=emr_db
        )
        print("Database already exists - skip creation")
        return "skip_emr_database_creation"
    except:
        print("No EMR Database Found")
        return "create_emr_database_step"

def cleanup_emr_cluster_if_steps_fail(context):
    print("This is invoked when a running EMR cluster has a step running that fails.")
    print("If we do not do this, the DAG will stop but the cluster will still keep running")
    
    early_terminate_emr_cluster = EmrTerminateJobFlowOperator(
        task_id='terminate_emr_cluster',
        job_flow_id=context["ti"].xcom_pull('create_emr_database_cluster'),
        aws_conn_id='aws_default',
        )
    return early_terminate_emr_cluster.execute(context=context)
    
check_emr_database = BranchPythonOperator(
    task_id='check_emr_database',
    provide_context=True,
    python_callable=check_emr_database,
    retries=1,
    dag=dag,
)

skip_emr_database_creation = DummyOperator(
    task_id="skip_emr_database_creation",
    trigger_rule=TriggerRule.NONE_FAILED,
    dag=dag,
)

emr_database_checks_done = DummyOperator(
    task_id="emr_database_checks_done",
    trigger_rule=TriggerRule.NONE_FAILED,
    dag=dag,
)

create_emr_database_step = EmrAddStepsOperator(
    task_id='create_emr_database_step',
    job_flow_id="{{ task_instance.xcom_pull(task_ids='create_emr_database_cluster', key='return_value') }}",
    aws_conn_id='aws_default',
    on_failure_callback=cleanup_emr_cluster_if_steps_fail,
    steps=CREATE_DATABASE,
    )
create_emr_database_sensor = EmrStepSensor(
    task_id='create_emr_database_sensor',
    job_flow_id="{{ task_instance.xcom_pull('create_emr_database_cluster', key='return_value') }}",
    step_id="{{ task_instance.xcom_pull(task_ids='create_emr_database_step', key='return_value')[0] }}",
    on_failure_callback=cleanup_emr_cluster_if_steps_fail,
    aws_conn_id='aws_default',
    )

create_emr_scripts >> create_emr_database_cluster >> check_emr_database

check_emr_database >> skip_emr_database_creation >> emr_database_checks_done  
check_emr_database >> create_emr_database_step >> create_emr_database_sensor >> emr_database_checks_done 

>> emr_database_checks_done >> terminate_emr_cluster

```
If we check this code in, and then trigger the DAG, we should now see now see the the Amazon EMR cluster start, run the step to create the database, and then terminate the cluster.

The rest of the workflow repeats the above process, adding addition steps. You can check the full workflow out [here in the GitHub repository](https://github.com/094459/devday-elt-automation/blob/main/dags/devday-emr-create.py)

**Running the workflow**

After committing the code you should have the workflows available in the Apache Airflow UI and can then trigger them via the UI. As each step starts, runs and then completes, you should be able to see the information and logs produced (including any of the Print statements included in the DAG).

Once the workflow has completed, you can now take a look at the outcome. If we use Hue, we can connect to the new database and view the new information using standard SQL in Presto. If we look at the Amazon S3 data lake, we can see we have our new files.

{% youtube e4EN8L8HiXs %}

### What Next?

Thanks for sticking with me to the end, and I hope you have found it useful to understand how you might use open source tools like Apache Airflow to automate your ELT (or for that matter ETL) tasks. Watch out for a future DevDay Data event where I walk you through the end to end building of this, but I hope that you will have enough information here to try this out for yourself.

It is not hard to see how you might build upon this example. Some examples might be:

* using a function you deploy on AWS Lambda to trigger the automated workflow - for example, a new data update you receive can lead to automatically these tables/export files being refreshed
* using other Airflow operators such as the ones to Amazon SageMaker that allow you to trigger automatic machine learning model training/tuning
* using additional workflows as part of the ingestion workflows to get the movielens database into the data lake, which then triggers the ELT workflows

As always, feel free to get in touch and provide comments/questions.
