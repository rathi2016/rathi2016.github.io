---
layout: post
title:  "All about "self" in Ruby"
date:   2017-08-18 13:29:57 -0400
---


One of the important key word used most oftenly is `self`. The value of self changes with the context it is used. Every new Ruby programmer should keep in there mind these golden words in ruby: " Everything in Ruby is object"  

self is a special keyword which points to the object that "owns" the currently executing line of code.

In theory, self is pretty obvious. But in practice, it's easy for tricky situations to pop up. That's why I wrote this post

## Examples of self

Its better to learn new concepts in coding with examples because it's easy to see the differences in different senarioes

**Inside of an instance method**

In the code below, reflect is an instance method. It belongs to the object we created via Mirror.new. So self points to that object.

```
class Mirror
  def reflect
    self
  end
end

g = Mirror.new
g.reflect == g  o/p => true
```

**Inside of a class method**

For this example, reflect is a class method of Mirror. With class methods, the class itself "owns" the method. self points to the class.

```
class Mirror
  def self.reflect
    self
  end
end

Mirror.reflect == Mirror o/p => true
```


