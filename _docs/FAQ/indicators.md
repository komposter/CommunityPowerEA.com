---
layout: page
title: How to get indicators?
permalink: /docs/FAQ/indicators
---

# How to attach indicators to the chart? Where can I get indicators?

{% for post in site.indicators %}
   <h3><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h3>
{% endfor %}
