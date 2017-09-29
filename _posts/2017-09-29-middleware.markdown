---
layout: post
title:  "Middleware"
date:   2017-09-29 23:58:03 +0000
---


In my previous blog about Life cycle of Action in Redux there was important part that I missed  which is use of middleware. So now the question is **What is Middleware?** 

I would love to explain how middleware as the name suggest comes between action creator and reducers so any actions realized out of action creator must pass through middleware, **So what does middleware do?**

So Middleware are function  & depending on the actions  type & actions payload or any number of factors the middleware can choose to let the action to pass through it. and also have all right to manipulate the action which passes through. So these are the things what it does to action passing through it:

```
1. Manupulate the action. 
2. Can console log it 
3. can stop it all together
```

It can do all this little task on these actions before they reach any reducers. We can consider middleware as gatekeeper(i.e They stop inspect & give instruction )

What it says on Redux documentation:
```
"It provides a third-party extension point between dispatching an action, and the moment it reaches the reducer"
```
