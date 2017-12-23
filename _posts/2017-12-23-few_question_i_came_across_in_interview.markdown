---
layout: post
title:      "Few question I came across in Interview"
date:       2017-12-23 15:39:44 +0000
permalink:  few_question_i_came_across_in_interview
---


**1.Difference between Composition and Inheritance?**

This was the question asked to me during one of the interview, I was not sure about the exactly how I will be explaning, therfore I did some research and came up with some conclustion:

* **Composition** is when we design a type around what they are on the other hand 
* **Inheritance** is when we design a type based on what they do.

**2.About Reduce Higher order function**

The magical trick which make me use them every where I use as a trick for array transformation:

Reduce is the multi tool list transformation,i.e it can be used to perform any list transformation infact we can use reduce to implement map, filter,reject or any other list transformation. 

**3.Clousure**

In javascript functions are not just functions but they are also closures, now what does this means is that the function body has acess to varibale that are defined outside the function, lets look at this code:

```
var food = 'cake'
function eatMe( ){
 console.log( 'I am eating' + food + '!')
 }
 eatMe( )
```
**output**
```
I am eating cake!
```

Looking at the output its very clear that the eatMe function has acess to variable declared outside of the eatMe( ) function this process of being able to acess the outer scope is called Closure.








