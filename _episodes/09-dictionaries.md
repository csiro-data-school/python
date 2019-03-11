---
title: "Dictionaries"
teaching: 15
exercises: 15
questions:
- "What is a dictionary?"
objectives:
- "Create dictionaries."
- "Add and retrieve values from a dictionary, and test for membership."
- "Iterate over a dictionary."
keypoints:
- "A dictionary is a data structure similar to a list, but that uses keys instead of indexes."
- "Dictionaries are created with `{}`, instead of `[]` for lists, or `()` for tuples."
- "A dictionary `key` can be a string, a number, or any hashable object."
- "To retrieve a value for a specific key we use the method `.get`."
- "Check if a key exists in a given dictionary by using the `in` operator."
- "We can iterate over a dictionary using a `for loop` to get both `keys` and `keys:values`."
- "A set is an unordered collection of items. Every element is unique and immutable."
- "Sets can be used to perform mathematical set operations like union, intersection, symmetric difference."

---
## What is a dictionary?

A dictionary is a data structure similar to a list, but that uses keys instead of indexes. It is the Python implementation of an associative container, or key-value store.

Each value in the dictionary is looked up using a key and new entries can be added by assigning to a non-existent key.

### Creating dictionaries

Dictionaries are created with `{}`, instead of `[]` for lists, or `()` for tuples.

For example, a phonebook can be created with:

~~~
phonebook = {}
phonebook["Carolina"] = 55512341
phonebook["Rhys"] = 55512342
phonebook["Christian"] = 55512343
phonebook
~~~
{: .python}
~~~
{'Carolina': 55512341, 'Rhys': 55512342, 'Christian': 55512343}
~~~
{: .output}

Alternatively, the following (key : value) shorthand can be used to initialise a dictionary:

~~~
phonebook = {
    "Carolina" : 55512341,
    "Rhys" : 55512342,
    "Christian" : 55512343
}
phonebook
~~~
{: .python}
~~~
{'Carolina': 55512341, 'Rhys': 55512342, 'Christian': 55512343}
~~~
{: .output}

A **key** can be a string, a number, or any hashable object (which roughly means no lists or other mutable containers).

You can even mix key types in a single dictionary although it tends to be confusing (you often wish to sort on the keys later!):

~~~
phrasebook = {
    1 : "Is 1 a page number?",
    "My tank is full of smolts" : "Vamos a la playa!",
    2 : "Does 2 come before or after 'my tank'?",
    (2, '9-12') : "sacred relic"
}
phrasebook
~~~
{: .python}
~~~
{1: 'Is 1 a page number?',
 'My tank is full of smolts': 'Vamos a la playa!',
 2: "Does 2 come before or after 'my tank'?",
 (2, '9-12'): 'sacred relic'}
~~~
{: .output}

### Adding and modifying values in a dictionary 

You can assign to an individual dictionary entry to add it or modify it using the following syntax: 
`mydict[key] = "value"`

> ## Adding and changing entries in the phonebook 
> 
> Add your phone number to the following phonebook, and then change the entry for "Christian". 
> ~~~
> phonebook = {
>    "Carolina" : 55512341,
>    "Rhys" : 55512342,
>    "Christian" : 55512343
> }
> ~~~
> {: .python}
>
> > ## Solution
> > ~~~
> > phonebook['My_number'] = 55567676
> > phonebook['Christian'] = 55534343
> > phonebook
> > ~~~
> > {: .python}
> > ~~~
> > {'Carolina': 55512341,
> > 'Rhys': 55512342,
> > 'Christian': 55534343,
> > 'My_number': 55567676}
> > ~~~
> > {: .output}
> > We can check the length of our updated dictionary using the function `len`. 
> {: .solution}
{: .challenge}

### Retrieving and removing values from a dictionary

Lets create a English-Spanish dictionary. 

~~~
ESdict = {
    "Cat" : "Gato",
    "Dog" : "Perro",
    "Apple" : "Manzana",
    "Table" : "Mesa"
}
ESdict
~~~
{: .python}
~~~
{'Cat': 'Gato', 'Dog': 'Perro', 'Apple': 'Manzana', 'Table': 'Mesa'}
~~~
{: .output}

To **retrieve** a value for a specific key we use the method `.get`

~~~
print(ESdict.get('Cat'))
print(ESdict.get('Dog'))
~~~
{: .python}
~~~
Gato
Perro
~~~
{: .output}

To **remove** a specific element from a dictionary, you can use the statement `del` and index the element using its `key`.

> ## Remove a word from this dictionary
>
> Remove the word 'Cat' from the English-Spanish dictionary.
> ~~~
> ESdict = {
>    "Cat" : "Gato",
>    "Dog" : "Perro",
>    "Apple" : "Manzana",
>    "Table" : "Mesa" }
> ~~~
> {: .python}
>
> > ## Solution
> > ~~~
> > del ESdict['Cat']
> > ~~~
> > {: .python}
> > Alternatively, if we want to return the value of the entry being removed we can use the method `.pop`, you can try this by 
> > typing `mydict.pop("Dog")`. 
> {: .solution}
{: .challenge}

### Testing membership (is my item in the dictionary or not?)

Check if a key exists in a given dictionary by using the `in` operator like this:

