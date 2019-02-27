---
title: "Creating and Running Python Scripts"
teaching: 10
exercises: 15
questions:
- "How can I run Python scripts and see results from them?"
- "How do you write comments?"
objectives:
- "Create a Python script and save it with an appropriate name."
- "Run the Python script from the command-line."
- "Write comments in the script, and use them to disable a line of code."
keypoints:
- "Python scripts are plain text files, usually with the `.py` extension."
- "You execute Python scripts at the command-line with the Python interpreter."
- "Values are displayed using the `print` function."
- "Comments are indicated with `#`. Anything between the `#` and the end of the line is ignored."
---

## Python programs are plain text files

*   They have the `.py` extension to let everyone (including the operating system)
    know it is a Python program.
    *   This is convention, not a requirement.
*   It's common to write them using a text editor.
    * Once your code gets more complex, you may switch to using a good Python
      Integrated Development Environment (IDE), or at the very least
      a syntax-aware text editor.
    * For this lesson, a simple text editor will be fine. Use whatever you feel
      comfortable with.

> ## Write your first Python program
>
> The traditional first program outputs "Hello World". So, open up your text
> editor with a new file. Enter the following Python code:
>
> ~~~
> print("Hello world!")
> ~~~
> {: .language-python}
>
> Now save the file as `hello-world.py`.
>
> Next, open up a command-line terminal, and change to the directory that you
> saved `hello-world.py` to. At the command-line, call the Python interpreter
> and tell it to run your script:
>
> ~~~
> $ python3 hello-world.py
> ~~~
> {: .language-bash}
> > ## Solution
> > You should see this output:
> >
> > ~~~
> > Hello world!
> > ~~~
> > {: .source}
> {: .solution}
{: .challenge}

> ## Why is the command `python3` instead of just `python`?
> This lesson uses Python 3, which is the current major version of Python.
> However, a lot of systems still have Python 2 as the default version which
> will be called if you use the `python` command. If `python3` doesn't work,
> then try `python`. On your system this may be Python 3. You can always check
> the versions by trying the following at the command-line:
>
> ~~~
> $ python --version
> $ python2 --version
> $ python3 --version
> ~~~
> {: .language-bash}
{: .callout}

## Comments

- Comments in all versions of Python use the `#` symbol.
- All text between the `#` and the end of the current line will be ignored.
- Comments can occur at the start of a line, or part-way along.
- There are conventions and guidelines for comments. Some important ones are:
    - Comments describing a block of code should be placed before the code.
    - Describe why you are doing something, don't just rephrase what the code
      does.

> ## Identify the good and bad comments
> In the following code, try to identify which comment is useful and which is
> not. Why?
> ~~~
> # Filter out missing values, because they break my analysis
> filter_missing_values(my_data)
> 
> y = 2 * x + 7  # Multiply x by 2, add 7, then store in y
> ~~~
> {: .language-python}
> > ## Solution
> > 1. The first comment is useful because it tells us something of the
> > programmer's intent that is not obvious from the code itself.
> > 2. The second comment simply rephrases what the code does. It does not add value.
> {: .solution}
{: .challenge}

> ## Modify your first program with some comments
>
> FIXME: Is this too easy?
>
> Open up `hello-world.py` with your editor again, and comment out the `print`
> line. Then run the file once more. What happens? Why?
> > ## Solution
> > There should be no output from your program, since you commented out the
> > only line of code.
> {: .solution}
{: .challenge}

> ## Experiment
>
> FIXME: Is this too easy?
>
> Spend a few minutes experimenting with your hello world program.
> 
> Suggestions:
> - Uncomment the `print` statement.
> - Add a comment to the end of the line.
> - Change the progam to print a different message.
{: .challenge}

{% include links.md %}

