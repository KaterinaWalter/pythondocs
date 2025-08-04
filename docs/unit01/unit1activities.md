---
layout: notes
title: "🎯 Unit 1 Activities" 
parent: "1️⃣ Python Bootcamp"
nav_order: 5
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

## 🧑‍🍳 ACTIVITY #1: Cooking with Functions

In this activity, you’ll write Python functions that represent steps in cooking simple recipes. Your goal is to **practice different types of function definitions** — with and without _arguments_, with and without _return_ values.

You'll also **call** your functions, and sometimes **store the result** if the function returns a value.

### PART A: Functions with No Arguments and No Return

<div class="task" markdown="block">

Define two functions that **just print steps**, like a recipe card.

```python
#Function that prints the steps to boil water
def boil_water():
    print("Fill a pot with water.")
    print("Put the pot on the stove.")
    print("Turn on the heat and wait for it to boil.")

# Function that prints a welcome message for the recipe
def welcome_message():
    print("Welcome to Python's Virtual Kitchen!")
    print("Today, we’ll learn how to make delicious recipes using functions.")
```

📣 **Call** both of these functions in your code to test them out!

</div> 

---

### PART B: Functions with Arguments and No Return

<div class="task" markdown="block">

Now define a function that takes in **ingredients** and **prints them out** as part of a recipe.

```python
# Function that prints the ingredients for a recipe
def list_ingredients(main_ingredient, side_dish):
    print(f"Main Ingredient: {main_ingredient}")
    print(f"Side Dish: {side_dish}")
```

📣 Call your function with two different combinations of ingredients.

</div> 

### PART C: Functions with Arguments and Return

<div class="task" markdown="block">

Define a function that **returns a string** representing a combined dish.

```python
# Function that returns a final dish name
def make_dish(ingredient1, ingredient2):
    return f"{ingredient1} and {ingredient2} Surprise!"
```

📣 Call the function and store the result in a **variable**, then print the result using `print()`.

</div> 

---

### PART D: Functions with Optional Arguments

<div class="task" markdown="block">

Define a function that makes a recipe with a **default spice** unless the user specifies one.

```python
# Define a function with a default argument
def add_spice(dish, spice="paprika"):
    print(f"Adding a dash of {spice} to the {dish}. Yum!")
```

📣 Call it once **with** the spice and once **without** the spice.

</div> 

---

### PART E: Review Challenge

<div class="task" markdown="block">

Write a `cook_recipe()` function that calls 3 or more of your previous functions in the correct order to simulate making a dish from start to finish.

_Example idea:_
```python
def cook_recipe():
    welcome_message()
    boil_water()
    list_ingredients("Pasta", "Garlic Bread")
    dish = make_dish("Pasta", "Tomato Sauce")
    print("Dish created:", dish)
    add_spice(dish)
```

📣 Then, call `cook_recipe()` at the end of your script to run the full simulation.

</div> 

---

## 💿 ACTIVITY #2: Data Collection Drills

In this activity you will practice working with the 4 built-in data collections: `Lists`, `Tuples`, `Sets`, and `Dictionaries`. 

Great call! Adding reflection questions with comments deepens understanding and reinforces good habits. Here's the updated version with those prompts woven into the drills:

---

## 💿 ACTIVITY #2: Data Collection Drills

In this activity, you’ll practice your skills with the 4 built-in data collections: `Lists`, `Tuples`, `Sets`, and `Dictionaries`.

Each **drill** is short and focused. **TYPE the code**, **RUN it**, and then **record your observations as comments** (`#`) in your program. 

---

### PART A: Lists

Lists are **ordered**, **changeable** collections. 

<div class="task" markdown="block">

1. Create a list of letters:

```python
my_list = ["h", "e", "l", "l", "o"]
```

1. Print the list to check it:

```python
print(my_list)
# What do you see? Record it here:
```

1. Add an exclamation mark to the end:

```python
my_list.append("!")
```

1. Print the list again:

```python
print(my_list)
# What changed? Describe the difference between the original and updated list:
```

1. How many items are in the list?

```python
print(len(my_list))
# How many elements are there? Record it:
```

1. Get the last two items using positive indexes:

```python
print(my_list[4:6])
# What values were returned? Why do those indexes work?
```

1. Try slicing from index 4 to the end:

