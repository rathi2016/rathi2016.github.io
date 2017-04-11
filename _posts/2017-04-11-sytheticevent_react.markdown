---
layout: post
title:  "SytheticEvent(React)"
date:   2017-04-11 03:10:39 +0000
---


	 In React, when we specify an event in JSX like we did with onClick, we are not directly dealing with regular DOM events. Instead, we are dealing with a React-specific event type known as a SyntheticEvent. Your event handlers don't get native event arguments of type MouseEvent, KeyboardEvent, etc. They always get event arguments of type SyntheticEvent that wrap your browser's native event instead. What is the fallout of this in our code? Surprisingly not a whole lot.

	 
Each SyntheticEvent contains the following properties:

![](http://i.imgur.com/KXn5rjQ.png)
These properties should seem pretty straightforward...and generic! The non-generic stuff depends on what type of native event our SyntheticEvent is wrapping. This means that a SyntheticEvent that wraps a MouseEvent will have access to mouse-specific properties such as the following:

![](http://i.imgur.com/B9f1x6U.png)

Similarly, a SyntheticEvent that wraps a KeyboardEvent will have access to these additional keyboard-related properties:

![](http://i.imgur.com/D0ZeIEB.png)


In the end, all of this means that you still get the same functionality in the SyntheticEvent world that you had in the vanilla DOM world.




			 

