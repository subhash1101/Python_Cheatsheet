# ACID Properties

ACID is a set of four important properties that ensure database transactions are processed reliably and safely.

ACID stands for:

* Atomicity
* Consistency
* Isolation
* Durability

---

## 1. Atomicity

Atomicity means **"all or nothing"**.

If any part of a transaction fails, the entire transaction fails, and the database is returned to its previous state.

### Simple Example:

Suppose you transfer 1000 rupees from Account A to Account B:

If the system crashes after deducting money from A but before adding it to B, the transaction will be rolled back.

So either:

* Both operations happen
  OR
* None of them happen

---

## 2. Consistency

Consistency ensures the database always follows defined conditions.

After a committed transaction, the database must be in a valid state.

### Example:

If a table has a constraint:

* balance >= 0

A transaction cannot commit if it makes balance negative. If rules are violated, the transaction fails.


## 3. Isolation

Isolation ensures that multiple transactions running at the same time do not interfere with each other.

### Example:

Two users try to withdraw money from the same account at the same time.

Without isolation:

* Both may read the same balance.
* Both may deduct money.
* Final balance becomes incorrect.

So to prevent above situation isolation is needed

---

## 4. Durability

Durability means once a transaction is committed, the changes are permanent.

Even if the system crashes the data will not be lost.

### Example:

The data is safely stored on disk.

Even after restart, the changes remain.

---
---

# CAP Theorem 

CAP Theorem is a concept that explains the limitations of distributed systems.

CAP stands for:

* Consistency
* Availability
* Partition Tolerance

The theorem states:
* In a distributed system, you can guarantee only two out of the three properties at the same time.

---

## Distributed System

A distributed system is a system where multiple servers work together and communicate over a network.

Since these systems rely on networks, network failures can happen. CAP theorem helps us understand how systems behave during failures.

---

## 1. Consistency (C)

Every user sees the same data at the same time.

After a successful write, all future reads will return the updated value.


## 2. Availability (A)

Every request receives a response, even if some servers are down.
But it cannot fail to respond.


## 3. Partition Tolerance (P)

The system continues working even if communication between servers is broken.

A partition happens when:

* Network failure splits servers into groups
* Servers cannot talk to each other

---

## The Main Rule of CAP Theorem

When a network partition happens, you must choose:

* Consistency OR Availability

---

## Types of Systems Based on CAP

### 1. CP System (Consistency + Partition Tolerance)

These systems:

* Ensure data is always correct
* May reject requests during partition

---

### 2. AP System (Availability + Partition Tolerance)

These systems:

* Always respond
* May return outdated data temporarily

---

### 3. CA System (Consistency + Availability)

These systems:

* Work only when there is no network partition
* Not practical in large distributed systems

---
---

# SQL JOINS

A JOIN in SQL is used to combine rows from two or more tables based on a related column.

In relational databases:

* Data is stored in multiple tables.
* Tables are connected using relationships.

---

# Types of JOINS

## 1. INNER JOIN

Returns only matching rows from both tables.
If there is no match, the row is not included.

### Syntax:

```sql
SELECT c.name, o.product
FROM customers c
INNER JOIN orders o
ON c.customer_id = o.customer_id;
```

## 2. LEFT JOIN

Returns all rows from the left table matching rows from the right 
table. 
If no match, NULL is returned.

## 3. RIGHT JOIN

Returns all rows from the right table matching rows from the left table.
If no match, NULL is returned.


## 4. FULL JOIN

Returns all rows from both tables.
Matching rows are combined.
Non-matching rows show NULL.

## 5. CROSS JOIN

Returns every combination of rows from both tables.


---
---

# Aggregations

Aggregation means performing a calculation on multiple rows and returning a single result.

---

## Common Aggregate Functions

### 1. COUNT()

Counts the number of rows.

```sql
SELECT COUNT(*) FROM employees;
```

---

### 2. SUM()

Adds values from a column.

```sql
SELECT SUM(salary) FROM employees;
```

---

### 3. AVG()

Finds average value.

```sql
SELECT AVG(salary) FROM employees;
```

---

### 4. MAX()

Returns highest value.

```sql
SELECT MAX(salary) FROM employees;
```

---

### 5. MIN()

Returns lowest value.

```sql
SELECT MIN(salary) FROM employees;
```

---

# GROUP BY

GROUP BY is used to group rows that have the same values in a column.

### Example:

```sql
SELECT department, SUM(salary)
FROM employees
GROUP BY department;
```

Each department is grouped separately.

---

# Filters

Filters are used to restrict rows returned in a query.

---

## WHERE Clause

Used to filter rows.

Example:

```sql
SELECT * FROM employees
WHERE salary > 50000;
```

Only employees with salary greater than 50000 are shown.

---

## Multiple Conditions

### AND

```sql
SELECT * FROM employees
WHERE department = 'IT' AND salary > 50000;
```

