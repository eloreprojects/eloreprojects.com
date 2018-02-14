---
title: "Why does 0! = x^0?"
layout: post
date: 2017-12-04 12:00
headerImage: false
star: false
category: Computation
author: arun
description: "Using base cases for mathematical intuition."
---

If you've ever taken a class in algebra or statistics, you would probably know from memory that $$0! = 1$$ and $$ x^0 = 1$$ (for any real number $$x$$). But why?

## 0! as a base case

The factorial 0! is weird.

We can illustrate $$0!$$ by determining the number of ways to arrange the elements of an empty set $$\{\}$$. Since there are no elements, there is only 1 possible set: $$\{\}$$. We usually use the factorial function when counting the number of permutations of a given set; so, it holds that $$0! = 1$$.

We formally define the factorial of an integer $$x$$ as $$x! = \prod\limits_{i=1}^x i$$. But if $$x = 0$$, where does the 1 come from? One way to think about why $$0! = 1$$ is through the concept of it being a base case for a recursive factorial function:

```python
def factorial(x):
  if x == 0:
    return 1
  else:
    return x * factorial (x - 1)
```

If the definition of factorial was $$x! = \prod\limits_{i=0}^x i$$, then the factorial of *any* number would be equal to 0. So, as notion we can assume that $$0! = 1$$ in order to delineate the final term of any given factorial such that it behaves accordingly.

## x^0 as a base case

The product $$x^0$$ is even weirder. 

We can't illustrate $$x^0$$ as easily as we could with $$0!$$. We're usually taught that a number $$x$$ raised to an exponent $$n$$ is simply $$x$$ multiplied by itself $$n$$ times. But how do we multiply something $$0$$ times? Isn't that just the absense of *any* quantity: 0? 

Again, it might easier to think of raising a number as an exponent as a recursive function:

```python
def exponent(x, n):
  if n == 0:
    return 1
  else:
    return x * exponent (x, n - 1)
```

Given that this function works, since we know $$x^2 = x * x$$ since $$n = 2$$, the exponentiation can be rewritten as $$x^2 = 1 * x * x$$. So, we can now think of exponentiation as $$1$$ multiplied by $$x$$ a total of $$n$$ times. 

Finally, the exponentiation of $$x^0 = 1$$ makes sense since 1 is being multiplied by $$x$$ a total of $$0$$ times - which is 1! (the exclamation point here is simultaneously a factorial and my excitement).

## Working backwards with factorials

Applying the recursive logic above, we can now just take an example to see **why** this works with factorials. This is easy to see since by definition, $$x! = \frac{(x + 1)!}{x}$$. Taking $$4$$ as an example:

$$ 4! = 4 * 3 * 2 * 1 = 24$$

$$ 3! = \frac{4!}{4} = \frac{24}{4} = 6$$

$$ 2! = \frac{3!}{3} = \frac{6}{3} = 2$$

$$ 1! = \frac{2!}{2} = \frac{2}{2} = 1$$

And finally,

$$ 0! = \frac{1!}{1} = \frac{1}{1} = 1 $$

Now, *that* deserves an exclamation point.

## Working backwards with exponents

Applying similar logic, we can do the same thing for the factorial function. Let's take my favourite number: 2. 

Working backwards, we can also say that $$2^3 = 2^{4 - 1}$$, or that $$2^3 = \frac{2^4}{2} = \frac{16}{2} = 8$$. Let's work with this pattern:

$$2^2 = \frac{2^3}{2} = \frac{8}{2} = 4$$

$$2^1 = \frac{2^2}{2} = \frac{8}{2} = 2$$

And for the final step,

$$2^0 = \frac{2^1}{2} = \frac{2}{2} = 1$$

(there's no exclamation point for me to make a pun about, but I find the exponent example *much* cooler because $$x^0$$ made no sense to me logically)

## Why does this matter?
Although this blog post may seem to be about number theory and algebra, the examples of factorial and exponents illustrate the importance of thinking about edge scenarios. Base cases and their respective functionalities are extremely useful in both computer science and mathematics thanks to the elegance of recursive functions.

Just don't go around throwing (!) all over your algebra! 

- - - -
