---
layout: post
author: mike
series: bandit
categories: bandit 
---

### Level 2 -> 3
#### Game Instructions
>The password for the next level is stored in a file called spaces in this filename located in the home directory

First, let's login using the previous password and the next login of `bandit2`:
```sh
ssh -p 2220 bandit2@bandit.labs.overthewire.org
password: CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9
```
So this one is fairly simple. You just need to understand how spaces `" "` work on the command line. If you just simply run `cat spaces in this filename`, you'll get This

```sh
cat: spaces: No such file or directory
cat: in: No such file or directory
cat: this: No such file or directory
cat: filename: No such file or directory
```
This is because separating by **spaces** will always look for another file. Basically you're asking `cat` to look for **4** different files. So we need to **escape** the **spaces**.  

There are two options here:
1. We can escape each space
`cat spaces\ in\ this\ filename`... escaping each space OR;
2. We can encapsulate the entire string in `" "`
`cat "spaces in this filename"`

Either one will make sure that `cat` treats the whole string as one file name... giving you the next password in the series:
```
UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK
```
