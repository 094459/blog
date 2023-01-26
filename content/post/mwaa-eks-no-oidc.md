
---
title: 'Configuring the KubernetesPodOperator on Managed Workflows for Apache Airflow (MWAA) - non OIDC Amazon EKS Clusters'
date: '2023-01-26'
tags: [Apache Airflow, mwaa, Amazon EKS, Kubernetes]
---

### Configuring the KubernetesPodOperator on Managed Workflows for Apache Airflow (MWAA) - non OIDC Amazon EKS Clusters

Today I came across an interesting question around the use of the KubernetesPodOperator working on EKS Clusters where you have not configured OIDC. They had followed my blog post, and when it came to running the DAG, they got the following error:

```
[2023-01-26, 13:03:18 UTC] {{kubernetes_pod.py:566}} INFO - Creating pod mwaa-pod-test.0ab20a7075b84175b2a9a3fe32796f53 with labels: {'dag_id': 'kubernetes_pod_example_iam_authenticator', 'task_id': 'pod-task', 'execution_date': '2023-01-26T130310.1069420000-c39a2d8b8', 'try_number': '1'}
[2023-01-26, 13:03:19 UTC] {{kubernetes_pod.py:612}} ERROR - (401)
Reason: Unauthorized
HTTP response headers: HTTPHeaderDict({'Audit-Id': '47ae7378-7037-4bee-851b-0ac9515c8228', 'Cache-Control': 'no-cache, private', 'Content-Type': 'application/json', 'Date': 'Thu, 26 Jan 2023 13:03:19 GMT', 'Content-Length': '129'})
HTTP response body: {"kind":"Status","apiVersion":"v1","metadata":{},"status":"Failure","message":"Unauthorized","reason":"Unauthorized","code":401}
```

As I still had the environment I built from [this blog post](https://dev.to/aws/running-the-kubernetespodoperator-in-different-aws-accounts-when-using-amazon-managed-workflows-for-apache-airflow-v2x-51l7) I decided to see if I could reproduce the problem.

I built a new EKS Cluster, following the same instructions EXCEPT the initial EKS Cluster creation which I used the following:

```
eksctl create cluster \
--name mwaa-eks3 \
--region eu-central-1 \
--version 1.24 \
--nodegroup-name linux-nodes \
--nodes 3 \
--nodes-min 1 \
--nodes-max 4 \
--ssh-access \
--ssh-public-key frank-open-distro \
--managed \
--vpc-public-subnets "subnet-0a6787dd2777c1897, subnet-0b10b70867384b67e" \
--vpc-private-subnets "subnet-05b6e2630d8f2d555, subnet-0fdcca6496460b7e6"
```
And sure enough, I got the same 401 Error. I experimented with different kube_config.yaml files, adding AWS Credentials to the AWS Connections page, but I only seemed to get different errors (see the end, with details of the 403 error)

I created a quick DAG to output the info of the identity when the DAG was running 


```
showconfig = BashOperator(
        task_id="sts_show",
        bash_command="aws sts get-caller-identity")
```

this output the following

```
[2023-01-26, 11:01:40 UTC] {{subprocess.py:89}} INFO - {
[2023-01-26, 11:01:40 UTC] {{subprocess.py:89}} INFO -     "UserId": "ARHELLOROKHELLOXU4IXJ:AmazonMWAA-airflow",
[2023-01-26, 11:01:40 UTC] {{subprocess.py:89}} INFO -     "Account": "{AWS ACCOUNT}",
[2023-01-26, 11:01:40 UTC] {{subprocess.py:89}} INFO -     "Arn": "arn:aws:sts::{AWS ACCOUNT}:assumed-role/mwaa-eks-multi-account-role/AmazonMWAA-airflow"
[2023-01-26, 11:01:40 UTC] {{subprocess.py:89}} INFO - }
```

I then updated the Trust Association of the MWAA role so it looked like this

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Principal": {
                "Service": [
                    "airflow-env.amazonaws.com",
                    "airflow.amazonaws.com"
                ]
            },
            "Action": "sts:AssumeRole"
        },
        {
            "Effect": "Allow",
            "Principal": {
                "AWS": "arn:aws:sts::{AWS ACCOUNT}:assumed-role/mwaa-eks-multi-account-role/AmazonMWAA-airflow"
            },
            "Action": "sts:AssumeRole"
        }
    ]
}
```

and then updated the original kube_config.yaml with two extra lines

```
apiVersion: v1
clusters:
- cluster:
    certificate-authority-data: LS0treadacted==
    server: https://F66B641DBB6C29956FE1189127C3EB9B.gr7.eu-central-1.eks.amazonaws.com
  name: arn:aws:eks:eu-central-1:{AWS ACCOUNT}:cluster/mwaa-eks3
