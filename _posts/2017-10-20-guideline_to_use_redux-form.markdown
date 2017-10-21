---
layout: post
title:      "Guideline to use redux-form "
date:       2017-10-21 01:34:08 +0000
permalink:  guideline_to_use_redux-form
---


When I started using "redux-form" I was not sure why we are using it at all, Why we ar not handling inputs manually like we did it in the past. So then I came across the guideline on how to use redux-form which clearly serves the purpose of "redux-form". 

These are the steps taken into consideration :

![](https://imgur.com/KOYTKZm.jpg?1)

1st step is to identify different pieces of state that exsists inside our form for example it can two state in case where we have to make form with Title text box and description text box this will be considered as two separate states.

2nd For each different piece of state we have we create <Field/> component, A field component is created by redux-form for us, all we have to do is let the field know what type of input to receive from user which can be a radio-button, check-box or some text input

3rd At some point in time the user is going to change the Field input.

4rth Internally redux-form automatically handles all this changes for us. In general we know what happens if we have to handle changes inside react i.e we use onChange handler, we set our state and then set the value to input ourself which means lot of work.all of this is set aside by the redux-form.

5th Finally when the user sets all the inputs and says ok I wanna submit the form and they are going to attempt to submit the form. 

6th  Now we are going to send two call-back to the redux-form that validtaes the different input that the users are provided and also if the submitted value is valid rect-redux also handles form submittal which the last stage where react-redux form  handes control over the form back to us which means the datas submitted by the user gets available to us to be saveed in our back end or do what ever we wanna do with data.




