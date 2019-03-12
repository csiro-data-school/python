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


# while loop
n = 10
cur_sum = 0
# sum of n  numbers
i = 1
while  i <= n :
    cur_sum = cur_sum + i
    i = i + 1
print("The sum of the numbers from 1 to", n, "is ", cur_sum)
~~~
{: .language-python}

~~~
The sum of the numbers from 1 to 10 is 55
~~~
{: .output}

Points to note:

1.	The condition clause (i <= n) in the while statement can be anything which when evaluated would return a Boolean value of either True of False. Initially i has been set to 1 (before the start of the loop) and therefore the condition is `True`.
2.	The clause can be made more complex by use of parentheses and `and` and `or`  operators amongst others
3.	The statements after the while clause are only executed if the condition evaluates as True.
4.	Within the statements after the while clause there should be something which potentially will make the condition evaluate as `False` next time around. If not the loop will never end.
5.  In this case the last statement in the loop changes the value of i which is part of the condition clause, so hopefully the loop will end.
6. We called our variable `cur_sum` and not `sum` because `sum` is a builtin function (try typing it in, notice the editor
changes it to green).  If we define `sum = 0` now we can't use the function `sum` in this Python session.

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
> # sum of n  numbers
> i = 0
> while  i <= n :
>     i = i + 1
>     cur_sum = cur_sum + i
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
> # sum of n  numbers
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
> # sum of n  numbers
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
> # while loop - summing the numbers 1.1 to 9.9 i. steps of 1.1
> n = 9.9
> cur_sum = 0
> # sum of n  numbers
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
> > 4. Because you cannot guarantee the internal representation of Float, you should never try to compare them for equality. In this particular case the i never 'equals' n and so the loop never ends. - If you did try running this, you can stop it using <kbd>Ctrl</kbd>+<kbd>c</kbd> in a terminal or going to the kernel menu of a notebook and choosing interrupt.
> {: .solution}
{: .challenge}

