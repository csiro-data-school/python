---
title: Repeating Actions with Loops
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

#A *for loop* executes commands once for each value in a collection

*   Doing calculations on the values in a list one by one
    is painful. 
*   A *for loop* tells Python to execute some statements once for each value in a list,
    a character string,
    or some other collection.
*   "for each thing in this group, do these operations"


> ## Printing a column of letters - the hard way
> Let's say you want to print each letter of the word 'lead' on a separate line, underneath each other. 
>
> ~~~
> word = 'lead'
> ~~~
> {: .language-python}
>
> With the skills you already have, we could do this by accessing each character in the string using its index.
> For example, we can get the first character of the word `'lead'`, by using `word[0]`. One way to print each 
> character is to usefour `print` statements:
>
>~~~
>print(word[0])
>print(word[1])
>print(word[2])
>print(word[3])
>~~~
>{: .language-python}
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

> 3.  **Fragile**. If we use it with a word that has more characters than what we initially
>    envisioned, it will only display part of the word's characters. A shorter string, on
>    the other hand, will cause an error because it will be trying to display part of the
>    string that don't exist.
>
~~~
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
> The improved version uses a [for loop]({{ page.root }}/reference/#for-loop)
> to repeat an operation --- in this case, printing --- once for each thing in a sequence.
{: .callout)

The general form of a loop is:

~~~
for variable in collection:
    do things using variable
~~~
{: .language-python}

Using the oxygen example above, the loop might look like this:

![loop_image](../fig/loops_image.png)

where each character (`char`) in the variable `word` is looped through and printed one character
after another. The numbers in the diagram denote which loop cycle the character was printed in (1
being the first loop, and 6 being the final loop).

We can call the [loop variable]({{ page.root }}/reference/#loop-variable) anything we like, but
there must be a colon at the end of the line starting the loop, and we must indent anything we
want to run inside the loop. Unlike many other languages, there is no command to signify the end
of the loop body (e.g. `end for`); what is indented after the `for` statement belongs to the loop.

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

> ## for loop syntax
> Which of these are valid `for` loops?
> 1. 
> ~~~
> for word in "Findable, Accessible, Interoperable, Resuable":
>     print("FAIR")
> ~~~
> {: .language-python}
> 2. 
> ~~~
> for word in "Findable, Accessible, Interoperable, Resuable":
>     print(word[0])
> ~~~
> {: .language-python}
> 3.
> ~~~
> for word in "Findable, Accessible, Interoperable, Resuable":
> print(word)
> ~~~
> {: .language-python}
{: .challenge}

## Variable names
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

> ## Reusing variables
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

In this example, we use a different variable, `length`, within the body of the loop. We first assign `length` to `0`
outside the loop, before it starts. Then, within the loop, we update the value of `length`, each time we progress through
the loop. This kind of pattern, where we initialise a variable to 0, then modify its value throughout a loop, is know as an **accumulator**. 



Note also that finding the length of a string is such a common operation
that Python actually has a built-in function to do it called `len`:

~~~
print(len('aeiou'))
~~~
{: .language-python}

~~~
5
~~~
{: .output}

`len` is much faster than any function we could write ourselves,
and much easier to read than a two-line loop;
it will also give us the length of many other things that we haven't met yet,
so we should always use it when we can.

> ## From 1 to N
>
> Python has a built-in function called `range` that creates a sequence of numbers. `range` can
> accept 1, 2, or 3 parameters.
>
> * If one parameter is given, `range` creates an array of that length,
>   starting at zero and incrementing by 1.
>   For example, `range(3)` produces the numbers `0, 1, 2`.
> * If two parameters are given, `range` starts at
>   the first and ends just before the second, incrementing by one.
>   For example, `range(2, 5)` produces `2, 3, 4`.
> * If `range` is given 3 parameters,
>   it starts at the first one, ends just before the second one, and increments by the third one.
>   For exmaple `range(3, 10, 2)` produces `3, 5, 7, 9`.
>
> Using write a loop that uses `range` to print the first 3 positive integers:
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



- Movivating example
- Boolean conditions
- While condition: Block
- range()
- For var in List
- Accumulation, reduction
- Continue, Break

{% include links.md %}

