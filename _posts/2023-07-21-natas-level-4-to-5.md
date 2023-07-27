---
layout: post
author: mike
categories: natas
---


### Level 4 -> 5
#### Game Instructions
>

We know the routine. Let's get signed in at the next exercise:
```
Username: natas5
URL:      http://natas5.natas.labs.overthewire.org
```
Sweet... we get this message
> Access disallowed. You are not logged in.

Nice. That makes no sense. Let's look at the source code:
```html
<html>
<head>
    <!-- This stuff in the header has nothing to do with the level -->
    <link rel="stylesheet" type="text/css" href="http://natas.labs.overthewire.org/css/level.css">
    <link rel="stylesheet" href="http://natas.labs.overthewire.org/css/jquery-ui.css"/>
    <link rel="stylesheet" href="http://natas.labs.overthewire.org/css/wechall.css"/>
    <script src="http://natas.labs.overthewire.org/js/jquery-1.9.1.js"></script>
    <script src="http://natas.labs.overthewire.org/js/jquery-ui.js"></script>
    <script src=http://natas.labs.overthewire.org/js/wechall-data.js></script>
    <script src="http://natas.labs.overthewire.org/js/wechall.js"></script>
    <script>
    var wechallinfo = {
        "level": "natas5",
        "pass": "Z0NsrtIkJoKALBCLi5eqFfcRN82Au2oD"
    };
    </script>
</head>
<body>
    <h1>natas5</h1>
    <div id="content">
    Access disallowed. You are not logged in</div>
</body>
</html>
```
Hmmm. Nothing I can see. The message says *Not logged in*, so it must have something to do with the `session`. Let's check our cookies and find the one that syas `http://natas5.natas.labs.overthewire.org`and set the `0` to a `1`.

Now refresh the page and BAM!
>Access granted. The password for natas6 is fOIvE0MDtPTgRhqmmvvAOt2EfXR6uQgR

Now we have the password for the next level:
`fOIvE0MDtPTgRhqmmvvAOt2EfXR6uQgR`

Let get to it...
