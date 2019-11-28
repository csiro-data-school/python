--
title: "Modules"
teaching: 30
exercises: 20
questions:
- "How do I use code defined in other files or libraries?"
- "What does the `import` statement do?"
- "What are the effects of the common import variations?"
objectives:
- "Learn what a module is."
- "Learn how to import symbols from other files and modules."
- "Understand the differences between the different forms of import statements."
- "Be able to import modules into your code."
keypoints:
- "Modules are simply Python files."
- "To use code from a module, it has to be imported."
- "The `import` command is used to import code from a module."
- "There are different ways to import from a module. Select the appropriate
  method based on the required effect."

---

## Modules and Packages

[Modules][python-modules] in Python are simply Python files with the .py
extension.

To use the functionality of a module, it has to be imported into your code. To
import a module, we use the `import` command.

The [full list of built-in modules][python-standard-modules] can be found in the
Python documentation.

For example:
~~~
# import the library
import os

# use it
os.listdir()
~~~
{: .language-python}

> ## The `math` module
>
> In the python interpreter, import the `math` module and print the value of
> `math.pi`.
>
> What happens if you don't import the math module first?
> > ## Solution
> > ~~~
> > $ python3
> > Python 3.6.7 (default, Oct 22 2018, 11:32:17)
> > [GCC 8.2.0] on linux
> > Type "help", "copyright", "credits" or "license" for more information.
> > >> import math
> > >> print(math.pi)
> > 3.141592653589793
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}

## `import` has many forms

When reading Python code, you may have seen many different types of import
statements, such as:
~~~
import math
import math as m
from math import pi
from math import *
~~~
{: .language-python}

Let's look at each one in turn.

### `import math`

The first, `import math` imports everything from the `math` module. To access
anything in `math`, you need to prefix with `math.`. This prevents conflicts
with other code, including your own.

> ## Two pi
>
> Either in a file or Python interpreter, try running the following code:
> ~~~
> pi = 3.14
> import math
> print(pi)
> print(math.pi)
> ~~~
> {: .language-python}
> Do you see that the values of `pi` and `math.pi` are different? And how using
> the module name makes it easy to know which is which?
{: .challenge}

### `import math as m`

The second form, `import math as m` is mostly the same, it just changes the name
that you need to use to refer to the imported objects. In this case, `m.`
instead of `math.`. When you start using packages from the SciPy ecosystem, you
will see this type of import a lot. Most of the common packages have
a conventional abbreviation. This keeps code concise but retains readability.
For example, rather than:
~~~
import numpy
a = numpy.array([1,2,3])
print(a)
~~~
{: .language-python}

It is more common to write:
~~~
import numpy as np
a = np.array([1,2,3])
print(a)
~~~
{: .language-python}

`np` is the conventional abbreviation (or alias) for numpy.

> ## Three pi
>
> Either in a file or Python interpreter, try running the following code:
>
> **Make sure to restart the Jupyter Notebook kernel, or this example won't work.**
> ~~~
> pi = 3.14
> import math as m
> print(pi)
> print(m.pi)
> print(math.pi)
> ~~~
> {: .language-python}
> > ## Solution
> > ~~~
> > $ python3
> > Python 3.6.7 (default, Oct 22 2018, 11:32:17)
> > [GCC 8.2.0] on linux
> > Type "help", "copyright", "credits" or "license" for more information.
> > >> pi = 3.14
> > >> import math as m
> > >> print(pi)
> > 3.14
> > >> print(m.pi)
> > 3.141592653589793
> > >> print(math.pi)
> > Traceback (most recent call last):
> >   File "<stdin>", line 1, in <module>
> > NameError: name 'math' is not defined
> > ~~~
> > {: .source}
> > The last error is because the `import math as m` changed the alias used to
> > refer to the imported math module.
> {: .solution}
{: .challenge}

### `from math import pi`

This one looks a little different. It starts with `from` rather than `import`,
but it is still an import statement. `from math import pi` is still importing
from the math module, but rather than importing everything and then needing to
access those symbols with the `math.` prefix, it specifically imports just the
definition of `pi`. There is another critical difference. See if you can work
out what it is?

> ## The differences between `import math` and `from math import pi`
>
> **Make sure to restart the Jupyter Notebook kernel, or this example won't work.**
>
> Either in a file or Python interpreter, try running the following code:
> ~~~
> from math import pi
> print(pi)
> print(math.pi)
> ~~~
> {: .language-python}
> > ## Solution
> > When importing specific symbols, nothing else from the module will be
> > available to your code. In this example, we have imported `pi` but nothing
> > else. Not even the `math.` prefix is defined.
> >
> > The other critical difference is that the imported symbol no longer requires
> > a prefix. You need to take care that it doesn't conflict with your own
> > variables or functions.
> {: .solution}
{: .challenge}

### `from math import *`


> ## Exploring `from math import *`
>
> **Make sure to restart the Jupyter Notebook kernel, or this example won't work.**
>
> The [built-in `dir()` function][python-dir] when called without arguments
> lists the names (variables, functions etc) defined in the local scope. This
> exercise uses `dir()` to explore the relative effect of different import
> statements.
>
> In a new interactive Python session, enter the following commands one at
> a time in the order shown. The output from `dir()` will show the defined names
> at each point.
>
> What items get added to the end of the `dir()` results at each stage?
> ~~~
> dir()
> ~~~
> {: .language-python}
>
> This first call to `dir()` shows a few standard items that should be ignored.
> Remember, we are looking for the changes once we start importing from `math`.
>
> ~~~
> import math
> dir()
> ~~~
> {: .language-python}
>
> ~~~
> from math import pi
> dir()
> ~~~
> {: .language-python}
>
> ~~~
> from math import *
> dir()
> ~~~
> {: .language-python}
> > ## Solution
> > - `import math`: The only new addition to local symbols is `math`.
> >     - This is the namespace object used to access the contents of the math
> >       module.
> > - `from math import pi`: Adds just one name - `pi`.
> > - `from math import *`: Adds everything from `math`. Imagine the effect if
> >   you did this for a lot of modules?
> {: .solution}
{: .challenge}

The code `from math import *` looks very similar to `from math import pi`, but
the effect on your code is huge. The `*` is a wildcard that matches everything
in the math module. The effect is to import everything **without** the `math.`
prefix. While this can be very convenient during interactive coding sessions and
in small programs, great care must be taken to avoid conflicts. If two modules
that you are using both define a function called `count_words`, then the version
you end up with depends on which was imported last. Things might work, but when
they fail errors like this can be very hard to find.

For these reasons, it it generally recommended to avoid this type of
import. However, it can still be convenient so long as you are aware of the
risks.

{% include links.md %}

[python-documentation]: https://docs.python.org/3/
[python-dir]: https://docs.python.org/3/library/functions.html#dir
[python-modules]: https://docs.python.org/3/tutorial/modules.html
[python-standard-modules]: https://docs.python.org/3/tutorial/modules.html#standard-modules
