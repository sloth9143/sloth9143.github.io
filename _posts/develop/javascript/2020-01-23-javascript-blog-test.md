---
layout: post
title:  "[jQuery] 눈 내리는 효과(Snowfall) 적용하기"
date:   2020-01-23
excerpt: "해당 글은 github에 있는 Snowfall이라는 jQuery 기반 플러그인을 활용하였습니다."
javascript: true
tag:
- javascript
- jQuery
- Snowfall
feature: https://sloth9143.github.io/assets/img/back01.png
comments: true
---

<br/>

* 해당 글은 github에 있는 <strong>Snowfall</strong>이라는 jQuery 기반 플러그인을 활용하였습니다.

<br/>

---

## 추가해야 할 파일

{% highlight scrt %}
 - jquery.js
 - snowfall.jquery.js
 - snowfall.js
{% endhighlight %}

*  해당 js파일은 [https://github.com/loktar00/JQuery-Snowfall](https://github.com/loktar00/JQuery-Snowfall)에서 다운로드 받을 수 있습니다.
*  기존 사용하는 jquery.js 파일이 있을 경우, 추가 선언하지 않아도 됩니다.

<br/>

---

## 소스 코드

{% highlight scrt %}
    <!-- javascript 선언 -->
    <script tyle="text/javascript" src="js/jquery.js"></script>
    <script tyle="text/javascript" src="js/snowfall.jquery.js"></script>
    <script tyle="text/javascript" src="js/snowfall.js"></script> 

    <script tyle="text/javascript">
        <!-- 페이지 호출 시 실행 -->
        $(document).ready(function(){
            $(document).snowfall({
                image :"img/flake.png", 
                minSize: 3, 
                maxSize:10, 
                flakeCount : 120
            });
        });
    </script>
{% endhighlight %}

* 페이지 상단 해당 스크립트를 선언하게 되면, 페이지에 효과가 적용됩니다.
* image, minSize, maxSize, flakeCount 등 그 외 옵션들을 통해 이벤트 조작이 가능합니다. 그 외 옵션들의 경우는 
[https://github.com/loktar00/JQuery-Snowfall](https://github.com/loktar00/JQuery-Snowfall)에서 참고하시길 바랍니다.