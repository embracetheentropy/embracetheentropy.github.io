---
layout: default
title: Blog
permalink: /blog/
---

# Blog

<div class="posts">
  {% for post in site.posts %}
    <article class="post">
      <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
      <time datetime="{{ post.date | date: "%Y-%m-%d" }}">{{ post.date | date: "%B %d, %Y" }}</time>
      {% if post.excerpt %}
        <p>{{ post.excerpt | strip_html | truncatewords: 50 }}</p>
      {% endif %}
    </article>
  {% endfor %}
</div>

{% if site.posts.size == 0 %}
<p>No blog posts yet. Check back soon!</p>
{% endif %}