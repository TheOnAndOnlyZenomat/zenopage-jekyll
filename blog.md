---
layout: default
title: Blog
header: Blog
description: "This is my personal blog"
permalink: /blog/
---

{% for post in site.posts %}
<h2>
  <a href="{{post.url | absolute_url }}">
    {{ post.title }}
  </a>
</h2>

<p class="meta">{{ post.date | date_to_string }}</p>
{% if post.tags.size > 0 %}
  <p class="meta">Tags: 
    {% for tag in post.tags %}
		{% if forloop.index  < post.tags.size %}
			{{ tag }},
		{% else %}
			{{ tag }}
		{% endif %}
    	{% endfor %}
  </p>
{% endif %}

{{ post.excerpt }}

{% endfor %}
