---
layout: post
title:  "Initialize Method"
date:   2017-07-06 13:55:34 +0000
---


When writing Ruby class we end up using initialize method, and Often as new programmer we assume it to be a method for initializing instance variable i.e to give default value to instance variables. 

Well Its true but Initialize method is more than that, It is a **Call back method** because it is automatically invoked every time the #new method is used to create a new instance of the class.
```
class Dog 
attr_accessor :name, :breed

 def initialize(name , breed)
  @name = name 
  @breed = breed 
 end 
 
end 
``` 
As in the above Dog class every time it is used to instantiate a new instance of this class, argument which is passed example `duffy = Dog.new(duffy, lab)` As soon as .new method gets argument it invokes initialize method. 

We can also think of initialize method as **constructor method**. A constructor method is invoked upon the creation of an instance of a class and used to help define the instance of that class.

They are also ** Private method.** ( why it is called private method, cause the variable initialized inside this method cannot be re initialized ) example -  If we call 

  Dobby = Dog.new
  Dobby.initialize
	
	and then if we try to run our ruby dog.rb  file . we will get to see message something like this -
	
	`dog.rb:240:in <main>: private method initialize called for #<Dog:0x007f9b6d05dc40> (NoMethodError)



