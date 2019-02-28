---
title: "Working with Files"
teaching: 0
exercises: 0
questions:
- "How do I work with text files in Python?"
objectives:
- "Understand the difference between text and binary files."
- "Open a text file."
- "Read lines of text from a file."
- "Close a file when processing is finished."
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
my_file = open("my_data_file.txt", "w")
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

## Reading from a file

Recall that `open()` returns a file object after successfully open a file. This
object can be used to read data from the file. The `readline()` method will be
most useful to us here. It reads a single line from the file. Repeated calls to
`readline()` will return subsequent lines in order until the end of the file is
reached. The newline character (`\n`) is left at the end of the string, and is
only omitted on the last line of the file. This means that the end of the file
is indicated when `readline()` returns an empty string. Blank lines in the file
are indicated by the string `"\n"`.

## FIXME
- Write
- Closing
- Context Managers

## More Information

For more information on basic file IO in Python, please refer to the [Reading and
 Writing Files][python-tutorial-files] section of the Python documentation.

{% include links.md %}

[python-tutorial-files]: https://docs.python.org/3/tutorial/inputoutput.html#reading-and-writing-files
