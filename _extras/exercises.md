---
title: Exercises
---
# Types and expressions

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
{: .challenge}

> ## Think like a computer - division
> Computers cannot intuitively solve problems; the problem must be broken down by the computer into a series of logical steps.
> How would a computer solve the following problem? 
> 
> If `num_subjects` is the number of subjects taking part in a study,
> and `num_per_survey` is the number that can take part in a single survey,
> write a series of expressions that calculates the number of surveys needed
> to reach everyone once.
>
> Hint: you may need to use `//` and `%`
>
> Test your expressions with `num_subjects` = 600 and `num_per_survey` = 20.
>
> Now test again with `num_per_survey` = 42.
{: .challenge}

# Conditionals - if statements

> ## Close Enough
>
> Write some conditions that print `True` if the variable `a` is within 10% of the variable `b`
> and `False` otherwise.
> Compare your implementation with your partner's:
> do you get the same answer for all possible pairs of numbers?
> Try you code with:
> ~~~
> a = 5
> b = 5.1
> ~~~
> {: .language-python}
>
> Try it again with:
> ~~~
> a = 7
> b = 4
> ~~~
> {: .language-python}
> What other values of `a` and `b` would it be good to try your code with?
{: .challenge}
