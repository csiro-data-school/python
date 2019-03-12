---
title: "While loops"
teaching: 20
exercises: 40
questions:
- "What other constructs are available for changing the flow of a program?"
objectives:
- "Change program flow using available language constructs"
- "Demonstrate how to execute a section of code until a condition is met"
keypoints:
- "Most programs will require 'Loops' and 'Branching' constructs."
- "`while` statements, in addition to `for`, allow for looping through sections of code"
- "The programmer must provide a condition to end a `while` loop."
---

We have seen that `for` loops provide a powerful form of repetition - the ability to repeat the same actions for every unit of data in a collection.

`while` loops facilitate another form of repetition; in this case, repeating a set of commands while a condition is `True`.

~~~
num_moons = 3
while num_moons > 0:
    print(num_moons)
    num_moons = num_moons - 1
~~~
{: .language-python}

`While` loops:
* start with the keyword `while`
* are followed by an expressions that evaluates to `True` or `False`
    * here, `num_moons` has be set, or *initialised* to `3` before the loop starts, so the condition is initially `True`
    * we change the value of `num_moons` within the loop, so that eventually the condition becomes `False`
* the `while` statement (first line of a while loop) ends with a colon `:`
* code within the `while` loop is indented. This code is performed at each iteration through the loop
* end when the condition becomes `False`

> ## Assignment operators
> In the `while` loop above, we updated the value of the variable `num_moons` while the loop was running,
> by typing the following code:
> ~~~
> num_moons = num_moons - 1
> ~~~
> {: .language-python}
> This pattern, where modify the value of a variable using an operator and reassign the new value back to the same
> variable, is so common that Python has special short-hand **assignment operators** for this task. In the example above, 
> the equivalent assignment operator looks like this:
> ~~~
> num_moons -= 1
> ~~~
> {: .language-python}
{: .callout}

## `while` loops can run zero times
~~~
num_moons = -3
while num_moons > 0:
    print(num_moons)
    num_moons -= 1
~~~
{: .language-python}

## or they may run infinitely... 

~~~
forever = 'the infinite while loop'
while forever:
    pass
~~~
{: .language-python}

To interrupt your code, **press 'I' twice quickly**. Note: `pass` is a valid statement within the body of a `while` loop (or a `for` loop, or an `if` statement). It means 'go onto the next step'.

> ## interrupting execution
> Try out the following code:
> ~~~
> counts = 1
> while counts:
>     counts += 1
> ~~~
> {: language-python}
> What is happening here?
> 
> Interrupt your code. Now try:
> ~~~
> print(counts)
> ~~~
> {: .language-python}
{: .challenge}

> ## cumulative sum
> Calculating the sum of a series of numbers is a common use for a `while` loop.>
>
> ~~~
> n = 10
> current_sum = 0
> i = 1
> while  i <= n :
>    current_sum += i
>    i = i + 1
> print("The sum of the numbers from 1 to", n, "is ", current_sum)
> ~~~
> {: .language-python}
>
> ~~~
> The sum of the numbers from 1 to 10 is 55
> ~~~
> {: .output}
>
> 1. How many times is the body of the `while` loop executed?
> 2. Write out, on paper, a table that describes the values of `n`, `current_sum`, and `i` at each step through the loop.
> 2. Why didn't we call our variable 'sum' instead of the longer, more cumbersome 'current_sum'?
{: .challenge}


> ## Exercise - Things that can go wrong with while loops
>
> In the examples below, without running them try to decide why we will not get the required answer.
> Run each, one at a time, and then correct them. Remember that when the input next to a notebook cell
> is [*] your Python interpreter is still working.
>
> ~~~
> # while loop - summing the numbers 1 to 10
> n = 10
> cur_sum = 0
> i = 0
> while  i <= n :
>     i += 1
>     cur_sum += i
>     
> print("The sum of the numbers from 1 to", n, "is ", cur_sum)
> ~~~
> {: .language-python}
>
> ~~~
> # while loop - summing the numbers 1 to 10
> n = 10
> cur_sum = 0
> boolvalue = False
> i = 0
> while  i <= n and boolvalue:
>     cur_sum = cur_sum + i
>     i = i + 1
>     
> print("The sum of the numbers from 1 to", n, "is ", cur_sum)
> ~~~
> {: .language-python}
>
> ~~~
> # while loop - summing the numbers 1 to 10
> n = 10
> cur_sum = 0
> i = 0
> while  i != n :
>     cur_sum = cur_sum + i
>     i = i + 1
>
> print("The sum of the numbers from 1 to", n, "is ", cur_sum)
> ~~~
> {: .language-python}
>
> ~~~
> # while loop - summing the numbers 1.1 to 9.9 in steps of 1.1
> n = 9.9
> cur_sum = 0
> i = 0
> while  i != n :
>     cur_sum = cur_sum + i
>     i = i + 1.1
>     print(i)
>     
> print("The sum of the numbers from 1.1 to", n, "is ", sum)
> ~~~
> {: .language-python}
>
> > ## Solution
> >
> > 1. Because i is incremented before the sum, you are summing 1 to 11.
> > 2. The Boolean value is set to False the loop will never be executed.
> > 3. When i does equal 10 the expression is False and the loop does not execute so we have only summed 1 to 9
> > 4. Because you cannot guarantee the internal representation of Float, you should never try to compare them for equality. In this particular case the i never 'equals' n and so the loop never ends!
> {: .solution}
{: .challenge}

> ## combining control structures: while and if
> 1. Fill in the blanks in the following code, so that it 
> prints all the odd numbers from 0 to 10
> ~~~
> num = 0
> while num <= __: 
>     if (num % 2) __ 1:
>         print(__)
>         ___ += 1
> ~~~
> {: .language-python}
> 2. Now, edit this code so it prints only the even numbers from 0 to 20. 
> 3. Can you find a simpler way to code this, using just a `while` loop? (i.e. no `if` statement)
{: .challenge}

{% include links.md %}
