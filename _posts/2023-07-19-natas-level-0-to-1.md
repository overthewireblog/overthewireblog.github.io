---
layout: post
author: mike
categories: natas
---


### Level 0 -> 1
#### Game Instructions
> Figure it out

Let's go to our next level and use the password we just got:
```
Username: natas1
URL:      http://natas1.natas.labs.overthewire.org
```

This one they blocked the **right-click** ability. So we'll just use a keyboard shortcut to open up **inspector**

On Safari it's `CMD+Opt+U` but any browser has one.

Now we can see the code:
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
<script>var wechallinfo = { "level": "natas1", "pass": "g9D9cREhslqBKtcA2uocGHPfMZVzeFK6" };</script></head>
<body oncontextmenu="javascript:alert('right clicking has been blocked!');return false;">
<h1>natas1</h1>
<div id="content">
You can find the password for the
next level on this page, but rightclicking has been blocked!

<!--The password for natas2 is h4ubbcXrWqsTo7GGnnUMLppXbOogfBZ7 -->
</div>
</body>
</html>
```
Just like last time, the password is in the source at the bottom.

Password:
`h4ubbcXrWqsTo7GGnnUMLppXbOogfBZ7`

Boom. Now let's get to the next one.
