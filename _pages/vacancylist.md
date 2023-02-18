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
  <p>Site time {{ epoch_time }}</p>
  <p>Job time {{ vacancy_epoch }}</p>
  {% if vacancy_epoch >= epoch_time %}
  <h1><a href="/HPC-SIG{{ post.url }}">{{ post.title }}</a></h1>
  <p>Closing date: {{ post.vacancies_date }}<br>Location: {{ post.site }}</p>
  {% endif %}  
{% endfor %}
</div>  
