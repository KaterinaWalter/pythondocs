---
layout: project
title: "💻 Project #4"
projectname: "Full-Stack C.R.U.D. App"
parent: "3️⃣ Flask Web Apps"
nav_order: 5
---

### Project Overview

This project will help you practice **full-stack development** using `Flask` and `SQLAlchemy`, while allowing you to explore a topic that interests you. Choose a theme, be creative, and have fun! 🚀

<html>
  <details>
    <summary>💻 <strong class="text-green-200">PROJECT PROGRAM SETUP INSTRUCTIONS</strong></summary>
    
<div class="setup" markdown="block">

1. Go to the public template **repository** for our class: [BWL-CS Python Template](https://github.com/BWL-CS/python-template)
2. Click the <button type="button" name="button" class="btn btn-green">Use this template</button> button above the list of files then select `Create a new repository`
3. Specify the **repository name**: `CS3-Project-CRUD`
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

### Project Instructions

#### 1. Choose a Theme
Pick a theme for your app that excites you! Your app should **store, display, and modify data** from an SQLite database. _Examples:_

- **Shopping List App**: A shopping list app where users can add, edit, and delete items.
- **Event Planner**: A portal for creating and sharing social plans with friends.
- **Library System**: A database of books with borrowing and returning functionality.
- **Movie Collection**: A catalog where users can add, rate, and review movies.
- **Recipe Manager**: A site where users can create, update, and delete recipes.
- **Fantasy World Explorer**: A site where users create and manage characters, locations, or quests.

#### 2. Set Up Your Flask App
- **App Structure**: Organize your app into the following folders and files:
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
    ```

- **Install Dependencies**:
   ```bash
   pip install flask flask-sqlalchemy
   ```

#### 3. Database Setup
- **Define a database model** in `app.py` using `Flask-SQLAlchemy`.
- Include at least **three fields** (e.g., `id`, `name`, `date_created`).
- _Example:_
   ```python
   from flask_sqlalchemy import SQLAlchemy
   from datetime import datetime, timezone

   db = SQLAlchemy()

   class Task(db.Model):
       id = db.Column(db.Integer, primary_key=True)
       content = db.Column(db.String(200), nullable=False)
       date_created = db.Column(db.DateTime, default=datetime.utcnow)
   ```

#### 4. Implement CRUD Operations

Your app must support the **Create, Read, Update, and Delete** operations. _Below are the required features:_

##### CREATE (Add Data)
- Use an HTML `<form>` to **submit data**.
- **Store** the data in an `SQLite` database.
- _Example:_
   ```python
   @app.route('/', methods=['POST'])
   def add_task():
       task_content = request.form['content']
       new_task = Task(content=task_content)
       db.session.add(new_task)
       db.session.commit()
   ```

##### READ (View Data)
- **Fetch** records from the database and **display** them using a `Jinja` template.
- _Example:_
   ```python
   @app.route('/')
   def index():
       tasks = Task.query.order_by(Task.date_created).all()
       return render_template('index.html', tasks=tasks)
   ```

##### UPDATE (Modify Data)
- Provide an option to **edit** existing records.
- _Example:_
   ```python
   @app.route('/update/<int:id>', methods=['GET', 'POST'])
   def update(id):
       task = Task.query.get_or_404(id)
       if request.method == 'POST':
           task.content = request.form['content']
           db.session.commit()
           return redirect('/')
       return render_template('update.html', task=task)
   ```

##### DELETE (Remove Data)
- Implement a **delete button** to remove entries.
- _Example:_
   ```python
   @app.route('/delete/<int:id>')
   def delete(id):
       task_to_delete = Task.query.get_or_404(id)
       db.session.delete(task_to_delete)
       db.session.commit()
       return redirect('/')
   ```

#### 5. Create HTML Templates
- Use [Jinja](https://jinja.palletsprojects.com/en/stable/) to dynamically display data.
- Extend a base template (`layout.html`) for consistent navigation.
- *Example:* `index.html`
  ```html
  {% raw %}
  {% extends "layout.html" %}
  
  {% block content %}
  <h2>Task List</h2>
  <ul>
      {% for task in tasks %}
      <li>{{ task.content }} - <a href="/update/{{task.id}}">Edit</a> | <a href="/delete/{{task.id}}">Delete</a></li>
      {% endfor %}
  </ul>
  
  <form action="/" method="POST">
      <input type="text" name="content" required>
      <button type="submit">Add Task</button>
  </form>
  {% endblock %}
  {% endraw %}
  ```

#### 6. Style Your App
- **CSS**: Create a `static/style.css` file for styling.
- **Bootstrap (Optional)**: Use [Bootstrap](https://getbootstrap.com/docs/5.3/getting-started/introduction/) for a responsive UI.
- **Images/Icons**: Store visuals in the `static` folder.

#### 7. Serve Your App
Run your Flask app:
  ```bash
  python app.py
  ```
If using Flask’s built-in development server:
  ```python
  if __name__ == "__main__":
      with app.app_context():
          db.create_all()
      app.run(debug=True)
  ```

---

### Minimum Requirements
- [ ] At least **three HTML pages** extending a base template.  
- [ ] A **Flask-SQLAlchemy database** with at least **one model**.  
- [ ] **CRUD functionality** (Create, Read, Update, Delete).  
- [ ] A **form** to add records.  
- [ ] A **delete button** to remove records.  
- [ ] Styling using **CSS** or **Bootstrap**.  
- [ ] At least **one image** in the `static` folder.  
- [ ] Use of **template inheritance** and Jinja control structures.  

---

### Bonus Challenges
- 🎯 Add **user authentication** (login/logout).  
- 🎯 Use `JavaScript` for **live updates** or **form validation**.  
- 🎯 Add a **REST API endpoint** returning `JSON` data.  
- 🎯 Use Flask’s `flash` messages for user feedback.  