contexts:
- context:
    cluster: arn:aws:eks:eu-central-1:{AWS ACCOUNT}:cluster/mwaa-eks3
    user: arn:aws:eks:eu-central-1:{AWS ACCOUNT}:cluster/mwaa-eks3
  name: aws
current-context: aws
kind: Config
preferences: {}
users:
- name: arn:aws:eks:eu-central-1:{AWS ACCOUNT}:cluster/mwaa-eks3
  user:
    exec:
      apiVersion: client.authentication.k8s.io/v1beta1
      args:
      - --region
      - eu-central-1
      - eks
      - get-token
      - --cluster-name
      - mwaa-eks3
      - --role
      - arn:aws:iam::{AWS ACCOUNT}:role/mwaa-eks-multi-account-role-iam
      command: aws
```

And once I had saved this, uploaded the new kube_config.yaml, when I ran the DAG again, success!

```
[2023-01-26, 15:26:05 UTC] {{taskinstance.py:1262}} INFO - Executing <Task(KubernetesPodOperator): pod-task> on 2023-01-26 15:25:56.779128+00:00
[2023-01-26, 15:26:05 UTC] {{standard_task_runner.py:52}} INFO - Started process 8277 to run task
[2023-01-26, 15:26:05 UTC] {{standard_task_runner.py:76}} INFO - Running: ['airflow', 'tasks', 'run', 'kubernetes_pod_example_iam_authenticator', 'pod-task', 'manual__2023-01-26T15:25:56.779128+00:00', '--job-id', '84', '--raw', '--subdir', 'DAGS_FOLDER/k8s-iam.py', '--cfg-path', '/tmp/tmpny2trk92', '--error-file', '/tmp/tmp7o5zb5hr']
[2023-01-26, 15:26:05 UTC] {{standard_task_runner.py:77}} INFO - Job 84: Subtask pod-task
[2023-01-26, 15:26:05 UTC] {{logging_mixin.py:109}} INFO - Running <TaskInstance: kubernetes_pod_example_iam_authenticator.pod-task manual__2023-01-26T15:25:56.779128+00:00 [running]> on host ip-10-192-20-19.eu-central-1.compute.internal
[2023-01-26, 15:26:05 UTC] {{taskinstance.py:1429}} INFO - Exporting the following env vars:
AIRFLOW_CTX_DAG_OWNER=aws
AIRFLOW_CTX_DAG_ID=kubernetes_pod_example_iam_authenticator
AIRFLOW_CTX_TASK_ID=pod-task
AIRFLOW_CTX_EXECUTION_DATE=2023-01-26T15:25:56.779128+00:00
AIRFLOW_CTX_DAG_RUN_ID=manual__2023-01-26T15:25:56.779128+00:00
[2023-01-26, 15:26:05 UTC] {{kubernetes_pod.py:566}} INFO - Creating pod mwaa-pod-test.e1fa0df5eca9461caeecfa37e2d7b97b with labels: {'dag_id': 'kubernetes_pod_example_iam_authenticator', 'task_id': 'pod-task', 'execution_date': '2023-01-26T152556.7791280000-4a81f53d7', 'try_number': '1'}
[2023-01-26, 15:26:06 UTC] {{pod_manager.py:157}} WARNING - Pod not yet started: mwaa-pod-test.e1fa0df5eca9461caeecfa37e2d7b97b
[2023-01-26, 15:26:07 UTC] {{pod_manager.py:157}} WARNING - Pod not yet started: mwaa-pod-test.e1fa0df5eca9461caeecfa37e2d7b97b
[2023-01-26, 15:26:08 UTC] {{pod_manager.py:197}} INFO - {AWS ACCOUNT}
[2023-01-26, 15:26:08 UTC] {{pod_manager.py:215}} WARNING - Pod mwaa-pod-test.e1fa0df5eca9461caeecfa37e2d7b97b log read interrupted but container base still running
[2023-01-26, 15:26:09 UTC] {{pod_manager.py:197}} INFO - 704533066374
[2023-01-26, 15:26:09 UTC] {{pod_manager.py:234}} INFO - Pod mwaa-pod-test.e1fa0df5eca9461caeecfa37e2d7b97b has phase Running
[2023-01-26, 15:26:11 UTC] {{kubernetes_pod.py:462}} INFO - skipping deleting pod: mwaa-pod-test.e1fa0df5eca9461caeecfa37e2d7b97b
[2023-01-26, 15:26:12 UTC] {{taskinstance.py:1280}} INFO - Marking task as SUCCESS. dag_id=kubernetes_pod_example_iam_authenticator, task_id=pod-task, execution_date=20230126T152556, start_date=20230126T152605, end_date=20230126T152612
[2023-01-26, 15:26:12 UTC] {{local_task_job.py:154}} INFO - Task exited with return code 0
[2023-01-26, 15:26:12 UTC] {{local_task_job.py:264}} INFO - 0 downstream tasks scheduled from follow-on schedule check
```

I hope this helps someone out - took me a few hours to get this working. Let me know if you found this useful.


**Appendix**

I thought I would post this here as it might help someone. One of the configuration changes I made was to deploy an updated kube_config.yaml that looked like this:

```
apiVersion: v1
clusters:
- cluster:
    certificate-authority-data: LS0tL--readacted--==
    server: https://F66B641DBB6C29956FE1189127C3EB9B.gr7.eu-central-1.eks.amazonaws.com
  name: arn:aws:eks:eu-central-1:{AWS ACCOUNT}:cluster/mwaa-eks3
