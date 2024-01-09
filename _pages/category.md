---
layout: post
title: Category List
permalink: /category/
---

{{ page.title }}
================

{% assign current_cat = page.url | split: "/" | last %}
{% for post in site.categories[current_cat] %}
    <ul><li><a href="{{ site.baseurl }}{{ post.url }}">{{post.title}}</a></li>  
    {% endfor %} </ul>
