---
layout: post
title:      "Role of dispatch"
date:       2017-11-06 04:23:22 +0000
permalink:  role_of_dispatch
---


This Library is used for performing asyncronous action creator. The purpose of redux think is to give us complete control over dispatch method. The dispatch method is a method a part of redux store. The action being called is sent to a dispatch method. We can consider dispatch as a big funnel of sort. 

We call an action creator, it returns an action which falls into the dispatch. Which makes sure the action gets sent off to all the different reducers. 

![](https://imgur.com/yj4Nwb4.jpg)

