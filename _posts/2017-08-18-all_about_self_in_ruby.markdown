---
layout: post
title:  "All about "self" in Ruby"
date:   2017-08-18 13:29:57 -0400
---

One of the important key word used most often is 'self'. The value of self changes with the context it is used. Every new Ruby programmer should keep in there mind these golden words " Everything in Ruby is object"

*self is special keyword which points to the object that "owns" the currently executing line of code*.

In theory, self is pretty obvious. But in practice, it's easy for tricky situations to pop up. That's why I wrote this post. 

## Examples of self
It's better to learn new concepts in coding with examples because it's easy to see the differences in different scenarious.

**Inside of an instance method**

In the code below, reflect is an instance method. It belogs to the object I created via Mirror.new. So self points to that object.
```
class Mirror
 def reflect
  self
 end 
end 
```

```
g = Mirror.new
g.reflect == Mirror o/p => true
```
It shows the same with "class" method inside of modules. For example:

```
module Mirror
 def self.reflect
  self
 end 
end

```

Remember, classes and modules are treated as object in Ruby. So this behavior isn't that different from the instance method behavior we saw in the first example.

**Inside of a class or module definition**

One feature of Ruby that makes it such a good fit for frameworks like Rails is that we can execute arbitary code inside class and module definitions. When you put code inside of a class/module definition, it runs just like any other Ruby code.

As we can see below, self points to the class or module that's in the process of being defined.

```
class Mirror
 self == Mirror o/p => true
end 
```

```
module Glass
 self == Glass o/p => true
end
```


