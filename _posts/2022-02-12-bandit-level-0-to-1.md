---
layout: post
author: mike
series: bandit
categories: bandit
---


### Level 0 -> 1
#### Game Instructions
>The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

Super simple setup here. Just `cat` the `readme` file:
```sh
cat readme

boJ9jbbUNNfktd78OOpsqOltutMc3MY1
```
Bam! Password revealed. Now let's use the password for the next level.

Password: <span class="secret">boJ9jbbUNNfktd78OOpsqOltutMc3MY1</span>
