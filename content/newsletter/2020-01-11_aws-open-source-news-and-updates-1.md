---
title: 'AWS open source news and updates  #1'
date: '2020-01-11'
tags : [ oss-newsletter ]
---

This is the first in a regular series that will keep you posted on the open source projects, communities and activities that are going on in AWS as well as bringing you some interesting open source projects that builders have put together and that I have stumbled across.

### Open Source projects of the week

A few open source projects caught my eye, and I havent not yet had a chance to try them out yet, they are on my weekend project todo list.

The first one is **[AWS Security Toolbox](https://github.com/z0ph/aws-security-toolbox)**, a project that tries to bring in a number of open source tools to help with SecOps on AWS.

The second one is for all you working on machine learning, **Sagify** is a great command line tool train and deploy machine learning models on AWS SageMaker. **[The Sagify repo project can be found here.](https://github.com/Kenza-AI/sagify)**

One final project is **AWSume** This very nice projects makes it simple to manage multiple credentials via your command line, works with MFA and helps you work faster whilst staying secure. Check out the github repo **[here](https://github.com/trek10inc/awsume)** and a blog about it **[here](https://www.trek10.com/blog/awsume-v4/)**.

### Tweet of the week

This is a great thread and one that is essential reading. [In this thread](https://twitter.com/swardley/status/1213855567804022784?s=11), read about open source as a disruptive force via Simon Wardley - https://twitter.com/swardley/status/1213855567804022784?s=11

### Other interesting open source posts

Your Dive Deep for this week on open source, an articulate post from Bradley Khun exploring copyleft licenses. Well worth a read if you want to go deep - [Copyleft equality](https://sfconservancy.org/blog/2020/jan/06/copyleft-equality/) 

### Open Distro for Elasticsearch

If have started experimenting with Open Distro for Elasticsearch, it is worth keeping up to date on what is being produced by the community. This blog posted popped up onto my radar "[Trying out Open Distro for Elasticsearch with Logstash](https://medium.com/@sjoerdsmink/trying-out-open-distro-for-elasticsearch-with-logstash-8cc8be3e1e84)" which is a great write up and follows some similar adventures I had a few months back when I was attempting to do the same.

In my setup, I was trying to extract the logs from my excellent ASUS AC68u router that natively supports syslog exporting to a remote machine, and then import them into Open Distro that I have running on an AWS EC2 instance. I wanted to use Logstash rather than filebeat becasue I was doing some transformation of IP address to GEO location, so I could track the geography of IP's that my router was dropping. Logstash is a great option when you want to do more transformations than Filebeat can do for you.

I am currently in the process of experimenting with running Open Distro for Elasticsearch on Amazon EKS, and so was glad to see that the Helm chart has been released via the community site (you can check it out [here](https://opendistro.github.io/for-elasticsearch-docs/docs/install/helm/))

Finally, Open Distro for Elasticsearch 1.3 was announced a few weeks back and it was a bumper edition. Aside from updates to Elasticsearch and Kibana versions to 7.3.2, what really caught my eye was the anomoly detection plugin that was released in alpha state. They released a blog post which you can read [here](https://opendistro.github.io/for-elasticsearch/blog/odfe-updates/2019/11/real-time-anomaly-detection-in-open-distro-for-elasticsearch/).

### We are hiring

We are hiring, so if you love open source, then why not check out the current openings. We would love to hear from you and if you want to chat and ask me anything, connect to me via LinkedIn or Twitter and always happy to talk.

[Open Source jobs at Amazon and AWS](https://aws.amazon.com/opensource/?opensource-all.sort-by=item.additionalFields.startDate&opensource-all.sort-order=asc) - scroll to bottom, on left.