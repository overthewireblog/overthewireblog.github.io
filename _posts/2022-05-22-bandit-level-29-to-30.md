---
layout: post
author: mike
series: bandit
categories: bandit 
---

### Level 29 -> 30
#### Game Instructions
> There is a git repository at ssh://bandit29-git@localhost/home/bandit29-git/repo. The password for the user bandit29-git is the same as for the user bandit29.

Login as `bandit29`
```
ssh -p 2220 bandit29@bandit.labs.overthewire.org
password: bbc96594b4e001778eee9975372716b2
```
Clone the repo to whatever temp directory you choose.

`git clone ssh://bandit29-git@localhost/home/bandit29-git/repo`

Now `cd` into it to take a look  around.

There's a `README` file in there but nothing to go off of. Let's check versions and commit history like before:

`git log -p`

Nothing shows up. There must be some `branches` handing around somewhere either local or remote. Let's list all remote and local branches:
`git branch -a`
We see a couple of them. Let's switch to the `dev` branch to see if we get anything.
`git checkout dev`
Ok let's check this README. Woo! First try:
```
Some notes for bandit30 of bandit.
## credentials
- username: bandit30
- password: 5b90576bedb2cc04c86a9e924ce42faf
```

We now have the password for `bandit30`. On to the next!
