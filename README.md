# SQL Learning Journey

## Concepts Covered

---

### 1. [**Basic SELECT Statements**](#basic-select-statements)  
### 2. [**Aggregate Functions**](#aggregate-functions)  
### 3. [**Filtering Results**](#filtering-results)  
### 4. [**Sorting Data**](#sorting-data)  
### 5. [**Using LIKE for Pattern Matching**](#using-like-for-pattern-matching)  
### 6. [**Logical Operators**](#logical-operators)  
### 7. [**JOINs**](#joins)  

---

## Detailed Overview of Concepts Covered

---

### <a name="basic-select-statements"></a>1. **Basic SELECT Statements**  
**Overview of SQL Concept:**  
The `SELECT` statement retrieves data from a database. In this case, filtering is done using the `WHERE` clause, and results are sorted using `ORDER BY`.

- `WHERE category = 'Electronics'` filters for only Electronics products.
- `ORDER BY price DESC` sorts the results from highest to lowest price.

**Practice Question:**

You have a table `products` with the following columns:
- `product_name` (TEXT)
- `price` (DECIMAL)
- `category` (TEXT)

Write an SQL query to:
- Select `product_name` and `price`
- Filter for products in the 'Electronics' category
- Sort the results by `price` in descending order

**User's Answer:**

```sql
SELECT product_name, price FROM products WHERE category='Electronics' ORDER BY price DESC;
```

**Provided Answer:**

```sql
SELECT product_name, price FROM products WHERE category = 'Electronics' ORDER BY price DESC;
```

**Validity of User's Answer:**

✅ Correct  
☐ Not Correct  
☐ Almost Correct

---

### <a name="aggregate-functions"></a>2. **Aggregate Functions**  
**Overview of SQL Concept:**  
Aggregate functions perform calculations on a set of values and return a single value. They are commonly used with the `GROUP BY` clause.

- `SUM()`, `AVG()`, `COUNT()`, `MIN()`, and `MAX()` are common aggregate functions.

**Practice Question:**

You have a table `employees` with the following columns:
- `employee_id` (INTEGER)
- `first_name` (TEXT)
- `last_name` (TEXT)
- `salary` (DECIMAL)
- `department` (TEXT)

Write an SQL query to:
- Select the department and the total salary (`SUM(salary)`)
- Group the results by department

**User's Answer:**

```sql
SELECT department, SUM(salary) AS total_salary FROM employees GROUP BY department;
```

**Provided Answer:**

```sql
SELECT department, SUM(salary) AS total_salary FROM employees GROUP BY department;
```

**Validity of User's Answer:**

✅ Correct  
☐ Not Correct  
☐ Almost Correct

---

### <a name="filtering-results"></a>3. **Filtering Results**  
**Overview of SQL Concept:**  
The `WHERE` clause is used to filter records based on specific conditions. Multiple conditions can be combined with `AND`, `OR`, or `NOT`.

**Practice Question:**

You have a table `products` with the following columns:
- `product_name` (TEXT)
- `price` (DECIMAL)

Write an SQL query to:
- Select `product_name` and `price`
- Filter for products that have a price between 100 and 500

**User's Answer:**

```sql
SELECT product_name, price FROM products WHERE price BETWEEN 100 AND 500;
```

**Provided Answer:**

```sql
SELECT product_name, price FROM products WHERE price BETWEEN 100 AND 500;
```

**Validity of User's Answer:**

✅ Correct  
☐ Not Correct  
☐ Almost Correct

---

### <a name="sorting-data"></a>4. **Sorting Data**  
**Overview of SQL Concept:**  
The `ORDER BY` clause is used to sort the results of a query. You can sort in ascending (`ASC`) or descending (`DESC`) order.

**Practice Question:**

You have a table `products` with the following columns:
- `product_name` (TEXT)
- `price` (DECIMAL)

Write an SQL query to:
- Select `product_name` and `price`
- Sort the products by `price` in descending order

**User's Answer:**

```sql
SELECT product_name, price FROM products ORDER BY price DESC;
```

**Provided Answer:**

```sql
SELECT product_name, price FROM products ORDER BY price DESC;
```

**Validity of User's Answer:**

✅ Correct  
☐ Not Correct  
☐ Almost Correct

---

### <a name="using-like-for-pattern-matching"></a>5. **Using LIKE for Pattern Matching**  
**Overview of SQL Concept:**  
The `LIKE` operator is used for pattern matching in SQL. Wildcards `%` and `_` are used for flexible searches.

- `%` represents any sequence of characters.
- `_` represents a single character.

**Practice Question:**

You have a table `products` with the following columns:
- `product_name` (TEXT)

