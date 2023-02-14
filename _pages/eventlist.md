---
permalink: /eventlist/
title: "Event List"
---

<div id="dates3">
{% for post in site.events %}
  {% assign currentdate = post.date | date: "%Y-%M" %}
  {% if currentdate != date %}
    {% unless forloop.first %}{% endunless %}
    <h1 id="y{{post.date | date: "%Y-%M"}}">{{ currentdate }}</h1>
    {% assign date = currentdate %}
  {% endif %}
    <p>{{ post.date | slice: 0, 10 }} - <a href="/HPC-SIG/{{ post.url }}">{{ post.title }}</a></p>
  {% if forloop.last %}{% endif %}
{% endfor %}
</div>
