---
layout: post
title: "Git Branching Workflow - Part 1: Overview"
date: 2013-01-25
comments: true
---
<p>In this post I'm going to explain the current development model for my team. We use <a href="http://www.git-scm.com/">Git</a> very heavily. I will go over our branching workflow with some explanation of the basics, but if you need to learn some more about Git try the book <a href="http://www.git-scm.com/book">Git Pro</a>. It is avaiable as a free ebook and covers everything you'll need to know.&nbsp;</p>

<!--more-->

<p><img src="/assets/images/blog/git-workflow/branching-strategy.png" alt="" width="1081" height="904" /></p>
<h2>From Feature to Production</h2>
<h3>The Main Branches</h3>
<p>There are three main branches that we use in our central repository. We'll call that repo 'origin'. Our three main branches are development, staging and production.&nbsp;</p>
<p><strong>The development branch</strong>&nbsp;is used as one point to continually share code across the team. As a general rule code pushed out development branch should be code that will actually build and passes our unit tests. If we need to share more expermental code we will pull from eachother. The development branch commits are then occasionally merged into the staging branch when we feel the code is a candidate for release.</p>
<p><strong>The staging branch</strong> is monitored for changes by our build server. Our build server performs multiple functions including running our test suite and deploying to the staging environment. Once our tests are green and code has been deployed to the stanging environment we are able to perform our user acceptance testing. In addition to commits from the development development branch, bugfixes can also be merged directly to the staging branch. When a staging release is ready changes on the staging branch are then merged into production.</p>
<p><strong>The production branch</strong> (master) is the branch that reflects what is currently deployed to production. The production branch is also monitored for changes by our build server. Assuming our test suite continues to pass, the latest changes are deployed. In the event that there is a severe bug that need to be fixed immediately (a hotfix), a temporary hotfix branch can be created off the production branch. Changes in the hotfix branch can then be merged directly into production and then also merged directly into the development branch so changes are shared and propagated back through the workflow.&nbsp;</p>
<p>Note that while these branches comprise a majority of our development processes Git, however, is still a distributed version control system (DVCS). Having a central repository that we use for development and deployment in no way prevents us from pull changes directly from team members and other places.&nbsp;</p>
<h3>Posts in This Series</h3>
<p>Part 1: Overview<br /><a href="/steve/blog/git-branching-workflow-part-2-feature-branches">Part 2: Feature Branches</a></p>