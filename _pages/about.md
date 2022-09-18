---
permalink: /
title: "About me"
excerpt: "About me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

Vu Hong Quan's Blog <br>
Topics: machine learning, data science, data applications, recommendation system, signal processing, neural science.

## RECENT POSTS

{% for post in site.posts limit:10 %}
  {% include archive-single.html %}
{% endfor %}