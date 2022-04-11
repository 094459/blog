---
title: 'Long running data import jobs with AWS Session Manager'
date: '2020-09-10'
tags: [AWS Session Manager, TPC-H, Amazon Aurora]
---
Yesterday I was looking to import the TPC-H dataset (some 600 or so million rows) into Amazon Aurora from a workstation that I connect to using AWS Session Manager.

[AWS Session Manager](https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager.html) is a great way to simplify your life by allowing you to connect to a machine via the AWS console and not worry about having to manage ssh keys or remembering to lock down external public access from the net. I find myself using this when I need to do sysadmin-y things, and just makes managing your bastion hosts just that bit simpler.

One of the things I have been doing this past week is using this to to benchmarking on Amazon Aurora, and part of that means importing/bulk loading a small amount of data (ok, well over 800 million rows). I encountered an issue in that the sessions terminate after 20 mins, and I didn't really want to babysit the sessions to keep 'tickling' the session open.

Given it was Linux running under the covers, I decided to try a few tricks from the past that had served me well during my days working on Solaris systems.

My plan was to kick the process off and then move it to the background. I fiddled with using & to kick it off as a background task, and then used nohup to make sure the terminal session would not kill the process, but neither of these approaches worked. I did find a neat solution to this on [StackOverflow](https://stackoverflow.com/questions/30224105/running-a-sql-query-in-the-background-using-mysql) which I used as the basis of my solution.

> I use environment variables to hold values such as the DB host, username and password just in case you wonder what the $ values below are. Substitute your own.

I connected to Amazon Aurora using the mysql client and initiated the load. 

```
LOAD DATA LOCAL INFILE '/data/part.tbl' INTO TABLE PART FIELDS TERMINATED BY '|';
```
Once this was running, I hit CTRL and Z which then suspended the process. You should see something like:

```
mysql >
[1]+ Stopped   mysql -h$DBHOST -u$DBUSER -p"$DBPASS"
```
I then used the **bg** command to move it to the background.

```
$ > bg
[1]+ Stopped mysql -h$DBHOST -u$DBUSER -p"$DBPASS" &
```
You should see the trailing & meaning it has now been woken up and is running, just in the background. Which you can confirm using the jobs command:

```
$ > jobs
[1]+ Stopped mysql -h$DBHOST -u$DBUSER -p"$DBPASS"
```

Next, I used ps -ef | grep mysql to check the running processes. Not sure why this was necessary, I just wanted to make sure I could see the process, what the PID was and check throughout that I hadn't harmed it.

You can also start another instance of the mysql client and from mysql it should display your mysql connection/process.

```
mysql > show full processlist;
```

From here you can now use the disown command to detach the PID from this shell. This is important as when the shell times out, it will take everything it owns with it.

```
$> disown -h %1
```

And that is it. I left it running overnight, and when I woke up, all 600 millions rows had imported correctly, taking a little under 5 hours to do so.

That saved me from a lot of tickling.


### Footnote

Of course, this was just a challenge to see if I could do it. The post mortem I had with myself over breakfast was that it would have been way smarter to:

1. Generate an ssh key-pair, extract the public key (ssh-keygen -y -f {key})
2. Start a session with the instance and add this public key to the ~/.ssh/authorized_keys file
3. Change the security group to add a new inbound rule for ssh for just my IP address and to just this instance
4. Remove the inbound rule once the work has been done

This took me all of about 5 minutes to do, so if you are looking to do this, I suggest the faster path.

###

How would you have improved on this? Is there a better way - I am sure there is, and I would love to know how this could be made simpler without sacrificing security.






