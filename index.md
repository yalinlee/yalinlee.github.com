---
layout: page
title: Yalinlee's Blog
---
{% include JB/setup %}

##Latest Post
<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>



[更多文章](categories.html)