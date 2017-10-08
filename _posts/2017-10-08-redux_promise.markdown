---
layout: post
title:      "Redux Promise"
date:       2017-10-08 19:02:47 +0000
permalink:  redux_promise
---


My previous blog was all about middleware but with no example of such, So here is this blog speaking all about one such example of middleware i:e Redux promise. So what does this do ? 

Recall on what a middleware is " A function that takes in action and depending on the actions type & actions's payload middleware can manipulate these data before they are sent to reducers. "

Working of Redux-Promise:

- When Redux-Promise receives an action, it looks at paload's property.

- If the payload is a promise the redux-promise stops it entirely. 

- Ones th request finishes, it dispatches a new action of same type but with a payload of the resolved request, i:e it unwraps the promise for us.

**Block Diagram Representing the flow :**

![](https://imgur.com/HpiNSoz.jpg?1)
