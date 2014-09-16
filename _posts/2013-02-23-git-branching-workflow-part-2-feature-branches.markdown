---
layout: post
title: "Git Branching Workflow - Part 2: Feature Branches"
date: 2013-02-23
comments: true
---
<h2>Working With a Feature Branch</h2>
<p>Disclaimer: The following section of our workflow includes rebasing. Rebasing can be a dangerous operation of you don't know what you're doing. Commits can be lost and you can make life hell for a developer who is working off of a commit you've borked. So follow the golden rule...&nbsp;<strong>Do not rebase commits that you have pushed to a public repository</strong>. Thanks!</p>

<!--more-->

<h3>Create a Feature Branch</h3>
<p>Every journey has to start some where. Our journey starts with a feature branch. A feature branch affords us the ability to develop a new feature without polluting main development branch.&nbsp;</p>
<pre>git checkout -b feature_name dev</pre>
<p>At this point we've created and checkout a new branch based off of our development branch. Now we can continue to work on this branch without affecting our mainline dev branch.</p>
<h3>Rebasing a Feature Branch With the Latest Code</h3>
<p>As we work on our new feature, there will undoubtedly be code that is pushed up to origin/development by other developers. Pulling that code into our feature branches gets us a couple of things. First, having the latest development branch code while were working on a feature makes merging easier. Second, if we rebase the latest code into our feature branch we avoid some extraneous merge commits that add additional clutter to the history.</p>
<pre>// get the latest changes<br />git checkout development<br />git pull -u origin development<br /><br />// rebase the latest changes into our feature branch<br />git checkout feature_branch<br />git rebase development</pre>
<h3>Merging a Feature Branch (using interactive rebase)</h3>
<p>Additionally, there are feature branch benefits when it comes time to push out our changes.&nbsp;The old addage 'commit early, commit often' holds true during development. Many commits give developers the flexibility and security they need. When it comes to the main branches, though, all of those developmental commit just tend to clutter up the history. What we really want in the main branches is a single commit that represents the feature we've built. This is where interactive rebasing comes in.&nbsp;</p>
<p>Here's what we're going to achieve. We're going to rewrite our feature history to include the latest changes from the development branch and at the same time we're going to 'squash' all of our commits in our feature branch into a single commit. Here's how we do this.</p>
<pre>// get the latest changes, same as before<br />git checkout development<br />git pull -u origin master<br /><br />// perform the interactive rebase, notice the extra '-i'<br />git checkout feature_branch<br />git rebase -i development</pre>
<p>This will present us with a editor that will allow us to 'pick' and 'squash' commits. For our team generally we will 'pick' the first commit and 'squash' all of the other commits into that first commit. All that's needed is to rename 'pick' to 'squash' at the beginning of all the commits you're squashing. See the screen shot below.&nbsp;</p>
<p><img src="/assets/images/blog/git-workflow/git-rebase.png" alt="" width="843" height="711" /></p>
<p>After you save git will then perform the rebase and squashing! All that's needed is to merge your feature branch into the local/development branch and push it up to origin/development to share with the rest of the team!</p>
<h3>Posts in This Series</h3>
<p><a href="/steve/blog/git-branching-workflow-part-1-overview">Part 1: Overview</a><br />Part 2: Feature Branches</p>