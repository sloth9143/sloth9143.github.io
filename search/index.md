---
layout: page
title: Search
date: 2020-01-10
comments: false
---


<form name="search" id="search-form" onsubmit="return false;">
	<div>
		<i class="icon-search"></i>
		<input type="text" name="q" autocomplete="off" style="width:100%;" />
	</div>
</form>
<script type="text/javascript" src="/assets/js/light-jekyll-search.js"></script>
<script type="text/javascript">
	lightJekyllSearch.search({
		el : document.querySelector('form[name="search"] input[name="q"]'),
		placeholder : 'input Keyword',
		postJsonPath : '/posts.json'
	});
	
	var el = document.getElementsByClassName("zoombtn")[0];
	el.style.display = "none";
</script>