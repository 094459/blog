---
title: 'Building a culture of security in open source software development'
date: '2020-07-15'
tags: [open source]
---

*Updated on Jan 18th to remove broken link to report*

According to a number of recent studies, the use and adoption of open source software continues to rise. From studies such as the [State of Enterprise Open Source](https://www.redhat.com/en/enterprise-open-source-report/2019) by Red Hat (in which nearly 70% of respondents stated that open source software is either extremely or very important) or TideLift’s April 2019 survey report (that found more than 90% of professional developers use open source in building their applications) it is clear that developers from startups to highly regulated enterprises have embraced open source solutions. These reports and others show that the use of open source code and components in projects is increasing.

With the increasing adoption of open source also increases the need to ensure that security remains a top priority, which means you need to think about your approach to securing your open source supply chain. 

Another recent report, [The State of Open Source Security 2020](https://snyk.io/blog/opensourcesecurity-2020survey/) by Snyk, highlights this growth in the context of open source security and how businesses are managing the security when adopting these open source technologies. Security is not only a concern for people using open source software—open source projects themselves are built on top of other open source software, and those project maintainers must ensure they address security threats as a priority to gain user trust.

The impact of not addressing security is well known. For example, Heartbleed and the Struts vulnerabilities exposed business and customer data, and the [removal of left-pad](https://www.theregister.co.uk/2016/03/23/npm_left_pad_chaos/), a small software module on NPM, had a huge impact on hundreds of applications that used this as a package upon which many other components depended. 

In this post, I explore answers to two questions: 

1. How do you prioritize security and minimize your risk when using open source software solutions?
2. How do you instill a security-first mindset when you create open source projects and software, and ensure that you are producing open source software that users can trust?

The answer to both these questions lies in culture. 

What do I mean by culture and how it applies to open source projects? I think culture boils down to three factors: 

1. A set of basic assumptions that govern day-to-day interactions and activities

2. A set of values and [corresponding behaviors](https://www.tutor2u.net/business/reference/models-of-organisational-culture-schein) and artifacts that promote and communicate the set of values and behaviors you want to achieve, and 

3. The right cultural levers to support security, which is everybody’s responsibility.

#### Setting a security-first tone

Open source projects typically focus on delivering new releases with new features for users. Project maintainers need to balance these updates and new features with ensuring that the design, implementation, and code is secure. That balance is influenced by the culture within the project and how that culture values security.

#### Start with leadership

Project leaders set the tone and priority for security,  and security must be a priority. That security focus needs to permeate throughout the community, too. For projects that are just starting out, project creators need to earn the trust of users, and showing that security matters is an important step toward gaining trust.

According to Colm MacCarthaigh in his re:Invent talk, [“It’s always day zero: Working on open source and security”] (https://www.youtube.com/watch?v=3Me_eapZ1bI) long-tenured open source projects that have earned user trust have done so because they have leaders that prioritize and champion a security-first approach. They have done this through good project stewardship and working closely with their communities.

#### Community engagement

A key element projects must address is the relationship and engagement with people outside of the project, such as users reporting issues or security researchers. There is a natural tension between the development team producing code and users reporting issues. If you do not set the right leadership example, this relationship dynamic can potentially become a hostile and adversarial situation. 

Project leaders should help build a collaborative culture in which people reporting issues are valued as project contributors and working with developers to tackle security vulnerabilities.

A couple of open source projects that apply this good practice include projects such as [Amazon Corretto Crypto Provider](https://github.com/corretto/amazon-corretto-crypto-provider), a high-performance cryptographic implementation for Java, and [s2n](https://github.com/awslabs/s2n), an implementation of the SSL/TLS network encryption protocols. Take a look at those pages and find how they provide clear guidance on reporting issues.

There are plenty of other good examples to choose from. For example, the [Apache Security notification page](https://www.apache.org/security/) and the [OpenBSD Security page](https://www.openbsd.org/security.html) are great templates for other projects to consider. These and other older, well-established open source projects and organizations have security policies have been in place for many years, and that have been refined and improved upon over time.

As well as documenting how to disclose security vulnerabilities, open source projects can also provide security documentation to ensure that security best practices are followed during implementation. There are many good examples, but  the security documentation for the [Apache httpd project](https://httpd.apache.org/docs/2.4/misc/security_tips.html) has been around a long time and is a great place to start.

There are a number of ways open source project leaders can elevate their security culture, including:

* providing transparency and governance around how security issues are reported, triaged, and then resolved;
* celebrating and highlighting contributions and fixes that identify and resolve security issues; 
* setting strong security tenets and guiding principals within projects that ensure sensible defaults such as least privilege or disabled by default are followed;
* ensuring that developers write clean and easy-to-read code; and
* mentoring community members to encourage security-first principals and best practices.

What is the security culture of open source projects you contribute to?

#### Tools matter

Tooling can also be important to help projects with potentially limited resources or less experience in identifying security issues. Tools such as [lgtm](https://lgtm.com/) provide security analysis of source code and are free for open source projects to use, and there are open source tools such as [trivy](https://github.com/aquasecurity/trivy) that also provide vulnerability scanning if you are deploying your projects on container repositories. As part of setting up your project tooling and building pipelines, you should assess what tools you could use to help improve security. 

#### Building on top of existing open source software

What about developers building on top of existing open source projects? As Amazon.com CTO Werner Vogels said in a post on security at AWS, “I'm a strong believer that in these days, security is no longer the job of the security team, or just the security team. I think security is everyone's job today. If we really want to protect our customers and our business, we all have to take responsibility for security." 

Setting up an Open Source Program Office (OSPO) is one big step toward managing open source code use within an organization. The OSPO team works with business stakeholders to define an organization’s open source strategy and the mechanisms and tools to help manage the open source supply chain. The OSPO is also fundamental in educating and promoting the right culture when using open source within an organization, and that includes security.

Because open source projects are often built on top of other open source technologies, the digital supply chain of open source software can extend to hundreds if not thousands of projects via all the dependencies. Thus, when creating or using open source software, you must understand and manage this web of dependencies. For example, when choosing open source solutions, among other considerations, you must address:

* License compliance and compatibility: Do you understand the open source licensing—and dependencies—for your solution? Are you potentially opening yourself up to a legal or compliance risk down the line?
* Assess the security culture of the open source software: If you are developing software that uses open source building blocks, you must make sure that all components have prioritized security.
* Supporting open source software: What mechanisms are in place that help you manage and support the open source software you use? Will you join, contribute to, and participate in the community? Will relay on third parties to provide project support? Or will you take another approach?

The good news is that there is now a wealth of tooling that can help you tackle these challenges throughout the application development life cycle. 

You do not have to use tooling, although it will make your life much easier. Putting together risk and assessment spreadsheets is where a lot of people begin. Make sure you set a set of criteria on which to measure the open source project and then use information repositories such as [CVE](https://cve.mitre.org/) and [OpenHub](https://www.openhub.net/) to help you complete your assessments.

#### Helping secure the open source supply chain

There are many startups and established businesses that have been helping to tackle open source software development and adoption challenges. Companies such as Black Duck, WhiteSource, and Sonatype, and startups like Meterian provide tools and expertise to help minimize legal and security risks during the application development life cycle. From ensuring developers understand open source licensing legal risks, to tracking and managing vulnerabilities throughout open source code you use (including dependencies that often make up the biggest part) to tracking and managing the open source software bill of materials that allows you to quickly identify risks and determine impact within your projects. 

One of the powerful things these tools are able to help you with is to track and mange security vulnerabilities, prioritise critical risks and help you manage the risk of using these open source components all whilst integrating as part of your CI/CD pipeline.

Other startups, such as [Huntr](https://aws.amazon.com/blogs/opensource/how-a-startup-wants-to-help-secure-the-open-source-ecosystem-with-huntr-a-bug-bounty-board/), are taking a more novel approach. Recognizing that enterprise customers want to use open source software, but want to help with the support and maintenance of open source projects they use, Huntr provides a bug bounty platform that incentivizes the resolution of security vulnerabilities and creates an environment in which open source developers and projects are paid when security issues are closed.

#### Conclusion

As you build or improve your security culture when creating or using open source software solutions, you’ll want to keep a few security-first concepts in mind, including:


1. Ensure that security is promoted as the top priority within your open source projects. Create security-minded culture by prioritizing security, adopting security policies that promote secure development practices, and having clear governance and transparency on how you manage security threats and vulnerabilities as they arise.

2. Consider how you promote and reward security within your open source project. If you do not have any clear or recent examples of how you have done this, then this may be an area of initial focus.

3. A variety of tools that help promote good security hygiene are available to open source software developers, often at no cost. Explore incorporating security-related tools into your project development processes.

4. Have mechanisms in place, for example within a dedicated Open Source Program Office team, to manage the digital supply chain of the software products you create. You will use open source software, so how you select and then manage those building blocks is critical to maintaining the highest security posture.
