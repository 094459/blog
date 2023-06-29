---

title: 'Deploying a serverless web analytics solution for your websites'
date: '2023-06-29'
tags : [ open source, serverless-website-analytics]

---

Like many folk, I run a [personal blog](https://blog.beachgeek.co.uk). This blog runs Hugo and turns my markdown pages into static content, which I then deploy on Netlify. One of the key things about running a blog is understanding how readers are interacting with your content, and this is where web analytics solutions can help you. A common solution to this has been to use something like Google Analytics as this typically is very easy to integrate into your website.

Very recently I came across a very cool project from AWS Hero Rehan van der Merwe, called [serverless-website-analytics](https://aws-oss.beachgeek.co.uk/2yx). 

![architecture of serverless-website-analytics](https://github.com/rehanvdm/serverless-website-analytics/blob/main/docs/imgs/serverless-website-analytics.drawio.png?raw=true)

This project helps you to provision infrastructure needed to manage capturing analytics for any number of your web sites. It makes deployment super easy because it comes as an AWS CDK construct (TypeScript/Javascript only sadly, but at least it was good excuse to try something different). Whilst the core of the project is this CDK construct, the project also has a couple of other repos that provide an example site setup for you to reference, as well as a dedicated client portion if you want to do deeper integration with your site.

In this blog post I want to share how I moved my analytics to using this project, and hope that some of you will also check this out and try it out for yourselves. I will just touch upon basic integration, and leave you to explore the finer details of what you might be able to achieve when using this project. A big hats off to Rehan for creating this project.

**What do you need**

* An AWS Account in which to deploy serverless-website-analytics
* A Route53 hosted zone
* An SSL certificate generated through AWS Certificate Manager
* CDK v2 - I am running 2.85.0 (build 4e0d726) at the time of writing this post

You will find all the code I used to deploy my site at my [GitHub repo](https://github.com/094459/analytics).

One of the best things about the documentation on this project is that it has a great summary of expected costs you might expect based on different load scenarios. This is awesome, and I wish more projects would add this info. I have been running it for about 24 hours, and looking at the AWS Cost Explorer, its costing me around \$0.50 at the moment.

**Getting started - DNS and Certificate**

Like many of you, over the years I have purchased a number of domains that I had great plans for. I thought this would be the perfect time to put one of those to use.

The first thing to bear in mind is that you need to change AWS region to us-east-1, even if you are going to deploy this project in a different AWS region (in my case, eu-west-1).

From the us-east-1 AWS region I created a new Route 53 Hosted Zone, and configured the naming servers where I had originally purchased my domains (https://www.ionos.co.uk/) to point to the naming servers of this new Hosted Zone. The reason I did this was to make it simpler when doing the next step of creating my SSL certificate, but also because the CDK construct can then automatically create the Cloudfront resources for me without me having to do this manually afterwards. So my domain (mydomain.com) was now being managed by Route53. You will need to grab the **Hosted zone ID** from the Route53 console. It is actually hidden by default, and you have to click on the twisty called "Hosted zone details" to reveal. We will need that when we deploy the CDK stack.

Sticking with the us-east-1 region, I then created a new public certificate against this domain (for example, web-analytics.mydomain.com). Once completed, you will need to grab the certificate Arn, as we will need this in the CDK stack.

**Updating our CDK stack**

We are now ready to configure our AWS CDK stack. Grabbing the code from my [GitHub repo](https://github.com/094459/analytics), there are a couple of things you need to update.

First you will need to update the "bin/index.ts" file to reflect your AWS account and the region you want to deploy this into. It is probably worth noting that whilst this might work in many AWS regions, this project does use a wide variety of AWS services and so you should check that those are available in the region you want to deploy into.

```
#!/usr/bin/env node
import 'source-map-support/register';
import * as cdk from 'aws-cdk-lib';
import { App } from '../lib/app';
import {Tags} from "aws-cdk-lib";

const app = new cdk.App();

const swaStack = new App(app, 'beachgeek-analytics', {
  env: {
    account: 'xxxxxxxx', 
    region: 'eu-west-1',
  },
});

/* Adds tags to all the resources for billing purposes */
Tags.of(swaStack).add('App', 'beachgeek-analytics');
```

Once we have updated this, we can move to the main act, updating the "lib/app.ts" file. Now this is very nicely commented by Rehan to make it easyt for you to understand how you can tweak the deployment to your own needs. The CDK construct also provides lots of flexibility around deployment choices which is very nice.

The first thing we need to do is update the Certificate Arn information for the certificate we created

```
import * as cdk from 'aws-cdk-lib';
import { Construct } from 'constructs';
import * as cert from 'aws-cdk-lib/aws-certificatemanager';
import * as route53 from 'aws-cdk-lib/aws-route53';
import * as sns from 'aws-cdk-lib/aws-sns';
// import {Swa} from "serverless-website-analytics/src"; // For the npm linked package one while testing
import {AllAlarmTypes, Swa} from 'serverless-website-analytics';

export class App extends cdk.Stack {
  constructor(scope: Construct, id: string, props?: cdk.StackProps) {
    super(scope, id, props);

    /* Optional, see descriptions on the `domain` property below. Needs tp cover the `domain.name` and
       {auth.cognito.loginSubDomain}.{domain.name}` domains and must be in us-east-1 even if your stack is
       somewhere else  */
    const wildCardCertUsEast1 = cert.Certificate.fromCertificateArn(this, 'Cert',
        'arn:aws:acm:us-east-1:xxxx:certificate/a58c22ba-e1cb-4b16-a74e-2f3da70ecxxx');


```

Next we need to provide an email for the SNS alerts that the project creates. You will be sent an email to this, which you will need to click to confirm subscription.

```
    const alarmTopic = new sns.Topic(this, "alarm-topic");
    new sns.Subscription(this, "alarm-topic-subscription", {
      topic: alarmTopic,
      protocol: sns.SubscriptionProtocol.EMAIL,
      endpoint: 'ricsue@amazon.co.uk',
    });
```
Next we define which sites we want to collect analytics for - in my case I want to use this against my site, blog.beachgeek.co.uk

```
    new Swa(this, 'beachgeek-analytics', {
      environment: 'prod',
      awsEnv: {
        account: this.account,
        region: this.region,
      },
      sites: [
        'blog.beachgeek.co.uk',
      ],
```
You can tweak your allowedOrigins to narrow down access as to who can ingest data if you need. I left mine open

```
      allowedOrigins: ['*'],
      /* Can be set explicitly instead of allowing all */
      // allowedOrigins: [
      //   'https://example.com',
      //   'https://www.example.com',
      //   'http://localhost:3000',
      //   'tests1',
      //   'tests2',
      // ],
```

Next I configured security access to the actual dashboard. Now you can leave this open if you are just demoing this, but I wanted to use this so I set up Basic Authentication. This is not the recommended setup if you are going to be using this in production, but is ok for just testing out this solution. For a more robust deployment, you should consider configuring Cognito, which is what I will be doing down the line once I have had a chance to further evaluate the tool. 

> **Note!** The project repo provides additional information around the auth options including how the Cognito integration works, so check that out.

```

      /* Specify one or the other, not both. Specifying neither means the site is unauthenticated, which is what we
         want for the Demo. */
      auth: {
        basicAuth: {
          username: 'xxxx',
          password: 'xxxx',
        },
      },
      //  auth: {
      //    cognito: {
      //      loginSubDomain: 'login', // This has to be unique across Cognito if not specifying your own domain
      //      users: [{
      //        name: 'Ricardo Sueiras',
      //        email: 'ricsue@amazon.co.uk',
      //      }]
      //    }
      //  },
```
Finally we update the domain information that we want to use to connect to the dashboard. Here we take the domain name we registered our certificate against (for example, web-analytics.mydomain.com) and update the name: value. We updated the hostedZoneId with our Route53 hosted zone id info we got, and then finally we updatge the zoneName with our domain (for example, mydomain.com).

As I want to use this, I also set the "isDemoPage" to false (the default is true in the sample repo).

I leave all other settings as default.

```

      /* Optional, if not specified uses default CloudFront and Cognito domains */
      domain: {
        name: 'web-analytics.mydomain.com',
        certificate: wildCardCertUsEast1,
        /* Optional, if not specified then no DNS records will be created. You will have to create the DNS records yourself. */
        hostedZone: route53.HostedZone.fromHostedZoneAttributes(this, 'HostedZone', {
          hostedZoneId: 'Z08557552NF1Q1JMUT38G',
          zoneName: 'mydomain.com',
        }),
        trackOwnDomain: true,
      },
      isDemoPage: false, /* Do not specify for your dashboard */

      observability: {
        dashboard: true,
        alarms: {
          alarmTopic,
          alarmTypes: AllAlarmTypes
        },
      }
    });

  }
}
```
Once saved, we are ready to deploy.

**Deploying our CDK stack**

To deploy we simply use the following command:

```
cdk destroy beachgeek-analytics
```
CDK will initially upload assets to its S3 bucket, and then you will be asked to review some security information of resources the stack wants to create. Once you have reviewed, if you are happy to proceed answer Y. The stack will start to deploy and will take around 20-25 minutes to complete. You should see output similar to the following:


```
[Warning at /beachgeek-analytics] Basic auth is not recommended for production use, it only protects the html page, not the APIs, consider Cognito instead

✨  Synthesis time: 7.38s

beachgeek-analytics:  start: Building 04cd21d1b6969e2a33e6fdbb3a391ae03298671a7afb974a3a29f42642967e01:665240076514-eu-west-1
beachgeek-analytics:  success: Built 04cd21d1b6969e2a33e6fdbb3a391ae03298671a7afb974a3a29f42642967e01:665240076514-eu-west-1

Do you wish to deploy these changes (y/n)? y
beachgeek-analytics: deploying... [1/1]
beachgeek-analytics: creating CloudFormation changeset...

 ✅  beachgeek-analytics

✨  Deployment time: 501.96s

Outputs:
beachgeek-analytics.beachgeekanalyticsAnalyticsBucket = beachgeek-analytics-bucket-analytics
beachgeek-analytics.beachgeekanalyticsAnalyticsGlueDbName = beachgeek-analytics-db
beachgeek-analytics.beachgeekanalyticsApiFrontLambdaUrl = https://web-analytics.mydomain.com/api
beachgeek-analytics.beachgeekanalyticsApiIngestUrl = https://web-analytics.mydomain.com/api-ingest
beachgeek-analytics.beachgeekanalyticsCloudFrontId = E211ERAL6DFR11
beachgeek-analytics.beachgeekanalyticsDashboardUrl = https://eu-west-1.console.aws.amazon.com/cloudwatch/home?region=eu-west-1#dashboards/dashboard/beachgeek-analytics-dashboard
beachgeek-analytics.beachgeekanalyticsFirehoseEventsName = beachgeek-analytics-analytic-events-firehose
beachgeek-analytics.beachgeekanalyticsFirehosePageViewsName = beachgeek-analytics-analytic-page-views-firehose
beachgeek-analytics.beachgeekanalyticsFrontendUrl = https://web-analytics.mydomain.com
Stack ARN:
arn:aws:cloudformation:eu-west-1:xxxx:stack/beachgeek-analytics/2cccca50-15fa-11ee-9846-0a2fd60626fb

✨  Total time: 509.34s
```
That's it, you are done.

**Integrating this into your websites**

We now have all the infrastructure setup the start receiving our click stream data from our websites. You can actually open up a browser and access it via the URL that you defined (in my example above, https://web-analytics.mydomain.com). If you do this, you will be asked to authenticate based on the method you chose (Basic Authetnication or Cognito), and after logging in you will see a blank dashboard. What we need to do now is to integrate our websites.

Rehan has created a separate repo for the client side of this project, which you can look at [here](https://github.com/rehanvdm/serverless-website-analytics-client). As I have a simple Hugo site, all I need to do is use the standalone import script approach, and figure out how I can integrate:

```
<script src="web-analytics.mydomain.com/cdn/client-script.js" site="blog.beachgeek.co.uk"></script>

```
Into my site. Before I did that however, I wanted to make sure that I could access the client-script.js. In a new browser (in private/incognito mode) I opened up this resource ("web-analytics.mydomain.com/cdn/client-script.js") expecting to see the code that would be used to send clickstream data. However, I was prompted to authenticate. This was unexpected and not the desired behaviour given my static websites do not require authentication.

I ended up have to change the code that the CDK stack deployed slightly. As part of the deployment there is a CloudFront function that implements basic authentication. I just needed to add an exclusion so that it would not try and authenticate requests to this client-script.js. From the CloudFront console, I update the code as follows (the code is also in the repo)

```
var USERNAME = 'xxxxx';
var PASSWORD = 'xxxxx';

var response401 = {
  statusCode: 401,
  statusDescription: 'Unauthorized',
  headers: {
    'www-authenticate': {value:'Basic'},
  },
};

function validateBasicAuth(authHeader)
{
  var match = authHeader.match(/^Basic (.+)$/);
  if (!match)
    return false;

  //https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/functions-javascript-runtime-features.html
  var credentials = String.bytesFrom(match[1], 'base64').split(':', 2);

  return credentials[0] === USERNAME && credentials[1] === PASSWORD;
}

function handler(event)
{
  var request = event.request;
  var headers = request.headers;
  var uri = request.uri;
  var specificUri = 'cdn/client-script.js';
  var auth = (headers.authorization && headers.authorization.value) || '';
  
  if (uri.includes(specificUri))
    return request;

  if (!validateBasicAuth(auth))
    return response401;

  return request;
}

```
I am not sure if this needs to be updated when using Cognito, so will update this post when I go down that path. Once I saved and deployed this change, I was now able to view the script without being requested to authenticate. All good.

As mentioned previously, my blog uses Hugo. Hugo itself has the concept of templates, and these templates provide opportunities to insert snippets of code to integrate clickstream analytics very easily. If I look at the theme I am using (cupper-hugo) I can see that in the layouts/partials folder there are a number of html files, including one called analytics.html. When I open up this file:

```
<!-- paste your analytics code into a analytics.html file in your partials directory -->
```

so I just update this so that it looks like

```
<script src="web-analytics.mydomain.com/cdn/client-script.js" site="blog.beachgeek.co.uk"></script>
```
and then just rebuild and redeploy the site. It is as simple as that. When I look at the page source for the blog, right at the bottom I can see this script has now been added:

```
<script src="https://web-analytics.mydomain.com/cdn/client-script.js" site="blog.beachgeek.co.uk"></script>
```

Now I was expecting stuff to appear straight away in my dashboard, but this was not the case. I had to wait a few minutes before I started to see data and activity appear in my dashboard. The project documentation actually breaks down the architecture, the components and how these all work together so I strongly suggest you dive deeper into that so you get comfortable with how this works.

**serverless-website-analytics in action**

So as of writing this blog post, I have been running this tool for just under 24 hours, and it is already producing me some very nice reports.

![report of 12 hours access of my blog](https://ricsuepublicresources.s3.eu-west-1.amazonaws.com/images/blog/analytics-in-action.png)

I will be running it for about a week before I look at moving to using Cognito.

**Cleaning up**

If you want to remove serverless-website-analytics, then all you need to do is run the following command (replace beachgeek-analytics with whatever you call your stack):

```
cdk destroy beachgeek-analytics
```
Which will take around 15-20 minutes to clean up all the resources.

```
cdk destroy beachgeek-analytics
Are you sure you want to delete: beachgeek-analytics (y/n)? y
beachgeek-analytics: destroying... [1/1]

 ✅  beachgeek-analytics: destroyed
```

### Conclusion

[serverless-website-analytics](https://aws-oss.beachgeek.co.uk/2yx) is a great project that solves a real problem - how to collect useful metrics from my websites. I am going to be running this over the next few months, and will update this post to include things like how much it has cost to run, the quality of the reports its produced, and more. So stay tuned folks.

Make sure you check out the project and if you like it, show your appreciation.

**Feedback**

If you have found this blog post helpful, please give me some feedback by [completing this very short survey here](https://pulse.buildon.aws/survey/D4L9Y3II).