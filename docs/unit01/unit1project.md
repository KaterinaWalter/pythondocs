---
layout: project
title: "💻 Unit 1 Project"
projectname: "Trivia Quiz App"
parent: "1️⃣ Python Bootcamp"
nav_order: 6
---

### Project Overview

In this project, students will demonstrate understanding of Python programming basics, including variables, data types, functions, loops, conditionals, dictionaries, and lists, by creating an interactive quiz. The quiz should take input from the user, process that input, and provide appropriate feedback based on the user’s responses.

- **Project Goal:** Develop an interactive trivia quiz in Python that tests the user’s knowledge on a topic of your choice (e.g., general knowledge, mathematics, history, etc.).
- You are encouraged to be creative with the quiz topics and question types.
- Testing your program thoroughly before submission is crucial to ensure it handles different inputs and scenarios effectively.
- Collaboration with classmates is allowed, but each student must submit their unique quiz project.

<html>
  <details>
    <summary>📥 <strong class="text-green-200">PROJECT SETUP & SUBMISSION INSTRUCTIONS</strong></summary>
    
<div class="setup" markdown="block">

1. Go to the `CS3 Unit 1 Project` assignment on **Blackbaud** and follow the provided **GitHub Classroom** link.
  > 📁 Clicking the link generates a **private repository** for your project with the appropriate starter code. Note that **projects** are stored within the [BWL-CS Organization](https://github.com/BWL-CS), so you _cannot_ access it from the "Your Repositories" page!
2. Open the repository in a **Codespace** whenever you spend time working on the program, in class or at home. 
  > ⚠️ Always remember to `commit changes` after every coding session!
3. When your project is complete, **submit the link to your repository** in the `CS3 Unit 1 Project` assignment on Blackbaud.

</div>

</details>
</html>

---

### Instructions & Requirements

<div class="task" markdown="block">

#### Project Specifications
- **Trivia Questions:** The quiz should have a minimum of _10 multiple-choice_ questions. The program should evaluate the user’s responses and provide overall feedback on their performance at the end of the quiz.
- **Main Program:** The main program should initialize the quiz, call the necessary functions, and handle the quiz’s overall flow.
- **User Interaction:** Ensure the quiz is interactive by taking user input (`choice = input(question)`) and providing immediate feedback after each question.
- **Scoring:** Implement a scoring system that tracks the user’s correct answers and displays the final score at the end.
- **Error Handling:** Include basic error handling for user inputs (e.g., ensuring the user selects a valid option for multiple-choice questions).

#### Core Python Concepts to Implement
- **Variables:** Use variables to store user inputs, scores, and other relevant data.
- **Data Types:** Implement different data types, including `strings`, `integers`, `lists`, and `dictionaries`, to manage quiz questions, answers, and user data.
  - Use a `list` to store all the question objects. 
  - Inside the list, create a `dictionary` to store the body of each question, the correct choice, and its corresponding possible answers. Each question object should be its own dictionary, within the overall list collection.
 
```python
trivia = [
          { 'question': "question body goes here",
            'answer': 'correct answer',
            'options': ['option a', 'option b', 'option c', 'correct answer'],
          },
          { 'question': "question body goes here",
            'answer': 'correct answer',
            'options': ['option a', 'option b', 'option c', 'correct answer'],
          }
         ]
```

- **Functions:** Write at least two functions:
  - `ask_question(question, options, answer)` displays the question and options, takes user input, checks if the answer is correct, and **returns** a `boolean` value indicating correctness.
  - `calculate_score(total_questions, num_correct)` calculates and returns the user’s score as a percentage.
- **Loops:** Use loops to iterate through the questions stored in the list and handle repeated tasks (e.g., displaying questions, capturing responses).
- **Conditionals:** Implement conditionals to check if the user’s response is correct and update the score accordingly.

#### Bonus Challenges (Optional)
- **Randomized Questions:** Randomize the order of the questions each time the quiz is run.
- **Timed Quiz:** Implement a timer for each question, giving the user a limited amount of time to answer.
- **High Scores:** Add functionality to save and display the highest score achieved by any user.


</div> 


