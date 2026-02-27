
# AMA
---

## 1. Difference between UNION and UNION ALL ?

Both UNION and UNION ALL are used to vertically concatenate the results of two or more statements.
The difference is that:

* **UNION** – Removes duplicate rows.
* **UNION ALL** – Keeps duplicates.

---

## 2. What is the use of COMMIT and ROLLBACK ?

* **COMMIT** – It is a TCL command which is used to save changes permanently.
* **ROLLBACK** – It is also a TCL command which undoes all changes made in the current transaction and restores the database to the state it was in after the last COMMIT.

---
 
## 3. Difference between INNER JOIN and CROSS JOIN ?

* **INNER JOIN** – Returns matching rows from both tables when joining tables.
* **CROSS JOIN** – Returns the Cartesian product (all combinations) of rows from the tables which are being joined.

---

## 4. What is PRIMARY KEY?

* Uniquely identifies each row.
* Cannot be **NULL** and must be **unique**.

---

## 5. What is Set and What is Dictionary?

### Set:

* Stores unique elements.
* It is unordered.

### Dictionary:

* Stores data in key-value pairs.
* Keys must be unique, values can be duplicated.

---

## 6. Which command is used to describe a table in terminal?

`\d` is used to show tables in a database.

But if we need the schema of a single table:

```
\d TABLE_NAME
```

---

## 7. What happens when a Set is converted to List?

* Order may change.
* Duplicates are still not present.

---

## 8. Difference between LEFT JOIN and RIGHT JOIN ?

* **LEFT JOIN** → All rows from the left table + matching rows from the right.
* **RIGHT JOIN** → All rows from the right table + matching rows from the left.

---

## 9. What is Normalization and its types?

Normalization is the process of reducing redundancy and increasing the integrity of the table.

Main types of Normalization are:

* **1NF** – Eliminating duplicate records.
* **2NF** – Eliminating partial dependency.
* **3NF** – Eliminating transitive dependency.
* **BCNF** – The stricter form of 3NF.

---

## 10. Difference between VARCHAR and TEXT ?

* **VARCHAR** – Defined length `n`. Limits vary by different Database Management Systems.
* **TEXT** – Very large or unlimited length strings.

---

## 11. What is S in SOLID?

* S refers to **Single Responsibility Principle**.
* A class should have only one reason to change.

---

## 12. What is LIMIT in SQL?

Limits the number of rows returned from a `SELECT` query.

Example:

```
SELECT * FROM table LIMIT 5;
```

---

## 13. What is OFFSET in SQL?

Skips a number of rows before returning results.
Used with LIMIT.

Example:

```
LIMIT 5 OFFSET 10;
```

---

## 14. What is TRUNCATE in SQL?

* Removes all rows.
* Faster than DELETE.
* Cannot use WHERE clause.

---

## 15. What is DELETE in SQL?

* Removes specific rows.
* Can use WHERE.

---

## 16. Which is faster, TRUNCATE or DELETE? Why?

**TRUNCATE is faster**

Because:

* Doesn’t scan rows.
* Directly deallocates data pages.

