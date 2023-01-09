---
title: 'Running the KubernetesPodOperator in different AWS accounts when using Amazon Managed Workflows for Apache Airflow v2.x'
date: '2023-01-09'
tags: [Apache Airflow, mwaa, Amazon EKS, Kubernetes]
---


### Running KubernetesPodOperator in different AWS accounts

I got a mail from Apurav Sharma who was looking to find out about how MWAA supported using the KubernetesPodOperator to kick off tasks in Amazon EKS Containers in any AWS account. This post reveals how you can do that, using a very simple task that displays the AWS account number.

![sample architecture for multi account eks](https://ricsuepublicresources.s3.eu-west-1.amazonaws.com/images/eks-multi.png)

**Pre-requisites**

* You will need admin access to two AWS Accounts, with local AWS Cli tools setup and 
* eksctl version 0.124.0
* kubectl version at least v1.24.1
* A MWAA environment up and running (I am using MWAA with Apache Airflow 2.2.2)

As I have two different AWS accounts, I am using profiles in my local .aws/credentials file to enable me to ensure I access the specific AWS account. Any references to "--profile personal" is referring to the second AWS account, and where it is omitted, the first AWS account.

**Creating a new Amazon EKS cluster**

I used the same steps that were in my original blog post, [Working with Amazon EKS and Amazon Managed Workflows for Apache Airflow v2.x](https://dev.to/aws/working-with-amazon-eks-and-amazon-managed-workflows-for-apache-airflow-v2-x-k12). I will repeat those steps here to make it easier to follow along. I have used the latest version of Kubernetes in this post, that Amazon EKS supports (1.24).

To create the Amazon EKS Cluster on the first AWS account I run the following command

```
eksctl create cluster \
--name mwaa-eks \
--region eu-central-1 \
--version 1.24 \
--nodegroup-name linux-nodes \
--nodes 3 \
--nodes-min 1 \
--nodes-max 4 \
--with-oidc \
--ssh-access \
--ssh-public-key frank-open-distro \
--managed \
--vpc-public-subnets "subnet-0a6787dd2777c1897, subnet-0b10b70867384b67e" \
--vpc-private-subnets "subnet-05b6e2630d8f2d555, subnet-0fdcca6496460b7e6"
```

output similar to 

```
2023-01-06 14:21:45 [ℹ]  eksctl version 0.124.0-dev+ac917eb50.2022-12-23T08:09:21Z
2023-01-06 14:21:45 [ℹ]  using region eu-central-1
2023-01-06 14:21:47 [✔]  using existing VPC (vpc-05733622960d2fa38) and subnets (private:map[eu-central-1a:{subnet-0fdcca6496460b7e6 eu-central-1a 10.192.20.0/24 0 } eu-central-1b:{subnet-05b6e2630d8f2d555 eu-central-1b 10.192.21.0/24 0 }] public:map[eu-central-1a:{subnet-0a6787dd2777c1897 eu-central-1a 10.192.10.0/24 0 } eu-central-1b:{subnet-0b10b70867384b67e eu-central-1b 10.192.11.0/24 0 }])
2023-01-06 14:21:47 [!]  custom VPC/subnets will be used; if resulting cluster doesn't function as expected, make sure to review the configuration of VPC/subnets
2023-01-06 14:21:47 [ℹ]  nodegroup "linux-nodes" will use "" [AmazonLinux2/1.24]
2023-01-06 14:21:47 [ℹ]  using EC2 key pair %!q(*string=<nil>)
2023-01-06 14:21:47 [ℹ]  using Kubernetes version 1.24
2023-01-06 14:21:47 [ℹ]  creating EKS cluster "mwaa-eks" in "eu-central-1" region with managed nodes
2023-01-06 14:21:47 [ℹ]  will create 2 separate CloudFormation stacks for cluster itself and the initial managed nodegroup
2023-01-06 14:21:47 [ℹ]  if you encounter any issues, check CloudFormation console or try 'eksctl utils describe-stacks --region=eu-central-1 --cluster=mwaa-eks'
2023-01-06 14:21:47 [ℹ]  Kubernetes API endpoint access will use default of {publicAccess=true, privateAccess=false} for cluster "mwaa-eks" in "eu-central-1"
2023-01-06 14:21:47 [ℹ]  CloudWatch logging will not be enabled for cluster "mwaa-eks" in "eu-central-1"
2023-01-06 14:21:47 [ℹ]  you can enable it with 'eksctl utils update-cluster-logging --enable-types={SPECIFY-YOUR-LOG-TYPES-HERE (e.g. all)} --region=eu-central-1 --cluster=mwaa-eks'
2023-01-06 14:21:47 [ℹ]
2 sequential tasks: { create cluster control plane "mwaa-eks",
    2 sequential sub-tasks: {
        4 sequential sub-tasks: {
            wait for control plane to become ready,
            associate IAM OIDC provider,
            2 sequential sub-tasks: {
                create IAM role for serviceaccount "kube-system/aws-node",
                create serviceaccount "kube-system/aws-node",
            },
            restart daemonset "kube-system/aws-node",
        },
        create managed nodegroup "linux-nodes",
    }
}
2023-01-06 14:21:47 [ℹ]  building cluster stack "eksctl-mwaa-eks-cluster"
2023-01-06 14:21:49 [ℹ]  deploying stack "eksctl-mwaa-eks-cluster"
```

check cloudformation and come back in 10-15 mins

```
2023-01-06 14:27:56 [ℹ]  waiting for CloudFormation stack "eksctl-mwaa-eks-cluster"
2023-01-06 14:28:57 [ℹ]  waiting for CloudFormation stack "eksctl-mwaa-eks-cluster"
```

when it finishes you should see something similar to

```
2023-01-06 14:40:48 [ℹ]  waiting for the control plane to become ready
2023-01-06 14:40:50 [✔]  saved kubeconfig as "/Users/ricsue/.kube/config"
2023-01-06 14:40:50 [ℹ]  no tasks
2023-01-06 14:40:50 [✔]  all EKS cluster resources for "mwaa-eks" have been created
2023-01-06 14:40:51 [ℹ]  nodegroup "linux-nodes" has 3 node(s)
2023-01-06 14:40:51 [ℹ]  node "ip-10-192-10-251.eu-central-1.compute.internal" is ready
2023-01-06 14:40:51 [ℹ]  node "ip-10-192-10-57.eu-central-1.compute.internal" is ready
2023-01-06 14:40:51 [ℹ]  node "ip-10-192-11-142.eu-central-1.compute.internal" is ready
2023-01-06 14:40:51 [ℹ]  waiting for at least 1 node(s) to become ready in "linux-nodes"
2023-01-06 14:40:51 [ℹ]  nodegroup "linux-nodes" has 3 node(s)
2023-01-06 14:40:51 [ℹ]  node "ip-10-192-10-251.eu-central-1.compute.internal" is ready
2023-01-06 14:40:51 [ℹ]  node "ip-10-192-10-57.eu-central-1.compute.internal" is ready
2023-01-06 14:40:51 [ℹ]  node "ip-10-192-11-142.eu-central-1.compute.internal" is ready
2023-01-06 14:40:56 [ℹ]  kubectl command should work with "/Users/ricsue/.kube/config", try 'kubectl get nodes'
2023-01-06 14:40:56 [✔]  EKS cluster "mwaa-eks" in "eu-central-1" region is ready
```

Check its configured correctly

```
eksctl utils associate-iam-oidc-provider \
--region eu-central-1 \
--cluster mwaa-eks \
--approve
```

which will output

```
2023-01-06 15:03:17 [ℹ]  IAM Open ID Connect provider is already associated with cluster "mwaa-eks" in "eu-central-1"
```

**Creating a new Kubernetes namespace**

Create a new Kubernetes namespace where we will run our DAG

```
kubectl create namespace mwaa
```

which will output

```
namespace/mwaa created
```

and we can check by running

```
kubectl get ns
```

which should list our new namespace

```
NAME              STATUS   AGE
default           Active   37m
kube-node-lease   Active   37m
kube-public       Active   37m
kube-system       Active   37m
mwaa              Active   62s
```

**Create a role for the mwaa namespace**

Now you need to create a new Kubernetes manifest file that will create a role for the MWAA namespace.

If you run the following command:

```
kubectl get pods -n mwaa --as mwaa-service
```

You will probably get the following error message:

```
Error from server (Forbidden): pods is forbidden: User "mwaa-service" cannot list resource "pods" in API group "" in the namespace "mwaa"
```

So lets fix that. First we are going to create and apply a new role for the MWAA namespace.


```
cat << EOF | kubectl apply -f - -n mwaa
kind: Role
apiVersion: rbac.authorization.k8s.io/v1
metadata:
  name: mwaa-role
rules:
  - apiGroups:
      - ""
      - "apps"
      - "batch"
      - "extensions"
    resources:      
      - "jobs"
      - "pods"
      - "pods/attach"
      - "pods/exec"
      - "pods/log"
      - "pods/portforward"
      - "secrets"
      - "services"
    verbs:
      - "create"
      - "delete"
      - "describe"
      - "get"
      - "list"
      - "patch"
      - "update"
---
kind: RoleBinding
apiVersion: rbac.authorization.k8s.io/v1
metadata:
  name: mwaa-role-binding
subjects:
- kind: User
  name: mwaa-service
roleRef:
  kind: Role
  name: mwaa-role
  apiGroup: rbac.authorization.k8s.io
EOF

```

When you run this, you should get the following

```
role.rbac.authorization.k8s.io/mwaa-role created
rolebinding.rbac.authorization.k8s.io/mwaa-role-binding created
```

Now if we try again the command ("kubectl get pods -n mwaa --as mwaa-service") that generated the error above, we should get a new output

```
No resources found in mwaa namespace.
```

**Modifying the MWAA Worker Execution policy**

You now need to create a new MWAA Worker Execution role with an updated policy. The steps are 1/ Create a new IAM policy, 2/ Create a new IAM Role and attach the policy you created in Step 1, and 3/ Reconfigure your MWAA environment to use this new IAM Role.

When creating a new IAM policy, copy the existing policy statements you have in your MWAA Execution policy, but add the following (replacing {AWS ACCOUNT NUMBER} with your AWS account):

```
        {
            "Effect": "Allow",
            "Action": [
                "eks:DescribeCluster"
            ],
            "Resource": "arn:aws:eks:eu-central-1:{AWS ACCOUNT NUMBER}:cluster/mwaa-eks"
        } 
```

This is the complete new role that I created

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": "airflow:PublishMetrics",
            "Resource": "arn:aws:airflow:eu-central-1:{AWS ACCOUNT NUMBER}:environment/EKSMultiAccount"
        },
        {
            "Effect": "Deny",
            "Action": "s3:ListAllMyBuckets",
            "Resource": [
                "arn:aws:s3:::airflow-eks-multi-account",
                "arn:aws:s3:::airflow-eks-multi-account/*"
            ]
        },
        {
            "Effect": "Allow",
            "Action": [
                "s3:GetObject*",
                "s3:GetBucket*",
                "s3:List*"
            ],
            "Resource": [
                "arn:aws:s3:::airflow-eks-multi-account",
                "arn:aws:s3:::airflow-eks-multi-account/*"
            ]
        },
        {
            "Effect": "Allow",
            "Action": [
                "logs:CreateLogStream",
                "logs:CreateLogGroup",
                "logs:PutLogEvents",
                "logs:GetLogEvents",
                "logs:GetLogRecord",
                "logs:GetLogGroupFields",
                "logs:GetQueryResults"
            ],
            "Resource": [
                "arn:aws:logs:eu-central-1:{AWS ACCOUNT NUMBER}:log-group:airflow-EKSMultiAccount-*"
            ]
        },
        {
            "Effect": "Allow",
            "Action": [
                "logs:DescribeLogGroups"
            ],
            "Resource": [
                "*"
            ]
        },
        {
            "Effect": "Allow",
            "Action": "cloudwatch:PutMetricData",
            "Resource": "*"
        },
        {
            "Effect": "Allow",
            "Action": [
                "sqs:ChangeMessageVisibility",
                "sqs:DeleteMessage",
                "sqs:GetQueueAttributes",
                "sqs:GetQueueUrl",
                "sqs:ReceiveMessage",
                "sqs:SendMessage"
            ],
            "Resource": "arn:aws:sqs:eu-central-1:*:airflow-celery-*"
        },
        {
            "Effect": "Allow",
            "Action": [
                "kms:Decrypt",
                "kms:DescribeKey",
                "kms:GenerateDataKey*",
                "kms:Encrypt"
            ],
            "NotResource": "arn:aws:kms:*:{AWS ACCOUNT NUMBER}:key/*",
            "Condition": {
                "StringLike": {
                    "kms:ViaService": [
                        "sqs.eu-central-1.amazonaws.com"
                    ]
                }
            }
        },
        {
            "Effect": "Allow",
            "Action": [
                "eks:DescribeCluster"
            ],
            "Resource": "arn:aws:eks:eu-central-1:{AWS ACCOUNT NUMBER}:cluster/mwaa-eks"
        }
    ]
}
```

Once you have updated your MWAA Worker Execution role with this new role, the MWAA environment will take 20-30 minutes to update. However, we need to make one more change that will also require a restart, so complete the next step so we only have to do this once.

**Deploying the Kubernetes operators into Apache Airflow**

Create a new requirements.txt file with the following:

```
kubernetes==11.0.0
apache-airflow[cncf.kubernetes]
```

And then in the S3 bucket that you are using for your MWAA environment, create a folder and upload this file. You will then need to edit your environment to point to this requirements.txt file. Once updated, the MWAA environment will need to update which may take 20-25 minutes to complete.

> Tip! You can track and debug Python library loading and import issues by reviewing the CloudWatch logs for the MWAA Worker nodes. There will be a "requirements_install_***" log file which you can view and this will help you troubleshoot issues.

**Creating a new identity mapping**

Use the following command to create a new identity mapping for Amazon EKS (replacing {AWS ACCOUNT NUMBER} with your AWS account number)


```
eksctl create iamidentitymapping \
--region eu-central-1 \
--cluster mwaa-eks \
--arn arn:aws:iam::{AWS ACCOUNT NUMBER}:role/mwaa-eks-multi-account-role \
--username mwaa-service
```

which should output something like

```
2023-01-06 16:21:17 [ℹ]  checking arn arn:aws:iam::{AWS ACCOUNT NUMBER}:role/mwaa-eks-multi-account-role against entries in the auth ConfigMap
2023-01-06 16:21:17 [ℹ]  adding identity "arn:aws:iam::{AWS ACCOUNT NUMBER}:role/mwaa-eks-multi-account-role" to auth ConfigMap
```

**Creating your kubeconfig file**

When we use the KubernetesPodOperator we need to provide a kube_config.yaml file which we will upload into the same folder as our DAG. To create this, we use the following command.

```
aws eks update-kubeconfig \
--region eu-central-1 \
--kubeconfig ./kube_config.yaml \
--name mwaa-eks \
--alias aws
```
Which will display the following output

```
Added new context aws to /Users/ricsue/Projects/keys/ssh-keygen-keys/kube_config.yaml
```

You should now have your kube_config.yaml file in the same folder (where {AWS ACCOUNT NUMBER} is your AWS Account number).

```
apiVersion: v1
clusters:
- cluster:
    certificate-authority-data: REDACTED....REDACTED....REDACTED....REDACTED....REDACTED....REDACTED....REDACTED....REDACTED....REDACTED....REDACTED....REDACTED....REDACTED....REDACTED....REDACTED....REDACTED....REDACTED....REDACTED....REDACTED....REDACTED....REDACTED....REDACTED....REDACTED....REDACTED....REDACTED....REDACTED....REDACTED....REDACTED....REDACTED....REDACTED....REDACTED....==
    server: https://REDACTED.gr7.eu-central-1.eks.amazonaws.com
  name: arn:aws:eks:eu-central-1:{AWS ACCOUNT NUMBER}:cluster/mwaa-eks
