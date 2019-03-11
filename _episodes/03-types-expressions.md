---
title: "Data 'types' and expressions"
teaching: 20
exercises: 15
questions:
- "What are expressions?"
- "What are operators?"
- "What are comparisons?"
- "What are precedence and associativity?"
objectives:
- "Understand how different types of operators function."
- "Understand that types determine the type of operations that can be done on a value."
- "Know how to use the in-built function `len`."
- "Understand order of precedence."
- "Know how to concatinate strings."
keypoints:
- "Types control what operations can be done on values."
- "Strings can be added and multiplied."
- "Strings have a length (but numbers don’t)."
- "Must convert numbers to strings or vice versa when operating on them."
---

## Operators and Expressions

We have already seen how Python can be used as a calculator:

~~~
5 - 3
~~~
{: .language-python}

This is an example of an 'expression'. 

*	An expression is a combination of values, variables, and 'operators'.
*	Operators include `+`, `-`, `/`, `//`, `*`, `**`, `%`, `==`, `!=` plus more..
*	Expressions need to be evaluated.

Technically, the 'expression' is the entire `5 - 3`.This can be broken down into 'operators' and 'operands'.<br/>
The operator is the `-` and the data values (`5` and `3`) are the operands.


## Expressions with 'numbers'

We can use many other kinds of operators to construct different expressions:

#### Multiplication
~~~
2 * 3
~~~
{: .python}
~~~
6
~~~
{: .output}

#### Exponent
~~~
2 ** 3
~~~
{: .python}
~~~
8
~~~
{: .output}

#### Division
~~~
13 / 3
~~~
{: .python}
~~~
4.333333333333333
~~~
{: .output}

#### Floor Division
~~~
13 // 3
~~~
{: .python}
~~~
4
~~~
{: .output}

Rounds the answer down to the nearest integer value.

#### Modulo
~~~
13 % 3
~~~
{: .python}
~~~
1
~~~
{: .output}
`%` returns the remainder of the division.

