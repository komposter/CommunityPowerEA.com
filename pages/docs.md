---
layout: page
title: Documentation
permalink: /docs/
---

# Documentation

Full documentation is available on [Google Drive](https://docs.google.com/document/d/1ww1M97H54IBwtCKZDhxtqsTsrtEMKofXHMEWMGCyZNs) (will be moved here soon).


<div class="section-index">
    <hr class="panel-line">
    {% for post in site.docs  %}        
    <div class="entry">
    <h5><a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></h5>
    <p>{{ post.description }}</p>
    </div>{% endfor %}
</div>
