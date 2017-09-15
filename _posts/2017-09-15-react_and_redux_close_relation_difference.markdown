---
layout: post
title:  " React & Redux close relation/difference"
date:   2017-09-14 22:03:13 -0400
---

I specifically started writting this blog to write down what I started unfolding while seeing the difference of react & redux library. So first thing both are two separte javascript libraries. Then how are both related ? This blog can be helpful for begineers because when I started learing React then steped to Redux it became so confusing, that at one point I had no idea the difference and narrow gaps they hold. So enough about my confusing story let step to learn the difference they hold. 

1. Both React & Redux are two separate javscript libraries. and there functionality is independent. 
2. Redux can be considered as container holding states of an application, React on the other hand is the view part of an application. 

To explain it more clearly we can take an example of an application, say which has list of students name on one side of the page and on clicking the name it pulls out the details related to that student on the right side of the screen something like what it is showed below:

![](https://imgur.com/7LODGfk.jpg)

So to explain this in detail about how this application can be made, using specific redux part for storing all the states of the application or we can say the data part of the application. to show how the two are related refer below block diagram:

![](https://imgur.com/vDkOS15.jpg)

The right side are data part of the application and which is taken care by redux where as the view part on the left is taken care by react. so how the two linked? using react-redux which is third javascript helper  to give as the connectors.I hope to come with more specific details on my next blog.

