---
layout: default
title: "标签"
tags: active
---
<div>
{% for tag in site.tags %} 
	<a name="{{ tag[0] }}"></a><h3>{{ tag[0] }}({{ tag[1].size }})</h3>
	<ul>
	{% for post in tag[1] %}
		<li>
              <div class="date"><span>{{ post.date | date: "%d" }}</span>{{ post.date | date: "%-m" }}月</div>
              <div class="collections-info">
                  <h5>
                      <a href="{{ post.url }}">{{ post.title }}</a>
                  </h5>
                  <div class="description">{{ post.summary }}</div>
                  <p>
                      <a class="blue-link" href="{{ post.url }}">阅读全文...</a>
                      · 评论
                  </p>
              </div>
            </li>
	{% endfor %}
	</ul>
{% endfor %}
</div>