~~~
motifs = {
    "m1" : "AGTTGC",
    "m2" : "TTTGCG",
    "m3" : "GTGTAA",
    "m4" : "AAATGC"}

print('m1' in motifs)
print('m3' in motifs)
print('m5' in motifs)
~~~
{: .python}
~~~
True
True
False
~~~
{: .output}


### Iterating over a dictionary

We can iterate over a dictionary using a `for loop` to get both `keys` and `keys:values`. Going back to our `motifs` dictionary, iterate over the dictionary to get all the keys. 

~~~
for key in motifs:
    print(key)
~~~
{: .python}
~~~
m1
m2
m3
m4
~~~
{: .output}

> ## How to iterate over a dictionary to get all key,value pairs
>
> Construct a for loop to extract both keys and values from the `motifs` dictionary. 
> *Hint: you will need to use a dictionary method*
> ~~~
> motifs = {
>    "m1" : "AGTTGC",
>    "m2" : "TTTGCG",
>    "m3" : "GTGTAA",
>    "m4" : "AAATGC"}
> ~~~
> {: .python}
>
> > ## Solution
> > ~~~
> > for item in motifs.items():
> >     print(items)
> > ~~~
> > {: .python}
> > ~~~
> > ('m1', 'AGTTGC')
> > ('m2', 'TTTGCG')
> > ('m3', 'GTGTAA')
> > ('m4', 'AAATGC')
> > ~~~
> > {: .output}
> > Alternatively, if we want to return the keys and values as separate items we can use:
> > ~~~
> > for key, value in motifs.items():
> >     print(key, ":", value)
> > ~~~
> > {: .python}
> > ~~~
> > m1 : AGTTGC
> > m2 : TTTGCG
> > m3 : GTGTAA
> > m4 : AAATGC
> > ~~~
> > {: .output}
> {: .solution}
{: .challenge}

*Note: As of Python 3.7, iterating over items in a dictionary is now done in the order in which they were inserted as a "feature" of the language.*

## Sets

### What is a set?

*   A set is an unordered collection of items. Every element is unique (no duplicates) and must be immutable (which cannot be changed).
*   However, the set itself is mutable. We can add or remove items from it.
*   Sets can be used to perform mathematical set operations like union, intersection, symmetric difference etc.

### How to create a set?

*   A set is created by placing all the items (elements) inside curly braces {}, separated by comma or by using the built-in function set().
*   It can have any number of items and they may be of different types (integer, float, tuple, string etc.).

~~~
# set of integers
my_set = {1, 2, 3}
print(my_set)

# set of mixed datatypes
my_set = {1.0, "Hello", (1, 2, 3)}
print(my_set)

# set do not have duplicates
my_set = {1, 2, 3, 4, 3, 2}
print(my_set)
~~~
{: .python}
~~~
{1, 2, 3}
{1.0, 'Hello', (1, 2, 3)}
{1, 2, 3, 4}
~~~
{: .output}

*   A `set` cannot have a mutable element, like a `list`. 

~~~
# here [3, 4] is a mutable list
# the following command will cause an error:
# my_set = {1, 2, [3, 4]}
~~~
{: .python}
~~~
TypeError: unhashable type: 'list'
~~~
{: .error}

### How to change a set in Python?

*   Sets are mutable. But since they are unordered, we cannot access or change an element of set using indexing or slicing. 
Set does not support it.

*   We can add single element using the `add()` method and multiple elements using the `update()` method. The `update()` method can take tuples, lists, strings or other sets as its argument. In all cases, duplicates are avoided.

~~~
# create a set
my_set = {1,3}
print(my_set)

# add an element
my_set.add(2)
print(my_set)

# add multiple elements
my_set.update([2,3,4])
print(my_set)

# add list and set
my_set.update([4,5,1,1], {1,6,7,8}) 
print(my_set)
~~~
{: .python}
~~~
{1, 3}
{1, 2, 3}
{1, 2, 3, 4}
{1, 2, 3, 4, 5, 6, 7, 8}
~~~
{: .output}

### Python set operations

Sets can be used to carry out mathematical set operations like union, intersection, difference and symmetric difference. We can do this with operators or methods:

*   **Union** is performed using `|` operator, or the method `union()`.
*   **Intersection** is performed using `&` operator,or using the method `intersection()`.
*   **Set Difference** of A and B (A - B) is a set of elements that are only in A but not in B. Similarly, B - A is a set of element in B but not in A. Difference is performed using `-` operator, or the method `difference()`.
*   **Symmetric Difference** of A and B is a set of elements in both A and B except those that are common in both. Symmetric difference is performed using `^` operator, or the method `symmetric_difference()`.

> ## Python set operation exercises
> 
> Solve the following operations:
> ~~~
> print(A - B)
> print(B - A)
> print(A.intersection(B))
> print(A ^ B)
> print(A.union(B) & B.intersection(A))
> print(B.intersection(A) - A.union(B))
> ~~~
> {: .python}
> > ## Solution
> > ~~~
> > {1, 2, 3, 4, 11}
> > {7, 8, 9, 10, 15}
> > {13, 5, 6, 14}
> > {1, 2, 3, 4, 7, 8, 9, 10, 11, 15}
> > {5, 13, 6, 14}
> > set()
> > ~~~
> > {: .output}
> > Note that `set()` represents an empty set. 
> {: .solution}
{: .challenge}


{% include links.md %}
