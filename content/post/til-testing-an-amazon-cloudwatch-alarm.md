---
title: 'TIL: Testing an Amazon Cloudwatch alarm'
date: '2021-01-07'
tags: [aws cloudwatch]
---
Today I was setting up an application load balancer that sits in front of a test application I have put together. Setting this up was super easy, and very quickly I had my domain pointing to the alias and serving requests.

As part of the setup, I wanted to monitor the application load balancer to let me know when requests were failing to the downstream application (anything other than an HTTP 200) and so I set this up super easily in Amazon Cloudwatch. I now had monitoring and a nice dashboard that gave me the health of the application from the application load balancer perspective.

However, what I really needed was to be informed when there was issues. Within the Amazon CloudWatch dashboard I was able to very easily setup an alarm, and then trigger an SNS notification that would send me an email every time the threshold of failed requests was met/exceeded.

With this setup, I needed to now figure out how I was going to test this, after all, no one really cares about the monitoring/alarms until they actually need to be used. I found [this](https://devopslife.io/testing-cloudwatch-alarm-using-aws-cli/) post from the devopslife blog which pointed me in the right direction.

Using this command,

```
$ aws cloudwatch set-alarm-state --alarm-name "{your alarm name}" --state-reason "Testing the Amazon Cloudwatch alarm" --state-value ALARM
```

>The above assumes you have the aws cli installed somewhere and are using credentials/account with the right level of access.

I was able to validate that the Alarm had been setup and I would receive the notification. When I looked at the Cloudwatch dashboard I could see that this metric was now in Alarm status, and after about a minute I received my notification. The alarm reset itself after a few minutes so you do not need to do anything extra.