contexts:
- context:
    cluster: arn:aws:eks:eu-central-1:{AWS ACCOUNT NUMBER}:cluster/mwaa-eks
    user: arn:aws:eks:eu-central-1:{AWS ACCOUNT NUMBER}:cluster/mwaa-eks
  name: aws
current-context: aws
kind: Config
preferences: {}
users:
- name: arn:aws:eks:eu-central-1:{AWS ACCOUNT NUMBER}:cluster/mwaa-eks
  user:
    exec:
      apiVersion: client.authentication.k8s.io/v1beta1
      args:
      - --region
      - eu-central-1
      - eks
      - get-token
      - --cluster-name
      - mwaa-eks
      command: aws
```

**Creating your Apache Airflow DAG**

Create your DAG, using the following sample code. This DAG uses the aws-cli public container and runs a simple aws cli command to output the AWS account number.

> Note! You will notice the path to the kube_config.yaml file is /usr/local/airflow/dags/kube_config.yaml - you do not need to edit/change this (as long as your config file was not renamed from kube_config.yaml)

```
from airflow import DAG
from datetime import datetime
from airflow.providers.cncf.kubernetes.operators.kubernetes_pod import KubernetesPodOperator

default_args = {
   'owner': 'aws',
   'depends_on_past': False,
   'start_date': datetime(2019, 2, 20),
   'provide_context': True
}

