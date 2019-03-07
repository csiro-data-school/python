---
title: "Python Syntax"
teaching: 10
exercises: 10
questions:
- "What constitutes a legal Python code?"
- "How can code be commented in Python?"
- "What are keywords, identifiers, expressions, statements in Python?"
- "What is indentation used for in Python?"
- "What kinds of brackets are used in Python code?"
objectives:
- "Learn about the different kinds of comments and their uses"
- "Understand the significance of indentation in Python code"
- "Know when line continuation characters are required"
- "Learn about key aspects of Python syntax"
- "Understand the different kinds of 'brackets' in Python"
keypoints:
- "Legal Python code follows the laws of syntax"
- "Python allows single and multiple line comments"
- "A Python keyword is a symbol that has special meaning in a Python script"
- "An identifier names a value, e.g. x = 21"
- "A Python script consists of sequence of statements that make use of expressions and keywords"
- "Indentation introduces a code block"
- "`[` and `]` are used to surround literal list values"
- "`{` and `}` are used to surround literal dictionary values"
- "`(` and `)` are used surround function parameters and to change the priority of expression evaluation order"
---

## Notes

Also keywords, identifiers, expressions. As seen in previous episodes. Including line continuation.

https://www.tutorialsteacher.com/python/python-basic-syntax

https://realpython.com/python-comments-guide/

https://developer.rhino3d.com/guides/rhinopython/python-statements/

PEP-8?

Line continuation

More than one statement can appear on a single line, each separated by a semi-colon

## Whitespace

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
"""
This script outputs Hello World
"""
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

## Keywords, identifiers, expressions, statements 

## Indentation and Code Blocks

## Line continuation

## Brackets

{% include links.md %}