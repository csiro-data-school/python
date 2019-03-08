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
phonebook["Chapman"] = 55512341
phonebook["Cleese"] = 55512342
phonebook["Gilliam"] = 55512343
print(phonebook)
~~~
{: .python}
~~~
{'Chapman': 55512341, 'Rhys': 55512342, 'Gilliam': 55512343}
~~~
{: .output}

Alternatively, the following (key : value) shorthand can be used to initialise a dictionary:

~~~
phonebook = {
    "Chapman" : 55512341,
    "Rhys" : 55512342,
    "Gilliam" : 55512343
}
~~~
{: .python}





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

