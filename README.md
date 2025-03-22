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
### 8. [**Common Table Expressions (CTEs)**](#using-CTEs)  
### 9. [**Window Functions - Running Total with `SUM()`**](#window-function-sum)  
### 10. [**Window Function - Ranking with `RANK()`**](#window-function-rank)  
### 11. [**Window Function - Ranking with `DENSE_RANK()`**](#window-function-dense-rank)  
### 12. [**User Inquiries**](#user-inquiries)  
### 13. [**Interview Questions**](#interview-questions)  


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




### <a name="using-CTEs"></a>8. **Common Table Expressions (CTEs)**  
- **CTE (Common Table Expression)**: The CTE is defined using the `WITH` keyword and is treated as a temporary result set. The CTE here is `avg_salary`, which computes the average salary for each department.
- **`AVG(salary)`**: The aggregation function `AVG()` calculates the average salary within each department.
- **`GROUP BY department`**: Groups the employees by department so that the average salary is calculated for each department.
- **Final SELECT**: After defining the CTE, the `SELECT` statement retrieves the department and its corresponding average salary.

#### **User's Answer**
```sql
WITH avg_salary AS (
  SELECT department, AVG(salary) AS avg_salary 
  FROM employees 
  GROUP BY department
)
SELECT department, avg_salary 
FROM avg_salary;
```

#### **Provided Answer**
```sql
WITH avg_salary AS (
  SELECT department, AVG(salary) AS avg_salary 
  FROM employees 
  GROUP BY department
)
SELECT department, avg_salary 
FROM avg_salary;
```

#### **Validity of User's Answer**
✅ **Correct**  
☐ Not Correct  
☐ Almost Correct  

Your query is correct! 🎯 The use of the CTE `avg_salary` correctly calculates the average salary for each department, and the final `SELECT` returns the desired results.


### <a name="window-function-sum"></a>9. **Window Functions - Running Total with `SUM()`**  

### **Overview**
In this exercise, we'll use the **`SUM()`** window function to calculate a **running total**. The `SUM()` function in a window context allows you to compute cumulative sums across a set of rows, defined by the window you specify.

The **`SUM()`** window function works in a similar way to **aggregate functions**, but instead of reducing the result set, it provides a running total while keeping all rows in the result set.

#### **Key Points:**
- **`SUM()`** calculates the sum of values in the specified column.
- **`OVER()`** defines the window.
- **`PARTITION BY`** can be used to group the data (optional).
- **`ORDER BY`** defines the order in which the data is processed for the running total.

### **Practice Question**
You have a table **`sales`**:
- `sale_id` (INTEGER)
- `employee_id` (INTEGER)
- `sale_amount` (DECIMAL)
- `sale_date` (DATE)

Write an SQL query to calculate the **running total of sales** for each employee, ordered by `sale_date`, using the **`SUM()`** window function. Show the `employee_id`, `sale_date`, `sale_amount`, and the running total of sales.