```python
print(my_list[4:])
# What do you notice? Is the result the same as above?
```

1. Now try negative indexing:

```python
print(my_list[-2:])
# What does this do? Why is it useful?
```

1. Remove the first `"l"`:

```python
my_list.remove("l")
print(my_list)
# What changed? Where did it remove the "l" from?
```

1. Put it back at index 2:

```python
my_list.insert(2, "l")
print(my_list)
# Did it go where you expected? What is at index 2 now?
```

1. Delete the first element:

```python
del my_list[0]
print(my_list)
# What item got removed?
```

1. Remove and save the last item:

```python
last_item = my_list.pop()
print(last_item)
print(my_list)
# What item was removed? What’s left in the list?
```

1. Print the item at index 2:

```python
print(my_list[2])
# What is it?
```

1. Check if `"!"` is in the list:

```python
print("!" in my_list)
# True or False? Why?
```

1. Sort the list in reverse order:

```python
my_list.sort(reverse=True)
print(my_list)
# What is the new order? Did sort() return anything?
```

1. Create a sorted copy without changing the original:

```python
print(sorted(my_list))
print(my_list)
# Did the original change? What’s the difference between sorted() and sort()?
```

</div>

### PART B: Tuples

Tuples are like lists, but **immutable** — once created, they **can’t be changed**.

<div class="task" markdown="block">

1. Create a simple tuple:

```python
my_tuple = ("red", "green", "blue")
print(my_tuple)
# What values are inside this tuple?
```

1. Access individual items:

```python
print(my_tuple[0])
print(my_tuple[-1])
# What was printed in each case? Why does negative indexing work?
```

1. Try to change a value:

```python
my_tuple[1] = "yellow"
# What happens? What error do you get?
```

1. Create a single-item tuple:

```python
one_item = ("hello",)
print(one_item)
# What do you notice about the syntax?
```

1. Count how many times an item appears:

```python
colors = ("red", "blue", "red", "green", "red")
print(colors.count("red"))
# How many "red" entries are there?
```

1. Find the index of the first match:

```python
print(colors.index("green"))
# What position is "green" in the tuple?
```

</div>


### PART C: Sets

Sets are **unordered** collections that only keep **unique values**.

<div class="task" markdown="block">

1. Make a set:

```python
my_set = {"apple", "banana", "cherry"}
print(my_set)
# Does the order match what you typed? Why or why not?
```

1. Add a new item:

```python
my_set.add("orange")
print(my_set)
# What changed?
```

1. Try adding a duplicate:

```python
my_set.add("banana")
print(my_set)
# Did anything change? Why or why not?
```

1. Remove an item:

```python
my_set.remove("apple")
print(my_set)
# Which item is gone?
```

1. Use `discard()` instead of `remove()`:

```python
my_set.discard("pear")
# What happened? Was there an error?
```

1. Combine sets:

```python
tropical = {"banana", "mango", "papaya"}
all_fruits = my_set.union(tropical)
print(all_fruits)
# What items are in the result? Any duplicates?
```

</div>

### PART D: Dictionaries

Dictionaries store data in **key-value pairs** — think of them like labeled containers.

<div class="task" markdown="block">

1. Make a dictionary:

```python
my_dict = {"name": "Sam", "age": 16, "grade": "11th"}
print(my_dict)
# What keys and values are present?
```

1. Get a value using its key:

```python
print(my_dict["age"])
# What value did this return?
```

1. Try accessing a missing key:

```python
print(my_dict["school"])
# What error do you get?
```

1. Change the grade:

```python
my_dict["grade"] = "12th"
print(my_dict)
# Did the value update?
```

1. Add a new key-value pair:

```python
my_dict["school"] = "Central High"
print(my_dict)
# What’s the new key and value?
```

1. Remove a key:

```python
del my_dict["age"]
print(my_dict)
# Which key is missing now?
```

1. Use `.get()` to safely access a key:

```python
print(my_dict.get("locker"))
# What value was returned? Was there an error?
```

1. Loop through keys and values:

```python
for key, value in my_dict.items():
    print(key, "->", value)
# What got printed? How does this help you read the dictionary?
```

</div>

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [LearnPython - Nina Zakharenko](https://www.learnpython.dev/).
{: .fs-2 }


