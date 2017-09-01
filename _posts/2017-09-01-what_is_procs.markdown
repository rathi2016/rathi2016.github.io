---
layout: post
title:  "What is Procs ?"
date:   2017-09-01 16:45:11 +0000
---


**In simple english :** It is a ways of grouping code we want to run.

We discussed about blocks in my previous blog which actually gives me opennig line for this blog about procs " Blocks and procs are identical constructs except that a proc is an actual Ruby object and a block is just part of the syntax of a method invocation.

Just like blocks, a proc can be created in a couple of ways
```
Proc.new { hello_world }
proc { hello_world }

```
From the above defination its clear to us that blocks are not objects, but they can be converted into objects of class Proc. This can be done by calling the lambda method of the class Object. A block created with lambda acts like a Ruby method. If we don't specify the right number of argumets, we can't call the block.

Procs are not strict about number of argumets and neither are blocks. In contrast, our other flavor of code pod, the lambda, cares very much about the number of argument:

```
testing1 = lambda { |promise| puts "I #{promise}, I'll never die." }
testing.call()

**AugmentError: wrong number of arguments (0 for 1)**
```
Our code pod raises an error when we call it without fulfilling our promise on argument. It will raise a similar error if we pass too many arguments
```
testing1 = lambda { |promise| puts "I #{promise}, I'll never die." }
testing.call(true, false)
**AugmentError: wrong number of arguments (2 or 1)**
```
If you tell your lambda that it takes a specific number of arguments it expects you to follow through on that promise. None of this "take any arguments I want"

Heree's another example of passing arguments using lambda. 
```
a_Block = lambda { |x|"Hello #{x}}
puts a_Block.call'World'
#output is: Hello World!
```

