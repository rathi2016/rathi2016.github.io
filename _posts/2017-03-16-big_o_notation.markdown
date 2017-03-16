---
layout: post
title:  "BIG O NOTATION "
date:   2017-03-16 04:03:11 +0000
---

Hope for the best and prepare for the worst ....  

Big-O notation used to be a really scary concept for me. I thought this is how "real" programmers talked about their code. It was all the more scary because the academic descriptions (such as Wikipedia) made very little sense to me. This is frustrating because the underlying concepts aren't actually that hard.

**Why do we want to analyze algorithm ? **

 Lets say we have task of going from city A to city B  and we have lot of transportation option like –
 
* 	We can walk from city A to city B 
* 	We can ride a Bike. 
* 	We can take a city Bus. 
* 	Drive a car  or you can fly. 
![](http://68.media.tumblr.com/c38c9d4ca1eece91110d3bdd035ca55e/tumblr_inline_ojfdfmgLdt1sndsvm_540.gif)
 Some of these make sense over other for example the city B is right across the road from city A which we can simply walk over than flying over but if the city B was across the country then buying plane ticket makes more sense than walking till the destination. 


 Computing algorithm is same as choosing the best mode of transmission to go from position A to B 
The major goals we think of while writing algorithm is –
**Completing task efficiently **
Efficiency is measured in terms of space and time, By analyzing, we can compare algorithm,and depending on the task pick the best ones. 


** What is running time analysis **?

![](https://media.giphy.com/media/NPXH9DAWLf5hm/giphy.gif)

 Determining the running time increase related to the size of the input value.
Input = n values  
Some definition to know –
Rate of Growth: the rate at which running time increases as a function of input. 
Lower order Term: When given an approximation of the rate of growth of a function, we tend to drop the lower order terms as they are less significant to higher order terms.

![](http://i.imgur.com/q8vutzO.png)

Therefore,we will only take Higher order term,   f(n) = n3 +  n  and  we right 
    big O notation as - O(n3) 
		
		Type of analysis – We can analyze an algorithm in 3 ways: 
![](http://i.imgur.com/IfFJ96k.png)  

  Most of the time we use the Big –Oh notation because this is the most practically used  one among the three. On best case, we cannot rely and average case is less useful than the average case, well this made me think about our real life situation of “Hoping for the best and preparing for the worst”  
	![](http://i.imgur.com/df4FgkW.png)
	
**Algorithm**
![](http://i.imgur.com/hJGySis.png?1)    







more algorithm in next blog ....











