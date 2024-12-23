---
layout: page
title: Blog
permalink: blog/
---
<div class="posts">
  {% for post in site.posts %}
    {% unless post.categories contains "portfolio" %}
      <div class="post">
        <h1 class="post-title">
          <a href="{{ post.url }}">{{ post.title }}</a>
        </h1>
        <span class="post-date">{{ post.date | date_to_string }}</span>
        {{ post.excerpt }}
        <a href="{{ post.url }}">Read more...</a>
      </div>
    {% endunless %}
  {% endfor %}
</div>

<!-- Pagination links -->
<div class="pagination">
  {% if paginator.previous_page %}
    <a href="{{ paginator.previous_page_path }}" class="previous">Previous</a>
  {% endif %}

  <span class="page-number">
  Page {% if paginator.page %}{{ paginator.page }}{% else %}1{% endif %} 
  of {% if paginator.total_pages %}{{ paginator.total_pages }}{% else %}1{% endif %}
  </span>
  {% if paginator.next_page %}
    <a href="{{ paginator.next_page_path }}" class="next">Next</a>
  {% endif %}
</div>
