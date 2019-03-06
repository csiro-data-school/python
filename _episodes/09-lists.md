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

*   To get the first element of this list we use the index 0 because python is a 0-based indexing lamnguage. 
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
print('weights are now:', weights)
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



- What is a collection
- Zero based
- Lists
- Indexing
- basic operations
- Enumerate
- slicing
- strings
- tuples
- order preserving


{% include links.md %}

