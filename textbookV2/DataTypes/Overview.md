---
title: "Overview"
date: 2019-05-30T16:13:46-04:00
draft: false
weight: 5
---

When writing any value in Python, a **type** will be assigned to it. Whether it be a raw number or anything stored inside a variable, Python will "guess" what **type** your data should be based on certain characterstics within the data itself. 

The built in `type` function can be used to tell what type a piece of data is (as demonstrated below). 

~~~python
meaning_of_life = 42
type(meaning_of_life)
~~~

~~~python
"int"
~~~

We will learn about what `int` and other possible types mean in the following lessons! 

### Using Methods on Data

The existence of types is a powerful feature and lets us use **methods** to manipulate our data. Certain **methods** only work for specific data types so it's important to know what type your data is currently formatted in (`type` can be helpful here.)

Let's look at the `sqrt` method which takes the square root of number and use it to take the square root of `9`. 

~~~ python
import math 
math.sqrt(9)
~~~

~~~python
3.0
~~~

There's two things to take note here (beyond the correct answer of `3.0`). 

1. In order to use the `sqrt` function we had to use an **import statement**. This is a fairly common practice in Python; while there are some methods that are built into the language, the vast majority of methods need to be imported in order to be used. 

   * In this example, we used `import` to bring in `math`, one of many **modules** that are avalible in Python. **Modules** are a *collection of methods* and importing one module lets you use all the methods within it. 	

     

2. We used **dot notation** `.` to actually take the square root of the number. Because the `sqrt  ` method came from within the `math` module and wasn't built in, Python needs to told to look within `math` to find it. This "search" was done using a *module.method* syntax. 

   * Dot notation will be seen and used quite a bit, it's the main way we use methods to manipulate data. 

### Functions vs. Methods

In chapter three we introduced the `print` **function** which took in a phrase (inside of a set of parenthesis) and printed it back to us. We also showed off the `type` **function** earlier, which takes in data and returns back the Python type associated with it. 

Don't both these functions act similarily to our `sqrt` **method**? Chiefly, taking in data and transforming it for us? 

While there's a Python specific difference between functions and methods, for all practical purposes they do *exactly the same thing*, transform data. 

One key usage difference though between function and methods is that we use **dot notation** for methods. This is so that Python knows what module the methods that are being used are coming from, something that's not needed for functions. (Notice the lack of dot notation when we used `print` and `type`).  