dag = DAG(
   'kubernetes_pod_example', default_args=default_args, schedule_interval=None)

kube_config_path = '/usr/local/airflow/dags/kube_config.yaml'

podRun = KubernetesPodOperator(
                       namespace="mwaa",
                       #image="ubuntu:18.04",
                       image="public.ecr.aws/aws-cli/aws-cli",
                       cmds=["bash"],
                       arguments=["-c", "aws sts get-caller-identity --query 'Account' --output text"],
                       labels={"foo": "bar"},
                       name="mwaa-pod-test",
                       task_id="pod-task",
                       get_logs=True,
                       dag=dag,
                       is_delete_operator_pod=False,
                       config_file=kube_config_path,
                       in_cluster=False,
                       cluster_context='aws'
                       )
```

> **Error and Debugging**
>
> When I initially ran this, I got the following error
> ```
> kubernetes.client.rest.ApiException: (401)
> Reason: Unauthorized
> HTTP response headers: HTTPHeaderDict({'Audit-Id': '2c8f0848-1506-44ec-92a8-772c8756e1ee', 'Cache-Control': 'no-cache, private', 'Content-Type': 'application/json', 'Date': 'Fri, 06 Jan 2023 17:05:51 GMT', 'Content-Length': '129'})
> HTTP response body: {"kind":"Status","apiVersion":"v1","metadata":{},"status":"Failure","message":"Unauthorized","reason":"Unauthorized","code":401}
> ```
> 
> If you get this, then I suggest waiting a few moments. When I initially triggered the DAG I got this error. When I then went for a short lunch break and tried again, it worked.
> 

When you trigger this, it should output the AWS account number where the Kubernetes Pod is running. This is what I get when I run this:

```
[2023-01-09, 10:41:30 UTC] {{logging_mixin.py:109}} INFO - Running <TaskInstance: kubernetes_pod_example.pod-task manual__2023-01-09T10:41:21.080681+00:00 [running]> on host ip-10-192-20-19.eu-central-1.compute.internal
[2023-01-09, 10:41:30 UTC] {{taskinstance.py:1429}} INFO - Exporting the following env vars:
AIRFLOW_CTX_DAG_OWNER=aws
AIRFLOW_CTX_DAG_ID=kubernetes_pod_example
AIRFLOW_CTX_TASK_ID=pod-task
AIRFLOW_CTX_EXECUTION_DATE=2023-01-09T10:41:21.080681+00:00
AIRFLOW_CTX_DAG_RUN_ID=manual__2023-01-09T10:41:21.080681+00:00
[2023-01-09, 10:41:30 UTC] {{kubernetes_pod.py:566}} INFO - Creating pod mwaa-pod-test.0de50f0e9f0f44a788cc15dadc0052e7 with labels: {'dag_id': 'kubernetes_pod_example', 'task_id': 'pod-task', 'execution_date': '2023-01-09T104121.0806810000-b4d079a05', 'try_number': '1'}
[2023-01-09, 10:41:31 UTC] {{pod_manager.py:157}} WARNING - Pod not yet started: mwaa-pod-test.0de50f0e9f0f44a788cc15dadc0052e7
[2023-01-09, 10:41:32 UTC] {{pod_manager.py:157}} WARNING - Pod not yet started: mwaa-pod-test.0de50f0e9f0f44a788cc15dadc0052e7
[2023-01-09, 10:41:33 UTC] {{pod_manager.py:197}} INFO - {AWS ACCOUNT NUMBER}
[2023-01-09, 10:41:33 UTC] {{pod_manager.py:215}} WARNING - Pod mwaa-pod-test.0de50f0e9f0f44a788cc15dadc0052e7 log read interrupted but container base still running
[2023-01-09, 10:41:34 UTC] {{pod_manager.py:197}} INFO - {AWS ACCOUNT NUMBER}
[2023-01-09, 10:41:34 UTC] {{pod_manager.py:234}} INFO - Pod mwaa-pod-test.0de50f0e9f0f44a788cc15dadc0052e7 has phase Running
[2023-01-09, 10:41:36 UTC] {{kubernetes_pod.py:462}} INFO - skipping deleting pod: mwaa-pod-test.0de50f0e9f0f44a788cc15dadc0052e7
[2023-01-09, 10:41:37 UTC] {{taskinstance.py:1280}} INFO - Marking task as SUCCESS. dag_id=kubernetes_pod_example, task_id=pod-task, execution_date=20230109T104121, start_date=20230109T104130, end_date=20230109T104137
[2023-01-09, 10:41:37 UTC] {{local_task_job.py:154}} INFO - Task exited with return code 0
[2023-01-09, 10:41:37 UTC] {{local_task_job.py:264}} INFO - 0 downstream tasks scheduled from follow-on schedule check
```

You should be able to see your account number where I have shown {AWS ACCOUNT NUMBER} above.

We have now completed the first step which is configuring MWAA to execute within an Amazon EKS cluster in the SAME account as MWAA is running. 

The next step is to get MWAA to execute a task on an Amazon EKS cluster in a different AWS account.

>
> Note!, whilst I will be using a different AWS account,  I will stick within the same AWS Region
> 

**Setting up my EKS Cluster in a new Account**

As I am not going to have a MWAA environment in this new AWS Account, I need to setup the Amazon EKS environment a little differently.

In my second AWS account I have set up a new VPC with public/private subnets in the same AWS Region, and I have also created a new keypair which is used when we create the new EKS Cluster. You will notice here that I am using the "--profile personal" which I have configured in my local .aws/credentials to point to an IAM user in the new account.

I create my new EKS Cluster (called mwaa-eks2) using this command: 

```
eksctl create cluster \
--name mwaa-eks2 \
--region eu-central-1 \
--version 1.24 \
--nodegroup-name linux-nodes \
--nodes 3 \
--nodes-min 1 \
--nodes-max 4 \
--with-oidc \
--ssh-access \
--ssh-public-key mwaa-eks \
--managed \
--vpc-public-subnets "subnet-081d77fe5ceb5ae90, subnet-0b9b3a80c1f5d046b" \
--vpc-private-subnets "subnet-014a24745c5edbbbd, subnet-0d9dc9f06d773243b" \
--profile personal
```

Configure IAM

```
eksctl utils associate-iam-oidc-provider \
--region eu-central-1 \
--cluster mwaa-eks2 \
--approve \
--profile personal
```

Create a Kubernetes namespace called mwaa2

```
kubectl create namespace mwaa2
```

Create the mwaa-role and service mapping

```
cat << EOF | kubectl apply -f - -n mwaa2
kind: Role
apiVersion: rbac.authorization.k8s.io/v1
metadata:
  name: mwaa-role
