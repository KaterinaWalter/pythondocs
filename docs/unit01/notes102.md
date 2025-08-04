---
layout: notes
title: "📓1.2: Data Collections" 
parent: "1️⃣ Python Bootcamp"
nav_order: 2
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

## Data Collections

Python provides 4 **built-in data structures** that allow you to store _collections of data_ in a _single named variable_:

<html>
<dl>
  <dt>Lists</dt>
  <dd>Ordered, mutable sequences, declared with square brackets <code>[ ]</code>. Suitable for storing collections of items that can be changed.</dd>
  <dt>Tuples</dt>
  <dd>Ordered, immutable sequences, declared with parentheses <code>( )</code>. Useful for storing fixed collections of items that should not be modified.</dd>
  <dt>Sets</dt>
  <dd>Unordered collections of unique, immutable elements, declared with curly braces <code>{ }</code>. Ideal for storing distinct items and performing set operations.</dd>
  <dt>Dictionaries</dt>
  <dd>Unordered collections of key-value pairs, declared with curly braces <code>{ }</code>. Excellent for storing data with associated labels for quick retrieval.</dd>
</dl>
</html>

### Lists
Lists are one of the most powerful data types in Python. Generally, they're container objects used to **store related items together**.

#### `list` cheat sheet
{: .no_toc }

| type             	| `list`                                                                                	|
|------------------	|---------------------------------------------------------------------------------------	|
| use              	| Used for storing similar items, and in cases where items need to be added or removed. 	|
| creation         	| `[]` or `list()` for empty list, or `[1, 2, 3]` for a list with items.                            	|
| search methods   	| `my_list.index(item)` or `item in my_list`                                                                           	|
| search speed     	| Searching in an item in a large list is slow. Each item must be checked.                               	|
| common methods   	| `len(my_list)`, `append(item)` to add, `insert(index, item)` to insert in the middle, `pop()` to remove.         	|
| order preserved? 	| Yes. Items can be accessed by index.                                                  	|
| mutable?         	| Yes                                                                                   	|
| in-place sortable?        	| Yes. `my_list.sort()` will sort the list in-place. `my_list.sort(reverse=True)` will sort the list in-place in *descending* order. `my_list.reverse()` will *reverse the items* in `my_list` in-place.           	|


Let's create a few lists to see how they work.

An empty list can be created in two ways. The first, by calling the `list()` method. More commonly, it's created with two empty brackets `[]`. Don't forget to check the type of the list with the `type` built-in function.

```python
>>> list()
[]
>>> []
[]
>>> type(list())
<class 'list'>
>>> type([])
<class 'list'>
```

Let's create our list with a few items in it. Let's say we want to keep track of a list of names. We add items to our list, and separate them with commas `,`.

```python
>>> names = ["Nina", "Max", "Jane"]
```

We can check its length with the built-in `len()` method, like so:

```python
>>> len(names)
3
```

### Indexes and Indices
{: .no_toc }

**Lists retain the order** of the items in them. In the next section, you'll learn about some data structures that don't.

In order to *access* items in a list, we'll need to use an *index*. (Multiple indexes are sometimes also called indices). The index for the item you want to access is *an integer* put in *square brackets* after the list.

{:.highlight}
**Indexes start at** `0` in Python and most other programming languages.

<div class="task" markdown="block">

```python
>>> names = ["Nina", "Max", "Jane"]
>>> names[0]
>>> names[1]
>>> names[2]
```

</div>

#### Updating an item in a list
{: .no_toc }

To update a particular item in a `list` use square-bracket notion and assign a new value. `my_list[pos] = new_value`

<div class="task" markdown="block">

```python
>>> names = ["Nina", "Max", "Jane"]
>>> names[2] = "Floyd"
>>> names
```
</div>

{:.highlight}
If you try to access an index that is greater than or equal to (>=) the length of the list, you'll get an `IndexError`.

```python
>>> names = ["Nina", "Max", "Jane"]
>>> len(names)
3
>>> names[3]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: list index out of range
```

#### Formatting
{: .no_toc }

{:.highlight}
We can *optionally* add new lines after the commas. This helps with readability for more complex list items.

Notice that we can also *optionally* add a trailing comma after the last item. A trailing comma isn't required to create a valid list, but it does help minimize version control differences when working on a Python codebase with a team.

```python
>>> names = [
... "Nina",
... "Max",
... "Jane",
... ]
```


### Common Mistakes
{: .no_toc }

{:.highlight}
If you forget to include commas between your items, you'll get a `SyntaxError`.

