---
layout: post
author: mike
series: bandit
categories: bandit 
---

### Level 4 -> 5
#### Game Instructions
>The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.

Let's go ahead and login with the next level `bandit4`
```sh
ssh -p 2220 bandit4@bandit.labs.overthewire.org
password: pIwrPrtPN36QITSp3EQaw936yaFoFgAB
```

By the instructions of the game, let's go ahead and execute the `reset` command. Just to clear things up.

Now the game is telling us that we need to find the only **human-readable** file in the `inhere` directory.

Let's `cd` into the `inhere` directory to get to work:
```bash
cd inhere
```
When we `ls` this directory, we'll see a bunch of files starting with that pesky `-` that we came across earlier. So we know that we're going to have to use `./` to `cat` them effectively.

This particular exercise is best tackled manually. We'll simply `cat` each file and look for **human-readable** text:

```bash
cat ./-file00 ./-file01 ./-file02 ./-file03 ./-file04 ./-file05 ./-file06 ./-file07 ./-file08 ./-file09
```
```
??????????~%	C[?걱>??| ????U"7?w???H??ê?Q??(???#????T?v??(?ִ?????A*?
2J?Ş؇_?y7?.A??u??#???w$N?c?-??Db3??=???=<?W?????ht?Z??!??{?U    ?+??pm???;??:D??^??@?gl?Q??@?%@???ZP*E??1?V???̫*????
koReBOKuIDDepwhWk7jZC0RTdopnAYKh
FPn?  '?U???M??/u XS
?mu?z???хN?{??Y?d4????]3?????9(?
```

Do you see the human-readable text? Yep! That's right:

`koReBOKuIDDepwhWk7jZC0RTdopnAYKh`

Now we have the password for `bandit5`
