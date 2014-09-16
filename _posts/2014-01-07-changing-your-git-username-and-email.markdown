---
layout: post
title: "Changing Your Git Username and Email"
date: 2014-01-07
comments: true
---
<p>When Git is installed the first thing you probably want to do is set up your username and email. That is unless of course&nbsp;<em>git blame</em>&nbsp;always seems to out you for breaking the build!&nbsp;</p>
<p>My preferred route is to simple use the <em>git config&nbsp;</em>command. Basically, all the command is really doing is editing the .gitconfig file off of your root directory. You can edit that file directly, but I tend to find the command a little easier.&nbsp;</p>

<!--more--> 

<p><strong>View your .gitconfig file</strong></p>
<p>Here are a couple methods to view what you currenly have set up in&nbsp;your .gitconfig.&nbsp;<br />First, here's how we show our info via&nbsp;the config command</p>
<pre>git config user.name&nbsp;</pre>
<p><strong>Change your username</strong></p>
<p>Here is the command to change your username.</p>
<pre>git config --global user.name "Your Name"</pre>
<p><strong>Change your email</strong></p>
<p>Here is the command to change your email.</p>
<pre>git config --global user.email youremail@foo.com</pre>
<p><strong>How .gitconfig ends up looking</strong></p>
<p>So this is the final product. If you&nbsp;<em>cat</em> your ~/.gitconfig file you'll get something like this. Also, if you want to skip the commands you can maually edit and save the file to look like the output below.</p>
<pre>[user]<br />    name = Your Name<br />    email = youremail@foo.com</pre>
<p></p>