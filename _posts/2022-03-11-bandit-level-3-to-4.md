---
layout: post
author: mike
series: bandit
categories: bandit 
---

### Level 3 -> 4
#### Game Instructions
>The password for the next level is stored in a hidden file in the inhere directory.

Let's get this one going the same way we have been. Using the next level up login `bandit3`
```sh
ssh -p 2220 bandit3@bandit.labs.overthewire.org
password: UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK
```
Next you'll need to navigate into the `inhere` directory:
```sh
cd inhere
```
Once inside the directory, we'll need to list all files. Now a simple `ls` to list files will return blank here. So we'll need to add the `-a` flag to show **hidden** files.
```sh
ls -a
```
Alright! Now we have a file to work with named `.hidden`

Let's `cat` the `.hidden` file to see what's inside:

```sh
cat .hidden
pIwrPrtPN36QITSp3EQaw936yaFoFgAB
```

Nice! Now we have the password for the next level!!
