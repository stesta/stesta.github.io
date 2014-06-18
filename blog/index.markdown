---
layout: page
title: Steve Testa's Blog
permalink: /steve/blog/
---
<ul class="posts">
{% for post in site.posts %}
    <li>
    <span class="post-date">{{ post.date | date: "%b %-d, %Y" }}</span>
    <a class="post-link" href="{{ post.url | prepend: site.url }}">{{ post.title }}</a>
    </li>
{% endfor %}
</ul>

<p class="rss-subscribe">subscribe <a href="{{ "/feed.xml" | prepend: site.url }}">via RSS</a></p>