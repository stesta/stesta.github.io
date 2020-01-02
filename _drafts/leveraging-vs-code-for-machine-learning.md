---
layout: post
title: Leveraging VS Code for Machine Learning
image: /assets/images/blog/thumbnails/haskell.png
date: 2019-12-17
---

VS Code is my code editor of choice. I use it constantly in my daily life as a software developer. However, I've found that it is incredibly useful when working in the machine learning realm as well. Jupyter Notebook are of course fantastic, but I've found the VS Code provides a more comfortable, familiar, and efficient environment.  

Python
------
This is a given if you plan on doing any machine learning work within VS Code. Not only does this library provide rich language support for python, but it also provides amazing support for the extras like [Jupyter Notebooks][notebooks] support, [Environment switching][environments] (virualenv, venv, pipenv, cona, pyenv), and [Refactoring][refactoring] utilities.  

Visual Studio IntelliCode
-------------------------
I would be remissed if I didn't mention a plugin that provides AI-assissted development features for Python in a machine learning blog post.  

Remote Development
------------------
The Remote Development plugin is magic! It provides the ability to connect VS Code to a remote machine via SSH, Containers, or even WSL (Windows Subsystem for Linux). Imagine being able to work inside the comfort of your local machine while everything within the context of VS Code is connected to a remote compute instance with more powerful hardware. This means that features like brosing the filesystem or using the console all operate as if you're working directly on the remote machine. 

- example: connecting to a google compute instance? aws? paperspace? 

Terminal
--------
A built in feature of VS Code, but one you should be using. (CTRL+`)(note: that's a backtick not an apostrophe)

TODO: expand on
- Manage multiple terminal windows, including split windowing
- New Terminals can be added to the menu

The integrated terminal is more than just a convenience feature. If you are leveraging remote development features the integrated terminal is another feature that functions as if you're actually working on the remote machine. Every command and task is executed on the remote instance in one seamless experience. 

Snippets
--------
Snippets provide a simple and efficient way to quickly write out common boilerplate code. 
I'm not going to dig into every collection of snippets out there. There are plugins and snippet collections for almost every framework or language that you can imagine. Whether you're working in Tensorflow, Pytorch, or literally anything else there are snippets out there to make your life easier. 

TODO: expand on
- what snippets do
- how to recognize and execute available snippets
- writing your own snippets

Noteworthy Mentions
-------------------
- Sand Dance
- Azure ML Studio

[notebooks]: https://code.visualstudio.com/docs/python/jupyter-support 
[environments]: https://code.visualstudio.com/docs/python/environments
[refactoring]: https://code.visualstudio.com/docs/python/editing#_refactoring