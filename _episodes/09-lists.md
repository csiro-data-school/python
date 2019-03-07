---
title: "Lists"
teaching: 0
exercises: 0
questions:
- "How can I store multiple values?"
objectives:
- "Explain why programs need collections of values."
- "Write programs that create flat lists, index them, slice them, and modify them through assignment and method calls."
keypoints:
- "A list stores many values in a single structure."
- "Use an item's index to fetch it from a list."
- "Lists' values can be replaced by assigning to them."
- "Appending items to a list lengthens it."
- "Use `del` to remove items from a list entirely."
- "The empty list contains no values."
- "Lists may contain values of different types."
- "Character strings can be indexed like lists."
- "Character strings are immutable."
- "Python uses 0-based indexing. The first index is zero, the second index is one, and so forth"
- "Indexing beyond the end of the collection is an error."
---
## Lists are collections of data 

We have already encountered some simple Python types like integers, strings and booleans. Now we will see how we can group multiple values together in a collection – like a list of numbers or a list of names. Collections in Python are containers that are used to store collections of data, and include lists, dictionaries and tuples, which we will cover in future lessons. 

*   A list stores many values in a single structure.
*   Doing calculations with a hundred variables called `weight_001`, `weight_002`, etc.,
    would be at least as slow as doing them by hand.
*   Use a *list* to store many values together.
    *   Contained within square brackets `[...]`.
    *   Values separated by commas `,`.
*   Use `len` to find out how many values are in a list.

~~~
weights = [173, 175, 277, 275, 176]
print('weights:', weights)
print('length:', len(weights))
~~~
{: .python}
~~~
weights: [173, 175, 277, 275, 176]
length: 5
~~~
{: .output}

## Use an item's index to fetch it from a list.

*   To get the first element of this list we use the index 0 because python is a 0-based indexing language. 
*   Indexes are written within square brackets `[]`.

~~~
print('zeroth item of weights:', weights[0])
print('fourth item of weights:', weights[4])
~~~
{: .python}
~~~
zeroth item of weights: 173
fourth item of weights: 176
~~~
{: .output}

## Lists' values can be replaced by assigning to them.

*   Use an index expression on the left of assignment to replace a value.

~~~
weights[0] = 265
print('weights is now:', weights)
~~~
{: .python}
~~~
weights are now: [0.265, 0.275, 0.277, 0.275, 0.276]
~~~
{: .output}

## Appending items to a list lengthens it.

*   Use `list_name.append` to add items to the end of a list.

~~~
primes = [2, 3, 5]
print('primes is initially:', primes)
primes.append(7)
primes.append(9)
print('primes has become:', primes)
~~~
{: .python}
~~~
primes is initially: [2, 3, 5]
primes has become: [2, 3, 5, 7, 9]
~~~
{: .output}

*   `append` is a *method* of lists.
    *   Like a function, but tied to a particular object.
*   Use `object_name.method_name` to call methods.
    *   Deliberately resembles the way we refer to things in a library.
*   We will meet other methods of lists as we go along.
    *   Use `help(list)` for a preview.
*   `extend` is similar to `append`, but it allows you to combine two lists.  For example:

~~~
teen_primes = [11, 13, 17, 19]
middle_aged_primes = [37, 41, 43, 47]
print('primes is currently:', primes)
primes.extend(teen_primes)
print('primes has now become:', primes)
primes.append(middle_aged_primes)
print('primes has finally become:', primes)
~~~
{: .python}
~~~
primes is currently: [2, 3, 5, 7, 9]
primes has now become: [2, 3, 5, 7, 9, 11, 13, 17, 19]
primes has finally become: [2, 3, 5, 7, 9, 11, 13, 17, 19, [37, 41, 43, 47]]
~~~
{: .output}

Note that while `extend` maintains the "flat" structure of the list, appending a list to a list makes the result two-dimensional.

## Use `del` to remove items from a list entirely.

*   `del list_name[index]` removes an item from a list and shortens the list.
*   Not a function or a method, but a statement in the language.

~~~
print('primes before removing last item:', primes)
del primes[4]
print('primes after removing last item:', primes)
~~~
{: .python}
~~~
primes before removing last item: [2, 3, 5, 7, 9]
primes after removing last item: [2, 3, 5, 7]
~~~
{: .output}

## The empty list contains no values

*   Use `[]` on its own to represent a list that doesn't contain any values.
    *   "The zero of lists."
*   Helpful as a starting point for collecting values
    (which we will see in future chapters).

## Lists may contain values of different types

*   A single list may contain numbers, strings, and anything else.

~~~
goals = [1, 'Create lists.', 2, 'Extract items from lists.', 3, 'Modify lists.']
~~~
{: .python}

