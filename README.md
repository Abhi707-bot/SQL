# SQL & Databases - Beginner Guide

## 📌 Lesson 1: Introduction to SQL & Databases

### 1️⃣ What is SQL?
SQL (Structured Query Language) is used to store, retrieve, manipulate, and manage data in relational databases.

### ✅ Uses of SQL:
- Fetching data from databases:  
  ```sql
  SELECT * FROM employees;
  ```
- Updating records:  
  ```sql
  UPDATE employees SET salary = 60000 WHERE emp_id = 5;
  ```
- Deleting records:  
  ```sql
  DELETE FROM employees WHERE emp_id = 5;
  ```
- Creating tables, defining schema, and managing relationships

### 2️⃣ What is a Database?
A database is a structured collection of data.

#### Examples:
- A bank stores customer transactions in a database.
- An e-commerce site stores product and order details in a database.

### 3️⃣ What is an RDBMS?
An **RDBMS (Relational Database Management System)** organizes data into tables (rows & columns) and maintains relationships between tables using keys.

🔹 **Popular RDBMS:**
- MySQL (Open-source, widely used)
- PostgreSQL (Advanced, supports complex queries)
- SQL Server (Microsoft's enterprise-level database)
- Oracle Database (Used in large-scale applications)

---

## 📌 Lesson 2: SQL Basics - Writing Queries

### 1️⃣ Creating a Database
```sql
CREATE DATABASE company_db;
USE company_db;
```

### 2️⃣ Creating a Table
```sql
CREATE TABLE employees (
    emp_id INT PRIMARY KEY,
    name VARCHAR(50),
    age INT,
    department VARCHAR(50),
    salary DECIMAL(10,2)
);
```

### 3️⃣ Inserting Data
```sql
INSERT INTO employees (emp_id, name, age, department, salary)
VALUES (1, 'Alice', 30, 'HR', 60000);
```

### 4️⃣ Retrieving Data
```sql
SELECT * FROM employees;
```

### 5️⃣ Filtering Data
```sql
SELECT * FROM employees WHERE department = 'HR';
```

---

## 📌 Lesson 3: Filtering & Sorting Data

### 1️⃣ Selecting Specific Columns
Instead of `SELECT *`, you can choose specific columns:
```sql
SELECT name, department FROM employees;
```

### 2️⃣ Filtering Data Using WHERE Clause
The `WHERE` clause helps in applying conditions:
```sql
SELECT * FROM employees WHERE salary > 50000;
```

🔹 Operators you can use in WHERE:
- `=` (Equal to)
- `!=` or `<>` (Not equal to)
- `>` (Greater than), `<` (Less than)
- `>=` (Greater than or equal to), `<=` (Less than or equal to)
- `BETWEEN` (Range)
- `LIKE` (Pattern matching)
- `IN` (Matches multiple values)

### 3️⃣ Sorting Data Using ORDER BY
Sort results ascending (default) or descending:
```sql
SELECT * FROM employees ORDER BY salary ASC;  -- Ascending order  
SELECT * FROM employees ORDER BY salary DESC; -- Descending order  
```

### 4️⃣ Using DISTINCT to Remove Duplicates
```sql
SELECT DISTINCT department FROM employees;
```
This returns unique department names.

---

## 🎯 Hands-on Exercise
✅ **Task:**
1. Retrieve all students from `students` whose marks are greater than 80.
2. Sort students by age in descending order.
3. Find all unique classes from the `students` table.

### 📝 Solution
```sql
SELECT * FROM students WHERE marks > 80;
SELECT * FROM students ORDER BY age DESC;
SELECT DISTINCT class FROM students;
```
