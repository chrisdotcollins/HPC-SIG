---
permalink: /vacancylist/
title: "HPC Related Vacancies"
---

<div id="dates3">
  {% assign current_time = site.time | date: '%Y-%m-%d' %}
  {% assign epoch_time = site.time | date: '%s' %}
  <p>{{ current_time }}</p>
  <p>{{ epoch_time }}</p>

  {% for post in site.vacancies %}
  {% assign currentdate = post.vacancies_date | date: "%Y-%m" %}
  {% assign vacancy_epoch = post.vacancies_date | date: "%s" %}
  <p>Site time {{ epoch_time }}</p>
  <p>Job time {{ vacancy_epoch }}</p>
  {% if vacancy_epoch >= epoch_time %}
  <p><b><a href="/HPC-SIG{{ post.url }}">{{ post.title }}</a></b></p>
  <p>Closing date: {{ post.vacancies_date }}</p>
  <p>Location: {{ post.site }}</p>
  {% endif %}  
{% endfor %}
</div>  
