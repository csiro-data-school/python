---
title: "Working with Files"
start: true
teaching: 20
exercises: 40
questions:
- "How do I open a file in Python?"
- "How do I access the data or text inside an open file?"
objectives:
- "Open a text file."
- "Close a file when processing is finished."
- "Read lines of text from a file."
- "Open a text file for writing and write lines of text to it."
- "Understand the importance of closing files when finished with them."
- "Learn some useful patterns for line-by-line processing of text files with
  Python."
keypoints:
- "Files are opened with the `open()` function."
- "The `open()` function returns a file object."
- "Files need to be closed when they are no longer required by your program."
- "The `close()` method of the file object closes a file."
- "The `with` statement provides an elegant and safe way to automatically close
  your files."
- "Data can be read from text files a line at a time by the `readline()` file
  object method."
- "If you want to process each line of a text file in order, then iteration is
  useful."
- "Data can be written to a file with the `write()` file object method."
- "Patterns are common and repeatable recipes for common problems. The text file
  sequential processing pattern is simple, robust and efficient."

---

## Reading files

Reading files in python uses `for` loops. As a refresher, here is a simple `for` loop in Python:

~~~
for letter in 'ABCDEFGHIJ':
    print(letter)
~~~
{: .language-python}

> ## For loop practice
> Write a `for` loop that generates this image:
>
> .
>
> ..
>
> ...
>
> ....
>
> .....
{: .challenge}

Working with files is a two-step process. We first need to 'open' the file. Then, we can 'read' it line by line.
There is some special syntax for opening files in Python. Behind the scenes, this special sytnax makes sure that the file is
closed again when we are done with it, and that the working memory it occupies becomes freed up for use again. This is the
general recipe for reading a file:

~~~
with open('my_file.txt') as f:
    for line in f:
        print(line)
~~~
{: .language-python}


> ## Open a file
> Fill in the blanks below to open and print the contents of a hypothetical file `data.csv`:
> ~~~
> with open('data.csv') as f:
>     for line in ___:
>         print(____)
> ~~~
> {: .language-python}
{: .challenge}

> ## Open a_few_lines_of_text.txt
> Open and print to screen the contents of `a_few_lines_of_text.txt`
>
> Can you find a file on your computer to open and print? E.g. a .csv data file?
> {: .language-python}
{: .challenge}

In the examples above, we used the `open()` function, which returns a **file** object. This
object is assigned to the name `f`.

There is nothing special about `f` or `line`, we can use any legal variable names here. This should also work:

~~~
with open('dataschool/python/a_few_lines_of_text.txt') as fluffy:
    for unicorn in fluffy:
        print(unicorn)
~~~
{: .language-python}

> ## Opening Files
>
> `open()` is a *function* that takes two arguments
>
> ~~~
> open("my_data_file.txt", "r")
> ~~~
> {: .language-python}

> The first argument, `"my_data_file.txt"` is a *string* containing the filename.

> The second argument, `"r"`, is also a string. This is the *mode* of the open
> file, and indicates how we want to use the file. The mode can be:
>    * `"r"` : the file will only be read (this is the default)
>    * `"w"` : only writing (an existing file with the same name will be erased)
>    * `"a"` : for appending; any data written to the file is automatically added to the end
>    * `"r+"`: both reading and writing.
{: .callout}

> ## File found?
>
> Try and open a non-existent text file:
> ~~~
> with open('flying_circus.txt') as f:
>     for line in f:
>         print(line)
> ~~~
> {: .language-python}
> What happened?
{: .language-python}



## Reading line-by-line

We can also access lines of the file one at a time
using the `readline()` method.

* `readline()` reads a single line from the file as a `string`
* repeated calls to `readline()` will return subsequent lines of the file, in order, until the end of the file is
reached.

> ## When will it end?
> `readline()` leaves the newline character (`\n`) at the end of the string. It omits
> the newline on the last line of the file. This means that the end of the file
> is indicated when `readline()` returns an empty string. This allows blank lines in the file
> to be indicated by the string `"\n"`.
{: .callout}

~~~
with open('example.txt') as f:
    line = f.readline()
    while line:
        print(line)
        line = f.readline()
~~~
{: .language-python}

> ## while `line`
> Examine the following code:
>
> ~~~
> data_list = []
> with open("observation_data.csv", "r") as my_file:
>     header = my_file.readline()
>     line = my_file.readline()
>     while line:
>         data_list.append(line)
>         line = my_file.readline()
> ~~~
> {: .language-python}
>
> What does this code do? Write out an English language explanation
> of each line of code. Discuss you explanation with the person sitting next to you.
>
{: .challenge}

