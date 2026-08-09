# Automotive Market Trends & Pricing Analysis | SQL

## Overview

This project uses a real-world used-car listing dataset to explore pricing, vehicle usage and market trends in the Indian automotive market using SQL.

Rather than treating the dataset as a simple query exercise, the analysis is structured around practical questions such as how vehicle characteristics relate to listed prices, which larger vehicles offer stronger mileage, how prices vary within models, and how listed values change across model years.

The project demonstrates analytical SQL ranging from filtering and aggregation through to subqueries, Common Table Expressions (CTEs) and window functions such as `SUM() OVER`, `LAG()` and `RANK()`.

> **Note:** The dataset contains vehicle listings and listed selling prices. Results should therefore be interpreted as patterns within the available listing data rather than confirmed transaction prices, revenue or causal market effects.

---

## Dataset

Each row represents a used car listing and includes attributes such as:

- `Name` – vehicle model / variant
- `year` – model year
- `selling_price` – listed selling price
- `km_driven` – distance driven
- `fuel` – fuel type
- `seller_type` – seller category
- `transmission` – manual or automatic
- `owner` – ownership history
- `mileage` – fuel-efficiency measure
- `engine` – engine capacity
- `max_power` – maximum power
- `torque` – torque information
- `seats` – seating capacity

### Files

- [`Exploring Trends in the Automotive Industry.csv`](./Exploring%20Trends%20in%20the%20Automotive%20Industry.csv) – source dataset
- [`Exploring Trends in the AutomotiveIndustry.sql`](./Exploring%20Trends%20in%20the%20AutomotiveIndustry.sql) – analytical SQL queries

---

## Analytical Questions

### 1. How does listed price vary by fuel type?

Calculates average selling price by fuel type for vehicles that are:

- Manual transmission
- First-owner vehicles

**SQL used:** `WHERE`, `GROUP BY`, `AVG()`

---

### 2. Which larger vehicles have the highest average mileage?

Filters vehicles with more than five seats and identifies the top three models by average mileage.

**SQL used:** `WHERE`, `GROUP BY`, `AVG()`, `ORDER BY`, `LIMIT`

---

### 3. Which models show the greatest price variation?

Compares the maximum and minimum listed price within each model and identifies models whose price spread exceeds a specified threshold.

This can help highlight models appearing across substantially different years, trims, conditions or specifications.

**SQL used:** `MAX()`, `MIN()`, `GROUP BY`, `HAVING`

---

### 4. Which listings appear expensive relative to their mileage?

Compares individual listings with dataset-wide benchmarks and returns vehicles that have:

- Above-average selling prices
- Below-average mileage

This creates a simple value-screening rule based on two market-wide measures.

**SQL used:** scalar subqueries, `AVG()`, multiple filtering conditions

---

### 5. How does cumulative listed value develop across model years?

Uses a window function to calculate a cumulative sum of listed prices for each vehicle model ordered by year.

**SQL used:**

```sql
SUM(selling_price) OVER (
    PARTITION BY Name
    ORDER BY year
)
```

This demonstrates partitioned cumulative calculations without collapsing the underlying rows.

---

### 6. Which vehicles are priced close to the overall market average?

Identifies listings whose selling price falls within ±10% of the dataset-wide average selling price.

This provides a simple way to isolate vehicles around the centre of the observed price distribution.

**SQL used:** subqueries, `BETWEEN`, calculated thresholds

---

### 7. How can price trends be smoothed over time?

Calculates an expanding running average of selling prices for each model ordered by year.

**SQL used:**

```sql
AVG(selling_price) OVER (
    PARTITION BY Name
    ORDER BY year
    ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW
)
```

This smooths individual observations by incorporating all preceding records for the model.

> The original query comment refers to this calculation as an exponential moving average (EMA). Technically, the implemented SQL is a cumulative / expanding average rather than a true EMA because it does not apply exponentially declining weights.

---

### 8. Which models show lower prices than the previous observation?

