---
title: Repeating Actions with For Loops
teaching: 30
exercises: 30
questions:
- "How can I do the same operations on many different values?"
objectives:
- "Explain what a `for` loop does."
- "Correctly write `for` loops to repeat simple calculations."
- "Trace changes to a loop variable as the loop runs."
- "Trace changes to other variables as they are updated by a `for` loop."
- "Combine `for` loops with conditionals to process collections of data."

keypoints:
- "Use `for variable in sequence` to process the elements of a sequence one at a time."
- "The body of a `for` loop must be indented."
- "Use `len(thing)` to determine the length of something that contains other values."
- "Use accumulator structures with a `for` loop to update the value of an existing variable"
---

## A `for` loop executes commands once for each value in a collection

*   Doing calculations on the values in a list one by one
    is painful. 
*   A *for loop* tells Python to execute some statements once for each value in a list,
    a character string,
    or some other collection.
*   "for each thing in this group, do these operations"


> ## Printing a column of letters - the hard way
>
> Let's say you want to print each letter of the word 'lead' on a separate line, underneath each other. 
>
> ~~~
> word = 'lead'
> ~~~
> {: .language-python}
>
> With the skills you already have, we could do this by accessing each character in the string using its index.
> For example, we can get the first character of the word `'lead'`, by using `word[0]`. One way to print each 
> character is to use four `print` statements:
>
> ~~~
> print(word[0])
> print(word[1])
> print(word[2])
> print(word[3])
> ~~~
> {: .language-python}
>
> ~~~
> l
> e
> a
> d
> ~~~
> {: .output}
>
> While this works, it is a bad approach for three reasons:
>
> 1.  **Not scalable**. Imagine you need to print the characters of a string that is hundreds
>     of letters long.  It might be easier just to type them in manually.
>
> 2.  **Difficult to maintain**. If we want to decorate each printed character with an
>    asterix or any other character, we would have to change four lines of code. While
>    this might not be a problem for short strings, it would definitely be a problem for
>    longer ones.
>
> 3.  **Fragile**. If we use it with a word that has more characters than what we initially
>    envisioned, it will only display part of the word's characters. A shorter string, on
>    the other hand, will cause an error because it will be trying to display part of the
>    string that don't exist.
>
> ~~~
> word = 'tin'
> print(word[0])
> print(word[1])
> print(word[2])
> print(word[3])
> ~~~
> {: .language-python}
>
> ~~~
> t
> i
> n
> ~~~
> {: .output}
>
> ~~~
> ---------------------------------------------------------------------------
> IndexError                                Traceback (most recent call last)
> <ipython-input-3-7974b6cdaf14> in <module>()
>       3 print(word[1])
>       4 print(word[2])
> ----> 5 print(word[3])
> 
> IndexError: string index out of range
> ~~~
> {: .error}
>
> The alternative way of doing this is to use a `for` loop:
>
> ~~~
> word = 'lead'
> for char in word:
>    print(char)
>
> ~~~
> {: .language-python}
>
> ~~~
> l
> e
> a
> d
> ~~~
> {: .output}
>
> This is shorter --- certainly shorter than something that prints every character in a
> hundred-letter string --- and more robust as well:
>
> ~~~
> word = 'oxygen'
> for char in word:
>    print(char)
> ~~~
> {: .language-python}
>
> ~~~
> o
> x
> y
> g
> e
> n
> ~~~
> {: .output}
>
> The improved version uses a `for` loop
> to repeat an operation --- in this case, printing --- once for each thing in a sequence.
{: .callout}


The general form of a loop is:
> ~~~
> for variable in collection:
>     do things using variable
> ~~~
> {: .language-python}

Our example demonstrates all the parts of this general `for` loop form:

> ~~~
> word = 'oxygen'
> for char in word:
>    print(char)
> ~~~
> {: .language-python}

Here, we have a:

* **collection** `word`
* **body** `print(char)`
* **loop variable** `char`

This image conveys how a computer processes and understands this `for` loop, one step at a time:

![loop_image](../fig/loops_image.png)

Each character `char` in the variable `word` is looped through and printed one character
after another. The numbers in the diagram denote which loop cycle the character was printed in (1
being the first loop, and 6 being the final loop).

