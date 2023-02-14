---
permalink: /eventlist/
title: "Event List"
---

<div id="dates3">

{% assign events_sorted = site.events | sort %}
  
<!--{% for post in site.events %}-->
{% for post in events_sorted %}-->
  {% assign currentdate = post.event_date | date: "%Y-%m" %}
  {% if currentdate != date %}
    {% unless forloop.first %}{% endunless %}
    <h1 id="y{{post.event_date | date: "%Y-%m"}}">{{ currentdate }}</h1>
    {% assign date = currentdate %}
  {% endif %}
    <p>{{ post.event_date }} - <a href="/HPC-SIG/{{ post.url }}">{{ post.title }}</a></p>
  {% if forloop.last %}{% endif %}
{% endfor %}
</div>  
