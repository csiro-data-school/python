---
title: "Python Syntax"
teaching: 30
exercises: 30
questions:
- "What constitutes a legal Python program (script)?"
- "What are keywords, identifiers, expressions, statements?"
- "How can code be commented?"
- "What is indentation used for in Python?"
- "What kinds of brackets are used in Python code?"
- "Where can I find out more about Python style guidelines?"
objectives:
- "Learn about the key aspects of Python syntax"
keypoints:
- "Legal Python code follows rules of syntax"
- "A Python keyword is a symbol that has special meaning in a Python script"
- "Python provides for single and multiple line comments"
- "An identifier names a value, e.g. as in the assignment statement: x = 21"
- "A Python script consists of a sequence of statements that make use of keywords, identifiers and expressions"
- "Indentation introduces a code block"
- "`[` and `]` are used to surround literal list values"
- "`{` and `}` are used to surround literal dictionary values"
- "`(` and `)` are used for function parameters, to change expression evaluation order, and to specify tuple values"
- "The [PEP 8 Python Style Guidelines](https://www.python.org/dev/peps/pep-0008/) provide more code layout and convention details"
---

## Syntax
The grammatical rules or syntax of any language dictate the construction of "legal" sentences.

The syntax of a programming language determines what counts as a legal or well-formed program.

A Python program consists of a sequence of syntactically correct "sentences" entered into Jupyter notebook cells, at a Python interpreter prompt, or contained within files.

This episode introduces the following Python syntax elements, many of which we have seen in other episodes: keywords, identifiers, expressions, statements, comments, indentation and code blocks, brackets and quotes.

## Keywords 
In Python, keywords are special words used for core language constructs. An example of a Python keyword is `if`, used within so-called conditional statements.

> ## Keywords
>
> Entering `help()` in a Jupyter notebook cell, then entering `keywords` at the 
> prompt that follows, will show the available Python keywords.
>
> In a new cell, type:
> ~~~
> help()
> ~~~
> {: .language-python}
> 
> Then at the "help>" prompt that follows, enter:
> ~~~
> keywords
> ~~~
> {: .language-python}
>
> > ## Solution
> > You should see output like this:
> >
> > ~~~
> > Here is a list of the Python keywords.  Enter any keyword to get more help.
> >
> > False               def                 if                  raise
> > ...
> > continue            global              pass 
> > ~~~
> > {: .source}
> {: .solution}
{: .challenge}

Try entering one or more keywords at the "help>" prompt to get a brief description of what they are used for.

Spaces and tabs separate keywords, identifiers and expressions. They also play a special role in indentation levels in code blocks, which is covered later in this episode. 

## Identifiers
A Python identifier is a name or label used to identify a variable or function (identifiers are also used to label `class` and `module` objects, which we will cover in advanced Python). An identifier can start with a letter (a to z, A to Z) but may contain letters, underscores and digits (0 to 9) thereafter. (In some special cases, it can also start with an underscore). 

Additionally, Python is case-sensitive, so `myInt` is not the same identifier as `MyInt`.

