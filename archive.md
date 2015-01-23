---
layout: page
title: Archive
---

## Blog Posts


{% for post in site.posts %}
  {% capture currentyear %}{{post.date | date: "%Y"}}{% endcapture %}
    {% if currentyear != year %}
      {% unless forloop.first %}</ul>{% endunless %}
        <h1>{{ currentyear }}</h1>
      <ul>
      {% capture year %}{{currentyear}}{% endcapture %}
    {% endif %}
    <li><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}