contexts:
- context:
    cluster: arn:aws:eks:eu-central-1:{AWS ACCOUNT}:cluster/mwaa-eks3
    user: arn:aws:eks:eu-central-1:{AWS ACCOUNT}:cluster/mwaa-eks3
  name: aws
current-context: aws
kind: Config
preferences: {}
users:
- name: arn:aws:eks:eu-central-1:{AWS ACCOUNT}:cluster/mwaa-eks3
  user:
    exec:
      apiVersion: client.authentication.k8s.io/v1beta1
      args:
      - --region
      - eu-central-1
      - token
      - -i
      - mwaa-eks3
      command: aws-iam-authenticator
```

However, when using this configuration, I got the following error.

```
[2023-01-26, 09:40:15 UTC] {{kubernetes_pod.py:566}} INFO - Creating pod mwaa-pod-test.0ed6353e13b64a2e9231bc31ee44d550 with labels: {'dag_id': 'kubernetes_pod_example_iam', 'task_id': 'pod-task', 'execution_date': '2023-01-26T094010.2670960000-7c7d26fe9', 'try_number': '1'}
[2023-01-26, 09:40:15 UTC] {{refresh_config.py:71}} ERROR - [Errno 13] Permission denied: 'aws-iam-authenticator'
[2023-01-26, 09:40:15 UTC] {{kubernetes_pod.py:612}} ERROR - (403)
Reason: Forbidden
HTTP response headers: HTTPHeaderDict({'Audit-Id': '3bb7c88f-8a1b-470b-ade0-f53c4ba6e484', 'Cache-Control': 'no-cache, private', 'Content-Type': 'application/json', 'X-Content-Type-Options': 'nosniff', 'X-Kubernetes-Pf-Flowschema-Uid': 'b6ddf183-f682-4992-86ed-c89b0ff14218', 'X-Kubernetes-Pf-Prioritylevel-Uid': '5d91d704-f92a-4308-989d-c9808855b1b3', 'Date': 'Thu, 26 Jan 2023 09:40:15 GMT', 'Content-Length': '366'})
H

