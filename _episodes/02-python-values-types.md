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
- Boolean
- Strings
- Lists
- None

The types to optionally cover, if there is room in the episode:
- Complex
- Basic operations 4 + 2

## Variables, Values and Types

*	Although they may often feel like the same thing, it is helpful to distinguish between variables, values, and types.
*	**Variables** are symbols (often descriptive words) that can represent or stand in for different values. Variables are named with identifiers.




## Every value has a type.

*   Every value in a program has a specific type.
*   Integer (`int`): Counting numbers like 3 or -512.
*   Floating point number (`float`): Fractional numbers like 3.14159 or -2.5.
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
{: .error}
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
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unsupported operand type(s) for -: 'str' and 'str'
~~~
{: .error}

## Strings can be added and multiplied.

*   "Adding" character strings concatenates them.

~~~
full_name = 'Ahmed' + ' ' + 'Walsh'
print(full_name)
~~~
{: .python}
~~~
Ahmed Walsh
~~~
{: .output}

*   Multiplying a character string by an integer replicates it.
    *   Since multiplication is just repeated addition.

~~~
separator = '=' * 10
print(separator)
~~~
{: .python}
~~~
==========
~~~
{: .output}

## Strings have a length (but numbers don't).

*   The built-in function `len` counts the number of characters in a string.

~~~
print(len(full_name))
~~~
{: .python}
~~~
11
~~~
{: .output}

*   But numbers don't have a length (not even zero).

~~~
print(len(52))
~~~
{: .python}
~~~
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: object of type 'int' has no len()
~~~
{: .error}

## Must convert numbers to strings or vice versa when operating on them.

*   Cannot add numbers and strings.

~~~
print(1 + 'A')
~~~
{: .python}
~~~
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unsupported operand type(s) for +: 'int' and 'str'
~~~
{: .error}

*   This is not allowed because it's ambiguous: should `1 + '2'` be `3` or `'12'`?
*   Some types can be converted to other types by using the type name as a function.

~~~
print(1 + int('2'))
print(str(1) + '2')
~~~
{: .python}
~~~
3
12
~~~
{: .output}

## Can mix integers and floats freely in operations.

*   Integers and floating-point numbers can be mixed in arithmetic.
    *   Python automatically converts integers to floats as needed.

~~~
print('half is', 1 / 2.0)
print('three squared is', 3.0 ** 2)
~~~
{: .python}
~~~
half is 0.5
three squared is 9.0
~~~
{: .output}

## Variables only change value when something is assigned to them.

*   If we make one cell in a spreadsheet depend on another,
    and update the latter,
    the former updates automatically.
*   This does **not** happen in programming languages.

~~~
first = 1
second = 5 * first
first = 2
print('first is', first, 'and second is', second)
~~~
{: .python}
~~~
first is 2 and second is 5
~~~
{: .output}

*   The computer reads the value of `first` when doing the multiplication,
    creates a new value, and assigns it to `second`.
*   After that, `second` does not remember where it came from.

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