```python
>>> numbers = [1, 2 3]
  File "<stdin>", line 1
    numbers = [1, 2 3]
                    ^
SyntaxError: invalid syntax
```

The REPL makes it difficult to forget the closing bracket, but if you forget it while writing code in a Python file, you'll see a `SyntaxError` with a different name. It'll say: `SyntaxError: unexpected EOF while parsing` or `SyntaxError: invalid syntax`.

For example:

```python
# Python file: program.py
names = ["Nina",
x = 5
```

Notice how the `SyntaxError` points to a completely valid line of Python code. In these cases, you also need to check the line of code **before** the line with the `SyntaxError`. There, we'll notice that we forgot the closing bracket of our `names` list.

```bash
# In a shell
(env) $ python program.py
  File "/Users/nina/Desktop/program.py", line 2
    x = 5
      ^
SyntaxError: invalid syntax
```

### Sorting
{: .no_toc }

Sorting sounds complicated, but in practice, it's just one method call away!

#### Sorting a Copy Of Your List
{: .no_toc }

If you'd like sort to return a brand new copy of your list, instead of modifying your original copy, you can use the built-in `sorted(my_list)` function on your list to return a *new* `list`, sorted in increasing (ascending) order. Or use `sorted(my_list, reverse=True)` to create a new `list` sorted backwards, in decreasing (or descending) order. This operation will **not modify** the underlying list.

Either of these operations will return a *new* list.

```python
>>> lottery_numbers = [1, 4, 32423, 2, 45, 11]
>>> sorted(lottery_numbers)
[1, 2, 4, 11, 45, 32423]
>>> lottery_numbers
[1, 4, 32423, 2, 45, 11]
>>> sorted(lottery_numbers, reverse=True)
[32423, 45, 11, 4, 2, 1]
>>> lottery_numbers
[1, 4, 32423, 2, 45, 11]
```

#### Sorting the list in-place
{: .no_toc }

You can call `my_list.sort()` on your list to sort it in increasing (ascending) order, or `my_list.sort(reverse=True)` on the list to sort it backwards, in decreasing (or descending) order. This operation will modify the underlying list, and *doesn't return a value*.

```python
>>> lottery_numbers = [1, 4, 32423, 2, 45, 11]
>>> lottery_numbers.sort()
>>> lottery_numbers
[1, 2, 4, 11, 45, 32423]

>>> lottery_numbers.sort(reverse=True)
>>> lottery_numbers
[32423, 45, 11, 4, 2, 1]

>>> words = ["Umbrella", "Fox", "Apple"]
>>> words.sort()
>>> words
['Apple', 'Fox', 'Umbrella']
```

#### Reverse the list in-place
{: .no_toc }

To reverse the items of a list in-place, call `my_list.reverse()` on it.

```python
>>> lottery_numbers = [1, 4, 32423, 2, 45, 11]
>>> lottery_numbers.reverse()
>>> lottery_numbers
[11, 45, 2, 32423, 4, 1]
```

### Finding Methods
{: .no_toc }

Remember, if you ever forget which methods are available on `list`, just call `dir` on it. Ignore the methods that start with underscores. If you need help remembering what a method does, you can call `help()` on it. For example, for append, call `help(list.append)`.

#### Adding, Removing, Changing, and Finding Items in `list`s cheat sheet
{: .no_toc }


| action                                           	| method                                	| returns           	| possible errors                            	|
|--------------------------------------------------	|---------------------------------------	|-------------------	|--------------------------------------------	|
| check length                                     	| `len(my_list)`                        	| `int`             	|                                            	|
| **add:** to the end                              	| `my_list.append(item)`                	| -                 	|                                            	|
| **insert:** at position                          	| `my_list.insert(pos, item)`           	| -                 	|                                            	|
| **update:** at position                          	| `my_list[pos] = item`          	| -        -         	| `IndexError` if `pos` is >= `len(my_list)`                                          	|
| **extend:** add items from another list          	| `my_list.extend(other_list)`          	| -                 	|                                            	|
| is item in list?                                 	| `item in my_list`                     	| `True` or `False` 	|                                            	|
| **index** of item                                	| `my_list.index(item)`                 	| `int`             	| `ValueError` if `item` is not in `my_list` 	|
| **count** of item                                	| `my_list.count(item)`                 	| `int`             	|                                            	|
| **remove** an item                               	| `my_list.remove(item)`                	| -                 	| `ValueError` if `item` not in `my_list`    	|
| **remove** the last item, or an item at an index 	| `my_list.pop()` or `my_list.pop(pos)` 	| `item`            	| `IndexError` if `pos` >= `len(my_list)`    	|


