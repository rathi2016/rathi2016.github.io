---
layout: post
title:      "Flow of redux-thunk"
date:       2017-11-11 01:28:28 +0000
permalink:  flow_of_redux-thunk
---


I started speaking about redux-thunk in my previous blogs and also about dispatch. To clearify why we started using redux-thunk library with vanilla react-redux libraries . So the drop back of not being able to perform asyncronous fetch of data made redux-thunk very popular, because majority of the application build needs to fetch data through asyncronous channel in another word, where when we call action creator we actually wanna go and fetch some amount of data from some API, kind of some asyncrounous action and only when this request resolve when we are actually ready to create an action. 

So the main purpose of redux-thunk is to give as direct control over the dispatch method.

Lets assume user makes changes on the dom component-
.componet calls an action (example "fetchUsers"). 

.Axios makes request to API, usually all of our action creators expected to return a plane javascript object but because we are using redux-thunk we get an additional return type from our action creator of a function.

![](https://imgur.com/GSVFFkF.jpg)

Redux thunk which is our middle ware sees it as function but not a plain action and immediatly it invokes a function with a dispatch method. 

After a while a request is resolved.
