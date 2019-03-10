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

## Using dictionaries

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

To **remove** a specific element from a dictionary, you can use function `del` and index the element using its `key`.

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

