---
layout: post
title: Writing Testable Code
image: /assets/images/.png
date: 2020-01-09
tags: [architecture, testing]
---

Writing testable code (and the tests themselves) is not always the easiest task and there are many factors that can compound the difficulty: 

 - libraries and frameworks not condusive to testable code
 - architectural choices 
 - complex logic 
 - technical debt
 - culture
 - looming deadlines
 - incomplete or unclear requirements 

That is hardly an exhaustive list. While challenges writing or refactoring code may exist, the benefits are worth the effort. The benefits of having a robust suite of tests for a given project include providing the developer with confidence when refactoring, helping with clarity and identifying gaps in the requirements and intent, giving insight into the health of the application, and facilitating automated deployment pipelines.  


Guidelines
----------

### SOLID Design Principles

There are many books, articles, and posts regarding the SOLID Design principles so I'm not going to go into details. 

### Being Mindful of Dependencies  
(including hidden ones)

Dependency Inversion Priniciple basically already says this, but I wanted to back up that idea even further. 

Creation Logic separate from Application Logic 

Hidden Dependencies

### Leverage Dependency Injection

Strategy Pattern

Inversion of Control (IoC) Frameworks 


Working Around Un-Testable Code
-------------------------------

Sometimes there are libraries and dependencies that we must work around in order to write testable code. One example that comes to mind is when dealing with global context objects that would be called to retrieve some piece of state. The following is a contrived example, but think about the times you would write something like...

```csharp
public string GetFullName() 
{
  User currentUser = Context.User;

  return $"{currentUser.FirstName} {currentUser.LastName}"
}
``` 

If that context object is locked down to the point a user can't be set or the object itself can't be mocked or faked then the method itself becomes wholly un-testable. 

If you were trying to test that method

 - Adapter Pattern
 - Facade Pattern
 - 


Tests
-----

So what about the actual tests themselves?  

Generally tests will fall into three different categories: unit tests, behavior tests, and integration tests. Each type of test is necessary for proper test coverage.

### Unit Tests

Unit tests, however, are not the full picture.

### Behavior Tests
 - test behaviors across multiple areas of code
 - can involve the stake holders and product owners if you use something like SpecFlow

### Integration Tests


### Mocks and Fakes
 - what is a mock
 - what is a fake 

### Pragmatic Guidelines
 - In the real world, we often encounter projects and code that are written without testing in mind. 
 It's a chicken and the egg scenario - I want to refactor, but don't have unit tests to give me the confidence to do so and in order to create the unit tests I have to refactor. At some point, when the decision is made to add testing to a project, we have to bite the bullet and proceed with refactoring. 
 
 Proceed incrementally. The unfortunate reality is that a manual testing process needs to take place. 

 - How much is enough test coverage?
 
 - Serializing and Deserialize Data for Fakes
 
 - Find the right Frameworks, don't reinvent the wheel
