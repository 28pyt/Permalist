# 🗂️ Permalist - Todo List App (Full Stack)

A simple full-stack Todo List application built with **Node.js, Express, PostgreSQL, and EJS**.  
This project demonstrates CRUD operations connected to a real database.

---

## 📌 Features

- ➕ Add new tasks
- 📄 View all tasks from PostgreSQL database
- ✏️ Edit existing tasks
- ❌ Delete tasks
- 💾 Persistent storage using PostgreSQL

---

## 🛠️ Tech Stack

- **Backend:** Node.js, Express
- **Database:** PostgreSQL
- **Frontend:** EJS templates
- **Middleware:** body-parser
- **Styling:** Static CSS (public folder)

---

## 🧠 How it works

The app performs full CRUD operations:

### ➕ Create
Users can add a new task:
```js
INSERT INTO items (title) VALUES ($1)
📖 Read

All tasks are loaded from PostgreSQL:

SELECT * FROM items ORDER BY id ASC
✏️ Update

Tasks can be edited:

UPDATE items SET title = $1 WHERE id = $2
❌ Delete

Tasks can be removed:

DELETE FROM items WHERE id = $1
📁 Project Structure
/public        → static files (CSS, images)
/views         → EJS templates
server.js      → main backend logic
⚙️ Setup Instructions
1. Install dependencies
npm install
2. Setup PostgreSQL database

Create database:

CREATE DATABASE permalist;

Create table:

CREATE TABLE items (
  id SERIAL PRIMARY KEY,
  title TEXT NOT NULL
);
3. Configure database connection

Update credentials in server.js:

const db = new pg.Client({
  user: "postgres",
  host: "localhost",
  database: "permalist",
  password: "your_password",
  port: 5432,
});
4. Run the server
node index.js

App runs on:

http://localhost:3000
📚 What I learned
Building REST-style routes with Express
Connecting Node.js with PostgreSQL
Performing CRUD operations
Using EJS for dynamic server-side rendering
Handling form data with body-parser
⚠️ Notes
This is a learning project
No authentication system included
Database runs locally (not deployed)
👨‍💻 Author

Built as part of a full-stack development learning journey.
