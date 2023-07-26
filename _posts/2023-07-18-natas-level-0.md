---
layout: post
author: mike
categories: natas
---

### Level 0
#### Game Instructions
> The instruction for this is basically "figure it out". Let's get going.

They give us the password and username for this one to find the password for level 1.
```
Username: natas0
Password: natas0
URL:      http://natas0.natas.labs.overthewire.org
```
Going to the URL and entering the user/pass provided, we're presented with:

*You can find the password for the next level on this page*

This one is pretty elementary. Just right click to view the page source:
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
<script>var wechallinfo = { "level": "natas0", "pass": "natas0" };</script></head>
<body>
<h1>natas0</h1>
<div id="content">
You can find the password for the next level on this page.

<!--The password for natas1 is g9D9cREhslqBKtcA2uocGHPfMZVzeFK6 -->
</div>
</body>
</html>
```

Looking at the bottom of the page you'll see it pretty obvious

```
Password: g9D9cREhslqBKtcA2uocGHPfMZVzeFK6
```