There are naming conventions. These are not enforced by the language but following them helps produce readable and consistent code. The primary Python style guide is [PEP 8](https://www.python.org/dev/peps/pep-0008/).

## Expressions
Python values such as numbers and strings can be combined with operators to yield expressions. For example, the following combines numbers and operators to give an expression that when evaluated gives the number `42`: 

> ~~~
> 3 * 10 + 12
> ~~~
> {: .language-python}

The following asks whether this expression has the value we think it should:

> ~~~
> 3 * 10 + 12 == 42
> ~~~
> {: .language-python}

The "Expressions" episode provides more detail.

## Statements
Python statements make use of keywords, identifiers, and expressions. The following statement assigns the value of the `42` yielding expression from the last section to the variable designated by the identifier `meaning_of_life`:

> ~~~
> meaning_of_life = 3 * 10 + 12
> ~~~
> {: .language-python}

More than one statement can appear on a single line, each statement separated by a semi-colon, e.g.

> ~~~
> x=42; print("the meaning of life is ", x)
> ~~~
> {: .language-python}

It tends to be less confusing to keep each line as simple as possible however:

> ~~~
> x=42
> print("the meaning of life is ", x)
> ~~~
> {: .language-python}


## Comments
Comments are annotations embedded in code to summarise and explain the programmer's intent.

In Python there are two styles of comment: single line and multiple line.

## Single Line Comments
Anything that follows a `#` symbol on a line is considered a comment. The `#` may appear anywhere on a line. 

> ## Write code containing single-line comments
>
> In a new cell, enter the following Python code:
>
> ~~~
> print("Hello")
> # print("Again")
> print("World")  # trailing comment
> ~~~
> {: .language-python}
>
> > Notice that since the second `print` was commented, `Again` did not appear in the output. Note also that the text `trailing comment` was ignored.
> {: .solution}
{: .challenge}

## Multiple Line Comments
Triple single `'` or double `"` quotes begin and end a multi-line string, but if you don't assign this string to a variable, then any code within it has no effect and is effectively commented out.

> ## Write code containing multiple-line comments
>
> In a new cell, enter the following Python code:
>
> ~~~
> """
> This code outputs Hello World
> """
> print("Hello World")
> ~~~
> {: .language-python}
>
> > ## Solution
> > You should see this output:
> >
> > ~~~
> > Hello World
> > ~~~
> > {: .source}
> > 
> > Notice that the triple-quoted section at the top is ignored.
> {: .solution}
{: .challenge}


## Indentation and Code Blocks
Python uses indentation level to determine the start and end of code blocks - unlike many languages which use braces (`{` and `}`), or others that use keywords such as `begin` and `end`.

Code blocks are used in a number of contexts in Python including `if` statements and loops. 

The following shows a simple code block, introduced by a line ending in a colon with subsequent lines (just one in this case) indented by four spaces. Any number of spaces or even tabs can be used within a block, so long as each line within that block is indented to the same level. Four spaces are normally used by convention. The main point is to be consistent.

> ~~~
> if 3 > 2:
>    print("inside the block")  # this line is indented four spaces
> ~~~
> {: .language-python}

> ## Code Blocks
>
> In a new cell, enter the following Python code:
>
> ~~~
> if 3 > 2:
>     print("3 is greater than 2")
>     if 2 > 3:
>         print("that seems surprising")
>     else:
>         print("3 is still greater than 2")
> ~~~
> {: .language-python}
>
> > ## Solution
> > You should see this output:
> >
> > ~~~
> > 3 is greater than 2
> > 3 is still greater than 2
> > ~~~
> > {: .source}
> >
> {: .solution}
{: .challenge}

The "Conditional Statements" episode covers `if` statements in more detail.

You will find a colon (`:`) at the end of a line that preceeds a space-indented code block.

Python aware editors (e.g. Visual Code, vim) help in maintaining consistent indenting levels. Jupyter notebook code cells are indentation aware.

## Line Continuation
Some statements are long enough that it may be necessary, or at least desirable, to spread them over multiple lines. Suppose we have an expression that we would like to split over multiple lines:

> ~~~
> obliquity = degrees - 46.8150 * T - 0.00059 * (T * T) + 0.001813 * (T * T * T)
> ~~~
{: language-python}

The following would lead to a syntax error:

> ~~~
> obliquity = degrees - 46.8150 * T - 
>             0.00059 * (T * T) + 
>             0.001813 * (T * T * T)
> ~~~
{: language-python}
In Python, the line continuation character `\` must be used at the end of each line for this to satisfy the rules of syntax:

> ~~~
> obliquity = degrees - 46.8150 * T - \
>             0.00059 * (T * T) + \
>             0.001813 * (T * T * T)
> ~~~
{: .language-python}

## Brackets and Quotes
In Python, special characters denote the beginning and end of values of particular types.

There are 3 different enclosing bracket types used in Python:
* Parentheses: `(` `)`
* Square brackets: `[` `]`
* Braces: `{` `}`

Parentheses are used in Python to:
* change the order of evaluation of an expression, e.g. `12 + 2 * 6` vs `(12 + 2) * 6`. See the "Expressions" episode for more detail;
* specify a list of function parameters, e.g. `f(2, 3, 5, 7)`; 
* denote a tuple value, e.g. `x = (1,2,3)`.

Square brackets are used to begin and end a list value, e.g. `first5Primes = [2,3,5,7,11]`, or to access the elements of an ordered collection e.g.
~~~
`first5Primes[2]`
~~~
{: .language-python}

~~~
5
~~~
{: .output}

Braces (sometimes called "curly braces") are used to delimit the key-value pairs in a dictionary, e.g. `ages = {"Fred":42, "David":55, "Jack":31}`

There are two different quote characters for delimiting strings:
* Single: `'`
* Double: `"`

Both are used to delimit string values, e.g. `'abc'`, `"abc"`. When quotes of either type must be included within a string, the opposite type can be used to delimit the string value.

> ## Quotes within Quotes
>
> In a new cell, enter:
> ~~~
> print("David's favourite programming language is X")
> ~~~
> {: .language-python}
> 
> > ## Solution
> > You should see the following output:
> >
> > ~~~
> > David's favourite programming language is X 
> > ~~~
> > {: .source}
> {: .solution}
{: .challenge}

> ## If the delimiting quotes in the print statement above are changed from `"` to `'`, why does a syntax error occur?
> It is possible to "escape" quote characters within a string using the `\` character, e.g. `'David\'s' favourite programming language is X'`.
{: .callout}

We have also seen how triple quotes can be used for multi-line comments (or string values assigned to a variable).

See episodes such as "Python Values and their Type", "Expressions", "Lists", and "Dictionaries" for additional examples of brackets and quotes.

{% include links.md %}
