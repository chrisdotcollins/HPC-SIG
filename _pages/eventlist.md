---
permalink: /eventlist/
title: "Event List"
---

<div id="dates3">
{% for post in site.events %}
  {% assign currentdate = post.date | date: "%Y-%m" %}
  {% if currentdate != date %}
    {% unless forloop.first %}{% endunless %}
    <h1 id="y{{event.event_date | date: "%Y-%m"}}">{{ currentdate }}</h1>
    {% assign date = currentdate %}
  {% endif %}
    <p>{{ event.event_date | slice: 0, 10 }} - <a href="/HPC-SIG/{{ post.url }}">{{ post.title }}</a></p>
  {% if forloop.last %}{% endif %}
{% endfor %}
</div>
