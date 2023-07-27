---
layout: post
author: mike
categories: natas
---

### Level 1 -> 2
#### Game Instructions
> Again the instructions are basically "figure it out"

We'll do the same as last time and go to the URL with the new password and username:
```
Username: natas2
URL:      http://natas2.natas.labs.overthewire.org
```

After we log in, we're given the message: *There's nothing on this page*.

That's a pretty solid hint, but lets check out the source of the page anyway.

```html
<html>
<head>
<!-- This stuff in the header has nothing to do with the level -->
<link rel="stylesheet" type="text/css" href="http://natas.labs.overthewire.org/css/level.css">
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/jquery-ui.css" />
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/wechall.css" />
<script src="http://natas.labs.overthewire.org/js/jquery-1.9.1.js"></script>
<script src="http://natas.labs.overthewire.org/js/jquery-ui.js"></script>
<script src=http://natas.labs.overthewire.org/js/wechall-data.js></script><script src="http://natas.labs.overthewire.org/js/wechall.js"></script>
<script>var wechallinfo = { "level": "natas2", "pass": "h4ubbcXrWqsTo7GGnnUMLppXbOogfBZ7" };</script></head>
<body>
<h1>natas2</h1>
<div id="content">
There is nothing on this page
<img src="files/pixel.png">
</div>
</body></html>
```
So no passwords this time. However, there's a file called `pixel.png` that is there for seemingly no reason.

If we download `pixel.png` and open it, there's nothing. Trying to view the source yields nothing as well. Having this file does, however, let us know that there is a `files` directory on the site...

There's nothing on **this page**. However, they didn't specify the whole directory.

Let's just navigate to the directory and see what we have:

Boom! now we have access to more stuff. Listed in the directory are two files:
1. `/pixel.png`
2. `/users.txt`

Let's open up `users.txt`
```bash
# username:password
alice:BYNdCesZqW
bob:jw2ueICLvT
charlie:G5vCxkVV3m
natas3:G6ctbMJ5Nb4cbFwhpMPSvxGHhQ7I6W8Q <--
eve:zo4mJWyNj2
mallory:9urtcpzBmH
```

Password: `G6ctbMJ5Nb4cbFwhpMPSvxGHhQ7I6W8Q`

There it is! The password for the next level =)
