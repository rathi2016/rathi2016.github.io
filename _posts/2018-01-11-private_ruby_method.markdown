---
layout: post
title:      "Private Ruby method"
date:       2018-01-11 22:05:00 +0000
permalink:  private_ruby_method
---


I was recently asked in one of the interview the differences between Private and Protected.Which gave me idea to write about Private method in this blog and I will write about Protected in my next blog.When a method is declared private in Ruby, it means this method can never be called with an explicit receiver. Any time we're able to call a private method with an implicit receiver it will always succeed. This means we can call a private method from within a class it is declared in as well as all subclasses of this class e.g

```
class A
 def public_method
  private_method
 end 
 
 private
 
  def private_method
	 puts "hello from #{self.class}"
	end
end
```

```
class B<A

 def public_method
  private_method
 end 
 
end 

```
**output**
```
 A.new.public_method
 B.new.public_method

 hello from A
 hello from B
```

However, if we try to use an explicit receiver, even in this situation where receiver is "self", the method call will fail e.g

```
class C< A
 def public_method
  self.private_method
 end
end

C.new.public_method
```
**output**

```
We will end up getting (NoMethodError)
```

Since we can't call a private method with an explicit receiver, we can never call it from outside the class hierarchy where it was defined.



