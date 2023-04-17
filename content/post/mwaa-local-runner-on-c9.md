---
title: 'Getting mwaa-local-runner up on AWS Cloud9'
date: '2023-04-17'
tags: [ Apache Airflow, mwaa, mwaa-local-runner, AWS Cloud9 ]
---

Here is a quick recipe if you are looking to get mwaa-local-runner up and running on your Cloud9 developer setup. This might not be the most optimised way, so I am very happy to received suggestions on how to improve this. What I will cover here is how to deploy mwaa-local-runner onto a standard Cloud9 IDE, deployed in a default VPC.

The first thing I needed to do was to increase the size of my local disk as Cloud9 only provides 10gb of storage. This is fine for typical use cases, but we are going to be building container images, so need to set this higher.

```
pip3 install --user --upgrade boto3
export instance_id=$(curl -s http://169.254.169.254/latest/meta-data/instance-id)
python -c "import boto3
import os
from botocore.exceptions import ClientError 
ec2 = boto3.client('ec2')
volume_info = ec2.describe_volumes(
    Filters=[
        {
            'Name': 'attachment.instance-id',
            'Values': [
                os.getenv('instance_id')
            ]
        }
    ]
)
volume_id = volume_info['Volumes'][0]['VolumeId']
try:
    resize = ec2.modify_volume(    
            VolumeId=volume_id,    
            Size=30
    )
    print(resize)
except ClientError as e:
    if e.response['Error']['Code'] == 'InvalidParameterValue':
        print('ERROR MESSAGE: {}'.format(e))"
if [ $? -eq 0 ]; then
    sudo reboot
fi
```

The next thing I need to do is install "docker-compose" as whilst Docker is installed, docker-compose is not. This is the script I use

```
wget https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)
sudo mv docker-compose-$(uname -s)-$(uname -m) /usr/bin/docker-compose
chmod +x /usr/bin/docker-compose
```

And if this is successful, you should now have it available via the command line

```
ops:~/environment $ docker-compose version
Docker Compose version v2.17.2
```

This should be everything you need to get started. However, we do need one piece of information before we proceed, and that is the public IP address for your Cloud9 instance. We need this as we are going to update the URL configuration parameter in mwaa-local-runner. (If you do not do this, you will get 400 Gateway errors when accessing Airflow via the UI). Run the following command to find yours

```
curl http://169.254.169.254/latest/meta-data/public-ipv4
3.253.9.131
```

You can now check out the mwaa-local-runner project into your Cloud9 environment

```
git clone https://github.com/aws/aws-mwaa-local-runner.git
```

We now need to change a couple of things.

The first is to update the airflow.cfg so that we can update the base_url parameter (line 406) with the public IP of your Cloud9 instance.

```
#base_url = http://localhost:8080
base_url = https://3.253.9.131:8080
```

The next change, still in the airflow.cfg, to update how quickly it picks up DAGs in the DAGs folder. Line 757 is changed

```
#dag_dir_list_interval = 300
dag_dir_list_interval = 5

```

You can now save this file, and you are ready to build your mwaa-local-runner image. You do this using the following command (and this works against any version of Apache Airflow that mwaa supports)

```
mwaa-local-env build-image
```

This will now take around 10 minutes to complete the build process. Go grab your favourite drink and then come back. Hopefully, you should see something like:

```
[+] Building 543.8s (27/27) FINISHED                                                                                                                                                                           
 => [internal] load build definition from Dockerfile                                                                                                                                                      0.0s
 => => transferring dockerfile: 43B                                                                                                                                                                       0.0s
 => [internal] load .dockerignore                                                                                                                                                                         0.0s
 => => transferring context: 2B                                                                                                                                                                           0.0s
 => [internal] load metadata for docker.io/library/amazonlinux:2                                                                                                                                          1.6s
 => [auth] library/amazonlinux:pull token for registry-1.docker.io                                                                                                                                        0.0s
 => CACHED [ 1/21] FROM docker.io/library/amazonlinux:2@sha256:ad9b9135cd4eaa9f5a7b903b1cd72fef23027260c9aa84a743d090b64ce3609e                                                                           0.0s
 => [internal] load build context                                                                                                                                                                         0.0s
 => => transferring context: 5.46kB                                                                                                                                                                       0.0s
 => [ 2/21] COPY script/bootstrap.sh /bootstrap.sh                                                                                                                                                        0.1s
 => [ 3/21] COPY script/systemlibs.sh /systemlibs.sh                                                                                                                                                      0.0s
 => [ 4/21] COPY script/generate_key.sh /generate_key.sh                                                                                                                                                  0.0s
 => [ 5/21] COPY script/run-startup.sh /run-startup.sh                                                                                                                                                    0.0s
 => [ 6/21] COPY script/shell-launch-script.sh /shell-launch-script.sh                                                                                                                                    0.0s
 => [ 7/21] COPY script/verification.sh /verification.sh                                                                                                                                                  0.0s
 => [ 8/21] COPY config/constraints.txt /constraints.txt                                                                                                                                                  0.0s
 => [ 9/21] COPY config/mwaa-base-providers-requirements.txt /mwaa-base-providers-requirements.txt                                                                                                        0.0s
 => [10/21] RUN chmod u+x /systemlibs.sh && /systemlibs.sh                                                                                                                                              133.1s
 => [11/21] RUN chmod u+x /bootstrap.sh && /bootstrap.sh                                                                                                                                                343.3s 
 => [12/21] RUN chmod u+x /generate_key.sh && /generate_key.sh                                                                                                                                            0.6s 
 => [13/21] RUN chmod u+x /run-startup.sh                                                                                                                                                                 0.3s 
 => [14/21] RUN chmod u+x /shell-launch-script.sh                                                                                                                                                         0.3s 
 => [15/21] RUN chmod u+x /verification.sh                                                                                                                                                                0.5s 
 => [16/21] COPY script/entrypoint.sh /entrypoint.sh                                                                                                                                                      0.0s 
 => [17/21] COPY config/airflow.cfg /usr/local/airflow/airflow.cfg                                                                                                                                        0.0s 
 => [18/21] COPY config/webserver_config.py /usr/local/airflow/webserver_config.py                                                                                                                        0.0s
 => [19/21] RUN chown -R airflow: /usr/local/airflow                                                                                                                                                     31.4s
 => [20/21] RUN chmod +x /entrypoint.sh                                                                                                                                                                   0.4s
 => [21/21] WORKDIR /usr/local/airflow                                                                                                                                                                    0.1s
 => exporting to image                                                                                                                                                                                   31.7s
 => => exporting layers                                                                                                                                                                                  31.7s
 => => writing image sha256:54d466e5db131a71b694018f94ab69653794548551c37b05d172f5070f4deda8                                                                                                              0.0s
 => => naming to docker.io/amazon/mwaa-local:2_4                                                                                                                                                          0.0s

Use 'docker scan' to run Snyk tests against images to find vulnerabilities and learn how to fix them
```

Congratulations, the hard part has been done.


> **Note** If you see the following error: 
> ```
> 16 188.4 + sudo -u airflow pip3 install --no-use-pep517 --constraint /constraints.txt poetry
> 16 188.8 
> 16 188.8 Usage:   
> 16 188.8   pip3 install [options] <requirement specifier> [package-index-options] ...
> 16 188.8   pip3 install [options] -r <requirements file> [package-index-options] ...
> 16 188.8   pip3 install [options] [-e] <vcs project url> ...
> 16 188.8   pip3 install [options] [-e] <local project path> ...
> 16 188.8   pip3 install [options] <archive url/path> ...
> 16 188.8 
> 16 188.8 --no-use-pep517 error: It is not possible to use --no-use-pep517
> 16 188.8 without setuptools and wheel installed.
>
>executor failed running [/bin/sh -c chmod u+x /bootstrap.sh && /bootstrap.sh]: exit code: 2
>```
>
>You will need to update the "bootstrap.sh" script, and update line 43 so that it looks like:
>```
>pip3 install $PIP_OPTION --upgrade 'pip<23'
>```
>This is to resolve an issue with pip version 23.1
>

To start mwaa-local-runner, all you need to do now is:

```
mwaa-local-env start
```
And Apache Airflow will start to boot. It will take 2-3 minutes, but once ready you will see something like

```
aws-mwaa-local-runner-2_4-local-runner-1  | [2023-04-17 10:09:29 +0000] [202] [INFO] Starting gunicorn 20.1.0
aws-mwaa-local-runner-2_4-local-runner-1  | [2023-04-17 10:09:29 +0000] [202] [INFO] Listening at: http://0.0.0.0:8080 (202)
```
And you can now open a browser, pointing to your public Ip address and access Apache Airflow on port 8080.

**Conclusion**

This short post showed you how you can get mwaa-local-runner up and running on your AWS Cloud9 instances. I have been experimenting using this, and really like that I can decouple this from my local setup. I am still working on tweaking the setup so that I can locadown public access to the Cloud9 instance to just my own IP address, something I would recommend you do to. 

If you have found this blog post helpful, please give me some feedback by completing [this very short survey here](https://pulse.buildon.aws/survey/D4L9Y3II)


