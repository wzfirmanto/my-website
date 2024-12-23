---
layout: page
title: Blog
permalink: blog/
---
<div class="posts">
  {% for post in paginator.posts %}
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
  <span class="page_number">Page {{ paginator.page }} of {{ paginator.total_pages }}</span>
  {% if paginator.next_page %}
    <a href="{{ paginator.next_page_path }}" class="next">Next</a>
  {% endif %}
</div>