Uses `LAG()` to compare each listed price with the previous row for the same model when ordered by year, then flags decreases.

**SQL used:** `LAG()`, `PARTITION BY`, subquery filtering

```sql
LAG(selling_price) OVER (
    PARTITION BY Name
    ORDER BY year
)
```

This demonstrates row-to-row comparison using analytical window functions.

---

### 9. Which models accumulate the highest recorded kilometres by transmission type?

Groups vehicles by model and transmission, sums `km_driven`, and then identifies the highest aggregate value within each transmission category.

**SQL used:** CTEs, `SUM()`, `GROUP BY`, grouped maximum comparison

This section demonstrates how an intermediate result set can be created with a Common Table Expression and reused in a second-stage query.

---

### 10. Ranking and yearly price analysis

The final query experiments with `RANK()` alongside yearly average selling prices.

The current implementation partitions the ranking by vehicle model, which means the rank is calculated **within each model** rather than across all models. It therefore does not yet isolate the three highest-priced models overall as the query comment originally intended.

A future refinement would first calculate a model-level price metric, rank models globally, and then return yearly averages only for the top three.

**SQL used:** CTEs, `RANK()`, window functions, `GROUP BY`

---

## SQL Concepts Demonstrated

| Area | Techniques |
|---|---|
| Filtering | `WHERE`, `BETWEEN`, multiple conditions |
| Aggregation | `AVG()`, `SUM()`, `MIN()`, `MAX()` |
| Segmentation | `GROUP BY`, `HAVING` |
| Subqueries | Global-average comparisons and threshold calculations |
| CTEs | Multi-stage analytical queries |
| Window functions | `SUM() OVER`, `AVG() OVER`, `LAG()`, `RANK()` |
| Ranking | Top-N analysis and ordered comparisons |
| Trend analysis | Cumulative values, running averages and previous-period comparisons |
| Business logic | Price bands, mileage filters, ownership and transmission segmentation |

---

## What This Project Demonstrates

The project shows the ability to move from a raw business dataset to targeted analytical questions and translate those questions into SQL.

Key capabilities demonstrated include:

- Writing analytical SQL beyond basic `SELECT` statements
- Segmenting vehicle listings by commercial and technical attributes
- Benchmarking individual records against dataset-level averages
- Analysing price dispersion and usage patterns
- Using subqueries and CTEs to structure multi-stage analysis
- Applying window functions for cumulative calculations, ranking and row-to-row comparisons
- Recognising the difference between observed associations in listing data and stronger claims such as realised sales or causal market behaviour

---

## Tools & Technologies

- **SQL**
- **Relational database environment**
- **CSV data import**
- Compatible with a SQL environment supporting CTEs and window functions, with minor syntax changes where required

---

## How to Run

1. Create a database, for example `cars_info`.
2. Import `Exploring Trends in the Automotive Industry.csv` into a table named `car_info`.
3. Check that numeric fields such as `selling_price`, `km_driven`, `mileage` and `seats` use appropriate data types.
4. Run the queries in `Exploring Trends in the AutomotiveIndustry.sql`.
5. Review each result in the context of the analytical question documented above.

The queries can be executed in a database client or adapted for use in a Jupyter Notebook through a SQL extension and database connection.

---

## Skills Demonstrated

**SQL · Data Analysis · Exploratory Data Analysis · Window Functions · CTEs · Subqueries · Data Aggregation · Trend Analysis · Pricing Analysis · Market Analysis · Analytical Thinking**

---

## Potential Extensions

The project could be developed further by:

- Normalising the single listing table into related vehicle, model, seller and specification tables
- Adding multi-table `JOIN` analysis
- Converting the running average query into a true EMA calculation
- Correcting the final ranking logic to identify the top three models globally
- Calculating depreciation-style measures while controlling for model year and mileage
- Adding manufacturer-level analysis
- Connecting the SQL output to Power BI for interactive visualisation
- Introducing data-quality checks for missing, duplicated or inconsistent vehicle attributes

---

## Author

**Yasir Savanur**
