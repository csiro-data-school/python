---
title: Exercises
---
# Types and expressions

> ## Arithmetic with Different Types
>
> Which of the following will print 2.0?
> Note: there may be more than one right answer.
>
> ~~~
> first = 1.0
> second = "1"
> third = "1.1"
> ~~~
> {: .python}
>
> 1. first + float(second)
> 2. float(second) + float(third)
> 3. first + int(third)
> 4. first + int(float(third))
> 5. int(first) + int(float(third))
> 6. 2.0 * second
>
{: .challenge}

> ## Think like a computer - division
> Computers cannot intuitively solve problems; the problem must be broken down by the computer into a series of logical steps.
> How would a computer solve the following problem? 
> 
> If `num_subjects` is the number of subjects taking part in a study,
> and `num_per_survey` is the number that can take part in a single survey,
> write a series of expressions that calculates the number of surveys needed
> to reach everyone once.
>
> Hint: you may need to use `//` and `%`
>
> Test your expressions with `num_subjects` = 600 and `num_per_survey` = 20.
>
> Now test again with `num_per_survey` = 42.
{: .challenge}

# Conditionals - if statements

> ## Close Enough
>
> Write some conditions that print `True` if the variable `a` is within 10% of the variable `b`
> and `False` otherwise.
> Compare your implementation with your partner's:
> do you get the same answer for all possible pairs of numbers?
> Try you code with:
> ~~~
> a = 5
> b = 5.1
> ~~~
> {: .language-python}
>
> Try it again with:
> ~~~
> a = 7
> b = 4
> ~~~
> {: .language-python}
> What other values of `a` and `b` would it be good to try your code with?
{: .challenge}

# For loops

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
> so that they print a list with the cumulative sum of data.
> The result should be `[1, 3, 5, 10]`.
>
> ~~~
> cumulative = cumulative.append(my_sum)
> for number in data:
> cumulative = []
> my_sum = my_sum + number
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
{: .challenge}

> ## Reverse a String
>
> Knowing that two strings can be concatenated using the `+` operator,
> write a loop that takes a string
> and produces a new string with the characters in reverse order,
> so `'Newton'` becomes `'notweN'`.
{: .challenge}

> ## Counting Vowels
>
> 1. Write a loop that counts the number of vowels in a character string.
> 2. Test it on a few individual words and full sentences.
> 3. Once you are done, compare your solution to your neighbor's.
>    Did you make the same decisions about how to handle the letter 'y'
>    (which some people think is a vowel, and some do not)?
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
{: .challenge}

