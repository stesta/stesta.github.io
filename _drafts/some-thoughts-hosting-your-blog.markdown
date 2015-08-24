---
layout: post
title: "Using GitHub Pages to Host Your Blog"
date: 2015-08-14
comments: true
---

I was speaking with a developer friend recently. My friend is a really smart guy with a lot great knowledge to share with the world. He is ready to start his own blog and started asking some questions about what I use for hosting. I mentioned that my personal preference these days is [GitHub Pages][githubpages]. For starters **it's a free service**! However, like Mr. Phil Haack before me, I've also realized that hosting my own blog is no longer a concern I want to have. I prefer to focus on the content. All the extra fluff that comes with managing VMs is completely unecessary in this context. When hosting a blog, the needs are relatively simple as most of it is static content. There are a few pieces that are 'dynamic' such as the blog post listing or the latests posts lists. GitHub Pages uses and wonderful tool called [jekyll] to generate static content and fake most of that dynamic behavior.  

For now, let's start in with **some of the benefits**:

### Jekyll  

As mentioned, Jekyll is a static content generator. Basically what this means is that we can use standard html, handlebar templates and markdown to create layouts and templates that are used to generate a static html website. All technologies Jekyll leverages are usually directly in a web developer's wheelhouse. The added bonus is that static html is simple and performant.  

### Git    

Would you believe that hosting on GitHub Pages uses Git? Crazy, right?! Source control should be a given these days and Git is, in my opinion, the premier tool in its class.

### Markdown    

Markdown is a lightweight markup language that was specifically designed to be easily converted to html while still being easy to create via a standard text editor. Pay attention to that last little bit. Markdown is easy to create via a standard editor. For me this translates to focusing on the content and content is king.

### Collaboration  

This is all still GitHub! The central theme here is open source and collaboration. Your audience will probably notice your mistakes more quickly than you will. Using Github we can easily allow the grammar police out there to get statisfaction by submitting a pull request. Don't believe me? You can send me a pull request for this very article!  

Dynamic Elements
----------------

So I'm not going to go over too many of the technical details of how to implement your layouts and the structure of a jekyll based website. There is plenty of documentation on that. Plus, you can always feel free to take a look at the [source code for my blog][myblogsource] to figure out what you need to know! Instead I'd prefer to walk you through some of the common solutions I've used for some of the more advanced and dynamic features of a blog.

### Domains and DNS  

When using GitHub Pages you'll get a default url that looks something like mysite.githubpages.io. That's all well and good, but most of the time you're going to want a custom domain name. On some of the other hosting platforms we don't have to think about things like domains and DNS. Often times, the domain and DNS are wired up for you right there on the platform. Unfortunately, with GitHub Pages, this is not the case. So we need to resort to finding our DNS service. Below are my two favorite options.  

**Google Domains**  
A relatively new Google Service, but an awesome one. Domains are around $12/year plus free DNS with it. You won't find many more budget friendly services out there.

**DNSimple**  
Slightly more expensive than Google Domains, but also a bit more user friendly. DNSimple offers pre-defined service configurations including one for GitHub Pages. The standard .com TLD is $14. Additionally, you have to purchase a month DNS subscription plan. Their starter plan is $5 month and allows for 5 domains to be managed. 

### Search  

Search functionality is usually something that requires a server-side language. Normally, I'd default to Lucene.Net or running Solr on top of Tomcat. With GitHub Pages we don't have that option. I know some folks have an aversion to Google, but Google's Custom Search Engine is an attractive option when you're restricted to only JavaScript. 

### Comments  

Disqus. It's super awesome. 

### DotNetFiddle  

Now don't get me wrong. My friend and I are very similiar professionally. We're both .Net developers and, for the most part, web developers. This means that when we want to showcase some .Net code static sites like those hosted on GitHub Pages might not be the right fit. One option I enjoy is DotNetFiddle. 

[github]: https://github.com
[githubpages]: https://pages.github.com/
[jekyll]: http://jekyllrb.com/
[dotnetfiddle]: https://dotnetfiddle.net/
[googlecse]: https://cse.google.com/cse/
[googledomains]: http://
[dnsimple]: http://
[myblogsource]: https://github.com/stesta/stesta.github.io 