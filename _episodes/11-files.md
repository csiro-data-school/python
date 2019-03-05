---
title: "Working with Files"
teaching: 0
exercises: 0
questions:
- "How do I work with text files in Python?"
objectives:
- "Understand the difference between text and binary files."
- "Open a text file."
- "Close a file when processing is finished."
- "Read lines of text from a file."
- "Open a text file for writing and write lines of text to it."
- "Understand the importance of closing files when finished with them."
- "Apply a useful pattern for line-by-line processing of text files."
keypoints:
- "First key point. Brief Answer to questions. (FIXME)"
---

## About Files

- Files store data on disk.
- They can be either text or binary files.
- Text files store text data in standard encodings that can be understood by
  many programs.
    - Often have name extensions that indicate the type of file, such as `.py`
      for Python scripts, `.csv` for comma-separated values data,
      and `.txt` for plain text files.
    - There are different encodings for text data that affect how the text is
      stored. Common encodings are ASCII and UTF-8. We will ignore encodings
      from here on.
- Binary files store binary data. Apart from conventions about the ordering of
  bytes on disk, binary files can have almost any internal structure.
    - There are some well documented binary file standards, such as PDF, and
      NetCDF.
    - However, frequently binary files can only be read by the software that
      created them.
- Python supports working with both binary and text files.
- We only explore working with text files here.

## Opening files

To open a file, we use the `open()` function, which returns a file object:

~~~
my_file = open("my_data_file.txt", "r")
~~~
{: .language-python}

- The first argument is a string containing the filename.
- The second argument is the mode string describing the intended use.
  The mode can be:
    - `"r"` : the file will only be read (this is the default)
    - `"w"` : only writing (an existing file with the same name will be erased)
    - `"a"` : for appending; any data written to the file is automatically added to the end
    - `"r+"`: both reading and writing.
- Files are normally opened in text mode. By appending `"b"` to the mode,
  the file will be opened in binary mode.
- If the open succeeds, a file object will be returned.
- If the open fails, an exception will be raised.

> ## What are some reasons that opening a file might fail?
> Try to think of some reasons that opening a file might fail. How common are
> they? Are there any particular situations that your program needs to handle?
>
> Often no special handling apart from displaying an error message is required,
> but thinking about these questions can help us write more robust code.
{: .discussion}

## Closing files

Files need to be closed when they are no longer needed. One reason is that
operating systems can lock files while they are open, to prevent unexpected
changes while the file is in use.

In Python, closing files is a simple call to the `close()` method on the file
object. You can check the status of a file with the `closed` property:

~~~
my_file = open("my_data_file.txt", "r")
# do some processing
print(my_file.closed)  # should print False
my_file.close()
print(my_file.closed)  # should print True
~~~
{: .language-python}

## Reading from a file

Recall that `open()` returns a file object after successfully open a file. This
object can be used to read data from the file. The `readline()` method will be
most useful to us here. It reads a single line from the file. Repeated calls to
`readline()` will return subsequent lines in order until the end of the file is
reached. The newline character (`\n`) is left at the end of the string, and is
only omitted on the last line of the file. This means that the end of the file
is indicated when `readline()` returns an empty string. Blank lines in the file
are indicated by the string `"\n"`.

> ## Read some text from a file
>
> In this exercise, write a Python program to read lines of text from
> `a_few_lines_of_text.txt` and print them one at a time. Prefix each line with
> the line count. Your program should close the file there are no more lines.
>
> You should see this output:
>
> ~~~
> 0 This file contains just a few lines of text.
>
> 1 Not a lot.
>
> 2 Just a few.
> ~~~
> {: .source}
> > ## Solution
> > There are many solutions, but one that only uses file operations presented
> > so far in this episode is:
> >
> > ~~~
> > f = open("a_few_lines_of_text.txt")
> > count = 0  # initialise the line count
> > line = f.readline()  # read the first line before entering the loop
> > while line:  # readline() returns an empty string at end of file
> >     print(count, line)
> >     count = count + 1
> >     line = f.readline()
> > f.close()
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}

For reading lines from a file, you can iterate over the file object. This is memory efficient, fast, and leads to simple code:
~~~
for line in f:
    print(line)
~~~
{: .language-python}

> ## Update your text reading program to use file iteration
> Update your previous program to use the file iteration approach. You should
> see the same output.
> > ## Solution
> > ~~~
> > f = open("a_few_lines_of_text.txt")
> > count = 0  # initialise the line count
> > for line in f:
> >     print(count, line)
> >     count = count + 1
> > f.close()
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}

Iterating a collection where both the data and the index (the line count in our
case) are required is a very common operation, and Python provides the
[`enumerate()`](https://docs.python.org/3/library/functions.html#enumerate) function
for just this purpose.

> ## Update your text reading program to use `enumerate`
> Update your previous program to use the `enumerate()` function. You should
> see the same output.
> > ## Solution
> > ~~~
> > f = open("../data/a_few_lines_of_text.txt")
> > for count, line in enumerate(f):
> >     print(count, line)
> > f.close()
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}

## FIXME
- Write
- Context Managers

## More Information

For more information on basic file IO in Python, please refer to the [Reading and
 Writing Files][python-tutorial-files] section of the Python documentation.

{% include links.md %}

[python-tutorial-files]: https://docs.python.org/3/tutorial/inputoutput.html#reading-and-writing-files
