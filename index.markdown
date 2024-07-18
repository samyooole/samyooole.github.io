---
layout: default
title: Home
---

<div class="posts">
  {% for post in site.posts %}
  {% assign currentdate = post.date | date: "%B %Y" %}
  {% if currentdate != date %}
  {% unless forloop.first %}</ul>{% endunless %}
  <h2>{{ currentdate }}</h2>
  <ul>
  {% assign date = currentdate %}
  {% endif %}
  <li><a href="{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
  </ul>
</div>