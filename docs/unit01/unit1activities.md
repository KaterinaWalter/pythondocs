---
layout: notes
title: "🎯 Unit 1 Activities" 
parent: "1️⃣ Python Bootcamp"
nav_order: 4
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

<html>
  <details>
    <summary>💻 <strong class="text-green-200">ACTIVITY PROGRAM SETUP INSTRUCTIONS</strong></summary>
    
<div class="setup" markdown="block">

1. Go to the public template **repository** for our class: [BWL-CS Python Template](https://github.com/BWL-CS/python-template)
2. Click the <button type="button" name="button" class="btn btn-green">Use this template</button> button above the list of files then select `Create a new repository`
3. Specify the **repository name**: `CS3-Unit1-Activity#`
    > Replace `#` with the specific _activity number_.
4. Click <button type="button" name="button" class="btn btn-green">Create repository</button>
    > Now you have **your own personal copy** of this starter code that you can always access under the `Your repositories` section of GitHub! 📂
5. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
6. Click `Create Codespace on main` and wait for the environment to load, _then you're ready to code_!

</div>

<br>

<div class="warn" markdown="block">

🛑 When class ends, don't forget to **SAVE YOUR WORK**! **Codespaces** are TEMPORARY editing environments, so you need to COMMIT changes properly in order to update the main **repository** for your program. 

_There are multiple steps to saving in GitHub Codespaces:_

1. Navigate to the `Source Control` menu on the _LEFT_ sidebar
2. Click the <button type="button" name="button" class="btn btn-green">commit changes</button> button on the _LEFT_ menu
3. Type a brief **commit message** at the top of the file that opens, for example: `updated main.py`
4. Click the small `✔️` **checkmark** in the _TOP RIGHT_ corner
5. Click the <button type="button" name="button" class="btn btn-green">sync changes</button> button on the _LEFT_ menu
6. _Finally you can close your Codespace!_

</div>

  </details>
</html>

---

## ACTIVITY #1: Variables & Data Types Practice

### PART : Lists

Lists are great for storing an ordered sequence of objects. 

<div class="task" markdown="block">

Remember that you can see the current state of your list at any time by typing the name of your list by itself. Check your list after every operation to see if it has changed.

```python
>>> my_list = ["h", "e", "l", "l", "o"]
# Let's look at our list:
>>> my_list
# Let's add to my_list:
>>> my_list.append("!")
# Now let's see it again:
>>> my_list
```
</div>

<div class="task" markdown="block">

Let's play with slices. How do we get the last two elements of our list?

```python
# We know the number of items in our list is 6...
>>> len(my_list)
6
# So the last two indexes are 4 and 5. Since the first number in the slice is inclusive, and the second number is exclusive, we can ask for everything between index 4 and 6
>>> my_list[4:6]
# We can also say "Give me everything after index 4
>>> my_list[4:]
# Or, we can ask for just the last two items without caring how big the list is. This means "give me everything starting from two before the end":
>>> my_list[-2:]
```
</div>

<div class="task" markdown="block">

There are many other ways to interact with our lists as well:

```python
# Remove the first L:
>>> my_list.remove("l")
# Let's put it back at index 2
>>> my_list.insert(2, "l")

# Delete any element
>>> del my_list[0]
# Remove and return the last element. Useful for queues!
>>> last_item = my_list.pop()
>>> last_item

# We can also look at individual items my using an index:
>>> my_list[2]
# Or we can see if a certain value exists in the list:
>>> "!" in my_list
# Let's sort our list in reverse order
>>> my_list.sort(reverse=True)
>>> my_list
# Note that sort() doesn't return anything, it sorts the list in-place
# You can also use the sorted() function to return a new, sorted list without modifying the old one
>>> sorted(my_list, reverse=False)
>>> my_list
```
</div>

<html>
<details>
<summary><strong>✅ Check your result after testing (no peeking!):</strong></summary>
<div markdown="block"> 

```python
>>> my_list = ["h", "e", "l", "l", "o"]
>>> my_list
['h', 'e', 'l', 'l', 'o']
>>> my_list.append("!")
>>> my_list
['h', 'e', 'l', 'l', 'o', '!']

>>> len(my_list)
6
>>> my_list[4:6]
['o', '!']
>>> my_list[4:]
['o', '!']
>>> my_list[-2:]
['o', '!']

>>> my_list.remove("l")
>>> my_list.insert(2, "l")
>>> del my_list[0]
>>> last_item = my_list.pop()
>>> last_item
'o'
>>> my_list[2]
'l'
>>> "!" in my_list
False
>>> my_list.sort(reverse=True)
>>> my_list
['o', 'l', 'l', 'h', 'e', '!']
>>> sorted(my_list, reverse=False)
['!', 'e', 'h', 'l', 'l', 'o']
```

</div>
</details>
</html>

### PART : Tuples

Tuples are a lightweight way to hold information that describes something, like a person - their name, age, and hometown. You can think about it kind of like a row in a spreadsheet. Tuples are represented inside parentheses, however parentheses are not required to create a tuple, just a sequence of objects followed by commas.

<div class="task" markdown="block">

Try this:

```python
>>> my_tuple = 1,
>>> my_tuple
# Let's add to our tuple
>>> my_tuple[1] = 2
```

</div>

Oops! Remember that tuples are immutable, so you can't change them once they've been created. Tuples are great for moving data around in a lightweight way, because you can unpack them easily into multiple variables.

<div class="task" markdown="block">
Try this:
    
```python
>>> person = ('Jim', 29, 'Austin, TX')
>>> name, age, hometown = person
>>> name
>>> age
>>> hometown
```

</div>

<html>
<details>
<summary><strong>✅ Check your result after testing (no peeking!):</strong></summary>
<div markdown="block"> 
    
```python
>>> my_tuple = 1,
>>> my_tuple
(1,)
>>> my_tuple[1] = 2
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'tuple' object does not support item assignment
```

```python
>>> person = ('Jim', 29, 'Austin, TX')
>>> name, age, hometown = person
>>> name
'Jim'
>>> age
29
>>> hometown
'Austin, TX'
```

</div>
</details>
</html>

### PART : Sets

Sets are a great data type for storing unique data - you can only have one of any given object in a set. Sets are unordered, thus you can't access them with `[]` indexing syntax, but they do have some handy functions.

<div class="task" markdown="block">

Let's play with some set operations:

```python
# Create an empty set
>>> my_set = {}
>>> type(my_set)
# Gotcha: using {} actually creates an empty dictionary. To create an empty set, use set()
>>> my_set = set()
>>> my_set

# Let's create a non-empty set
>>> my_set = {1, 2, 3}
# We can add and remove items from the set
>>> my_set.add(4)
>>> my_set.remove(2)
# We can test if an item exists in the set
>>> 2 in my_set

# Unlike lists, every item in a set must be unique
>>> my_set
>>> my_set.add(3)
>>> my_set
# There is still only one 3 in the set

>>> my_set
# my_set should equal {1, 3, 4}
>>> my_other_set = {1, 2, 3}
# We can combine two sets
>>> my_set.union(my_other_set)
# We can get the intersection of two sets
>>> my_set.intersection(my_other_set)
# We can get the difference of two sets
>>> my_set.difference(my_other_set)

```
</div>

<html>
<details>
<summary><strong>✅ Check your result after testing (no peeking!):</strong></summary>
<div markdown="block"> 
    
```python
>>> my_set = {}
>>> type(my_set)
<class 'dict'>
>>> my_set = set()
>>> type(my_set)
<class 'set'>

>>> my_set = {1, 2, 3}
>>> my_set.add(4)
>>> my_set.remove(2)
>>> 2 in my_set
False

>>> my_set
{1, 3, 4}
>>> my_set.add(3)
>>> my_set
{1, 3, 4}

>>> my_other_set = {1, 2, 3}
>>> my_set.union(my_other_set)
{1, 2, 3, 4}
>>> my_set.intersection(my_other_set)
{1, 3}
>>> my_set.difference(my_other_set)
{4}
```

</div>
</details>
</html>

### PART : Dictionaries

Dictionaries are great for storing data that you can index with keys. The keys must be unique, and the dictionaries *are* stored in the order you inserted items, however this is only guaranteed as of Python 3.7.

<div class="task" markdown="block">

Try this:
    
```python
>>> my_dict = {"key": "value"}
# Remember, dictionaries don't have numerical indexes like lists, so if you try to use an index number...
# Unless 0 happens to be a key.
>>> my_dict[0]
# You'll get a KeyError!

# Let's put some more things into our dictionary
>>> my_dict["hello"] = "world"
>>> my_dict["foo"] = "bar"
>>> my_dict

# What was the value for "hello" again?
>>> my_dict["hello"]
# You can also use get() to get a key
>>> my_dict.get("hello")
# What if the key you want doesn't exist?
>>> my_dict["baz"]
# If you're not sure if a key exists, you can ask:
>>> "baz" in my_dict
# Or you can use a default value. If "baz" doesn't exist, return "boo":
>>> my_dict.get("baz", "boo")

# Let's try separating the dictionary into lists of keys and values:
>>> my_dict.keys()
>>> my_dict.values()

# What if we want to iterate over a dictionary's items? We can use the items() function to get a list of tuples:
>>> my_dict.items()
```
</div>

<html>
<details>
<summary><strong>✅ Check your result after testing (no peeking!):</strong></summary>
<div markdown="block"> 
    
```python
>>> my_dict = {"key": "value"}
>>> my_dict[0]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 0

>>> my_dict["hello"] = "world"
>>> my_dict["foo"] = "bar"
>>> my_dict
{'foo': 'bar', 'hello': 'world', 'key': 'value'}

>>> my_dict["hello"]
'world'
>>> my_dict.get("hello")
'world'
>>> my_dict["baz"]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'baz'
>>> "baz" in my_dict
False
>>> my_dict.get("baz", "default response")
'default response'

>>> my_dict.keys()
['foo', 'hello', 'key']
>>> my_dict.values()
['bar', 'world', 'value']

>>> my_dict.items()
[('foo', 'bar'), ('hello', 'world'), ('key', 'value')]
```

</div>
</details>
</html>


### PART : Mutability

Remember, in Python, some data types are **immutable** -- that means that once they're created, their contents can't be changed. Tuples are immutable - once you make one, you can't alter it, you can only make a new one. Conversely, lists, dictionaries, and sets are mutable - you can change them without making new ones.

<div class="task" markdown="block">

Let's see this in practice:

```python
# Lists are mutable
>>> my_list = [1, 2, 3]
>>> my_list[0] = 'a'
>>> my_list

# Dictionaries are also mutable
>>> my_dict = {"hello": "world"}
>>> my_dict["foo"] = "bar"
>>> my_dict

# Sets are mutable, but don't support indexing or item assignment, so you have to use add() and remove()
>>> my_set = {1, 2, 3}
>>> my_set[0] = 'a' # This will throw a TypeError
>>> my_set.add('a')
>>> my_set

# Tuples are immutable
>>> my_tuple = (1, 2, 3)
>>> my_tuple[0] = 'a' # This will throw a TypeError
```
</div>

<html>
<details>
<summary><strong>✅ Check your result after testing (no peeking!):</strong></summary>
<div markdown="block"> 
    
```python
>>> my_list = [1, 2, 3]
>>> my_list[0] = 'a'
>>> my_list
['a', 2, 3]

>>> my_dict = {"hello": "world"}
>>> my_dict["foo"] = "bar"
>>> my_dict
{'hello': 'world', 'foo': 'bar'}

>>> my_set = {1, 2, 3}
>>> my_set[0] = 'a'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'set' object does not support item assignment
>>> my_set.add('a')
>>> my_set
{1, 2, 3, 'a'}

>>> my_tuple = (1, 2, 3)
>>> my_tuple[0] = 'a'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'tuple' object does not support item assignment
```

</div>
</details>
</html>

---

## ACTIVITY #2: 

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [LearnPython - Nina Zakharenko](https://www.learnpython.dev/).
{: .fs-2 }


