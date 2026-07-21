---
layout: default
title: 博客
permalink: /blog/
---

<nav class="top-nav">
  <span>
    <a href="/"><i class="fas fa-home"></i> 首页</a>
  </span>
  <span class="live-clock" id="live-clock"></span>
</nav>

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

<script>
(function updateClock(){
  var now=new Date();
  var s=now.getFullYear()+'-'+
    String(now.getMonth()+1).padStart(2,'0')+'-'+
    String(now.getDate()).padStart(2,'0')+' '+
    String(now.getHours()).padStart(2,'0')+':'+
    String(now.getMinutes()).padStart(2,'0')+':'+
    String(now.getSeconds()).padStart(2,'0');
  var el=document.getElementById('live-clock');
  if(el)el.textContent='🕐 '+s;
  setTimeout(updateClock,1000);
})();
</script>
