---
title: "Expressions"
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

*	An expression is a combination of values, variables, operators and a calls to a function.
*	Expressions need to be evaluated.
*	Operators include `+`, `-`, `/`, `//`, `*`, `**`, `%`, `==`, `!=` plus more..

## Use Python as a calculator on `numbers`
~~~
5 - 3
~~~
{: .python}
~~~
2
~~~
{: .output}

In this case the above expression is 5 - 3. This expression can be broken down into operators and operands.<br/>
The operator is the `-` and the data are the operands.

Multiplication
~~~
2 * 3
~~~
{: .python}
~~~
6
~~~
{: .output}

Exponent
~~~
2 ** 3
~~~
{: .python}
~~~
8
~~~
{: .output}

Division
~~~
13 / 3
~~~
{: .python}
~~~
4.333333333333333
~~~
{: .output}

Floor Division
~~~
13 // 3
~~~
{: .python}
~~~
4
~~~
{: .output}
Rounds the answer down to the nearest integer value, note if one of the values is a float you will get back a float.

Modulo
~~~
13 % 3
~~~
{: .python}
~~~
1
~~~
{: .output}
`%` returns the remainder of the division.

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

## Comparisons, Membership Tests and Identity Tests

*	Always returns a `bool`
*	`<`, `<=`, `>`, `>=`, `!=`, `==`, `in`, `not in`, `is`, `is not`


Comparison?
~~~
3 = 3
~~~
{: .python}
~~~
File "<stdin>", line 1
SyntaxError: can't assign to literal
~~~
{: .error}

~~~
3 == 3
~~~
{: .python}
~~~
True
~~~
{: .output}

~~~
3 != 3
~~~
{: .python}
~~~
False
~~~
{: .output}

~~~
6 < 3
~~~
{: .python}
~~~
False
~~~
{: .output}

~~~
list1 = [1, 2, 3, 4]
2 in list1
~~~
{: .python}
~~~
True
~~~
{: .output}

## Precedence and Associativity

*	Follows **B**rackets, **E**xponents, **D**ivision, **M**ultiplication, **A**ddition, **S**ubtraction **BEDMAS**
*	When two operators have the same precedence, accociativity determines the order of operations.
*	Associativity is the order in which an expression is evaluated, almost always **left-to-right**.


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

*   In Python string concatenation is done with the addition `+` operator.

~~~
full_name = 'Ahmed' + ' ' + 'Walsh'
print(full_name)
~~~
{: .python}
~~~
Ahmed Walsh
~~~
{: .output}

*   Multiplying a character string by an integer replicates it.<br/>
	Since multiplication is just repeated addition.

~~~
'spam' * 5

~~~
{: .python}
~~~
'spamspamspamspamspam'
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

> ## Division Types
>
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
>
> If `num_subjects` is the number of subjects taking part in a study,
> and `num_per_survey` is the number that can take part in a single survey,
> write an expression that calculates the number of surveys needed
> to reach everyone once.
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
> 1. `first + float(second)`
> 2. `float(second) + float(third)`
> 3. `first + int(third)`
> 4. `first + int(float(third))`
> 5. `int(first) + int(float(third))`
> 6. `2.0 * second`
>
> > ## Solution
> > Answer: 1 and 4
> {: .solution}
{: .challenge}

{% include links.md %}

