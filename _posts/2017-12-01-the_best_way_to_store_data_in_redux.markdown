---
layout: post
title:      "The best way to store data in Redux"
date:       2017-12-01 06:37:26 +0000
permalink:  the_best_way_to_store_data_in_redux
---


So this blog is about how we store data in different reducer with redux u.e what kind of data structure we use inside of our reducers, the really simple pattern is to use an array. example will be if we have say array based storage then say if posts is an array holding individual post object

where "Post Model"

```
post = {
  id:1
	title: 'Sunshine'
	body:'It was such a shinny day...'
}

```
In case of **Array based storage**
```
state === {
posts: [post, post, post]
}
```

In case of **Object based storage**

```
state === {
  posts:{
	    14: [post with post-id]
			15: [post with post-id]
			}
			  }
```

