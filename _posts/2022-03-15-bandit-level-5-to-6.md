---
layout: post
author: mike
series: bandit
categories: bandit 
---
### Level 5 -> 6
#### Game Instructions
>The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:
human-readable
1033 bytes in size
not executable

So we're looking for a file that is:
- Human readable
- 1033 bytes in size
- Non-executable

Let's get logged in:
```bash
ssh -p 2220 bandit5@bandit.labs.overthewire.org

password: koReBOKuIDDepwhWk7jZC0RTdopnAYKh
```
There are obviously a few ways that we can tackle this one. The one that sticks out to me is the **1033 byte** file size.
This is very easy to search with `find`. And if we do happen to have a lot of files that are 1033 bytes in size, we'll further refine with the other criteria.

So let's use `find` and get this party started:
```bash
# Find in *Everywhere* and print all files 1033 bytes in size
find * -size 1033c -print
```
This gives us:
```bash
maybehere07/.file2
```
We found it! No need to further filter as it's the only file that is 1033 bytes.

Now let's just read the file and get the password:
```bash
cat maybehere07/.file2

password: DXjZPULLxYr17uwoI01bNLQbtFemEgo7
```
Bam! Now we have the password for the next game!
