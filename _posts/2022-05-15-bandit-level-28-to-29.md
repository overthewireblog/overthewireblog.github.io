---
layout: post
author: mike
series: bandit
categories: bandit 
---
### Level 28 -> 29
#### Game Instructions
>There is a git repository at ssh://bandit28-git@localhost/home/bandit28-git/repo. The password for the user bandit28-git is the same as for the user bandit28.

I'm going to stay in the same shell as the last exercise for this one and just clone the repo.

If you closed out, however, just login with bandit28
```
ssh -p 2220 bandit28@bandit.labs.overthewire.org
password: 0ef186ac70e04ea33b4c1853d2526fa2
```
`git clone ssh://bandit28-git@localhost/home/bandit28-git/repo repo2` * You may notice I've add a **repo2** to specify folder. I don't want to get confused between the last repo and this one.
Password is `0ef186ac70e04ea33b4c1853d2526fa2`
`cd` into `repo2` and let's have a look.

Another `README.md` but with no information inside. Knowing that this is `git` and well, the whole point is version control and managing various commits, etc. Let's check the changes to the repo.

`git log`
```sh
bandit27@bandit:/tmp/repo12/repo2$ git log
commit edd935d60906b33f0619605abd1689808ccdd5ee
Author: Morla Porla <morla@overthewire.org>
Date:   Thu May 7 20:14:49 2020 +0200

   fix info leak

commit c086d11a00c0648d095d04c089786efef5e01264
Author: Morla Porla <morla@overthewire.org>
Date:   Thu May 7 20:14:49 2020 +0200

   add missing data

commit de2ebe2d5fd1598cd547f4d56247e053be3fdc38
Author: Ben Dover <noone@overthewire.org>
Date:   Thu May 7 20:14:49 2020 +0200

   initial commit of README.md
```
Looks like they patched an "info leak", so let's check that commit history:

`git log -p`
```sh
- username: bandit29
-- password: bbc96594b4e001778eee9975372716b2
+- password: xxxxxxxxxx
```
There we go we have the next password:
`bbc96594b4e001778eee9975372716b2`
