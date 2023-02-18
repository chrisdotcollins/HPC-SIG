---
permalink: /vacancylist/
title: "HPC Related Vacancies"
---

<div id="dates3">
  {% assign current_time = DateTime.now %}
  <p>{{ current_time }}</p>
  <p>Test Test Test</p>
{% for post in site.vacancies %}
  <p>{{ post.vacancies_date }} - <a href="/HPC-SIG{{ post.url }}">{{ post.title }}</a></p>
  {% assign currentdate = post.vacancies_date | date: "%Y-%m" %}
  {% if currentdate != date %}
    {% unless forloop.first %}{% endunless %}
    <h1 id="y{{post.vacancies_date | date: "%Y-%m"}}">{{ currentdate }}</h1>
    {% assign date = currentdate %}
  {% endif %}
    <p>{{ post.vacancies_date }} - <a href="/HPC-SIG{{ post.url }}">{{ post.title }}</a></p>
  {% if forloop.last %}{% endif %}
{% endfor %}
</div>  
