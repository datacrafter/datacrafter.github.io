---
layout: home
title: "Recent Posts"
tags: [Jekyll, theme, responsive, blog, template]
image:
  feature: typewriter.jpg
---

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      {{ post.excerpt }}
    </li>
  {% endfor %}
</ul>