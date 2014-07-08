---
layout: default
title: Steve Testa's Blog
---
<div class="container">
    <div class="row">
        <div class="col-md-9">
            {% for post in site.posts %}
            <div class="post">
                <h2><a class="post-link" href="{{ post.url | prepend: site.url }}">{{ post.title }}</a></h2>
                <span class="post-date">{{ post.date | date: "%b %-d, %Y" }}</span>
            </div>
            {% endfor %}
        </div>
        <div class="col-md-1">
        </div>
    </div>
</div>

<!--<p class="rss-subscribe">subscribe <a href="{{ "/feed.xml" | prepend: site.url }}">via RSS</a></p>-->