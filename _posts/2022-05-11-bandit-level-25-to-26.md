---
layout: post
author: mike
series: bandit
categories: bandit 
---
### Level 25 -> 26
#### Game Instructions
> Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not /bin/bash, but something else. Find out what it is, how it works and how to break out of it.

Let's get started:
```
ssh -p 2220 bandit25@bandit.labs.overthewire.org
password: uNG9O58gUE7snukf3bvZ0rxhtnjzSGzG
```

So here we need to figure out what type of shell **bandit26** is using.

First, we'll check the `passwd` file for `bandit26`
`cat /etc/passwd | grep bandit26`
We get
`bandit26:x:11026:11026:bandit level 26:/home/bandit26:/usr/bin/showtext`
So no let's `grep` the file we're shown
`cat /usr/bin/showtext`
This gives us
```sh
#!/bin/sh
export TERM=linux
more ~/text.txt
exit 0
```
So now we know he's using `#1/bin/sh`

Then we need to figure out how it works and how to break out of it.

This works by using the `sshkey.private` that is provided in the `home` directory. However, you'll notice that the shell immediately closes out. So let's take a look at the above pulled shell config... Notice the `more ~/text.txt`. It's using `more` to view the file so we'll use that to break in.

No `more` will show one page of data at a time. So what happens if the window is just a **bit too small**? It won't close. This will allow us to use `vim` to break out an gain a shell.

Make the terminal window super tiny (less than 6 lines) and try to get back in using `ssh -i sshkey.private bandit26@localhost`. You'll notice it hangs (Yay!).

Now hit `v` to bring up command options in `vim`. Type:
`:e /etc/bandit_pass/bandit26`

Now we have it!

`5czgV9L3Xx8JPOyRbXh6lQbmIOWvPT6Z`

**Don't close the terminal we need the same shell to finish the next level!!**
