---
layout: page
title: Posts by Tag
---
{% capture tags %}{% for tag in site.tags %}{{ tag[0] }}|{% endfor %}{% endcapture %}
{% assign sortedtags = tags | split:'|' | sort %}
{% for tag in sortedtags %}
  <a name="{{ tag }}"></a>
  <h4>{{ tag }}</h4>
  <ul>
    {% for post in site.tags[tag] %}
      <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}
