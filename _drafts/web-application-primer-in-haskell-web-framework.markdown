---
layout: post
title: "Web Application Primer in Haskell - Overview"
date: 2017-06-14
comments: true
---

- Heroku  
  - Docker  
    - React + ES6  
    - Snap Framework + Heist + Websockets  
    - Haskell

### Web Framework: Snap Framework

There were plenty of choices when it came to web frameworks: yesod, spock, snap, happstack - just to name a few. The [Haskell Wiki][webFrameworks] provides a list of descriptions and differences between some of the web frameworks out there. 

Ultimately, I landed on the [Snap Framework][snapFramework]. Snap seemed like it was lightweight enough to get up and running quickly without too much ceremony. Getting and HTTP server up and running along with some simple routing is a breeze. 

Additionally, Snap has this concept of [Snaplets][snaplets] that let you build self-contained bits of additional functionality. When it comes time to add in things like sessions and authentication you can do so easily via available snaplets - or build your own. Third-perty Snaplets for even more functionality seemed readily available and easy to find. 

### Templating: Heist 

For webpage and HTML templating [Heist][heist] was a natural choice because it was developed by the same folks who wrote Snap and you get it bundled for free. Heist as a template engine was a selling point for me regarding Snap. The `bind` and `apply-content` features make it possible to build a series of nested templates. When you couple all of that with `splices`, which basically let you call Haskell code from your templates, you have a really powerful system. 

### Communication Protocol: Websockets

I could have used REST here. It is easy to create an REST API as a Snaplet. For the purposes for the Game of Haskell, however, I needed something a little more real-time. 

Websockets are the no-brainer client-server communication protocol for the web. Packages are available to add websocket support in for Haskell as well as a corresponding Snaplet to plug in to our application. 