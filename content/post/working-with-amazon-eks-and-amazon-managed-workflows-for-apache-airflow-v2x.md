---
title: 'Working with Amazon EKS and Amazon Managed Workflows for Apache Airflow v2.x'
date: '2021-06-10'
tags: [Apache Airflow, aws, kubernetes]
---
### Introduction

The Apache Airflow slack channel is a vibrant community of open source builders that is a great source of feedback, knowledge and answers to problems and use cases you might have when trying to do stuff with Apache Airflow. This week I picked up on someone seeing errors with Amazon EKS, and so I thought what better time to try out the new Apache Airflow 2.x version that was recently launched in Amazon Managed Workflows for Apache Airflow (MWAA).

In this post, I will explore one of the code examples in the 
MWAA documentation, [Using Amazon MWAA with Amazon EKS](https://aws-oss.beachgeek.co.uk/ls) and specifically look at getting this up and running with the recently announced Apache Airflow 2.x. The post assumes that you already have your MWAA 2.x environment up and running.

### What will you need

* An AWS account with the right level of privileges
* The latest/up to date aws cli - at least version 1.19.73 / 2.24
* The eksctl and kubectl command line tools - you can find details on how to install those from the original documentation guide linked above
* A MWAA environment up and running - may I suggest you check out some of my earlier blog post [like this one if you are familiar with AWS CDK](https://dev.to/aws/using-aws-cdk-to-deploy-your-amazon-managed-workflows-for-apache-airflow-environment-12cf) or [this one](https://dev.to/aws/automating-the-installation-of-managed-workflows-for-apache-airflow-5h8a), if you are not. All you will need to do is change the version number in the template/CDK app to "2.0.2" from the current version of "1.10.12"
* An EC2 key pair for the region you have deployed your MWAA environment

I ran this on my Mac and on my Ubuntu desktop, but I have not tried it on Windows but cannot see why it would not work on that too.

### Creating the Amazon EKS Cluster

As per the original documentation, you will need to create a public key from an EC2 keypair in your region. I already had one that I use, but if you do not, then you can either use the AWS cli or Console to create one. Ensure you create it in the SAME region as your MWAA environment.

We will also create a folder to keep everything that we are creating in one place.

```
mkdir mwaa-eks
cd mwaa-eks
ssh-keygen -y -f airflow-eu-2.pem > airflow-eu-2.pub
```

We now can create our Amazon EKS cluster. We are going to call this "mwaa-2-eks" and deploy this in the same region as our MWAA environment. We need to additionally add the EC2 keypair information and details of the Private and Public subnets of the MWAA environment.

When you created your MWAA environment, you will have created a VPC. If you used the AWS CDK or CloudFormation templates linked above, you can go to the CloudFormation console to view the resources created, and obtain the Subnet info for your MWAA environment.

This is what my command looks like, yours will look different.

```
eksctl create cluster \
--name mwaa-2-eks \
--region eu-central-1 \
--version 1.18 \
--nodegroup-name linux-nodes \
--nodes 3 \
--nodes-min 1 \
--nodes-max 4 \
--with-oidc \
--ssh-access \
--ssh-public-key airflow-eu-2 \
--managed \
--vpc-public-subnets "subnet-0e15c476b96769dd0, subnet-0a49eb679f8c55f5b" \
--vpc-private-subnets "subnet-051d91dcd0103d0b3, subnet-00ac6b944d5a0e902"
```
When we run this, we can check in CloudFormation console for any issues. This takes a few minutes (about 5 mins when I ran this) to complete. You can confirm all is good by running the following command:

```
eksctl utils associate-iam-oidc-provider \
--region eu-central-1 \
--cluster mwaa-2-eks \
--approve
```
And you should get output like

```
[ℹ]  eksctl version 0.35.0
[ℹ]  using region eu-central-1
[ℹ]  IAM Open ID Connect provider is already associated with cluster "mwaa-2-eks" in "eu-central-1"
```

The next step is to create a new namespace in EKS, which we do running this command

```
kubectl create namespace mwaa
```
which should return the following if successful.

```
namespace/mwaa created
```

### Updating permissions for your MWAA environment

The next step is to create a new role. From the same terminal, run this command.

```
cat << EOF | kubectl apply -f - -n mwaa
kind: Role
apiVersion: rbac.authorization.k8s.io/v1beta1
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
apiVersion: rbac.authorization.k8s.io/v1beta1
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

which will generate the following if successful

```
role.rbac.authorization.k8s.io/mwaa-role created
rolebinding.rbac.authorization.k8s.io/mwaa-role-binding created
```
and you can check this by running the following command

```
kubectl get pods -n mwaa --as mwaa-service
```
which for the time being will return

```
No resources found in mwaa namespace.
```

We need to update/create a new IAM policy for the MWAA environment. I am not going to go into details here on how to do that, other than outline the steps I took:

* create a new IAM policy (which I called mwaa-2-ekspolicy)
* create a new IAM role (which I called mwaa-2-eks-role) which uses that policy created in the previous step
* update the MWAA environment Execution policy to use this new role

This is the policy I created, based on the MWAA environment I setup using the AWS CDK deployment

```

    "Version": "2012-10-17",
    "Statement": [
        {
            "Action": "airflow:PublishMetrics",
            "Resource": "arn:aws:airflow:eu-central-1:xxxxxxxxxxxx:environment/cdk-ricsue-demo-delete",
            "Effect": "Allow"
        },
        {
            "Action": "s3:ListAllMyBuckets",
            "Resource": [
                "arn:aws:s3:::airflow-ricsue-cdk-demo/*",
                "arn:aws:s3:::airflow-ricsue-cdk-demo"
            ],
            "Effect": "Deny"
        },
        {
            "Action": "s3:*",
            "Resource": [
                "arn:aws:s3:::airflow-ricsue-cdk-demo/*",
                "arn:aws:s3:::airflow-ricsue-cdk-demo"
            ],
            "Effect": "Allow"
        },
        {
            "Action": [
                "logs:CreateLogStream",
                "logs:CreateLogGroup",
                "logs:PutLogEvents",
                "logs:GetLogEvents",
                "logs:GetLogRecord",
                "logs:GetLogGroupFields",
                "logs:GetQueryResults"
            ],
            "Resource": "arn:aws:logs:eu-central-1:xxxxxxxxxxxx:log-group:airflow-cdk-ricsue-demo-delete-*",
            "Effect": "Allow"
        },
        {
            "Action": "logs:DescribeLogGroups",
            "Resource": "*",
            "Effect": "Allow"
        },
        {
            "Effect": "Allow",
            "Action": "cloudwatch:PutMetricData",
            "Resource": "*"
        },
        {
            "Action": [
                "sqs:ChangeMessageVisibility",
                "sqs:DeleteMessage",
                "sqs:GetQueueAttributes",
                "sqs:GetQueueUrl",
                "sqs:ReceiveMessage",
                "sqs:SendMessage"
            ],
            "Resource": "arn:aws:sqs:eu-central-1:*:airflow-celery-*",
            "Effect": "Allow"
        },
        {
            "Condition": {
                "StringEquals": {
                    "kms:ViaService": [
                        "sqs.eu-central-1.amazonaws.com",
                        "s3.eu-central-1.amazonaws.com"
                    ]
                }
            },
            "Action": [
                "kms:Decrypt",
                "kms:DescribeKey",
                "kms:GenerateDataKey*",
                "kms:Encrypt"
            ],
            "Resource": "*",
            "Effect": "Allow"
        },
        {
            "Effect": "Allow",
            "Action": [
                "eks:DescribeCluster"
            ],
            "Resource": "arn:aws:eks:eu-central-1:xxxxxxxxxxxx:cluster/mwaa-2-eks"
        }
    ]
}
```

Make sure that the role you created is also has the correct Trust association for MWAA, which I configured as follows. This ensures that MWAA can uses this role.

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
    }
  ]
}
```

### Updating your MWAA environment 

Before we update the MWAA environment for that IAM role update to take affect, we also need to create a requirements.txt file so that we can load up some dependencies that the KubernetesPodOperator will need.

One of the changes with MWAA when you create an Apache 2.x environment is that not all the providers are deployed, which means we need to install them. You can read more [here](https://docs.aws.amazon.com/mwaa/latest/userguide/airflow-versions.html#airflow-versions-what-changed-202) 

I created a txt file with the following

```
awscli
kubernetes
cryptography
watchtower==1.0.6
apache-airflow[cncf.kubernetes]==2.0.2
apache-airflow-providers-http==1.1.1
apache-airflow-providers-ssh==1.3.0
apache-airflow-providers-postgres==1.0.1
```

Once you have created this file, upload it to the Apache Airflow DAG's Amazon S3 bucket. This is the folder structure I have setup (created by the CDK app), and I created a folder called "requirements" and the uploaded the requirements.txt into this folder.

```
airflow-ricsue-cdk-demo
├── dags
│   └── <empty>
└── requirements
    └── requirements.txt
```

I now update the MWAA environment, and make two updates:

* update the MWAA Execution role to use the newly created one
* add a "requirements.txt" configuration that points to this file. 

This will cause your environment to update, so will take 10-15 mins to complete.

Once the environment has finished (it will say Available) you can now create an identity mapping for EKS using the IAM role we create above.

```
eksctl create iamidentitymapping \
--region eu-central-1 \
--cluster mwaa-2-eks \
--arn arn:aws:iam::xxxxxxxxxxxx:role/mwaa-2-eks-role \
--username mwaa-service
```

Which should output something like this: 

```
[ℹ]  eksctl version 0.35.0
[ℹ]  using region eu-central-1
[ℹ]  adding identity "arn:aws:iam::704533066374:role/mwaa-2-eks-role" to auth ConfigMap
```

### Creating the kube_config

We now need to create the kube_config.yaml by running this command

```
aws eks update-kubeconfig \
--region eu-central-1 \
--kubeconfig ./kube_config.yaml \
--name mwaa-2-eks \
--alias aws
```
which will output the following
```
Added new context aws to /Users/ricsue/Projects/CloudBuilders/Airflow/eks/kube_config.yaml
```

It also creates in the directory where you ran the command, a file called kube_config.yaml which we need to edit. Edit this file, and at the end, replace

```
command: aws
```
with
```
command: /usr/local/airflow/.local/bin/aws
```

This was what my finished file looked like:

```
apiVersion: v1
clusters:
- cluster:
    certificate-authority-data: <redacted>
    server: https://<yourecrhost>.gr7.eu-central-1.eks.amazonaws.com
  name: arn:aws:eks:eu-central-1:xxxxxxxxxxxx:cluster/mwaa-2-eks
contexts:
- context:
    cluster: arn:aws:eks:eu-central-1:xxxxxxxxxxxx:cluster/mwaa-2-eks
    user: arn:aws:eks:eu-central-1:xxxxxxxxxxxx:cluster/mwaa-2-eks
  name: aws
current-context: aws
kind: Config
preferences: {}
users:
- name: arn:aws:eks:eu-central-1:xxxxxxxxxxxx:cluster/mwaa-2-eks
  user:
    exec:
      apiVersion: client.authentication.k8s.io/v1alpha1
      args:
      - --region
      - eu-central-1
      - eks
      - get-token
      - --cluster-name
      - mwaa-2-eks
      command: /usr/local/airflow/.local/bin/aws
```

### Creating and running your DAG

We are nearly there now. We can now create a sample DAG, using the same example from the documentation. We do however, need to change this to reflect differences between Airflow 1.x and 2.x. We change the original

```
from airflow.contrib.operators.kubernetes_pod_operator import KubernetesPodOperator
```
to

```
from airflow.providers.cncf.kubernetes.operators.kubernetes_pod import KubernetesPodOperator
```

The complete DAG looks like the following:

```
from airflow import DAG
from datetime import datetime
#from airflow.contrib.operators.kubernetes_pod_operator import KubernetesPodOperator
from airflow.providers.cncf.kubernetes.operators.kubernetes_pod import KubernetesPodOperator

default_args = {
   'owner': 'aws',
   'depends_on_past': False,
   'start_date': datetime(2019, 2, 20),
   'provide_context': True
}

dag = DAG(
   'kubernetes_pod_example', default_args=default_args, schedule_interval=None)

#use a kube_config stored in s3 dags folder for now
kube_config_path = '/usr/local/airflow/dags/kube_config.yaml'

podRun = KubernetesPodOperator(
                       namespace="mwaa",
                       image="ubuntu:18.04",
                       cmds=["bash"],
                       arguments=["-c", "ls"],
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

We now upload both the DAG and the kube_config.yaml file to the DAG folder of MWAA. This is what our directory tree now looks like:

```
airflow-ricsue-cdk-demo
├── dags
│   └── example-eks.py
│   └── kube_config.yaml
└── requirements
    └── requirements.txt
```

And after around 1-2 minutes, we can see the new DAG appear within the Apache Airflow 2.x UI.

![finished](https://ricsuepublicresources.s3-eu-west-1.amazonaws.com/images/blog-eks-mwaa-2.png)

When we run this DAG, we can see the output of the log

```
[2021-06-10 15:13:52,508] {{standard_task_runner.py:77}} INFO - Job 18: Subtask pod-task
[2021-06-10 15:13:52,670] {{logging_mixin.py:104}} INFO - [2021-06-10 15:13:52,670] {{base_aws.py:368}} INFO - Airflow Connection: aws_conn_id=aws_default
[2021-06-10 15:13:52,727] {{logging_mixin.py:104}} INFO - [2021-06-10 15:13:52,727] {{base_aws.py:179}} INFO - No credentials retrieved from Connection
[2021-06-10 15:13:52,785] {{logging_mixin.py:104}} INFO - [2021-06-10 15:13:52,784] {{base_aws.py:87}} INFO - Creating session with aws_access_key_id=None region_name=eu-central-1
[2021-06-10 15:13:52,854] {{logging_mixin.py:104}} INFO - [2021-06-10 15:13:52,854] {{base_aws.py:157}} INFO - role_arn is None
[2021-06-10 15:13:52,963] {{logging_mixin.py:104}} INFO - Running <TaskInstance: kubernetes_pod_example.pod-task 2021-06-10T15:13:50.295205+00:00 [running]> on host ip-10-192-2-117.eu-central-1.compute.internal
[2021-06-10 15:13:53,133] {{taskinstance.py:1283}} INFO - Exporting the following env vars:
AIRFLOW_CTX_DAG_OWNER=aws
AIRFLOW_CTX_DAG_ID=kubernetes_pod_example
AIRFLOW_CTX_TASK_ID=pod-task
AIRFLOW_CTX_EXECUTION_DATE=2021-06-10T15:13:50.295205+00:00
AIRFLOW_CTX_DAG_RUN_ID=manual__2021-06-10T15:13:50.295205+00:00
[2021-06-10 15:13:54,075] {{kubernetes_pod.py:367}} INFO - creating pod with labels {'dag_id': 'kubernetes_pod_example', 'task_id': 'pod-task', 'execution_date': '2021-06-10T151350.2952050000-061341893', 'try_number': '1'} and launcher <airflow.providers.cncf.kubernetes.utils.pod_launcher.PodLauncher object at 0x7f17f1bc7d10>
[2021-06-10 15:13:54,390] {{logging_mixin.py:104}} INFO - [2021-06-10 15:13:54,390] {{pod_launcher.py:189}} INFO - Event: mwaa-pod-test.946a6687934d4ed6a67bf11070b5b24f had an event of type Pending
[2021-06-10 15:13:54,487] {{logging_mixin.py:104}} INFO - [2021-06-10 15:13:54,486] {{pod_launcher.py:126}} WARNING - Pod not yet started: mwaa-pod-test.946a6687934d4ed6a67bf11070b5b24f
[2021-06-10 15:13:55,566] {{logging_mixin.py:104}} INFO - [2021-06-10 15:13:55,566] {{pod_launcher.py:189}} INFO - Event: mwaa-pod-test.946a6687934d4ed6a67bf11070b5b24f had an event of type Pending
[2021-06-10 15:13:59,516] {{logging_mixin.py:104}} INFO - [2021-06-10 15:13:59,515] {{pod_launcher.py:126}} WARNING - Pod not yet started: mwaa-pod-test.946a6687934d4ed6a67bf11070b5b24f
[2021-06-10 15:14:00,613] {{logging_mixin.py:104}} INFO - [2021-06-10 15:14:00,613] {{pod_launcher.py:189}} INFO - Event: mwaa-pod-test.946a6687934d4ed6a67bf11070b5b24f had an event of type Succeeded
[2021-06-10 15:14:00,694] {{logging_mixin.py:104}} INFO - [2021-06-10 15:14:00,694] {{pod_launcher.py:302}} INFO - Event with job id mwaa-pod-test.946a6687934d4ed6a67bf11070b5b24f Succeeded
[2021-06-10 15:14:00,775] {{logging_mixin.py:104}} INFO - [2021-06-10 15:14:00,775] {{pod_launcher.py:148}} INFO - bin
[2021-06-10 15:14:00,825] {{logging_mixin.py:104}} INFO - [2021-06-10 15:14:00,825] {{pod_launcher.py:148}} INFO - boot
[2021-06-10 15:14:00,879] {{logging_mixin.py:104}} INFO - [2021-06-10 15:14:00,879] {{pod_launcher.py:148}} INFO - dev
[2021-06-10 15:14:00,937] {{logging_mixin.py:104}} INFO - [2021-06-10 15:14:00,936] {{pod_launcher.py:148}} INFO - etc
[2021-06-10 15:14:00,999] {{logging_mixin.py:104}} INFO - [2021-06-10 15:14:00,999] {{pod_launcher.py:148}} INFO - home
[2021-06-10 15:14:01,088] {{logging_mixin.py:104}} INFO - [2021-06-10 15:14:01,088] {{pod_launcher.py:148}} INFO - lib
[2021-06-10 15:14:01,167] {{logging_mixin.py:104}} INFO - [2021-06-10 15:14:01,167] {{pod_launcher.py:148}} INFO - lib64
[2021-06-10 15:14:01,224] {{logging_mixin.py:104}} INFO - [2021-06-10 15:14:01,224] {{pod_launcher.py:148}} INFO - media
[2021-06-10 15:14:01,317] {{logging_mixin.py:104}} INFO - [2021-06-10 15:14:01,317] {{pod_launcher.py:148}} INFO - mnt
[2021-06-10 15:14:01,376] {{logging_mixin.py:104}} INFO - [2021-06-10 15:14:01,376] {{pod_launcher.py:148}} INFO - opt
[2021-06-10 15:14:01,453] {{logging_mixin.py:104}} INFO - [2021-06-10 15:14:01,453] {{pod_launcher.py:148}} INFO - proc
[2021-06-10 15:14:01,803] {{logging_mixin.py:104}} INFO - [2021-06-10 15:14:01,803] {{pod_launcher.py:148}} INFO - root
[2021-06-10 15:14:01,866] {{logging_mixin.py:104}} INFO - [2021-06-10 15:14:01,866] {{pod_launcher.py:148}} INFO - run
[2021-06-10 15:14:03,722] {{logging_mixin.py:104}} INFO - [2021-06-10 15:14:03,722] {{pod_launcher.py:148}} INFO - sbin
[2021-06-10 15:14:04,031] {{logging_mixin.py:104}} INFO - [2021-06-10 15:14:04,031] {{pod_launcher.py:148}} INFO - srv
[2021-06-10 15:14:04,085] {{logging_mixin.py:104}} INFO - [2021-06-10 15:14:04,085] {{pod_launcher.py:148}} INFO - sys
[2021-06-10 15:14:04,732] {{logging_mixin.py:104}} INFO - [2021-06-10 15:14:04,732] {{pod_launcher.py:148}} INFO - tmp
[2021-06-10 15:14:04,957] {{logging_mixin.py:104}} INFO - [2021-06-10 15:14:04,957] {{pod_launcher.py:148}} INFO - usr
[2021-06-10 15:14:05,021] {{logging_mixin.py:104}} INFO - [2021-06-10 15:14:05,021] {{pod_launcher.py:148}} INFO - var
[2021-06-10 15:14:06,113] {{logging_mixin.py:104}} INFO - [2021-06-10 15:14:06,113] {{pod_launcher.py:189}} INFO - Event: mwaa-pod-test.946a6687934d4ed6a67bf11070b5b24f had an event of type Succeeded
[2021-06-10 15:14:08,356] {{logging_mixin.py:104}} INFO - [2021-06-10 15:14:08,356] {{pod_launcher.py:302}} INFO - Event with job id mwaa-pod-test.946a6687934d4ed6a67bf11070b5b24f Succeeded
[2021-06-10 15:14:08,441] {{logging_mixin.py:104}} INFO - [2021-06-10 15:14:08,441] {{pod_launcher.py:189}} INFO - Event: mwaa-pod-test.946a6687934d4ed6a67bf11070b5b24f had an event of type Succeeded
[2021-06-10 15:14:08,500] {{logging_mixin.py:104}} INFO - [2021-06-10 15:14:08,500] {{pod_launcher.py:302}} INFO - Event with job id mwaa-pod-test.946a6687934d4ed6a67bf11070b5b24f Succeeded
[2021-06-10 15:14:08,565] {{taskinstance.py:1192}} INFO - Marking task as SUCCESS. dag_id=kubernetes_pod_example, task_id=pod-task, execution_date=20210610T151350, start_date=20210610T151351, end_date=20210610T151408
[2021-06-10 15:14:08,656] {{taskinstance.py:1246}} INFO - 0 downstream tasks scheduled from follow-on schedule check
[2021-06-10 15:14:08,834] {{logging_mixin.py:104}} INFO - [2021-06-10 15:14:08,833] {{local_task_job.py:146}} INFO - Task exited with return code 0
```

### Conclusion

In this post we took a look at how to run one of the code examples in the MWAA documentation, showing you how you can run DAGs using the KubernetesPodOperator when you have configured Apache Airflow version 2.x.
