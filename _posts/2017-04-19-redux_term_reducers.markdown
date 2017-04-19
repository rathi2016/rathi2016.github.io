---
layout: post
title:  "Redux Term: “Reducers”"
date:   2017-04-19 02:25:14 +0000
---


Reducers are functions that take “state” from Redux and “action” JSON object and returns a new “state” to be stored back in Redux.
 
1. Reducer functions are called by the “Container” containers when there is a user action.


2. If the reducer changes the state, Redux passes the new state to each component and React re-renders each component

```
For example the below function takes Redux’ state(an array of previous todos), and returns a **new** array of todos(new state) w/ the new Todo added if action’s type is “ADD_TODO”.
const todo = (state = [], action) => {
 switch (action.type) {
  case ‘ADD_TODO’:
     return 
       […state,{id: action.id, text: action.text, completed:false}]; 
 }
```
