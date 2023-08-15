---
title: 'A look at airflowctl, a tool to help you manage Apache Airflow projects'
date: '2023-08-14'
tags : [ oss-newsletter, Apache Airflow, airflowctl]

---

I have written in the past about setting up developer environments and tools when working with Apache Airflow. Today I came across a new tool from [Kaxil Naik](https://github.com/kaxil), director of engineering at Astronomer and all round Apache Airflow good guy. Kaxil has put together [airflowctl](https://aws-oss.beachgeek.co.uk/35c), a command-line tool for managing Apache Airflow™ projects, and making it super easy to get up and running. What does it do? Well, it helps you install and use different versions of Apache Airflow, work with Variables and Connections, provide live logs, and more.

The README provides nice documentation to get you up and running, but I thought I would do a quick demo showing how you can get this up and running on your AWS environment, using my Cloud 9 developer environment. This is my first impressions of the tool, having used it for the past few hours.

The tool has a number of different steps you need to follow. Configure, Build, and then Run, so lets take a look at each of these as we get up and running.

**Configure**

First we need to install the tool. I am running Python 3.7.16.

```
pip install airflowctl

..
..
  Downloading exceptiongroup-1.1.3-py3-none-any.whl (14 kB)
Installing collected packages: click, colorama, mdurl, markdown-it-py, rich, shellingham, typer, psutil, pyyaml, idna, certifi, sniffio, h11, exceptiongroup, anyio, httpcore, httpx, python-dotenv, rich-argparse, airflowctl
Successfully installed airflowctl-0.1.6 anyio-3.7.1 certifi-2023.7.22 click-8.1.6 colorama-0.4.6 exceptiongroup-1.1.3 h11-0.14.0 httpcore-0.17.3 httpx-0.24.1 idna-3.4 markdown-it-py-2.2.0 mdurl-0.1.2 psutil-5.9.5 python-dotenv-0.21.1 pyyaml-6.0.1 rich-13.5.2 rich-argparse-1.2.0 shellingham-1.5.0.post1 sniffio-1.3.0 typer-0.9.0
```
We can make sure this has worked ok by running the --help for the command

```
airflowctl --help
                                                                                                                                                                                  
 Usage: airflowctl [OPTIONS] COMMAND [ARGS]...                                                                                                                                    
                                                                                                                                                                                  
╭─ Options ──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╮
│ --install-completion          Install completion for the current shell.                                                                                                        
│ --show-completion             Show completion for the current shell, to copy it or customize the installation.                                                                 
│ --help                        Show this message and exit.                                                                                                                      
╰────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╯
╭─ Commands ─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╮
│ build     Build an Airflow project. This command sets up the project environment, installs Apache Airflow and its dependencies.                                                
│ info      Display information about the current Airflow project.                                                                                                               
│ init      Initialize a new Airflow project.                                                                                                                                    
│ list      List all Airflow projects created using this CLI.                                                                                                                    
│ logs      Continuously display live logs of the background Airflow processes.                                                                                                  
│ start     Start Airflow.                                                                                                                                                       
│ stop      Stop a running background Airflow process and its entire process tree.                                                                                               
╰────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╯
```
and if I try and use the list command to list Airflow environments

```
airflowctl list
No tracked Airflow projects found.
```
No surprises that it did not find any. Lets fix that. We use the init command to create a new environment, and we can pass in additional configuration details. To explore the different options, we can use the --help command again.

```
airflowctl init --help
                                                                                                                                                                                  
 Usage: airflowctl init [OPTIONS] PROJECT_PATH                                                                                                                                    
                                                                                                                                                                                  
 Initialize a new Airflow project.                                                                                                                                                
                                                                                                                                                                                  
╭─ Arguments ────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╮
│ *    project_path      PATH  Path to initialize the project in. [default: None] [required]                                                                                     
╰────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╯
╭─ Options ──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╮
│ --project-name                           TEXT  Name of the Airflow project to be initialized.                                                                                  
│ --airflow-version                        TEXT  Version of Apache Airflow to be used in the project. Defaults to latest. [default: 2.6.3]                                       
│ --python-version                         TEXT  Version of Python to be used in the project. [default: 3.7.16]                                                                  
│ --build-start        --no-build-start          Build the project and start after initialization. [default: no-build-start]                                                     
│ --background         --no-background           Run Airflow in the background. [default: no-background]                                                                         
│ --help                                         Show this message and exit.                                                                                                     
╰────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╯

```

I want to spin up an Apache Airflow 2.4.3 so that I can work with my Managed Workflows for Apache Airflow environments of the same version, and I want a version of Python to match.

```
airflowctl init airflow-jokes --airflow-version 2.4.3 --python-version 3.10.11
```

The command is super quick, and the output of this tool generates a folder in the directory you ran the command. We can now see we have a airflow-jokes directory with a number of files.

```
├── airflow-jokes
│   ├── .airflowctl
│   │   └── config.yaml
│   ├── dags
│   │   └── example_dag_basic.py
│   ├── .env
│   ├── plugins
│   ├── requirements.txt
│   └── settings.yaml
```

The project repo provides details as to what these files do, so go check the project  to dive deeper. For the purpose of this quick walk through, we do not need to change anything, and our configuration stage is complete. Now lets build our Apache Airflow environment.

**Build**

Changing into the directory that the Configure stage created, we can now build  our project using the following command.

```
airflowctl build

Python version (3.10.11) is different from the default Python version (3.7.16 (default, Mar 10 2023, 03:25:26) 
[GCC 7.3.1 20180712 (Red Hat 7.3.1-15)]).
pyenv found. Using pyenv to install and set the desired Python version.
Requirement already satisfied: pip in ./.venv/lib/python3.10/site-packages (23.0.1)
..
..
Apache Airflow 2.4.3 installed successfully!
Virtual environment at /home/ec2-user/environment/airflow-jokes/.venv
Airflow project built successfully.

```

> **NOTE** When I did this the first time, I had no available Python version that matched what I had setup in my initial configure command (--python-version 3.10.11). This tool will use pyenv if it is available, but I had not installed it. If you plan to use a specific Python version, make sure you have pyenv up and running.
>  I used [this gist](https://aws-oss.beachgeek.co.uk/35d) when I setup my Cloud 9 environment which seemed to do the trick for me. You will also need to make sure you have any dependencies already installed in order to build newer versions of Python. I have the following setup which worked for me:
> ```
> sudo yum install gcc zlib-devel bzip2 bzip2-devel readline readline-devel sqlite sqlite-devel openssl openssl-devel libffi-devel xz-devel -y
> ```
> If you are trying to install 3.10.11 and run into errors (such as "ModuleNotFoundError: No module named '_ssl'") then this [Stack Overflow](https://aws-oss.beachgeek.co.uk/35e) solution worked for me

It took about 5 minutes to complete on my Cloud9 environment. We are now ready to run our Apache Airflow environment.

**Starting Apache Airflow**

We use the following command to start our Apache Airflow instance. You can use the --background flag if you want to run it as a background process, but I want to see the logs and make sure it is all up and running.

```
airflowctl start

Verifying Airflow installation...
2.4.3
standalone | Starting Airflow Standalone
standalone | Checking database is initialized
INFO  [alembic.runtime.migration] Context impl SQLiteImpl.
INFO  [alembic.runtime.migration] Will assume non-transactional DDL.
INFO  [alembic.runtime.migration] Running stamp_revision  -> e07f49787c9d
..
..
 scheduler | [2023-08-14 14:11:12 +0000] [19952] [INFO] Booting worker with pid: 19952
 webserver | [2023-08-14 14:11:15 +0000] [19942] [INFO] Starting gunicorn 20.1.0
 webserver | [2023-08-14 14:11:15 +0000] [19942] [INFO] Listening at: http://0.0.0.0:8080 (19942)
 webserver | [2023-08-14 14:11:15 +0000] [19942] [INFO] Using worker: sync
 webserver | [2023-08-14 14:11:15 +0000] [19976] [INFO] Booting worker with pid: 19976
 webserver | [2023-08-14 14:11:15 +0000] [19977] [INFO] Booting worker with pid: 19977
standalone | 
standalone | Airflow is ready
standalone | Login with username: admin  password: TwBXRVqEUuNQ4wfx
standalone | Airflow Standalone is for development purposes only. Do not use this in production!
standalone | 

```
You will notice that the admin passwords appears in the console log. It is also output as a file called standalone_admin.txt incase you want to access it quickly.

> **HELP!** If when you run the start command, you get an error like 
> """
> airflow.exceptions.AirflowConfigException: error: sqlite C library version too old (< 3.15.0). See https://airflow.apache.org/docs/apache-airflow/2.4.3/howto/set-up-database.html#setting-up-a-sqlite-database
> Error starting Airflow: Command 'source /home/ec2-user/environment/airflow-jokes/.venv/bin/activate && airflow version' returned non-zero exit status 1.
> """
> then check out [this](https://aws-oss.beachgeek.co.uk/35f) on the Apache Airflow site. You will now run this as root on your Linux environment. You will need to uninstall anything you had previously installed, and re-create your configuration files (or at least, I could not get them to work until I did this)
> 

You can also run this in the background, by using the --background flag. So hitting CTRL+C to exit the foreground mode, I then ran

```
airflowctl start --background

Verifying Airflow installation...
2.4.3
Airflow is starting in the background (PID: 17208).
Logs are being captured. You can use 'airflowctl logs' to view the logs.
```

And I now have control of the shell. If I want to view the logs, I simply use the logs command with a suitable flag depending on which log I want to use. -w for web server, -s for scheduler. The options are in the docs, so check that out.

```
airflowctl logs -w
```

When you are in the logs, you will need to CTRL + C to exit.

*Accessing the Airflow UI*

You can now open up the URL in Cloud9 to access this. However, we have to do a couple of things first. First we need to go to your Cloud9 instance, and open up an inbound port for your specific IP address, to access port 8080. This is the port that Apache Airflow is listening on, so we need to open this up. The second is to grab the IP of our Cloud 9 instance, which we can do easily enough by running this command in a terminal. Read [this page](https://docs.aws.amazon.com/cloud9/latest/user-guide/app-preview.html) of the AWS Cloud 9 documentation to help you through this if you are not sure.

```
curl http://169.254.169.254/latest/meta-data/public-ipv4
```
The output will be your public IP address. You can now open this up in a browser, and you should be presented with a familiar Apache Airflow login box.

![example apache airflow ui as seen from airflowctl](https://ricsuepublicresources.s3.eu-west-1.amazonaws.com/images/blog/airflowctl.png)


> **Note!** This setup only runs Apache Airflow in http not https mode.

**Stopping your environments**

To stop Apache Airflow, you can use either CTRL+C is you are running it in the foreground, or the airflowctl stop command if running in background.

> **NOTE!** I found a small issue in that when you run in background mode, it creates a file (.airflowctl/.background_process_ids) which contains the parent PID. The PID was always off, so I needed to manually edit this. I have created [an issue here](https://github.com/kaxil/airflowctl/issues/1) so if this happens to you, follow that.


```
airflowctl stop
All background processes and their entire process trees have been stopped.
/bin/sh: line 1: 17210 Terminated              airflow standalone > /tmp/tmpbzr1ytmd 2>&1
```

And that is it, you have now stopped your environment.

**Other useful commands**

airflowctl has a few other useful commands. You can list the number of Airflow environments you have using the --list flag

```
airflowctl list
┏━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━┓
┃ Project Name                             ┃ Project Path                             ┃ Python Version ┃ Airflow Version ┃
┡━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━━┩
│ /home/ec2-user/environment/airflow-jokes │ /home/ec2-user/environment/airflow-jokes │ 3.10.11        │ 2.4.3           │
└──────────────────────────────────────────┴──────────────────────────────────────────┴────────────────┴─────────────────┘

```

**Deleting environments**

I am not sure if this is the correct way, but given that these Airflow environments all live within a directory, to remove everything I just deleted the parent folder.

**Conclusion**

It is always fun to see new projects to help developers get hands on with Apache Airflow and boost their productivity. I will be using this and testing it out over the coming weeks and see how it compares to some of the others tools I have been using, such as [mwaa-local-runner](https://aws-oss.beachgeek.co.uk/gd).