kubernetes.client.rest.ApiException: (403)
Reason: Forbidden
HTTP response headers: HTTPHeaderDict({'Audit-Id': 'c40440c0-3e2b-4345-8024-b3a06e1dba9a', 'Cache-Control': 'no-cache, private', 'Content-Type': 'application/json', 'X-Content-Type-Options': 'nosniff', 'X-Kubernetes-Pf-Flowschema-Uid': 'b6ddf183-f682-4992-86ed-c89b0ff14218', 'X-Kubernetes-Pf-Prioritylevel-Uid': '5d91d704-f92a-4308-989d-c9808855b1b3', 'Date': 'Thu, 26 Jan 2023 09:40:15 GMT', 'Content-Length': '258'})
HTTP response body: {"kind":"Status","apiVersion":"v1","metadata":{},"status":"Failure","message":"pods is forbidden: User \"system:anonymous\" cannot list resource \"pods\" in API group \"\" in the namespace \"mwaa\"","reason":"Forbidden","details":{"kind":"pods"},"code":403}


During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "/usr/local/airflow/.local/lib/python3.7/site-packages/airflow/task/task_runner/standard_task_runner.py", line 85, in _start_by_fork
    args.func(args, dag=self.dag)
  File "/usr/local/airflow/.local/lib/python3.7/site-packages/airflow/cli/cli_parser.py", line 48, in command
    return func(*args, **kwargs)
  File "/usr/local/airflow/.local/lib/python3.7/site-packages/airflow/utils/cli.py", line 92, in wrapper
    return f(*args, **kwargs)
  File "/usr/local/airflow/.local/lib/python3.7/site-packages/airflow/cli/commands/task_command.py", line 292, in task_run
    _run_task_by_selected_method(args, dag, ti)
  File "/usr/local/airflow/.local/lib/python3.7/site-packages/airflow/cli/commands/task_command.py", line 107, in _run_task_by_selected_method
    _run_raw_task(args, ti)
  File "/usr/local/airflow/.local/lib/python3.7/site-packages/airflow/cli/commands/task_command.py", line 184, in _run_raw_task
    error_file=args.error_file,
  File "/usr/local/airflow/.local/lib/python3.7/site-packages/airflow/utils/session.py", line 70, in wrapper
    return func(*args, session=session, **kwargs)
  File "/usr/local/airflow/.local/lib/python3.7/site-packages/airflow/models/taskinstance.py", line 1332, in _run_raw_task
    self._execute_task_with_callbacks(context)
  File "/usr/local/airflow/.local/lib/python3.7/site-packages/airflow/models/taskinstance.py", line 1458, in _execute_task_with_callbacks
    result = self._execute_task(context, self.task)
  File "/usr/local/airflow/.local/lib/python3.7/site-packages/airflow/models/taskinstance.py", line 1514, in _execute_task
    result = execute_callable(context=context)
  File "/usr/local/airflow/.local/lib/python3.7/site-packages/airflow/providers/cncf/kubernetes/operators/kubernetes_pod.py", line 432, in execute
    remote_pod=remote_pod,
  File "/usr/local/airflow/.local/lib/python3.7/site-packages/airflow/providers/cncf/kubernetes/operators/kubernetes_pod.py", line 452, in cleanup
    raise AirflowException(f'Pod {pod and pod.metadata.name} returned a failure: {remote_pod}')
airflow.exceptions.AirflowException: Pod mwaa-pod-test.0ed6353e13b64a2e9231bc31ee44d550 returned a failure: None
[2023-01-26, 09:40:15 UTC] {{local_task_job.py:154}} INFO - Task exited with return code 1
[2023-01-26, 09:40:15 UTC] {{local_task_job.py:264}} INFO - 0 downstream tasks scheduled from follow-on schedule check
```

My lack of knowledge of how Kubernetes authentication and authorisation works let me down here, so if anyone knows how to fix this then please let me know!