---
layout: default
title: Steve Testa's Blog
---
<div class="breadcrumbs">
    <div class="container">
        <h1 class="pull-left">Blog</h1>
        <ul class="pull-right breadcrumb">
            <li><a href="/">Home</a></li>
            <li class="active">Blog</li>
        </ul>
    </div>
</div>

<div class="container content">		
	<div class="row blog-page">    
        <!-- Left Sidebar -->
    	<div class="col-md-9 md-margin-bottom-40">
            {% for post in site.posts %}
            <div class="row blog blog-medium margin-bottom-40">
                <div class="col-md-5">
                    <img class="img-responsive lazy" data-original="{{ post.thumbnail }}" src="http://fpoimg.com/440x270" alt="{{ post.title }}">
                </div>    
                <div class="col-md-7">
                    <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
                    <ul class="list-unstyled list-inline blog-info">
                        <li><i class="fa fa-calendar"></i> {{ post.date | date: "%b %-d, %Y" }}</li>
                        <li><i class="fa fa-comments"></i> <a href="#">{% include post/comments_link.html %}</a></li>
                        {% if page.categories %}<li><i class="fa fa-tags"></i> {% include post/categories.html %}</li>{% endif %}
                    </ul>
                    <p>{{ post.excerpt }}</p>
                    <p><a class="btn-u btn-u-sm" href="{{ post.url }}">Read More <i class="fa fa-angle-double-right margin-left-5"></i></a></p>
                </div>    
            </div>
            <hr class="margin-bottom-40" />
			{% endfor %}
		</div>
		<div class="col-md-3">
            <div class="magazine-sb-social margin-bottom-30">
                <div class="headline headline-md"><h2>Social</h2></div>
                <ul class="social-icons social-icons-color">
                    <li><a class="social_rss" data-original-title="Feed" href="/steve/blog/feed.xml"></a></li>
                    <li><a class="social_twitter" data-original-title="Twitter" href="https://twitter.com/steven_testa" rel="me"></a></li>
                    <li><a class="social_facebook" data-original-title="Facebook" href="https://www.facebook.com/steven.testa" rel="me"></a></li>
                    <li><a class="social_googleplus" data-original-title="Google Plus" href="https://plus.google.com/114388532024454912535/about" rel="me"></a></li>
                    <li><a class="social_linkedin" data-original-title="LinkedIn" href="http://www.linkedin.com/in/stevendtesta"></a></li>
                    <li><a class="social_github" data-original-title="Github" href="{{ site.github_repo_url }}"></a></li>
                </ul>
                <div class="clearfix"></div>                
            </div>
			<div class="posts margin-bottom-40">
            <div class="headline headline-md"><h2>Author</h2></div>
                <p>Steve Testa <br />I am a developer, consultant, entrepreneur and self described foosball champion. I like to blog occasionally about technology, code, trends and the community.</p>
	        </div>
		</div>      
	</div>
</div>