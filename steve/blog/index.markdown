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
                <div class="lead post-date">{{ post.date | date: "%b %-d, %Y" }}</div>
                <div class="lead post-content">{{ post.excerpt }}</div>
                <div class="lead"><a class="post-link" href="{{ post.url | prepend: site.url }}">read more...</a></div>
            </div>
            
            <hr class="featurette-divider" />
            {% endfor %}
        </div>
        <div class="col-md-1">
        </div>
    </div>
</div>

<!--<p class="rss-subscribe">subscribe <a href="{{ "/feed.xml" | prepend: site.url }}">via RSS</a></p>-->