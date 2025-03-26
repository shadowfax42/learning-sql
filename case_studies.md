
## SQL Case Studies


## Outline

1. [Case Study 1: Employee Management System](#case-study-1-employee-management-system)
2. [Case Study 2: E-commerce System](#case-study-2-e-commerce-system)
3. [Case Study 3: Library Management System](#case-study-3-library-management-system)
4. [Case Study 4: Hospital Patient Management](#case-study-4-hospital-patient-management)
5. [Case Study 5: University Course Enrollment](#case-study-5-university-course-enrollment)
6. [Case Study 6: Retail Store Sales Analysis](#case-study-6-retail-store-sales-analysis)
7. [Case Study 7: Bank Loan Approval System](#case-study-7-bank-loan-approval-system)
8. [Case Study 8: Event Management System](#case-study-8-event-management-system)
9. [Case Study 9: Inventory Management for a Warehouse](#case-study-9-inventory-management-for-a-warehouse)
10. [Case Study 10: Healthcare Insurance Claims](#case-study-10-healthcare-insurance-claims)

## Case Studies

### Case Study 1: Employee Management System

**Scenario**:  
You are tasked with creating an employee management system for a company. The system should store information about employees, departments, and the projects they work on. You need to write SQL queries to perform various tasks such as retrieving employee details, assigning employees to projects, and generating reports.

**Concepts Covered**: SELECT, WHERE, INSERT INTO, UPDATE, DELETE, INNER JOIN, LEFT JOIN, GROUP BY, HAVING, Subqueries

#### Tables:

1. **employees**
   - Columns: `employee_id` (integer, primary key), `name` (varchar), `department_id` (integer), `salary` (decimal)

2. **departments**
   - Columns: `department_id` (integer, primary key), `department_name` (varchar)

3. **projects**
   - Columns: `project_id` (integer, primary key), `project_name` (varchar)

4. **employee_projects**
   - Columns: `employee_id` (integer), `project_id` (integer)

#### Practice Questions:
1. Write a SQL query to retrieve the names of all employees working on a project named 'Project X'.
2. Write a SQL query to count the number of employees in each department.
3. Write a SQL query to find all projects that have no employees assigned.
4. Write a SQL query to insert a new employee into the 'employees' table.
5. Write a SQL query to update the salary of an employee.
6. Write a SQL query to delete an employee from the 'employees' table.

---

### Case Study 2: E-commerce System

**Scenario**:  
You are responsible for managing the database of an e-commerce system. The system should store information about products, customers, and orders. You need to write SQL queries to manage inventory, track customer orders, and generate sales reports.

**Concepts Covered**: SELECT, WHERE, ORDER BY, INNER JOIN, LEFT JOIN, GROUP BY, HAVING, UNION, Subqueries, Aggregate Functions

#### Tables:

1. **products**
   - Columns: `product_id` (integer, primary key), `product_name` (varchar), `price` (decimal)

2. **customers**
   - Columns: `customer_id` (integer, primary key), `customer_name` (varchar), `email` (varchar)

3. **orders**
   - Columns: `order_id` (integer, primary key), `customer_id` (integer), `order_date` (datetime)

4. **order_items**
   - Columns: `order_id` (integer), `product_id` (integer), `quantity` (integer)

#### Practice Questions:
1. Write a SQL query to generate a sales report showing the total sales amount for each product.
2. Write a SQL query to find the total number of orders placed by each customer.
3. Write a SQL query to list all customers who have not placed any orders.
4. Write a SQL query to retrieve product details and sort them by price in descending order.
5. Write a SQL query to find customers who placed orders in both January and February.
6. Write a SQL query to calculate the average order value for each customer.

---

### Case Study 3: Library Management System

**Scenario**:  
You are developing a library management system to keep track of books, members, and borrowings. You need to write SQL queries to manage book inventory, register new members, and track borrowings.

**Concepts Covered**: SELECT, WHERE, ORDER BY, INSERT INTO, UPDATE, DELETE, INNER JOIN, LEFT JOIN, GROUP BY, HAVING, Subqueries, Aggregate Functions, DISTINCT

#### Tables:

1. **books**
   - Columns: `book_id` (integer, primary key), `title` (varchar), `author` (varchar)

2. **members**
   - Columns: `member_id` (integer, primary key), `member_name` (varchar), `membership_date` (datetime)

3. **borrowings**
   - Columns: `borrowing_id` (integer, primary key), `book_id` (integer), `member_id` (integer), `borrow_date` (datetime), `return_date` (datetime)

#### Practice Questions:
1. Write a SQL query to find all books borrowed by a member named 'John Doe'.
2. Write a SQL query to count the number of books borrowed by each member.
3. Write a SQL query to list all books that have never been borrowed.
4. Write a SQL query to insert a new book into the 'books' table.
5. Write a SQL query to update the author of a book.
6. Write a SQL query to delete a book from the 'books' table.
7. Write a SQL query to retrieve distinct authors from the 'books' table.

---

### Case Study 4: Hospital Patient Management

**Scenario**:  
You are tasked with managing patient records, including admissions, discharges, treatments, and billing. You need to write SQL queries to analyze patient data, track treatments, and generate billing reports.

**Concepts Covered**: SELECT, WHERE, ORDER BY, INNER JOIN, LEFT JOIN, GROUP BY, HAVING, Subqueries, Aggregate Functions, DISTINCT, SQL Functions, SQL Views

#### Tables:

1. **patients**
   - Columns: `patient_id` (integer, primary key), `patient_name` (varchar), `date_of_birth` (date)

2. **admissions**
   - Columns: `admission_id` (integer, primary key), `patient_id` (integer), `admission_date` (datetime), `discharge_date` (datetime)

3. **treatments**
   - Columns: `treatment_id` (integer, primary key), `patient_id` (integer), `treatment_date` (datetime), `treatment_description` (varchar)

4. **billing**
   - Columns: `billing_id` (integer, primary key), `patient_id` (integer), `billing_date` (datetime), `amount` (decimal)

#### Practice Questions:
1. Write a SQL query to find all treatments provided to a patient named 'Jane Smith'.
2. Write a SQL query to calculate the total billing amount for each patient.
3. Write a SQL query to list all patients who have been admitted but not yet discharged.
4. Write a SQL query to create a view named 'patient_billing_view' that includes the 'patient_name' and total billing amount for each patient.
5. Write a SQL query to calculate the average amount billed per patient.
6. Write a SQL query to retrieve the patient names and their ranks based on the total billing amount.

---

### Case Study 5: University Course Enrollment

**Scenario**:  
You are tasked with managing course enrollments, student records, and grades at a university. You need to write SQL queries to track enrollments, calculate grades, and generate reports.

**Concepts Covered**: SELECT, WHERE, ORDER BY, INNER JOIN, LEFT JOIN, GROUP BY, HAVING, Subqueries, Aggregate Functions, DISTINCT, SQL Functions, SQL Views, Indexes

#### Tables:

1. **students**
   - Columns: `student_id` (integer, primary key), `student_name` (varchar), `enrollment_date` (date)

2. **courses**
   - Columns: `course_id` (integer, primary key), `course_name` (varchar), `credits` (integer)

3. **enrollments**
   - Columns: `enrollment_id` (integer, primary key), `student_id` (integer), `course_id` (integer), `grade` (varchar)

#### Practice Questions:
1. Write a SQL query to list all courses a student named 'Alice Johnson' is enrolled in.
2. Write a SQL query to calculate the GPA for each student based on their grades.
3. Write a SQL query to find all courses that have no students enrolled.
4. Write a SQL query to create a view named 'student_courses_view' that includes the 'student_name' and 'course_name' columns from the 'students' and 'courses' tables.
5. Write a SQL query to create an index on the 'course_id' column of the 'enrollments' table.
6. Write a SQL query to calculate the total number of credits each student is enrolled in.

---

### Case Study 6: Retail Store Sales Analysis

**Scenario**:  
You are tasked with analyzing sales data for a retail store. The system should store information about products, sales transactions, and customers. You need to write SQL queries to identify trends, best-selling products, and customer preferences.

**Concepts Covered**: SELECT, WHERE, ORDER BY, INNER JOIN, LEFT JOIN, GROUP BY, HAVING, Subqueries, Aggregate Functions, DISTINCT, SQL Functions, SQL Views, Indexes, Window Functions

#### Tables:

1. **products**
   - Columns: `product_id` (integer, primary key), `product_name` (varchar), `price` (decimal)

2. **customers**
   - Columns: `customer_id` (integer, primary key), `customer_name` (varchar), `email` (varchar)

3. **sales**
   - Columns: `sale_id` (integer, primary key), `customer_id` (integer), `sale_date` (datetime), `total_amount` (decimal)

4. **sale_items**
   - Columns: `sale_id` (integer), `product_id` (integer), `quantity` (integer), `price` (decimal)

#### Practice Questions:
1. Write a SQL query to find the total sales amount for each product.
2. Write a SQL query to list all customers who have made purchases in the last 30 days.
3. Write a SQL query to find the best-selling product in terms of quantity sold.
4. Write a SQL query to create a view named 'product_sales_view' that includes the 'product_name' and total sales amount for each product.
5. Write a SQL query to create an index on the 'customer_id' column of the 'sales' table.
6. Write a SQL query to calculate the total sales amount for each customer.
7. Write a SQL query to retrieve the product names and their ranks based on total sales amount.

---

### Case Study 7: Bank Loan Approval System

**Scenario**:  
You are responsible for managing the database of a bank's loan approval system. The system should store information about loan applications, approvals, and rejections. You need to write SQL queries to analyze loan data and identify trends.

**Concepts Covered**: SELECT, WHERE, ORDER BY, INNER JOIN, LEFT JOIN, GROUP BY, HAVING, Subqueries, Aggregate Functions, DISTINCT, SQL Functions, SQL Views, Indexes, Window Functions, CTEs

#### Tables:

1. **loans**
   - Columns: `loan_id` (integer, primary key), `customer_id` (integer), `loan_amount` (decimal), `application_date` (datetime), `status` (varchar)

2. **customers**
   - Columns: `customer_id` (integer, primary key), `customer_name` (varchar), `email` (varchar)

#### Practice Questions:
1. Write a SQL query to find the total loan amount approved for each customer.
2. Write a SQL query to list all loan applications that were rejected in the last 6 months.
3. Write a SQL query to calculate the average loan amount for approved loans.
4. Write a SQL query to create a view named 'customer_loans_view' that includes the 'customer_name' and total loan amount for each customer.
5. Write a SQL query to create an index on the 'customer_id' column of the 'loans' table.
6. Write a SQL query to calculate the total loan amount for each status (approved, rejected, pending).
7. Write a SQL query to retrieve the customer names and their ranks based on the total loan amount approved.

---

### Case Study 8: Event Management System

**Scenario**:  
You are tasked with managing an event management system. The system should store information about events, attendees, and feedback. You need to write SQL queries to track event details, attendee registrations, and feedback.

**Concepts Covered**: SELECT, WHERE, ORDER BY, INNER JOIN, LEFT JOIN, GROUP BY, HAVING, Subqueries, Aggregate Functions, DISTINCT, SQL Functions, SQL Views, Indexes, Window Functions, CTEs, CROSS JOIN

#### Tables:

1. **events**
   - Columns: `event_id` (integer, primary key), `event_name` (varchar), `event_date` (datetime)

2. **attendees**
   - Columns: `attendee_id` (integer, primary key), `attendee_name` (varchar), `email` (varchar)

3. **registrations**
   - Columns: `event_id` (integer), `attendee_id` (integer)

4. **feedback**
   - Columns: `feedback_id` (integer, primary key), `event_id` (integer), `attendee_id` (integer), `rating` (integer), `comments` (varchar)

#### Practice Questions:
1. Write a SQL query to list all attendees registered for an event named 'Tech Conference 2023'.
2. Write a SQL query to calculate the average rating for each event.
3. Write a SQL query to find all events that have no attendees registered.
4. Write a SQL query to create a view named 'event_feedback_view' that includes the 'event_name' and average rating for each event.
5. Write a SQL query to create an index on the 'attendee_id' column of the 'registrations' table.
6. Write a SQL query to calculate the total number of attendees for each event.
7. Write a SQL query to retrieve the event names and their ranks based on the average rating.

---

### Case Study 9: Inventory Management for a Warehouse

**Scenario**:  
You are responsible for managing the inventory of a warehouse. The system should store information about products, inventory levels, and restocking schedules. You need to write SQL queries to monitor inventory levels, track restocks, and optimize inventory management.

**Concepts Covered**: SELECT, WHERE, ORDER BY, INNER JOIN, LEFT JOIN, GROUP BY, HAVING, Subqueries, Aggregate Functions, DISTINCT, SQL Functions, SQL Views, Indexes, Window Functions, CTEs, Pivot Tables

#### Tables:

1. **products**
   - Columns: `product_id` (integer, primary key), `product_name` (varchar), `price` (decimal)

2. **inventory**
   - Columns: `product_id` (integer), `quantity` (integer), `last_restock_date` (datetime)

3. **restocks**
   - Columns: `restock_id` (integer, primary key), `product_id` (integer), `restock_date` (datetime), `quantity` (integer)

#### Practice Questions:
1. Write a SQL query to find the current inventory level for each product.
2. Write a SQL query to list all products that need to be restocked (quantity < 10).
3. Write a SQL query to find the total quantity restocked for each product in the last 6 months.
4. Write a SQL query to create a view named 'inventory_status_view' that includes the 'product_name' and current inventory level for each product.
5. Write a SQL query to create an index on the 'product_id' column of the 'inventory' table.
6. Write a SQL query to calculate the total restocked quantity for each product.
7. Write a SQL query to retrieve the product names and their ranks based on the total quantity restocked.

---

### Case Study 10: Healthcare Insurance Claims

**Scenario**:  
You are tasked with managing insurance claims for a healthcare provider. The system should store information about claims, approvals, and payments. You need to write SQL queries to analyze claim data and generate reports.

**Concepts Covered**: SELECT, WHERE, ORDER BY, INNER JOIN, LEFT JOIN, GROUP BY, HAVING, Subqueries, Aggregate Functions, DISTINCT, SQL Functions, SQL Views, Indexes, Window Functions, CTEs

#### Tables:

1. **claims**
   - Columns: `claim_id` (integer, primary key), `patient_id` (integer), `claim_date` (datetime), `status` (varchar), `amount` (decimal)

2. **patients**
   - Columns: `patient_id` (integer, primary key), `patient_name` (varchar), `date_of_birth` (date)

3. **payments**
   - Columns: `payment_id` (integer, primary key), `claim_id` (integer), `payment_date` (datetime), `amount` (decimal)

#### Practice Questions:
1. Write a SQL query to find the total claim amount approved for each patient.
2. Write a SQL query to list all claims that have not been paid.
3. Write a SQL query to calculate the average claim amount for each status (approved, rejected, pending).
4. Write a SQL query to create a view named 'patient_claims_view' that includes the 'patient_name' and total claim amount for each patient.
5. Write a SQL query to create an index on the 'patient_id' column of the 'claims' table.
6. Write a SQL query to calculate the total claim amount for each status (approved, rejected, pending).
7. Write a SQL query to retrieve the patient names and their ranks based on the total claim amount approved.

---