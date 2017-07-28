---
layout: post
title:  "Why using Module in Ruby ? ? ?"
date:   2017-07-28 16:14:15 -0400
---



Realized that more you learn about certain subject the clearer the concepts get, one such concept in ruby was about module.When came across the term module for the first time I made a rough sketch about how module work in my head and according to that sketch it was just the helper method which i can call in my current method. But we as the ruby coder know ruby is not just about methods but it has classes too. When took further steps closer to the understanding about the ruby it was more like research on certain species,ooh yes!!!! MODULE is different species

![](https://media.giphy.com/media/12M5oHBISJLdUA/giphy.gif)



> I loved this book by Peter Cooper, to explore about Ruby where defination for module is- Modules provide a structure to collect Ruby classes, methods & constants into a single, separtly named & defined unit.
> So first note about modules, why we use them? - to avoid clashes with existing classes, methods and constants

**Namespaces**

example Lets say we have two methods and both have same name “timer” but both in different file called example1.rb and example2.rb

**example1.rb**

```
def timer

 time1 = Time.new
 puts "Current Year: " + time1.year

end 
```

**example2.rb**

```
def timer

 time2 = Time.new
 puts "Current Day : "+ time2.day

end 
```
example1.rb have functionality to put current year and example2.rb to put current day when it is called but both have same method name prity much by now you can smell the coming problem, & if we end up[ requiring both the files i.e

```
 require 'example1.rb'
 require 'example2.rb'

 puts timer
```

Conflict!!!! result in example2.rb will be loaded & this situation is known as name conflict. The same situation can cause clashes if we end up using same class name. If a class Poem is defined in one external file and also in a second external file, then class Poem when called can be a bad mix of two. Some time we might end up getting intended behavior, but in other cases this can cause problem.

Module can help solve these conflicts: ex1.rb

```
module Year
  def timer
	  time1 = Time.new
    puts "Current Year: " + time1.year
	end 
end 
```

**ex2.rb**

```
module Day
 def timer
  time2 = Time.new
  puts "Current Day : "+ time2.day
 end 
end 
```

So in order to call result specific to functionality we made two separate module taking care of individual functionality,

```
puts Year.timer
puts Day.timer
```
I love this example of class Ruler which shows how module help is creating namspacing with same class name

```
module ToolBox
 class Ruler
  attr_accessor :length
 end
end
```
```
module Country 
 def Ruler
  attr_accessor :length
 end 
end 
```
This is how we can call class with same name but kept in different module

  ```
 a = ToolBox::Ruler.new
	 a.length = 50
	 
	 b = Country::Ruler.new
	 b.name = "Alexander"		
```				
							
In the next blog I will take simple example like these and explain Mixins.Till then keep digging information to make a pile of knowledge in your brain.


