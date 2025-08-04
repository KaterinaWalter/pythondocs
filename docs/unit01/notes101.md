---
layout: notes
title: "📓1.1: Variables & Functions" 
parent: "1️⃣ Python Bootcamp"
nav_order: 1
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

## Introduction to the Python Language
### What is Python?

Python is a programming language created by Guido Van Rossum in the late 1980s. Python the language is [open source](https://github.com/python/cpython).

Python has a wide variety of **real-world applications** such as:

- AI/ML
    - SciPi
    - NumPy
    - Pandas
    - PyTorch
- Hardware & Micro-controllers
    - Raspberry Pi
    - MicroPython
    - CircuitPython
- Web Development
    - Django
    - Flask
- Scripting
    - DevOps
    Configuration scripts

Python has an incredibly rich fully featured [standard library](https://docs.python.org/3/library/), as well as the [PyPI Package Index](https://pypi.org/) for 3rd party packages, which as of February 2019 contains 167,107 packages.

Python is considered to be a "batteries included" language, because the standard library contains a majority of the libraries and packages you'll need in a standard application.

#### PEP8 STYLE GUIDELINES
{:.no_toc}

[PEP8](https://pep8.org/) is a Python **coding standard**, that sets guidelines for how our Python code should look like. 
> 💬 How does the style guide for the Python language compare to the conventions we learned in Java last year? Or JavaScript from the year before?

### GitHub Account Setup

<div class="task" markdown="block">

1. **Go to:** [GitHub Sign Up](https://github.com/signup)
2. Enter your `@gbwl.org` **school email**
3. Create a **password** that you'll remember 
4. Enter a **username** that follows this pattern: `FirstName` `LastInitial` `GradYear`
    > _For example:_ `KaterinaW2014`
    > 
    > DO NOT include your entire last name (_privacy reasons_)
5. After verifying your account, **let me know** so I can add you to the GitHub Classroom group!
6. Once everyone is ready, we'll follow this **tutorial**: [GitHub Workflow](https://docs.github.com/en/get-started/start-your-journey/hello-world)
   
</div>

---

## Variables & Data Types

First, make sure you have a blank Python program to take notes and code along as we dive into the lesson:

<html>
  <details>
    <summary>📓 <strong class="text-green-200">NOTES PROGRAM SETUP INSTRUCTIONS</strong></summary>
    
<div class="setup" markdown="block">

1. Go to the public template **repository** for our class: [BWL-CS Python Template](https://github.com/BWL-CS/python-template)
2. Click the <button type="button" name="button" class="btn btn-green">Use this template</button> button above the list of files then select `Create a new repository`
3. Specify the **repository name**: `CS3-Unit1-Notes`
4. Click <button type="button" name="button" class="btn btn-green">Create repository</button>
    > Now you have **your own personal copy** of this starter code that you can always access under the `Your repositories` section of GitHub! 📂
5. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
6. Click `Create Codespace on main` and wait for the environment to load, _then you're ready to code_!
7. 📝 Take notes in this Codespace during class, writing **code** & **comments** along with the instructor.

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

### Variables Store Data

**Variables** in Python allow us to store information and give it a label that we can use to retrieve that information later. We can use variables to store numbers, strings (a sequence of characters), or even more complex data types like lists and dictionaries.

{: .highlight }
We assign _values_ to _variables_ by putting the _value_ to the right of an equal sign.

Because Python is a *dynamic* language, we **don't need to declare the type** of the variables before we store data in them.

That means that this is valid Python code:

```python
x = 42
```
> Compare to variable initialization in Java: `int x = 42;`

Unlike strictly-typed languages, the **type** of what's contained in Python variables can CHANGE at any time!

For example, the below is perfectly valid Python code:

```python
x = 42
x = "hello"
```
> Here, the value of the variable `x` changed from a number to a string.

#### Naming Variables
{: .no_toc }

When creating variables in Python, there are a few best practices you should follow. The [PEP8 guidelines](https://www.python.org/dev/peps/pep-0008/#naming-conventions) specify the following convention for naming variables: 

{: .highlight }
Python variable names are entirely **lowercase**, with multiple words separated by **underscores** `_`. 

> Unlike other languages that name multi-word variables with **camelCase** (like `Java`).

Because Python is a **dynamic language** and you don't have type hints to explain what's stored inside a variable while reading code, you should do your best naming your variables to **clearly describe** what is stored inside of them.

It's ok to be _verbose_. For example, `n` is a poor variable name, while `numbers` is a better one. If you're storing a collection of items, name your variable as a **plural**.

<div class="warn" markdown="block">

* You can't _start_ your variable name with a numerical digit, although your variable name can _end_ in a digit. 
* Your variable name can't contain special characters, such as `!`,  `@`,  `#`, `$`,  `%` and more.
* There are some things that you can't name your variables, such as `and`, `if`, `True`, or `False`. That's because Python uses these names for program control structure.
* 💣 Python will let you override built-in methods and types without a warning so don't name your Python variables things like `list`, `str`, or `int`.
    * If you notice your program behaving oddly and you can't find the source of the bug, double check the list of [built-in functions](https://docs.python.org/3/library/functions.html) and [built-in types](https://docs.python.org/3/library/stdtypes.html) to make sure that your variable names don't conflict.

</div>

### Numbers
There are three different types of numbers in Python: `int` for **Integer**, **Float**, and **Complex**.

```python
# These are all INTEGERS
x = 4
y = -193394
z = 0
```

```python
# These are all FLOATS
x = 5.0
y = -3983.2
z = 0.
```

```python
# This is a COMPLEX number
x = 42j
```

In Python, Integers and other simple data types are just considered **"objects"** under the hood. That means that you can create new ones by calling methods. You can provide either a number, or a string. This will come in handy later on in the course.

```python
# Converting number types
x = int(4)
y = int('4')
z = float(5.0)
```

Python also provides a `decimal` library, which has certain benefits over the `float` datatype. For more information, refer to the [Python documentation](https://docs.python.org/3/library/decimal.html).

### Mathematical Operations
{: .no_toc }

Numbers can be added together. If you add a `float` and an `int`, the resulting type will be a `float`.

If you divide two `int`s (integers), the result will be of type `float`.

### Booleans
{: .no_toc }

In Python, Booleans are of type `bool`. Surprisingly, the boolean types `True` and `False` are also numbers under the hood.

* `True` is `1` under the hood.
* `False` is `0` under the hood.

### Strings

String text in Python can be enclosed either with single quotes like `'hello'` or double quotes, like `"hello"`.

Strings can also be **concatenated** (added together) using the `+` operator to combine an arbitrary number of Strings. For example:

<pre><code class="plaintext">1334</code></pre>

```python
salutation = "Hello "
name = "Nina"
greeting = salutation + name
# The value of greeting will be "Hello Nina"
```

To use the same type of quote within a string, that quote needs to be **escaped** with a `\` - backwards slash.

```python
greeting = 'Hello, it\'s Nina'
```

Alternately, mixed quotes can be present in a Python string without escaping.

```python
# Notice that the single quote ' is surrounded by
# double quotes, ""
greeting = "Hello, it's Nina"
```

Long multi-line strings can be represented in between `"""` (triple quotes), but the whitespace will be part of the string.

```python
long_greeting = """
                Greetings and salutations, dear Nina.
                I'm superfluous with my words,
                and require more space to say Hello!"
                """
```

#### The `print()` Function

Strings can be printed out (_displayed_) using the `print()` function in Python.

To use the `print()` function, call it with a **string literal** or a **variable**:

```python
print("Hello")
```
```python
name = "Katerina"
print(name)
```

#### The `type()` Function

Python has a very easy way of determining the type of something, with the `type()` function.

```python
num = 42
print(type(num))
```
> The output in this case would be: `<class 'int'>`.

#### No-Value, `None`, or Null Value
{: .no_toc }

There's a special type in Python that signifies no value at all. In other languages, it might be called Null. In Python, it's called `None`.

```python
x = None
print(x)
```
> If you try to examine a variable that's been set to `None`, you won't see any output. We'll talk more about the `None` type later in the class.

#### String Formatting

There are several types of string formatting in Python. If you're using Python 3.7 and above you can use my favorite type of string formatting, and the one I'll be using for the course called **f-Strings**.

{:.highlight}
With f-Strings, your string is prepended with the letter `f` and your **variables** or **expressions to interpret** are placed in `{brackets}`.

```python
name = "Nina"
print(f"Hello, my name is {name} and I pay ${rent / 30} in rent per day")
```
```
Hello, my name is Nina and I pay $16.0 in rent per day
```
> **f-Strings** allow you to simply and easily reference variables in your code, and as a bonus, they're *much* faster to type.

### Common Errors

There are a few common errors that you'll encounter when working with Strings and numbers. In Python programs, errors are called `Exceptions`. By going over what they are, you'll be able to recognize them immediately.

#### Scenario 1: Mismatched string quotes
{: .no_toc }

{:.highlight}
Mismatched string quotes will result in a `SyntaxError`

When we try to start a String with one type of quote, and end with another, we'll see a syntax error.

For example, starting the string Hello with a double quote, and ending in a single quote, like this:

```python
>>> name = 'Hello"
  File "<stdin>", line 1
    name = "Hello'
                 ^
SyntaxError: EOL while scanning string literal
```

**Solution:** use matching quote types for defining your strings. Either single quotes `'Hello'` or double quotes `"Hello"`.

#### Scenario 2: Trying to print a String and a number with concatenation using the "+" symbol.
{: .no_toc }

{:.highlight}
Trying to add or concatenate a String and a number will result in a `TypeError`


If you add try to add (or concatenate) a String and a number, you'll get an error saying that adding the two types together isn't possible.

```python
>>> print(3 + " Three")
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unsupported operand type(s) for +: 'int' and 'str'
```

**Solutions:**

There are two possible solutions here, for two different scenarios.

1. In the first scenario, you'd like to add a number to a string via **concatenation**. In order to do that, you must first convert the number to a string via the `str()` method.

```python
>>> my_num = 3
>>> print(str(my_num) + " Three")
3 Three
```

2. In the second scenario, you'd like to a convert a number that's contained in a string (ex: `"3"`) into an Integer, so you can use it like any other number. In this case, you'd like to convert it to an Integer, with the `int()` method.

```python
>>> str_num = "3"
>>> print(int(str_num) + 5)
8
```

---

## Functions

The purpose of _functions_ in Python are to **create reusable code**. If we find ourselves copying and pasting the same code multiple times, that's a good sign that a function might help!

### Defining Functions

<div class="imp" markdown="block">

This is the recipe for defining a Python function:

1. `def`: the `def` keyword, telling Python we're about to start a function definition
1. a name for the function
1. `(`: opening parenthesis
1. (optional) the **names** of one or more arguments, separated with `,`
1. (optional) the **names** and **values** of one or more default arguments, separated with (`,`) *note: we'll see these in the next section*
1. `)` closing parenthesis
1. `:` a colon

</div>

{:.highlight}
A function in Python is defined with the `def` keyword, followed by the function names, zero or more argument names contained in parenthesis `()`, and a colon `:` to indicate the start of the function. The contents of the function then follow. Then, an *optional* `return` statement can follow, if the function plans on passing data back to the caller.

```python
# Function that accepts no arguments and returns nothing.
def hello_world():
    print("Hello, World!")
```
```python
# Function that accepts two arguments and returns the sum.
def add_numbers(x, y):
    return x + y
```

{:.highlight}
If you **forget** the recipe while trying to create a function, Python will help you remember with a `SyntaxError`.

For example, trying to create a function without the colon `:`:

```python
>>> def hello_world()
  File "<stdin>", line 1
    def hello_world()
                    ^
SyntaxError: invalid syntax
```

And trying to create a function without the parenthesis `()`:

```python
>>> def hello_world:
  File "<stdin>", line 1
    def hello_world:
                   ^
SyntaxError: invalid syntax
```

### Function Contents
{: .no_toc }

<div class="imp" markdown="block">

The recipe for **function contents**:

1. a new line
1. indentation (press tab on your keyboard)
1. one or more lines
1. (optional) a `return` statement

</div>

#### `return` statement
{: .no_toc }

A `return` statement is a way to "short-circuit" the function.

Using a `return` statement, you can optionally **pass back data** to the caller of your function.

#### with no `return` statement
{: .no_toc }

If a function doesn't have a return statement, it implicitly returns `None`.

```python
def foo():
    x = 5

val = foo()
print(type(val))
```

#### with a `return` statement, but no value
{: .no_toc }

If a function has a return statement, but no value, it also returns `None`. This is typically used to control the **flow** of a program.

```python
def foo():
    x = 5
    return

val = foo()
print(type(val))
```

#### with a `return` statement and a value
{: .no_toc }

To return a value from a function, just type it after the `return` statement. You can return anything from a Python function, including other functions! For today, we'll focus on simple and complex data types.

```python
def foo():
    x = 5
    return x

val = foo()
print(val)
```

As we explore simple functions, our `return` statements will usually be at the **END** of the function, but that's not the only way they can be used. A function can have multiple `return` statements, and those `return` statements can be used to help control the flow of the program.


#### Indentation
{: .no_toc }

One of the most important aspects of functions is **indentation**. Remember, Python doesn't use curly braces to figure out what's inside a function like other languages you've seen like JavaScript or Java.
> Python _knows what code is related to a function_ by how it's indented. Anything that's indented **one level deep** under the function declaration is part of the function, no matter how many spaces there are between lines.

{:.highlight}
To add a level of **indentation**, just press the `Tab` key on your keyboard after entering a new line, or type 4 `spaces`.


### Calling Functions

Once you've defined a function, you can call it from your Python code as many times as you'd like.

{:.important}
📣 To CALL a Python function: type its **name**, along with **parentheses** `( )`, and pass in any *required* **arguments** to the function.

#### With no arguments
{: .no_toc }

Let's try it now, with a function that doesn't require arguments.

```python
def hello_world():
    print("Hello, World!")

# Call function
hello_world()
```

#### With arguments
{: .no_toc }

Let's try it again, this time with a function that does accept arguments – it needs **INPUT** to work. 

{:.highlight}
Here, note that the function _definition_ accepts **variable names** for the arguments. But, when we _call_ the function, we're passing in actual **values**.

```python
def add_numbers(x, y):
    return x + y

# Call function
add_numbers(3, 5)
```

#### Storing the `return` value of a function
{: .no_toc }

Storing the `return`ed value (**OUTPUT**) of a function is easy. All you need to do is assign the function call to a variable: 

```python
def add_numbers(x, y):
    return x + y

new_number = add_numbers(3, 5)
print(new_number)
```
> The variable `new_number` now contains the result of running our `add_numbers` function with our arguments `3` and `5`.

### Arguments in Practice
{: .no_toc }

#### Positional arguments are required
{: .no_toc }

Positional arguments are all **required**, and must be given in the **order** they are declared.

For example, this function doesn't do what we expected, because we passed in our arguments in the wrong order:

```python
def say_greeting(name, greeting):
    print(f"{greeting}, {name}.")

say_greeting("Hello!", "Nina")
```

#### Keyword arguments with default values
{: .no_toc }

Functions can accept two types of named arguments, ones without default values, and ones with default values. Arguments that have default values are called **keyword arguments**. 
> The nice thing about defaults is they can be _overridden_ when needed.

Let's see this in practice, by writing two functions that print out a greeting. One function will have a default argument to make things easier for us.

```python
# No default arguments
def say_greeting(greeting, name):
    print(f"{greeting}, {name}.")
```

Let's make a new function, `say_greeting_with_default` that accepts two arguments -- `name`, and a now **optional** argument, `greeting`. 
```python
# Default argument
def say_greeting_with_default(name, greeting="Hello", punctuation="!"):
    print(f"{greeting}, {name}{punctuation}")
```
> If `greeting` is not passed in, it will default to `Hello`.

#### Order matters!
{: .no_toc }

A function can accept all of one type or the other, but **arguments need to go in a specific order**.

All of the *required arguments go first*. They are then *followed by the optional keyword arguments*.

What happens when we try to define our arguments out of order? If you guessed a `SyntaxError`, you're correct!

```python
>>> def say_greeting_bad(greeting="Hello", name):
...     print("Oops, this won't work!")
...
  File "<stdin>", line 1
SyntaxError: non-default argument follows default argument
```

### Calling functions with arguments
{: .no_toc }

There are a few important things to know about calling functions with arguments.

#### Arguments without defaults are **required**!
{: .no_toc }

Arguments without default values are **required** by Python. Otherwise your function wouldn't know what to do! If you don't pass in all the required arguments, you'll get a `TypeError`.

```python
>>> def say_greeting(name, greeting):
...     print(f"{greeting}, {name}.")
...
>>> say_greeting("Nina")
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: say_greeting() missing 1 required positional argument: 'greeting'
```

#### You can pass in none, some, or all of the keyword arguments
{: .no_toc }

If your function takes keyword arguments, you can provide zero, one, or all of them when you call it. You don't need to pass these arguments in order either.

```python
>>> def create_query(language="JavaScipt", num_stars=50, sort="desc"):
...     return f"language:{language} num_stars:{num_stars} sort:{sort}"
...
>>> create_query()
'language:JavaScipt num_stars:50 sort:desc'
>>> create_query(language="Ruby")
'language:Ruby num_stars:50 sort:desc'
>>> create_query(num_stars=1, language="Python", sort="asc")
'language:Python num_stars:1 sort:asc'
```

#### You can pass in required parameters by keyword.
{: .no_toc }

Even if your function arguments don't have keyword arguments with defaults, you can still pass values in to the function by name. This is especially helpful if you want to be extra clear about what you're passing in.

```python
>>> def say_greeting(name, greeting):
...     print(f"{greeting}, {name}.")
...
>>> say_greeting("Nina", "Hello")
Hello, Nina.
>>> say_greeting(name="Max", greeting="Bonjour")
Bonjour, Max.
```

### Arguments Danger Zone
{: .no_toc }

{:.warning}
Never use **mutable** types, like `list`s, as a default argument.

We'll talk more about `list`s and mutability in the coming chapter, but for the time being remember to never use an empty list as a default value to a function.

Why? Because it won't work like you'd expect it to.

```python
>>> # Don't do this!
>>> def add_five_to_list(my_list=[]):
...     my_list.append(5)
...     return my_list
...
>>> # This works like we expected it to.
>>> add_five_to_list()
[5]
>>> # Huh?
>>> add_five_to_list()
[5, 5]
>>> # We see that the original `my_list` is still being modified.
>>> add_five_to_list()
[5, 5, 5]
```

If you need to use a mutable type, like a `list` as a default, use a *marker* instead. We'll cover this technique when we talk about `list`s in the next chapter.

In Python, default arguments are evaluated only once -- when the function is defined. Not each time the function is called. That means if you use a value that can be changed, it won't behave like you'd expect it to.

### Naming Functions and Arguments
{: .no_toc }

Because Python is a dynamic language (sometimes called duck-typed) we use names as cues for what our function does, the arguments it accepts, and the values it returns.

This is especially important because we generally don't declare *types* for our programs when we're first starting out. *Note: Python does support Type hinting, but it's more of an intermediate feature. Make sure you have the basics down before learning more about it.*

{:.highlight}
Try to avoid single character names for your functions and variables, unless they have meaning in math.

For example, in this function, `x` and `y` are common names used when referring to points, so it's OK to use single-letter names in this scenario.

```python
def add_points(x1, y1, x2, y2):
    return x1 + x2, y1 + y2
```

For sequences, like `list`s, it's appropriate to name them in the plural.

For example, I'd expect a variable called `name` to be a single string, and a variable called `names` to be a list of strings.

{:.highlight}
A great resource to help you figure out the best naming conventions to use in your production Python code is a talk by Brandon Rhodes, called ["The Naming of Ducks: Where Dynamic Types Meet Smart Conventions"](https://www.youtube.com/watch?v=YklKUuDpX5c).

### Function Scope

🔎 Inside of a function in Python, the **scope** changes.

Think about it this way: scoping in Python happens with **whitespace**. When we delineate the code a function contains by indenting it under a function definition, it's scope **changes** to a new internal scope. It has access to the variables defined outside of it, but it can't change them.

Once the function is done running, its scope goes away, as do its defined variables.

```python
>>> def twitter_info():
...     twitter_account = "nnja"
...     print(f"Account inside function: {twitter_account}")
...
>>> twitter_info()
Account inside function: nnja
>>> print(f"Account outside of function: {twitter_account}")
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'twitter_account' is not defined
```

We get a `NameError` when trying to access the `twitter_account` variable outside of the function. That's because it's out of scope, exactly like we expected it to be.


#### Using variables defined outside of the function
{: .no_toc }

Generally, we want to be careful when using variables defined outside of our function.

Note, that if we try to change the value of a variable defined outside of our function, we'll see the changes in the function, but not outside of it.

You can't change variables defined outside of the function inside of the function. If you try to, your changes will only apply while the function is running. Once the function is done running, the value goes back to what it was before your function ran.

A little confusing, but let's see it in action:

```python
>>> name = "Nina"
>>> print(f"Name outside of function: {name}")
Name outside of function: Nina
>>>
>>> def try_change_name():
...     name = "Max"
...     print(f"Name inside of function: {name}")
...
>>> try_change_name()
Name inside of function: Max
>>> print(f"Name outside of function: {name}")
Name outside of function: Nina
```

If we didn't know what to look for, the program might not behave how we'd expect it to. A good rule of thumb is to name our variables clearly, and minimize how many variables we declare outside of functions and classes, which you'll learn about in day two.


{:.highlight}
An appropriate use is when using a **constant**, a variable defined in all caps, with the words separated by underscores. A constant is a value that we expect to use several times within our program, but we never expect to change it programmatically.

For example:

```python
>>> ROOT_API_URL =  "https://api.github.com"
>>> def api_search_repos_url():
...     return f"{ROOT_API_URL}/search/repositories"
...
>>> api_search_repos_url()
'https://api.github.com/search/repositories'
>>>
```

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [LearnPython - Nina Zakharenko](https://www.learnpython.dev/).
{: .fs-2 }

