---
permalink: /eventlist-v2/
title: "HPCSIG Events"
author_profile: false
---

<div id="dates3">

{% for post in site.events %}
  {% assign currentdate = post.event_date | date: "%Y-%m" %}
  {% if currentdate != date %}
    {% unless forloop.first %}{% endunless %}
    {% assign currentmonth = post.event_date | date: "%Y %B" %}
    <h1 id="y{{post.event_date | date: "%Y-%m"}}">{{ currentmonth }}</h1>
    {% assign date = currentdate %}
  {% endif %}
    <p>{{ post.event_date }} - <a href="/HPC-SIG{{ post.url }}">{{ post.title }}</a></p>
  {% if forloop.last %}{% endif %}
{% endfor %}
</div>  

