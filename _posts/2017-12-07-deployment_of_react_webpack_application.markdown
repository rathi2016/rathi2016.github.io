---
layout: post
title:      "Deployment of React,Webpack application"
date:       2017-12-08 02:18:06 +0000
permalink:  deployment_of_react_webpack_application
---


When we are talking about deploying or application we have two separate pipelines, 

* Development pipeline
* Production pipeline

So Development pipeline is more about how we are writing our code, testing our code in a local host browser i.e something which is required during devlopment process of an application & there is completly different process involved in production enviroment there are many differnt ways to do deployment, but one such most commonly used deployment process is using Herokku. 

Below is the process showing devlopment and production pipeplines:

![](https://imgur.com/9muJERl.jpg)

Lets talk about what is happpening is development process first step including having our code i.e repository holding our application which  uses webpack so when we run npm start which causes all of the code to be processed by webpack(i.e dealing with all import, export statement and forming desired flow of data) then webpack hands oof this built file to local-host 8080 which means gives something to visit our browser to checkout our application as we are devloping it.

Where as in case of production pipeline it include one shot deployment in the platform which runs aour application and in this case we are specifically talking about Herokku. The first step in the process is:
* Pushing our local repository or we can say it or code into Hrokku . 
* Herroku will install all the required dependencies using npm like react or redux. 
* the third and the most important steps include manually describing some amount of configiguration like telling herroku this is how we build and run our program.

