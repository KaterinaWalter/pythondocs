---
layout: notes
title: "📓2.1: Pandas DataFrames" 
parent: "2️⃣ Data Science"
nav_order: 1
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

<div style="text-align: center;">
<span class="highlighter-green"> 
<strong>✴✴✴ NEW UNIT/SECTION! ✴✴✴</strong><br>Create a blank Python program to take your class notes in for the next few lessons.<br><em>Click on the collapsed heading below for GitHub instructions</em> ⤵  
</span>
</div>

<html>
  <details>
    <summary>📓 <strong class="text-green-200">NOTES PROGRAM SETUP INSTRUCTIONS</strong></summary>
    
<div class="setup" markdown="block">

1. Go to the public template **repository** for our class: [BWL-CS Python Template](https://github.com/BWL-CS/python-template)
2. Click the <button type="button" name="button" class="btn btn-green">Use this template</button> button above the list of files then select `Create a new repository`
3. Specify the **repository name**: `CS3-Unit2-Notes`
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

---

## What is Data Science? 🧪

<html>
<dl>
  <dt>Data Science</dt>
  <dd>An emerging, interdisciplinary field that brings together ideas that have been around for years, or even centuries about processes and systems to <strong>extract knowledge</strong> and/or to <strong>make predictions</strong> from data in various forms.
  </dd>
</dl>
</html>

In 2016 a study reported that [90% of the data in the world today has been created in the last two years alone](http://www.iflscience.com/technology/how-much-data-does-the-world-generate-every-minute).
This is the result of the _continuing acceleration of the rate_ at which we store
data. Some estimates indicate that roughly 2.5 quintillion bytes of data are
generated per day; that's 2,500,000,000,000,000,000 bytes! 
> By comparison, all the data in the Library of Congress adds up to about 200 TB, merely 200,000,000,000,000 bytes. This means that we are capturing _12,500 libraries of congress per day_!

The amount of data that Google alone stores in its servers is estimated to be 15 exabytes (15 followed by 18 zeros!). You can visualize 15 exabytes as a [pile of cards three miles high](https://what-if.xkcd.com/63/), covering all of New England. 

Everywhere you go, someone or something is collecting data about you: what you buy, what you read, where you eat, where you stay, how and when you travel, and so much more. By 2025, it is estimated that 463 exabytes of data will be created each day globally, and the entire digital universe is expected to reach 44 zettabytes by 2020. [This would mean there would be 40 times more bytes than there are stars in the observable universe](https://www.visualcapitalist.com/how-much-data-is-generated-each-day/)!

Often, this data is collected and stored with _little idea about how to use it_, because technology makes it so easy to capture. Other times, the data is collected quite intentionally. The big question is: **what does it all mean?** That's where data science comes in. 

### What does a data scientist do?

<a href="https://www.youtube.com/watch?v=X3paOmcrTjQ"><button class="btn btn-purple">📺 VIDEO: Data Science in 5 Minutes</button></a>

As an interdisciplinary field of inquiry, data science is perfect for a liberal arts college as well as many other types of universities.
Combining statistics, computer science, writing, art, and ethics, data science has application across the entire curriculum:  biology, economics, management, English, history, music, pretty much everything. The best thing about data science is that the job of a data scientist seems perfectly suited to many liberal arts students.

{:.highlight}
"The best data scientists have one thing in common: **unbelievable curiosity**." - D.J. Patil, *Chief Data Scientist of the United States from 2015 to 2017*.

![image](https://static1.squarespace.com/static/5150aec6e4b0e340ec52710a/t/51525c33e4b0b3e0d10f77ab/1364352052403/Data_Science_VD.png?format=1500w)

> The diagram above is widely used to answer the question "What is Data Science?" It also is a great illustration of the **liberal arts** nature of data science. Some computer science, some statistics, and something from one of the many majors available at a liberal arts college, all of which are looking for people with data skills!

---

## Data Manipulation with Pandas 🐼

![image](https://miro.medium.com/max/800/1*9PJob-rUG-_m5hbqsaQ2Ig.jpeg)

### From NumPy to Pandas

**NumPy** is a Python library centered around the `ndarray` object, which enables efficient storage and manipulation of dense typed arrays. **Pandas** is a newer package built on top of **NumPy** that provides an efficient implementation of a `DataFrame`, which is the main data structure offered by Pandas. 
> **NumPy**'s limitations become clear when we need more flexibility (e.g., attaching labels to data, working with missing data, etc.) and when attempting operations that do not map well to element-wise broadcasting (e.g., groupings, pivots, etc.), each of which is an important piece of analyzing the less structured data available in many forms in the world around us.

<html>
<dl>
  <dt>DataFrame</dt>
  <dd>A multidimensional array object with attached <code>row</code> and <code>column</code> labels, often containing heterogeneous types and/or missing data. The concept is similar to a <strong>spreadsheet</strong> in Excel or Google Sheets, but more versatile.</dd>
</dl>
</html>

As well as offering a convenient storage interface for labeled data, Pandas implements a number of powerful **data operations** familiar to users of both database frameworks and spreadsheet programs. Pandas, and in particular its `Series` and `DataFrame` objects, builds on the NumPy array structure and provides efficient access to these sorts of "data munging" tasks that occupy much of a data scientist's time.

As we will see during the course of this chapter, Pandas provides a host of useful tools, methods, and functionality on top of the basic data structures, but nearly everything that follows will require an understanding of what these structures are.
Thus, before we go any further, let's take a look at these three fundamental Pandas data structures: the `Series`, `DataFrame`, and `Index`.

We will start our code sessions with the standard NumPy and Pandas **imports**, under the aliases `np` and `pd`:

```python
import numpy as np
import pandas as pd
```

---

## Pandas Objects

### The `Series` Object

<html>
<dl>
  <dt>Series</dt>
  <dd>A one-dimensional array object of indexed data.</dd>
</dl>
</html>

A `Series` object can be created from a `list` or array as follows:

```python
data = pd.Series([0.25, 0.5, 0.75, 1.0])
```

The `Series` combines a sequence of **values** with an explicit sequence of **indices**, which we can access with the `values` and `index` attributes. The `values` are simply a NumPy array:
```python
data.values
```

The `index` is an array-like object of type `pd.Index`, which we'll discuss in more detail momentarily:
```python
data.index
```

Like with a NumPy array, data can be accessed by the associated index via the familiar Python square-bracket notation:

```python
data[1]
data[1:3]
```

As we will see, though, the Pandas `Series` is much more general and flexible than the one-dimensional NumPy array that it emulates.

#### Series as Generalized NumPy Array
{:.no_toc}

From what we've seen so far, the `Series` object may appear to be basically interchangeable with a one-dimensional NumPy array. The essential difference is that while the NumPy array has an *implicitly defined* integer index used to access the values, the Pandas `Series` has an *explicitly defined* index associated with the values.

This explicit index definition gives the `Series` object additional capabilities. For example, the index need not be an integer, but can consist of values of any desired type.
So, if we wish, we can use strings as an index:

```python
data = pd.Series([0.25, 0.5, 0.75, 1.0],
                 index=['a', 'b', 'c', 'd'])
print(data)
```

And the item access works as expected:

```python
print(data['b'])
```

We can even use noncontiguous or nonsequential indices:

```python
data = pd.Series([0.25, 0.5, 0.75, 1.0],
                 index=[2, 5, 3, 7])
print(data)
print(data[5])
```

#### Series as Specialized Dictionary
{:.no_toc}

In this way, you can think of a Pandas `Series` a bit like a specialization of a Python dictionary.
A dictionary is a structure that maps arbitrary keys to a set of arbitrary values, and a `Series` is a structure that maps typed keys to a set of typed values.
This typing is important: just as the type-specific compiled code behind a NumPy array makes it more efficient than a Python list for certain operations, the type information of a Pandas `Series` makes it more efficient than Python dictionaries for certain operations.

The `Series`-as-dictionary analogy can be made even more clear by constructing a `Series` object directly from a Python dictionary, here the five most populous US states according to the 2020 census:

```python
population_dict = {'California': 39538223, 'Texas': 29145505,
                   'Florida': 21538187, 'New York': 20201249,
                   'Pennsylvania': 13002700}
population = pd.Series(population_dict)
```

From here, typical dictionary-style item access can be performed:

```python
print(population['California'])
```

Unlike a dictionary, though, the `Series` also supports array-style operations such as slicing:

```python
print(population['California':'Florida'])
```

#### Constructing Series Objects
{:.no_toc}

We've already seen a few ways of constructing a Pandas `Series` from scratch. All of them are some version of the following:

```python
pd.Series(data, index=index)
```
where `index` is an optional argument, and `data` can be one of many entities.

For example, `data` can be a list or NumPy array, in which case `index` defaults to an integer sequence:

```python
pd.Series([2, 4, 6])
```

Or `data` can be a scalar, which is repeated to fill the specified index:

```python
pd.Series(5, index=[100, 200, 300])
```

Or it can be a dictionary, in which case `index` defaults to the dictionary keys:

```python
pd.Series({2:'a', 1:'b', 3:'c'})
```

In each case, the index can be explicitly set to control the order or the subset of keys used:

```python
pd.Series({2:'a', 1:'b', 3:'c'}, index=[1, 2])
```

### The Pandas `DataFrame` Object

The next fundamental structure in Pandas is the `DataFrame`. Like the `Series` object discussed in the previous section, the `DataFrame` can be thought of either as a generalization of a NumPy array, or as a specialization of a Python dictionary. Since we didn't spend time on NumPy arrays, we'll focus on the concept of a **DataFrame as a specialized dictionary**.

#### DataFrame as Specialized Dictionary
{:.no_toc}

Where a dictionary maps a key to a value, a `DataFrame` maps a column name to a `Series` of column data.
For example, asking for the `'area'` attribute returns the `Series` object containing the areas we saw earlier:

```python
print(states['area'])
```

### Constructing DataFrame Objects
{:.no_toc}

A Pandas `DataFrame` can be constructed in a variety of ways.
Here we'll explore several examples.

#### From a single Series object
{:.no_toc}

A `DataFrame` is a collection of `Series` objects, and a single-column `DataFrame` can be constructed from a single `Series`:

```python
pd.DataFrame(population, columns=['population'])
```

#### From a list of dicts
{:.no_toc}

Any list of dictionaries can be made into a `DataFrame`. Even if some keys in the dictionary are missing, Pandas will fill them in with `NaN` values (i.e., "Not a Number")

We'll use a simple list comprehension to create some data:


```python
data = [{'a': i, 'b': 2 * i}
        for i in range(3)]
pd.DataFrame(data)
```

#### From a dictionary of Series objects
{:.no_toc}

As we saw before, a `DataFrame` can be constructed from a dictionary of `Series` objects as well:


```python
pd.DataFrame({'population': population,
              'area': area})
```

---

## Helpful `DataFrame` Operations

<div class="task" markdown="block">
 
1. Download this [Pokemon Dataset](https://github.com/katerinanavab/pokemon-pandas-tutorial/blob/master/pokemon_data.csv) CSV file to use while we learn `Pandas` operations.
2. Upload it to your `Unit-2-Notes` repository.
3. Load data from the CSV file into a `DataFrame`:
```python
pokemon = pd.read_csv('pokemon_data.csv')
```
4. Check out the DataFrame:
```python
print(pokemon)
print(pokemon.columns)
```
</div>

### Selecting Columns in DataFrames

Recall that a `DataFrame` acts in many ways like a two-dimensional _array_, and in other ways like a _dictionary_ of `Series` structures sharing the same **index**. These analogies can be helpful to keep in mind as we explore **data selection** within this structure.

#### DataFrame as Dictionary
{:.no_toc}

The first analogy we will consider is the `DataFrame` as a _dictionary_ of related `Series` objects. The individual `Series` that make up the **columns** of the `DataFrame` can be _accessed via dictionary-style indexing_ of the column name:

```python
pokemon['Type 1']
```

Equivalently, we can use _attribute-style access_ with simple string column names:

```python
pokemon.HP
```

{:.warning}
Though this is a useful shorthand, keep in mind that it does not work for all cases!
_For example:_ if the column names include whitespace (like `'Type 1'`), are not strings, or if the column names conflict with methods of the `DataFrame`, this **attribute-style access** is not possible.

Like with the `Series` objects discussed earlier, this dictionary-style syntax can also be used to **modify** the object, in this case _adding a new column_:

```python
# Compute ratio of Attack stat to Special Attack stat
pokemon['Attack Ratio'] = pokemon['Attack'] / pokemon['Sp. Atk']
```

### Viewing Data & Basic Statistics

***Attributes:***
* `df.shape` - tuple of (rows, columns)
* `df.columns` - list of column names
* `df.index` - row index info
* `df.dtypes` - data type of each column

***Functions:***
* `df.head(n)` - show first _n_ rows (default 5)
* `df.tail(n)` - show last _n_ rows (default 5)
* `df.sample(n)` - show random sample of _n_ rows
* `df.info()` - summary of columns, non-null counts, data types
* `df.describe()` - numeric summary (mean, std, min, max)
* `df.describe(include='all')` - includes non-numeric columns
* `df.count()` - number of non-null values per column
* `df['col'].value_counts()` - frequency counts for values in a column
* `df.sort_values('col')[:10]` - top 10 after sorting
* `df.nlargest(5, 'col')` - 5 largest values in col
* `df.nsmallest(5, 'col')` - 5 smallest values in col

#### Aggregation with `.groupby`

* Average stats by primary type:
  ```python
  df.groupby('Type 1')[['Attack', 'Defense', 'Speed']].mean()
  ```
  > **Output:** Shows mean Attack, Defense, and Speed for each Pokémon type (e.g., Fire, Water, Grass).

* Count of Pokémon by type:
  ```python
  df.groupby('Type 1').size().sort_values(ascending=False)
  ```
  > **Output:** Number of Pokémon per primary type, sorted from most to least common.

* Average total stats by generation:
  ```python
  df['Total'] = df[['HP', 'Attack', 'Defense', 'Speed']].sum(axis=1)
  df.groupby('Generation')['Total'].mean()
  ```
  > **Output:** Average combined stats per generation.

* Compare legendary vs. non-legendary averages:
  ```python
  df.groupby('Legendary')[['Attack', 'Defense', 'Speed']].mean()
  ```
  > **Output:** two rows, `False` (normal Pokémon) and `True` (legendary), with mean values for each stat.


### Selecting Rows in DataFrames

Recall that a `DataFrame` acts in many ways like a two-dimensional _array_, and in other ways like a _dictionary_ of `Series` structures sharing the same **index**. These analogies can be helpful to keep in mind as we explore **data selection** within this structure.

#### DataFrame as Two-Dimensional Array
{:.no_toc}

As mentioned previously, we can also view the `DataFrame` as an enhanced two-dimensional array.

We can examine the raw underlying data array using the `values` attribute:

```python
pokemon.values
```

#### Indexers: `.loc` & `.iloc`

When it comes to indexing of a `DataFrame` object, Pandas again uses the `loc` and `iloc` indexers mentioned earlier.

* Use `.iloc` when you want to access data by position.
* Use `.loc` when you want to access data by label (e.g., Pokémon names).

Using the `iloc` indexer, we can index the underlying array as if it were a simple NumPy array (using the implicit Python-style index), but the `DataFrame` index and column labels are maintained in the result:

```python
# Read a specific location [R, C]
print(pokemon.iloc[100,1])

# Read several rows
print(pokemon.iloc[25:30])

# Read every row for a certain column
for index, row in pokemon.iterrows():
    print(index, row['Name'])
```

Similarly, using the `loc` indexer we can index the underlying data in an array-like style but using the explicit index and column names:

```python
grass_types = pokemon.loc[pokemon['Type 1'] == "Grass"]
print(grass_types)
```

#### Using `String` Indices

If you modify your DataFrame to use string indices, such as the Pokémon names, you will likely use `.loc` more frequently than `.iloc`. You first need to set the Pokémon names as the index: 

```python
poke = pokemon.set_index('Name', inplace=True)
```

Accessing a specific row and column:

```python
# Example accessing Pikachu's type by name
print(poke.loc['Pikachu', 'Type 1'])
```

To read multiple rows using `.loc`, you need to specify a list of Pokémon names:

```python
# Example accessing a range of Pokémon by their names
print(poke.loc[['Squirtle', 'Bulbasaur', 'Charmander']])
```

When iterating with `.iterrows()`, it automatically provides the index (now Pokémon names) along with the row:
```python
# Iterate through each row, printing Name - Type
for index, row in poke.iterrows():
    print(index, " - ", row['Type 1'])
```

#### Conditional Slicing

---

## ⭐️ Glossary

### Definitions
{:.no_toc}

<html>
<dl>
  <dt>Data Frame</dt>
  <dd>Data frames are multidimensional arrays taken from a larger dataset. 
They are used to implement specific data operations that may not need the entire dataset.
(In pandas it is called <code>DataFrame</code>)
  </dd>
  <dt>Explicit Index</dt>
  <dd>Uses the values (numeric or non-numeric) set as the index.  For example, if we 
set a column or row as the index then we can use values in the row or column as indices in different 
panda methods. 
  </dd>
  <dt>Implicit Index</dt> 
  <dd>Uses the location (numeric) of the indices, similar to the python style of indexing. 
  </dd>
  <dt>Index</dt>
  <dd>An Index is a value that represents a position (address) in the <code>DataFrame</code> or <code>Series</code>. 
  </dd>
  <dt>Series</dt>
  <dd>A series is an array of related data values that share a connecting factor or property.
  </dd>
</dl>
</html>

### Keywords
{:.no_toc}

* ``import``: Import lets programmers use packages, libraries or modules that have already been programmed. 

* ``<DataFrame>[<string>]``: return the series corresponding to the given column (<string>).

* ``<DataFrame>[<list of strings>]``: returns a given set of columns as a ``DataFrame``.

* ``<DataFrame>[<series/list of Boolean>]``: If the index in the given list is ``True`` then it returns the row from that same index in the ``DataFrame``.

* ``<DataFrame>.loc[ ]``: Uses explicit indexing to return a ``DataFrame`` containing those indices and the values associated with them. 

* ``<DataFrame>.loc[<string1>:<string2>]``: This takes in a range of explicit indices and returns a ``DataFrame`` containing those indices and the values associated with them.

* ``<DataFrame>.loc[<string>]``: Uses an explicit index and return the row(s) for that index value.

* ``<DataFrame>.loc[<list/series of strings>]``: Returns a new ``DataFrame`` containing the labels given in the list of strings.

* ``<DataFrame>.iloc[ ]``: Uses implicit indexing to return a ``DataFrame`` containing those indices and the values associated with them.

* ``<DataFrame>.iloc[<index, range of indices>]``: This takes in an implicit index (or a range of implicit indices) and returns a ``DataFrame`` containing those 
indices and the values associated with them.

* ``<DataFrame>.set_index [<string)>]``: Sets an existing column(s) with the <string> name as the index of the ``DataFrame``. 

* ``<DataFrame>.head(<numeric>)``: Returns the first <numeric> element(s). If no parameter (<numeric>) is set then it will return the first five elements. 

* ``<pandas>.DataFrame(<data>)``: Used to create a ``DataFrame`` with the given data.

* ``<pandas>.read_csv()``: Used to read a csv file into a ``DataFrame``.

* ``<DataFrame>.set_index(<column>)``: Gets the values of the given column and sets them as indices. The output will be sorted in accending order based on the new indices.

* ``<pandas>.to_numeric()``: Converts what is inside the parenthesis into neumeric values. 

* ``<series>.str.startswith(<string>)``: ``.str.startswith()`` (in pandas) checks if a series contains a string(s) that starts with the given prarameter (<string>), 
and returns a boolean value (True or False).
 
* ``<data frame>.sort_index()``: Sorts the different objects in the ``DataFrame``. By default, the ``DataFrame`` is sorted based on the first column in accending order.

<br>

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [How to Think Like a Data Scientist on Runestone Academy - Brad Miller, Jacqueline Boggs, and Jan Pearce](https://runestone.academy/ns/books/published/httlads/index.html?mode=browsing) and [Python Data Science Handbook - Jake VanderPlas](https://jakevdp.github.io/PythonDataScienceHandbook/).
{: .fs-2 }