We can call the loop variable anything we like, but:

* there must be a **colon** at the end of the line starting the loop
* and we must **indent** anything we want to run inside the loop. 

> ## anatomy of a `for` loop
> Consider the following Python code:
> ~~~
> for my_int in [1,2,3,4,5,6,7,8,9]:
>     print(my_int**2)
> ~~~
> {: .language-python}
> 1. What is the variable name?
> 2. What is the value of the variable at the end of the loop?
> 3. What is the body of the loop?
> 4. Which part is the collection?
> 5. How many times does the body of the loop get executed?
> 6. What is the final value of `my_int`?
{: .challenge}


## The body of a loop can contain many statements.

Unlike many other languages, there is no command to signify the end
of the loop body (e.g. `end for`); what is indented after the `for` statement belongs to the loop.

*   But no loop should be more than a few lines long.
*   Hard for human beings to keep larger chunks of code in mind.

~~~
primes = [2, 3, 5]
for p in primes:
    squared = p ** 2
    cubed = p ** 3
    print(p, squared, cubed)
~~~
{: .language-python}
~~~
2 4 8
3 9 27
5 25 125
~~~
{: .output}


> ## `for` loop syntax
> Which of these are valid `for` loops?
>
> 1. 
> ~~~
> for word in ["Findable", "Accessible", "Interoperable", "Resuable"]:
>     print("FAIR")
> ~~~
> {: .language-python}
>
> 2. 
> ~~~
> for word in ["Findable", "Accessible", "Interoperable", "Resuable"]:
>     print(word[0])
> ~~~
> {: .language-python}
>
> 3.
> ~~~
> for word in ["Findable", "Accessible", "Interoperable", "Resuable"]:
> print(word)
> ~~~
> {: .language-python}
{: .challenge}

## Loop Variables
In the example above, the loop variable was given the name `word`. There is nothing special
about this variable name, `word` was chosen as it makes sense in the context. Just `w` or
even `flibble` would have worked as well; the important thing is to choose a name that will
help you understand your code next time you want to work on it!

> ## What's in a name?
>
> Consider the `for` loop from the last exercise:
> 
> ~~~
> for word in "Findable, Accessible, Interoperable, Resuable":
>     print(word)
> ~~~
> {: .language-python}
> 
> 1. Change the variable name to `x`. How many times do you need to replace `word`? 
> 2. Now change it again, to something of your choosing. 
> 3. Can you think of / find a variable name that **doesn't** work?
{: .challenge}

> ## Reusing variable names
> ~~~
> letter = 'z'
> print(letter)
> for letter in 'abc':
>     print(letter)
> print('after the loop, letter is', letter)
> ~~~
> {: .language-python}
> Try out this code snippet. Explain the results to your neighbour.
{: .challenge}

> ## Persistance of loop variables
> Run this example `for` loop code:
> ~~~
> length = 0
> for vowel in 'aeiou':
>    length = length + 1
> print('There are', length, 'vowels')
> ~~~
> {: .language-python}
> What is the value of `vowel` now? Why?
{: .challenge}

## From 1 to N: using `range` for iteration

Python has a built-in function called `range` that creates a sequence of numbers. 

* `range` does *not* return a list: the numbers are produced on demand
* `range(N)` is the numbers 0..N-1. This is exactly the legal indices of a list or character string of length N.

> ## difference between `range` and `list`
> Try:
> ~~~
> print(range(10))
> ~~~
> {: .language-python}
> Is this what you expected?
> Now try:
> ~~~
> print(list(range(10)))
> ~~~
> {: .language-python}
> Now run and compare the following code snippets:
> ~~~
> for i in range(100000000):
>     pass
>
> for i in list(range(100000000)):
>     pass
> ~~~
> {: .language-python}
> 1. Are the two `for` loops equivalent?
> 2. What do you notice that is different?
{: .challenge}

For efficency, the elements in a range are produced on the fly:
~~~
print('a range is not a list:', range(0, 3))
for number in range(0,3):
    print(number)
~~~
{: .language-python}
~~~
a range is not a list: range(0, 3)
0
1
2
~~~
{: .output}

