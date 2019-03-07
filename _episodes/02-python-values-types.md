---
title: "Python Values and their Type"
teaching: 15
exercises: 10
questions:
- "What are the basic single-valued data types in Python?"
- "What are variables?"
- "What is one way to store a group of values?"

objectives:
- "Explain key differences between integers and floating point numbers."
- "Explain key differences between numbers and character strings."
- "Use built-in functions to convert between integers, floating point numbers, and strings."
- "Explain what a boolean expression is."
- "Explain how to group items into a list."
- "Explain when a NoneType object would occur."

keypoints:
- "Variables are descriptive words that represent objects"
- "Values are the actual numbers or objects stored in memory"
- "Every value has a type."
- "Use the built-in function `type` to find the type of a value."
- "Can mix integers and floats freely in operations."
- "Booleans are used for comparison."
- "Lists are used to group objects."
- "NoneType indicated a varible with no value."

---

## Variables, Values and Types

*	Although they may often feel like the same thing, it is helpful to distinguish between variables, values, and types.
*	**Variables** are symbols (often descriptive words) that can represent or stand in for different values.<br />
	Variables are named with identifiers.
*	**Values** are the actual values and data objects stored in memory.<br /> 
	The reason they often feel the same as variables is that in Python you can only access a value through a variable.
*	The **type** of a value indicates what type of value it is and defines the set of legal operations.<br />
	As well as providing a large range of built-in types (such as `int`, `float`, `str` and `bool`), <br />
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

*	Integers `int`.
*	Floating point numbers `float`.
*	To define a floating point number we must include a decimal point otherwise it is an integer!

~~~
myint = 1
print(myint)
~~~
{: .python}
~~~
1
~~~
{: .output}

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

*	Can be defined by single ('') or double ("") quotes.
*	One difference is that double quotes allow for apostrophes, <br />
	which would otherwise mark the end of the string.

~~~
string1 = 'hello'
string2 = "hello"
string3 = '1234'
string4 = str(56789)
~~~
{: .python}

## Boolean Expressions - **True** or **False**

*	Python comparison operators return a `bool` value, **True** or **False** and these can be stored in `bool` variables
*	Equality is tested with the double-equals (`==`) operator while inequality uses exclamation-mark-equals (`!=`), read as not`!` equals`=`.
*	In numeric contexts they behave like the integers 0 and 1
*	Use the built-in function bool() to case any value to a `bool`

~~~
count = 3
print(count == 4)
print(count < 3)
print(count == 3)
print(count > 4)
string1 == string2
~~~
{: .python}
~~~
False
False
True
False
True
~~~
{: .output}

## Lists

*	Lists are probably the most commonly used container in Python.
*	Allow multiple values to be grouped together.
*	Can contain variables of any type.
*	Lists are **also** themselves values or objects so can nest lists within other lists.
*	Lists preserve their order allowing us to easily pull values out.

~~~
mylist = []
mylist2 = list()
mylist.append(1)
mylist.append(2)
mylist.append(3)
print(mylist)
~~~
{: .python}
~~~
[1, 2, 3]
~~~
{: .output}

## Special Case - NoneType

*	Type for the `None` object that indicates no value
*	Is the return value of functions that don't return anything

~~~
empty = None
print(empty)
~~~
{: .python}
~~~
None
~~~
{: .output}


> ## Choose a Type
>
> What type of value (integer, floating point number, character string or list)
> would you use to represent each of the following?
>
> 1. Number of days since the start of the year.
> 2. Time elapsed since the start of the year.
> 3. Serial number of a piece of lab equipment.
> 4. A lab specimen's age.
> 5. Current population of a city.
> 6. Average population of a city over time.
> 7. The ages of all students in a class.
{: .challenge}

> ## Identify the outputs
>
> What are the outputs from the following commands?
>
> 1. print(type(3))
> 2. print(float(3))
> 3. print(int(3.9))
> 4. print(bool(0))
> 5. print(type(None))
{: .challenge}

{% include links.md %}

