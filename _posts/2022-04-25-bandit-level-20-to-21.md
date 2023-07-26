---
layout: post
author: mike
series: bandit
categories: bandit 
---

### Level 20 -> 21
#### Game Instructions
> There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

First we send the string of the last password to a TCP server running on a port of our choice (in this exampe **61137**).
`echo "GbKksEFF4yrVs6il55v6gwY5aVje5f0j" | nc -l localhost -p 61137 &`

Then we check to make sure it's working

`ps aux`

```USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
bandit20   658  0.0  0.1  21148  5144 pts/54   Ss   17:22   0:00 -bash
bandit20  1103  0.0  0.1  21148  4860 pts/35   Ss+  16:36   0:00 -bash
bandit20  1157  0.0  0.0   6300  1584 pts/39   S+   16:36   0:00 nc -l localhost
bandit20  1523  0.0  0.0   6300  1660 pts/54   S    17:24   0:00 nc -l localhost
bandit20  1696  0.0  0.0  19188  2372 pts/54   R+   17:24   0:00 ps aux
bandit20 31119  0.0  0.1  21148  4968 pts/39   Ss   16:32   0:00 -bash
```

We can see that it is running on process ID **1523**

No we can run the binary to ask the server to send us the next one:

`./suconnect 61137`

Next password:
`gE269g2h3mw3pwgrj0Ha9Uoqen1c9DGr`
