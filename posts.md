---
layout: page
title: News
subtitle: See, what's happened to us!
bigimg:
- "/img/big-imgs/news.jpg" : "caption text"
---

<div class="list-filters">
  <a href="/posts" class="list-filter filter-selected">News</a>
  <a href="/tags" class="list-filter">Index</a>
</div>

<div class="posts-list">
  {% for post in site.posts %}
  <article>
    <a class="post-preview" href="{{ post.url | prepend: site.baseurl }}">
	    <h2 class="post-title">{{ post.title }}</h2>
	    {% if post.subtitle %}
	    <h3 class="post-subtitle">
	      {{ post.subtitle }}
	    </h3>
	    {% endif %}
      <p class="post-meta">
        Posted on {{ post.date | date: "%b %-d, %Y" }}
      </p>
      <div class="post-entry">
        {{ post.content | truncatewords: 50 | strip_html | xml_escape}}
        <!-- <span href="{{ post.url | prepend: site.baseurl }}" class="post-read-more">[Read&nbsp;More]</span> -->
      </div>
    </a>  
   </article>
  {% endfor %}
</div>