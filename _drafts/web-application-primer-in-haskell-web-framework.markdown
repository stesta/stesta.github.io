---
layout: post
title: "Web Application Primer in Haskell - Web Framework"
date: 2017-07-04
comments: true
thumbnail: /assets/images/blog/thumbnails/haskell.png
---

There are plenty of choices when it comes to Haskell web frameworks: yesod, spock, snap, happstack - just to name a few.<!--more--> The [Haskell Wiki][webFrameworks] provides a list of descriptions and differences between some of the web frameworks out there. 

- Heroku  
  - Docker  
    - React + ES6  
    - **Snap Framework + Heist + Websockets**
    - [Haskell][goh-haskell]

Web Framework: Snap Framework
-----------------------------

I spent a little bit of time researching the various frameworks to determine if there was an outright favorite. Nope. It was a bit of a tough decision. I wanted a framework that was easy to get up and running quickly and would be extensible enough for future projects. Yesod seemed like a great option, but they lost me on the [Shakespearean Template Languages][shakespearean-templates]. That particular flavor of templating just isn't for me. Maybe I'll change my mind in the future. I suggest you decide for yourself what works best for you and your situation.

Ultimately, I landed on the [Snap Framework][snapFramework]. For me, the Snap felt lightweight enough to get up and running quickly without too much ceremony. Getting an HTTP server up and running along with some simple routing is a breeze. Additionally, Snap's templating system (Heist) felt very natural to me. 

As far as extensibility goes, they have a concept of [Snaplets][snaplets]. Snaplets allow you to build self-contained bits of additional functionality. When it comes time to add in things like sessions and authentication you can do so easily via built-in Snaplets (or write your own). Third-party Snaplets seemed readily available and easy to find. 

On to the code!

### Setting up a Basic HTTP Server



### Templating via Heist 

For webpage and HTML templating [Heist][heist] was a natural choice because it was developed by the same folks who wrote Snap and you get it bundled for free. Heist as a template engine was a selling point for me regarding Snap. The `bind` and `apply-content` features make it possible to build a series of nested templates. When you couple all of that with `splices`, which basically let you call Haskell code from your templates, you have a really powerful system. 

### Setting up Websockets

I could have used REST here. It is easy to create an REST API as a Snaplet. For the purposes for the Game of Haskell, however, I needed something a little more real-time. 

Websockets are the no-brainer client-server communication protocol for the web. Packages are available to add websocket support in for Haskell as well as a corresponding Snaplet to plug in to our application. 

[webFrameworks]: https://wiki.haskell.org/Web/Frameworks
[shakespearean-templates]: https://www.yesodweb.com/book/shakespearean-templates
[snapFramework]: http://snapframework.com/
[snaplets]: http://snapframework.com/snaplets
[heist]: http://snapframework.com/docs/tutorials/heist
[goh-haskell]: /steve/blog/web-application-primer-in-haskell-programming-language  
