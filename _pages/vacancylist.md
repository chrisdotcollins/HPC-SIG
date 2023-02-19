---
permalink: /vacancylist/
title: "HPC Related Vacancies"
---

<div id="dates3">
  {% assign current_time = site.time | date: '%Y-%m-%d' %}
  {% assign epoch_time = site.time | date: '%s' %}

  {% for post in site.vacancies %}
  {% assign currentdate = post.vacancies_date | date: "%Y-%m" %}
  {% assign vacancy_epoch = post.vacancies_date | date: "%s" %}

  {% if vacancy_epoch >= epoch_time %}
  <h2><a href="/HPC-SIG{{ post.url }}">{{ post.title }}</a></h2>
  <p>Closing date: {{ post.vacancies_date }}<br>Location: {{ post.site }}</p>
  {% endif %}  
{% endfor %}
</div>  
