---
title: "Python Syntax"
teaching: 20
exercises: 20
questions:
- "What constitutes legal Python code?"
- "How can code be commented?"
- "What are keywords, identifiers, expressions, statements?"
- "What is indentation used for in Python?"
- "What kinds of brackets are used in Python code?"
- "Where can I find out more about Python style guidelines?"
objectives:
- "Learn about the different kinds of Python comments"
- "Understand the significance of indentation in Python code"
- "Know when line continuation characters are required"
- "Learn about key aspects of Python syntax"
- "Understand the different kinds of 'brackets' in Python"
keypoints:
- "Legal Python code follows rules of syntax"
- "Python allows single and multiple line comments"
- "A Python keyword is a symbol that has special meaning in a Python script"
- "An identifier names a value, e.g. as in the assignment statement: x = 21"
- "A Python script consists of sequence of statements that make use of keywords, identifiers and expressions"
- "Indentation introduces a code block"
- "`[` and `]` are used to surround literal list values"
- "`{` and `}` are used to surround literal dictionary values"
- "`(` and `)` are used surround function parameters and to change the priority of expression evaluation order"
- "The [PEP 8 Python Style Guidelines](https://www.python.org/dev/peps/pep-0008/) provide more code layout and convention details"
---

## Notes

Also keywords, identifiers, expressions. As seen in previous episodes. Including line continuation.

https://www.tutorialsteacher.com/python/python-basic-syntax

https://realpython.com/python-comments-guide/

https://developer.rhino3d.com/guides/rhinopython/python-statements/

## Syntax
Every language has grammatical rules. The syntax of any language dictates the construction of "legal" sentences.

The syntax of a programming language determines what counts as a legal or well-formed program (or script).

A Python program consists of a sequence of syntactically correct "sentences" entered at a Python interpreter prompt (or into Jupyter notebook cells) or contained within files.

This episode introduces the following Python syntax elements, many of which are elaborated upon in other episodes: comments, keywords, identifiers, expressions, statements, indentation and code blocks, brackets and quotes.

## Comments
Comments are annotations embedded in code to summarise and explain the programmer's intent.

In Python there are two styles of comment: single line and multiple line.

## Single Line Comments
Anything that follows a `#` symbol on a line is considered a comment. The `#` may appear anywhere on a line. 

> ## Write code containing single-line comments
>
> Open up your text editor, entering the following Python code:
>
> ~~~
> print("Hello")
> # print("Again")
> print("World")  # trailing comment
> ~~~
> {: .language-python}
>
> Save the file as `hello-world-single.py` and run it from command-line terminal with:
>
> ~~~
> $ python3 hello-world-single.py
> ~~~
> {: .language-bash}
> > ## Solution
> > You should see this output:
> >
> > ~~~
> > Hello
> > World
> > ~~~
> > {: .source}
> > 
> > Notice that since the second `print` was commented, `Again` did not appear in the output. Note also that the text `trailing comment` was ignored by the Python interpreter.
> {: .solution}
{: .challenge}

## Multiple Line Comments
Triple single `'` or double `"` quotes begin and end a multi-line string, but if you don't assign that string to a variable, then any code within it has no effect and is effectively commented out.

> ## Write code containing multiple-line comments
>
> Open up your text editor, entering the following Python code:
>
> ~~~
> """
> This script outputs Hello World
> """
> print("Hello World")
> ~~~
> {: .language-python}
>
> Save the file as `hello-world-multiple.py` and run it from command-line terminal with:
>
> ~~~
> $ python3 hello-world-multiple.py
> ~~~
> {: .language-bash}
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

Multi-line comments, or doc strings, are used to add documentation comments to scripts, functions, classes, modules, some of which will be covered in other episodes.

## Keywords 
In Python, keywords are special words used in core language constructs. An example of a Python keyword is `if`, used within so-called conditional statements.

