---
title: 'Reading and writing data across different AWS accounts with Amazon Managed Workflows for Apache Airflow v2.x'
date: '2021-09-07'
tags: [Apache Airflow, mwaa, security]
---
**Reading and writing data across different AWS accounts in you Apache Airflow DAGs**

As regular readers will know, I sometimes lurk in the [Apache Airflow slack channel](https://apache-airflow.slack.com/) to see what is going on. If you are new to Apache Airflow, or want to get a deeper understanding then I highly recommend spending some time here. The community is super welcoming and eager to help new participants.

It was during a recent session I came across an interesting problem that one of the builders was having, which was how to access (read/write) data in an S3 bucket which was in a different account to the one hosting Amazon Managed Workflows for Apache Airflow (MWAA). 

The rest of this post will be a quick look at the setup, the error that occurred and how to configure MWAA so that you can read/write data confidently across your different AWS accounts.

### The problem

A customer was using MWAA 2.0.2, and within their workflow, they were trying to upload data to an S3 bucket in a different AWS account to what their MWAA environment was running in. When they triggered their DAG, they were getting errors such as the following:

```
 An error occurred (AccessDenied) when calling the PutObject operation: Access Denied
```

To help with troubleshooting, the customer had created a test DAG that would try and read/write files to a sample S3 bucket in three ways:

* using boto3, the Python SDK for interacting with AWS
* using Apache Airflow operators - airflow.providers.amazon.aws.hooks.s3
* using the pandas Python library - using s3fs

Here is the test DAG that the customer put together

```
import logging
import random
from datetime import timedelta
import pandas as pd
import boto3
from airflow.models import Variable
from airflow import DAG
from airflow.operators.python import PythonOperator
from airflow.providers.amazon.aws.hooks.s3 import S3Hook
from airflow.utils.dates import days_ago


def save_file_to_s3():
    n = random.randint(100, 10000)
    filename = f'demo_{n}.csv'
    local_file_path = f'/tmp/{filename}'
    demo_data = pd.DataFrame({'num_legs': [2, 4, 8, 0],
                              'num_wings': [2, 0, 0, 0],
                              'num_specimen_seen': [10, 2, 1, 8]},
                             index=['falcon', 'dog', 'spider', 'fish'])
    demo_data.to_csv(local_file_path, index=False)

    bucket_name = Variable.get('TEST_BUCKET')
    folder_name = Variable.get('TEST_FOLDER')
    s3_key = f'{folder_name}/boto3_{filename}'
    logging.info(f'local_file_path: {local_file_path}, bucket_name: {bucket_name}, key: {s3_key}')

    logging.info('Uploading CSV to S3 with boto3')
    s3 = boto3.resource('s3')
    try:
        s3.meta.client.upload_file(local_file_path, bucket_name, s3_key, ExtraArgs={'ACL': 'bucket-owner-full-control'})
    except Exception as e:
        logging.info(e)
        pass
    logging.info('Done uploading CSV to S3 with boto3')
    logging.info('Uploading CSV to S3 with S3HOOK')
    s3_hook = S3Hook()
    s3_key = f'{folder_name}/s3hook_{filename}'
    try:
        s3_hook.load_file(local_file_path, bucket_name=bucket_name, key=s3_key, acl_policy='bucket-owner-full-control')
    except Exception as e:
        logging.info(e)
        pass
    logging.info('Done uploading CSV to S3 with S3HOOK')

    logging.info('Uploading CSV to S3 with pandas')
    demo_data.to_csv(f's3://{bucket_name}/{folder_name}/pandas_{filename}', index=False)
    logging.info('Done uploading CSV to S3 with pandas')


def run_dag():
    save_file_to_s3()


dag_default_args = {
    'owner': 'airflow',
    'depends_on_past': False,
    'email': ['airflow@example.com'],
    'email_on_failure': False,
    'email_on_retry': False,
    'retries': 0,
    'retry_delay': timedelta(minutes=2)
}

with DAG(
    'demo',
    default_args=dag_default_args,
    description='description',
    schedule_interval="0 10 * * *",
    start_date=days_ago(1),
    tags=['test'],
) as dag:
    test_dag = PythonOperator(
        task_id="test_dag",
        python_callable=run_dag
    )

```

What was interesting, was that when they ran the DAG, the boto3 function would write the file to the target S3 bucket, but the other two failed.

Time to take a closer look.

### The approach

I wanted to see if I could reproduce this issue, so the approach I took was to 

1/ set up an environment running the same version of MWAA as the customer, but initially use an S3 bucket in the SAME account to make sure that everything works as expected, 

2/ setup a new S3 bucket on a different AWS account and repeat to see if I could reproduce the error, 

3/ review CloudTrail and MWAA logs to see if I could identify any issues and fix.

### The setup

The customer was running a standard MWAA 2.0.2 environment in one AWS account, so I quickly provisioned an environment (using my CDK application [which I have blogged about before](https://dev.to/aws/using-aws-cdk-to-deploy-your-amazon-managed-workflows-for-apache-airflow-environment-12cf)).

I deployed the above DAG, and then had to do a couple of things:

* create a new S3 bucket (in my case, I called this "ricsue-airflow-s3hook" and within this bucket, I created a folder called "s3permissions")
* adjusted the permissions for the MWAA execution role (which you can find by opening up your MWAA environment in the AWS console) to include the new bucket I just created

```
...
            "Resource": [
                "arn:aws:s3:::airflow-ricsue-cdk-demo/*",
                "arn:aws:s3:::airflow-ricsue-cdk-demo",
                "arn:aws:s3:::ricsue-airflow-s3hook/*",
                "arn:aws:s3:::ricsue-airflow-s3hook"
            ],
            "Effect": "Allow"
...
```

* within the MWAA console, using the Admin menu option in the Apache Airflow UI, I created two new variables: TEST_BUKCET (with a value of "ricsue-airflow-s3hook") and TEST_FOLDER (with a value of "s3permissions")

Once I had completed that, I enabled it and then manually triggered it. It failed with the following error:

```
[2021-09-06 12:36:26,255] {{customer-s3.py:26}} INFO - local_file_path: /tmp/demo_2025.csv, bucket_name: ricsue-airflow-s3hook, key: s3permissions/boto3_demo_2025.csv
[2021-09-06 12:36:26,284] {{customer-s3.py:28}} INFO - Uploading CSV to S3 with boto3
[2021-09-06 12:36:26,429] {{customer-s3.py:35}} INFO - Done uploading CSV to S3 with boto3
[2021-09-06 12:36:26,455] {{customer-s3.py:36}} INFO - Uploading CSV to S3 with S3HOOK
[2021-09-06 12:36:26,487] {{logging_mixin.py:104}} INFO - [2021-09-06 12:36:26,486] {{base_aws.py:368}} INFO - Airflow Connection: aws_conn_id=aws_default
[2021-09-06 12:36:26,545] {{logging_mixin.py:104}} INFO - [2021-09-06 12:36:26,545] {{base_aws.py:179}} INFO - No credentials retrieved from Connection
[2021-09-06 12:36:26,571] {{logging_mixin.py:104}} INFO - [2021-09-06 12:36:26,571] {{base_aws.py:87}} INFO - Creating session with aws_access_key_id=None region_name=None
[2021-09-06 12:36:26,613] {{logging_mixin.py:104}} INFO - [2021-09-06 12:36:26,613] {{base_aws.py:157}} INFO - role_arn is None
[2021-09-06 12:36:26,782] {{customer-s3.py:44}} INFO - Done uploading CSV to S3 with S3HOOK
[2021-09-06 12:36:26,813] {{customer-s3.py:46}} INFO - Uploading CSV to S3 with pandas
[2021-09-06 12:36:26,851] {{taskinstance.py:1482}} ERROR - Task failed with exception
Traceback (most recent call last):
  File "/usr/local/lib/python3.7/site-packages/airflow/models/taskinstance.py", line 1138, in _run_raw_task
    self._prepare_and_execute_task_with_callbacks(context, task)
  File "/usr/local/lib/python3.7/site-packages/airflow/models/taskinstance.py", line 1311, in _prepare_and_execute_task_with_callbacks
    result = self._execute_task(context, task_copy)
  File "/usr/local/lib/python3.7/site-packages/airflow/models/taskinstance.py", line 1341, in _execute_task
    result = task_copy.execute(context=context)
  File "/usr/local/lib/python3.7/site-packages/airflow/operators/python.py", line 117, in execute
    return_value = self.execute_callable()
  File "/usr/local/lib/python3.7/site-packages/airflow/operators/python.py", line 128, in execute_callable
    return self.python_callable(*self.op_args, **self.op_kwargs)
  File "/usr/local/airflow/dags/customer-s3.py", line 52, in run_dag
    save_file_to_s3()
  File "/usr/local/airflow/dags/customer-s3.py", line 47, in save_file_to_s3
    demo_data.to_csv(f's3://{bucket_name}/{folder_name}/pandas_{filename}', index=False)
  File "/usr/local/lib64/python3.7/site-packages/pandas/core/generic.py", line 3403, in to_csv
    storage_options=storage_options,
  File "/usr/local/lib64/python3.7/site-packages/pandas/io/formats/format.py", line 1083, in to_csv
    csv_formatter.save()
  File "/usr/local/lib64/python3.7/site-packages/pandas/io/formats/csvs.py", line 234, in save
    storage_options=self.storage_options,
  File "/usr/local/lib64/python3.7/site-packages/pandas/io/common.py", line 563, in get_handle
    storage_options=storage_options,
  File "/usr/local/lib64/python3.7/site-packages/pandas/io/common.py", line 315, in _get_filepath_or_buffer
    fsspec = import_optional_dependency("fsspec")
  File "/usr/local/lib64/python3.7/site-packages/pandas/compat/_optional.py", line 109, in import_optional_dependency
    raise ImportError(msg) from None
ImportError: Missing optional dependency 'fsspec'.  Use pip or conda to install fsspec.
```

Whilst the boto3 and Apache Airflow operators had worked, the Python library (pandas) had not. This is because they were not installed on the Apache Airflow worker nodes.

I amended the requirements text to add the following:

```
fsspec
s3fs
```
Once uploaded, the MWAA environment had to be updated. This took approx 20 mins, but once it completed, I was then able to trigger the DAG successfully. No errors, and when I looked in the local S3 bucket, I could see the following files:

```
boto3_demo_9977.csv
s3hook_demo_9977.csv
pandas_demo_9977.csv
```

So, the first step completed - we have everything working as expected. Now to change the DAG to write those files to an S3 bucket in a different AWS account.

### The error

In order to reproduce the same setup as the customer, I had to:

* create a new S3 bucket in a different AWS account - (in my case, I called this "ricsue-airflow-s3hook-diffawsaccount" and within this bucket, I kept the same folder called "s3permissions")
* I needed to UPDATE the Apache Airflow variable, TEST_BUCKET. From within the Apache Airflow UI, I edited the value to point to this new bucket and the different AWS account.

To make this easier, I had two browsers running with Chrome running my AWS account with MWAA, and Firefox running a different AWS account with just the Amazon S3 bucket.

Once I had made those changes, I triggered the DAG again. I did not expect ANY of these ways to upload the file to work given that these are two separate AWS accounts, but I wanted to baseline. Sure enough, I got the following error with the DAG failing:

```
[2021-09-06 13:18:54,317] {{customer-s3.py:26}} INFO - local_file_path: /tmp/demo_5839.csv, bucket_name: ricsue-airflow-s3hook-diffawsaccount, key: s3permissions/boto3_demo_5839.csv
[2021-09-06 13:18:54,344] {{customer-s3.py:28}} INFO - Uploading CSV to S3 with boto3
[2021-09-06 13:18:54,479] {{customer-s3.py:33}} INFO - Failed to upload /tmp/demo_5839.csv to ricsue-airflow-s3hook-diffawsaccount/s3permissions/boto3_demo_5839.csv: An error occurred (AccessDenied) when calling the PutObject operation: Access Denied
[2021-09-06 13:18:54,507] {{customer-s3.py:35}} INFO - Done uploading CSV to S3 with boto3
[2021-09-06 13:18:54,531] {{customer-s3.py:36}} INFO - Uploading CSV to S3 with S3HOOK
[2021-09-06 13:18:54,558] {{logging_mixin.py:104}} INFO - [2021-09-06 13:18:54,558] {{base_aws.py:368}} INFO - Airflow Connection: aws_conn_id=aws_default
[2021-09-06 13:18:54,602] {{logging_mixin.py:104}} INFO - [2021-09-06 13:18:54,602] {{base_aws.py:179}} INFO - No credentials retrieved from Connection
[2021-09-06 13:18:54,631] {{logging_mixin.py:104}} INFO - [2021-09-06 13:18:54,631] {{base_aws.py:87}} INFO - Creating session with aws_access_key_id=None region_name=None
[2021-09-06 13:18:54,673] {{logging_mixin.py:104}} INFO - [2021-09-06 13:18:54,673] {{base_aws.py:157}} INFO - role_arn is None
[2021-09-06 13:18:54,792] {{customer-s3.py:42}} INFO - An error occurred (403) when calling the HeadObject operation: Forbidden
[2021-09-06 13:18:54,818] {{customer-s3.py:44}} INFO - Done uploading CSV to S3 with S3HOOK
[2021-09-06 13:18:54,850] {{customer-s3.py:46}} INFO - Uploading CSV to S3 with pandas
[2021-09-06 13:18:56,049] {{taskinstance.py:1482}} ERROR - Task failed with exception
Traceback (most recent call last):
  File "/usr/local/airflow/.local/lib/python3.7/site-packages/s3fs/core.py", line 248, in _call_s3
    out = await method(**additional_kwargs)
  File "/usr/local/airflow/.local/lib/python3.7/site-packages/aiobotocore/client.py", line 155, in _make_api_call
    raise error_class(parsed_response, operation_name)
botocore.exceptions.ClientError: An error occurred (AccessDenied) when calling the CreateBucket operation: Access Denied

The above exception was the direct cause of the following exception:

Traceback (most recent call last):
  File "/usr/local/lib/python3.7/site-packages/airflow/models/taskinstance.py", line 1138, in _run_raw_task
    self._prepare_and_execute_task_with_callbacks(context, task)
  File "/usr/local/lib/python3.7/site-packages/airflow/models/taskinstance.py", line 1311, in _prepare_and_execute_task_with_callbacks
    result = self._execute_task(context, task_copy)
  File "/usr/local/lib/python3.7/site-packages/airflow/models/taskinstance.py", line 1341, in _execute_task
    result = task_copy.execute(context=context)
  File "/usr/local/lib/python3.7/site-packages/airflow/operators/python.py", line 117, in execute
    return_value = self.execute_callable()
  File "/usr/local/lib/python3.7/site-packages/airflow/operators/python.py", line 128, in execute_callable
    return self.python_callable(*self.op_args, **self.op_kwargs)
  File "/usr/local/airflow/dags/customer-s3.py", line 52, in run_dag
    save_file_to_s3()
  File "/usr/local/airflow/dags/customer-s3.py", line 47, in save_file_to_s3
    demo_data.to_csv(f's3://{bucket_name}/{folder_name}/pandas_{filename}', index=False)
  File "/usr/local/lib64/python3.7/site-packages/pandas/core/generic.py", line 3403, in to_csv
    storage_options=storage_options,
  File "/usr/local/lib64/python3.7/site-packages/pandas/io/formats/format.py", line 1083, in to_csv
    csv_formatter.save()
  File "/usr/local/lib64/python3.7/site-packages/pandas/io/formats/csvs.py", line 234, in save
    storage_options=self.storage_options,
  File "/usr/local/lib64/python3.7/site-packages/pandas/io/common.py", line 563, in get_handle
    storage_options=storage_options,
  File "/usr/local/lib64/python3.7/site-packages/pandas/io/common.py", line 345, in _get_filepath_or_buffer
    filepath_or_buffer, mode=fsspec_mode, **(storage_options or {})
  File "/usr/local/airflow/.local/lib/python3.7/site-packages/fsspec/core.py", line 438, in open
    **kwargs,
  File "/usr/local/airflow/.local/lib/python3.7/site-packages/fsspec/core.py", line 292, in open_files
    [fs.makedirs(parent, exist_ok=True) for parent in parents]
  File "/usr/local/airflow/.local/lib/python3.7/site-packages/fsspec/core.py", line 292, in <listcomp>
    [fs.makedirs(parent, exist_ok=True) for parent in parents]
  File "/usr/local/airflow/.local/lib/python3.7/site-packages/fsspec/asyn.py", line 88, in wrapper
    return sync(self.loop, func, *args, **kwargs)
  File "/usr/local/airflow/.local/lib/python3.7/site-packages/fsspec/asyn.py", line 69, in sync
    raise result[0]
  File "/usr/local/airflow/.local/lib/python3.7/site-packages/fsspec/asyn.py", line 25, in _runner
    result[0] = await coro
  File "/usr/local/airflow/.local/lib/python3.7/site-packages/s3fs/core.py", line 731, in _makedirs
    await self._mkdir(path, create_parents=True)
  File "/usr/local/airflow/.local/lib/python3.7/site-packages/s3fs/core.py", line 716, in _mkdir
    await self._call_s3("create_bucket", **params)
  File "/usr/local/airflow/.local/lib/python3.7/site-packages/s3fs/core.py", line 268, in _call_s3
    raise err
PermissionError: Access Denied
```

As we can see, all three methods failed. Exactly what I expected.

What was strange was that the customer was not seeing this issue, and was able to write to the target S3 bucket using boto3. Lets see how to reproduce that in my environment.

### The fix

Within your Amazon S3 bucket, you have the ability to define bucket policies that allow access to read/write files from other AWS accounts.

In the NEW AWS account, I created the following bucket policy for the new bucket I had created ("ricsue-airflow-s3hook-diffawsaccount"). This is what I added:

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Principal": {
                "AWS": "arn:aws:iam::704533066374:role/mwaa-2-eks-role"
            },
            "Action": [
                "s3:GetObject*",
                "s3:GetBucket*",
                "s3:List*",
                "s3:PutObject*"
            ],
            "Resource": [
                "arn:aws:s3:::ricsue-airflow-s3hook-diffawsaccount/*",
                "arn:aws:s3:::ricsue-airflow-s3hook-diffawsaccount"
            ]
        }
    ]
}
```
The policy contains the arn of the MWAA execution role for my MWAA environment in my original AWS account, configures allowed actions (in this instance, I have narrowed it down to these actions - GetObject* , GetBucket* , List* , and PutObject* ) and then configured the target S3 buckets resources (here it is all resources under this bucket, but you could also reduce the scope to just certain folders if you wanted to)

When I saved this, and then re-ran the DAG. Success, it all worked.

```
[2021-09-06 18:09:15,305] {{customer-s3.py:26}} INFO - local_file_path: /tmp/demo_3455.csv, bucket_name: ricsue-airflow-s3hook-diffawsaccount, key: s3permissions/boto3_demo_3455.csv
[2021-09-06 18:09:15,335] {{customer-s3.py:28}} INFO - Uploading CSV to S3 with boto3
[2021-09-06 18:09:15,499] {{customer-s3.py:35}} INFO - Done uploading CSV to S3 with boto3
[2021-09-06 18:09:15,564] {{customer-s3.py:36}} INFO - Uploading CSV to S3 with S3HOOK
[2021-09-06 18:09:15,592] {{logging_mixin.py:104}} INFO - [2021-09-06 18:09:15,592] {{base_aws.py:368}} INFO - Airflow Connection: aws_conn_id=aws_default
[2021-09-06 18:09:15,632] {{logging_mixin.py:104}} INFO - [2021-09-06 18:09:15,632] {{base_aws.py:179}} INFO - No credentials retrieved from Connection
[2021-09-06 18:09:15,681] {{logging_mixin.py:104}} INFO - [2021-09-06 18:09:15,681] {{base_aws.py:87}} INFO - Creating session with aws_access_key_id=None region_name=None
[2021-09-06 18:09:15,719] {{logging_mixin.py:104}} INFO - [2021-09-06 18:09:15,719] {{base_aws.py:157}} INFO - role_arn is None
[2021-09-06 18:09:15,859] {{customer-s3.py:44}} INFO - Done uploading CSV to S3 with S3HOOK
[2021-09-06 18:09:15,887] {{customer-s3.py:46}} INFO - Uploading CSV to S3 with pandas
[2021-09-06 18:09:16,729] {{customer-s3.py:48}} INFO - Done uploading CSV to S3 with pandas
[2021-09-06 18:09:16,762] {{python.py:118}} INFO - Done. Returned value was: None
[2021-09-06 18:09:16,805] {{taskinstance.py:1192}} INFO - Marking task as SUCCESS. dag_id=demo, task_id=test_dag, execution_date=20210906T180913, start_date=20210906T180914, end_date=20210906T180916
[2021-09-06 18:09:16,901] {{taskinstance.py:1246}} INFO - 0 downstream tasks scheduled from follow-on schedule check
[2021-09-06 18:09:16,943] {{logging_mixin.py:104}} INFO - [2021-09-06 18:09:16,943] {{local_task_job.py:146}} INFO - Task exited with return code 0
```

But wait, that does not describe the customer problem. They could get it working with boto3, so what is going on then?

I altered the bucket policy so that it had fewer permissions, specifically removing the List* as follows:

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Principal": {
                "AWS": "arn:aws:iam::704533066374:role/mwaa-2-eks-role"
            },
            "Action": [
                "s3:GetObject*",
                "s3:GetBucket*",
                "s3:PutObject*"
            ],
            "Resource": [
                "arn:aws:s3:::ricsue-airflow-s3hook-diffawsaccount/*",
                "arn:aws:s3:::ricsue-airflow-s3hook-diffawsaccount"
            ]
        }
    ]
}
```
And when I re-ran the DAG, boto3 worked, but the S3 Hook and the pandas failed with permissions errors:

