---
layout: post
author: mike
series: bandit1
categories: bandit 
---

### Level 7 -> 8
#### Game Instructions
>The password for the next level is stored in the file data.txt next to the word millionth

Oooo... now it's time for some sleuthing. We need to read the `data.txt` file and find the word "millionth".

First things first, let's `ssh` into that server:
```bash
ssh -p 2220 bandit7@bandit.labs.overthewire.org
password: HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs
```
Now if we `ls` to see the current directory, we'll see a single file named `data.txt`. Lets use `grep` to search the file for "millionth"
```bash
grep "millionth" data.txt
```
This will give us:
```bash
millionth	cvX2JJa4CFALtqS87jk27qwqGhBM9plV
```
Yay! That one was pretty easy.
