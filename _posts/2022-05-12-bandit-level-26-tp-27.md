---
layout: post
author: mike
series: bandit
categories: bandit 
---

### Level 26 -> 27
#### Game Instructions
>Good job getting a shell! Now hurry and grab the password for bandit27!

Ok now this is easy if we keep the same terminal open from the last time. All we are going to do is use the power of `vim` to execute a couple of simple shell commands.

Go back to the command area of `vim` and type in
`:set shell=/bin/bash` Note: you won't see confirmation
Now type `:shell` and you should be good to go!

Now navigate to `~` and use the `bandit27-do` file to `cat` as `bandit27`

`./bandit27-do cat /etc/bandit_pass/bandit27`

Boom. Done.

`3ba3118a22e93127a4ed485be72ef5ea`
