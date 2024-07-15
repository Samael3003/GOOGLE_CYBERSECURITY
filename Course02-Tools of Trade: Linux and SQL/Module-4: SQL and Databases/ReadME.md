# SQL Notes

## Table of Contents
1. [Query a Database](#query-a-database)
2. [Apply Filters to SQL Queries](#apply-filters-to-sql-queries)
3. [Join Tables](#join-tables)
4. [Perform Calculations](#perform-calculations)

---

## Query a Database
To retrieve information from a database, use the following keywords:

- **SELECT**: Indicates which columns to return.
- **FROM**: Indicates which table to query; required to perform a query.
- **ORDER BY**: Sequences the records returned by a query based on a specified column or columns.

### Examples:
- `SELECT employee_id FROM employees;` 
- `SELECT * FROM employees ORDER BY department ASC;`
- `ORDER BY city DESC;`
- `ORDER BY country, city;`

---

## Apply Filters to SQL Queries
Use the `WHERE` clause along with other SQL keywords to apply filters.

### Keywords:
- **AND**: Specifies that both conditions must be met.
- **BETWEEN**: Filters for values within a range.
- **=**: Equal to.
- **>**: Greater than.
- **>=**: Greater than or equal to.
- **<**: Less than.
- **<=**: Less than or equal to.
- **LIKE**: Searches for a pattern.
- **NOT**: Negates a condition.
- **<> / !=**: Not equal to.
- **OR**: Specifies that either condition can be met.
- **%**: Wildcard for any number of characters.
- **_**: Wildcard for one character.

### Examples:
- `WHERE region = 5 AND country = 'USA';`
- `WHERE hiredate BETWEEN '2002-01-01' AND '2003-01-01';`
- `WHERE title LIKE 'IT%';`
- `WHERE NOT country = 'Mexico';`
- `WHERE country = 'Canada' OR country = 'USA';`

---

## Join Tables
Use the following SQL keywords to join tables:

- **FULL OUTER JOIN**: Returns all records from both tables.
- **INNER JOIN**: Returns records matching on a specified column in both tables.
- **LEFT JOIN**: Returns all records from the first table and matching records from the second.
- **RIGHT JOIN**: Returns all records from the second table and matching records from the first.

### Examples:
- `SELECT * FROM employees FULL OUTER JOIN machines ON employees.device_id = machines.device_id;`
- `SELECT * FROM employees INNER JOIN machines ON employees.device_id = machines.device_id;`
- `SELECT * FROM employees LEFT JOIN machines ON employees.device_id = machines.device_id;`
- `SELECT * FROM employees RIGHT JOIN machines ON employees.device_id = machines.device_id;`

---

## Perform Calculations
Use the following aggregate functions for calculations:

- **AVG**: Returns the average of numerical data in a column.
- **COUNT**: Returns the number of records from a query.
- **SUM**: Returns the sum of numerical data in a column.

### Examples:
- `SELECT AVG(height) FROM employees;`
- `SELECT COUNT(firstname) FROM employees;`
- `SELECT SUM(cost) FROM products;`

---

Feel free to edit and expand upon these notes as needed!
