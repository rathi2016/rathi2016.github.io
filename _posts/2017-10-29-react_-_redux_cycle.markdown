---
layout: post
title:      "React - Redux cycle"
date:       2017-10-29 18:34:17 +0000
permalink:  react_-_redux_cycle
---


Today I decided to write blog based on my complete understanding of react-redux cycle and little bit about cons its hold. So the below diagram clearly shows the complete life cycle a react-redux application hold.

The purpose of using redux is to hold the applications state. One of the important feature of redux is that we can change state in an application in a very well defined pattern. Thats the pattern which we repeat over and over again.

![](https://imgur.com/8RFwOwE.jpg)

We wait for user to make change in the application, Which triggers action creator which in return produces action, action flows through middleware and eventually processed action flows into reducers and reducers later releases state which flows back into the react and user sees the required changes in the state of the application, ultimately this syncrounous process repeats over and over again. 

By syncrounous it means when we call an action creator we immediatly returns an action which instantly flows till it reaches reducers. Vanilla redux can only perform syncrounous action but not asyncrounous action which included fetching data from different channel, I would like to speak more about this behavior of redux and more on how this was eventually resolved using another set of library with react-redux which is known as redux-thunk in my next blog. 


