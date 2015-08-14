---
layout: post
title: "Using GitHub Pages to Host Your Blog"
date: 2015-08-14
comments: true
---

I was speaking with a developer friend recently. My friend is a really smart guy with a lot great knowledge to share with the world. He is ready to start his own blog and started asking some questions about what I use for hosting. I mentioned that my personal preference these days is [GitHub Pages][githubpages]. For starters **it's a free service**! However, like Mr. Phil Haack before me, I've also realized that hosting my own blog is no longer a concern I want to have. I prefer to focus on the content. All the extra fluff that comes with managing VMs is completely unecessary in this context. When hosting a blog, the needs are relatively simple as most of it is static content. There are a few pieces that are 'dynamic' such as the blog post listing or the latests posts lists. GitHub Pages uses and wonderful tool called [jekyll] to generate static content and fake most of that dynamic behavior. More on that later. 

Benefits
-------- 

For now, let's start in with some of the benefits

### Jekyll

Jekyll utilizes html, handlebar templates and markdown - all technologies that are usually right in a web developer's wheelhouse.

### Git  

Would you believe that hosting on GitHub Pages uses Git as it's souce control? Who woulda thought?!?! 

### Markdown  

Markdown

### Collaboration  

This is all still GitHub... the central theme here is open source and collaboration. Your audience will probably notice your mistakes more quickly than you will. Using Github we can easily allow the grammar police out there to get statisfaction by submitting a pull request. Don't believe me? You can send me a pull request for this very article!

Getting Started
---------------

So I'm not going to go over too many of the technical details of how to implement your layouts and the structure of a jekyll based website. There is plenty of documentation on that. Plus, you can always feel free to take a look at the [source code for my blog][myblogsource] to figure out what you need to know! Instead I'd prefer to walk you through some of the common solutions I've used for some of the more advanced and dynamic features of a blog.

### The Basics

### Domains and DNS

When using GitHub Pages you'll get a default url that looks something like mysite.githubpages.io. That's all well and good, but most of the time you're going to want a custom domain name. On some of the other hosting platforms we don't have to think about things like domains and DNS. Often times, the domain and DNS are wired up for you right there on the platform. Unfortunately, with GitHub Pages, this is not the case. So we need to resort to finding our DNS service. Below are my two favorite options.  

**Google Domains**

**DNSimple** 

### Search

### Comments

### DotNetFiddle

Now don't get me wrong. My friend and I are very similiar professionally. We're both .Net developers and, for the most part, web developers. This means that when we want to showcase some .Net code static sites like those hosted on GitHub Pages might not be the right fit.  

When You Just Need Something More
---------------------------------

### Azure

### Pricing  


[github]: https://github.com
[githubpages]: https://pages.github.com/
[jekyll]: http://jekyllrb.com/
[dotnetfiddle]: https://dotnetfiddle.net/
[googlecse]: https://cse.google.com/cse/
[googledomains]: http://
[dnsimple]: http://
[myblogsource]: https://github.com/stesta/stesta.github.io 