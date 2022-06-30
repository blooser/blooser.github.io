---
title: "Memory in Python"
date: 2022-05-30T09:39:44+02:00
draft: false 
---

One of the most important thing in the whole technical world is a memory. To allow computer programs to remember what they already compute, the memory is used. All what is about to be stored is located in the memory in a programming languages. The memory allows the machinr to learn, memory is extremely important in the programming world.

But some programming languages contains different ways and rules to interract with a memory.

### Strong typing

In C++ dominates strong typing, all types tells the compiler how they behaves in the memory, the type is a set of rules and one of the rule is how it interact with the computer's memory. 

```C++
char a // 1 Byte
int b; // 4 Byte
double c; // 6 Byte
```

All these declarations are an information how the data will melt away in the digital memory.

### One variable, one memory unit.

Let's think about variable as a memory, forming a new data in digital memory causes a new addresses we can inspect!

```c++
int a = 2;
int b = 2;

// Show addresses of the data.
std::cout << &a << std::endl
std::cout << &b << std::endl
```

And the output is. 

```txt
0x12345678
0x87654321
```

### Duck typing

There is a another style, where programmer doesn't need to take any care about typing, there is no need any knowledge to know how type behaves in the memory. In JavaScript types are guessed by the interpreter. 

```javascript
var number = 2.25; // It should be number!
```

The interpreter inspect the value we want to bind with the number label and guess the valid type of it. In this kind of memory dealing we as programmer don't need to think much about typing and their behavior in the memory, all the job is done by another program.

## Pythonic way of dealing with the memory.

However in the Python there is very interesting bunch of rules about the compuer memory. 

### Variable as one unit of the memory.

Let's take a glance about this simple instruction in C++

```C++
int number = 15;
```

This tells that number as memory unit is located somewhere and can be accessed(globally) by `number` word. We can access the address and manipulate it. 

```C++
number = 100;
```

A address contains a new value!

### Kind different

In Python, such instruction

```python
number = 15
```

Is different in way of thinking about the memory. Let's try to access the address, where 15 is located


```Python
print(hex(id(number)))
```

And this will show

```bash
0x12345678
```

Let's do the same example like in C++!

```Python
a = 25
b = 25
```

Check the address

```Python
print(hex(id(a)))
print(hex(id(b)))
```

This goes to show

```bash
0x12345678
0x12345678
```

Something weird happend!

#### Is this a problem?

No! That's the definition of memory dealing in Python! 

### What is a completed definition?

A memory work kind different in the Python. All declared and definied variables are just a labels attached to the value, one value can have multiple labels, so calling `a` and `b` show the same. Values belong to interpreter, he is the main owner of all objects, we as programmers can only show the value with a finger. 

Let's check an address of the value, we pointed in previous example.

```python
print(hex(id(25)))
``` 

Output is 

```bash
0x12345678
```

So, writing a instructions like:

```python
a = 25
b = 25
```

Means, we pointed to the same address object in memory.

## Mutable and immutable

One of the important feature about Python's memory is it ability to be immutable. There are more immutable types than mutable. Immutability has one big benefit, it is preventing the program before any memory violations, so, the immutabe types increases the program safety. This is the same like in functional programming languages, like Haskell, in functional programming languages we do not transform and mutable any data, we only creates new with different values. This works same in Python's immutable types.

### Immutable

In immutable types, we do not modify any value in particural memory's address. Any kind of operations where the effects is to modify the values, a new address is located and value put in the memory's location. 

```python
a = 5
a += 15
```

In this operation, a two memory cells were created, first our `a` label pointed to `5` value, next the `__iadd__` operation changed label to point to `20` value, which contains totally different address.

An immutable types are

```
int, double, str, tuple...
```

### Mutable

A mutable type like `list` gives us confidence that any modification operation will not change our memory address.

We can be sure that `items` 

```python
items = list(1, 2, 3, 4)
items.append(5)
```

Will be static in memory.

An mutable types are 

```
set, list...
```

## An memory guard

Python is a interpreter language, it does mean that our code in interpreterd by another program and proper operations are executed telling the computer what it should do to be correct with the story we write in our code using Python's code form. All the job about allocating and deallocating in responsible by the interpreter. Setting labels in the code only points to the objects, but the objects are carring by someone other. It is gives python's code ability to provide memory protection. And the memory is most important thing in the computer's world.




