Sure! Here's a complete **example project** idea that brings together **HTML**, **CSS**, and **JavaScript** in a real-world scenario, with a detailed breakdown of its structure and functionality.

---

# 🌟 **Project Title: Interactive To-Do List App**

---

## ✅ **Project Overview**

Build a web-based **To-Do List App** where users can:
- Add new tasks
- Mark tasks as completed
- Delete tasks
- Filter tasks (All, Active, Completed)
- Persist data using **Local Storage**

This project reinforces the **DOM**, **event handling**, **CSS styling**, and **basic CRUD operations** using JavaScript.

---

## 🗂️ **Project Structure**

```
todo-app/
│
├── index.html
├── style.css
└── script.js
```

---

## 🧱 **1. index.html**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>To-Do List</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <div class="container">
    <h1>📝 To-Do List</h1>
    <form id="task-form">
      <input type="text" id="new-task" placeholder="Add a new task..." required />
      <button type="submit">Add</button>
    </form>

    <ul id="task-list"></ul>

    <div class="filters">
      <button class="filter-btn active" data-filter="all">All</button>
      <button class="filter-btn" data-filter="active">Active</button>
      <button class="filter-btn" data-filter="completed">Completed</button>
    </div>
  </div>

  <script src="script.js"></script>
</body>
</html>
```

---

## 🎨 **2. style.css**

```css
body {
  font-family: sans-serif;
  background: #f7f9fc;
  display: flex;
  justify-content: center;
  padding-top: 50px;
}

.container {
  background: #fff;
  padding: 2rem;
  border-radius: 12px;
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
  width: 350px;
}

h1 {
  text-align: center;
  margin-bottom: 1.5rem;
}

#task-form {
  display: flex;
  gap: 0.5rem;
}

#new-task {
  flex: 1;
  padding: 0.5rem;
}

button {
  padding: 0.5rem 1rem;
  border: none;
  background: #007bff;
  color: white;
  border-radius: 6px;
  cursor: pointer;
}

button:hover {
  background: #0056b3;
}

ul {
  list-style: none;
  padding: 0;
  margin-top: 1rem;
}

li {
  background: #f1f1f1;
  margin-bottom: 0.5rem;
  padding: 0.5rem;
  display: flex;
  justify-content: space-between;
  border-radius: 6px;
}

.completed {
  text-decoration: line-through;
  color: gray;
}

.filters {
  display: flex;
  justify-content: center;
  margin-top: 1rem;
  gap: 10px;
}

.filter-btn.active {
  background: #343a40;
}
```

---

## ⚙️ **3. script.js**

```javascript
const taskForm = document.getElementById('task-form');
const taskInput = document.getElementById('new-task');
const taskList = document.getElementById('task-list');
const filterButtons = document.querySelectorAll('.filter-btn');

let tasks = JSON.parse(localStorage.getItem('tasks')) || [];

function saveTasks() {
  localStorage.setItem('tasks', JSON.stringify(tasks));
}

function renderTasks(filter = 'all') {
  taskList.innerHTML = '';

  tasks
    .filter(task => {
      if (filter === 'active') return !task.completed;
      if (filter === 'completed') return task.completed;
      return true;
    })
    .forEach((task, index) => {
      const li = document.createElement('li');
      li.innerHTML = `
        <span class="${task.completed ? 'completed' : ''}" data-index="${index}">
          ${task.text}
        </span>
        <button onclick="deleteTask(${index})">❌</button>
      `;

      li.querySelector('span').addEventListener('click', () => toggleComplete(index));
      taskList.appendChild(li);
    });
}

function addTask(text) {
  tasks.push({ text, completed: false });
  saveTasks();
  renderTasks();
}

function deleteTask(index) {
  tasks.splice(index, 1);
  saveTasks();
  renderTasks();
}

function toggleComplete(index) {
  tasks[index].completed = !tasks[index].completed;
  saveTasks();
  renderTasks();
}

taskForm.addEventListener('submit', (e) => {
  e.preventDefault();
  const text = taskInput.value.trim();
  if (text) {
    addTask(text);
    taskInput.value = '';
  }
});

filterButtons.forEach(btn => {
  btn.addEventListener('click', () => {
    document.querySelector('.filter-btn.active').classList.remove('active');
    btn.classList.add('active');
    renderTasks(btn.dataset.filter);
  });
});

renderTasks();
```

---

## 🎯 **Learning Goals Covered**

- ✅ **HTML**: Semantic structure, forms, inputs, buttons
- 🎨 **CSS**: Styling, layout, hover effects, class manipulation
- 🚀 **JavaScript**:
  - DOM manipulation
  - Event handling
  - Array methods (e.g. `forEach`, `filter`, `splice`)
  - Local storage API
  - Toggle classes dynamically

---

## 🔧 **Possible Enhancements**

- Add **edit task** functionality
- Include a **light/dark theme switch**
- Sync tasks with a **backend server**
- Add **animations** for adding/removing tasks

---
