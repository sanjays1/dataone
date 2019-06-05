---
title: "Strings"
date: 2019-05-31T17:35:18-04:00
draft: false
weight: 15
---

Quite a bit of the data we deal on a day to day basis are *text* based. Text in Python falls under the **String** data type or `str`. 

For Python to understand a piece of data is a **string**, the string itself must be contained *either* in single quotation marks *or* in double quotations marks (not both at the same time). The following two phrases are equivalent: 

~~~python
"Hello World!"
~~~

~~~python
'Hello World!'
~~~

Strings, just like any other data type, can be stored inside variables.

~~~python
what_mom_says = "Eat your veggies!"
~~~

We can also combine strings by "adding" them. 

~~~python
birthday_greeting = "Happy" + " Birthday" + " To" + " You!"
birthday_greeting
~~~

~~~python
'Happy Birthday To You'
~~~

Finally, we can also repeat strings a specified amount of times by "multiplying" them by a integer!

~~~python
pizzaz = "cha" * 3
pizzaz
~~~

~~~python
'chachacha'
~~~

What happens if we try using other mathematical operators (like `/`)? Only way to know is to try it out! (You might be surprised by the result.)

### String Functions and Methods 

Because text data is such a common data format, there's many different functions and methods avalible to help manipulate strings. While many functions and methods are built into Python, others need to be imported. 

Just like the last lesson, we've highlighted some useful functions and methods for strings. 

**`upper`** and **`lower`** 

The `upper` and `lower` methods returns an all upper case or an all lower case string respectively.

~~~python
"I'm shouting".upper()
~~~

~~~python
"I'M SHOUTING"
~~~

~~~python
"I NeED to Be QUIET".lower()
~~~

~~~python
'i need to be quiet'
~~~

**`len`**

The `len` method returns the length of a string. 

~~~python
third_longest_palindrome = "Malayalam"
len(third_longest_palindrome)
~~~

~~~python
9
~~~

**`strip`**

The `strip` method returns a string without any whitespace in it. 

~~~python
"   device      ".strip()
~~~

~~~python
'device'
~~~

**`replace`**

The `replace` method needs two inputs; first a part of string that needs to be replaced and then its replacement (order matters). 

~~~python
names = "george;lisa;mandy;javier"
names.replace(";", ",")
~~~

~~~python
'george,lisa,mandy,javier'
~~~

 