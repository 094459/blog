---
title: 'Self managed Apache Airflow with Data on EKS'
date: '2023-03-22'
tags : [ aws open source, apache airflow, doeks, Terraform, Kubernetes, Amazon EKS ]

---

I have written in the past about how you can get started with Apache Airflow using the AWS managed service, Managed Workflows for Apache Airflow. But what if you want to self managed Apache Airflow? When I speak with developers, there are sometimes reasons why a managed service might not fit their needs. Some of the common things that come up include:

* whether you need the increase level of access, a greater level of control of the configuration of Apache Airflow
* have the need to have the very latest versions or features of Apache Airflow
* if you have the need to run workflows that use more resources that managed services provide (for example, need significant compute)

> **Total Cost Ownership** One thing to consider when assessing managed vs self managed is the cost of the managed service against the total costs of you having to do the same thing. It is important to assess a true like for like, and we often see just the actual compute and storage resources being compared without all the additional things that you need to make this available.
>

If the answer to these is yes, then it is likely that using a managed service may frustrate you.

**Self Managed Apache Airflow**

There are many ways you can deploy your own Apache Airflow, but I want to share with you a really cool project that is going to help simplify your life. Based on [EKS Blueprints](https://aws-quickstart.github.io/cdk-eks-blueprints/), Data on EKS (or DoEKS for short) is a comprehensive tool that allows you to build scalable data platforms on Amazon EKS. The repository provides you with a wealth of resources, including Infrastructure as Code templates, guidance on best practices for deploying solutions on Amazon EKS, and more. One of the supported solutions they provide is a self managed Apache Airflow.

![overview of all doeks projects available](https://user-images.githubusercontent.com/19464259/208900860-a7ccdaeb-158d-4767-baad-fbc76388bc09.png)

In this blog post I want to share my journey in deploying a self managed Apache Airflow using DoEKS. The project is well documented, and we are going to be referencing the document[ Self-managed Apache Airflow deployment for EKS](https://awslabs.github.io/data-on-eks/docs/job-schedulers/self-managed-airflow) throughout this post. 

> **Note!** Currently I could not get this working from my Cloud9 development desktop. I am currently looking at why and then documenting a fix. It is something to do with the kms key generation which fails from C9, but works fine when running from my local Macbook.

**Pre-reqs**

To get started with this you are going to need:

* AWS account (non Prod) with sufficient privileges
* You will need to make sure you have enough capacity to deploy a new VPC - by default, you can deploy 5 VPCs in a region. If you are already at your limit, you will need to increase that limit or clean up one of your existing VPCs
* Terraform installed  (I was using Terraform v1.4.2 on darwin_amd64)
* The following tools: git 

> Note! The code has been developed on a Linux machine, and tested/working on a Mac. It should work on a Windows machine with the Windows Subsystem for Linux (WSL) installed although I have not tested this. If you do encounter issues, I recommend that you spin up an Amazon Cloud9 IDE environment and run through the code there.

**Installation**

So what exactly does the DoEKS install? The Self Managed Airflow pattern deploys the following starter pattern:

* An Amazon EKS cluster
* An EFS shared volume that will be mounted by the EKS cluster for persistent storage of logs and DAGs
* An S3 bucket for Apache Airflow logging
* AWS Secrets Manager for storing passwords for the PostgreSQL database used by Apache Airflow for the metastore database
* An Amazon RDS PostgreSQL instance
* KMS keys to ensure everything is encrypted
* AWS CloudWatch logging groups for Apache Airflow and Amazon RDS
* Deployment of the official Apache Airflow helm chart
* Deployment of the git-sync sidecar to synchronise DAGs from a test GitHub repository

As the source code is open, you can explore how each of these components is configured and suit to your own needs. The documentation provides the steps to install, so I will be borrowing heavily from the docs over the next few steps. 

We start off by grabbing the code from GitHub. This will actually clone all the other deployment patterns, but we are only interested in the self-managed-airflow.

```
git clone https://github.com/awslabs/data-on-eks.git
cd data-on-eks/schedulers/terraform/self-managed-airflow
```

Before proceeding it is worth checking and updating the **variables.tf** file to suit your particular setup. This was how I set mine up, changing the default region but other than that, keeping the same defaults in the original file.

```
variable "name" {
  description = "Name of the VPC and EKS Cluster"
  type        = string
  default     = "self-managed-airflow"
}

variable "region" {
  description = "region"
  type        = string
  default     = "eu-north-1"
}

variable "eks_cluster_version" {
  description = "EKS Cluster version"
  type        = string
  default     = "1.23"
}

variable "vpc_cidr" {
  description = "VPC CIDR"
  type        = string
  default     = "10.0.0.0/16"
}

```

We can now initialise Terraform, which will begin downloading any required Terraform modules needed as defined within the configuration files.

```
export AWS_REGION=eu-north-1
terraform init
```

Which will generate the following output

```
Initializing modules...
Downloading git::https://github.com/aws-ia/terraform-aws-eks-blueprints.git?ref=v4.15.0 for airflow_irsa...
- airflow_irsa in .terraform/modules/airflow_irsa/modules/irsa
Downloading registry.terraform.io/terraform-aws-modules/s3-bucket/aws 3.8.2 for airflow_s3_bucket...
- airflow_s3_bucket in .terraform/modules/airflow_s3_bucket
Downloading registry.terraform.io/terraform-aws-modules/rds/aws 5.6.0 for db...
- db in .terraform/modules/db

..
..

Terraform has been successfully initialized!

You may now begin working with Terraform. Try running "terraform plan" to see
any changes that are required for your infrastructure. All Terraform commands
should now work.

If you ever set or change modules or backend configuration for Terraform,
rerun this command to reinitialize your working directory. If you forget, other
commands will detect it and remind you to do so if necessary.
```

This will take about 2-3 minutes. Once finished (hopefully without errors) you can run the Terraform plan.

```
terraform plan
```
This will generate a lot of ouput, and is worth checking out before proceeding as it will save you from cleaning up for any obvious typos you might have made.

```
..
..
  # module.eks_blueprints_kubernetes_addons.module.cluster_autoscaler[0].module.helm_addon.module.irsa[0].kubernetes_service_account_v1.irsa[0] will be created
  + resource "kubernetes_service_account_v1" "irsa" {
      + automount_service_account_token = true
      + default_secret_name             = (known after apply)
      + id                              = (known after apply)

      + metadata {
          + annotations      = (known after apply)
          + generation       = (known after apply)
          + name             = "cluster-autoscaler-sa"
          + namespace        = "kube-system"
          + resource_version = (known after apply)
          + uid              = (known after apply)
        }
    }

Plan: 154 to add, 0 to change, 0 to destroy.

Changes to Outputs:
  + configure_kubectl = (known after apply)

──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────

Note: You didn't use the -out option to save this plan, so Terraform can't guarantee to take exactly these actions if you run "terraform apply" now.
```

Once satisfied, you are now ready to deploy using terraform apply

```
terraform apply
```

After about 1-2 minutes, and a lot of screen output, you will be prompted to proceed. After reviewing the configuration information, enter "yes" if you want to go ahead.

```
Do you want to perform these actions?
  Terraform will perform the actions described above.
  Only 'yes' will be accepted to approve.

  Enter a value: yes
```

Now time to grab a cup of tea and come back in around 20-30 minutes. 

When if finishes, you should be greeted by a message similar to this one.

```
module.eks_blueprints_kubernetes_addons.module.aws_coredns[0].aws_eks_addon.coredns[0]: Still creating... [15m0s elapsed]
module.eks_blueprints_kubernetes_addons.module.aws_ebs_csi_driver[0].aws_eks_addon.aws_ebs_csi_driver[0]: Still creating... [15m0s elapsed]
module.eks_blueprints_kubernetes_addons.module.aws_coredns[0].aws_eks_addon.coredns[0]: Creation complete after 15m4s [id=self-managed-airflow:coredns]
module.eks_blueprints_kubernetes_addons.module.aws_ebs_csi_driver[0].aws_eks_addon.aws_ebs_csi_driver[0]: Still creating... [15m10s elapsed]
module.eks_blueprints_kubernetes_addons.module.aws_ebs_csi_driver[0].aws_eks_addon.aws_ebs_csi_driver[0]: Creation complete after 15m14s [id=self-managed-airflow:aws-ebs-csi-driver]

Apply complete! Resources: 154 added, 0 changed, 0 destroyed.

Outputs:

configure_kubectl = "aws eks --region eu-north-1 update-kubeconfig --name self-managed-airflow"
```

To test this has worked ok, run the following command to grab the Kubernetes ingress url

```
kubectl get ingress -n airflow
```
which should output something like

```
http://k8s-dataengineering-2f8f57eb47-601603010.eu-north-1.elb.amazonaws.com/home
```
You can then pop this into a browser and then login using the Airflow default user (admin/admin). You should then see the Apache Airflow 2.4.3 UI, and also have a couple of workflows (DAGs) that have been populated from the git repository configured in our code (https://github.com/Hyper-Mesh/airflow-dags)

Congratulations, you have completed your setup. How easy was that!

**Improving the setup**

This setup is pretty good, but there is still some stuff that you should look at.

* enabling TLS - the example code does not setup a certificate or dns for the load balancer, but this can be easily configured using the existing code
* configuring a private git repository - the current demo uses a sample, read only GitHub repo to pull in the sample DAGs. You can configure the values.yaml to point to your private repo
* configuring a specific Airflow docker image - typically you will have your own requirements and will not use the vanilla Airflow image, so configuring a pipeline to build your own Airflow container image and then use this by updating values.yaml

I will come back to this blog post in the future and update with additional sections to show you how you can implement these. I am interested in what you think is missing or perhaps you would like to see. Let me know in the comments and I will add it to the list.

**Cleaning up**

Once you have deployed this tutorial, you should delete all the resources to ensure you do not incur any further costs. To do that, we can use these commands:

```
terraform destroy -target="module.db" -auto-approve
terraform destroy -target="module.eks_blueprints_kubernetes_addons" -auto-approve
terraform destroy -target="module.eks_blueprints" -auto-approve
terraform destroy -auto-approve
```
**Conclusion**

In this short blog post I introduced you to another way you can deploy Apache Airflow, using Data on EKS (DoEKS) patterns. DoEKS makes it a breeze to install popular open source data tools, and I encourage you to explore some of the other open source projects you can deploy.

Let me know if you found this quick tutorial useful, and what you would like to see me add to this.



### Troubleshooting

When I was putting this post together, I encountered a number of errors. When these came up, trying to carry on installation after resolving the issues ended up causing me more problems, and what I found worked was to completely do a clean up (delete all resources) before trying again. 

I like cataloging the errors and issues that I came across incase anyone else bumps into these too. So the following section provides a postscript of the issues I ran into and some of the things that helped me solve them.

**Running within Cloud9**

I got the following error:

```
module.vpc.aws_route.private_nat_gateway[0]: Creation complete after 1s [id=r-rtb-0976ae5b23f3943d41080289494]
╷
│ Error: creating IAM Role (self-managed-airflow-cluster-role): InvalidClientTokenId: The security token included in the request is invalid
│       status code: 403, request id: 776f7a95-9def-42af-9e21-b1fc4133a45f
│ 
│   with module.eks_blueprints.module.aws_eks.aws_iam_role.this[0],
│   on .terraform/modules/eks_blueprints.aws_eks/main.tf line 250, in resource "aws_iam_role" "this":
│  250: resource "aws_iam_role" "this" {
│ 
╵
╷
│ Error: creating IAM Role (airflow-metastore-20230320121551043100000002): InvalidClientTokenId: The security token included in the request is invalid
│       status code: 403, request id: 926bc806-96a7-4715-a8f1-6c4781b5cd71
│ 
│   with module.db.module.db_instance.aws_iam_role.enhanced_monitoring[0],
│   on .terraform/modules/db/modules/db_instance/main.tf line 177, in resource "aws_iam_role" "enhanced_monitoring":
│  177: resource "aws_iam_role" "enhanced_monitoring" {
│ 
╵
╷
│ Error: creating KMS Key: MalformedPolicyDocumentException: Policy contains a statement with one or more invalid principals.
│ 
│   with module.eks_blueprints.module.kms[0].aws_kms_key.this,
│   on .terraform/modules/eks_blueprints/modules/aws-kms/main.tf line 2, in resource "aws_kms_key" "this":
│    2: resource "aws_kms_key" "this" {
│ 
╵
```

**Not finding resources**

In one deployment, it looked like it was creating resources in us-west-2 for some reason. Even though I had set the environment variable (AWS_REGION=) it looked as if you also have to update the variables.tf file

```
variable "region" {
  description = "region"
  type        = string
  default     = "eu-north-1"
}
```

**Non unique S3 bucket**

I also ran into this error:

```
│ Error: creating Amazon S3 (Simple Storage) Bucket (airflow-logs-704533066374): ExpiredToken: The provided token has expired.
│       status code: 400, request id: DVKHWQN4PF4GJQZ2, host id: HxyY0MENSjXG6NGDpoEh+EuiShPxT7kYXK1XOTuzrmlzw+8dL+Xm9vQH9dS7xRb+9fdXYQumIoQ=
│ 
│   with module.airflow_s3_bucket.aws_s3_bucket.this[0],
│   on .terraform/modules/airflow_s3_bucket/main.tf line 20, in resource "aws_s3_bucket" "this":
│   20: resource "aws_s3_bucket" "this" {
│ 
╵
```

which was the result of a duplicate S3 bucket being created. Once I removed and waited, I was able to redo this.

> **Hack** I modified the main.tf logic and changed the name for the S3 bucket name to save myself some time.
> 

**Resources not available in the AWS region I was deploying into**

I also got this error when I was deploying in eu-north-1

```
module.eks_blueprints_kubernetes_addons.module.aws_ebs_csi_driver[0].aws_eks_addon.aws_ebs_csi_driver[0]: Creation complete after 36m29s [id=self-managed-airflow:aws-ebs-csi-driver]
╷
│ Error: creating RDS DB Instance (airflow): InvalidParameterValue: Invalid DB Instance class: db.m6i.xlarge
│       status code: 400, request id: d163835c-604b-4f8a-b2a8-16e54998d1ff
│ 
│   with module.db.module.db_instance.aws_db_instance.this[0],
│   on .terraform/modules/db/modules/db_instance/main.tf line 32, in resource "aws_db_instance" "this":
│   32: resource "aws_db_instance" "this" {
```
And taking a look within the RDS console confirmed this instance type was unavailable, so I switched it to a similar (db.m5d.xlarge, 4vpu with 16gb ram) by updating the main.tf file

```
  #instance_class       = "db.m6i.xlarge"
  instance_class       = "db.m5.xlarge"
```

**Not cleaning up resources before installing**

I also encountered the following error whilst I was getting this code working.

```
│ Error: cannot re-use a name that is still in use
│ 
│   with module.eks_blueprints_kubernetes_addons.module.prometheus[0].module.helm_addon.helm_release.addon[0],
│   on .terraform/modules/eks_blueprints_kubernetes_addons/modules/kubernetes-addons/helm-addon/main.tf line 1, in resource "helm_release" "addon":
│    1: resource "helm_release" "addon" {
```
I got this error when I tried to carry on deploying an interrupted installation. I found that deleting (cleaning up) all the resources and then doing everything from the beginning resolve the issue.

If you do have to re-start the installation, the destroy does not clean up all the resources. Make sure you look and manually delete the following:

* CloudWatch log groups - /aws/eks/self-managed-airflow/cluster (anything with "self-managed-airflow" that you did not have there before) 
