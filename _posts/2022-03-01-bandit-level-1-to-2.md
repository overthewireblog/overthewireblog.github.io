---
layout: post
author: mike
series: bandit
categories: bandit
---

### Level 1 -> 2
#### Game Instructions
>The password for the next level is stored in a file called - located in the home directory

This level is also quite simple. The password for the next level is stored in a file named `-`. So all we have to do is `ssh` using the next level `bandit1` username and  use `cat` to read the file... right?
```sh
cat -
...
```
Nope!!! They pulled a sneaky on you. Notice that when you try this, the __command line will stall__.  

In bash, the `-` will tell the interpreter to look for a `flag`. So what we need to do here is tell the command line that `-` is a **file**. How do we do this? With `./`

State that __this current directory, look for file__:
```sh
cat ./-

CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9
```
Boom! now you have the password and you've hacked the mainframe. Now let's go to the next level.

Password: <span class="secret">CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9</span>
