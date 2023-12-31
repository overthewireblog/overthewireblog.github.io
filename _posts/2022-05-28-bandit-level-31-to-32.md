---
layout: post
author: mike
series: bandit
categories: bandit 
---
### Level 31 -> 32
#### Game Instructions
> There is a git repository at ssh://bandit31-git@localhost/home/bandit31-git/repo. The password for the user bandit31-git is the same as for the user bandit31.

```
ssh -p 2220 bandit31@bandit.labs.overthewire.org
password: 47e603bb428404d265f59c42920d81e5
```
Clone the repo
`git clone ssh://bandit31-git@localhost/home/bandit31-git/repo`

Ok let's check it out
`cd repo`

We can see a sweet `README.md` in there. What does is say?
```
This time your task is to push a file to the remote repository.

Details:
    File name: key.txt
    Content: 'May I come in?'
    Branch: master
```
Right on! All we need to do is create a `key.txt` file and push it to remote ranch and we'll be good to go right?

Well they pulled a little sneaky on us and add `*.txt` to the `.gitignore` file. Which will prevent any type of `txt` file from being uploaded. No worries. We'll just remove that line from the `.gitignore` so we can upload it.

`nano .gitignore` to open the file. Once we have it open we simply delete that line and `ctrl+x` to save it and remove that pesky attribute.

Then we create a file and add the aboe text that is rerquired:
`echo "May I come in?" > key.txt`
Great! Now we've created the file so all we need to do stage it and push it
Add the files:
`git add --all`
Commit the files:
`git commit -m "I did it!!"`
Then finally push to the `master`branch
`git push -u origin master`

Bam! We did it!

Here's what we get as feedback:
```
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote:
remote: Well done! Here is the password for the next level:
remote: 56a9bf19c63d650ce78e6ec0354ee45e
remote:
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
```

Now we have our next password!
`56a9bf19c63d650ce78e6ec0354ee45e`
