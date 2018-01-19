---
layout: post
title:      "Protected Ruby method"
date:       2018-01-19 19:47:34 +0000
permalink:  protected_ruby_method
---


My last blog was about the private method in ruby and with the continuation of same topic I will write about my understanding of protected ruby method and how is this different from private ruby method.

Protected methods are also a little different. We can always call a protected method with an implicit receiver. just like private,but in addition you can call a protected method with an explicit receiver as long as this receiver is self or an object of the same class as self. Let's see some of the example:

```
class A 
 def public_method
  method1
 end 
 
 protected 
 
 def  method1
  puts "hello from #{self.class}"
 end 
 
 end
```
```
class B < A
 def public_method
  method1
 end 
end 
```
```
class C < A
 def public_method 
  self.method1
 end 
end 
```
**Out when run all the above class will be:**

```
hello from A
hello from B
hello from C
```

Now, the call with the implicit receiver in class B succeeds but the call with the explicit receiver in class C also succeeds. Furthermore, doing the following is also fine:
```
class D 
 def public_method
  B.new.method1
 end
end 
```
out of which will be 

```
(NoMethodError)
```
In this case B.new is no longer the same type of object as self and so trying to call a protected method with B.new as the receiver -fails.So, I guess the inheritamnce hirarchy does actually play a role when it comes to access control in ruby

