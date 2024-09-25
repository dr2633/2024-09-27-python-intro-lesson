---
title: Lists
teaching: 25
exercises: 10
---

::::::::::::::::::::::::::::::::::::::: objectives

- Create collections to work with in Python using lists.
- Write Python code to index, slice, and modify lists through assignment and method calls.

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: questions

- How can I store multiple items in a Python variable?

::::::::::::::::::::::::::::::::::::::::::::::::::

## A list stores many values in a single structure.
The most popular kind of data collection in Python is the list. Lists have two primary important characteristics:

1. They are mutable, i.e., they can be changed after they are created.
2. They are heterogeneous, i.e., they can store values of many different types.

To create a new list, you can just put some values in square brackets with commas in between. Let's create a short list of some amino acids.

```python
amino_acids = ['alanine', 'leucine', 'cysteine', 'isoleucine']
amino_acids
```

```output
['alanine', 'leucine', 'cysteine', 'isoleucine']
```

We can use `len()` to find out how many values are in a list.

```python
len(amino_acids)
```

```output
4
```

## Use an item's index to fetch it from a list.

In the same way we used index numbers for strings, we can reference elements and slices in a list.

```python
print(f'First item: {amino_acids[0]}')
print(f'The first three items: {amino_acids[0:3]}')
```

```output
First item: alanine
The first three items: ['alanine', 'leucine', 'cysteine']
```

## Reassign list values with their index.

Use an index value along with your list variable to replace a value from the list.

```python
print(f'List was: {metadata}')
metadata[0] = 'methionine'
print(f'List is now: {metadata}')
```

```output
List was: ['alanine', 'leucine', 'cysteine', 'isoleucine']
List is now: ['methionine', 'leucine', 'cysteine', 'isoleucine']
```


### Character strings are immutable.

Unlike lists, we cannot change the characters in a string using its index value. In other words strings are *immutable* (cannot be changed in-place after creation), while lists are *mutable*: they can be modified in place. Python considers the string to be a single value with parts, not a collection of values.

```python
ile = 'Osoleucine' # oops, typo!
ile[0] = 'I'
```

```error
TypeError: 'str' object does not support item assignment
```

## Appending items to a list lengthens it.

Use `list_name.append` to add items to the end of a list. In Python, we would call `.append()` a *method* of the list object. You can use the syntax of `object.method()` to call methods.

```python
print(f'list was:{amino_acids}')
amino_acids.append('glutamine')
print(f'list is now: {amino_acids}')
```

```output
list was: ['methionine', 'leucine', 'cysteine', 'isoleucine']
list is now: ['methionine', 'leucine', 'cysteine', 'isoleucine', 'glutamine']
```


## Lists may contain values of different types.

A single list may contain numbers, strings, and anything else (including other lists!). If you're dealing with a list within a list you can continue to use the square bracket notation to reference specific items. 

```python
mixed_list = ['hello world', 3.2, [10, 20, 30]]
f'First item in sublist: {mixed_list[2][0]}'
```

```output
First item in sublist: 10
```

## Lists can contain lists.

Lists which contain other lists can be very useful. Imagine you poll your friends on their favorite pizza toppings.

```python
pizza_toppings = ['pepperoni', 'mushroom', 'pineapple']
print(pizza_toppings)
```

```output
['pepperoni', 'mushroom', 'pineapple']
```

One of your friends likes Buffalo chicken pizza. Buffalo chicken is really three toppings combined: chicken, Buffalo sauce, and blue cheese. Here is how we can represent that in the list.

```python
buffalo_chicken = ['chicken', 'buffalo sauce', 'blue cheese']
pizza_toppings.append(buffalo_chicken)
print(pizza_toppings)
```

```output
['pepperoni', 'mushroom', 'pineapple', ['chicken', 'buffalo sauce', 'blue cheese']]
```
We can access the items in the sublist as shown above:

```python
print(pizza_toppings[3][2])
```

```output
blue cheese
```

## Use `del` to remove items from a list entirely.

`del list_name[index]` removes an item from a list and shortens the list. Unlike `.append()`, `del` is not a method, but a "statement" in Python. In the example below, `del` performs an "in-place" operation on a list of prime numbers. This means that the `primes` variable will be reassigned when you use the `del` statement, without needing to use an assignment operator (e.g., `primes = ...`) .

