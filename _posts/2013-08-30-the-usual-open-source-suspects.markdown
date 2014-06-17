---
layout: post
title: "The Usual Open Source Suspects"
date: 2013-08-30
comments: true
---
<p>I consider myself a good developer. Perhaps I'm not a great one (yet), but to use a popular moniker these days I strive to be a software craftsman. I try to hone my software development skills every single day. With that in mind I have know I have a bad habit of automatically adding certain open source libraries to every new project I create. Steve Smith (<a href="https://twitter.com/ardalis/">@Ardalis)</a> would say I'm probably in the over zealous phase.</p>
<p>Admittedly, a lot of times the project I'm working on doesn't require the complexity that the following libaries introduce. I add them anyway and that's what makes it a bad habit. That being said I'm also not afraid to scrap code if the direction and architectual patterns these libraries may introduce just aren't working.</p>
<p>A little background on my list. For the most part I'm a web developer. I also work almost exclusively in C#. What I'm really trying to elicit here is to get feedback regarding what other libraries similar developers use on a frequent basis. Each one of the following libraries is available on Nuget. Here we go...</p>
<p><strong>NLog <br /></strong></p>
<p>ALL software should have logging. Logging is a solved problem. Get NLog. There's no need to reinvent the wheel.<br /><a href="http://nlog-project.org/">http://nlog-project.org/</a></p>
<p><strong>Ninject</strong></p>
<p>Far and away my favorite dependency injection / inversion of control container. It is just so easy to set up and so easy to use. Generally this is the first library I add even if the project doesn't require the extra complexity. <br /><a href="http://www.ninject.org/">http://www.ninject.org/</a></p>
<p><strong>AutoMapper</strong></p>
<p>If any sort of external data is involved, chances are so is automapper. I'm so over hand mapping DTOs and domain models.<br /><a href="http://automapper.org/">http://automapper.org/</a></p>
<p><strong>Dapper</strong></p>
<p>A beautiful Micro ORM. It's the one I would write if I were smarter. It's fast and close enough to the metal for my tastes.<br /><a href="http://code.google.com/p/dapper-dot-net/">http://code.google.com/p/dapper-dot-net/</a></p>
<p><strong>RestSharp</strong></p>
<p>Third Party Rest APIs anyone? Rest APIs are all the rage these days and it seems like every service has one. RestSharp is the kind of library that makes development life easy.<br /><a href="http://restsharp.org/">http://restsharp.org/</a></p>
<p>&nbsp;</p>
<p>So again... what else is out there that you other developers use in nearly every project?! I want to know!</p>