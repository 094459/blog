---
title: 'Automating the installation and configuration of Amazon Managed Workflows for Apache Airflow'
date: '2021-01-26'
tags: [Apache Airflow, mwaa, IaC, AWS CDK, AWS CloudFormation]
---
**updated, August 25th**
*Thanks to Philip T for spotting a typo in the cloudformation code below - it is ok in the GitHub repo, but I have fixed it now below.*

![innovate](https://raw.githubusercontent.com/094459/innovateaiml-airflow/main/images/banner.png)
Part of a series of posts to support an up-coming online event, the Innovate AI/ML on February 24th, from 9:00am GMT - you can sign up [here](https://aws.amazon.com/events/aws-innovate/machine-learning/online/emea/?sc_channel=em&sc_campaign=EMEA_FIELD_WEBINAR_innovate-AIML_20210224_7014z000001MJbu&sc_medium=em_&sc_content=REG_t1_field&sc_geo=emea&sc_country=mult&sc_outcome=reg&sc_publisher=aws&trkCampaign=emea21_innovatemlq1&trk=em_emea21_innovatemlq1_ricardosueiras)

* **Part 1** - Installation and configuration of Managed Workflows for Apache Airflow <- this post
* **Part 2** - [Working with Permissions](https://aws-oss.beachgeek.co.uk/3n)
* **Part 3** - [Accessing Amazon Managed Workflows for Apache Airflow environments](https://aws-oss.beachgeek.co.uk/3o) 
* **Part 4** - [Interacting with Amazon Managed Workflows for Apache Airflow via the command line](https://aws-oss.beachgeek.co.uk/4s)
* **Part 5** - [A simple CI/CD system for your development workflow](https://aws-oss.beachgeek.co.uk/4t)
* **Part 6** - [Monitoring and logging](https://aws-oss.beachgeek.co.uk/5r)
* **Part 7** - Automating a simple AI/ML pipeline with Apache Airflow 

In this post I will be covering Part 1, automating the installation and configuration of  Managed Workflows for Apache Airflow (MWAA).

**What will you need**

* An AWS account with the right level of privileges
* An environment with the AWS CLI tools configured and running
* Access to an AWS region where Managed Workflows for Apache Airflow is supported
* Make sure you check the number of existing VPCs in your region. Typically the soft limit is 5 VPCs, which you can increase via support. Go to your VPC section in the console and find out how many you have before proceeding.

**Automation approaches**

Whilst the provisioning of MWAA environments via the console is fine when you first start off, as you grow and scale your use of Apache Airflow you need to look at options to help you automate the deployment and configuration of these environments.

* AWS CDK - the AWS Cloud Development Kit (CDK) allows you to write code using a familiar language and tooling to provision infrastructure. It uses the concept of Constructs which provide programatic access to configure and deploy those resources by synthesising the output to an AWS CloudFormation template.
* AWS CloudFormation - using either json or YAML templates, you can automate the provisioning of collections of AWS resources
* HashiCorp Terraform - an indépendant solution to help you configure your AWS environments.

For the purpose of this post I am going to be using AWS CloudFormation. Currently there is no AWS CDK Construct for MWAA, so I will update this post when that becomes available. If you still wanted to use CDK then it is possible to use/manipulate Cloudformation templates within CDK but that is beyond the scope of this post. The same is true of Terraform, although [this PR](https://github.com/hashicorp/terraform-provider-aws/issues/16432) looks promising and may have progressed further by the time this post is published.

**CloudFormation templates** 

To provision MWAA you need to ensure that your networking infrastructure satisfies the base requirements or the installation will fail. 

For that reason, we have a sample networking template you can use. If your existing setup has these components you should be good to go and re-use your existing. One thing I am asked often is whether it is ok to combine the networking and the MWAA templates together. This is absolutely fine to do, but I tend to split them out so they can be managed separately.

When setting up your environment you have a number of choices you need to make. The first one is whether you are going to open up the environment to the public internet (this will expose the GUI, but it will not let anyone access Apache Airflow until you have configured access to it) or whether you want to keep Apache Airflow to within the private subnet. It is possible to change this later on if you want, but like all changes within MWAA, it will require the environment to update and restart.

For this example I will setup a public environment with networking. I will use an AWS region that has MWAA available (not all AWS regions currently have this available)

**[1]** Create a new VPC using this template - feel free to change the CIDR as needed. This is the same template as the MWAA documentation [here](https://docs.aws.amazon.com/mwaa/latest/userguide/vpc-create.html#vpc-create-template-code).

Copy this into a new file (for example, mwaa-vpc.yaml).

```
Description:  This template deploys a VPC, with a pair of public and private subnets spread
  across two Availability Zones. It deploys an internet gateway, with a default
  route on the public subnets. It deploys a pair of NAT gateways (one in each AZ),
  and default routes for them in the private subnets.

Parameters:
  EnvironmentName:
    Description: An environment name that is prefixed to resource names
    Type: String
    Default: mwaa-

  VpcCIDR:
    Description: Please enter the IP range (CIDR notation) for this VPC
    Type: String
    Default: 10.192.0.0/16

  PublicSubnet1CIDR:
    Description: Please enter the IP range (CIDR notation) for the public subnet in the first Availability Zone
    Type: String
    Default: 10.192.10.0/24

  PublicSubnet2CIDR:
    Description: Please enter the IP range (CIDR notation) for the public subnet in the second Availability Zone
    Type: String
    Default: 10.192.11.0/24

  PrivateSubnet1CIDR:
    Description: Please enter the IP range (CIDR notation) for the private subnet in the first Availability Zone
    Type: String
    Default: 10.192.20.0/24

  PrivateSubnet2CIDR:
    Description: Please enter the IP range (CIDR notation) for the private subnet in the second Availability Zone
    Type: String
    Default: 10.192.21.0/24

Resources:
  VPC:
    Type: AWS::EC2::VPC
    Properties:
      CidrBlock: !Ref VpcCIDR
      EnableDnsSupport: true
      EnableDnsHostnames: true
      Tags:
        - Key: Name
          Value: !Ref EnvironmentName

  InternetGateway:
    Type: AWS::EC2::InternetGateway
    Properties:
      Tags:
        - Key: Name
          Value: !Ref EnvironmentName

  InternetGatewayAttachment:
    Type: AWS::EC2::VPCGatewayAttachment
    Properties:
      InternetGatewayId: !Ref InternetGateway
      VpcId: !Ref VPC

  PublicSubnet1:
    Type: AWS::EC2::Subnet
    Properties:
      VpcId: !Ref VPC
      AvailabilityZone: !Select [ 0, !GetAZs '' ]
      CidrBlock: !Ref PublicSubnet1CIDR
      MapPublicIpOnLaunch: true
      Tags:
        - Key: Name
          Value: !Sub ${EnvironmentName} Public Subnet (AZ1)

  PublicSubnet2:
    Type: AWS::EC2::Subnet
    Properties:
      VpcId: !Ref VPC
      AvailabilityZone: !Select [ 1, !GetAZs  '' ]
      CidrBlock: !Ref PublicSubnet2CIDR
      MapPublicIpOnLaunch: true
      Tags:
        - Key: Name
          Value: !Sub ${EnvironmentName} Public Subnet (AZ2)

  PrivateSubnet1:
    Type: AWS::EC2::Subnet
    Properties:
      VpcId: !Ref VPC
      AvailabilityZone: !Select [ 0, !GetAZs  '' ]
      CidrBlock: !Ref PrivateSubnet1CIDR
      MapPublicIpOnLaunch: false
      Tags:
        - Key: Name
          Value: !Sub ${EnvironmentName} Private Subnet (AZ1)

  PrivateSubnet2:
    Type: AWS::EC2::Subnet
    Properties:
      VpcId: !Ref VPC
      AvailabilityZone: !Select [ 1, !GetAZs  '' ]
      CidrBlock: !Ref PrivateSubnet2CIDR
      MapPublicIpOnLaunch: false
      Tags:
        - Key: Name
          Value: !Sub ${EnvironmentName} Private Subnet (AZ2)

  NatGateway1EIP:
    Type: AWS::EC2::EIP
    DependsOn: InternetGatewayAttachment
    Properties:
      Domain: vpc

  NatGateway2EIP:
    Type: AWS::EC2::EIP
    DependsOn: InternetGatewayAttachment
    Properties:
      Domain: vpc

  NatGateway1:
    Type: AWS::EC2::NatGateway
    Properties:
      AllocationId: !GetAtt NatGateway1EIP.AllocationId
      SubnetId: !Ref PublicSubnet1

  NatGateway2:
    Type: AWS::EC2::NatGateway
    Properties:
      AllocationId: !GetAtt NatGateway2EIP.AllocationId
      SubnetId: !Ref PublicSubnet2

  PublicRouteTable:
    Type: AWS::EC2::RouteTable
    Properties:
      VpcId: !Ref VPC
      Tags:
        - Key: Name
          Value: !Sub ${EnvironmentName} Public Routes

  DefaultPublicRoute:
    Type: AWS::EC2::Route
    DependsOn: InternetGatewayAttachment
    Properties:
      RouteTableId: !Ref PublicRouteTable
      DestinationCidrBlock: 0.0.0.0/0
      GatewayId: !Ref InternetGateway

  PublicSubnet1RouteTableAssociation:
    Type: AWS::EC2::SubnetRouteTableAssociation
    Properties:
      RouteTableId: !Ref PublicRouteTable
      SubnetId: !Ref PublicSubnet1

  PublicSubnet2RouteTableAssociation:
    Type: AWS::EC2::SubnetRouteTableAssociation
    Properties:
      RouteTableId: !Ref PublicRouteTable
      SubnetId: !Ref PublicSubnet2


  PrivateRouteTable1:
    Type: AWS::EC2::RouteTable
    Properties:
      VpcId: !Ref VPC
      Tags:
        - Key: Name
          Value: !Sub ${EnvironmentName} Private Routes (AZ1)

  DefaultPrivateRoute1:
    Type: AWS::EC2::Route
    Properties:
      RouteTableId: !Ref PrivateRouteTable1
      DestinationCidrBlock: 0.0.0.0/0
      NatGatewayId: !Ref NatGateway1

  PrivateSubnet1RouteTableAssociation:
    Type: AWS::EC2::SubnetRouteTableAssociation
    Properties:
      RouteTableId: !Ref PrivateRouteTable1
      SubnetId: !Ref PrivateSubnet1

  PrivateRouteTable2:
    Type: AWS::EC2::RouteTable
    Properties:
      VpcId: !Ref VPC
      Tags:
        - Key: Name
          Value: !Sub ${EnvironmentName} Private Routes (AZ2)

  DefaultPrivateRoute2:
    Type: AWS::EC2::Route
    Properties:
      RouteTableId: !Ref PrivateRouteTable2
      DestinationCidrBlock: 0.0.0.0/0
      NatGatewayId: !Ref NatGateway2

  PrivateSubnet2RouteTableAssociation:
    Type: AWS::EC2::SubnetRouteTableAssociation
    Properties:
      RouteTableId: !Ref PrivateRouteTable2
      SubnetId: !Ref PrivateSubnet2

  NoIngressSecurityGroup:
    Type: AWS::EC2::SecurityGroup
    Properties:
      GroupName: "no-ingress-sg"
      GroupDescription: "Security group with no ingress rule"
      VpcId: !Ref VPC

Outputs:
  VPC:
    Description: A reference to the created VPC
    Value: !Ref VPC

  PublicSubnets:
    Description: A list of the public subnets
    Value: !Join [ ",", [ !Ref PublicSubnet1, !Ref PublicSubnet2 ]]

  PrivateSubnets:
    Description: A list of the private subnets
    Value: !Join [ ",", [ !Ref PrivateSubnet1, !Ref PrivateSubnet2 ]]

  PublicSubnet1:
    Description: A reference to the public subnet in the 1st Availability Zone
    Value: !Ref PublicSubnet1

  PublicSubnet2:
    Description: A reference to the public subnet in the 2nd Availability Zone
    Value: !Ref PublicSubnet2

  PrivateSubnet1:
    Description: A reference to the private subnet in the 1st Availability Zone
    Value: !Ref PrivateSubnet1

  PrivateSubnet2:
    Description: A reference to the private subnet in the 2nd Availability Zone
    Value: !Ref PrivateSubnet2

  NoIngressSecurityGroup:
    Description: Security group with no ingress rule
    Value: !Ref NoIngressSecurityGroup
```
and deploy via this command. If you used the same name as above (mwaa-vpc.yaml) then this would be the command you might use. You need to replace {your-unique-stack-name} with the name you will use to identify this within the AWS CloudFormation console. 

```
aws cloudformation create-stack --stack-name {your-unique-stack-name} --template-body file://mwaa-vpc.yaml 
```

If you want to deploy this into a specific region, then add "--region=" to the command (for example, --region=eu-central-1 to deploy into Frankfurt)

```
aws cloudformation create-stack --stack-name {your-unique-stack-name} --template-body file://mwaa-vpc.yaml --region={region}
```

**[2]** When you run that command, you should see something like the following. 

```
{
    "StackId": "arn:aws:cloudformation:{region}:{your AWS account number}:stack/{your-unique-stack-name}/aaaaaaaa-bbbb-cccc-dddd-eeeeeeeeeeee"
}
```

If you now go to the AWS console and to the CloudFormation dashboard, you should see this stack in the process of being created.

![console-deploying-vpc](https://github.com/094459/innovateaiml-airflow/blob/main/images/airblog-1.png?raw=true)

This should take no more than 5-10 minutes to complete. Once finished, check the OUTPUTS tab. You should have details of the Public and Private Subnet IDs, the VPC ID and more.

**[3]** Create a new file called something like mwaa-cfn-parameters.json (you can call it what you like if you have a naming convention, it is not important). Create this in the same folder as the previous Cloudformation template file. You need to amend this file and substitute the Private Subnet IDs and the VPC Id in the file below (just the ones in { } ) and then provide a unique Amazon S3 bucket name which has to be prefixed "airflow-". Make sure it is unique, as this is a global namespace so using something generic like "airflow-demo" is likely to fail.


```
[
    {
  "ParameterKey": "s3BucketName",
      "ParameterValue": "airflow-xxxx"
    }, 
    {
      "ParameterKey": "subnetIds",
      "ParameterValue": "{privatesubnet1-id},{privatesubnet2-id}"
    },
    {
        "ParameterKey": "vpcId",
        "ParameterValue": "{vpc-id}"
      }
  ]
```

**[4]** You can now use that parameter file together with the following template to install/configure a MWAA environment. Copy this into a new file (for example, mwaa-cfn-install.yaml). I have also provided a copy of this file [here](https://github.com/094459/innovateaiml-airflow/tree/main/cf).

This template will configure the following:

* A Public facing MWAA environment
* Worker nodes with mw1.small instance size, and a maximum of 5 of them
* Logging enabled, with all logs set to INFO
* An environment name defined by the stackname postfixed with "-MwaaEnvironment"

You can change these as you see fit, or better still amend the file so it can be parameterised (I will try and do this in a future post, but for the moment, this is the MVP)

```
AWSTemplateFormatVersion: "2010-09-09"

Parameters:
  s3BucketName:
    Type: String
    Description: The S3 bucket where your source code is stored.
    AllowedPattern: "airflow-[a-z-]+"
  
  vpcId:
    Type: AWS::EC2::VPC::Id
    Description: The VPC ID

  subnetIds:
    Type: List<AWS::EC2::Subnet::Id>
    Description: Provide a JSON list of 2 subnet IDs by name. These must be private subnets, in the same VPC, in two different availability zones.

Resources:

  EnvironmentBucket:
    Type: AWS::S3::Bucket
    Properties:
      BucketName: !Ref s3BucketName
      VersioningConfiguration:
        Status: Enabled

  MwaaEnvironment:
    Type: AWS::MWAA::Environment
    Properties:
      AirflowVersion: 1.10.12
      Name: !Sub "${AWS::StackName}-MwaaEnvironment"
      SourceBucketArn: !GetAtt EnvironmentBucket.Arn
      ExecutionRoleArn: !GetAtt MwaaExecutionRole.Arn
      DagS3Path: dags
      LoggingConfiguration:
        DagProcessingLogs:
          Enabled: True
          LogLevel: INFO
        SchedulerLogs:
          Enabled: True
          LogLevel: INFO
        TaskLogs:
          Enabled: True
          LogLevel: INFO
        WebserverLogs:
          Enabled: True
          LogLevel: INFO
        WorkerLogs:
          Enabled: True
          LogLevel: INFO
      EnvironmentClass: mw1.small
      MaxWorkers: 5
      NetworkConfiguration:
        SecurityGroupIds:
          - !GetAtt SecurityGroup.GroupId
        SubnetIds: !Ref subnetIds
      WebserverAccessMode: PUBLIC_ONLY
    DependsOn: MwaaExecutionPolicy
  
  SecurityGroup:
    Type: AWS::EC2::SecurityGroup
    Properties:
      VpcId: !Ref vpcId
      GroupDescription: !Sub "Security Group for Amazon MWAA Environment ${AWS::StackName}-MwaaEnvironment"
      GroupName: !Sub "airflow-security-group-${AWS::StackName}-MwaaEnvironment"
  
  SecurityGroupIngress:
    Type: AWS::EC2::SecurityGroupIngress
    Properties:
      GroupId: !Ref SecurityGroup
      IpProtocol: "-1"
      SourceSecurityGroupId: !Ref SecurityGroup

  SecurityGroupEgress:
    Type: AWS::EC2::SecurityGroupEgress
    Properties:
      GroupId: !Ref SecurityGroup
      IpProtocol: "-1"
      CidrIp: "0.0.0.0/0"

  MwaaExecutionRole:
    Type: AWS::IAM::Role
    Properties:
      AssumeRolePolicyDocument:
        Version: 2012-10-17
        Statement:
          - Effect: Allow
            Principal:
              Service:
                - airflow-env.amazonaws.com
                - airflow.amazonaws.com
            Action:
             - "sts:AssumeRole"
      Path: "/service-role/"

  MwaaExecutionPolicy:
    Type: AWS::IAM::ManagedPolicy
    Properties:
      Roles:
        - !Ref MwaaExecutionRole
      PolicyDocument:
        Version: 2012-10-17
        Statement:
          - Effect: Allow
            Action: airflow:PublishMetrics
            Resource:
              # - !GetAtt MwaaEnvironment.Arn
              - !Sub "arn:aws:airflow:${AWS::Region}:${AWS::AccountId}:environment/${AWS::StackName}-MwaaEnvironment"
          - Effect: Deny
            Action: s3:ListAllMyBuckets
            Resource:
              - !GetAtt EnvironmentBucket.Arn
              - !Sub "${EnvironmentBucket.Arn}/*"
          - Effect: Allow
            Action:
              - "s3:GetObject*"
              - "s3:GetBucket*"
              - "s3:List*"
            Resource:
              - !GetAtt EnvironmentBucket.Arn
              - !Sub "${EnvironmentBucket.Arn}/*"
          - Effect: Allow
            Action:
              - logs:CreateLogStream
              - logs:CreateLogGroup
              - logs:PutLogEvents
              - logs:GetLogEvents
              - logs:GetLogRecord
              - logs:GetLogGroupFields
              - logs:GetQueryResults
              - logs:DescribeLogGroups
            Resource:
              - !Sub "arn:aws:logs:${AWS::Region}:${AWS::AccountId}:log-group:airflow-${AWS::StackName}-MwaaEnvironment-*"
          - Effect: Allow
            Action: cloudwatch:PutMetricData
            Resource: "*"
          - Effect: Allow
            Action:
              - sqs:ChangeMessageVisibility
              - sqs:DeleteMessage
              - sqs:GetQueueAttributes
              - sqs:GetQueueUrl
              - sqs:ReceiveMessage
              - sqs:SendMessage
            Resource:
              - !Sub "arn:aws:sqs:${AWS::Region}:*:airflow-celery-*"
          - Effect: Allow
            Action:
              - kms:Decrypt
              - kms:DescribeKey
              - "kms:GenerateDataKey*"
              - kms:Encrypt
            NotResource: !Sub "arn:aws:kms:*:${AWS::AccountId}:key/*"
            Condition:
              StringLike:
                "kms:ViaService":
                  - !Sub "sqs.${AWS::Region}.amazonaws.com"

```

**[5]** With this file saved in the same folder as the parameters file you created in step **[3]** you can now kick off the installation by issuing the following command:

```
aws cloudformation create-stack --stack-name {your-unique-stack-name} --template-body file://{name of the mwaa template file} --parameters file://{name of your parameters file} --capabilities CAPABILITY_IAM --region={region}
```
Note the stack name should be different to the previous one you created when doing the VPC configuration.

You should see something like the following when you kick this off:

```
{
    "StackId": "arn:aws:cloudformation:{region}:{your AWS account number}:stack/{your-mwaa-unique-stack-name}/aaaaaaaa-bbbb-cccc-dddd-eeeeeeeeeeee"
}
```

And if you go back to the CloudFormation console, you should see these resources being created. This time it will take around 25-30 minutes to complete, so time for a nice cup of tea.

![console-deploying-vpc](https://github.com/094459/innovateaiml-airflow/blob/main/images/airblog-2.png?raw=true)

**Create failures**

If your build fails with the following error:

```
Invalid request provided: Provided role does not have sufficient permissions for s3 location airflow-xxx-xxx/dags
```

or perhaps this message 

```
(Service: Mwaa, Status Code: 400, Request ID: 634a77b4-0105-443d-a64f-d8ef3c141c26)
```

Then you are using an old version of the cf templates from my repo. There was a change made that caused this error to start in the past few weeks, so I have updated the code.

**Creating your dags folder**

Now that the environment is setup, within the Amazon S3 bucket you defined in your template (s3BucketName) you will now need to create a folder called dags as the CloudFormation service will not provision this for you.

```
aws s3 mb s3://{s3bucketname}/dags --region={your region}
```

**Customising**

**[6]** You can customise a number of things in the template. Here is just a selection of the things you can do:

```
AirflowVersion : 1.10.12 
EnvironmentClass: mw1.small | mw1.medium | mw1.large
MaxWorkers: 1 - 25
WebserverAccessMode: PUBLIC_ONLY | PRIVATE_ONLY
WeeklyMaintenanceWindowStart: "SUN:02:30"

```
Take a look at the documentation [here](https://aws-oss.beachgeek.co.uk/3j) to see what other values you can change.

If you want to update the Airflow configuration settings, then use the following format:

```
      AirflowConfigurationOptions: 
        core.default_task_retries: 3
        smtp.smtp_mail_from : "ricsue@amazon.com"
```

You can find the options you can set in the documentation. 

You can of course also combine this with your existing CloudFormation templates if you want to do things like deploy other services that will interact with Apache Airflow - perhaps you want this to orchestrate your big data pipelines, or kick off training jobs in Amazon SageMaker.

**Checking the installation**

**[7]** Once the CloudFormation stack has completed, run the following command to get details of the environment created. The name of the environment created will be the CloudFormation stack name postfixed with MwaaEnvironment if you use the template as is.

```
aws mwaa get-environment --name {name of the environment created} --region={region}
```

Which should generate output like the following:

```
{
    "Environment": {
        "AirflowVersion": "1.10.12",
        "Arn": "arn:aws:airflow:eu-central-1:xxxxxxxxxxxx:environment/blog-post-airflow-install-MwaaEnvironment",
        "CreatedAt": 1611662444.0,
        "DagS3Path": "dags",
        "EnvironmentClass": "mw1.small",
        "ExecutionRoleArn": "arn:aws:iam::xxxxxxxxxxxx:role/service-role/blog-post-airflow-install-MwaaExecutionRole-13T4Z4Z2HSIA7",
        "LoggingConfiguration": {
            "DagProcessingLogs": {
                "CloudWatchLogGroupArn": "arn:aws:logs::xxxxxxxxxxxx:log-group:airflow-blog-post-airflow-install-MwaaEnvironment-DAGProcessing",
                "Enabled": true,
                "LogLevel": "INFO"
            },
            "SchedulerLogs": {
                "CloudWatchLogGroupArn": "arn:aws:logs::xxxxxxxxxxxx:log-group:airflow-blog-post-airflow-install-MwaaEnvironment-Scheduler",
                "Enabled": true,
                "LogLevel": "INFO"
            },
            "TaskLogs": {
                "CloudWatchLogGroupArn": "arn:aws:logs::xxxxxxxxxxxx:log-group:airflow-blog-post-airflow-install-MwaaEnvironment-Task",
                "Enabled": true,
                "LogLevel": "INFO"
            },
            "WebserverLogs": {
                "CloudWatchLogGroupArn": "arn:aws:logs::xxxxxxxxxxxx:log-group:airflow-blog-post-airflow-install-MwaaEnvironment-WebServer",
                "Enabled": true,
                "LogLevel": "INFO"
            },
            "WorkerLogs": {
                "CloudWatchLogGroupArn": "arn:aws:logs::xxxxxxxxxxxx:log-group:airflow-blog-post-airflow-install-MwaaEnvironment-Worker",
                "Enabled": true,
                "LogLevel": "INFO"
            }
        },
        "MaxWorkers": 5,
        "Name": "blog-post-airflow-install-MwaaEnvironment",
        "NetworkConfiguration": {
            "SecurityGroupIds": [
                "sg-0ece6c67a578345fc"
            ],
            "SubnetIds": [
                "subnet-0948720d896569082",
                "subnet-0d232be248a4aba85"
            ]
        },
        "ServiceRoleArn": "arn:aws:iam::xxxxxxxxxxxx:role/aws-service-role/airflow.amazonaws.com/AWSServiceRoleForAmazonMWAA",
        "SourceBucketArn": "arn:aws:s3:::airflow-cloudfninstalldemo-ricsue",
        "Status": "AVAILABLE",
        "Tags": {},
        "WebserverAccessMode": "PUBLIC_ONLY",
        "WebserverUrl": "2969c079-ac03-4583-97c0-d6f9458462d2.c2.eu-central-1.airflow.amazonaws.com",
        "WeeklyMaintenanceWindowStart": "SUN:03:30"
    }
}
```
You can use the following cli command to list all the MWAA environments for a given region.

```
aws mwaa list-environments --region={region}
```

and you will get output showing the environments you have setup. This is what I see, you will get different output.

```
{
    "Environments": [
        "airflow-frank-demo-MwaaEnvironment",
        "blog-post-airflow-install-MwaaEnvironment"
    ]
}
```
**Accessing the Apache Airflow UI**

**[8]** To access the Web UI, find the "WebServerUrl" value from the output of the previous step (you will see it second line from bottom) and than append /home. So in the above example, we would access the Apache Airflow UI via the following link:

```
https://2969c079-ac03-4583-97c0-d6f9458462d2.c2.eu-central-1.airflow.amazonaws.com/home
```

We would then need to login using our AWS credentials, so clicking on the "Sign in with AWS Management Console SSO" link will take you to the AWS login page. After logging in, you should see the Apache Airflow UI.

![apache-airflow-ui](https://github.com/094459/innovateaiml-airflow/blob/main/images/airblog-3.png?raw=true)

**Removing your installation**

**[9]** To remove the environment you have created, you can delete via the CloudFormation console (using the delete stack option) or use the command line.

**Note! This will result in the removal of the installation including the S3 bucket that contains your workflow DAGs. Remember to make a backup of these before proceeding.

```
aws cloudformation delete-stack {stack-name} --region={region}
```

This will not generate any output at the command line, but if you go to the CloudFormation console you will see the stack being deleted.

You should uninstall in the reverse order you installed. So remove the MWAA stack first before removing the VPC stack.

**Apache Airflow configuration**

For those already familiar with Apache Airflow, or if you are new, one of the key configuration files that you use to ensure your environment is configured as per your requirements is the **airflow.cfg**.

MWAA does not expose this and so you cannot directly make any changes to this file. There are some configuration changes you can make, and I covered these briefly above (AirflowConfigurationOptions: section) but you can see the documentation page, [Customizing Apache Airflow configurations](https://docs.aws.amazon.com/mwaa/latest/userguide/configuring-env-variables.html), that shows in more detail what configuration options are available.

If you want to dive a little deeper, check out this great post from Gary Stafford, [Amazon Managed Workflows for Apache Airflow — Configuration](https://aws-oss.beachgeek.co.uk/3r) that provides some additional information as well as some example workflows you can use to explore your own MWAA environments.

**Conclusion**

This concludes the first post around how to automate the installation and configuration via AWS CloudFormation. You can find the templates used in this post [here](https://aws-oss.beachgeek.co.uk/3i), and watch out for the next posts which take a look configuring permissions, accessing additional AWS resources and setting up developer workflows.

In the next post we will look at permissions and how you can review and automate these too.

If there is specific content you want to see, please get in touch.

Also, remember to sign up [here](https://aws.amazon.com/events/aws-innovate/machine-learning/online/emea/?sc_channel=em&sc_campaign=EMEA_FIELD_WEBINAR_innovate-AIML_20210224_7014z000001MJbu&sc_medium=em_&sc_content=REG_t1_field&sc_geo=emea&sc_country=mult&sc_outcome=reg&sc_publisher=aws&trkCampaign=emea21_innovatemlq1&trk=em_emea21_innovatemlq1_ricardosueiras) for the Innovate AI/ML conference and check out my session on using open source tools.
