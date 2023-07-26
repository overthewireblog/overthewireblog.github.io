---
layout: post
author: mike
series: bandit
categories: bandit 
---

### Level 10 -> 11
#### Game Instructions
> The password for the next level is stored in the file data.txt, which contains base64 encoded data

`ssh` into the server
```bash
ssh -p 2220 bandit10@bandit.labs.overthewire.org
password: truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk
```

Since they gave us a solid clue by mentioning the **base64** encoding, this one was pretty easy.

`cat data.txt | base64` and we get:
The password is `IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR`

Sweet.