#### Checking Length
{: .no_toc }

Before we add or remove items, it's usually a good idea to check a list's length. We do that with the `len` built in function. We can even use the `len` built in function to check the lengths of other types, like strings.

Let's see it in action on a names `list` with two items, and a name `str`ing with four characters.

```python
>>> len(names)
2
>>> name = "Nina"
>>> len(name)
4
```

### Adding Items
{: .no_toc }

Let's start with a list of two names.

```python
>>> names = ["Nina", "Max"]
```

##### `my_list.append(item)` adds to the end of `my_list`
{: .no_toc }

We can use `my_list.append(item)` to add an additional item to the end of the list.

```python
>>> names.append("John")
>>> names
['Nina', 'Max', 'John']
```

##### `my_list.insert(pos, item)` inserts an item into `my_list` at the given position
{: .no_toc }

Use `my_list.insert(pos, item)` to insert items in an arbitrary position in the list. If the position is 0, we'll insert at the beginning of the list.

```python
>>> names.insert(0, "Rose")
>>> names
['Rose', 'Nina', 'Max', 'John']
```

You can call `dir()` on our names list to verify that it's actually of type `list`. If you forget which order insert is called in, don't forget you can always use the `help()` function on the REPL. **Remember: Press `q` to quit the help screen.** Let's try it now:

```python
>>> type(names)
<class 'list'>
>>> help(names.insert)

Help on method_descriptor:

insert(self, index, object, /)
    Insert object before index.
```

You can also call help on `names.insert`. Because `names` is already of type `list`, it achieves the same result.

##### `my_list.extend(other_list)` adds all the contents of `other_list` to `my_list`
{: .no_toc }

```python
>>> names = ["Nina", "Max"]
>>> colors = ["Red", "Blue"]
>>> names
['Nina', 'Max']
>>> names.extend(colors)
>>> names
['Nina', 'Max', 'Red', 'Blue']
```

### Looking for Items
{: .no_toc }

Looking for items in a list is *slow*. Each item needs to be checked in order to find a match.

This doesn't matter much when you're just getting started, unless your data set is large, or if you're building high-performance systems. If you want to quickly search for an item, you'll need to use a `set` or a `dict`ionary instead.

There are a few ways to determine if an item is in the list, and at which position. Let's try this on our list of names.

```python
names = ["Nina", "Max", "Phillip", "Nina"]
```

##### Use the `in` keyword to determine if an item is present or not.
{: .no_toc }

```python
>>> "Nina" in names
True
>>> "Rose" in names
False
```

##### Use the `my_list.index(item)` method to find the **first** index of a potential match.
{: .no_toc }

Notice that only the *first* index of the string `"Nina"` is returned. We'll learn more about what an index is in the next chapter.

{:.highlight}
If the item we're looking for *is not* in the list, Python will throw a `ValueError`.

You'll learn how to deal with exceptions later. For now, you can use the `in` operator to check if an item is present in the list before finding its index.

```python
>>> names.index("Nina")
0
>>> names.index("Rose")
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: 'Rose' is not in list
```

##### Use the `my_list.count(item)` method to find out how many times an item appears in a list.
{: .no_toc }

```python
>>> names.count("Nina")
2
>>> names.count("Rose")
0
```

### Updating Items
{: .no_toc }

To update items in a list, use the *position* of the item you'd like to change using square bracket `[]` syntax. Like: `my_list[pos] = new_item`

For example:

```python
>>> names = ["Nina", "Max"]
>>> names[0] = "Rose"
>>> names
['Rose', 'Max']
```

Or, when used with `my_list.index(item)`:

```python
>>> names = ["Nina", "Max"]
>>> pos = names.index("Max")
>>> names[pos] = "Rose"
>>> names
['Nina', 'Rose']
```

{:.highlight}
You'll see a `IndexError: list assignment index out of range` if you try to update an item in a position that doesn't exist, that is *if the position is greater than or equal to `>=` the length of the list*.

```python
>>> names = ["Nina", "Max"]
>>> len(names)
2
>>> names[2] = "Rose"
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: list assignment index out of range
```

### Removing Items
{: .no_toc }

There are a few ways to remove items from a list.

##### Use `my_list.remove(item)` to remove the *first* instance of the item
{: .no_toc }

