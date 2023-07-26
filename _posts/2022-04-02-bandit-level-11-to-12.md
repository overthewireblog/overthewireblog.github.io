---
layout: post
author: mike
series: bandit
categories: bandit 
---

### Level 11 -> 12
#### Game Instructions
> The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

`ssh` into the server
```bash
ssh -p 2220 bandit11@bandit.labs.overthewire.org
password: IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR
```
When we `cat` the `data.txt` file, we get this jumble:
`Gur cnffjbeq vf 5Gr8L4qetPEsPk8htqjhRK8XSP6x2RHh`

Based off of the game description. We know it is just rotated text 13 times. (Look up **rot13**)

Here we'll use `tr` to reverse the rot13 "encryption". A primitive form of letter scrambling (not secure).

`cat data.txt | tr 'n-za-mN-ZA-M' 'a-zA-Z'`

Now we get a print of:
`The password is 5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu`

All set for the next level.
