---
layout: post
author: mike
series: bandit
categories: bandit 
---

### Level 9 -> 10
#### Game Instructions
> The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.

Let's `ssh` into the server
```bash
ssh -p 2220 bandit9@bandit.labs.overthewire.org
password: UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR
```

This one was more of an art than anything. I simply `cat` the contents of the `data.txt` file and searched for multiple `=` signs in a row.

Found it. `truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk`
