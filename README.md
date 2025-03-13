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

## 📌 Lesson 4: Aggregations & Grouping

### 1️⃣ Aggregate Functions
Aggregate functions perform calculations on a group of rows and return a single value.

| Function | Description |
|----------|-------------|
| COUNT()  | Counts the number of rows |
| SUM()    | Adds up values in a column |
| AVG()    | Calculates the average value |
| MAX()    | Finds the highest value |
| MIN()    | Finds the lowest value |

🔹 **Examples:**
```sql
SELECT COUNT(*) FROM employees;  -- Total number of employees  
SELECT AVG(salary) FROM employees;  -- Average salary  
SELECT MAX(salary) FROM employees;  -- Highest salary  
SELECT MIN(salary) FROM employees;  -- Lowest salary  
```

### 2️⃣ Grouping Data Using GROUP BY
Used to group rows that have the same values.
```sql
SELECT department, COUNT(*) FROM employees GROUP BY department;
```
This returns the number of employees in each department.

### 🔹 Using HAVING (Filtering Grouped Data)
The `HAVING` clause filters groups, similar to `WHERE` but used after `GROUP BY`.
```sql
SELECT department, AVG(salary) 
FROM employees 
GROUP BY department 
HAVING AVG(salary) > 50000;
```
This returns only departments where the average salary is greater than 50,000.

---

## 📌 Understanding GROUP BY and HAVING

### 1️⃣ What is GROUP BY?
- `GROUP BY` groups rows that have the same values in a column.
- It is always used with aggregate functions (`COUNT()`, `SUM()`, `AVG()`, etc.).
- It collapses multiple rows into a single row per group.

🔹 **Example:** Count the number of employees in each department:
```sql
SELECT department, COUNT(*) AS employee_count
FROM employees
GROUP BY department;
```

### 2️⃣ What is HAVING?
- `HAVING` is used to filter grouped data (i.e., after `GROUP BY` is applied).
- It works like `WHERE`, but `WHERE` cannot be used with aggregate functions.

🔹 **Example:** Find only departments with more than 1 employee:
```sql
SELECT department, COUNT(*) AS employee_count
FROM employees
GROUP BY department
HAVING COUNT(*) > 1;
```

### 📌 Difference Between HAVING and WHERE

| Feature      | WHERE  | HAVING  |
|-------------|--------|---------|
| Used with   | Individual rows | Groups (after aggregation) |
| Can filter on | Any column | Aggregate functions |
| Works before/after GROUP BY | Before | After |

🔹 **Example 1: Using WHERE (Before Aggregation)**
```sql
SELECT * FROM employees WHERE salary > 50000;
```
✅ This filters rows first, before grouping.

🔹 **Example 2: Using HAVING (After Aggregation)**
```sql
SELECT department, AVG(salary) 
FROM employees 
GROUP BY department 
HAVING AVG(salary) > 50000;
```
✅ This first groups departments, calculates average salary, then filters the results.

---

## 🎯 Hands-on Exercise
✅ **Task:**
1. Find the total salary paid in each department.
2. Retrieve only those departments where the total salary is greater than 100,000.
3. Find the number of students in each class from the `students` table.
4. Retrieve only those classes where more than 3 students are enrolled.

---

🚀 **Happy Learning!**
