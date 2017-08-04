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

For better or worse I am an enterprise developer by trade. For me, an end-to-end solution isn't complete without a reliable build and deployment scenario. What I don't want to happen is to fall into the copy/paste deploy scenario. 

Step 1: source control...   
Github was the obvious choice. That decision was especially easy when I began considering Docker as a option for containerizing (that's a word, fight me) and deploying my application. Github and Docker Hub have a nice integration that allow new builds to be kicked off automatically whenever code is committed. Docker Hub is Docker's cloud based solution for building, versioning, and storing Docker containers. 

Once my Docker Hub was up and running I could commit code and have it built automatically by Docker Hub. From there it was easy enough to pull down a pre-built image and deploy that directly to Heroku. Deploying a pre-built image was important in terms of Haskell, because Heroku has a 15 minute build time limit. The Haskell/Docker builds usually blow that 15 minutes out of the water pretty quickly. The Haskell framework itself along with all the tooling can take a while to fully install.
