---
title: 'Accessing your Amazon Managed Workflows for Apache Airflow environments'
date: '2021-01-28'
tags: [airflow, mwaa]
---
![innovate](https://raw.githubusercontent.com/094459/innovateaiml-airflow/main/images/banner.png)

Part of a series of posts to support an up-coming online event, the Innovate AI/ML on February 24th, from 9:00am GMT - you can sign up [here](https://aws.amazon.com/events/aws-innovate/machine-learning/online/emea/?sc_channel=em&sc_campaign=EMEA_FIELD_WEBINAR_innovate-AIML_20210224_7014z000001MJbu&sc_medium=em_&sc_content=REG_t1_field&sc_geo=emea&sc_country=mult&sc_outcome=reg&sc_publisher=aws&trkCampaign=emea21_innovatemlq1&trk=em_emea21_innovatemlq1_ricardosueiras)

* **Part 1** - [Installation and configuration of Managed Workflows for Apache Airflow](https://aws-oss.beachgeek.co.uk/3h)
* **Part 2** - [Working with Permissions](https://aws-oss.beachgeek.co.uk/3n)
* **Part 3** - Accessing Amazon Managed Workflows for Apache Airflow environments < this post
* **Part 4** - [Interacting with Amazon Managed Workflows for Apache Airflow via the command line](https://aws-oss.beachgeek.co.uk/4s)
* **Part 5** - [A simple CI/CD system for your development workflow](https://aws-oss.beachgeek.co.uk/4t)
* **Part 6** - [Monitoring and logging](https://aws-oss.beachgeek.co.uk/5r)
* **Part 7** - Automating a simple AI/ML pipeline with Apache Airflow 

In this post I will be covering Part 3, how you can interact and access the Apache Airflow environments. Specifically I will cover a couple of things:

1. How Private and Public MWAA environments differ and some options on how you can access Private configurations
2. A walkthrough of one approach to accessing Private MWAA environments

**What will you need**

* An AWS account with the right level of privileges
* An environment with the AWS CLI tools configured and running
* Access to an AWS region where Managed Workflows for Apache Airflow is supported
* An environment of Amazon Managed Workflows for Apache Airflow already setup - you should ideally have followed [part one here](https://aws-oss.beachgeek.co.uk/3h).

**Public vs Private MWAA environments**

You have two options when you create your MWAA environments, a Public or Private configuration (which as you will recall from the CloudFormation template, was governed by the WebserverAccessMode: PUBLIC_ONLY|PRIVATE_ONLY parameter)

When you configure a Public environment, in effect you are exposing the Apache Airflow UI via a public URL that can be accessed over the public internet. This very simple diagram shows the flows. You still need to know the URL and you still need to authenticate to actually gain access so it is still a secure option to use.


![arch](https://github.com/094459/innovateaiml-airflow/blob/main/images/airflow-arch1.png?raw=true)


When you look at the Apache Airflow URL, it is typically in the format of **https://{unique-id}.{region}.airflow.amazonaws.com/home**. 

When you configure a Private environment (which is the recommended choice to maximise security) you will notice that this URL is different and looks like **{unique-id}-vpce.{region}.airflow.amazonaws.com**. If you are having issues access an Airflow instance and you notice the "vpce" in the URL, then this is probably why. When you see this, access is configured via a [VPC Endpoint](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-endpoints.html) and no access over the public internet is enabled.

So how do you access your Private Apache Airflow instances?

You have a number of options available to you and your organisation preferences/standards might dictate which one is suitable. Here is a list of some of the approaches you can take:

* Configuring access to the VPC via your organisations network integration - typically via something like site to site VPN
* Configuring a client VPN solution like OpenVPN
* Providing access via a bastion host and using a client side proxy solution in conjunction with ssh tunneling

I will cover the last option here, and hope to cover the others in future posts.

**Accessing Private instance via Bastion Host and client proxy**

You will need the following to complete this:

* an AWS key pair (make sure it is in the same region as you are configuring your MWAA environment)
* ssh - you will be creating an ssh tunnel on your local setup
* (optional) you can use a browser proxy plugin like FoxyProxy but this is not needed but will probably make your life easier

The first thing to do is to deploy a bastion host. For this, using the AWS Quickstart makes sense as this is a separate component to MWAA and I want to manage this configuration separately. You can find the quickstart link [here](https://docs.aws.amazon.com/quickstart/latest/linux-bastion/welcome.html).

After downloading the template either use the console to create this stack, or create a parameter file with the options you want. I have provided a sample parameter file as well as the CloudFormation template I used for this in the [GitHub repo here](https://github.com/094459/innovateaiml-airflow/tree/main/cf)

When selecting the configuration options from this template use the following information:

* VPC/ID and Public Subnets 1 and 2 - make sure you configure these to be the same as your MWAA environment.
* For the allowed CIDR range, select the narrow/specific address for your client. When I did this, I used my own external IP which was 54.240.197.xxx/32 but yours will be different. If you wanted to leave this wide open, you can use 0.0.0.0/0 but I would not recommend that.
* From the pull down select the AWS key pair you will use to connect to the bastion host
* Change the TCP Forwarding to TRUE

This is what the parameter file looks like

```
[
    {
      "ParameterKey": "KeyPairName",
      "ParameterValue": "{your-keypair-name}"
    }, 
    {
      "ParameterKey": "PublicSubnet1ID",
      "ParameterValue": "{public subnet 1}"
    },
    {
      "ParameterKey": "PublicSubnet2ID",
      "ParameterValue": "{public subnet 2}"
    },
    {
        "ParameterKey": "VPCID",
        "ParameterValue": "{vpc id}"
    },
    {
      "ParameterKey": "RemoteAccessCIDR",
      "ParameterValue": "{your CIDR}"
    },
    {
      "ParameterKey":"EnableTCPForwarding",
      "ParameterValue": "true"
    }
  ]
```

And you can use the following command to deploy this stack.

```
aws cloudformation create-stack --stack-name {your-unique-stack-name} --template-body file://{name of the bastion template file} --parameters file://{name of your bastion parameters file} --capabilities CAPABILITY_IAM --region={region}
```

When you run this command, you will get the following output and if you go to the CloudFormation console, you should see it building your stack.

```
{
    "StackId": "arn:aws:cloudformation:eu-west-1:xxxxxxxxxxxx:stack/mwaa-bastion-proxy/aaaaaaaa-bbbb-cccc-dddd-eeeeeeeeeeee"
}
```

**Configuring security group for the bastion host**

You now have the bastion host configured and running. You should make sure it is all ok and that you can ssh into it before proceeding.

The bastion host you deployed is currently not able to access the MWAA environments. This is because there is a security group that governs access. The next step is to add this bastion host to that MWAA security group, and enable only HTTPS access.

When you setup the MWAA environment it created a security group. You can use the following cli commands to find the security group you need to change.

First list your MWAA environments

```
aws mwaa list-environments --region={region}
```

When you run this, you get output like the following.

```
{
    "Environments": [
        "PrivateEnvironment",
        "apache-airflow-aimlinnovate",
        "apache-airflow-innovate",
        "ricsue-dublin"
    ]
}

```
Then use the following command with the environment name you want to get the Security group from. As we are doing this for the Private Environment (in the example above) we issue this command:

```
aws mwaa get-environment --name {name of your MWAA Environment} | jq -r '.Environment | .NetworkConfiguration'
```

Which will generate this output. We can now see the name of the security group we need to add this Bastion Host to (it is only the SecurityGroupIds you need, you can ignore the SubnetIds).

```
{
  "SecurityGroupIds": [
    "sg-04aca4413364fexxx"
  ],
  "SubnetIds": [
    "subnet-0493dffd0282f4xxx",
    "subnet-08f416023356ffxxx"
  ]
}
```

You now need to add a new inbound rule for HTTPS and the source being the bastion security group which would have been setup as part of the CloudFormation stack. You can use the following command to obtain this information, replacing stack name with the one you used during the Linux bastion installation.

```
aws cloudformation describe-stack-resources --stack-name {stack name} | grep sg
```
This will create the following output.

```
"PhysicalResourceId": "sg-0a9b0b33467820xxx",
```
Which is the group you will need to add.

**SSH tunnel and proxy**

Once you have done that, it is now time to configure your ssh tunnel and browser proxy. To open an ssh tunnel to the Linux bastion host, use the following command replacing the ip/dns name and key with your own.

```
ssh -i {key.pem} -N -D 8157 ec2-user@{bastion-host-ip}
```
When you run this command you will not see any output. That is ok (and I have assumed you validated your ssh connection previously)

Now that is running, time to configure your browser. If you are NOT using a browser plugin (like FoxyProxy) then many web browsers allow you to configure proxies via a command line or configuration parameter. For example, with Chromium you can start the browser with the following command:

```
chromium --proxy-server="socks5://localhost:8157"
```
Which will start a browser session which will now use the ssh tunnel to proxy its requests. If you open your Private MWAA url as follows:

```
https://{unique-id}-vpce.{region}.airflow.amazonaws.com/home.
```
(Remember, you will have to add the https:// first as well as append /home from the uri you see in the MWAA console)

You should now have the Apache Airflow UI in your console. Check out the URL in the browser window - you can see it is the Private Apache Airflow environment.

![arch](https://github.com/094459/innovateaiml-airflow/blob/main/images/airflow-4.png?raw=true)

Follow the same process if you are using a browser plugin like FoxyProxy. Simply configure a local socks5 proxy on port 8157, and then configure a matching url pattern. If you use FoxyProxy, check out the repo as I have provided a sample configuration file you can use - you just need to edit the file and update to include your vpce url.


**Changing back/to Public and Private**

You can change between Public and Private at any time. Simply from the MWAA console, edit the current environment and change the settings. You can also do this via the CloudFormation script and change the value before running the AWS CloudFormation update-stack command.


**Conclusion**

This concludes the third post. I will create future posts covering some of the other ways you can connect to private instances, such as VPN in the future so keep a watch out.

In the next post we will look at how you can interact with MWAA via the command line, taking a look at the Apache Airflow commands available to you. 

If there is specific content you want to see, please get in touch.