```
[2021-09-06 18:07:11,238] {{customer-s3.py:26}} INFO - local_file_path: /tmp/demo_6465.csv, bucket_name: ricsue-airflow-s3hook-diffawsaccount, key: s3permissions/boto3_demo_6465.csv
[2021-09-06 18:07:11,263] {{customer-s3.py:28}} INFO - Uploading CSV to S3 with boto3
[2021-09-06 18:07:11,420] {{customer-s3.py:35}} INFO - Done uploading CSV to S3 with boto3
[2021-09-06 18:07:11,454] {{customer-s3.py:36}} INFO - Uploading CSV to S3 with S3HOOK
[2021-09-06 18:07:11,481] {{logging_mixin.py:104}} INFO - [2021-09-06 18:07:11,481] {{base_aws.py:368}} INFO - Airflow Connection: aws_conn_id=aws_default
[2021-09-06 18:07:11,547] {{logging_mixin.py:104}} INFO - [2021-09-06 18:07:11,546] {{base_aws.py:179}} INFO - No credentials retrieved from Connection
[2021-09-06 18:07:11,571] {{logging_mixin.py:104}} INFO - [2021-09-06 18:07:11,571] {{base_aws.py:87}} INFO - Creating session with aws_access_key_id=None region_name=None
[2021-09-06 18:07:11,578] {{logging_mixin.py:104}} WARNING - /usr/local/airflow/.local/lib/python3.7/site-packages/watchtower/__init__.py:205 WatchtowerWarning: Failed to deliver logs: None
[2021-09-06 18:07:11,649] {{logging_mixin.py:104}} INFO - [2021-09-06 18:07:11,649] {{base_aws.py:157}} INFO - role_arn is None
[2021-09-06 18:07:11,761] {{customer-s3.py:42}} INFO - An error occurred (403) when calling the HeadObject operation: Forbidden
[2021-09-06 18:07:11,789] {{customer-s3.py:44}} INFO - Done uploading CSV to S3 with S3HOOK
[2021-09-06 18:07:11,817] {{customer-s3.py:46}} INFO - Uploading CSV to S3 with pandas
[2021-09-06 18:07:12,347] {{taskinstance.py:1482}} ERROR - Task failed with exception
Traceback (most recent call last):
  File "/usr/local/airflow/.local/lib/python3.7/site-packages/s3fs/core.py", line 248, in _call_s3
    out = await method(**additional_kwargs)
  File "/usr/local/airflow/.local/lib/python3.7/site-packages/aiobotocore/client.py", line 155, in _make_api_call
    raise error_class(parsed_response, operation_name)
botocore.exceptions.ClientError: An error occurred (AccessDenied) when calling the CreateBucket operation: Access Denied

The above exception was the direct cause of the following exception:

Traceback (most recent call last):
  File "/usr/local/lib/python3.7/site-packages/airflow/models/taskinstance.py", line 1138, in _run_raw_task
    self._prepare_and_execute_task_with_callbacks(context, task)
  File "/usr/local/lib/python3.7/site-packages/airflow/models/taskinstance.py", line 1311, in _prepare_and_execute_task_with_callbacks
    result = self._execute_task(context, task_copy)
  File "/usr/local/lib/python3.7/site-packages/airflow/models/taskinstance.py", line 1341, in _execute_task
    result = task_copy.execute(context=context)
  File "/usr/local/lib/python3.7/site-packages/airflow/operators/python.py", line 117, in execute
    return_value = self.execute_callable()
  File "/usr/local/lib/python3.7/site-packages/airflow/operators/python.py", line 128, in execute_callable
    return self.python_callable(*self.op_args, **self.op_kwargs)
  File "/usr/local/airflow/dags/customer-s3.py", line 52, in run_dag
    save_file_to_s3()
  File "/usr/local/airflow/dags/customer-s3.py", line 47, in save_file_to_s3
    demo_data.to_csv(f's3://{bucket_name}/{folder_name}/pandas_{filename}', index=False)
  File "/usr/local/lib64/python3.7/site-packages/pandas/core/generic.py", line 3403, in to_csv
    storage_options=storage_options,
  File "/usr/local/lib64/python3.7/site-packages/pandas/io/formats/format.py", line 1083, in to_csv
    csv_formatter.save()
  File "/usr/local/lib64/python3.7/site-packages/pandas/io/formats/csvs.py", line 234, in save
    storage_options=self.storage_options,
  File "/usr/local/lib64/python3.7/site-packages/pandas/io/common.py", line 563, in get_handle
    storage_options=storage_options,
  File "/usr/local/lib64/python3.7/site-packages/pandas/io/common.py", line 345, in _get_filepath_or_buffer
    filepath_or_buffer, mode=fsspec_mode, **(storage_options or {})
  File "/usr/local/airflow/.local/lib/python3.7/site-packages/fsspec/core.py", line 438, in open
    **kwargs,
  File "/usr/local/airflow/.local/lib/python3.7/site-packages/fsspec/core.py", line 292, in open_files
    [fs.makedirs(parent, exist_ok=True) for parent in parents]
  File "/usr/local/airflow/.local/lib/python3.7/site-packages/fsspec/core.py", line 292, in <listcomp>
    [fs.makedirs(parent, exist_ok=True) for parent in parents]
  File "/usr/local/airflow/.local/lib/python3.7/site-packages/fsspec/asyn.py", line 88, in wrapper
    return sync(self.loop, func, *args, **kwargs)
  File "/usr/local/airflow/.local/lib/python3.7/site-packages/fsspec/asyn.py", line 69, in sync
    raise result[0]
  File "/usr/local/airflow/.local/lib/python3.7/site-packages/fsspec/asyn.py", line 25, in _runner
    result[0] = await coro
  File "/usr/local/airflow/.local/lib/python3.7/site-packages/s3fs/core.py", line 731, in _makedirs
    await self._mkdir(path, create_parents=True)
  File "/usr/local/airflow/.local/lib/python3.7/site-packages/s3fs/core.py", line 716, in _mkdir
    await self._call_s3("create_bucket", **params)
  File "/usr/local/airflow/.local/lib/python3.7/site-packages/s3fs/core.py", line 268, in _call_s3
    raise err
PermissionError: Access Denied
```
So, we can close that loop. We now understand under what scenarios this might work (target S3 bucket policy not having the right permissions for the various methods of uploading files) and we can address/solve this as needed.

### Conclusion

In this post I showed you how you can set up your S3 buckets so that you can use them to read and write data from your MWAA environment. I showed you how this works whether you are doing this via boto3, using the Apache Airflow S3 operator,  or doing this via a third party Python library.

Please let me know via the comments of any additional questions or comments you have on this post.

You can view/use the files that accompany this blog [via the GitHub repository link here](https://github.com/094459/blog-mwaa-xaccount)