Write an SQL query to:
- Select `product_name`
- Filter for products whose names start with 'Smart'

**User's Answer:**

```sql
SELECT product_name FROM products WHERE product_name LIKE 'Smart%';
```

**Provided Answer:**

```sql
SELECT product_name FROM products WHERE product_name LIKE 'Smart%';
```

**Validity of User's Answer:**

✅ Correct  
☐ Not Correct  
☐ Almost Correct

---

### <a name="logical-operators"></a>6. **Logical Operators**  
**Overview of SQL Concept:**  
Logical operators (`AND`, `OR`, `NOT`) are used to combine multiple conditions in a `WHERE` clause.

**Practice Question:**

You have a table `employees` with the following columns:
- `first_name` (TEXT)
- `last_name` (TEXT)
- `salary` (DECIMAL)
- `department` (TEXT)

Write an SQL query to:
- Select `first_name`, `last_name`, and `salary`
- Filter for employees who work in the 'HR' department and earn more than 50,000

**User's Answer:**

```sql
SELECT first_name, last_name, salary FROM employees WHERE department = 'HR' AND salary > 50000;
```

**Provided Answer:**

```sql
SELECT first_name, last_name, salary FROM employees WHERE department = 'HR' AND salary > 50000;
```

**Validity of User's Answer:**

✅ Correct  
☐ Not Correct  
☐ Almost Correct

---

### <a name="joins"></a>7. **JOINs**  
**Overview of SQL Concept:**  
`JOIN` operations are used to combine rows from two or more tables based on a related column.

- `INNER JOIN`: Combines rows that have matching values in both tables.
- `LEFT JOIN`: Includes all rows from the left table, and matching rows from the right table.
- `RIGHT JOIN`: Includes all rows from the right table, and matching rows from the left table.

**Practice Question:**

You have two tables: `employees` and `departments`.

Table `employees` columns:
- `employee_id` (INTEGER)
- `first_name` (TEXT)
- `last_name` (TEXT)
- `department_id` (INTEGER)

Table `departments` columns:
- `department_id` (INTEGER)
- `department_name` (TEXT)

Write an SQL query to:
- Select `first_name`, `last_name`, and `department_name`
- Use an `INNER JOIN` to join `employees` and `departments` based on `department_id`

**User's Answer:**

```sql
SELECT first_name, last_name, department_name
FROM employees
INNER JOIN departments
ON employees.department_id = departments.department_id;
```

**Provided Answer:**

```sql
SELECT first_name, last_name, department_name
FROM employees
INNER JOIN departments
ON employees.department_id = departments.department_id;
```

**Validity of User's Answer:**

✅ Correct  
☐ Not Correct  
☐ Almost Correct

---

## Syntax for Advanced SQL concept

add this to the list of concepts

You're correct that we haven’t fully explored some of these topics in detail yet. Let's go through them in the order you mentioned:

---

### **Subqueries:**

1. **`IN` Clause with Subqueries:**
   - A subquery used with the `IN` operator helps you filter results based on a list of values returned by a subquery.
   - **Syntax:**
     ```sql
     SELECT column1, column2
     FROM table1
     WHERE column1 IN (SELECT column1 FROM table2 WHERE condition);
     ```
   
2. **`EXISTS` Clause with Subqueries:**
   - The `EXISTS` operator is used with a subquery to test if a subquery returns any rows. It returns `TRUE` if the subquery produces any results.
   - **Syntax:**
     ```sql
     SELECT column1, column2
     FROM table1
     WHERE EXISTS (SELECT 1 FROM table2 WHERE condition);
     ```

3. **Subqueries in the `SELECT` Clause:**
   - A subquery can be placed in the `SELECT` clause to calculate values for each row in the outer query.
   - **Syntax:**
     ```sql
     SELECT column1, (SELECT AVG(column2) FROM table2 WHERE table2.column1 = table1.column1) AS avg_value
     FROM table1;
     ```

4. **Subqueries in the `FROM` Clause:**
   - A subquery in the `FROM` clause allows you to treat the result of the subquery as a temporary table or derived table.
   - **Syntax:**
     ```sql
     SELECT t.column1, t.column2
     FROM (SELECT column1, column2 FROM table2 WHERE condition) AS t;
     ```

---

### **Window Functions:**

#### **Ranking Functions:**

1. **`ROW_NUMBER()`**:
   - Assigns a unique number to each row based on the specified order.
   - **Syntax:**
     ```sql
     ROW_NUMBER() OVER (PARTITION BY partition_expression ORDER BY order_expression)
     ```

2. **`RANK()`**:
   - Assigns a rank to each row, with gaps in the ranking for tied values.
   - **Syntax:**
     ```sql
     RANK() OVER (PARTITION BY partition_expression ORDER BY order_expression)
     ```

