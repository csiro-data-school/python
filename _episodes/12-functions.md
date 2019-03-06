---
title: "Functions"
teaching: 20
exercises: 20
questions:
- "What are functions?"
- "How do I create my own functions in Python?"
- "How do I use my own functions?"
- "How do I document my functions?"
objectives:
- "First learning objective. (FIXME)"
keypoints:
- "Don't repeat yourself. Keep your code DRY by using functions."
- "Break programs down into functions to make them easier to understand."
- "Define a function using `def` with a name, parameters, and a block of code."
- "Defining a function does not run it."
- "Arguments in the function call are matched to the parameters in the function definition."
- "Optional arguments have a default value in the function definition."
- "Functions return results with the `return` statement."
- "Use docstrings to document your functions in a standard way."

---

## Don't Repeat Yourself

One of the core principles of any programming language is, "Don't Repeat
Yourself", often referred to as DRY. If you have an action that should occur
many times, you can define that action once and then call that code whenever you
need to carry out the action.

Functions mean less work for us as programmers, and effective use of functions
results in code that is less error-prone.

When our function works, we don't have to worry about that code anymore. Every
time you repeat code in your program, you introduce an opportunity to make
a mistake. Writing a function means there is one place to fix mistakes, and when
those bugs are fixed, we can be confident that this function will continue to
work correctly.

## Break programs down into functions to make them easier to understand

We can only keep a few items or ideas in working memory at a time. To understand
complicated ideas, we chunk information together and then think about the
higher-level chunks. For example, when thinking about cars we may just think
about engines, wheels, and entertainment systems. Each one is a complicated
system, but we don't need to consider every detail all the time.

Functions serve the same purpose in programs. They chunk some code together so we
can treat it as a single thing elsewhere. For example, I can use a `sort()` function to
order a list of strings without needing to think about the implementation
details of sorting algorithms.

Functions allow us to:

- order our code,
- think about our code at a higher-level,
- make our code more readable,
- make our code reusable,
    - write once, use often
- make our code more reliable,
- make our code easier to update,
    - modifying a function is easier than finding and modifying multiple
      sections of duplicated code
- make our code testable (see the [testing episode]({{ page.root
  }}/13-testing/)),
- define interfaces so others can use our code.

Additionally, functions provide a convenient focal point for documentation.
They are at the right level of detail for documenting your code, and Python has
a number of good tools for generating formatted documentation from functions.

### FIXME: Do I need the next 2 paragraphs?
Conceptually, functions can be treated as a box of code. When using a function
it can be a black box. You need only consider the inputs and outputs: what data
do you supply, and what should you get back. When writing functions they are
a white box: you must pay attention to the internal details as well as the
data flow (inputs and outputs).

Finally, when designing your functions, it can be helpful to only write
functions that do a single task. One function, one job. Complicated functions
that do many things are harder to write, harder to debug, and harder to use.

## Define a function using `def` with a name, parameters, and a block of code

- Begin the definition of a new function with `def`.
- Followed by the name of the function.
    - Must obey the same rules as variable names.
    - A variable name tells you what kind of value the variable contains;
      a function name should tell you what the function does.
- Then *parameters* in parentheses.
    - These are basically variable names, but they are only used in the function.
        - Again, the same variable naming rules apply.
    - Empty parentheses if the function doesn't take any inputs.
- Then a colon.
- Then an indented block of code.
    - This is the body of the function.

~~~
def print_greeting():
    print('Hello!')
~~~
{: .language-python}

> ## Write a Happy Birthday function
>
> Write a function called `happy_birthday` that prints the message "Happy
> birthday!".
> > ## Solution
> > ~~~
> > def happy_birthday():
> >     print("Happy birthday!")
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}

## Defining a function does not run it

- Defining a function does not run it.
- Must call the function to execute the code it contains.
- Function arguments can either be literal values or variables.

~~~
print_greeting()
~~~
{: .language-python}

~~~
Hello!
~~~
{: .output}

> ## A Common Error
> Functions must be defined before you can call them.
> The following code would not work:
> ~~~
> print_greeting("Bruce")
>
> def print_greeting():
>     print('Hello!')
> ~~~
> {: .language-python}
{: .callout}

> ## Call your Happy Birthday function
>
> Call your `happy_birthday` function.
> > ## Solution
> > ~~~
> > happy_birthday()
> > ~~~
> > {: .language-python}
> > ~~~
> > Happy birthday!
> > ~~~
> > {: .output}
> {: .solution}
{: .challenge}

## Arguments in the function call are matched to the parameters in the function definition

- Functions are most useful when they can operate on different data.
- Specify *parameters* when defining a function.
    - These become *variables* when the function is executed.
    - They are assigned the arguments in the function call (i.e., the values
      passed to the function).
    - If you don't name the arguments when using them in the call, the arguments
      will be matched to parameters in the order the parameters are defined in
      the function.

~~~
def print_date(year, month, day):
    joined = str(year) + '/' + str(month) + '/' + str(day)
    print(joined)

print_date(1871, 3, 19)
~~~
{: .language-python}
~~~
1871/3/19
~~~
{: .output}

Or, we can name the arguments when we call the function, which allows us to
specify them in any order:
~~~
print_date(month=3, day=19, year=1871)
~~~
{: .language-python}
~~~
1871/3/19
~~~
{: .output}

> ## Add a name parameter to your Happy Birthday function
>
> Add a parameter called `name` to your happy birthday function. The function
> should now use the supplied name in the message. Do not worry about the case
> where the name is not supplied.
> > ## Solution
> > ~~~
> > def happy_birthday(name):
> >     print("Happy birthday to " + name + "!")
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}

## Optional arguments have a default value in the function definition

- You can add optional arguments to your functions by providing a default value
in the function definition.
- If a value is supplied in the function call, that value will be used.
- If no value is supplied at call time, the default will be used.

~~~
def print_greeting(who=""):
    if who:  # recall that empty strings are treated as False
        print("Hello " + who + "!")
    else:
        print("Hello!")
~~~
{: .language-python}
~~~
print_greeting()
~~~
{: .language-python}
~~~
Hello
~~~
{: .output}
~~~
print_greeting("Brian")
~~~
{: .language-python}
~~~
Hello Brian
~~~
{: .output}

> ## Add a default value to `name`
>
> Give the `name` parameter a default value of "you".
> > ## Solution
> > ~~~
> > def happy_birthday(name="you"):
> >     print("Happy birthday to " + name + "!")
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}

> ## Positional and Keyword Arguments
> In the Python world, you will frequently see function arguments described as
> *positional* and *keyword* arguments. Positional arguments are those that are
> matched to parameters by position in the function call, while keyword arguments are matched
> by name. Historically, positional arguments were used for parameters without
> a default value, while keyword arguments were used for parameters with default
> values. However this need not be the case.
{: .callout}

## Functions return results with the `return` statement

- Use `return ...` to give a value back to the caller.
- May occur anywhere in the function.
- But functions are easier to understand if `return` occurs:
    - At the start to handle special cases.
    - At the very end, with a final result.
- Every function returns something. If your function does not explicitly
  `return` a value, then `None` is returned automatically.

> ## Averaging numbers
> Write a function that accepts a list of numbers and returns the average.
> If the argument is an empty list, then return `None`. All other error
> conditions can be ignored.
> > ## Solution
> > ~~~
> > def average(values):
> >     if len(values) == 0:
> >         return None
> >     return sum(values) / len(values)
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}

## Use docstrings to document your functions in a standard way

## Use doctests to add tests

## Scope

## Side effects

---

{% include links.md %}

