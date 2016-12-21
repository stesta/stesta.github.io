---
layout: post
title: "Why a Clean Git History Matters"
date: 2016-11-22
comments: true
---

Ugly git histories annoy the hell out of me!!!
----------------------------------------------

... and they should annoy the hell out of you too!  

I can't stand looking at the `git log` (the history) for a project that contains a ton of merge commits causing complex branching paths which are impossible to follow. I completely understand that the history of the code base has no bearing on how the current iteration of the code functions - so here are the reasons I care:

### 1) Having a Clue  
For starters, it is a demonstration that you have some semblance of an idea of what you are doing; or that you have no clue what you are doing. Git is an amazing tool for source control. It provides many opportunities for complex source control management and workflow. By the same token it also provides many opportunities to screw things up. Having a clean and readable Git history is an indicator that the folks working with the code base are familiar with the tooling and haven't done anything detrimental. It's an indicator that everyone on the team is familiar with the workflows and processes that have been put in place. Note I used the word "indicator" because bad things still happen. Code may not be properly resolved during conflicts and public commits can get rebased while maintaining a clean history.

### 2) Change Logs  
Another reason the history matters are for change logs. The Git history can be leveraged to create accurate and detailed logs of any and all changes that are made. The logs are an often overlooked and valuable artifact to many different people. 
   - it gives have insight into the code we've written. It's easy to forget all the features that get built or bugs that get fixed. 
   - provide better estimates in the future
   - justify what gets billed to a client
   - gives the end user insight into new features that hopefully make their lives easier  

### 3) Roll-Back Plan
A clean history also allows for a better roll-back plan. Git provides some remarkable abilities to roll back and recover old interations of the code. A clean history helps us, the developer, to leverage those features of Git during those times when critical failures need to be addressed.

### 4) Code Recovery  
History allows provides a window into older code that we may have written and since cut out of the code base. Too often we fall into the trap of keeping unecessary code around. Never be afraid to scrap code! Move on. Git provides affords us a safety net. If there's ever a bit of code that needs to be brought back from the dead, it's possible.  

Visualizing Git History from the Command Line
---------------------------------------------

There are plenty of graphical tools out there that help visualize Git history, but did you know you can do that from the command line? Personally, I enjoy the command line. Git commands can be cumbersome at times, but it really helps me to be clear and certain about every action I am performing against the code base. That being the case it's nice not to have to leave the command line when I need to review the Git logs. 

    git log --graph --oneline --abbrev --color --decorate 

One additional little tip is that I like to set up that command as an alias to "gg" in the ~/.bashrc file.
 
    alias gg=git log --graph --oneline --abbrev --color --decorate 

this let's us just type "gg" (for git graph) into the command line instead of having to type out that long statement every single time. 

So What Does a Clean Git History Actually Lookg Like?  
-----------------------------------------------------

There is no concensus here. A clean history can mean different things depending on the workflow being used on a given project. Generally, however, I tend to stick to the following rules. 

 - do your work on a local copy of your feature branch
   - allows for interactive rebasing 
 - commits are tagged properly
 - prefer rebasing you local working branches
   - squash dev commits 
   - reword commit messages, add in smart tags and things that may help automate your workflow
 - use a merge commit when pulling code into your master or production branches 
   - I know I said merges were bad, but...