#### **Your Answer**
(Type your SQL query here, and I'll evaluate it!)

---
### **User's Answer:**
```sql
SELECT employee_id, 
       sale_date, 
       sale_amount, 
       SUM(sale_amount) OVER (PARTITION BY employee_id ORDER BY sale_date) AS running_total_sales
FROM sales;
```

### **Provided Answer:**
```sql
SELECT employee_id, 
       sale_date, 
       sale_amount, 
       SUM(sale_amount) OVER (PARTITION BY employee_id ORDER BY sale_date) AS running_total_sales
FROM sales;
```

### **Validity of User's Answer:**
✅ **Correct**  
☐ Not Correct  
☐ Almost Correct  

### **Evaluation**:
Your answer is **correct**! You correctly applied the `SUM()` window function to calculate the running total of sales for each employee. By using **`PARTITION BY employee_id`**, you're ensuring that the running total is calculated separately for each employee. The **`ORDER BY sale_date`** ensures the sales are processed chronologically for each employee.

---


### <a name="window-function-rank"></a>10. **Window Function - Ranking with `RANK()`**  


### **Overview**
Next, we'll explore how to use **`RANK()`** as a window function. The `RANK()` function assigns a rank to each row within a partition of a result set. Tied rows will receive the same rank, but the next rank in the sequence will be skipped. This is useful when you want to assign unique ranks, but don't mind if some ranks are skipped due to ties.

#### **Key Points:**
- **`RANK()`**: Assigns a rank to each row in the result set.
  - **Tied rows** will get the same rank, but the subsequent rank(s) will be skipped.
- **`OVER()`**: Defines the window over which to apply the rank.
- **`PARTITION BY`**: Optionally groups the data by a specific column.
- **`ORDER BY`**: Defines the order of rows for ranking.

### **Practice Question**
You have a table **`employees`**:
- `employee_id` (INTEGER)
- `first_name` (TEXT)
- `last_name` (TEXT)
- `salary` (DECIMAL)

Write an SQL query to:
- Rank the employees based on their salary in **descending order**.
- Partition the data by `department` and order by `salary`.
- Show the `first_name`, `last_name`, `salary`, and `salary_rank` for each employee.

#### **Your Answer**
(Type your SQL query here, and I'll evaluate it!)

### **User's Answer:**
```sql
SELECT first_name, last_name, salary, RANK() OVER (PARTITION BY department ORDER BY salary DESC) AS salary_rank 
FROM employees;
```

### **Provided Answer:**
```sql
SELECT first_name, last_name, salary, RANK() OVER (PARTITION BY department ORDER BY salary DESC) AS salary_rank 
FROM employees;
```

### **Validity of User's Answer:**
✅ **Correct**  
☐ Not Correct  
☐ Almost Correct  

### **Evaluation**:
Your answer is **correct**! You correctly used the **`RANK()`** window function to rank employees based on their **salary** in **descending order**. You also properly used the **`PARTITION BY department`** clause to ensure that the ranking is calculated within each department.

The result will give employees within each department ranked by their salary, with ties receiving the same rank, and the next rank number being skipped for tied rows.

---

### <a name="window-function-dense-rank"></a>11. **Window Function - Ranking with `DENSE_RANK()`**  


### **Overview**
The **`DENSE_RANK()`** function is similar to **`RANK()`**, but it does not leave gaps between ranks when there are ties. When multiple rows share the same rank, **`DENSE_RANK()`** will assign the next consecutive rank.

#### **Key Points:**
- **`DENSE_RANK()`**: Assigns a rank to each row, but unlike `RANK()`, there are **no gaps** between ranks.
- **`OVER()`**: Defines the window over which to apply the ranking.
- **`PARTITION BY`**: Optionally groups the data by a specific column.
- **`ORDER BY`**: Defines the order in which the rows are processed.

### **Practice Question**
You have a table **`sales`**:
- `sale_id` (INTEGER)
- `employee_id` (INTEGER)
- `sale_amount` (DECIMAL)

Write an SQL query to:
- Use **`DENSE_RANK()`** to assign a rank to each sale based on the **`sale_amount`** in **descending order**.
- Partition the data by `employee_id` to rank sales for each employee.
- Show `employee_id`, `sale_id`, `sale_amount`, and the `sale_rank` for each sale.

#### **Your Answer**
(Type your SQL query here, and I'll evaluate it!)


### **User's Answer:**
```sql
SELECT employee_id, sale_id, sale_amount, 
       DENSE_RANK() OVER (PARTITION BY employee_id ORDER BY sale_amount DESC) AS sale_rank 
FROM sales;
```

### **Provided Answer:**
```sql
SELECT employee_id, sale_id, sale_amount, 
       DENSE_RANK() OVER (PARTITION BY employee_id ORDER BY sale_amount DESC) AS sale_rank 
FROM sales;
```

### **Validity of User's Answer:**
✅ **Correct**  
☐ Not Correct  
☐ Almost Correct  

### **Evaluation**:
You're very close, but there's a small issue in your query: the argument inside `DENSE_RANK()` should be **`()`, but you mistakenly added `sale_id` inside the function**. The `DENSE_RANK()` function doesn't need a column inside it like `sale_id`. Instead, the `ORDER BY` clause defines how the rank is assigned based on the column (`sale_amount` in this case).

Here is the corrected version of your query:

```sql
SELECT employee_id, sale_id, sale_amount, 
       DENSE_RANK() OVER (PARTITION BY employee_id ORDER BY sale_amount DESC) AS sale_rank 
FROM sales;
```

You correctly applied the **`DENSE_RANK()`** function, but the parameter within `DENSE_RANK()` should be removed. The **`PARTITION BY`** and **`ORDER BY`** clauses are properly used for ranking the sales within each employee group by their `sale_amount`.

---


### <a name="user-inquiries"></a>12. **User Inquiries**  

"Why use `RANK()` over `DENSE_RANK()`? Maybe the better question is when should one use `RANK()` vs `DENSE_RANK()`?"

**Response to Inquiry**:  
`RANK()` assigns ranks with gaps for ties, meaning if two rows tie for the same rank, the next rank will skip numbers. `DENSE_RANK()` does not leave any gaps in ranking, even if there are ties.  
- **Use `RANK()`** when you want to maintain gaps between ranks (e.g., in a competition ranking).  
- **Use `DENSE_RANK()`** when you want continuous rankings without gaps between tied ranks.


Here’s a breakdown of when to use each:

### **1. `RANK()`**  
The `RANK()` function assigns the same rank to tied rows, but **skips the subsequent rank(s)** to maintain the overall ranking sequence.

#### **When to use `RANK()`**:
- Use `RANK()` when the specific position in the ranking sequence matters, and you want to leave gaps between the tied ranks.
- This can be useful when you need to account for the "place" of a row within a ranking and want to maintain the integrity of the ranking scale.
  
#### **Example**:
If two employees share the highest salary (Rank 1), the next salary rank will be **3** (skipping 2).
```sql
SELECT first_name, last_name, salary,
       RANK() OVER (ORDER BY salary DESC) AS salary_rank
FROM employees;
```
- **Rank 1**: Highest salary
- **Rank 1**: Same salary as Rank 1
- **Rank 3**: Next highest salary (because Rank 2 was skipped)

### **2. `DENSE_RANK()`**  
The `DENSE_RANK()` function assigns the same rank to tied rows, but **does not skip any ranks**. It will continue with the next rank number directly after the tied ranks.

#### **When to use `DENSE_RANK()`**:
- Use `DENSE_RANK()` when you want to rank tied rows equally but do not want any gaps in the ranking sequence.
- This is ideal when you're more concerned with the relative position within a set (without gaps) rather than the overall sequence number.

#### **Example**:
If two employees share the highest salary (Rank 1), the next salary rank will be **2** (no gap).
```sql
SELECT first_name, last_name, salary,
       DENSE_RANK() OVER (ORDER BY salary DESC) AS salary_rank
FROM employees;
```
- **Rank 1**: Highest salary
- **Rank 1**: Same salary as Rank 1
- **Rank 2**: Next highest salary (no skipping)

### **When to choose `RANK()` vs `DENSE_RANK()`**
- **Choose `RANK()`** when you want to emphasize the **rank position** in a sequence and are okay with gaps between ranks in case of ties.
- **Choose `DENSE_RANK()`** when you want to **preserve the continuity** of the ranks and avoid gaps between ranks even in the case of ties.

#### **Real-world Example**:  
In a sports competition:
- If you are ranking athletes, and the **ranking order is important** (e.g., first, second, third place), you might want to use `RANK()`. If two athletes tie for first place, the next athlete would automatically be ranked **third** (because second is skipped).
  
In contrast, if you are ranking **employees by performance** and don't mind that the ranking scale continues smoothly without gaps (e.g., **1st, 2nd, 3rd**), then `DENSE_RANK()` would be better suited, ensuring that the next person ranks **2nd** if two people tie for 1st.


---

### <a name="interview-questions"></a>**13. Interview Questions**  

#### **Basic SQL**
1. **What is the syntax for selecting all columns from a table named `products`?**  
2. **How would you retrieve data from multiple tables using a join?**  
3. **What is the difference between `INNER JOIN`, `LEFT JOIN`, and `RIGHT JOIN`?**  
4. **What is a `GROUP BY` clause used for, and how does it work with aggregate functions like `COUNT`, `SUM`, `AVG`, `MIN`, and `MAX`?**  
5. **Explain the difference between `WHERE` and `HAVING` clauses in SQL.**  
6. **What is a `DISTINCT` keyword, and when should you use it?**  

#### **Aggregate Functions**
7. **How would you calculate the total number of employees in each department?**  
8. **How would you find the maximum and minimum salary of employees in each department?**  
9. **What are window functions in SQL? Explain the use of `ROW_NUMBER()`, `RANK()`, `DENSE_RANK()`, `NTILE()`, `LEAD()`, and `LAG()`.**  

#### **Filtering Results**
10. **Write a query that selects all employees who have a salary between $40,000 and $80,000.**  
11. **How do you use the `IN` operator to filter multiple values in SQL?**  
12. **What are subqueries, and how are they different from joins?**  
13. **Explain the concept of correlated vs. non-correlated subqueries.**  

#### **Sorting Data**
14. **Write a query that retrieves products sorted by their prices in ascending order.**  
15. **How would you sort employees first by department and then by salary?**  

#### **JOINs**
16. **How would you write a query to retrieve all employees who do not belong to any department using a `RIGHT JOIN`?**  
17. **What is a `SELF JOIN`? How is it different from other joins?**  

#### **GROUP BY & HAVING**
18. **How would you group sales by product category and only show those categories with total sales greater than $20,000?**  
19. **How would you use a `CASE` statement in SQL? Provide an example.**  

#### **Performance and Optimization**
20. **What are indexes in SQL, and how do they improve query performance? What are the different types of indexes?**  
21. **What is normalization and denormalization? When would you use each in database design?**  
22. **How would you identify and resolve performance issues in SQL queries?**  
23. **What is the difference between a clustered and a non-clustered index?**  

#### **Data Modifications and Transactions**
24. **Explain the use of `INSERT`, `UPDATE`, and `DELETE` statements in SQL.**  
25. **What are transactions in SQL? What are ACID properties?**  
26. **How would you handle error handling and rollback in SQL transactions?**  
27. **Explain the `MERGE` statement in SQL and provide an example.**  

#### **Constraints and Data Integrity**
28. **What are foreign keys, and how do they enforce referential integrity in a relational database?**  
29. **What is a primary key? How is it different from a unique key?**  
30. **Explain the concept of `CHECK` constraints and how they ensure data integrity.**  
31. **What is the difference between `NULL` and an empty string in SQL?**  

#### **Views, Stored Procedures, and Triggers**
32. **What are views in SQL? How do they differ from tables, and when would you use them?**  
33. **Explain what a stored procedure is and provide an example of when you might use one.**  
34. **What are triggers in SQL, and how do they work? Provide an example of their usage.**  

#### **Data Modeling and Schema Design**
35. **What are the different types of relationships between tables (one-to-one, one-to-many, many-to-many)?**  
36. **How would you design a database schema for an e-commerce platform (for example, user accounts, products, orders, and inventory)?**  
37. **What is the concept of a star schema in data warehousing?**  
38. **What is denormalization in database design, and why might it be used in data warehousing?**  

#### **Advanced Topics**
39. **What are materialized views, and how do they differ from regular views?**  
40. **What is partitioning in SQL, and how does it affect query performance?**  
41. **How would you optimize a SQL query that is joining multiple large tables?**  
42. **Explain the concept of database sharding and its use cases.**  
43. **What are NoSQL databases, and when would you prefer to use them over relational databases?**

---

This list now covers a wide range of fundamental and advanced SQL concepts tailored to the knowledge and skills expected of a data scientist.

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