rules:
  - apiGroups:
      - ""
      - "apps"
      - "batch"
      - "extensions"
    resources:      
      - "jobs"
      - "pods"
      - "pods/attach"
      - "pods/exec"
      - "pods/log"
      - "pods/portforward"
      - "secrets"
      - "services"
    verbs:
      - "create"
      - "delete"
      - "describe"
      - "get"
      - "list"
      - "patch"
      - "update"
---
kind: RoleBinding
apiVersion: rbac.authorization.k8s.io/v1
metadata:
  name: mwaa-role-binding
subjects:
- kind: User
  name: mwaa-service
roleRef:
  kind: Role
  name: mwaa-role
  apiGroup: rbac.authorization.k8s.io
EOF
```

We can make sure this all looks good by typing this command, and we should get the same output as we did when we ran it above.

```
kubectl get pods -n mwaa2 --as mwaa-service
```
**EKS Role and Permissions**

We now need to create and attach an IAM role that will allow the MWAA execution workers to access this new EKS Cluster. We are going to keep this policy simple, but you should scope down the IAM Actions if you are doing this in production.

Create a new IAM Policy and Role. Create the policy first as follows

```
{ 
  "Version": "2012-10-17",
   "Statement": [
      {
          "Effect": "Allow",
          "Action": [
            "eks:*"
            ],
          "Resource": "arn:aws:eks:eu-central-1:{2ND AWS ACCOUNT NUMBER}:cluster/mwaa-eks2"
       }
     ]
}
```

Now create a new role, and then attach this to the Role you create. You will need to change the TRUST ASSOCIATION of the Role so that the MWAA execution worker can assume this role:

```
{
	"Version": "2012-10-17",
	"Statement": [
		{
			"Effect": "Allow",
			"Principal": {
				"AWS": "arn:aws:iam::{AWS ACCOUNT NUMBER}:role/mwaa-eks-multi-account-role"
			},
			"Action": "sts:AssumeRole",
			"Condition": {}
		}
	]
}
```

The final step is to attach this to the new EKS Cluster we have running in the second account.

```
eksctl create iamidentitymapping \
--region eu-central-1 \
--cluster mwaa-eks2 \
--arn arn:aws:iam::{2ND AWS ACCOUNT NUMBER}:role/mwaa-eks-access \
--username mwaa-service \
--profile personal
```

which should generate the following:

```
2023-01-09 14:35:15 [ℹ]  checking arn arn:aws:iam::{2ND AWS ACCOUNT NUMBER}:role/mwaa-eks-access against entries in the auth ConfigMap
2023-01-09 14:35:15 [ℹ]  adding identity "arn:aws:iam::{2ND AWS ACCOUNT NUMBER}:role/mwaa-eks-access" to auth ConfigMap
```

**Updating the MWAA Execution permissions**

Now we add the following to the MWAA Execution policy of the first AWS Account where we have MWAA running. All we need to do is append this to the permissions:

```
        {
            "Effect": "Allow",
            "Action": [
                "sts:AssumeRole"
            ],
            "Resource": "arn:aws:iam::{2ND AWS ACCOUNT NUMBER}:role/mwaa-eks-access"
       }
