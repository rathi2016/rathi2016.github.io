---
layout: post
title:  "More about modules in Ruby"
date:   2017-08-04 17:06:35 +0000
---


Adding functionality of modules into our classes, **to add** is called "**Mix in**".So in Ruby there is no concept of *multiple inheritance* instead Ruby's inheritance functionality only lets us create simple trees of classes. So now the question is why are we using module? In some cases it can be useful to share functionality between different classes. In this sense, modules act like a sort of "super" class and be called inside other classes, which provides the class power to access the methods the module offers. For example:

```

module ExtraPower
 def super_human_power
	self.class.to_s.upcase	
 end
end 

``` 

```
class Human
 include ExtraPower
end

x = Human.new
puts x.super_human_power
```
outputs //- "HUMAN"

![](https://media.giphy.com/media/cZ7rmKfFYOvYI/giphy.gif)

In this code, ExtraPower looks very much like a class, however, modules are organizational tools rather than classes themselves. The super_human_power method is part of module, and as we have included ExtraPower module inside Human, Human can use methods or powers provided my ExtraPower, here's another example:

```
module Spark
 def lightning
  puts "Bamm" 
 end
end

include Spark
lightning
``` 
output //- Bamm 

The example above shows that we can actually include module's methods in the current scope, which means we need not directly call module within a class. So we can say its kind of like a class, though you can use the methods directly.
```
Spark.lightning
```

When I realized the power of module, I could see the power provided by Ruby tools like* include* which is doing the heavy lifting of connecting module easily at any scope in which its called.