## Remember that character strings can be indexed like lists

*   Get single characters from a character string using indexes in square brackets.

~~~
element = 'carbon'
print('zeroth character:', element[0])
print('third character:', element[3])
~~~
{: .python}
~~~
zeroth character: c
third character: b
~~~
{: .output}

## But unlike lists, character strings are immutable

*   Cannot change the characters in a string after it has been created.
    *   *Immutable*: can't be changed after creation.
    *   In contrast, lists are *mutable*: they can be modified in place.
*   Python considers the string to be a single value with parts,
    not a collection of values.

~~~
element[0] = 'C'
~~~
{: .python}
~~~
TypeError: 'str' object does not support item assignment
~~~
{: .error}

*   Lists and character strings are both *collections*.

## Indexing beyond the end of the collection is an error

*   Python reports an `IndexError` if we attempt to access a value that doesn't exist.
    *   This is a kind of runtime error.
    *   Cannot be detected as the code is parsed
        because the index might be calculated based on data.

~~~
print('99th element of element is:', element[99])
~~~
{: .python}
~~~
IndexError: string index out of range
~~~
{: .output}

## Slicing python lists

Let's create a normal, everyday list. Nothing crazy, just a normal list with letters from a to h. Now let's say that we really want the elements b, c, and d returned in a new list. How do we do that?

~~~
letters = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h']
letters[1:4] 
~~~
{: .python}
~~~
['b', 'c', 'd']
~~~
{: .output}

*   Remeber that `b` is the second element of this list because of the 0-based indexing

## Slice indices have useful defaults

*   An omitted second index defaults to the size of the list being sliced.
*   An omitted first index defaults to zero.

~~~
letters[4:] # list elements from position 4 (included) onwards ... start counting from 0!
~~~
{: .python}
~~~
['e', 'f', 'g', 'h']
~~~
{: .output}

~~~
letters[:5] # list elements from the beginning to position 5 (excluded)
~~~
{: .python}
~~~
['a', 'b', 'c', 'd', 'e']
~~~
{: .output}

*   Lists can also be sliced in reverse order. 

~~~
print('last item in the list:', letters[-1])
print('last two items in the list:', letters[-2:])   
print('everything except the last two items:', letters[:-2])   
~~~
{: .python}
~~~
last item in the list: h
last two items in the list: ['g', 'h']
everything except the last two items: ['a', 'b', 'c', 'd', 'e', 'f']
~~~
{: .output}

## Slice bounds

One way to remember how slices work is to think of the indices as pointing *between* elements, with the left edge of the  first character numbered 0. Then the right edge of the last character of a string of n characters has index n, for example:

~~~
 +---+---+---+---+---+---+---+---+
 | a | b | c | d | e | f | g | h |
 +---+---+---+---+---+---+---+---+
 0   1   2   3   4   5   6   7   8
-8  -7  -6  -5  -4  -3  -2  -1
~~~~

> ## Challenge question
> 
> How would you extract the letter `f` from `letters` using reverse indexing?
> 
> ~~~
> mylist[____:____]
> ~~~
> {: .python}
>
> > ## Solution
> > ~~~
> > letters[-3:-2]
> > ~~~
> > {: .python}
> {: .solution}
{: .challenge}

> ## Fill in the Blanks
>
> Fill in the blanks using methods of lists and slicing so that the program below produces the output shown. 
> *Tip: start with an empty list*
>
> ~~~
> values = ____
> values.____(1)
> values.____(3)
> values.____(5)
> print('first time:', values)
> values = values[____]
> print('second time:', values)
> ~~~
> {: .python}
>
> ~~~
> first time: [1, 3, 5]
> second time: [3, 5]
> ~~~
> {: .output}
>
> > ## Solution
> > ~~~
> > values = []
> > values.append(1)
> > values.append(3)
> > values.append(5)
> > print('first time:', values)
> > values = values[1:]
> > print('second time:', values)
> > ~~~
> > {: .python}
> {: .solution}
{: .challenge}

> ## How large is a slice?
>
> If 'low' and 'high' are both non-negative integers,
> how long is the list `values[low:high]`?
>
> > ## Solution
> > The list `values[low:high]` has `high - low` elements.  For example,
> > `values[1:4]` has the 3 elements `values[1]`, `values[2]`, and `values[3]`.
> > Note that the expression will only work if `high` is less than the total
> > length of the list `values`.
> {: .solution}
{: .challenge}

