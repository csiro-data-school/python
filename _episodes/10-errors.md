---
title: "Error Messages"
teaching: 10
exercises: 15
questions:
- "What kind of errors can occur in programs?"
- "How can I identify errors when they occur?"
objectives:
- "Explain the difference between syntax errors and run-time exceptions."
- "Understand that Python has built-in exceptions, and where to find information on them."
- "Correctly describe situations in which `SyntaxError`, `IndentationError`, `NameError`, `IndexError`, and `FileNotFoundError` occur."
keypoints:
- "Syntax errors occur because of illegal language constructs. They are detected by
  the Python parser."
- "Sometimes the actual error occurs slightly before the location reported by the Python exception."
- "Runtime errors occur when something goes wrong while a program is executing."
- "In Python, run-time errors raise exceptions."
- "Indentation is meaningful in Python."
---

## Errors Happen

You have almost certainly encountered errors in your Python code. For beginners,
the most common is the syntax error, which occurs when your code is not valid
Python. For example:
~~~
>>> for i in range(10) print(i)
  File "<stdin>", line 1
    for i in range(10) print(i)
                           ^
SyntaxError: invalid syntax
~~~
{: .language-python}

> ## Why does that example produce a syntax error?
> The message *"SyntaxError: invalid syntax"* is correct, but not very helpful.
>
> Note that the caret (`^`) indicates where Python detected a problem. What do
> you think the problem is?
> > ## Solution
> > The colon (`:`) that delimits the `for` loop from the loop body is missing.
> > The reason that the `print` is marked with the caret is that any code
> > following the `for` statement is invalid unless the statement is
> > preceded by a colon (`:`). So `print` is the first invalid code even though
> > the actual error occurs earlier.
> >
> > The correct code would be:
> > ~~~
> > for i in range(10): print(i)
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}


###   Lets look more closely at an error message:

~~~
print("hello world"
~~~
{: .python}
~~~
  File "<ipython-input-6-d1cc229bf815>", line 1
    print ("hello world"
                        ^
SyntaxError: unexpected EOF while parsing
~~~
{: .error}

*   The message indicates a problem on the first line of the input ("line 1").
    *   In this case the "ipython-input" section of the file name tells us that
        we are working with input into IPython,
        the Python interpreter used by the Jupyter Notebook.
*   The `-6-` part of the filename indicates that
    the error occurred in cell 6 of our Notebook.
*   Next is the problematic line of code,
    indicating the problem with a `^` pointer.

## Runtime errors happens when Python understands what you are saying but something goes wrong while a program is executing

> ## Run the following snippet of Python code
>
> ~~~
> numerator = 7
> denominator = 0
> result = numerator / denominator
> ~~~
> {: .language-python}
> What happens?
> > ## Solution
> > You get a `ZeroDivisionError`. This is the Python exception that indicates
> > a run-time error caused by a division by zero. Note that the code is
> > syntactically valid Python, so this is not a syntax error.
> > ~~~
> > >>> numerator = 7
> > >>> denominator = 0
> > >>> result = numerator / denominator
> > Traceback (most recent call last):
> >   File "<stdin>", line 1, in <module>
> > ZeroDivisionError: division by zero
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}

The `ZeroDivisionError` is built-in to Python. The next exercise looks at some
more [built-in exceptions](https://docs.python.org/3/library/exceptions.html#bltin-exceptions).

> ## Exploring the Built-in Exceptions
> Have a look at the documentation for
> [built-in exceptions](https://docs.python.org/3/library/exceptions.html#bltin-exceptions).
> See if you can find each of the following errors. If have encountered any
> other errors recently, see if you can find those as well.
>
> - `ZeroDivisionError`
> - `FileNotFoundError`
> - `TypeError`
> - `MemoryError`
> - `IndexError`
> - `KeyError`
>
{: .challenge}

## Indentation is meaningful in Python.

*   Python uses indentation to group sections of code together
    (discussed in the [loops episode]({{ site.github.url }}/06-for-loops)).
*   If the indentation changes in a way that Python does not expect,
    it reports an `IndentationError`
    (which is a more specific kind of syntax error).

~~~
firstName="Jon"
  lastName="Smith"
~~~
{: .python}
~~~
  File "<ipython-input-7-f65f2962bf9c>", line 2
    lastName="Smith"
    ^
IndentationError: unexpected indent
~~~
{: .error}

*   This error can be fixed by removing the extra spaces
    at the beginning of the second line.

> ## Identifying Variable Name Errors
>
> 1. Read the code below and try to identify what the errors are
>    *without* running it.
> 2. Run the code and read the error message.
>    What type of `NameError` do you think this is?
>    Is it a string with no quotes, a misspelled variable, or a
>    variable that should have been defined but was not?
> 3. Fix the error.
> 4. Repeat steps 2 and 3, until you have fixed all the errors.
>
> ~~~
> for number in range(10):
>     # use a if the number is a multiple of 3, otherwise use b
>     if (Number % 3) == 0:
>         message = message + a
>     else:
>         message = message + "b"
> print(message)
> ~~~
> {: .source}
{: .challenge}

> ## Identifying Item Errors
>
> 1. Read the code below and try to identify what the errors are
>    *without* running it.
> 2. Run the code, and read the error message. What type of error is it?
> 3. Fix the error.
>
> ~~~
> seasons = ['Spring', 'Summer', 'Fall', 'Winter']
> print('My favorite season is ', seasons[4])
> ~~~
> {: .source}
{: .challenge}
