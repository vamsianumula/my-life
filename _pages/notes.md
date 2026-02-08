---
layout: page
permalink: /notes/
title: notes
description: Random thoughts and learnings
nav: true
nav_order: 1
---

<div class="post">

<ul class="post-list">
  {% assign sorted_notes = site.notes | sort: "date" | reverse %}
  {% for post in sorted_notes %}

  {% assign read_time = post.content | number_of_words | divided_by: 180 | plus: 1 %}
  {% assign year = post.date | date: "%Y" %}
  {% assign tags = post.tags | join: "" %}
  {% assign categories = post.categories | join: "" %}

  <li>
    <h3>
      <a class="post-title" href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </h3>
    <p>{{ post.description }}</p>
    <p class="post-meta">
      {{ read_time }} min read &nbsp; &middot; &nbsp;
      {{ post.date | date: '%B %d, %Y' }}
    </p>
    <p class="post-tags">
      <i class="fa-solid fa-calendar fa-sm"></i> {{ year }}

      {% if tags != "" %}
      &nbsp; &middot; &nbsp;
        {% for tag in post.tags %}
          <i class="fa-solid fa-hashtag fa-sm"></i> {{ tag }}
          {% unless forloop.last %}&nbsp;{% endunless %}
        {% endfor %}
      {% endif %}

      {% if categories != "" %}
      &nbsp; &middot; &nbsp;
        {% for category in post.categories %}
          <i class="fa-solid fa-tag fa-sm"></i> {{ category }}
          {% unless forloop.last %}&nbsp;{% endunless %}
        {% endfor %}
      {% endif %}
    </p>
  </li>

  {% endfor %}
</ul>

</div>
