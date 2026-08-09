# Pet Sale Database

## Overview

This project is a compact SQL practice database built around a fictional pet shop. It focuses on core database operations, table manipulation and built-in SQL functions using a small transactional sales dataset.

The project was designed as a hands-on way to practise both Data Definition Language (DDL) and Data Manipulation Language (DML) operations before moving into more complex relational and analytical SQL work.

## Project Files

- `DDL - Exercise.sql` – creates and modifies pet sale tables using DDL and DML statements.
- `PETSALE-CREATE.sql` – creates a clean `PETSALE` table and inserts sample transaction data.
- `PETSALE-FUNCTIONS.sql` – applies aggregate, string and date functions to analyse the sales records.

## Database Structure

The project uses two small tables during the exercises.

### PETSALE
Stores sales transaction information including:

- Sale ID
- Animal type
- Quantity
- Sale price
- Sale date

An earlier version of the exercise also includes a `PROFIT` field before the table structure is modified.

### PET
Stores basic pet inventory information including:

- ID
- Animal type
- Quantity

## Database Operations Performed

The `DDL - Exercise.sql` script demonstrates how a database structure can be created and changed over time.

### Table Creation and Data Loading

The project uses:

- `CREATE TABLE`
- `INSERT INTO`
- `SELECT`

Sample records are inserted for cats, dogs, parrots, hamsters and goldfish.

### Table Alteration

The project modifies the `PETSALE` table using:

- `ALTER TABLE ... ADD COLUMN`
- `ALTER TABLE ... DROP COLUMN`
- `ALTER TABLE ... ALTER COLUMN`
- `ALTER TABLE ... RENAME COLUMN`

It also uses `UPDATE` statements to populate newly added quantity values.

### Removing Data and Objects

The project demonstrates the difference between:

- `TRUNCATE TABLE` – removing all rows while retaining the table structure.
- `DROP TABLE` – removing the table itself.

## SQL Functions Demonstrated

The `PETSALE-FUNCTIONS.sql` script applies several built-in SQL functions to the transaction data.

### Aggregate Functions

- `SUM()` to calculate total sales value.
- `MAX()` to identify the largest quantity sold.
- `AVG()` to calculate average sale price.
- Average price-per-unit calculations for selected animal types.

### String Functions

- `LENGTH()`
- `UCASE()`
- `LCASE()`
- `DISTINCT()`

These are used to transform and filter animal names.

### Date Functions and Date Arithmetic

- `DAY()`
- `MONTH()`
- Adding days to a sale date.
- Calculating the difference between the current date and the recorded sale date.

## SQL Concepts Demonstrated

- SQL fundamentals
- Data Definition Language (DDL)
- Data Manipulation Language (DML)
- `CREATE TABLE`
- `INSERT`
- `UPDATE`
- `ALTER TABLE`
- `TRUNCATE TABLE`
- `DROP TABLE`
- Primary keys
- Aggregate functions
- String functions
- Date functions
- Date arithmetic
- Filtering with `WHERE`
- Data type modification

## Purpose of the Project

This is intentionally a small sandbox-style database rather than a full business analytics case study. Its purpose is to demonstrate familiarity with the building blocks of SQL and how database tables can be created, populated, modified and queried.

It serves as a foundation for the more advanced projects in this repository, which introduce multi-table joins, relational database design and analytical SQL techniques.

## How to Run

1. Open a SQL environment compatible with the syntax used in the scripts, such as IBM Db2.
2. Run `PETSALE-CREATE.sql` to create and populate the main sales table.
3. Run `PETSALE-FUNCTIONS.sql` to test the aggregate, string and date functions.
4. Run `DDL - Exercise.sql` separately if you want to work through the table creation and alteration exercises from the beginning.

## Skills Demonstrated

- SQL
- Database Fundamentals
- Data Definition Language (DDL)
- Data Manipulation Language (DML)
- Database Administration Fundamentals
- Data Aggregation
- Data Transformation
- Query Development

## Author

**Yasir Savanur**
