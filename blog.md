---
layout: default
title: 博客
permalink: /blog/
---

<div class="blog-page">

<header class="blog-hero">
  <h1><i class="fas fa-blog"></i> 博客</h1>
  <p class="blog-subtitle">记录开发心得与日常思考</p>
</header>

<div class="post-grid">
{% for post in site.posts %}
  <a class="post-card" href="{{ post.url | relative_url }}">
    <div class="post-card-body">
      <div class="post-meta">
        <i class="far fa-calendar"></i> {{ post.date | date: "%Y年%m月%d日" }}
        {% if post.tags %}
        <span class="post-card-tags">
          {% for tag in post.tags %}<span class="pct">{{ tag }}</span>{% endfor %}
        </span>
        {% endif %}
      </div>
      <h2>{{ post.title }}</h2>
      <p>{{ post.description | default: post.excerpt | strip_html | truncate: 100 }}</p>
    </div>
    <div class="post-card-arrow">→</div>
  </a>
{% endfor %}
</div>

</div>
