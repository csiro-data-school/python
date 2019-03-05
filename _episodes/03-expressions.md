---
title: "Expressions"
teaching: 0
exercises: 0
questions:
- "Key question (FIXME)"
objectives:
- "First learning objective. (FIXME)"
keypoints:
- "First key point. Brief Answer to questions. (FIXME)"
---

- Procedure
- Associativity
- BEDMAS order of operations
- Types
- Numerical
- Boolean
- String


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






{% include links.md %}