```

the complete policy now looks like this:

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": "airflow:PublishMetrics",
            "Resource": "arn:aws:airflow:eu-central-1:{AWS ACCOUNT NUMBER}:environment/EKSMultiAccount"
        },
        {
            "Effect": "Deny",
            "Action": "s3:ListAllMyBuckets",
            "Resource": [
                "arn:aws:s3:::airflow-eks-multi-account",
                "arn:aws:s3:::airflow-eks-multi-account/*"
            ]
        },
        {
            "Effect": "Allow",
            "Action": [
                "s3:GetObject*",
                "s3:GetBucket*",
                "s3:List*"
            ],
            "Resource": [
                "arn:aws:s3:::airflow-eks-multi-account",
                "arn:aws:s3:::airflow-eks-multi-account/*"
            ]
        },
        {
            "Effect": "Allow",
            "Action": [
                "logs:CreateLogStream",
                "logs:CreateLogGroup",
                "logs:PutLogEvents",
                "logs:GetLogEvents",
                "logs:GetLogRecord",
                "logs:GetLogGroupFields",
                "logs:GetQueryResults"
            ],
            "Resource": [
                "arn:aws:logs:eu-central-1:{AWS ACCOUNT NUMBER}:log-group:airflow-EKSMultiAccount-*"
            ]
        },
        {
            "Effect": "Allow",
            "Action": [
                "logs:DescribeLogGroups"
            ],
            "Resource": [
                "*"
            ]
        },
        {
            "Effect": "Allow",
            "Action": "cloudwatch:PutMetricData",
            "Resource": "*"
        },
        {
            "Effect": "Allow",
            "Action": [
                "sqs:ChangeMessageVisibility",
                "sqs:DeleteMessage",
                "sqs:GetQueueAttributes",
                "sqs:GetQueueUrl",
                "sqs:ReceiveMessage",
                "sqs:SendMessage"
            ],
            "Resource": "arn:aws:sqs:eu-central-1:*:airflow-celery-*"
        },
        {
            "Effect": "Allow",
            "Action": [
                "kms:Decrypt",
                "kms:DescribeKey",
                "kms:GenerateDataKey*",
                "kms:Encrypt"
            ],
            "NotResource": "arn:aws:kms:*:{AWS ACCOUNT NUMBER}:key/*",
            "Condition": {
                "StringLike": {
                    "kms:ViaService": [
                        "sqs.eu-central-1.amazonaws.com"
                    ]
                }
            }
        },
        {
            "Effect": "Allow",
            "Action": [
                "eks:DescribeCluster"
            ],
            "Resource": "arn:aws:eks:eu-central-1:{AWS ACCOUNT NUMBER}:cluster/mwaa-eks"
        },
        {
            "Effect": "Allow",
            "Action": [
                "sts:AssumeRole"
            ],
            "Resource": "arn:aws:iam::{2ND AWS ACCOUNT NUMBER}:role/mwaa-eks-access"
        }
    ]
}
```
**Creating a new kube_config.yaml**

