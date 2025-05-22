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
![image](https://github.com/user-attachments/assets/ee6b57ac-518d-4d94-8c2a-72cfe5e96c46)


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
    orders o
JOIN 
    customer c ON o.customer_id = c.customer_id
JOIN 
    salesman s ON o.salesman_id = s.salesman_id;

```

**Output:**
![image](https://github.com/user-attachments/assets/8383e64b-15e2-4980-93b8-ae10a7bb70d3)


**Question 2**
---
![image](https://github.com/user-attachments/assets/7e674031-c432-4c80-a76a-9f5622062085)


```sql
SELECT 
    p.*
FROM 
    patients p
INNER JOIN 
    appointments a ON p.patient_id = a.patient_id
WHERE 
    a.appointment_date BETWEEN '2024-02-01' AND '2024-02-28';

```

**Output:**

![image](https://github.com/user-attachments/assets/2a14e8a2-6789-4a0e-bbc5-9ff29e79f6f7)


**Question 3**
---
![image](https://github.com/user-attachments/assets/63cabb6d-b901-4208-a5b1-bc3bb18f4e98)


```sql
SELECT 
    c.cust_name AS "Customer Name", 
    c.city AS "city", 
    s.name AS "Salesman", 
    s.city AS "city", 
    s.commission
FROM 
    customer c
INNER JOIN 
    salesman s ON c.salesman_id = s.salesman_id
WHERE 
    c.city != s.city 
    AND s.commission > 0.12;

```

**Output:**

![image](https://github.com/user-attachments/assets/16241bad-53e7-40c6-8cfe-8a21892ef880)


**Question 4**
---
![image](https://github.com/user-attachments/assets/66692f70-715e-4edb-9bbb-7550cf5d0915)


```sql
SELECT 
    s.name AS salesman_name,
    c.cust_name AS customer_name
FROM 
    salesman s
LEFT JOIN 
    customer c ON s.salesman_id = c.salesman_id;

```

**Output:**

![image](https://github.com/user-attachments/assets/df418e11-a7aa-4ccd-b741-881d52a8e4b4)


**Question 5**
---
![image](https://github.com/user-attachments/assets/9c0432a9-26e7-4b9d-84ae-84707a3bfc9f)


```sql
SELECT 
    c.cust_name AS "Customer Name",
    c.city AS "city",
    s.name AS "Salesman",
    s.commission
FROM 
    customer c
JOIN 
    salesman s ON c.salesman_id = s.salesman_id
WHERE 
    s.commission > 0.12;

```

**Output:**
![image](https://github.com/user-attachments/assets/cab62c64-726f-4b3b-b9a5-c8552d7b9017)


**Question 6**
---
![image](https://github.com/user-attachments/assets/b280fbdc-de00-4266-bfd5-e9814b23894a)


```sql
SELECT 
    c.cust_name AS cust_name,
    c.city AS city,
    c.grade,
    s.name AS Salesman,
    s.city AS 'city'
FROM 
    customer c
JOIN 
    salesman s ON c.salesman_id = s.salesman_id
WHERE 
    c.grade < 300
ORDER BY 
    c.customer_id ASC;

```

**Output:**

![image](https://github.com/user-attachments/assets/046876d9-3f12-4ea7-8472-1dbe4f7e4442)


**Question 7**
---
![image](https://github.com/user-attachments/assets/7dedb7dc-18df-4a09-beb2-ee0e8e9c95d9)


```sql
SELECT 
    s.name AS name,
    c.cust_name,
    c.city,
    c.grade,
    c.salesman_id
FROM 
    salesman s
LEFT JOIN 
    customer c ON s.salesman_id = c.salesman_id
WHERE 
    c.grade <= 100;

```

**Output:**
![image](https://github.com/user-attachments/assets/e9d0133c-ea24-4b3a-9cfa-691c1577bfad)


**Question 8**
---
![image](https://github.com/user-attachments/assets/f7a0bbe9-4341-4152-b396-7ee0f6d2862e)


```sql
SELECT 
    o.ord_no,
    o.purch_amt,
    c.cust_name,
    c.city
FROM 
    orders o
JOIN 
    customer c ON o.customer_id = c.customer_id
WHERE 
    o.purch_amt BETWEEN 500 AND 2000;

```

**Output:**
![image](https://github.com/user-attachments/assets/7ebca1e7-0cf9-4cdd-a712-7bd6b0541632)


**Question 9**
---
![image](https://github.com/user-attachments/assets/e88d3c5b-2f28-4b2c-8554-2d4256e59edf)


```sql
SELECT 
    p.first_name,
    p.last_name
FROM 
    patients p
INNER JOIN 
    surgeries s ON p.patient_id = s.patient_id
WHERE 
    s.surgery_date BETWEEN '2024-01-01' AND '2024-01-31';

```

**Output:**
![image](https://github.com/user-attachments/assets/af43d9b5-566b-4115-a644-2608323e70a8)


**Question 10**
---
![image](https://github.com/user-attachments/assets/2ce23921-6ebb-4a5a-a3a4-4ff711f8d875)


```sql
SELECT 
    p.date_of_birth, 
    a.*
FROM 
    patients p
INNER JOIN 
    appointments a ON p.patient_id = a.patient_id
WHERE 
    p.first_name = 'Alice';

```

**Output:**

![image](https://github.com/user-attachments/assets/c55e186b-99ff-419d-88df-ff32eaa6a5c1)


## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
