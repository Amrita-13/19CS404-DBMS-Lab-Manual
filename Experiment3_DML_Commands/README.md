# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
--
<img width="724" height="406" alt="image" src="https://github.com/user-attachments/assets/dec7e1db-74e9-4d95-98bd-2c06b75d34e7" />


```sql
UPDATE products
SET reorder_lvl = 40
WHERE category = 'Grocery';
```

**Output:**

<img width="1302" height="242" alt="image" src="https://github.com/user-attachments/assets/24ec3f9e-b407-4828-9c63-f587df97b03a" />


**Question 2**
---
<img width="505" height="144" alt="image" src="https://github.com/user-attachments/assets/a15e344f-3108-41da-8cd5-e69d740a1c37" />


```sql
UPDATE sales
SET sell_price = sell_price * 1.05
WHERE product_id = 15
  AND sale_date = '2023-01-31';
```

**Output:**

<img width="974" height="253" alt="image" src="https://github.com/user-attachments/assets/924fdbac-d6c4-4b79-bd4b-f95faa1364d1" />


**Question 3**
---
<img width="424" height="274" alt="image" src="https://github.com/user-attachments/assets/18be4d4e-e182-4d38-b80e-7daa1ebd021d" />


```sql
SELECT order_no, order_date, purch_amt
FROM orders
WHERE salesman_id = 5001;
```

**Output:**

<img width="407" height="253" alt="image" src="https://github.com/user-attachments/assets/06ce1966-fa6c-4586-b6a6-d33a849335dd" />


**Question 4**
---
<img width="364" height="116" alt="image" src="https://github.com/user-attachments/assets/37e3d584-d47b-40d1-9fe5-7ad94e17c0c7" />


```sql
UPDATE products
SET availability = availability * 2
WHERE product_id = 1;
```

**Output:**

<img width="676" height="154" alt="image" src="https://github.com/user-attachments/assets/927f9f8c-717c-41fd-a60e-cffcdb6c806e" />


**Question 5**
---
<img width="439" height="278" alt="image" src="https://github.com/user-attachments/assets/b5bc1d7b-a9a3-428f-996f-dc73d5691aa7" />


```sql
UPDATE PRODUCTS
SET sell_price = ROUND(sell_price * 1.10, 2)
WHERE supplier_id = 6;
```

**Output:**

<img width="1221" height="311" alt="image" src="https://github.com/user-attachments/assets/345fd60d-bdb5-4c83-a6b8-88461530b7f6" />


**Question 6**
---
<img width="785" height="232" alt="image" src="https://github.com/user-attachments/assets/b50512ab-dd3c-4f55-965b-265887c0385c" />


```sql
DELETE FROM Customer
WHERE CUST_COUNTRY NOT IN ('India', 'USA');
```

**Output:**

<img width="1662" height="330" alt="image" src="https://github.com/user-attachments/assets/782658c7-4bb4-4682-b22e-1a1150097c98" />


**Question 7**
---
<img width="859" height="370" alt="image" src="https://github.com/user-attachments/assets/574a99b2-17ce-47b8-b210-922c5dad0916" />


```sql
DELETE FROM Customer
WHERE GRADE >= 2;
```

**Output:**

<img width="400" height="357" alt="image" src="https://github.com/user-attachments/assets/4135c7af-daa9-411d-8e7c-848b223f91b2" />


**Question 8**
---
<img width="938" height="387" alt="image" src="https://github.com/user-attachments/assets/31e16bfb-1c25-47f3-a41e-a1dffbf5f8ca" />


```sql
DELETE FROM Customer
WHERE LENGTH(CUST_NAME) = 6;
```

**Output:**

<img width="1591" height="404" alt="image" src="https://github.com/user-attachments/assets/0fd11715-448c-49d0-b2e7-8db45b98f39c" />


**Question 9**
---
<img width="775" height="234" alt="image" src="https://github.com/user-attachments/assets/38b10b32-d581-4974-9214-c8f2567fd1ae" />


```sql
DELETE FROM Customer
WHERE GRADE % 2 <> 0;
```

**Output:**

<img width="1581" height="244" alt="image" src="https://github.com/user-attachments/assets/205cdc3b-a517-4f6a-962c-f642d2bcfdac" />


**Question 10**
---
<img width="818" height="279" alt="image" src="https://github.com/user-attachments/assets/8c088c74-20d2-4ecf-828c-5bfb82e2a8d9" />


```sql
DELETE FROM Customer
WHERE CUST_NAME LIKE '%Holmes%';
```

**Output:**

<img width="1624" height="305" alt="image" src="https://github.com/user-attachments/assets/351f7344-0e05-4ae8-b921-9ee6d991cf12" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
