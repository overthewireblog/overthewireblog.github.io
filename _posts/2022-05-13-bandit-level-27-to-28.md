---
layout: post
author: mike
series: bandit
categories: bandit 
---

### Level 27-28
#### Game Instructions
> There is a git repository at ssh://bandit27-git@localhost/home/bandit27-git/repo. The password for the user bandit27-git is the same as for the user bandit27.

>Clone the repository and find the password for the next level.

Start it up:
```
ssh -p 2220 bandit27@bandit.labs.overthewire.org
password: 3ba3118a22e93127a4ed485be72ef5ea
```
Clone the **repo**
`git clone ssh://bandit27-git@localhost/home/bandit27-git/repo`
**Note** the password is the same for the `git` cloning as for the `ssh` login.
Ok now we have our repo so we `cd repo` to get into the directory and there's only one file `REAMDE`
Super easy just `cat` the file and there's the password:
`0ef186ac70e04ea33b4c1853d2526fa2`