Be careful. `remove()` only removes the first instance of the item from the list, which isn't always what we want to do.

```python
>>> names = ["Nina", "Max", "Rose"]
>>> names.remove("Nina")
>>> names
['Max', 'Rose']
>>>
>>>
>>> names = ["Nina", "Max", "Nina"]
>>> names.remove("Nina")
>>> names
['Max', 'Nina']
```

{:.highlight}
If we try to remove an item that's not in the list, we'll get a `ValueError: list.remove(x): x not in list`.

```python
>>> names = ["Nina"]
>>> names.remove("Max")
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: list.remove(x): x not in list
```

##### Use `my_list.pop()` to remove the last item, or `my_list.pop(index)` to remove the item at that index
{: .no_toc }

Using `pop()` will also **return** the item that was in that position. That's useful if we want to save the item.

```python
>>> names = ["Nina", "Max", "Rose"]
>>> names.pop()
'Rose'
>>> names
['Nina', 'Max']
>>> names.pop(1)
'Max'
>>> names
['Nina']
```

{:.highlight}
If we try to pop an item from an index that is longer than or equal to the length of the list, we'll get an `IndexError: pop index out of range`.

```python
>>> names = ["Nina"]
>>> len(names)
1
>>> names.pop(1)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: pop index out of range
```

### Tuples
Tuples are light-weight collections used to keep track of related, but different items. Tuples are **immutable**, meaning that once a tuple has been created, the items in it can't change.

You might ask, why tuples when Python already has lists? Tuples are different in a few ways. While lists are generally used to store collections of similar items together, tuples, by contrast, can be used to contain a snapshot of data. They can't be continually changed, added or removed from like you could with a list.

#### `tuple` cheat sheet
{: .no_toc }

| type               	| `tuple`                                                                                                 	|
|--------------------	|---------------------------------------------------------------------------------------------------------	|
| use                	| Used for storing a snapshot of related items when we don't plan on modifying, adding, or removing data. 	|
| creation           	| `()` or `tuple()` for empty tuple. `(1, )` for one item, or `(1, 2, 3)` for a tuple with items.         	|
| search methods     	| `my_tuple.index(item)` or `item in my_tuple`                                                            	|
| search speed       	| Searching for an item in a large tuple is slow. Each item must be checked.                              	|
| common methods     	| Can't add or remove from tuples.                                                                        	|
| order preserved?   	| Yes. Items can be accessed by index.                                                                    	|
| mutable?           	| **No**                                                                                                  	|
| in-place sortable? 	| **No**                                                                                                  	|

#### Uses
{: .no_toc }
A good use of a `tuple` might be for storing the information for a *row* in a spreadsheet. That data is information only. We don't necessarily care about updating or manipulating that data. We just want a read-only snapshot.


Tuples are an interesting and powerful datatype, and one of the more unique aspects of Python. Most other programming languages have ways of representing lists and dictionaries, but only a small subset contain tuples. Use them to your advantage.

### Examples
{: .no_toc }

#### Empty and one-item `tuple`s
{: .no_toc }

One important thing to note about tuples, is there's a quirk to their creation. Let's check the type of an empty `tuple` created with `()`.
```python
>>> a = ()
>>> type(a)
<class 'tuple'>
```

That looks like we'd expect it to. What about if we *tried* to create a one-item `tuple` using the same syntax?

```python
>>> b = (1)
>>> type(b)
<class 'int'>
```

It didn't work! `type((1))` is an `int`eger. In order to create a one-item tuple, you'll need to include a trailing comma.

```python
>>> c = (1, )
>>> type(c)
<class 'tuple'>
```

{:.highlight}
If you're creating a one-item tuple, you **must** include a trailing comma, like this: `(1, )`

#### Creation
{: .no_toc }

Let's say we have a spreadsheet of students, and we'd like to represent each row as a tuple.

```python
>>> student = ("Marcy", 8, "History", 3.5)
```

#### Access by index
{: .no_toc }

We can access items in the `tuple` by index, but we **can't change them**.

```python
>>> student = ("Marcy", 8, "History", 3.5)
>>> student[0]
'Marcy'
>>> student[0] = "Bob"
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'tuple' object does not support item assignment
```

{:.highlight}
We'll see `TypeError: 'tuple' object does not support item assignment` if we try to change the items in a tuple.

`tuple`s also don't have an `append` or `extend` method available on them like lists do, because they can't be changed.

### `tuple` unpacking.
{: .no_toc }