`range` can accept 1, 2, or 3 parameters.

* If one parameter is given, `range` creates an array of that length,
   starting at zero and incrementing by 1.
   For example, `range(3)` produces the numbers `0, 1, 2`.
* If two parameters are given, `range` starts at
   the first and ends just before the second, incrementing by one.
   For example, `range(2, 5)` produces `2, 3, 4`.
* If `range` is given 3 parameters,
   it starts at the first one, ends just before the second one, and increments by the third one.
   For exmaple `range(3, 10, 2)` produces `3, 5, 7, 9`.

> ## Write a loop that uses `range` to print the first 3 positive integers:
>
> ~~~
> 1
> 2
> 3
> ~~~
> {: .language-python}
>
> > ## Solution
> > ~~~
> > for i in range(1, 4):
> >     print(i)
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}

> ## Even integers
> Write a loop that uses `range` to print all even integers between 0 and 100 inclusive.
> > ## Solution
> > ~~~
> > for i in range(0, 101, 2):
> >     print(i)
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}

## The accumulator structure

Here's another loop that repeatedly updates a variable:
~~~
length = 0
for vowel in 'aeiou':
    length = length + 1
print('There are', length, 'vowels')
~~~
{: .language-python}

~~~
There are 5 vowels
~~~
{: .output}

It's worth tracing the execution of this little program step by step.
Since there are five characters in `'aeiou'`,
the statement on line 3 will be executed five times.
The first time around,
`length` is zero (the value assigned to it on line 1)
and `vowel` is `'a'`.
The statement adds 1 to the old value of `length`,
producing 1,
and updates `length` to refer to that new value.
The next time around,
`vowel` is `'e'` and `length` is 1,
so `length` is updated to be 2.
After three more updates,
`length` is 5;
since there is nothing left in `'aeiou'` for Python to process,
the loop finishes
and the `print` statement on line 4 tells us our final answer.

In this example, `vowel` is the loop variable, but we don't actually use it in the 
body of the loop. Despite this, it still exists after the loop has finished.



In this example, we use a different variable, `length`, within the body of the loop. We first assign `length` to `0`
outside the loop, before it starts. Then, within the loop, we update the value of `length`, each time we progress through
the loop. This kind of pattern, where we initialise a variable to 0, then modify its value throughout a loop, is know as an **accumulator**. 

> ## Practice Accumulating
>
> Fill in the blanks in each of the programs below
> to produce the indicated result.
>
> ~~~
> # Total length of the strings in the list: ["red", "green", "blue"] => 12
> total = 0
> for word in ["red", "green", "blue"]:
>     ____ = ____ + len(word)
> print(total)
> ~~~
> {: .language-python}
>
> ~~~
> # List of word lengths: ["red", "green", "blue"] => [3, 5, 4]
> lengths = ____
> for word in ["red", "green", "blue"]:
>     lengths.____(____)
> print(lengths)
> ~~~
> {: .language-python}
>
> ~~~
> # Concatenate all words: ["red", "green", "blue"] => "redgreenblue"
> words = ["red", "green", "blue"]
> result = ____
> for ____ in ____:
>     ____
> print(result)
> ~~~~
> {: .language-python}
>
> ~~~
> # Create acronym: ["red", "green", "blue"] => "RGB"
> # write the whole thing
> ~~~
> {: .language-python}
{: .challenge}

> ## Cumulative Sum
>
> Reorder and properly indent the lines of code below
> so that they print an array with the cumulative sum of data.
> The result should be `[1, 3, 5, 10]`.
>
> ~~~
> cumulative += [sum]
> for number in data:
> cumulative = []
> sum += number
> print(cumulative)
> data = [1,2,2,5]
> ~~~
> {: .language-python}
{: .challenge}




> ## Computing Powers With Loops
>
> Exponentiation is built into Python:
>
> ~~~
> print(5 ** 3)
> ~~~
> {: .language-python}
>
> ~~~
> 125
> ~~~
> {: .output}
>
> Write a loop that calculates the same result as `5 ** 3` using
> multiplication (and without exponentiation).
>
> > ## Solution
> > ~~~
> > result = 1
> > for i in range(0, 3):
> >     result = result * 5
> > print(result)
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}

