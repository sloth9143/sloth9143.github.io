---
layout: page
title: Search
date: 2020-01-10
comments: false
---

<form name="search" id="search-form" onsubmit="return false;">
	<div>
		<input type="text" name="q" class="search-box" autocomplete="off" style="width:100%;" />
	</div>
</form>

<script type="text/javascript" src="/assets/js/light-jekyll-search.js"></script>
<script type="text/javascript">
	lightJekyllSearch.search({
		el : document.querySelector('form[name="search"] input[name="q"]'),
		placeholder : '검색하실 키워드를 입력해주세요',
		postJsonPath : '/posts.json'
	});
	
	var el = document.getElementsByClassName("zoombtn")[0];
	el.style.display = "none";
</script>

<style type="text/css">
.search-box {
	width: 80%;
	border: 2px solid #aaa;
	padding: 9px;
	position: relative;
	outline: 0;
	border-radius: 15px;
 }
.search-box:focus {
	box-shadow: 0 0 15px 5px #b0e0ee;
	border: 2px solid #bebede;
}
</style>
