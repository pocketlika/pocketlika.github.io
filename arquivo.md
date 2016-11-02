---
layout: page_no_comments
title: Archive
---

{% for post in site.posts %}
  <p class="blog-post-title"><a href="{{ post.url }}">{{ post.title }}</a></p>
  <p class="blog-post-info">
    {% assign d = post.date | date: "%-d"  %}
    {% case d %}
      {% when '1' or '21' or '31' %}{{ d }}st
      {% when '2' or '22' %}{{ d }}nd
      {% when '3' or '23' %}{{ d }}rd
      {% else %}{{ d }}th
      {% endcase %}
    {{ post.date | date: "%B" }}
    {{ post.date | date: "%Y" }}

    {% for tag in post.tags %}
        : <a href="{{ site.baseUrl }}/tag/#{{ tag }}">{{ tag }}</a>
    {% endfor %}
  </p>
  <div class="blog-post-excerpt">
    {{ post.excerpt }}
  </div>
  <p class="blog-post-readmore">
    <a href="{{ post.url }}">Read More</a>
  </p>
{% endfor %}