Both conditions must be true.

---

### OR

```sql
SELECT * FROM employees
WHERE department = 'IT' OR department = 'HR';
```

At least one condition must be true.

---

### NOT

```sql
SELECT * FROM employees
WHERE NOT department = 'IT';
```

Excludes IT department.

---

## BETWEEN

Used for ranges.

```sql
SELECT * FROM employees
WHERE salary BETWEEN 40000 AND 60000;
```

Includes both 40000 and 60000.

---

## IN

Checks multiple values.

```sql
SELECT * FROM employees
WHERE department IN ('IT', 'HR');
```

---

## LIKE

Used for pattern matching.

```sql
SELECT * FROM employees
WHERE name LIKE 'A%';
```

Names starting with A.

Common patterns:

* % - many characters
---

## IS NULL

Used to check NULL values.

```sql
SELECT * FROM employees
WHERE salary IS NULL;
```

Important:
You cannot use = NULL.

---
---

# Normalization

## What is Normalization?

Normalization is the process of organizing data in a database to reduce duplication and improve data integrity.

Normalization divides large tables into smaller related tables.

---

## Types of Normal Forms

### First Normal Form (1NF)

Definition:
A table is in 1NF if:

* Each column contains atomic (single) values.

### Second Normal Form (2NF)

Definition:
A table is in 2NF if:

* It is already in 1NF.
* All non-key columns fully depend on the entire primary key.

---

### Third Normal Form (3NF)

Definition:
A table is in 3NF if:

* It is in 2NF.
* No transitive dependency exists.

---
---

# Indexes

An index is a database object that improves the speed of SELECT queries.

It works like an index in a book:
* Instead of scanning all data, the database quickly finds the location.

---

## Types of Indexes

### 1. Primary Index

Automatically created when PRIMARY KEY is defined.

Characteristics:
* Unique
* Not NULL

---

### 2. Composite Index

Index created on multiple columns.
Useful when queries filter using both columns.

---

### 3. Clustered Index

Determines the physical order of data in the table.
Only one clustered index per table.

---

### 4. Non-Clustered Index

Separate structure that stores pointer to table rows.
Multiple allowed.

---
---

# Transactions

A transaction is a group of SQL operations executed as a single unit.

---

## Transaction Commands

### BEGIN

Starts a transaction.

```sql
BEGIN;
```

---

### COMMIT

Saves changes permanently.

```sql
COMMIT;
```

---

### ROLLBACK

Undo changes.

```sql
ROLLBACK;
```

---

### SAVEPOINT

Creates intermediate checkpoint.

```sql
SAVEPOINT sp1;
```

---
---

# Locking Mechanism

Locking controls concurrent access to data.

Prevents multiple users from changing same data simultaneously.

---

## Types of Locks

### 1. Shared Lock (Read Lock)

Definition:
Multiple transactions can read data.
No one can modify it.

---

### 2. Exclusive Lock (Write Lock)

Definition:
Only one transaction can modify data.
Others must wait.

---

### 3. Row-Level Lock

Locks specific rows.

---

### 4. Table-Level Lock

Locks entire table.

---

## Locking Problems

### Deadlock

Two transactions wait for each other.
Database automatically detects and kills one.

### Blocking

One transaction waits until another finishes.

---
---

# Database Isolation Levels

Isolation level controls how transactions see changes made by other transactions.

---

## 1. Read Uncommitted

Definition:
Can read uncommitted data.

Problem:
Dirty reads possible.

---

## 2. Read Committed

Definition:
Can only read committed data.

Prevents:
Dirty reads

Allows:
Non-repeatable reads

---

## 3. Repeatable Read

Definition:
If a row is read, it cannot change during transaction.

Prevents:
Dirty reads
Non-repeatable reads

Allows:
Phantom reads

---

## 4. Serializable

Definition:
Highest isolation level.

Transactions behave as if executed one by one.

Prevents:
Dirty reads
Non-repeatable reads
Phantom reads

Slower but safest.

---

## Common Transaction Problems

Dirty Read:
Reading uncommitted data.

Non-Repeatable Read:
Same query gives different result.

Phantom Read:
New rows appear in repeated query.

---
---

# Triggers

A trigger is a special stored procedure that automatically runs when certain events happen.

Events:

* INSERT
* UPDATE
* DELETE

---

## Types of Triggers

### 1. BEFORE Trigger

Runs before event happens.


---

### 2. AFTER Trigger

Runs after event completes.


---

### 3. INSTEAD OF Trigger

Replaces the original operation.

---

### 4. Row-Level Trigger

Runs for each row affected.

---

### 5. Statement-Level Trigger

Runs once per SQL statement.

---

## Example

```sql
CREATE TRIGGER update_log
AFTER UPDATE ON employees
FOR EACH ROW
EXECUTE FUNCTION log_function();
```

---
---