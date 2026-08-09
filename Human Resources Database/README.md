# Human Resources Database

## Overview

This project is a small relational Human Resources database designed to practise SQL schema design, multi-table querying and workforce analysis.

The database models common HR entities including employees, departments, jobs, job history and locations. The accompanying query files use these tables to answer practical questions around employee demographics, compensation, departmental headcount and job history.

## Project Files

- `HR database-DDL.sql` – creates the HR database tables and primary keys.
- `HR database-Queries.sql` – contains filtering, sorting, aggregation, grouping and introductory multi-table queries.
- `HR database-Queries_2.sql` – focuses on joins across employee, department, job and job-history data.

## Database Structure

The project contains five main tables:

### EMPLOYEES
Stores employee-level information including:

- Employee ID
- First and last name
- Date of birth
- Sex
- Address
- Job ID
- Salary
- Manager ID
- Department ID

### JOBS
Stores job information including:

- Job ID
- Job title
- Minimum salary
- Maximum salary

### JOB_HISTORY
Stores historical job assignments for employees, including:

- Employee ID
- Start date
- Job ID
- Department ID

### DEPARTMENTS
Stores organisational department information including:

- Department ID
- Department name
- Manager ID
- Location ID

### LOCATIONS
Stores location and department identifiers.

The tables are linked logically through shared identifiers such as employee IDs, job IDs and department IDs. The current DDL defines primary keys, while the relationships are demonstrated through SQL join logic rather than explicit foreign-key constraints.

## Analysis Performed

The query scripts cover a range of common HR and relational database tasks.

### Employee Filtering

Examples include:

- Finding employees based in a specific location.
- Identifying employees born within a particular decade.
- Filtering employees by salary range and department.

### Department-Level Analysis

The project uses `GROUP BY`, `COUNT()` and `AVG()` to calculate:

- Employee headcount by department.
- Average salary by department.
- Departments with fewer than a specified number of employees using `HAVING`.

### Multi-Table Joins

The project demonstrates several join types:

- `INNER JOIN`
- `LEFT OUTER JOIN`
- `FULL OUTER JOIN`

These are used to combine employee records with:

- Job history
- Job titles
- Department information

The queries also explore the difference between applying conditions in the `WHERE` clause and within a join condition.

## SQL Concepts Demonstrated

- Relational database design
- `CREATE TABLE`
- Primary keys
- `SELECT`
- `WHERE`
- `LIKE`
- `BETWEEN`
- `ORDER BY`
- `GROUP BY`
- `HAVING`
- `COUNT()`
- `AVG()`
- Subqueries
- `INNER JOIN`
- `LEFT OUTER JOIN`
- `FULL OUTER JOIN`
- Table aliases
- Date filtering with `YEAR()`

## Business Context

The project represents the type of analysis that could be carried out against an HR information system. The queries can support questions around workforce composition, departmental staffing, salary levels, job history and organisational structure.

## How to Run

1. Open a SQL environment that supports the syntax used in the scripts, such as IBM Db2.
2. Run `HR database-DDL.sql` to create the tables.
3. Load or insert suitable HR data into the tables.
4. Run the queries in `HR database-Queries.sql` and `HR database-Queries_2.sql`.

The scripts can also be run from Jupyter Notebook using a SQL extension and an appropriate database connection.

## Skills Demonstrated

- SQL
- Relational Databases
- Database Design
- Data Analysis
- HR / Workforce Analytics
- SQL Joins
- Data Aggregation
- Query Development
- Analytical Thinking

## Author

**Yasir Savanur**
