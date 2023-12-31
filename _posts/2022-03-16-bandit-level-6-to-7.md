---
layout: post
author: mike
series: bandit
categories: bandit 
---

### Level 6 -> 7
#### Game Instructions
>The password for the next level is stored somewhere on the server and has all of the following properties:
owned by user bandit7
owned by group bandit6
33 bytes in size

Alrighty let's get started on this badboy.

Get `ssh`'d in there:
```bash
ssh -p 2220 bandit6@bandit.labs.overthewire.org

password: DXjZPULLxYr17uwoI01bNLQbtFemEgo7
```
Now the instructions say it is **somewhere on the server**. This means that we can't operate from the `/home` directory like we have been. Let's get to root:
```bash
cd /
```
This will get us to the root directory where we can begin...

Again, let's use `find` to search these attributes. This time, however, we're going to add all of them together for one-command awesomeness:
```bash
# This command is searching Everywhere for a file owned by group `bandit6` and user `bandit7` that will be exactly 33 bytes in size
find * -size 33c -user bandit7 -group bandit6
```
This gives us the following:
```bash
bandit6@bandit:/$ find * -size 33c -user bandit7 -group bandit6
find: ‘boot/lost+found’: Permission denied
find: ‘cgroup2/csessions’: Permission denied
find: ‘etc/ssl/private’: Permission denied
find: ‘etc/lvm/backup’: Permission denied
find: ‘etc/lvm/archive’: Permission denied
find: ‘etc/polkit-1/localauthority’: Permission denied
find: ‘home/bandit28-git’: Permission denied
find: ‘home/bandit30-git’: Permission denied
find: ‘home/bandit31-git’: Permission denied
find: ‘home/bandit5/inhere’: Permission denied
find: ‘home/bandit27-git’: Permission denied
find: ‘home/bandit29-git’: Permission denied
find: ‘lost+found’: Permission denied
find: ‘proc/tty/driver’: Permission denied
find: ‘proc/7538/task/7538/fd/6’: No such file or directory
find: ‘proc/7538/task/7538/fdinfo/6’: No such file or directory
find: ‘proc/7538/fd/5’: No such file or directory
find: ‘proc/7538/fdinfo/5’: No such file or directory
find: ‘root’: Permission denied
find: ‘run/lvm’: Permission denied
find: ‘run/screen/S-bandit15’: Permission denied
find: ‘run/screen/S-bandit12’: Permission denied
find: ‘run/screen/S-bandit5’: Permission denied
find: ‘run/screen/S-bandit17’: Permission denied
find: ‘run/screen/S-bandit7’: Permission denied
find: ‘run/screen/S-bandit13’: Permission denied
find: ‘run/screen/S-bandit11’: Permission denied
find: ‘run/screen/S-bandit9’: Permission denied
find: ‘run/screen/S-bandit27’: Permission denied
find: ‘run/screen/S-bandit25’: Permission denied
find: ‘run/screen/S-bandit2’: Permission denied
find: ‘run/screen/S-bandit16’: Permission denied
find: ‘run/screen/S-bandit20’: Permission denied
find: ‘run/screen/S-bandit30’: Permission denied
find: ‘run/screen/S-bandit14’: Permission denied
find: ‘run/screen/S-bandit31’: Permission denied
find: ‘run/screen/S-bandit8’: Permission denied
find: ‘run/screen/S-bandit4’: Permission denied
find: ‘run/screen/S-bandit29’: Permission denied
find: ‘run/screen/S-bandit28’: Permission denied
find: ‘run/screen/S-bandit21’: Permission denied
find: ‘run/screen/S-bandit26’: Permission denied
find: ‘run/screen/S-bandit24’: Permission denied
find: ‘run/screen/S-bandit22’: Permission denied
find: ‘run/screen/S-bandit1’: Permission denied
find: ‘run/screen/S-bandit19’: Permission denied
find: ‘run/screen/S-bandit23’: Permission denied
find: ‘run/shm’: Permission denied
find: ‘run/lock/lvm’: Permission denied
find: ‘sys/fs/pstore’: Permission denied
find: ‘tmp’: Permission denied
find: ‘var/spool/bandit24’: Permission denied
find: ‘var/spool/rsyslog’: Permission denied
find: ‘var/spool/cron/crontabs’: Permission denied
find: ‘var/log’: Permission denied
find: ‘var/tmp’: Permission denied
find: ‘var/cache/ldconfig’: Permission denied
find: ‘var/cache/apt/archives/partial’: Permission denied
var/lib/dpkg/info/bandit7.password ## <----------------------Only file we can access
find: ‘var/lib/apt/lists/partial’: Permission denied
find: ‘var/lib/polkit-1’: Permission denied
```
Notice the large list of *permission denied* results?

This game made it a little easy for us this time. The only file we can access is
`var/lib/dpkg/info/bandit7.password`
So let's `cat` that file and bam! Password.
```bash
password: HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs
```
