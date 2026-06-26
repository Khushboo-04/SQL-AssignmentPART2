# SQL-AssignmentPART2
1.Ans Execution Flow of SQL Commands

Execution Order
FROM -> WHERE -> GROUP BY -> HAVING -> SELECT -> ORDER BY 

FROM identifies the source table 
WHERE removes unwanted rows early.
GROUP BY creates groups for aggregation.
HAVING filters grouped data.
SELECT returns the required columns.
ORDER BY sorts the final output.

This execution order improves both correctness and performance.

SELECT department, AVG(salary)
FROM Employees
WHERE salary > 30000
GROUP BY department
HAVING AVG(salary) > 50000
ORDER BY AVG(salary) DESC;




2.Ans Five SQL Queries Demonstrating DDL Operations
   1. CREATE TABLE
    CREATE TABLE Student (
    student_id INT PRIMARY KEY,
    name VARCHAR(50),
    age INT);
Creates a new table.

2. ALTER TABLE
ALTER TABLE Student
ADD email VARCHAR(100);
Adds a new column.

3. RENAME TABLE
ALTER TABLE Student
RENAME TO Students;
Renames the table.

4. TRUNCATE TABLE
TRUNCATE TABLE Students;
Removes all records while keeping the table structure.

5. DROP TABLE
DROP TABLE Students;
Deletes the table completely.




3.Ans Three SQL Queries Demonstrating DML Operations
1. INSERT
INSERT INTO Student(student_id, name, age)
VALUES (1, 'Aditi', 21);
Adds a new record.

2. UPDATE
UPDATE Student
SET age = 22
WHERE student_id = 1;
Updates existing data.

3. DELETE
DELETE FROM Student
WHERE student_id = 1;
Deletes specific records.





4.Ans Create Two Tables and Demonstrate SQL Joins
Create Tables
Department Table
CREATE TABLE Department (
    dept_id INT PRIMARY KEY,
    dept_name VARCHAR(50)
);
Employee Table
CREATE TABLE Employee (
    emp_id INT PRIMARY KEY,
    emp_name VARCHAR(50),
    dept_id INT
);
Insert Sample Data
Department
INSERT INTO Department VALUES
(1, 'HR'),
(2, 'IT'),
(3, 'Finance'),
(4, 'Marketing');
Employee
INSERT INTO Employee VALUES
(101, 'Alice', 1),
(102, 'Bob', 2),
(103, 'Charlie', 2),
(104, 'David', 5);
INNER JOIN

Returns only matching rows.

SELECT e.emp_name, d.dept_name
FROM Employee e
INNER JOIN Department d
ON e.dept_id = d.dept_id;
LEFT JOIN

Returns all rows from the left table and matching rows from the right table.

SELECT e.emp_name, d.dept_name
FROM Employee e
LEFT JOIN Department d
ON e.dept_id = d.dept_id;
RIGHT JOIN

Returns all rows from the right table and matching rows from the left table.

SELECT e.emp_name, d.dept_name
FROM Employee e
RIGHT JOIN Department d
ON e.dept_id = d.dept_id;
FULL OUTER JOIN

Returns all matching and non-matching rows from both tables.

SELECT e.emp_name, d.dept_name
FROM Employee e
FULL OUTER JOIN Department d
ON e.dept_id = d.dept_id;



5. Ans Use meaningful table and column names.
Avoid using SELECT *; retrieve only required columns.
Create indexes on frequently searched columns.
Use WHERE clauses to reduce unnecessary data retrieval.
Use JOINs instead of nested subqueries where appropriate.
Normalize database tables to reduce redundancy.
Write readable SQL using proper indentation and formatting.
Use aliases (e, d) to improve readability.
Avoid duplicate data whenever possible.
Use transactions (COMMIT and ROLLBACK) for critical operations.
Always define PRIMARY KEY and FOREIGN KEY constraints.
Test queries on a small dataset before running them on production databases.
Add comments for complex SQL queries.
Prefer parameterized queries to prevent SQL injection.
Regularly analyze query performance using tools like EXPLAIN.
