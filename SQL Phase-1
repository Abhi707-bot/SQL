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

## 🎯 Hands-on Exercise
✅ **Task:**
1. Create a database called `school_db`.
2. Create a table `students` with columns: `student_id`, `name`, `age`, `class`, `marks`.
3. Insert 3 records into the `students` table.
4. Retrieve all records from the table.


### 📝 Solution
```sql
CREATE DATABASE school_db;
USE school_db;

CREATE TABLE students (
    student_id INT PRIMARY KEY,
    name VARCHAR(50),
    age INT,
    class VARCHAR(20),
    marks DECIMAL(5,2)
);

INSERT INTO students (student_id, name, age, class, marks) VALUES
(1, 'John Doe', 14, '8th Grade', 85.5),
(2, 'Jane Smith', 13, '7th Grade', 90.0),
(3, 'Sam Wilson', 15, '9th Grade', 78.5);

SELECT * FROM students;
```
