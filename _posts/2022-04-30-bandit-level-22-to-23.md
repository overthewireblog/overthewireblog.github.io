---
layout: post
author: mike
series: bandit
categories: bandit 
---
### Level 22 -> 23
#### Game Instructions
> A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

> NOTE: Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.

Let's start by getting into the new games
```
ssh -p 2220 bandit22@bandit.labs.overthewire.org
password: Yk7owGAcWjwMVRwrTesJEwB7WVOiILLI
```

Now we have another cronjob to look into.

Start by `cd`ing into the `/etc/cron.d` directory for the next level **bandit23**

`cd /etc/cron.d`

Then `cat` to get some more info.

`cat cronjob_bandit23`
And we get:
```
@reboot bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
* * * * * bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
```
Now let's see what's in that file:
`cat /usr/bin/cronjob_bandit23.sh`
And we get:
```bash
#!/bin/bash
myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"

cat /etc/bandit_pass/$myname > /tmp/$mytarget
```
So we see a pretty simple bash script. Now what are these variables? The script tells us:
`myname=$whoami` - we can simply run `whoami` to get the value of `bandit22`
`mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)` - Let's just run this string with the peice we know of - `$myname` (but use **bandit23** which is the next level)
`echo I am user bandit23 | md5sum | cut -d ' ' -f 1`
And we get:
`8ca319486bfbbc3663ea0fbe81326349`
Now we know what file will be in the `tmp` directory with the password dump:
`/tmp/8ca319486bfbbc3663ea0fbe81326349` let's `cat` that file:
`cat /tmp/8ca319486bfbbc3663ea0fbe81326349` and bam... password
`jc1udXuA1tiHqjIsL8yaapX5XIAI6i0n`
