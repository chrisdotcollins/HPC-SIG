---
permalink: /eventlist-v2/
title: "HPCSIG Events"
author_profile: false
---

<div id="dates3">
{% assign current_time = site.time | date: '%Y-%m-%d' %}
{% assign epoch_time = site.time | date: '%s' %}

    <h2>Upcoming Events</h2>
{% for post in site.events %}
  {% assign currentdate = post.event_date | date: "%Y-%m" %}
  {% assign event_epoch = post.event_date | date: "%s" %}

  {% if event_epoch >= epoch_time %}
    {% if currentdate != date %}
      {% unless forloop.first %}{% endunless %}
      <h3 id="y{{post.event_date | date: "%Y-%m"}}">{{ currentdate }}</h3>
      {% assign date = currentdate %}
    {% endif %}
      <p>{{ post.event_date }} - <a href="/HPC-SIG{{ post.url }}">{{ post.title }}</a></p>
    {% if forloop.last %}{% endif %}
  {% endif %}
{% endfor %}

  <h2>Past Events</h2>
{% for post in site.events %}
  {% assign currentdate = post.event_date | date: "%Y-%m" %}
  {% assign event_epoch = post.event_date | date: "%s" %}

  {% if event_epoch <= epoch_time %}
    {% if currentdate != date %}
      {% unless forloop.first %}{% endunless %}
      <h3 id="y{{post.event_date | date: "%Y-%m"}}">{{ currentdate }}</h3>
      {% assign date = currentdate %}
    {% endif %}
      <p>{{ post.event_date }} - <a href="/HPC-SIG{{ post.url }}">{{ post.title }}</a></p>
    {% if forloop.last %}{% endif %}
  {% endif %}
{% endfor %}




</div>  

