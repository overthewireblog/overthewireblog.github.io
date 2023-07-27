---
layout: post
author: mike
categories: natas
---

### Level 2 -> 3
#### Game Instructions
>

First let's get logged in at the new URL:
```
Username: natas3
URL:      http://natas3.natas.labs.overthewire.org
```
Again they give us the *There's nothing on this page*. Let's check the source code anyway:
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
<script>var wechallinfo = { "level": "natas3", "pass": "G6ctbMJ5Nb4cbFwhpMPSvxGHhQ7I6W8Q" };</script></head>
<body>
<h1>natas3</h1>
<div id="content">
There is nothing on this page
<!-- No more information leaks!! Not even Google will find it this time... -->
</div>
</body></html>
```

Here we see the message
>"No more information leaks!! Not even Google will find it this tim..."

Interesting statement. Google can't find it. Then it must be in the `robots.txt` file...

Let's go to it and see:
`http://natas3.natas.labs.overthewire.org/robots.txt`

And not we see this:

```
User-agent: *
Disallow: /s3cr3t/
```

Looks like there is a directory called `/s3cr3t/`. No way this could have anything in it :o

Lets check it out by navigating straight to it:
`http://natas3.natas.labs.overthewire.org/s3cr3t/`

Yay! Another `users.txt` file. What's in it?
```
natas4:tKOcJIbzM4lTs8hbCmzn5Zr4434fGZQm
```
The password of course! Alright let's get going to the next one...
