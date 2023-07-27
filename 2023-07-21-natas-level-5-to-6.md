### Level 5 -> 6
#### Game Instructions
>

Here we go logging in again:
```
Username: natas6
URL:      http://natas6.natas.labs.overthewire.org
```

Ok this one is a bit different. Now we have a form input for a *secret*. This time they are encouraging us to view the source of the page by giving us a link to do so.... Let's check it out:
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
<script>var wechallinfo = { "level": "natas6", "pass": "<censored>" };</script></head>
<body>
<h1>natas6</h1>
<div id="content">

<?

include "includes/secret.inc";

    if(array_key_exists("submit", $_POST)) {
        if($secret == $_POST['secret']) {
        print "Access granted. The password for natas7 is <censored>";
    } else {
        print "Wrong secret";
    }
    }
?>

<form method=post>
Input secret: <input name=secret><br>
<input type=submit name=submit>
</form>

<div id="viewsource"><a href="index-source.html">View sourcecode</a></div>
</div>
</body>
</html>
```
Awesome! Now we know that there's a file in `includes/secret.inc`. Let's navigate straight to it:
`http://natas6.natas.labs.overthewire.org/includes/secret.inc`
We get this sweet message:

```
<?
$secret = "FOEIUWGHFEEUHOFUOIU";
?>
```

Perfect. Let's input that into the home page and click *submit*.
That gives us the coveted password:
```
Access granted. The password for natas7 is jmxSiH3SP6Sonf8dv66ng8v1cIEdjXWr
```
Good to go! On to the next...