> ## Reverse a String
>
> Knowing that two strings can be concatenated using the `+` operator,
> write a loop that takes a string
> and produces a new string with the characters in reverse order,
> so `'Newton'` becomes `'notweN'`.
>
> > ## Solution
> > ~~~
> > newstring = ''
> > oldstring = 'Newton'
> > for char in oldstring:
> >     newstring = char + newstring
> > print(newstring)
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}

> ## Counting Vowels
>
> 1. Write a loop that counts the number of vowels in a character string.
> 2. Test it on a few individual words and full sentences.
> 3. Once you are done, compare your solution to your neighbor's.
>    Did you make the same decisions about how to handle the letter 'y'
>    (which some people think is a vowel, and some do not)?
>
> > ## Solution
> > ~~~
> > vowels = 'aeiouAEIOU'
> > sentence = 'Mary had a little lamb.'
> > count = 0
> > for char in sentence:
> >     if char in vowels:
> >         count += 1
> >
> > print("The number of vowels in this string is " + str(count))
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}


> ## Sorting a List Into Buckets
>
> In our `data` folder, large data sets are stored in files whose names start with
> "inflammation-" and small data sets -- in files whose names start with "small-". We
> also have some other files that we do not care about at this point. We'd like to break all
> these files into three lists called `large_files`, `small_files`, and `other_files`,
> respectively.
>
> Add code to the template below to do this. Note that the string method
> [`startswith`](https://docs.python.org/3/library/stdtypes.html#str.startswith)
> returns `True` if and only if the string it is called on starts with the string
> passed as an argument, that is:
>
> ~~~
> "String".startswith("Str")
> ~~~
> {: .language-python}
> ~~~
> True
> ~~~
> {: .output}
> But
> ~~~
> "String".startswith("str")
> ~~~
> {: .language-python}
> ~~~
> False
> ~~~
> {: .output}
>Use the following Python code as your starting point:
> ~~~
> files = ['inflammation-01.csv',
>          'myscript.py',
>          'inflammation-02.csv',
>          'small-01.csv',
>          'small-02.csv']
> large_files = []
> small_files = []
> other_files = []
> ~~~
> {: .language-python}
>
> Your solution should:
>
> 1.  loop over the names of the files
> 2.  figure out which group each filename belongs
> 3.  append the filename to that list
>
> In the end the three lists should be:
>
> ~~~
> large_files = ['inflammation-01.csv', 'inflammation-02.csv']
> small_files = ['small-01.csv', 'small-02.csv']
> other_files = ['myscript.py']
> ~~~
> {: .language-python}
>
> > ## Solution
> > ~~~
> > for file in files:
> >     if file.startswith('inflammation-'):
> >         large_files.append(file)
> >     elif file.startswith('small-'):
> >         small_files.append(file)
> >     else:
> >         other_files.append(file)
> >
> > print('large_files:', large_files)
> > print('small_files:', small_files)
> > print('other_files:', other_files)
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}


> ## Computing the Value of a Polynomial
>
> The built-in function `enumerate` takes a sequence (e.g. a list) and generates a
> new sequence of the same length. Each element of the new sequence is a pair composed of the index
> (0, 1, 2,...) and the value from the original sequence:
>
> ~~~
> for i, x in enumerate(xs):
>     # Do something using i and x
> ~~~
> {: .language-python}
>
> The code above loops through `xs`, assigning the index to `i` and the value to `x`.
>
> Suppose you have encoded a polynomial as a list of coefficients in
> the following way: the first element is the constant term, the
> second element is the coefficient of the linear term, the third is the
> coefficient of the quadratic term, etc.
>
> ~~~
> x = 5
> cc = [2, 4, 3]
> ~~~
> {: .language-python}
>
> ~~~
> y = cc[0] * x**0 + cc[1] * x**1 + cc[2] * x**2
> y = 97
> ~~~
> {: .output}
>
> Write a loop using `enumerate(cc)` which computes the value `y` of any
> polynomial, given `x` and `cc`.
>
> > ## Solution
> > ~~~
> > y = 0
> > for i, c in enumerate(cc):
> >     y = y + x**i * c
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}


{% include links.md %}

