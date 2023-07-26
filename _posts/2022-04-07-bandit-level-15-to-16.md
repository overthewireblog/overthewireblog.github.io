---
layout: post
author: mike
series: bandit
categories: bandit 
---

### Level 15 -> 16
#### Game Instructions
> The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL encryption.

> Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…

Similar to the last exercise, we don't log in to the game with `ssl` but rather send the previous passphrase through a port. This time it requires **SSL** so we'll be using OpenSSL to send it through to port **30001**

`openssl s_client -connect localhost:30001`

Now we can paste in `BfMYroe26WYalil77FoDi9qh59eK5xNr`and we've got the next key:
`cluFn7wTiGryunymYOu4RcffSxQluehd`