> ## Keywords
>
> Entering `help()` at a Python command prompt (or in a Jupyter notebook cell), then entering `keywords` at the prompt that follows, will show the available Python keywords.
>
> Run the Python interpreter from a command-line terminal with:
>
> ~~~
> $ python3
> ~~~
> {: .language-bash}
>
> Then enter:
> ~~~
> help()
> ~~~
> {: .language-bash}
> 
> Then at the "help>" prompt that follows, enter:
> ~~~
> keywords
> ~~~
> {: .language-bash}
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

Spaces and tabs separate keywords, identifiers and expressions. They also play a special role in indentation levels in code blocks, which is covered next. 

## Identifiers
A Python identifier is a name used to identify a variable, function, class, module or other object. An identifier can start with a letter (a to z, A to Z) or an underscore (_) but may contain letters, underscores and digits (0 to 9) thereafter.

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
Python statements make use of keywords, identifiers, and expressions. The following statement assigns the value of the `42` expression from the last section to the variable designated by the identifier `meaning_of_life`:

> ~~~
> meaning_of_life = 3 * 10 + 12
> ~~~
> {: .language-python}

More than one statement can appear on a single line, each statement separated by a semi-colon, e.g.

> ~~~
> x=42; print("the meaning of life is {}", x)
> ~~~
> {: .language-python}

It tends to be less confusing to keep each line as simple as possible however:

> ~~~
> x=42
> print("the meaning of life is {}", x)
> ~~~
> {: .language-python}

An example of another statement is:

> ~~~
> assert meaning_of_life == 42
> ~~~
> {: .language-python}

which asserts that the variable `meaning_of_life` is assumed to equal `42`. If not, an error will be generated. The notion of assertions will be further explored in other episodes, the "Testing" epiode in particular.

## Indentation and Code Blocks
Python uses indentation level to determine the start and end of code blocks - unlike many languages which use braces (`{` and `}`), or others that use keywords such as `begin` and `end`.

Code blocks are used in a number of contexts in Python including `if` statements, loops, functions, and classes. We won't dwell on the details of such constructs in this episode, merely give simple examples of indentation and blocks.

The following shows a simple code block, introduced by a line ending in a colon with subsequent lines (just one in this case) indented by four spaces. Any number of spaces or even tabs can be used within a block, so long as each line within that block is indented to the same level. Four spaces are normally used by convention. The main point is to be consistent.

> ~~~
> if 3 > 2:
>    print("inside the block")  # this line is indented four spaces
> ~~~
> {: .language-python}

> ## Code Blocks
>
> Open up your text editor, entering the following Python code:
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
> Save the file as `multiple-blocks.py` and run it from command-line terminal with:
>
> ~~~
> $ python3 multiple-blocks.py
> ~~~
> {: .language-bash}
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

A code block may also introduce a new "scope" for variables, but the episode "Writing Functions" will cover this.

## Line Continuation
Some statements are long enough that it may be necessary, or at least desirable, to spread them over multiple lines. Suppose we have an expression that we would like to split over multiple lines:

> ~~~
> obliquity = degrees - 46.8150 * T - 0.00059 * (T * T) + 0.001813 * (T * T * T)
> ~~~

The following would lead to a syntax error:

> ~~~
> obliquity = degrees - 46.8150 * T - 
>             0.00059 * (T * T) + 
>             0.001813 * (T * T * T)
> ~~~

In Python, the line continuation character `\` must be used at the end of each line for this to satisfy the rules of syntax:

> ~~~
> obliquity = degrees - 46.8150 * T - \
>             0.00059 * (T * T) + \
>             0.001813 * (T * T * T)
> ~~~

## Brackets

## Quotes

> ~~~
> ???
> ~~~
> {: .language-python}

> ## ???
>
> This 
> Open up your text editor, entering the following Python code:
>
> ~~~
> ???
> ~~~
> {: .language-python}
>
> Save the file as `???.py` and run it from command-line terminal with:
>
> ~~~
> $ python3 ???.py
> ~~~
> {: .language-bash}
> > ## Solution
> > You should see this output:
> >
> > ~~~
> > ???
> > ~~~
> > {: .source}
> >
> {: .solution}
{: .challenge}

{% include links.md %}