> ## From strings to lists and back
>
> Given this:
>
> ~~~
> print('string to list:', list('tin'))
> print('list to string:', ''.join(['g', 'o', 'l', 'd']))
> ~~~
> {: .python}
> ~~~
> ['t', 'i', 'n']
> 'gold'
> ~~~
> {: .output}
>
> 1.  Explain in simple terms what `list('some string')` does.
> 2.  What does `'-'.join(['x', 'y'])` generate?
>
> > ## Solution
> > 1. `list('some string')` "splits" a string into a list of its characters.
> > 2. `x-y`
> {: .solution}
{: .challenge}

> ## Stepping through a list
>
> What does the following program print?
>
> ~~~
> elements = ['H', 'He', 'Li', 'B', 'O', 'F', 'Mg', 'P', 'Mn', 'Cu']
> print(elements[::2])
> print(elements[::-1])
> ~~~
> {: .python}
>
> 1.  If we write a slice as `low:high:stride`, what does `stride` do?
> 2.  What expression would select all of the even-numbered items from a collection?
>
> > ## Solution
> > The program prints
> > ~~~
> > ['H', 'Li', 'O', 'Mg', 'Mn']
> > ['Cu', 'Mn', 'P', 'Mg', 'F', 'O', 'B', 'Li', 'He', 'H']
> > ~~~
> > {: .python}
> > 1. `stride` is the step size of the slice
> > 2. The slice `1::2` selects all even-numbered items from a collection: it starts
> >    with element `1` (which is the second element, since indexing starts at `0`),
> >    goes on until the end (since no `end` is given), and uses a step size of `2`
> >    (i.e., selects every second element).
> {: .solution}
{: .challenge}

## Using functions and methods on lists and strings

> ## Sort and sorted
>
> What do these two programs print?
> In simple terms, explain the difference between `sorted(letters)` and `letters.sort()`.
>
> ~~~
> # Program A
> letters = list('gold')
> result = sorted(letters)
> print('letters is', letters, 'and result is', result)
> ~~~
> {: .python}
>
> ~~~
> # Program B
> letters = list('gold')
> result = letters.sort()
> print('letters is', letters, 'and result is', result)
> ~~~
> {: .python}
>
> > ## Solution
> > Program A prints
> > ~~~
> > letters is ['g', 'o', 'l', 'd'] and result is ['d', 'g', 'l', 'o']
> > ~~~
> > {: .python}
> > Program B prints
> > ~~~
> > letters is ['d', 'g', 'l', 'o'] and result is None
> > ~~~
> > {: .python}
> > `sorted(letters)` returns a sorted copy of the list `letters` (the original
> > list `letters` remains unchanged), while `letters.sort()` sorts the list
> > `letters` in-place and does not return anything.
> {: .solution}
{: .challenge}

> ## Assigning lists to variables 
>
> What do these two programs print?
> In simple terms, explain the difference between `new = old` and `new = old[:]`.
>
> ~~~
> # Program A
> old = list('gold')
> new = old      # simple assignment
> new[0] = 'D'
> print('new is', new, 'and old is', old)
> ~~~
> {: .python}
>
> ~~~
> # Program B
> old = list('gold')
> new = old[:]   # assigning a slice
> new[0] = 'D'
> print('new is', new, 'and old is', old)
> ~~~
> {: .python}
>
> > ## Solution
> > Program A prints
> > ~~~
> > new is ['D', 'o', 'l', 'd'] and old is ['D', 'o', 'l', 'd']
> > ~~~
> > Program B prints
> > ~~~
> > new is ['D', 'o', 'l', 'd'] and old is ['g', 'o', 'l', 'd']
> > ~~~
> > {: .python}
> > `new = old` makes `new` a reference to the list `old`; `new` and `old` point
> > towards the same object.
> > 
> > `new = old[:]` however creates a new list object `new` containing all elements
> > from the list `old`; `new` and `old` are different objects.
> {: .solution}
{: .challenge}

## Basic operations with lists

Similar to strings, lists respond to the + and * operators. These operators also mean concatenation and repetition, respectively, except that the result is a new list, not a string.

> What do the following commands print?
>
> ~~~
> concatenate = [1, 2, 3] + [4, 5, 6]
> print('concatenate is:', concatenate)
> repetition = ['Hi!'] * 4
> print('repetition is:', repetition)
> ~~~
> {: .python}
>
> > ## Solution
> > The program prints
> > ~~~
> > concatenate is: [1, 2, 3, 4, 5, 6]
> > repetition is: ['Hi!', 'Hi!', 'Hi!', 'Hi!']
> > ~~~
> > {: .python}
> {: .solution}
{: .challenge}

## Another type of collection in Python: Tuples 

Similar to lists, tuples are also a collection of python objects or elements. The main difference between tuples and lists is that tuples are immutable. Also, while lists use square brackets, tuples use parentheses `()`. 





{% include links.md %}

