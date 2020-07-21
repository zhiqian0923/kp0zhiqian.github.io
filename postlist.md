---
layout: default
title: Posts
---

<div class="posts">
  {% for post in site.posts %}
      <p>
      <a style="color: #303030;" href="{{ post.url | absolute_url }}">
        {{ post.title }} 
      </a>
        <span style="float:right;">[{{ post.date | date_to_string }}]</span>
      </p>
  {% endfor %}
</div>

<div class="pagination">
  {% if paginator.next_page %}
    <a class="pagination-item older" href="{{ paginator.next_page_path | absolute_url }}">Older</a>
  {% else %}
    <span class="pagination-item older">Older</span>
  {% endif %}
  {% if paginator.previous_page %}
    {% if paginator.page == 2 %}
      <a class="pagination-item newer" href="{{ '/' | absolute_url }}">Newer</a>
    {% else %}
      <a class="pagination-item newer" href="{{ paginator.previous_page_path | absolute_url }}">Newer</a>
    {% endif %}
  {% else %}
    <span class="pagination-item newer">Newer</span>
  {% endif %}
</div>
