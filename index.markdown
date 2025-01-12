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
  <li>
    <a href="{{ post.url }}">{{ post.title }}</a>
    <span class="post-tags" > <!--- float right makes it justify to the right  style="float: right;"-->
      [{% for tag in post.tags %}
        <a href="{{ site.baseurl }}/tag/{{ tag }}">{{ tag }}</a>{% if forloop.last == false %}, {% endif %}
      {% endfor %}]
    </span>
  </li>
  {% endfor %}
  </ul>
</div>