---
layout: post
title: Writing Testable Code
image: /assets/images/.png
date: 2020-01-09
tags: [architecture, testing]
---

The Importance of Tests
 - confidence when refactoring
 - clarity regarding requirements and intent
 - insight into the health of the application

Types of Tests
 - Unit Tests
 - Behavior Tests
 - Integration Tests

Dependency Injection and Inversion of Control
 - what is a dependency?
 - "Hidden" dependencies (`new` is obvious): the clock, static "context" objects 
 - Strategy Pattern
 - IoC Containers
 - Scopes/Lifetimes
 - Frameworks

Mocking and Fakes
 - what is a mock
 - what is a fake 

Pragmatic Guidelines
 - In the real world, we often encounter projects and code that are written without testing in mind. 
 It's a chicken and the egg scenario - I want to refactor, but don't have unit tests to give me the confidence to do so and in order to create the unit tests I have to refactor. At some point, when the decision is made to add testing to a project, we have to bite the bullet and proceed with refactoring. The unfortunate reality is that a manual testing process needs to take place. 
  - How much is enough test coverage?

