---
layout: post
title:  "Blocks in Ruby !"
date:   2017-08-26 03:26:51 +0000
---


![](https://media.giphy.com/media/Q6p2n7oHvEjok/giphy.gif)

Considered as a coolest feature in ruby is blocks also called as closures in some other languages, they are nothing but some codes written between braces or between **do..end** in simple language we can say blocks as the way of grouping statements. The code in the block is not executed at the time it is encountered first. Instead, Ruby remembers the context in which the block appears and then enters the method.

There are two main ways to receive blocks in a method in Ruby: the first is to use the yield keyword like so:

```
def method1
puts yield
end 

method1 {"Hello World!"}
#Hello World!
# => nil
```

The other is the prefix the last argument in a method signature with an ampersand which will then create a Proc object from any block passed in. This object can then be ececuted with the call method like so:

```
def method2(&block)
 puts block.call
end

method2 {"Hello"}
# Hello
#=> nil
```

 will write more about role of proc in my next blog.. 



