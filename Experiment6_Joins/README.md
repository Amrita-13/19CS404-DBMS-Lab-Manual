# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**
--
<img width="1303" height="490" alt="image" src="https://github.com/user-attachments/assets/3347ee4e-ce42-4464-92ca-e7b2dd3897f3" />


```sql
SELECT 
    c.cust_name,
    o.ord_no,
    o.ord_date,
    o.purch_amt
FROM 
    customer AS c
LEFT JOIN 
    orders AS o
ON 
    c.customer_id = o.customer_id
WHERE 
    o.purch_amt > 1000;

```

**Output:**

<img width="1278" height="706" alt="image" src="https://github.com/user-attachments/assets/30abd923-fc8e-4e59-8ec7-21dfe931812d" />



**Question 2**
---
<img width="1284" height="636" alt="image" src="https://github.com/user-attachments/assets/a7027675-e4be-4937-8851-a51d00fccb19" />


```sql
SELECT 
    p.first_name AS patient_name,
    t.*
FROM 
    patients AS p
INNER JOIN 
    test_results AS t
ON 
    p.patient_id = t.patient_id
WHERE 
    p.admission_date BETWEEN '2024-01-01' AND '2024-01-31';

```

**Output:**

<img width="1282" height="334" alt="image" src="https://github.com/user-attachments/assets/81d8c483-6034-4884-bcd6-7585541b8f10" />


**Question 3**
---
<img width="930" height="650" alt="image" src="https://github.com/user-attachments/assets/b4105259-9a5f-4416-be83-ed52720f2cf5" />


```sql
SELECT 
    o.ord_no,
    o.purch_amt,
    c.cust_name,
    c.city
FROM 
    orders AS o
INNER JOIN 
    customer AS c
ON 
    o.customer_id = c.customer_id
WHERE 
    o.purch_amt BETWEEN 500 AND 2000;

```

**Output:**

<img width="946" height="381" alt="image" src="https://github.com/user-attachments/assets/53fcf036-69e6-4fc9-9eb0-557959909403" />


**Question 4**
---
<img width="694" height="737" alt="image" src="https://github.com/user-attachments/assets/340be3e9-b63f-4088-9e4e-b471c49b5dc8" />


```sql
SELECT 
    o.ord_no,
    o.purch_amt,
    o.ord_date,
    c.cust_name,
    c.city AS customer_city,
    c.grade,
    s.name AS salesman_name,
    s.city AS salesman_city,
    s.commission
FROM 
    orders AS o
INNER JOIN 
    customer AS c ON o.customer_id = c.customer_id
INNER JOIN 
    salesman AS s ON o.salesman_id = s.salesman_id;

```

**Output:**

<img width="1345" height="645" alt="image" src="https://github.com/user-attachments/assets/12dbb526-9fc8-4a7d-a312-aacf1a2d7aa7" />


**Question 5**
---
<img width="1347" height="350" alt="image" src="https://github.com/user-attachments/assets/db5f54a8-0f07-4b75-a26b-f8b2168c070a" />


```sql
SELECT 
    p.first_name AS patient_name,
    d.first_name AS doctor_name
FROM 
    patients AS p
INNER JOIN 
    doctors AS d
ON 
    p.doctor_id = d.doctor_id
WHERE 
    p.discharge_date IS NULL;

```

**Output:**

<img width="390" height="293" alt="image" src="https://github.com/user-attachments/assets/656158cd-8276-459c-a2e1-c0443a857bda" />


**Question 6**
---
<img width="679" height="742" alt="image" src="https://github.com/user-attachments/assets/cde26bbd-85bb-4137-a0b5-ad75c7c37df7" />


```sql
SELECT 
    o.ord_no,
    o.ord_date,
    o.purch_amt,
    c.cust_name AS "Customer Name",
    c.grade,
    s.name AS Salesman,
    s.commission
FROM 
    orders o
JOIN 
    customer c ON o.customer_id = c.customer_id
JOIN 
    salesman s ON o.salesman_id = s.salesman_id;

```

**Output:**

<img width="1036" height="650" alt="image" src="https://github.com/user-attachments/assets/894c0a5c-943d-4865-aab7-2386343088c3" />


**Question 7**
---
<img width="679" height="483" alt="image" src="https://github.com/user-attachments/assets/a9736ae6-ef8c-4d76-8983-209d59a53ffb" />


```sql
SELECT
    c.cust_name AS "Customer Name",
    c.city,
    s.name AS Salesman,
    s.commission
FROM
    customer c
JOIN
    salesman s ON c.salesman_id = s.salesman_id;

```

**Output:**

<img width="707" height="504" alt="image" src="https://github.com/user-attachments/assets/6b026e17-b8d9-4a94-a9db-52dbf31af8de" />


**Question 8**
---
<img width="1316" height="343" alt="image" src="https://github.com/user-attachments/assets/a6b54c6a-7e72-47d4-89d0-f01a2aaf4aef" />


```sql
SELECT p.*
FROM patients p
INNER JOIN test_results t ON p.patient_id = t.patient_id
WHERE t.test_name IN ('Blood Test', 'Blood Pressure')
  AND t.result NOT LIKE '%Normal%';

```

**Output:**

<img width="1108" height="249" alt="image" src="https://github.com/user-attachments/assets/6481f54c-0610-48c8-81fa-253cc5a6b05d" />


**Question 9**
---
<img width="775" height="497" alt="image" src="https://github.com/user-attachments/assets/c7e3c731-722a-4708-b497-4e12c73273c8" />


```sql
SELECT 
    c.cust_name,
    c.city,
    c.grade,
    s.name AS Salesman,
    s.city
FROM 
    customer c
JOIN 
    salesman s ON c.salesman_id = s.salesman_id
ORDER BY 
    c.customer_id ASC;


```

**Output:**

<img width="823" height="503" alt="image" src="https://github.com/user-attachments/assets/18aeea54-2425-4f60-bdb7-276fca4051dd" />


**Question 10**
---
<img width="1398" height="225" alt="image" src="https://github.com/user-attachments/assets/708e65e6-88cd-4dcf-bf63-84fd6b40747b" />


```sql
SELECT 
    s.name, 
    c.cust_name, 
    c.city, 
    c.grade, 
    c.salesman_id
FROM 
    salesman s
LEFT JOIN 
    customer c ON s.salesman_id = c.salesman_id
WHERE 
    s.salesman_id IN (
        SELECT salesman_id
        FROM customer
        GROUP BY salesman_id
        HAVING COUNT(*) > 1
    );

```

**Output:**

<img width="842" height="360" alt="image" src="https://github.com/user-attachments/assets/6e3d950c-d1c5-427d-9f1e-1513820f3daa" />



## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
