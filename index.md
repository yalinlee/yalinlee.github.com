---
layout: page
title: Yalinlee's Blog
---
{% include JB/setup %}

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>


<section>
<h4>About me</h4>
<div>
Enjoy technology with you。<a href="/about.html">更多信息</a> 
<br/>
<br/>
<strong><font color="red"><a href="/atom.xml" target="_blank">订阅本站</a></font></strong>
<br/><br/>
联系博主：yalinlee[a]126.com
</div>
</section>

