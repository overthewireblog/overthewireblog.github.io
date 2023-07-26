---
layout: post
author: mike
series: bandit
categories: bandit 
---


### Level 17 -> 18
#### Game Instructions
> There are 2 files in the homedirectory: passwords.old and passwords.new. The password for the next level is in passwords.new and is the only line that has been changed between passwords.old and passwords.new

> NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19

First we create a key from the information from the last level in `/tmp/bandit17/`

now we just `nano` `bandit17.key` and paste in the information.

This part was frustrating for me and took me a while. You need to set permissions on the file or it won't take.

`chmod 600 bandit17.key`

Then we can just used the command we used in a previous level to use that key without a password:

`ssh -i bandit17.key bandit17@localhost` Bam... we're in.

Now we need to `diff` these files `passwords.new` and `passwords.old` to see what the difference is.

There's only 2 options and this is the one:
`kfBf3eYk5BPBRzwjqutbbfE887SVc5Yd`
