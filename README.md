# task-sql-project
A time management system with SQL queries.
# ✅ Task Management System - SQL Based

This project represents a simple **Task Management System** using **SQL**. It is designed to manage users, categorize their tasks, and track their progress through statuses like `pending` and `completed`. Ideal for learning database relationships and query building.

---

## 📦 Features

- Full SQL schema with three normalized tables:
  - `Users`
  - `Categories`
  - `Tasks` (with foreign keys)
- Sample realistic data for users and tasks
- Demonstrates:
  - Table creation with constraints
  - Insertion and manipulation of data
  - Use of `JOIN`, `CASE`, `WHERE`, `UPDATE`, and `DELETE` queries
  - Filtering by task status
  - Handling missing descriptions gracefully

---

## 🧱 Database Structure

- **Users Table**
  - Stores user information like `username` and `email`

- **Categories Table**
  - Defines task categories such as "study", "home", "work", etc.

- **Tasks Table**
  - Contains task details with links to `Users` and `Categories`
  - Includes status validation (`CHECK(status IN ('pending', 'completed'))`)

---

## 🧪 Sample SQL Operations

- Update a user:
  ```sql
  UPDATE Users SET username = 'mahmoud' WHERE id = 9;
  UPDATE Users SET email = 'mahmoud@example.com' WHERE username = 'mahmoud';
Delete a task:

sql
نسخ
تحرير
DELETE FROM Tasks WHERE id = 11;
Get all users or tasks:

sql
نسخ
تحرير
SELECT * FROM Users;
SELECT * FROM Tasks;
View tasks by status:

sql
نسخ
تحرير
SELECT title, status FROM Tasks WHERE LOWER(status) = 'completed';
SELECT title, status FROM Tasks WHERE LOWER(status) = 'pending';
Show task list with user info and categories:

sql
نسخ
تحرير
SELECT 
  Users.username AS "User Name", 
  Users.email AS "Email Address", 
  Tasks.title AS "Task", 
  CASE 
    WHEN TRIM(IFNULL(Tasks.description, '')) = '' THEN 'Not found'
    ELSE Tasks.description
  END AS "Description",
  Tasks.status AS "Status", 
  Tasks.due_date AS "Due Date", 
  Categories.name AS "Category"
FROM Users
LEFT JOIN Tasks ON Users.id = Tasks.user_id
LEFT JOIN Categories ON Tasks.category_id = Categories.id;
🛠 Tools Used
SQLite / SQL Playground

GitHub for version control

SQL syntax (PostgreSQL-style compatibility)

📊 How to Use
Copy the SQL schema and data into your SQL environment (e.g., SQLiteStudio, DB Browser for SQLite).

Run each section to create and populate the tables.

Use the SELECT and UPDATE queries to explore or modify the dataset.

👩‍💻 Author
Salma Wael
GitHub: @Salmawaelmohamed
