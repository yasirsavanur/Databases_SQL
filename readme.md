# Databases & SQL Portfolio

A collection of SQL and relational database projects covering database design, data loading, querying, joins, aggregation, built-in functions and analytical SQL.

The projects show a progression from SQL fundamentals and database manipulation through to multi-table relational analysis and more advanced analytical queries using window functions.

## Projects at a Glance

| Project | Focus | Key SQL Skills |
|---|---|---|
| [Exploring Automotive Industry Trends in India](./Exploring%20Indian%20Automotive%20Industry) | Used-car pricing, mileage and market trend analysis | Aggregations, `HAVING`, subqueries, window functions, `LAG()`, `RANK()`, cumulative calculations |
| [Human Resources Database](./Human%20Resources%20Database) | Relational HR database and workforce queries | Schema design, joins, grouping, aggregation, subqueries, date filtering |
| [Case Study: City of Chicago Data Portal](./Case%20Study%3A%20City%20of%20Chicago%20Data%20Portal) | Public-sector data analysis using SQL from Jupyter | Data loading, SQL querying, filtering, aggregation, Db2, Jupyter SQL integration |
| [Pet Sale Database](./Pet%20Sale%20Database) | SQL fundamentals and database manipulation | DDL, DML, aggregate functions, string functions, date functions |

---

## 1. Exploring Automotive Industry Trends in India

This project analyses a real-world used-car dataset to explore pricing, vehicle usage and market trends in the Indian automotive market.

Each record represents a vehicle listing with attributes such as model, year, selling price, kilometres driven, fuel type, transmission, ownership history, mileage, engine size, power and seating capacity.

### Analysis performed

The SQL queries answer questions such as:

- How does average selling price vary by fuel type, transmission and ownership status?
- Which larger vehicles offer stronger average mileage?
- Which models show the widest price variation?
- Which listings are priced above the overall average while delivering below-average mileage?
- How does listed value change across model years?
- Which models experience year-on-year price declines?
- Which vehicles accumulate the highest mileage by transmission type?
- How do the highest-value models rank and change over time?

### SQL techniques demonstrated

- `WHERE`, `GROUP BY` and `HAVING`
- `AVG()`, `SUM()`, `MIN()` and `MAX()`
- Subqueries and market-average comparisons
- `SUM() OVER` for cumulative calculations
- `LAG()` for year-on-year comparisons
- `RANK()` for top-model analysis
- Moving-average style calculations
- Segmentation by fuel, transmission, seats and owner type

[View project files](./Exploring%20Indian%20Automotive%20Industry)

---

## 2. Human Resources Database

This project models a small Human Resources information system and uses SQL to analyse employee, job, department and job-history data across multiple related tables.

The database includes:

- `EMPLOYEES`
- `JOBS`
- `JOB_HISTORY`
- `DEPARTMENTS`
- `LOCATIONS`

### Analysis performed

The query scripts cover tasks such as:

- Filtering employees by location and birth year
- Identifying employees within specific salary bands and departments
- Calculating departmental headcount and average salary
- Finding departments below a specified staffing threshold
- Linking employees to job history and job titles
- Comparing employee and department data using different join types

### SQL techniques demonstrated

- Relational schema design
- `CREATE TABLE` and primary keys
- `WHERE`, `LIKE`, `BETWEEN` and `ORDER BY`
- `GROUP BY` and `HAVING`
- `COUNT()` and `AVG()`
- Subqueries
- `INNER JOIN`
- `LEFT OUTER JOIN`
- `FULL OUTER JOIN`
- Table aliases
- Date filtering with `YEAR()`

The project also explores the difference between applying conditions in a `WHERE` clause and applying them directly within a join condition.

[View project files and README](./Human%20Resources%20Database)

---

## 3. Case Study: City of Chicago Data Portal

This project uses public datasets from the City of Chicago to practise loading external data into a database and analysing it using SQL from a Jupyter Notebook.

The datasets include socioeconomic indicators such as poverty, unemployment, education, per-capita income and hardship levels across Chicago community areas.

### Workflow

1. Load public CSV data into Python.
2. Store the data in database tables.
3. Connect to the database from Jupyter.
4. Run SQL queries directly inside notebook cells.
5. Review and interpret query outputs alongside Markdown explanations.

### Tools and technologies

- SQL
- Python
- Pandas
- Jupyter Notebook
- SQLite / IBM Db2 workflow
- SQL magic extension

### Skills demonstrated

- Loading CSV data into relational tables
- Connecting Python and SQL workflows
- Data exploration
- Filtering and aggregation
- Query-based analysis of socioeconomic indicators
- Reproducible analysis inside a notebook environment

[View project files](./Case%20Study%3A%20City%20of%20Chicago%20Data%20Portal)

---

## 4. Pet Sale Database

This is a compact SQL fundamentals project built around a small pet-shop sales database. Its purpose is to demonstrate database creation, manipulation and the use of common SQL functions before moving into the more analytical projects in this repository.

### Database operations demonstrated

- `CREATE TABLE`
- `INSERT`
- `UPDATE`
- `ALTER TABLE`
- `ADD COLUMN`
- `DROP COLUMN`
- `ALTER COLUMN`
- `RENAME COLUMN`
- `TRUNCATE TABLE`
- `DROP TABLE`

### SQL functions demonstrated

- `SUM()`
- `MAX()`
- `AVG()`
- `ROUND()`
- `LENGTH()`
- `UCASE()` and `LCASE()`
- `DISTINCT`
- `DAY()` and `MONTH()`
- Date arithmetic
- `CURRENT DATE`

[View project files and README](./Pet%20Sale%20Database)

---

## SQL Skills Across the Repository

Across the four projects, the repository demonstrates:

- SQL querying and data extraction
- Relational database design
- DDL and DML
- Filtering and sorting
- Data aggregation
- Multi-table joins
- Subqueries
- Grouped analysis
- Window functions
- Ranking and year-on-year comparisons
- Date and string functions
- Database interaction from Jupyter Notebook
- Business-oriented analytical thinking

## Progression

The projects are intentionally varied in complexity:

**Pet Sale Database** → SQL fundamentals and database manipulation

**Human Resources Database** → relational schemas, joins and grouped analysis

**City of Chicago Case Study** → data loading and SQL analysis in a notebook workflow

**Automotive Industry Analysis** → analytical SQL, window functions and trend analysis

Together, they document the progression from core SQL syntax to using SQL as an analytical tool for practical datasets and business questions.

## Author

**Yasir Savanur**
