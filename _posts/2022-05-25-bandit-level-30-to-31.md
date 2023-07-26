---
layout: post
author: mike
series: bandit
categories: bandit 
---
### Level 30 -> 31
#### Game Instructions
> There is a git repository at ssh://bandit30-git@localhost/home/bandit30-git/repo. The password for the user bandit30-git is the same as for the user bandit30.

> Clone the repository and find the password for the next level.

Let's get started by `ssh`ing in.
```
ssh -p 2220 bandit30@bandit.labs.overthewire.org
password: 5b90576bedb2cc04c86a9e924ce42faf
```
Now let's clone that repo
`git clone ssh://bandit30-git@localhost/home/bandit30-git/repo`

`cd` in to see what's up...

Just an empty README.md

So we check `git` logs for version history... nothing.
What about other `branches`? Nope... nothing
So if we dig into git's `tagging` feature, we can see there is one called `secret`
`git show secret` gives us our password:
`47e603bb428404d265f59c42920d81e5`
