---
layout: post
author: mike
series: bandit
categories: bandit 
---

### Level 13 -> 14
#### Game Instructions
> The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Note: localhost is a hostname that refers to the machine you are working on

As usual, we start by `ssh`ing into the machine
```bash
ssh -p 2220 bandit12@bandit.labs.overthewire.org
password: 8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL
```
Here they gave us a sweet sweet `sshkey.private` ssh key which is basically like leaving us a key under the rug.

`ssh -i sshkey.private bandit14@localhost` logs us right into the system as **bandit14** and bam, we're in.

Not just a simple `cat /etc/bandit_pass/bandit14` gives us the next pwd.

`4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e`
