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

It works the same with "class" methods inside of modules. For example:

```
module Mirror
  def self.reflect
    self
  end
end 
Mirror.reflect == Mirror o/p => true
```

Remember, classes and modules are treated as objects in Ruby. So this behavior isn't that different from the instance method behavior we saw in the first example.

**Inside of a class or module definition**

One feature of Ruby that makes it such a good fit for frameworks like Rails is that you can execute arbitrary code inside class and module definitions. When you put code inside of a class/module definition, it runs just like any other Ruby code. The only real difference is the value of self.

As you can see below, self points to the class or module that's in the process of being defined.
```

class Mirror
  self == Mirror o/p => true
end 

module Glass
  self == Glass o/p => true
end 
```

**Inside mixin methods**

Mixed-in methods behave just like "normal" instance or class methods when it comes to self. This makes sense. Otherwise the mixin wouldn't be able to interact with the class we mixed it into.

*Instance methods*

Even though the reflect method was defined in the module, its self is the instance of the class it was mixed into.

```

module Reflection
  def reflect
    self
  end
end 
```

```
class Mirror
  include Reflection
end

g = Mirror.new
g.reflect == g o/p => true
```

**Class methods**

When we extend a class to mix in class methods, self behaves exactly like it does in normal class methods.

```
module Reflection
  def reflect
    self
  end
end 

class Mirror
  extend Reflection
end

Mirror.reflect == Mirror o/p => true
```

**Inside the metaclass**

Chances are you've seen this popular shortcut for defining lots of class methods at once.

```
class Mirror
  class << self 
    def method1
    end

    def method2
    end
  end
end
```

The `class << foo` syntax is actually pretty interesting. It lets you access an object's metaclass - which is also called the "singleton class" or "eigenclass." I plan on covering metaclasses more deeply in a future post. But for now, you just need to know that the metaclass is where Ruby stores methods that are unique to a specific object.

If you access self from inside the `class << foo` block, you get the metaclass.

```
class << "test"
  puts self.inspect
end
```


**Outside of any class**

If you're running code outside of any class, Ruby still provides self. It points to "main", which is an instance of Object:

`puts self.inspect o/p => main`


