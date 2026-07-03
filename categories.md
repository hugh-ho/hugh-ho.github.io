---
layout: page
title: 分类
permalink: /categories/
---

<div class="category-list">
  {% for category in site.categories %}
    <h2 id="{{ category[0] | slugify }}">{{ category[0] }}</h2>
    <ul class="post-list">
      {% for post in category[1] %}
      <li>
        <span class="post-meta">{{ post.date | date: "%Y年%m月%d日" }}</span>
        <h3>
          <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
        </h3>
      </li>
      {% endfor %}
    </ul>
  {% endfor %}
</div>
