# Using EXPLAIN and EXPLAIN ANALYZE in Athena

A data engineer wants to improve the performance of SQL queries in Amazon Athena that run against a sales data table.

The data engineer wants to understand the execution plan of a specific SQL statement. The data engineer also wants to see the computational cost of each operation in a SQL query.

**Which statement does the data engineer need to run to meet these requirements?**

**Response:**

EXPLAIN ANALYZE SELECT * FROM sales

### Documentation quote:
```
The EXPLAIN ANALYZE statement shows both the distributed execution plan of a
specified SQL statement and the computational cost of each operation in a SQL query.

You can output the results in text or JSON format.
```

Source: https://docs.aws.amazon.com/athena/latest/ug/athena-explain-statement.html