```python
primes = [2, 3, 5, 7, 11]
print(f'primes before: {primes}')
del primes[4]
print(f'primes after: {primes}')
```

```output
primes before: [2, 3, 5, 7, 11]
primes after: [2, 3, 5, 7]
```


:::::::::::::::::::::::::::::::::::::::  challenge

## Lists: Length and Indexing
1. Create a list named `colors` containing the strings 'red', 'blue', and 'green'. 
2. Print the length of the list.
3. Print the first color using indexing.

:::::::::::::::  solution

## Solution
```python
colors = ['red', 'blue', 'green']
print(len(colors))
print(colors[0])
```

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::  challenge

## List slicing
1. Create a list of numbers defined as [1, 2, 3, 4, 5, 6].
2. Print the first three items in the list using slicing.
3. Print the last three items using slicing.

:::::::::::::::  solution

## Solution
```python
numbers = [1, 2, 3, 4, 5, 6]
print(numbers[0:3])
print(numbers[3:6])
```
```output
[1, 2, 3]
[4, 5, 6]
```

You can also leave the first and last elements in a slice blank to refer to the first and last elements in a list:

```python
print(numbers[:3])
print(numbers[3:])
```
```output
[1, 2, 3]
[4, 5, 6]
```

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::::: spoiler

## Bonus Challenge: More Pizza

Another person has responded to your pizza poll. Their favorite pizza is Veggie (green pepper, onion, mushroom, broccoli, and olive).

###
1. Create a variable that represents the toppings making up a veggie pizza.
2. Add the veggie pizza to your pizza list.
3. Print the updated pizza list.
4. Use list indexing to print the *second* item that goes on a veggie pizza.

Here is the current pizza list to get you started: 

```python
pizza_toppings = ['pepperoni', 'mushroom', 'pineapple', ['chicken', 'buffalo sauce', 'blue cheese']]
print(pizza_toppings)
```

```output
['pepperoni', 'mushroom', 'pineapple', ['chicken', 'buffalo sauce', 'blue cheese']]
```

<!-- vertical spacer -->

:::::::::::::::  solution

## Solution

```python
veggie = ['green pepper', 'onion', 'mushroom', 'broccoli', 'olive']
pizza_toppings.append(veggie)
print(pizza_toppings)
print(pizza_toppings[4][1])
```

```output
['pepperoni', 'mushroom', 'pineapple', ['chicken', 'buffalo sauce', 'blue cheese'], ['green pepper', 'onion', 'mushroom', 'broccoli', 'olive']]
onion
```

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::::: spoiler

## Bonus Challenge: Fill in the Blanks

Fill in the blanks so that the program below produces the output shown. In the first line we create a blank list by assigning `values = []`.

```python
values = []
values.____(1)
values.____(3)
values.____(5)
print(f'first time: {values})
values = values[____]
print(f'second time: {values})
```

```output
first time: [1, 3, 5]
second time: [3, 5]
```

<!-- vertical spacer -->

:::::::::::::::  solution

## Solution

```python
values = []
values.append(1)
values.append(3)
values.append(5)
print(f'first time: {values})
values = values[1:3]
print(f'second time: {values})
```

```output
first time [1, 3, 5]
second time [3, 5]
```

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::


:::::::::::::::::::::::::::::::::::::::::: spoiler

## Bonus Challenge: Working With the End

Run the following code on your own and answer the following questions.

```python
resources = ['books','DVDs','maps','databases']
print(resources[-1])
```

1. How does Python interpret a negative index value?
2. If `resources` is a list, what does `del resources[-1]` do?

<!-- vertical spacer -->

:::::::::::::::  solution

## Solution

```output
databases
```

1. A negative index begins at the final element.
2. It removes the final element of the list.


:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::


:::::::::::::::::::::::::::::::::::::::: keypoints

- A list stores many values in a single structure.
- Use an item's index to fetch it from a list.
- Lists' values can be replaced by assigning to them.
- Appending items to a list lengthens it.
- Use `del` to remove items from a list entirely.
- Lists may contain values of different types.
- Character strings can be indexed like lists.
- Character strings are immutable.
- Indexing beyond the end of the collection is an error.

::::::::::::::::::::::::::::::::::::::::::::::::::


