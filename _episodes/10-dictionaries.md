---
title: "Dictionaries"
teaching: 0
exercises: 0
questions:
- "What is a dictionary?"
objectives:
- "Create dictionaries."
- "Add and retrieve values from a dictionary, and test for membership."
- "Iterate over a dictionary."
keypoints:
- "First key point. Brief Answer to questions. (FIXME)"
---
## What is a dictionary?

A dictionary is a data structure similar to a list, but that uses keys instead of indexes. It is the Python implementation of an associative container, or key-value store.

Each value in the dictionary is looked up using a key and new entries can be added by assigning to a non-existent key.

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

A **key** can be a string, number, or any hashable object (which roughly means no lists or other mutable containers).

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

## Removing a dictionary value

To remove a specific element from a dictionary, you can use `del` and index the element using its `key`.

> ## Remove a word from this dictionary
>
> Remove the word 'Cat' from this English-Spanish dictionary.
> ~~~
> mydict = {
>    "Cat" : "Gato",
>    "Dog" : "Perro",
>    "Apple" : "Manzana",
>    "Computer" : "Computador" }
> ~~~
> {: .python}
>
> > ## Solution
> > ~~~
> > del mydict['Cat']
> > ~~~
> > {: .python}
> > Alternatively, if we want to return the value of the entry being removed we can use the method `.pop`, you can try this by 
> > typing `mydict.pop("Dog")`. 
> {: .solution}
{: .challenge}



* What is a dictionary?
    * Key-value stores
    * Differences to list.
      * When to choose a list or dictionary.
* Using dictionaries
  * creating
  * adding values
  * retrieving values
  * testing membership (is my item in the dictionary or not?)
  * Iterating keys and keys/values
    * Non-order preserving
  * Other operations
* Sets
  * What are they?
  * Creating
  * Using

{% include links.md %}

