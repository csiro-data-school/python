---
title: "Python Values and their Type"
teaching: 15
exercises: 10
questions:
- "What are data types?"
- "What are the basic single-valued data types in Python?"
- "What is one way to store a list of values?"
- "What are variables?"
objectives:
- "Explain key differences between integers and floating point numbers."
- "Explain key differences between numbers and character strings."
- "Use built-in functions to convert between integers, floating point numbers, and strings."
- "Learn about Python's single-valued data types."
- "Learn about variables, how to name them and how to assign values to them."
- "Learn the basics about Python lists."
keypoints:
- "Every value has a type."
- "Use the built-in function `type` to find the type of a value."
- "Types control what operations can be done on values."
- "Strings can be added and multiplied."
- "Strings have a length (but numbers don't)."
- "Must convert numbers to strings or vice versa when operating on them."
- "Can mix integers and floats freely in operations."
- "Variables only change value when something is assigned to them."
---

FIXME: episode content.

## Every value has a type.

*   Every value in a program has a specific type.
*   Integer (`int`): counting numbers like 3 or -512.
*   Floating point number (`float`): fractional numbers like 3.14159 or -2.5.
    *   Integers are used to count, floats are used to measure.
*   Character string (usually just called "string", `str`): text.
    *   Written in either single quotes or double quotes (as long as they match).
    *   The quotation marks aren't printed when the string is displayed.

## Use the built-in function `type` to find the type of a value.

*   Use the built-in function `type` to find out what type a value has.
*   Works on variables as well.
    *   But remember: the *value* has the type --- the *variable* is just a label.

~~~
print(type(52))
~~~
{: .python}
~~~
<class 'int'>
~~~
{: .output}

~~~
print(type(fitness))
~~~
{: .python}
~~~
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'fitness' is not defined
~~~
{: .output}
~~~
fitness = 'average'
print(type(fitness))
~~~
{: .python}
~~~
<class 'str'>
~~~
{: .output}

## Types control what operations can be done on values.

*   A value's type determines what the program can do to it.

~~~
print(5 - 3)
~~~
{: .python}
~~~
2
~~~
{: .output}


~~~
print('hello' - 'h')
~~~
{: .python}
~~~
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
<ipython-input-2-67f5626a1e07> in <module>()
----> 1 print('hello' - 'h')

TypeError: unsupported operand type(s) for -: 'str' and 'str'
~~~
{: .error}








The types to definitely cover:
- Int
- Float
- Boolean
- Strings
- Lists
- None

The types to optionally cover, if there is room in the episode:
- Complex
- Basic operations 4 + 2

{% include links.md %}

