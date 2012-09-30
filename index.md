---
layout: default
title: Home
---
<div class="page-front">
<h1 class="title">Blog Posts</h1>

{% for post in site.posts limit: 5 %}
  <div class="post">
    <h2 class="title"><a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a></h2>
    <time datetime="{{ post.date | xmlschema }}">{{ post.date | date:"%Y/%m/%d" }}</time>
    <div class="posts">{{ post.content }}</div>
  </div>
{% endfor %}
</div>