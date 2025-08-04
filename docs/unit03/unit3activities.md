---
layout: notes
title: "🎯 Unit 3 Activities" 
parent: "3️⃣ Flask Web Apps"
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
3. Specify the **repository name**: `CS3-Unit3-Activity#`
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

## Flask Web App

For your project, you will create a **custom Flask web application** that demonstrates your mastery of Flask, Jinja templates, and the concepts covered in the tutorial. The project is intentionally open-ended to encourage creativity. Choose a theme that interests you and build an app that is interactive, visually appealing, and functional.

#### Project Goal
Design and develop a **themed Flask web application** with at least **three interconnected pages**, using templates, routing, static files, and basic control structures. The app should showcase your skills in creating a dynamic and engaging user experience.

---

### Project Instructions

#### 1. Choose a Theme
Pick a theme for your app that excites you! _Examples:_
- **Interactive Museum**: A virtual tour showcasing exhibits with descriptions and images.
- **Game Hub**: A hub featuring game stats, leaderboards, or interactive minigames.
- **Fantasy World Explorer**: A site where users can "travel" to different realms, each with unique features.
- **Adventure Guide**: A site with a map of fictional destinations. Each destination page dynamically displays weather, activities, and history.
- **Recipe Book**: A site with recipes and an interactive ingredient search.
- **Music Library**: A site where users can explore albums or songs, complete with audio previews.

#### 2. Create Your Flask App
1. **App Structure**: Organize your app into the following folders and files:
    ```
    project/
    ├── static/
    │   ├── style.css
    │   ├── script.js
    │   └── (images, additional assets)
    ├── templates/
    │   ├── layout.html
    │   ├── (your HTML pages)
    ├── app.py
    └── data.json (optional)
    ```

2. **Routes**:
   - Create routes for at least **three pages**, such as:
     - A **home page** introducing your theme.
     - An **interactive page** where users can input or interact with content.
     - A **customized page** that changes dynamically (e.g., based on URL parameters or user input).

3. **Templates**:
   - Use **template inheritance** to create a shared base layout (e.g., `layout.html`).
   - Include navigation links to all pages.
   - Use Jinja placeholders and control structures for dynamic content.

#### 3. Add Styling and Interactivity
- **CSS**: Style your app to match the theme using custom CSS in the `static/style.css` file.
- **JavaScript** (optional): Add simple interactivity, like a button that displays a message or a dynamic clock.
- **Images and Icons**: Add images or icons in the `static` folder for visual appeal.

#### 4. Showcase Flask Features
Incorporate the following features:
- **Dynamic Data**: Use variables, URL parameters, or data from a JSON file to populate your pages.
- **Control Structures**: Use `if` statements, loops, or conditions in your templates.
- **Static Files**: Include at least one custom CSS file and one image.
- **API Endpoint**: Create a route that serves a JSON response.

### Minimum Requirements
1. **Pages**: A minimum of three HTML pages, extending a base template.
2. **Dynamic Content**:
   - At least one page must dynamically change based on input or URL parameters.
   - Use a JSON file or dictionary for a collection of data.
3. **Styling**: A custom CSS file to style your pages.
5. **Static Files**: Use at least one image and one stylesheet.
6. **Documentation**: Include comments in your code explaining key sections.

### Bonus Challenges
- Use HTML **forms** to gather user input. 
- Add **user authentication** (e.g., login/logout with dummy data).
- Incorporate **JavaScript** to enhance interactivity.
- Use Flask's `flash` or `session` for notifications or user session data.
- Implement a basic database with `Flask-SQLAlchemy`.

---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from []().
{: .fs-2 }
