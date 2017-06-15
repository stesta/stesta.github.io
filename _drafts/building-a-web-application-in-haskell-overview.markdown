---
layout: post
title: "Web Application Primer in Haskell - Part 1: Overview"
date: 2017-06-14
comments: true
---

In this post we're going to go over the end-to-end process on how to build and deploy a web application using Haskell.<!--more--> I use the term "web application" instead of "website" because the implication is that we're building something more than just some static HTML and CSS. The intent is to build an actual application with dynamic front-end behavior that is in direct communication with the back-end code. 

In order to learn more about Haskell I decided to try and write a glorified Hello World program in the form of [Conway's Game of Life][gameoflife]. The original iteration was console based, but I quickly began yearning for something a little more gratifying visually. Hence, the Game of Haskell webapp was born!  

Technology Stack
----------------

It was important early on to make some very opinionated decisions regarding the technology stack. The following framework decisions represent my attempts at learning as many new things as possible with the caveat that these descisions should result in a new, reusable, robust and flexible toolbelt that can be applied toward future Haskell web development.  

### Programming Language: Haskell

I'm relatively new to it, but I love Haskell! I drank the kool-aid. As mentioned previously Haskell is the foundation we're building on.    

### Web Framework: Snap Framework

There were plenty of choices when it came to web frameworks: yesod, spock, snap, happstack - just to name a few. The [Haskell Wiki][webFrameworks] provides a list of descriptions and differences between some of the web frameworks out there. 

Ultimately, I landed on the [Snap Framework][snapFramework]. Snap seemed like it was lightweight enough to get up and running quickly without too much ceremony. Getting and HTTP server up and running along with some simple routing is a breeze. 

Additionally, Snap has this concept of [Snaplets][snaplets] that let you build self-contained bits of additional functionality. When it comes time to add in things like sessions and authentication you can do so easily via available snaplets - or build your own. Third-perty Snaplets for even more functionality seemed readily available and easy to find. 

### Templating: Heist 

For webpage and HTML templating [Heist][heist] was a natural choice because it was developed by the same folks who wrote Snap and you get it bundled for free. Heist as a template engine was a selling point for me regarding Snap. The `bind` and `apply-content` features make it possible to build a series of nested templates. When you couple all of that with `splices`, which basically let you call Haskell code from your templates, you have a really powerful system. 

### Communication Protocol: Websockets

I could have used REST here. It is easy to create an REST API as a Snaplet. For the purposes for the Game of Haskell, however, I needed something a little more real-time. 

Websockets are the no-brainer client-server communication protocol for the web. Packages are available to add websocket support in for Haskell as well as a corresponding Snaplet to plug in to our application. 

### Front-End Development: React 

This was sort of a fun one. Plenty of frameworks to choose from: Angular, React, Ember, Vue, Polymer... and on... and on... I picked React because I wanted to learn it and I heard it pairs well with Redux (which is next on my list). No other reason.

### Deployment and Hosting: GitHub, Docker and Heroku 

This was the final piece I struggled with. For better or worse I am an enterprise developer by trade. For me, an end-to-end solution isn't complete without a reliable build and deployment scenario. Everything built in Haskell boils down to an executable and what I don't want to happen is 

### Unit Testing: HSpec


 [gameOfLife]: https://en.wikipedia.org/wiki/Conway%27s_Game_of_Life  
 [webFrameworks]: https://wiki.haskell.org/Web/Frameworks
 [snapFramework]: http://snapframework.com/ 
 [snaplets]: http://snapframework.com/snaplets 
 [heist]: http://snapframework.com/docs/tutorials/heist