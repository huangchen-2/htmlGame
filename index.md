# 👾 htmlGame

> 网页对话小游戏 & 技术博客

## 🎮 游戏入口
👉 [末日生存对话游戏](apocalypse_survival.html)

---

## 📝 最新文章

<ul>
{% for post in site.posts limit:5 %}
  <li>
    <strong>{{ post.date | date: "%m-%d" }}</strong>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
  </li>
{% endfor %}
</ul>

[📖 查看所有文章 →]({{ '/blog/' | relative_url }})
