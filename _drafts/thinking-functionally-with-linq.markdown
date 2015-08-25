---
layout: post
title: "Thinking Functionally with LINQ"
date: 2015-08-25
comments: true
---

What would you do if I asked you to complete a task across a collection of objects without using a foreach loop? Or any loop<!--more-->ing construct at all for that matter? More importantly, why does it matter?  

In my last post, [Linq Helpers for IEnumerable](), I mentioned that LINQ to Objects was particularly appealing to me. Per MSDN (and they're spot on), LINQ queries offer three main advantages over the more procedural foreach loops:  

  1. They are more concise and readable, especially when filtering multiple conditions.  
  2. They provide powerful filtering, ordering, and grouping capabilities with a minimum of application code.   
  3. They can be ported to other data sources with little or no modification 

For me LINQ means that I can take piece of procedural code, such as a complex series of foreach loops, and break them down into clear declarative statements. Foreach loops certainly have their place, but can often be replaced by functional statements that make code much more readable. 

Let's look at an example of what I mean. The following example is a real-world example. I came across this bit of code in my day job. There's nothing inherently wrong with the code. Afterall, it does in fact work. It was just written by someone who is used to thinking more procedurally than functionally. 

Here is the basic gist of what needs to happen. In our system, Users can follow Accounts (companies). By following an Account a User is essentially following a list of people who are employed by that Account. 

To simplify what's going on, the code in question is attempting to get parse a list of paged search results. The list of results contains a list of Users who are following the searched account(s). For each person under those accounts some action is performed. Below is a simplified version (for demo purposes) of what was written. 

<script src="https://gist.github.com/stesta/3bfabceae3adc7462d3a.js"></script>    

