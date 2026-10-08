---
layout: page
title: Analysis
permalink: /analysis/
---
<p>This section will collect our latest analysis coverage.</p>

<div class="post-list">
{% assign items = site.posts | where_exp: "post", "post.categories contains 'analysis'" %}
{% for post in items %}
<article class="post-card">
  <p class="meta">{{ post.date | date: "%B %-d, %Y" }}</p>
  <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
  {% if post.description %}<p>{{ post.description }}</p>{% endif %}
</article>
{% endfor %}
</div>
