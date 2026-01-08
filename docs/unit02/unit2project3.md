---
layout: project
title: "💻 Project #3"
projectname: "Exploratory Data Analysis"
parent: "2️⃣ Data Science"
nav_order: 9
---

### Project Overview

This is a cumulative project focusing on **Exploratory Data Analysis (EDA)** using Python's `pandas`, `matplotlib`, and `seaborn` libraries. The project aims to demonstrate skills in data wrangling, visualization, and communication of findings through a scientific conference-style poster. You will work with a large, real-world dataset of your choice to perform EDA.

The long-term project consists of THREE main deliverables:

1. A descriptive **markdown** text file
2. A **python** code script
3. An academic conference-style **poster** 
> 📰 Make a copy of this [Google Slide Template](https://docs.google.com/presentation/d/1IkrIYBNTEBLFIO7kqUJWvrWhzRuiYhXyX7lxNZglkpU/edit?usp=sharing) for the poster!

<html>
  <details>
    <summary>💻 <strong class="text-green-200">PROJECT PROGRAM SETUP INSTRUCTIONS</strong></summary>
    
<div class="setup" markdown="block">

1. Go to the public template **repository** for our class: [BWL-CS Python Template](https://github.com/BWL-CS/python-template)
2. Click the <button type="button" name="button" class="btn btn-green">Use this template</button> button above the list of files then select `Create a new repository`
3. Specify the **repository name**: `CS3-Project-EDA`
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

### Instructions & Requirements

#### Dataset Sources:
- [Kaggle](https://www.kaggle.com/)
- [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/index.php)
- [Data.gov](https://www.data.gov/)

#### ① Markdown file:

- [ ] **Dataset**:
  - Provide a _link_ to the dataset you chose. 
    > In `markdown` syntax, you can format links like this: `[Link text](Link address)` 
- [ ] **Column Descriptions**:
  - Write a brief description of each column in your dataset. Include data types and potential values.
- [ ] **Hypotheses/Questions**:
  - List at least 5 questions you want to explore using your dataset. 
    > _Is there a correlation between two variables?_
    > _How do values in a specific column change over time or categories?_
- [ ] **Visualization Plan**:
  - Explain how you will use visualizations to test your hypotheses. Include the type of chart you plan to use for each question.
     
{:.highlight}
💡 Choosing the right type of visualization is crucial for effectively **exploring** your dataset and **communicating** your findings. Try this <a href="https://www.data-to-viz.com/"><button class="btn btn-primary">Data Viz Decision Tree</button></a> tool to help you pick a chart based on your data! 

#### ② Python script:

Your `main.py` script should be well-organized and demonstrate that you performed meaningful data analysis and generated diverse visualizations.

- [ ] **Load & process the dataset**
  - Handle missing values.
  - Rename columns if necessary for clarity.
  - Convert data types if needed.
  - Filter and/or group data for focused analysis.
- [ ] Contain code for at least **4 different types of visualizations**
  - Ensure each visualization is well-labeled with titles, axis labels, and legends.
  - Visualizations should be clear, informative, and **appropriate for the data**.
  > See the [Example Graph Gallery](https://python-graph-gallery.com/) for inspiration.
- [ ] Be thoroughly **commented**
  - Explain the purpose of each section of the code.
  - Use functions for reusable components of your code.

#### ③ Poster: 

A scientific poster for an academic conference must effectively communicate **key findings**. All captions and text should be concise and relevant.
  
- [ ] **Introduction**
  - Context for the dataset and why it is interesting/relevant.
  - Clearly state your research questions or hypotheses.
- [ ] **Methods**
  - Describe your process for cleaning and analyzing the data.
  - Include screenshots of key Python code snippets.
- [ ] **Results**
  - Present 2–3 visualizations from your analysis.
  - Provide clear captions for each figure.
- [ ] **Discussion**
  - Interpret your findings and discuss patterns or trends observed in the data.
  - Mention any limitations of your analysis.
- [ ] **Conclusions**
  - Summarize key takeaways.
  - Suggest potential areas for future research or data exploration.
- [ ] **References**
  - Cite the dataset and any external resources
  > 📚 Conduct _research_ on the topic to enhance your poster's **Introduction** and/or **Discussion** sections!

