---
layout: notes
title: "📓2.1: Pandas" 
parent: "2️⃣ Data Science"
nav_order: 1
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---
## What is Data Science?

<dl>
  <dt>Data Science</dt>
  <dd>An emerging, interdisciplinary field that brings together ideas that have been around for years, or even centuries about processes and systems to <strong>extract knowledge</strong> and/or to <strong>make predictions</strong> from data in various forms.</dd>
</dl>

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
"The best data scientists have one thing in common: **unbelievable curiosity**." - D.J. Patil,_ Chief Data Scientist of the United States from 2015 to 2017_.

![image](https://static1.squarespace.com/static/5150aec6e4b0e340ec52710a/t/51525c33e4b0b3e0d10f77ab/1364352052403/Data_Science_VD.png?format=1500w)

> The diagram above is widely used to answer the question "What is Data Science?" It also is a great illustration of the liberal arts nature of data science. Some computer science, some statistics, and something from one of the many majors available at a liberal arts college, all of which are looking for people with data skills!

---

## 🐼 Pandas with Movie Data

Data scientists have to deal with a lot of data at once. While Google Sheets and Excel are great ways to visualize and manipulate data, they are not as _versatile_ as we might want. In this chapter, you will be introduced to **data frames** and learn to use them to obtain information from data.

#### Using a GitHub Template for class notes

<div class="setup" markdown="block">

1. Go to the public template **repository** for our class: [BWL-CS Python Template](https://github.com/BWL-CS/python-template)
2. Click the <button type="button" name="button" class="btn btn-green">Use this template</button> button above the list of files then select `Create a new repository`
3. Specify the **repository name**: `CS3-Unit-2-Pandas`
4. Click <button type="button" name="button" class="btn btn-green">Create repository</button>
    > Now you have **your own personal copy** of this starter code that you can always access under the `Your repositories` section of GitHub! 
5. Now on your repository, click <button type="button" name="button" class="btn btn-green"> < > Code </button> and select the `Codespaces` tab
6. Click `Create Codespace on main` and wait for the environment to load, _then you're ready to code_!
7. 📝 Take notes in this Codespace during class, coding along with the instructor.

</div>
<br>
<div class="warn" markdown="block">

🛑 When class ends, don't forget to **SAVE YOUR WORK**! _There are multiple steps to saving in GitHub:_

1. Navigate to the `Source Control` menu on the _LEFT_ sidebar
2. Click the <button type="button" name="button" class="btn btn-green">commit changes</button> button on the _LEFT_ menu
3. Type a brief **commit message** at the top of the file that opens, for example: `updated main.py`
4. Click the small `✔️` **checkmark** in the _TOP RIGHT_ corner
5. Click the <button type="button" name="button" class="btn btn-green">sync changes</button> button on the _LEFT_ menu
6. _Finally you can close your Codespace!_

</div>

### Exploring the Data


### Filtering the Data

### Numbers as Indices

### Dealing with Multiple DataFrames

---

## ⭐️ Summary

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [How to Think Like a Data Scientist on Runestone Academy - Brad Miller, Jacqueline Boggs, and Jan Pearce](https://runestone.academy/ns/books/published/httlads/index.html?mode=browsing).
{: .fs-2 }