3. **`DENSE_RANK()`**:
   - Similar to `RANK()`, but no gaps are left in the ranking for tied values.
   - **Syntax:**
     ```sql
     DENSE_RANK() OVER (PARTITION BY partition_expression ORDER BY order_expression)
     ```

4. **`NTILE(n)`**:
   - Divides the result set into `n` roughly equal parts, assigning each row to one of the parts.
   - **Syntax:**
     ```sql
     NTILE(n) OVER (PARTITION BY partition_expression ORDER BY order_expression)
     ```

---

#### **Aggregate Functions (With Windowing)**:

1. **`SUM()`**:
   - Returns the sum of a specified expression across a set of rows.
   - **Syntax:**
     ```sql
     SUM(expression) OVER (PARTITION BY partition_expression ORDER BY order_expression)
     ```

2. **`AVG()`**:
   - Returns the average of a specified expression across a set of rows.
   - **Syntax:**
     ```sql
     AVG(expression) OVER (PARTITION BY partition_expression ORDER BY order_expression)
     ```

3. **`COUNT()`**:
   - Returns the count of rows for a specified expression.
   - **Syntax:**
     ```sql
     COUNT(expression) OVER (PARTITION BY partition_expression ORDER BY order_expression)
     ```

4. **`MIN()`**:
   - Returns the minimum value of a specified expression across a set of rows.
   - **Syntax:**
     ```sql
     MIN(expression) OVER (PARTITION BY partition_expression ORDER BY order_expression)
     ```

5. **`MAX()`**:
   - Returns the maximum value of a specified expression across a set of rows.
   - **Syntax:**
     ```sql
     MAX(expression) OVER (PARTITION BY partition_expression ORDER BY order_expression)
     ```

---

#### **Value Functions:**

1. **`LEAD()`**:
   - Returns the value of the expression for the next row in the result set, optionally with an offset and default value.
   - **Syntax:**
     ```sql
     LEAD(expression, offset, default) OVER (PARTITION BY partition_expression ORDER BY order_expression)
     ```

2. **`LAG()`**:
   - Returns the value of the expression for the previous row in the result set, optionally with an offset and default value.
   - **Syntax:**
     ```sql
     LAG(expression, offset, default) OVER (PARTITION BY partition_expression ORDER BY order_expression)
     ```

---

#### **Windowing Functions:**

1. **`FIRST_VALUE()`**:
   - Returns the first value of the specified expression in the result set, based on the window frame.
   - **Syntax:**
     ```sql
     FIRST_VALUE(expression) OVER (PARTITION BY partition_expression ORDER BY order_expression)
     ```

2. **`LAST_VALUE()`**:
   - Returns the last value of the specified expression in the result set, based on the window frame.
   - **Syntax:**
     ```sql
     LAST_VALUE(expression) OVER (PARTITION BY partition_expression ORDER BY order_expression)
     ```

---

#### **Statistical Functions:**

1. **`CUME_DIST()`**:
   - Calculates the cumulative distribution of a value within the result set, showing the relative rank of a value.
   - **Syntax:**
     ```sql
     CUME_DIST() OVER (PARTITION BY partition_expression ORDER BY order_expression)
     ```

2. **`PERCENT_RANK()`**:
   - Calculates the relative rank of a value within the result set, as a percentage.
   - **Syntax:**
     ```sql
     PERCENT_RANK() OVER (PARTITION BY partition_expression ORDER BY order_expression)
     ```

---



## Concepts Not Covered Yet

- **Subqueries**: Writing queries inside other queries.
- **Aggregation Functions**: Using functions like `COUNT()`, `AVG()`, `MAX()`, `MIN()`, and `SUM()` in queries.
- **Case Statements**: Conditional logic within queries.
- **Indexes**: Improving query performance through indexing.
- **Data Modifications (INSERT, UPDATE, DELETE)**: Adding, updating, and removing records.
- **Transactions**: Using `COMMIT`, `ROLLBACK`, and `SAVEPOINT` for handling transactions.
- **SELF JOIN**: A join where a table is joined with itself, typically used for finding relationships within the same dataset (e.g., finding pairs of employees that work in the same department).
- **Triggers**: Automating actions like updating or inserting data in response to certain changes in the database.
- **Views**: Storing complex queries as reusable views that can be referenced like tables.
- **Stored Procedures**: Writing SQL code that can be stored and reused multiple times, often for common tasks.
- **Foreign Keys and Referential Integrity**: Defining relationships between tables and ensuring data consistency.
- **Normalization & Denormalization**: Structuring a database to minimize redundancy and ensure consistency, and when to denormalize for performance.