Once we have done this, we can create a new kube_config.yaml file to include details of the new EKS Cluster in the second AWS account.


```
aws eks update-kubeconfig \
--region eu-central-1 \
--kubeconfig ./kube_config_2.yaml \
--name mwaa-eks2 \
--alias aws \
--profile personal

```
We need to modify to add this to add the IAM Role details to the user section

```
      - --role       
      - arn:aws:iam::{2ND AWS ACCOUNT NUMBER}:role/mwaa-eks-access
```

so the full config file now looks like

```
apiVersion: v1
clusters:
- cluster:
    certificate-authority-data: REDACTED....REDACTED....==
    server: https://ENDPOINT.gr7.eu-central-1.eks.amazonaws.com
  name: arn:aws:eks:eu-central-1:{2nd AWS ACCOUNT}:cluster/mwaa-eks2
contexts:
- context:
    cluster: arn:aws:eks:eu-central-1:{2nd AWS ACCOUNT}:cluster/mwaa-eks2
    user: arn:aws:eks:eu-central-1:{2nd AWS ACCOUNT}:cluster/mwaa-eks2
  name: aws
current-context: aws
kind: Config
preferences: {}
users:
- name: arn:aws:eks:eu-central-1:{2nd AWS ACCOUNT}:cluster/mwaa-eks2
  user:
    exec:
      apiVersion: client.authentication.k8s.io/v1beta1
      args:
      - --region
      - eu-central-1
      - eks
      - get-token
      - --cluster-name
      - mwaa-eks2
      - --role       
      - arn:aws:iam::{2nd AWS ACCOUNT}:role/mwaa-eks-access
      command: aws

```

