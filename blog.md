---
layout: default
title: "Blog"
---

<h1 style="text-align:center;">💾Blog</h1>

<h5 style="text-align:center;">Welcome to my blog page. Below you’ll find a list of my blog posts with a brief overview.</h5>

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
