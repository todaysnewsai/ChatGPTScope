---
layout: page
title: News
permalink: /news/
---
<p>This section will collect our latest news coverage.</p>

<div class="post-list">
{% assign items = site.posts | where_exp: "post", "post.categories contains 'news'" %}
{% for post in items %}
<article class="post-card">
  <p class="meta">{{ post.date | date: "%B %-d, %Y" }}</p>
  <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
  {% if post.description %}<p>{{ post.description }}</p>{% endif %}
</article>
{% endfor %}
</div>