**Updating the DAG**

I create a new DAG file based on the original, changing a few details to point to both the new kube_config file as well as the different Kubernetes namespace.

```
from airflow import DAG
from datetime import datetime
from airflow.providers.cncf.kubernetes.operators.kubernetes_pod import KubernetesPodOperator

default_args = {
   'owner': 'aws',
   'depends_on_past': False,
   'start_date': datetime(2019, 2, 20),
   'provide_context': True
}

dag = DAG(
   'kubernetes_pod_example2', default_args=default_args, schedule_interval=None)

#use a kube_config stored in s3 dags folder for now
kube_config_path = '/usr/local/airflow/dags/kube_config_2.yaml'

podRun = KubernetesPodOperator(
                       namespace="mwaa2",
                       #image="ubuntu:18.04",
                       image="public.ecr.aws/aws-cli/aws-cli",
                       cmds=["bash"],
                       arguments=["-c", "aws sts get-caller-identity --query 'Account' --output text"],
                       labels={"foo": "bar"},
                       name="mwaa-pod-test",
                       task_id="pod-task",
                       get_logs=True,
                       dag=dag,
                       is_delete_operator_pod=False,
                       config_file=kube_config_path,
                       in_cluster=False,
                       cluster_context='aws'
                       )
```

And that should be it. When we upload the new DAG and Kube Config files, and then trigger the new DAG. We see the following output:

