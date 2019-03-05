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

The types to definitely cover:
- Int
- Float
- Strings
- Boolean
- Lists
- None

The types to optionally cover, if there is room in the episode:
- Complex
- Basic operations 4 + 2

## Variables, Values and Types

*	Although they may often feel like the same thing, it is helpful to distinguish between variables, values, and types.
*	**Variables** are symbols (often descriptive words) that can represent or stand in for different values.<br />
	Variables are named with identifiers.
*	**Values** are the actual values and data objects stored in memory.<br /> 
	The reason they often feel the same as variables is that in Python you can only access a value through a variable.
*	The **type** of a value indicates what type of value it is and defines the set of legal operations.<br />
	As well as providing a large range of built-in types (such as `int`, `float`, `str` and `boolean`), <br />
	Python allows you to define your own types via classes.

~~~
a = 'a string'
~~~
{: .python}
In this simple line of code, we have the variable or identifier `a`, the value `a string`, and the type `str`.<br />
You can always check the type through the built-in function `type`:

~~~
type(a)
~~~
{: .python}
~~~
<class 'str'>
~~~
{: .output}

~~~
a = 7.1
type(a)
~~~
{: .python}
~~~
<class 'float'>
~~~
{: .output}

## Numbers

*	Integers `int`
*	Floating point numbers `float`
*	Complex numbers `complex` ??

~~~
myint = 1
print(myint)
~~~
{: .python}
~~~
1
~~~
{: .output}

To define a floating point number we must include a decimal point otherwise it is an integer!
~~~
myfloat = 1.0
print(myfloat)
~~~
{: .python}
~~~
1.0
~~~
{: .output}

Can also convert an `int` to `float` and vice-verse.
~~~
float(1)
int(1.0)
~~~
{: .python}
~~~
1.0
1
~~~
{: .output}

## Strings

*	Can be defined by single ('') or double ("") quotes
*	One difference is that double quotes allow for apostrophes, <br />
	which would otherwise mark the end of the string.

~~~
string1 = 'hello'
string2 = "hello"
string1 == string2
~~~
{: .python}
~~~
True
~~~
{: .output}

## Booleans

*	`bool` values are the two constant objects **True** or **False**
*	In numeric contexts they behave like the integers 0 and 1
*	Use the built-in function bool() to case any value to a `bool`

> ## Choose a Type
>
> What type of value (integer, floating point number, or character string)
> would you use to represent each of the following?
>
> 1. Number of days since the start of the year.
> 2. Time elapsed since the start of the year.
> 3. Serial number of a piece of lab equipment.
> 4. A lab specimen's age.
> 5. Current population of a city.
> 6. Average population of a city over time.
{: .challenge}


{% include links.md %}

