---
layout: default
title: Search
---

Powered by <a href="/blog/2016/01/04/how-to-make-lunrjs-jekyll-work-together/">lunr.js</a>.

<br/>&nbsp;
<div class="container">
<form action="get" id="site_search">
<center>
  <input style="font-size:20px;" type="text" id="search_box">
  <input style="font-size:20px;" type="submit" value="Go!">
</center>
</form>
<br/>&nbsp;
<br/>&nbsp;

<ul id="search_results"></ul>
</div>



<!-- <script src="/js/lunr.min.js"></script> -->
<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.3/jquery.min.js"></script>
<script src="https://unpkg.com/lunr/lunr.js"></script>
<script src="/assets/js/search.js"></script>
