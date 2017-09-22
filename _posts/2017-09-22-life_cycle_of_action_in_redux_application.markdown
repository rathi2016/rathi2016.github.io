---
layout: post
title:  "LIFE CYCLE OF ACTION IN REDUX APPLICATION"
date:   2017-09-22 21:42:56 +0000
---


One of the most important concept I came across while explaing one of my redux application was life cycle of an action.

![](https://media.giphy.com/media/pJSKQUb0ytPKo/giphy.gif)

I am going to use the same example of an application which I used on my previous blog i.e; a Student detail app,where there is list of students displayed on one side and upon clicking on the name right side displays detail about selected student.

![](https://i.imgur.com/7LODGfk.png)

Few keywords which we use most often while writting a redux based application. 

**Component**: Term used in context with *React* part of application, which are just content displayed on screen. 

**Container Component**:  A container component will grab data from state via mapStateTp Props. The component will then pass necessary portions of that data down its children as props.

A container component is also responsible for dispatching actions that make changes to application state.

**Action Creator**: Its just a function which returns javascript object and those object are called action.

**Action**: An action is just an object that flows through all redjucers.

**Reducers**: they uses action to produce different value for its particular piece of state.

**Life Cycle of Action Steps :**

. Any event started by user like onClick, onSubmit etc etc triggers *Action creator* 

. Action Creator returns object which has property type which shows what event was triggered by user and other property like payload i.e actually a key whose value is an action (an object).


```
function ( return {

 type: STUDENT_SELECTED
 payload: { name: 'Student 1' }

})
```


. Action `{ name: 'Student 1' }` is sent to all reducers.

. Active Student Reducer has switch statements which on the bases of what event was triggered as in this case it is BOOK_SELECTED returns new state which need to be updated in container component. 

. All Reducers processed the action & returns new state. New state get assembled and notify the containers of the changes to state. On notification containers rerenders with new props.

This was simple example showing a complete action's lifecycle, from the origin of event till the new state update of component.
