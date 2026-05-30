# SQL-Project

# SQL Practice Project – Employee Management

This project is a hands-on SQL exercise built with **PostgreSQL**. It covers fundamental database operations such as creating tables, inserting data, updating records, altering schemas, and writing queries to retrieve and manipulate employee data. The project is ideal for beginners learning SQL or anyone looking to refresh core database concepts.

## 📌 Project Overview

The main goal is to manage an `employees` table and perform common administrative and analytical tasks. The project includes:

- Table creation with constraints (`PRIMARY KEY`, `CHECK`, `NOT NULL`)
- Data insertion
- 10 SQL tasks ranging from simple `SELECT` queries to schema alterations
- Practical use of `UPDATE`, `DELETE`, `ALTER TABLE`, and `ORDER BY`

## 🛠️ Technologies Used

- **PostgreSQL** – relational database management system
- **SQL** – structured query language

## 📁 Files in the Repository

| File | Description |
|------|-------------|
| `SQL PROJECT.sql` | Complete SQL script: table creation, sample data, and solutions to all 10 questions |
| `Project Questions for SQL.docx` | Problem statement listing each task |

## 🗃️ Database Schema

The `employees` table contains the following columns:

| Column       | Type                     | Constraints                  |
|--------------|--------------------------|------------------------------|
| employee_id  | SERIAL                   | PRIMARY KEY                  |
| first_name   | VARCHAR(50)              | NOT NULL                     |
| last_name    | VARCHAR(50)              | NOT NULL                     |
| department   | VARCHAR(50)              |                              |
| salary       | DECIMAL(10,2)            | CHECK (salary > 0)           |
| joining_date | DATE                     | NOT NULL                     |
| age          | INT                      | CHECK (age >= 18)            |

Later modifications (questions 4, 5, 7) add an `email` column, rename `department` to `dept_name`, and change `salary` type to `INTEGER`.

## 📋 Tasks & Solutions

Here are the 10 tasks implemented in the script:

1. **Retrieve** all employees' first names and their departments.  
   `SELECT first_name, department FROM employees;`

2. **Update** salary of IT employees by +10%.  
   `UPDATE employees SET salary = salary * 1.10 WHERE department = 'IT';`

3. **Delete** employees older than 34 years.  
   `DELETE FROM employees WHERE age > 34;`

4. **Add** a new column `email` to the table.  
   `ALTER TABLE employees ADD COLUMN email VARCHAR(100);`

5. **Rename** column `department` to `dept_name`.  
   `ALTER TABLE employees RENAME COLUMN department TO dept_name;`

6. **Retrieve** names of employees who joined after January 1, 2021.  
   `SELECT first_name, last_name FROM employees WHERE joining_date > '2021-01-01';`

7. **Change** data type of `salary` column to `INTEGER`.  
   `ALTER TABLE employees ALTER COLUMN salary TYPE INTEGER;`

8. **List** all employees with age and salary, sorted by salary descending.  
   `SELECT first_name, last_name, age, salary FROM employees ORDER BY salary DESC;`

9. **Insert** a new employee: Raj Singh, Marketing, 60000, '2023-09-15', age 30.  
   `INSERT INTO employees (first_name, last_name, dept_name, salary, joining_date, age) VALUES ('Raj', 'Singh', 'Marketing', 60000, '2023-09-15', 30);`

10. **Update** age of every employee by +1.  
    `UPDATE employees SET age = age + 1;`

## ▶️ How to Run the Project

1. **Install PostgreSQL** (if not already installed).
2. Open **pgAdmin** or the **psql** command line.
3. Create a new database (optional):
   ```sql
   CREATE DATABASE employee_db;

What I Learned
Using ALTER TABLE to modify schema without losing data.

Importance of WHERE clauses in UPDATE and DELETE.

Type conversion in PostgreSQL (ALTER COLUMN ... TYPE).

Maintaining data integrity with CHECK constraints.

Writing clear, readable SQL scripts.

🤝 Connect
Feel free to use this project as a template for your own SQL practice. If you have suggestions or improvements, open an issue or submit a pull request.
