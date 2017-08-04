---
layout: post
title: "Web Application Primer in Haskell - Front End"
date: 2017-06-14
comments: true
thumbnail: /assets/images/blog/thumbnails/haskell.png
---

- Heroku  
  - Docker  
    - **React + ES6**  
    - [Snap Framework + Heist + Websockets][goh-web]  
    - [Haskell][goh-haskell]

### Front-End Development: React & ES6

This was sort of a fun one. Plenty of frameworks to choose from: Angular, React, Ember, Vue, Polymer... and on... and on... I picked React w/ ES6 because I wanted to learn it and I heard it pairs well with Redux (not used in this project, but it's next on my list). No other reason.

I also wanted to make use of ES6. Again, the point here was really to increase my own familiarity with the technology. In order to leverage all of the features of ES6, System.js and Babel were taken on as dependencies. System.js was chosen specifically as the module loader so that the ES6 import syntax could be used. I much prefer the ES6 import syntax as opposed to using something like require.js. 

The web socket workflow on the front-end is fairly straight forward. Once the page loads, an attempt to establish a connection is made. The front-end client sends across an integer to request a specific generation of the game board. After a response is received the new living cells are rendered to the screen. The generation integer is incremented and another request for the next board generation is sent. 

An HTML5 canvas was used to render the game board to the screen. A little bit of simple math and the `strokeRect` and `fillRect` methods were essentially all that was needed to get grid on the screen. 

As mentioned in the previous post, heist was used as a templating engine. I just wanted to get a basic feel for Heist so the templates were not at all complicated. A `base.tpl` served as the master page. The `index.tpl` inherited from that master/base page. 

[goh-web]: #
[goh-haskell]: #