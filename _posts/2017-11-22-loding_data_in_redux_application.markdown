---
layout: post
title:      "Loding data in Redux application"
date:       2017-11-22 15:29:18 +0000
permalink:  loding_data_in_redux_application
---


Dedicating this blog on story behind data loading in a redux application. 
1. We call an action creator. 
2. Action creator might use a http request library like axios.
3. Axios, which performs ajax request to some back-end server, where the request will be handled and give response.
4. Then response will end up in reducer and then the reducer will update state of the application with the new data which we got back from the server. 

![](https://imgur.com/cZ1P00i.jpg)

So this is what happens when ever an ajax request are performed. 

So the question arises i.e when to call action creator which is responsible for fetching data i.e we can call action creator from componentWillMount life cycle method, which is considered to be the most often used way to call action-creator even though this is not considered as a best practise because this does not lead to reusable component.


