---
layout: post
title:  "Object Methods vs. Class Method"
date:   2017-08-11 18:47:11 +0000
---


![](https://media.giphy.com/media/UZ12sB7FMkjG8/giphy.gif)

Exactly this is how I use to feel about difference between object method and class method, with reading and coding over and over with time i have now clear idea of “ What is an object method ? " & " What is a class method ? "

So according to the defination of class we know its like a blue print, which means we can create an instances from it.
Lets take a look at example of house class:

```
class House
 def initialize(side)
  @side = side
 end 
 
 def area
  @side * @side
 end
end 
```
Once we create a house with `house1 = House.new(12)` we can use `house.area` to get area of the house represented by house1, in this case ` area` method is considered as **object method**.

However, methods are not just made available on object instances but is also available to class intself, so those method which are available to the class are called class method. 

  Here's a simple demonstration of a class method:
	
```
 class House
 
   def initialize(side)
      @side = side
     if defined?(@@counter)
       @@counter += 1
     else 
       @@counter = 1
    end 
  end 
	
 def self.counter
    @@counter 
 end
 
 def area
  @side * @side
 end
 
end 
```

```
a = House.new(12)
puts House.counter
b = House.new(14)
puts House.counter
``` 

In the above example it has three methods, two of them are object methods and this `self.counter` is class method,
self refer's to "class House", '@@'symbols represent class variable, they are useful for storing informatiopn relevant to all objects of a certain class.

Beacuse @@counter is a class variable, its already defined each time we create a new object and `self.counter` class method is used to show how many houses are created using ` House class `.

The take away from this blog is, all class methods starts with `self` cause this can be called on class itself but not the object instances and object methods are called on object created from class and these methods get available to them ones they are created.
	


