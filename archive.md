---
layout: page
title: Archive
---

## Blog Posts

{% for post in site.posts %}
*
{% endfor %}

{% for post in site.posts %}
  {% capture currentyear %}{{post.date | date: "%Y"}}{% endcapture %}
    {% if currentyear != year %}
      {% unless forloop.first %}</ul>{% endunless %}
        <h1>{{ currentyear }}</h1>
      <ul>
      {% capture year %}{{currentyear}}{% endcapture %}
    {% endif %}
    {{ post.date | date_to_string }} &raquo; [ {{ post.title }} ]({{ site.baseurl }}{{ post.url }})
{% endfor %}
