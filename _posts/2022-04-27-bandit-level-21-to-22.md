---
layout: post
author: mike
series: bandit
categories: bandit 
---

### Level 21 -> 22
#### Game Instructions
> A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

Get into the remote machine:
```
ssh -p 2220 bandit21@bandit.labs.overthewire.org
password: gE269g2h3mw3pwgrj0Ha9Uoqen1c9DGr
```

Looking into the direcory of /etc/cron.d we see a few differenct cronjobs. Let's `cat` the `cronjob_bandit22` file and see what's up
```
@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
* * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
```

Now we know where the `sh` file is we can cat that as well for more information:

`cat /usr/bin/cronjob_bandit22.sh`

This give us the source code of the `sh` file:
```
#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
```

Once more, let's just `cat` the file in `/tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv`

`cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv`

Now we have our next password! Woop!

`Yk7owGAcWjwMVRwrTesJEwB7WVOiILLI`
