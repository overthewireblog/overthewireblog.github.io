---
layout: post
author: mike
series: bandit
categories: bandit 
---
### Level 8 -> 9
#### Game Instructions
>The password for the next level is stored in the file data.txt and is the only line of text that occurs only once

Let's `ssh` into the next game:
```bash
ssh -p 2220 bandit8@bandit.labs.overthewire.org
password: cvX2JJa4CFALtqS87jk27qwqGhBM9plV
```
This one seems more difficult but really isn't... Let's see what we need to do to find this file:
1. We need to `sort` all of the lines in the file
2. We then need to find out which one of these lines is *unique*

We'll use something called **Piping** `|` here.

```bash
sort data.txt | uniq -u
```
The above like uses the `sort` command to sort all lines, then uses `uniq` with the flag `-u` to find the only unique line.
```bash
password: UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR
```
Done and done... we just found that password... no big deal.
