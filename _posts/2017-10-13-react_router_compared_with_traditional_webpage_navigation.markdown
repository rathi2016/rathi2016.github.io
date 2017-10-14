---
layout: post
title:      "React Router compared with Traditional Webpage Navigation"
date:       2017-10-13 22:22:03 -0400
permalink:  react_router_compared_with_traditional_webpage_navigation
---


React has many library, one such library I came across was "react-router", As usual I started digging about it more and more and found why we are using react-router, than the traditional web page navigation.So today I decided to break down the differences via block diagrame:

**Traditional Webpage:**
- When user clicks on link,It issues a new request for some new web-page from some remote server.
- And HTML document is sent back to users browsers.

   ![](https://imgur.com/XFbwFcH.jpg?1)
	 
**React Router:**
The purpose of react-router is to find a way around the process opted by traditional webpage.

- Instead react-router intercept changes to URL. So instead of user trying to navigate to different page it stops the user to navigate and update the compont present on the current web-page.

![](https://imgur.com/vZeDFiR.jpg?1)

Block diagram above explains the flow of request and updation of react component.


