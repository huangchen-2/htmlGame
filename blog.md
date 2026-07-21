---
layout: default
title: 博客
permalink: /blog/
---

# 📝 博客文章

<ul>
{% for post in site.posts %}
  <li>
    <strong>{{ post.date | date: "%Y-%m-%d" }}</strong> —
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    <br><small>{{ post.description }}</small>
  </li>
{% endfor %}
</ul>
