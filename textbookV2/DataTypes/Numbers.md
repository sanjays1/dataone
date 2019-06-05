---
title: "Numbers"
date: 2019-05-30T18:56:32-04:00
draft: false
weight: 10 
---

We've used numbers in Python already but it's a good idea to take a step back to understand how Python treats the numbers that it sees. 

There's two main **data types** that Python can interpret as a number: `int` and `float`. 

- The `int` type, shortform for **Integer**, is assigned for integers (non decimal numbers).
- The `float` type, shortform for **Floating Point**, is assigned for decimal values (numbers that have a decimal point). 

As demonstrated in the last lesson, Python will immediately treat numbers without a decimal point as an `int`. 

~~~Python
meaning_of_life = 42
type(meaning_of_life)
~~~

~~~python
"int"
~~~

Similarily, numbers that have a decimal point are immediately a `float`.

~~~python
gpa = 4.0 
type(gpa)
~~~

~~~python
"float"
~~~

There are many useful methods and functions that can be applied towards `ints` and `floats`. We've showcased a couple useful ones for data science related tasks below: 

**`abs()`**

`abs()` returns the absolute value of an `int` or a `float`. 

~~~python
abs(-2/5)
~~~

~~~python
0.4
~~~

**`round()`**

`round()` returns the rounded value of an `int ` or a `float`. 

~~~python
round(1.65)
~~~

~~~python
2
~~~







