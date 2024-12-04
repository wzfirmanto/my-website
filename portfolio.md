---
layout: page
title: Portfolio
permalink: /portfolio/  # Make sure there's a leading slash
---

<div class="portfolio-list">
  {% for post in site.posts %}
    {% if post.categories contains "portfolio" %}
      <article class="portfolio-item">
        <h2 class="portfolio-title">
          <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        </h2>
        <span class="portfolio-date">{{ post.date | date: "%B %Y" }}</span>
        {% if post.description %}
          <p class="portfolio-description">{{ post.description }}</p>
        {% endif %}
      </article>
    {% endif %}
  {% endfor %}
</div>