Sounds like a lot of work for not a lot of benefit, right? Not so. `tuple`s are great when you depend on your data staying unchanged. Because of this guarantee, we can use `tuples` in other types of containers like `set`s and `dict`ionaries.

It's also a great way to quickly consolidate information.

You can also use `tuples` for something called unpacking. Let's see it in action:

```python
>>> student = ("Marcy", 8, "History", 3.5)
>>>
>>> name, age, subject, grade = student
>>> name
'Marcy'
>>> age
8
>>> subject
'History'
>>> grade
3.5
```

You can return tuples from functions, and use unpacking.

```python
>>> def http_status_code():
...     return 200, "OK"
...
>>> code, value = http_status_code()
>>> code
200
>>> value
'OK'
```

### Sets
Sets are a datatype that allows you to store other **immutable** types in an unsorted way. An item can only be contained in a set once. There are no duplicates allowed. The benefits of a set are: very fast membership testing along with being able to use powerful set operations, like `union`, `difference`, and `intersection`.

#### `set` cheat sheet
{: .no_toc }

| type               	| `set`                                                                                                                         	|
|--------------------	|-------------------------------------------------------------------------------------------------------------------------------	|
| use                	| Used for storing immutable data types uniquely. Easy to compare the items in `set`s.                                          	|
| creation           	| `set()` for an empty set (`{}` makes an empty `dict`) and `{1, 2, 3}` for a set with items in it                              	|
| search methods     	| `item in my_set`                                                                                                              	|
| search speed       	| Searching for an item in a large set is very fast.                                                                            	|
| common methods     	| `my_set.add(item)`, `my_set.discard(item)` to remove the item if it's present, `my_set.update(other_set)` 	|
| order preserved?   	| **No**. Items *can't* be accessed by index.                                                                                   	|
| mutable?           	| **Yes**. Can add to or remove from `set`s.                                                                                    	|
| in-place sortable? 	| **No**, because items aren't ordered.                                                                                                                        	|

### Examples
{: .no_toc }

#### Empty `set`s
{: .no_toc }

Let's create our first few sets.

The first thing we might try to do is create an empty set with `{}`, but we'll come across a hurdle.

```python
>>> my_new_set = {}
>>> type(my_new_set)
<class 'dict'>
>>> my_set = set()
>>> type(my_set)
<class 'set'>
```

{:.highlight}
You can't create an empty `set` with `{}`. That creates a `dict`. Create an empty set with `set()` instead.

{:.highlight}
While you're learning Python, it's useful to use `type()`, `dir()` and `help()` as often as possible.

#### `set`s with items
{: .no_toc }

Now, let's make a new set with some items in it, and test out important set concepts.

#### `set`s can't contain duplicate values
{: .no_toc }

```python
>>> names = {"Nina", "Max", "Nina"}
>>> names
{'Max', 'Nina'}
>>> len(names)
2
```

#### `set`s can't contain mutable types
{: .no_toc }

The way that `set`s allow you to quickly check if an item is contained in them or not is with an algorithm called a hash. I won't cover the details, but an algorithm is a way of representing an immutable data type with a unique numerical representation. In Python, there's a built-in `hash()` function.

The `hash()` function only works on immutable data types. That means, data types where the contents can't be changed after creation.

```python
>>> hash("Nina")
3509074130763756174
>>> hash([])
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unhashable type: 'list'
```

{:.highlight}
You'll see a `TypeError: unhashable type: 'list'` if you try to add a mutable data type (like a `list`) to a set.

If you try to add a mutable data type (like a `list`) to a set, you'll see the same `TypeError`, complaining about an `unhashable type`.

```python
>>> {"Nina"}
{'Nina'}
>>> {[]}
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unhashable type: 'list'
```

#### `set`s can be used to de-duplicate the items in a list
{: .no_toc }

**Tip:** *If you don't care about order*, you can quickly de-duplicate the items in a `list` by passing the `list` into the `set` constructor.

```python
>>> colors = ["Red", "Yellow", "Red", "Green", "Green", "Green"]
>>> set(colors)
{'Red', 'Green', 'Yellow'}
```

#### `set`s don't have an order
{: .no_toc }

Sets don't have an order. That means that when you print them, the items won't be displayed in the order they were entered in the list.

```python
>>> my_set = {1, "a", 2, "b", "cat"}
>>> my_set
{1, 2, 'cat', 'a', 'b'}
```

It also means that you *can't* access items in the `set` by position in subscript `[]` notation.

```python
>>> my_set = {"Red", "Green", "Blue"}
>>> my_set[0]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'set' object does not support indexing
```

