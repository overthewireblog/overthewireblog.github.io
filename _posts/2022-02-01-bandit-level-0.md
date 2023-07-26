---
layout: post
author: mike
series: bandit
categories: bandit
---

### Level 0
#### Game Instructions
>The goal of this level is for you to log into the game using SSH. The host to which you need to connect is ```bandit.labs.overthewire.org```, on ```port 2220```. The username is bandit0 and the password is bandit0. Once logged in, go to the Level 1 page to find out how to beat Level 1.

This level is the most basic of levels. It simply needs you to `ssh` into the game.
You'll need the login credentials (obviously):
```sh
username: bandit0
password: bandit0
```
All we have to do here is `ssh` into the WarGames.
We do this by using the `ssh` command with the `-p` flag on the port `2220` and the `bandit0` username:
```sh
ssh -p 2220 bandit0@bandit.labs.overthewire.org
```
Then just use the password `bandit0` when prompted.

That's it! You're on your way to being a hacker!
