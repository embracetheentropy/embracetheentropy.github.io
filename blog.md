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
      {% if post.categories.size > 0 %}
        <div class="post-categories">
          Categories: 
          {% for category in post.categories %}
            <span class="category">{{ category }}</span>{% unless forloop.last %}, {% endunless %}
          {% endfor %}
        </div>
      {% endif %}
      {% if post.excerpt %}
        <div class="post-excerpt">
          {{ post.excerpt | strip_html | truncatewords: 50 }}
          <a href="{{ post.url | relative_url }}">Read more →</a>
        </div>
      {% endif %}
    </article>
  {% endfor %}
</div>

{% if site.posts.size == 0 %}
<p>No blog posts yet. Check back soon!</p>
{% endif %}