```
[2023-01-09, 14:39:10 UTC] {{kubernetes_pod.py:566}} INFO - Creating pod mwaa-pod-test.2b6eb7ab07a44b5f99c7fcef440b783b with labels: {'dag_id': 'kubernetes_pod_example2', 'task_id': 'pod-task', 'execution_date': '2023-01-09T143906.4245000000-ca84eb319', 'try_number': '1'}
[2023-01-09, 14:39:11 UTC] {{pod_manager.py:157}} WARNING - Pod not yet started: mwaa-pod-test.2b6eb7ab07a44b5f99c7fcef440b783b
[2023-01-09, 14:39:12 UTC] {{pod_manager.py:157}} WARNING - Pod not yet started: mwaa-pod-test.2b6eb7ab07a44b5f99c7fcef440b783b
[2023-01-09, 14:39:13 UTC] {{pod_manager.py:157}} WARNING - Pod not yet started: mwaa-pod-test.2b6eb7ab07a44b5f99c7fcef440b783b
[2023-01-09, 14:39:14 UTC] {{pod_manager.py:157}} WARNING - Pod not yet started: mwaa-pod-test.2b6eb7ab07a44b5f99c7fcef440b783b
[2023-01-09, 14:39:15 UTC] {{pod_manager.py:157}} WARNING - Pod not yet started: mwaa-pod-test.2b6eb7ab07a44b5f99c7fcef440b783b
[2023-01-09, 14:39:16 UTC] {{pod_manager.py:157}} WARNING - Pod not yet started: mwaa-pod-test.2b6eb7ab07a44b5f99c7fcef440b783b
[2023-01-09, 14:39:17 UTC] {{pod_manager.py:157}} WARNING - Pod not yet started: mwaa-pod-test.2b6eb7ab07a44b5f99c7fcef440b783b
[2023-01-09, 14:39:18 UTC] {{pod_manager.py:157}} WARNING - Pod not yet started: mwaa-pod-test.2b6eb7ab07a44b5f99c7fcef440b783b
[2023-01-09, 14:39:19 UTC] {{pod_manager.py:197}} INFO - {2nd AWS ACCOUNT}
[2023-01-09, 14:39:22 UTC] {{pod_manager.py:234}} INFO - Pod mwaa-pod-test.2b6eb7ab07a44b5f99c7fcef440b783b has phase Running
[2023-01-09, 14:39:24 UTC] {{kubernetes_pod.py:462}} INFO - skipping deleting pod: mwaa-pod-test.2b6eb7ab07a44b5f99c7fcef440b783b
[2023-01-09, 14:39:24 UTC] {{taskinstance.py:1280}} INFO - Marking task as SUCCESS. dag_id=kubernetes_pod_example2, task_id=pod-task, execution_date=20230109T143906, start_date=20230109T143909, end_date=20230109T143924
[2023-01-09, 14:39:25 UTC] {{local_task_job.py:154}} INFO - Task exited with return code 0
[2023-01-09, 14:39:25 UTC] {{local_task_job.py:264}} INFO - 0 downstream tasks scheduled from follow-on schedule check
```

We can see the output has changed, and we now see the {2nd AWS ACCOUNT} number listed. Congratulations, you have now run your task on an EKS Cluster in a different AWS account.

**Cleaning up**

Once you have gone through this, be sure to clean up and delete these resources that you have created. The quickest way is to go to the CloudFormation and delete the stacks that have been created. It will take around 30-40 minutes for the cleanup to complete.

**Conclusion**

In this short walk through, we built upon a previous blog post [Working with Amazon EKS and Amazon Managed Workflows for Apache Airflow v2.x](https://dev.to/aws/working-with-amazon-eks-and-amazon-managed-workflows-for-apache-airflow-v2-x-k12) and extended this to show how you can run those tasks on other AWS Accounts.
