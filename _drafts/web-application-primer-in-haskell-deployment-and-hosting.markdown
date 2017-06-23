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

### Deployment and Hosting: GitHub, Docker and Heroku 

For better or worse I am an enterprise developer by trade. For me, an end-to-end solution isn't complete without a reliable build and deployment scenario. What I don't want to happen is to fall into the copy/paste deploy scenario. Github was the obvious choice especially when paired with Docker Hub. Github and Docker Hub have a nice integration that allows new builds to be kicked off automatically whenever code is committed. From there it was easy enough to pull down a pre-built image and deploy that to Heroku. This was important in terms of Haskell, because Heroku has a 15 minute build time limit. Deploying pre-built were an easy answer to. 
