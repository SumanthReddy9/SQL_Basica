# SQL_Basics

# Queries

Q. Return employee recoed with max salary ? (Employee (employee_id, first_name, last_anme, gender, position, dept_id, salary), Dept(dept_id, dept_name))

A. SELECT * FROM Employee WHERE salary  = (SELECT Max(salary) from Employee)


Q. Select second highest salary in the Employee table ? (Employee (employee_id, first_name, last_anme, gender, position, dept_id, salary), Dept(dept_id, dept_name))

A. SELECT Max(salary) from Employee where salary NOT IN (select Max(salary) from Employee)

Q. Select range of employees based on ids? (Employee (employee_id, first_name, last_anme, gender, position, dept_id, salary), Dept(dept_id, dept_name)) 

A. SELECT * from Employee WHERE employee_id between 2003 and 2008.

Q. Return employee name, highest salary and department name? (Employee (employee_id, first_name, last_anme, gender, position, dept_id, salary), Dept(dept_id, dept_name)) 

A. SELECT e.first_name, e.last_name, e.salary, d.dept_name FROM Employee e INNER JOIN Dept d ON (e.dept_id = d.dept_id) WHERE salary in (SELECT Max(salary) FROM Employee). 

Q. Return highest salary employee name, dept name for each dept.

A. SELECT e.first_name, e.last_name, e.salary, d.dept_name FROM Employee e INNER JOIN Dept d ON (e.dept_id = d.dept_id) WHERE salary in (SELECT Max(salary) FROM Employee GROUP BY dept_id)


# Questions

Q. What is the difference between DELETE and TRUNCATE ?

A. DELETE command is used to delete the row in the Table where TRUNCATE command is used to delete all the rows in Table.
   Roll back is possible in DELETE command but not in TRUNCATE. TRUNCATE is faster than DELETE.

Q. What are the different subsets of SQL ?

A.  There are four subsets in SQL 
    1) DDL (Data Definition Language) -- Consists of cmds which can be used to define database schema.
    2) DML (Data Manipulation Language) --  Consists of cmds that can be used for manipulation of data in present database.
    3) DCL (Data Control Language) -- Includes cmds deals with permissions, rights and other controls of database system.
    4) TCL (Transaction Control Language) -- Includes cmds which deals with trasactions in database.
    