> ## Division expressions
> What is the outcome of the following expressions?
> ~~~
> print('5 // 3:', 5//3)
> print('5 % 3:', 5%3)
> ~~~
> {: .python}
>
>>## Solution
>> 5 // 3: 1 <br/>
>> 5 % 3: 2
>{: .solution}
{: .challenge}

## Order of operations

*	Follows **B**rackets, **E**xponents, **D**ivision, **M**ultiplication, **A**ddition, **S**ubtraction **BEDMAS**
*	When two operators have the same precedence, *associativity* determines the order of operations.
*	Associativity is the order in which an expression is evaluated, almost always **left-to-right**.


> ## Precedence and Associativity
> If you had the following expressions what are the outputs?
>
>1. 2 + 3 * 4
>2. 5 * 2 // 3
>3. 5 * (2 // 3)
>4. 2 ** 3 ** 2
>5. (2 ** 3) ** 2
>
>>## Solution
>>1. Answer: 14
>>2. Answer: 3
>>3. Answer: 0
>>4. Answer: 512
>>5. Answer: 64
>{: .solution}
{: .challenge}


## Value 'types'

Data comes in different flavours ... intuitively, we know that we can do different things with different kinds of data. The expression `13 % 2` makes sense to us, but what about `'Brian' % 2`?


> ## Categorising data
> Group the following values into sensible categories:
> ~~~
> 10
> -5
> 'Harry'
> 2.71828
> 'x'
> 3.14159265359
> 1.0
> 0
> 'c'
> 'The meaning of life'
> ~~~
> What might be the implications, for a computer, of these different 'types' of data?
{: .challenge}

Although they may often feel like the same thing, it is helpful to distinguish between variables, values, and types.
*	**Variables** are symbols (often descriptive words) that can represent or stand in for different values.<br />
*	**Values** are the actual values (i.e. data) stored in memory. <br /> 
	In Python, you can only access a stored value through a variable. 
*	The **type** of a value indicates what the nature of the value is, and defines the set of legal operations that can be done on it.<br />
	As well as providing a large range of built-in types (such as `int`, `float`, `str` and `bool`), <br />

~~~
a = 'a string'
~~~
{: .language-python}
In this simple example, we have the variable or identifier `a`, the value `a string`, and the type `str`.<br />
You can always check the type through the built-in function `type`:

~~~
type(a)
~~~
{: .language-python}
~~~
<class 'str'>
~~~
{: .output}

~~~
a = 7.1
type(a)
~~~
{: .language-python}
~~~
<class 'float'>
~~~
{: .output}

### Number types: `Int` and `Float`

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

### Strings

*	Can be defined by single ('') or double ("") quotes.
*	This allows us to use both `'` and `"` as string characters, without accidentally indicating the end of the string.

~~~
string1 = 'hello'
string2 = "hello"
string3 = '1234'
string4 = str(56789)
string5 = 'x'
string6 = "Cleese's legacy"
string7 = 'Another Monty Python quote: "Blue. No, Yellow. Arrghh!"'
~~~
{: .python}

### Boolean Expressions - `True` or `False`

*	Python comparison operators return a `bool` value, **True** or **False** and these can be stored in `bool` variables
*	Equality is tested with the double-equals (`==`) operator while inequality uses exclamation-mark-equals (`!=`), read as not`!` equals`=`.
*	In numeric expressions they behave like the integers 0 and 1
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

### Special Case - NoneType

*	Type for the `None` object that indicates no value

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

## Comparisons, Membership Tests and Identity Tests

*	Always returns a value of type `bool`
*	`<`, `<=`, `>`, `>=`, `!=`, `==`, `in`, `not in`, `is`, `is not`


Note: a single `=` is for variable *assignment*, **not for comparison**.
~~~
3 = 3
~~~
{: .language-python}
~~~
File "<stdin>", line 1
SyntaxError: can't assign to literal
~~~
{: .error}

Double `==` is for comparison:
~~~
3 == 3
~~~
{: .language-python}
~~~
True
~~~
{: .output}

## Types control how values can be combined in expressions.

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

## Integers and floats can be mixed freely in expressions.

*   Integers and floating-point numbers can be mixed in arithmetic.
    * Python automatically converts integers to floats as needed.
    * this is new in Python 3

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






## Strings can be added and multiplied.

*   In Python string concatenation is done with the addition `+` operator.
* This is an example of *operator overloading*. In plain English, this means that the behaviour of `+`, the **operator**, changes depending on the **type** of data we give it.

~~~
age = 42
age + 3
~~~
{: .language-python}
~~~
45
~~~
{: .output}

~~~
full_name = 'Ahmed ' + 'Walsh'
print(full_name)
~~~
{: .python}
~~~
Ahmed Walsh
~~~
{: .output}

*   Multiplying a string by an integer replicates it. This makes sense, as multiplication is like repeated addition.

~~~
'spam' * 5

~~~
{: .python}
~~~
'spamspamspamspamspam'
~~~
{: .output}

## Built in functions and data types

Python pre-defines a number of core 'functions' as part of the base language. We have already met one of these functions, 
`print`. We 'call' a function by stating the name of the function, directly followed by some data (a 'value' or 'variable') inside round brackets:

~~~
print(42)
print(string7)
~~~
{: .language-python}

The built-in function `print` works on all data types. This is not true of all built in functions; many only work on certain kinds of data.

*   The built-in function `len` counts the number of characters in a string.

~~~
print(len(full_name))
~~~
{: .python}
~~~
11
~~~
{: .output}

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

> ## Strings to Numbers
>
> `float` will convert a string to a floating point number,
> and `int` will convert a floating point number to an integer:
>
> ~~~
> print("string to float:", float("3.4"))
> print("float to int:", int(3.4))
> ~~~
> {: .python}
>
> ~~~
> string to float:, 3.4
> float to int:, 3
> ~~~
> {: .output}
>
> Given that,
> what do you expect this program to do?
> What does it actually do?
> Why do you think it does that?
>
> ~~~
> print("fractional string to int:", int("3.4"))
> ~~~
> {: .python}
{: .challenge}

> ## Arithmetic with Different Types
>
> Which of the following will print 2.0?
> Note: there may be more than one right answer.
>
> ~~~
> first = 1.0
> second = "1"
> third = "1.1"
> ~~~
> {: .python}
>
> 1. first + float(second)
> 2. float(second) + float(third)
> 3. first + int(third)
> 4. first + int(float(third))
> 5. int(first) + int(float(third))
> 6. 2.0 * second
>
> > ## Solution
> > Answer: 1 and 4
> {: .solution}
{: .challenge}



> ## Think like a computer - division
> Computers cannot intuitively solve problems; the problem must be broken down by the computer into a series of logical steps.
> How would a computer solve the following problem? 
> 
> If `num_subjects` is the number of subjects taking part in a study,
> and `num_per_survey` is the number that can take part in a single survey,
> write a series of expressions that calculates the number of surveys needed
> to reach everyone once.
> Hint: you may need to use `//` and `%`
> Test your expressions with `num_subjects` = 600 and `num_per_survey` = 20.
> Now test again with `num_per_survey` = 42.
>>## Solution
>> First test if the number of subjects per survey divides evenly by the number of subjects using the `%` operator.
>> ~~~
>> num_subjects = 600
>> num_per_survey = 42
>> remainder = num_subjects % num_per_survey
>> num_surveys = num_subjects // num_per_survey
>> 
>> print(remainder)
>> print(num_subjects, 'subjects,', num_per_survey, 'per survey:', num_surveys + 1, 'surveys needed')
>> ~~~
>> {: .python}
>> 
>> ~~~
>> 12
>> 600 subjects, 42 per survey: 15 surveys needed
>> ~~~
>> {: .output}
>{: .solution}
{: .challenge}


{% include links.md %}

