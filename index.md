---
layout: default
title: "首页：Home"
---

{% for post in site.posts %}
<h2>
  <a href="{{ post.url }}">
    {{ post.title }}
  </a> 
  <div class="post-date">
	<span class="glyphicon glyphicon-time"></span>
	{{ post.date | date_to_string }}
  </div>
</h2>
<hr>
{{ post.excerpt }}
<p>
    <a href="{{ post.url }}">
      阅读全文
    </a> 
</p>
{% endfor %}

<!-- Pager indicator -->
<ul class="pager">
  {% if paginator.previous_page %} {% if paginator.previous_page == 1 %}
  <li class="previous">
    <a href="{{ site.url }}/">
      &larr; Older
    </a>
  </li>
  {% else %}
  <li class="previous">
    <a href="{{ site.url }}/page{{ paginator.previous_page }}">
      &larr; Older
    </a>
  </li>
  {% endif %} {% endif %} {% if paginator.next_page %}
  <li class="next">
    <a href="{{ site.url }}/page{{ paginator.next_page }}">
      Newer &rarr;
    </a>
  </li>
  {% endif %}
</ul>