> ## Print some text
>
> In this exercise, write some Python code to read lines of text from
> `a_few_lines_of_text.txt` and print them one at a time.
> Your program should close the file when there are no more lines.
>
> You should see this output:
>
> ~~~
> This file contains just a few lines of text.
>
> Not a lot.
>
> Just a few.
> ~~~
> {: .source}
>
> Now, modify your code so it also prints out the line number before the line's text.
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
>
> > ## Solution
> > One possible solution is:
> >
> > ~~~
> > count = 0  # initialise the line count
> > with open("a_few_lines_of_text.txt") as f:
> >     line = f.readline()  # read the first line before entering the loop
> >     while line:  # readline() returns an empty string at end of file
> >         print(count, line)
> >         count = count + 1
> >         line = f.readline()
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}

> ## Why all the blank lines?
> In the previous exercise, the input file does not contain blank lines, so where are they coming from?
> The answer is the `print` function. `print` is adding a newline character to the string read from the
> file, which already contains a newline character.
{: .callout }



> ## Using file iteration
> Update your previous program to use the file iteration approach. You should
> see the same output.
> > ## Solution
> > ~~~
> > count = 0  # initialise the line count
> > with open("a_few_lines_of_text.txt") as f:
> >     for line in f:
> >         print(count, line)
> >         count = count + 1
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}

Iterating a collection where both the data and the index (the line count in our
case) are required is a very common operation, and Python provides the
[`enumerate()`][enumerate-function] function
for just this purpose.

Let's see how this works for a list first:

~~~
my_list = ['a','b','c','d','e']
for index, value in enumerate(my_list):
    print(index, value)
~~~
{: .language-python}

> ## Update your text reading program to use `enumerate`
> Update your previous program to use the `enumerate()` function. You should
> see the same output.
> > ## Solution
> > ~~~
> > with open("a_few_lines_of_text.txt") as f:
> >     for count, line in enumerate(f):
> >         print(count, line)
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}

## Writing to a File

Text can be written to a text file that has been opened for writing with the
`write()` method on the file object:
~~~
with open("my_text.txt", "w") as f:
    f.write("This is a line of text")
~~~
{: .language-python}

> ## Write to a file
>
> Use Python to make a new file and save some text:
> ~~~
> with open("new_file", "w") as f:
>     f.write("Some initial text")
>     f.write("A second line of text")
> ~~~
> Now, open your new file using your favourite text editor.
> Is the content what you expect? If not, how would you fix it?
>
> Open your file again and try this fix:
> ~~~
> with open("new_file", "w") as f:
>     f.write("Line number one\n")
>     f.write("Line number two\n")
> ~~~
> {: .language-python}
> Open it again with your favourite text editor. What happened to your original text?
{: .challenge}

> ## `write()` and line breaks
> Note that `write()` does not add a newline to the end.
> If you want a newline or carriage return, you need to add it yourself
> using the string `\n`.
{: .callout}




## Putting it all together
> ## Reading and writing files at the same time
> In this exercise, write a Python program to read lines of text from
> `a_few_lines_of_text.txt`. For each line, write the line number followed by `": "`
> and then the input text to a separate file called "numbered_lines_of_text.txt".
> For example, if the third line of text is
> "this is the third line" then the third line of
> the new file would be "2: this is the third line".
>
> Your program should close both files when finished, including after any errors
> are encountered.
>
> Hint: `with` can be used to safetly open multiple files at once, e.g.
> `with open("a_file") as file_one, open("another_file) as file_two:` ...
>
> > ## Solution
> > ~~~
> > with open("../data/a_few_lines_of_text.txt") as f_in, open("numbered_lines_of_text.txt", "w") as f_out:
> >     for count, line in enumerate(f_in):
> >         f_out.write(count + ': ' + line + '\n'))
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}


## More Information

For more information on basic file IO in Python, please refer to the [Reading and
 Writing Files][python-tutorial-files] section of the Python documentation.

{% include links.md %}

[python-tutorial-files]: https://docs.python.org/3/tutorial/inputoutput.html#reading-and-writing-files
[with-statement]: https://docs.python.org/3/reference/compound_stmts.html#with
[enumerate-function]: https://docs.python.org/3/library/functions.html#enumerate
