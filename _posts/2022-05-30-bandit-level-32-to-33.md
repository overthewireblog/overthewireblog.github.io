---
layout: post
author: mike
series: bandit
categories: bandit 
---

### Level 32 -> 33
#### Game Instructions
> After all this git stuff its time for another escape. Good luck!

Let's get to it!
```
ssh -p 2220 bandit32@bandit.labs.overthewire.org
password: 56a9bf19c63d650ce78e6ec0354ee45e
```

This one took a bit for me to figure out. Actually, I didn't really know what I was doing. I just tinkered, tried the usual `ls` `cd` commands, etc. Then I went to just check what kind of shell I was using...

`$0` and what do you know... A wild bash shell appeared! Now that I was in bash I just `ls` the directory and ran `cat` on the final `bandit33` file:
```
Congratulations on solving the last level of this game!

At this moment, there are no more levels to play in this game. However, we are constantly working
on new levels and will most likely expand this game with more levels soon.
Keep an eye out for an announcement on our usual communication channels!
In the meantime, you could play some of our other wargames.
```

That's it. Hopefully they add some more soon!
