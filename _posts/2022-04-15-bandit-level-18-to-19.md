---
layout: post
author: mike
series: bandit
categories: bandit 
---

### Level 18 -> 19
#### Game instructions
> The password for the next level is stored in a file readme in the homedirectory. Unfortunately, someone has modified .bashrc to log you out when you log in with SSH.

When we put in the password, as mentioned above, we are successfully logged in -- only to be logged out immediately. However, they've let us know that there is a `readme` file in the home directory. So what if we can attach a `cat` command to scoop the password before we are logged out?

`ssh -p 2220 bandit18@bandit.labs.overthewire.org "cat ~/readme"`

This will let us get that password before we get kicked out. Password for `bandit19`

`IueksS7Ubh8G3DCwVzrTd8rAVOwq3M5x`