{:.highlight}
You'll see `TypeError: 'set' object does not support indexing` if you try to access the items in a `set` by index with `my_set[pos]`

**Tip:** If your set contains items of the same type, and you want to sort the items, you'll need to convert the `set` to a `list` first. Or, you can use the built-in `sorted(sequence)` method, which will do the conversion for you.

```python
>>> my_set = {"a", "b", "cat", "dog", "red"}
>>> my_set
{'b', 'red', 'a', 'cat', 'dog'}
>>> sorted(my_set)
['a', 'b', 'cat', 'dog', 'red']
```

#### adding to and removing from `set`s
{: .no_toc }

Since a set has no order, we can't add or remove items to it by index. We need to call the operations with the item itself.

#### Add items to a set with `my_set.add(item)`.
{: .no_toc }

```python
>>> colors = {"Red", "Green", "Blue"}
>>> colors.add("Orange")
>>> colors
{'Orange', 'Green', 'Blue', 'Red'}
```

#### Remove items with `my_set.discard(item)`
{: .no_toc }

You can remove an item from a `set` if it's present with `my_set.discard(item)`. If the set doesn't contain the item, no error occurs.

```python
>>> colors = {"Red", "Green", "Blue"}
>>> colors.discard("Green")
>>> colors
{'Blue', 'Red'}
>>> colors.discard("Green")
>>> colors
{'Blue', 'Red'}
```

You can also remove items from a `set` with `my_set.remove(item)`, which will raise a `KeyError` if the item doesn't exist.


#### Update a set with another sequence using `my_set.update(sequence)`
{: .no_toc }

You can update a `set` by passing in another sequence, meaning another `set`, `list`, or `tuple`.

```python
>>> colors = {"Red", "Green"}
>>> numbers = {1, 3, 5}
>>> colors.update(numbers)
>>> colors
{1, 3, 'Red', 5, 'Green'}
```

{:.highlight}
Be careful passing in a `str`ing to `my_set.update(sequence)`. That's because a `str`ing is *also* a sequence. It's a sequence of characters.

```python
>>> numbers = {1, 3, 5}
>>> numbers.update("hello")
>>> numbers
{1, 3, 'h', 5, 'o', 'e', 'l'}
```

Your set will update with each character of the `str`ing, which was probably not your intended result.

### `set` operations
{: .no_toc }

`sets` allow quick and easy operations to compare items between two sets.

#### `set` operations cheat sheet
{: .no_toc }

| Method Operation    	| Symbol Operation 	| Result    |
| ---------------------	| ------------------	| ---------------------------	|
| `s.union(t)`        	| <code>s &#124; t</code> | creates a new set with all the items **from both `s` and `t`**             |
| `s.intersection(t)` 	| `s & t`          	| creates a new set containing *only* items that are **both in `s` and in `t`** 	|
| `s.difference(t)`    	| `s ^ t`          	| creates a new set containing items that are **not in both `s` and in `t`**                        	|

#### examples
{: .no_toc }

Let's see it in action.

We have two sets, `rainbow_colors`, which contain the colors of the rainbow, and `favorite_colors`, which contain my favorite colors.

```python
>>> rainbow_colors = {"Red", "Orange", "Yellow", "Green", "Blue", "Violet"}
>>> favorite_colors = {"Blue", "Pink", "Black"}
```

First, let's combine the sets and create a new `set` that contains all of the items from `rainbow_colors` and `favorite_colors` using the union operation. You can use the `my_set.union(other_set)` method, or you can just use the symbol for union `|=` from the table above.

```python
>>> rainbow_colors | favorite_colors
{'Orange', 'Red', 'Yellow', 'Green', 'Violet', 'Blue', 'Black', 'Pink'}
```

Next, let's find the intersection. We'll create a new `set` with *only* the items in both `set`s.

```python
>>> rainbow_colors & favorite_colors
{'Blue'}
```

Lastly, We can also find the difference. Create a new set with the items that are in in one, but not the other. We'll see that `"Blue"` is missing from the list.

```python
>>> rainbow_colors ^ favorite_colors
{'Orange', 'Red', 'Yellow', 'Green', 'Violet', 'Black', 'Pink'}
```

There are other useful operations available on `set`s, such as checking if one set is a subset, a superset, and more, but I don't have time to cover them all. Python also has a `frozenset` type, if you need the functionality of a `set` in an immutable package (meaning that the contents can't be changed after creation).

