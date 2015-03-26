---
layout: default
title: Steve Testa's Blog
---
<div class="section blog-posts-wrapper">
    <div class="container">
        <div class="row">
            {% for post in site.posts %}
            <div class="col-md-4 col-sm-6">
                <div class="blog-post">
					<div class="post-info">
						<div class="post-date">
							<div class="date">{{ post.date | date: "%b %-d, %Y" }}</div>
						</div>
						<div class="post-comments-count">
							<a href="#" title="Show Comments"><i class="glyphicon glyphicon-comment icon-white"></i>16</a>
						</div>
					</div>
					<a href="{{ post.url | prepend: site.url }}"><img src="http://fillmurray.com/400/300" class="post-image" alt="{{ post.title }}"></a>
					<div class="post-title">
						<h3><a href="{{ post.url | prepend: site.url }}">{{ post.title }}</a></h3>
					</div>
					<div class="post-summary">
						<p>{{ post.excerpt }}</p>
					</div>
					<div class="post-more">
						<a href="{{ post.url | prepend: site.url }}" class="btn btn-small">Read more</a>
					</div>
				</div>
            </div>
            {% endfor %}
        </div>
    </div>
</div>
<!--<p class="rss-subscribe">subscribe <a href="{{ "/feed.xml" | prepend: site.url }}">via RSS</a></p>-->