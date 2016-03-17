---
layout: default
title: "首页"
active: "index"
---
{% for post in site.posts %}
<li>
  <div class="date"><span>{{ post.date | date: "%d" }}</span>{{ post.date | date: "%-m" }}月</div>
  <div class="collections-info">
      <h5>
          <a href="{{ post.url }}">{{ post.title }}</a>
      </h5>
      <div class="description">{{ post.excerpt }}</div>
      <p>
          <a class="blue-link" href="{{ post.url }}">阅读全文...</a>
          · 评论
          <span class="tag">
          <i class="fa fa-tags"></i>&nbsp;
              <a class="" href="/tags/1951/collections">连载</a>、
              <a class="" href="/tags/17/collections">故事</a>
          </span>
      </p>
  </div>
</li>
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