Find out more by reading the [documentation](https://docs.python.org/3/library/stdtypes.html#set), or calling `help()` on `set`.

### Dictionaries
Dictionaries are a useful type that allow us to store our data in key, value pairs. Dictionaries themselves are **mutable**, *but*, dictionary keys can only be **immutable** types.

We use dictionaries when we want to be able to quickly access additional data associated with a particular key. A great practical application for dictionaries is memoization. Let's say you want to save computing power, and store the result for a function called with particular arguments. The arguments could be the key, with the result stored as the value. Next time someone calls your function, you can check your dictionary to see if the answer is pre-computed.

Looking for a key in a large dictionary is extremely fast. Unlike lists, we don't have to check every item for a match.

### `dict`ionary cheat sheet
{: .no_toc }

| type               	| `dict`                                                                                                                                             	|
|--------------------	|----------------------------------------------------------------------------------------------------------------------------------------------------	|
| use                	| Use for storing data in key, value pairs. Keys used must be **immutable** data types.                                                              	|
| creation           	| `{}` or `dict()` for an empty `dict`. `{1: "one", 2: "two"}` for a `dict` with items.                                                              	|
| search methods     	| `key in my_dict`                                                                                                                                   	|
| search speed       	| Searching for a key in a large dictionary is fast.                                                                                                 	|
| common methods     	| `my_dict[key]` to get the value by `key`, and throw a `KeyError` if `key` is not in the dictionary. Use `my_dict.get(key)` to fail silently if `key` is not in `my_dict`. `my_dict.items()` for all key, value pairs, `my_dict.keys()` for all keys, and `my_dict.values()` for all values. 	|
| order preserved?   	| **Sort of**. As of Python 3.6 a `dict` is sorted by insertion order. Items *can't* be accessed by index, only by key.                              	|
| mutable?           	| **Yes**. Can add or remove keys from `dict`s.                                                                                                      	|
| in-place sortable? 	| **No**. `dict`s don't have an index, only keys.                                                                                                    	|

### Examples
{: .no_toc }

#### Empty `dict`s
{: .no_toc }

We already learned one of the methods of creating an empty `dict` when we tried (and failed) to create an empty set with `{}`. The other way is to use the `dict()` method.

```python
>>> my_dict = {}
>>> type(my_dict)
<class 'dict'>

>>> my_dict = dict()
>>> type(my_dict)
<class 'dict'>
```

#### Creating `dict`s with items
{: .no_toc }

If we want to create `dict`s with items in them, we need to pass in key, value pairs. A `dict` is declared with curly braces `{}`, followed by a key and a value, separated with a colon `:`. Multiple key and value pairs are separated with commas `,`.


We can call familiar methods on our dictionary, like finding out how many key / value pairs it contains with the built-in `len(my_dict)` method.

```python
>>> nums = {1: "one", 2: "two", 3: "three"}

>>> len(nums)
3
```

#### Side note: What can be used as keys?
{: .no_toc }

Any type of object, mutable or immutable, can be used as a value but just like `set`s, `dict`ionaries can only use immutable types as keys. That means you can use `int`, `str`, or even `tuple` as a key, but **not** a `set`, `list`, or other `dict`ionary.

The follow is OK:

```python
>>> my_dict = {1: 1}
>>> my_dict = {1: []}
```

{:.highlight}
You'll see a `TypeError: unhashable type: 'list'` if you try to use a mutable type, like a `list` as a `dict`ionary key.

```python
>>> my_dict = {[]: 1}
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unhashable type: 'list'
```

#### Accessing
{: .no_toc }

Our `dict` contains `key`, `value` pairs. Because a `dict`ionary isn't ordered, we *can't access the items in it by position*. Instead, to access the items in it, we use square-bracket `my_dict[key]` notation, similar to how we access items in a list with square bracket notation containing the position.

```python
>>> nums = {1: "one", 2: "two", 3: "three"}
>>> nums[1]
'one'
>>> nums[2]
'two'
```

Q: What happens when we try to access a key in a `dict`ionary with square bracket notation, but the key isn't present?

{:.highlight}
We'll get a `KeyError: key` if we try to access `my_dict[key]` with square bracket notation, but `key` isn't in the dictionary.

```python
>>> nums = {1: "one", 2: "two", 3: "three"}
>>> nums[4]

Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 4
```

One way to get around this is to use the `my_dict.get(key)` method. Using this method, if the key isn't present, no error is thrown, and no value (aka the `None` type) is returned.

```python
>>> nums = {1: "one", 2: "two", 3: "three"}
>>> nums.get(4)

>>> result = nums.get(4)
>>> type(result)
<class 'NoneType'>
```

If we want to provide a *default value* if the key is missing, we also pass an *optional* argument to the `my_dict.get(key)` method like so: `my_dict.get(key, default_val)`

```python
>>> nums = {1: "one", 2: "two", 3: "three"}
>>> nums.get(4, "default")
'default'
```

#### Adding, Removing
{: .no_toc }

To add a new key value pair to the dictionary, you'll use square-bracket notation.

If you try to put a key into a dictionary that's already there, you'll just end up replacing it. To avoid subtle bugs, you can check if a particular key is in a dictionary with the `in` keyword. We'll cover that technique in the Control Statements and Looping topic.

```python
>>> nums = {1: "one", 2: "two", 3: "three"}
>>> nums[8] = "eight"

>>> nums
{1: 'one', 2: 'two', 3: 'three', 8: 'eight'}

>>> nums[8] = "oops, overwritten"
>>> nums
{1: 'one', 2: 'two', 3: 'three', 8: 'oops, overwritten'}
>>> 8 in nums
True
```

#### Updating
{: .no_toc }

Just like with `list`s an `set`s, you can update the items in a dictionary with the items from another dictionary.

```python
>>> colors = {"r": "Red", "g": "Green"}
>>> numbers = {1: "one", 2: "two"}
>>> colors.update(numbers)
>>> colors
{'r': 'Red', 'g': 'Green', 1: 'one', 2: 'two'}
```

### Complex Dictionaries
{: .no_toc }

One incredibly useful scenario for dictionaries is storing the values in a `list` or other sequence. Going into too much detail is outside of the scope of the class, but I'll show you a quick example:

```python
>>> colors = {"Green": ["Spinach"]}
>>> colors
{'Green': ['Spinach']}
>>> colors["Green"].append("Apples")
>>> colors
{'Green': ['Spinach', 'Apples']}
```

### Working with `items`, `keys`, and `values`
{: .no_toc }

There are three useful methods you need to remember about `dict`ionary access:

1. `my_dict.keys()`
2. `my_dict.values()`
3. `my_dict.items()`

#### 1. `my_dict.keys()` Getting all the keys in a dictionary
{: .no_toc }

```python
>>> nums = {1: 'one', 2: 'two', 3: 'three', 8: 'eight'}
>>> nums.keys()
dict_keys([1, 2, 3, 8])
```

#### 2. `my_dict.values()` Getting all the values in a dictionary.
{: .no_toc }

```python
>>> nums = {1: 'one', 2: 'two', 3: 'three', 8: 'eight'}
>>> nums.values()
dict_values(['one', 'two', 'three', 'eight'])
```

#### 3. `my_dict.items()` Getting all the items (key, value pairs) in a dictionary
{: .no_toc }

Notice that `my_dict.items()` returns a type that looks like a list. It contains two-item `tuple`s containing the key, value pairs.

```python
>>> nums = {1: 'one', 2: 'two', 3: 'three', 8: 'eight'}
>>> nums.items()
dict_items([(1, 'one'), (2, 'two'), (3, 'three'), (8, 'eight')])
```

---

## Mutability

Mutability, simply put: the contents of a **mutable** object can be _changed_, while the contents of an **immutable** object _cannot be changed_.

### Simple Data Types
{: .no_toc }

All of the simple data types we covered first are **immutable**:

| type                      	| use                     	| mutable? 	|
|---------------------------	|-------------------------	|----------	|
| `int`, `float`, `decimal` 	| store numbers           	| **no**   	|
| `str`                     	| store strings           	| **no**   	|
| `bool`                    	| store `True` or `False` 	| **no**   	|

### Collection/Container Types
{: .no_toc }

For the mutability of the container types we covered in this chapter, check this helpful list:

| container type 	| use                                                                                                     	| mutable? 	|
|----------------	|---------------------------------------------------------------------------------------------------------	|----------	|
| `list`         	| ordered group of items, accessible by position                                                          	| **yes**  	|
| `set`          	| mutable unordered group consisting only of immutable items. useful for set operations (membership, intersection, difference, etc) 	| **yes**  	|
| `tuple`        	| contain ordered groups of items in an **immutable** collection                                          	| **no**   	|
| `dict`         	| contains key value pairs                                                                                	| **yes**  	|

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [LearnPython - Nina Zakharenko](https://www.learnpython.dev/).
{: .fs-2 }
