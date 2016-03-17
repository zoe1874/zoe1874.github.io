---
layout: default
title: "归档"
active: "archives"
---
<ul class="list-unstyled">
     {% for post in site.posts limit:100 %} 
	 {% unless post.next %} 
    <h2>{{ post.date | date: '%Y' }}</h2> 
	{% else %} {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %} {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %} 
	{% if year != nyear %} 
    <h2>{{ post.date | date: '%Y' }}</h2> {% endif %} 
	{% endunless %} 
    <li>
          <div class="date"><span>{{ post.date | date: "%d" }}</span>{{ post.date | date: "%-m" }}月</div>
          <div class="collections-info">
              <h5>
                  <a href="{{ post.url }}">{{ post.title }}</a>
              </h5>
              <div class="description">{{ post.excerpt }}</div>
              <p>
                  <a class="blue-link" href="{{ post.url }}">阅读全文...</a>
                  ·  评论
                  <span class="tag">
                  <i class="fa fa-tags"></i>&nbsp;
                      <a class="" href="/tags/1951/collections">连载</a>、
                      <a class="" href="/tags/17/collections">故事</a>
                  </span>
              </p>
          </div>
        </li>
	{% endfor %} 
</ul> 
