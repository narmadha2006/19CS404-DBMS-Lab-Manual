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
![image](https://github.com/user-attachments/assets/1d0270c9-2ca3-4e76-9c51-86b28587a59a)


```sql
UPDATE Products
SET reorder_lvl = 20
WHERE  quantity < 10
AND category = 'Snacks'
;
```

**Output:**

![image](https://github.com/user-attachments/assets/08ce4519-dd09-4899-bd36-b512e9ceac04)


**Question 2**
---
![image](https://github.com/user-attachments/assets/ccfc44dd-7ae5-46ff-8919-a9ee3febacf1)


```sql
UPDATE EMPLOYEES
SET first_name ='John'
WHERE department_id = 80 AND commission_pct < 0.35
;
```

**Output:**

![image](https://github.com/user-attachments/assets/38f205a8-b569-4fe7-8845-a5d1598e837a)


**Question 3**
---
![image](https://github.com/user-attachments/assets/8d9bc76d-8c00-4038-b7b9-23bbc0461a47)


```sql
UPDATE Employees
SET salary = salary + 500,email = 'updated'
WHERE job_id = 'SA_REP' AND commission_pct > 0.15
;
```

**Output:**

![image](https://github.com/user-attachments/assets/165c6ad8-1136-4acd-b91a-a0002a1fdb32)


**Question 4**
---
![image](https://github.com/user-attachments/assets/a4e23c14-5d09-4b5e-918b-066dc41d773a)


```sql
UPDATE SALES
SET total_sell_price = quantity * sell_price
WHERE product_id = 10
;
```

**Output:**

![image](https://github.com/user-attachments/assets/c9322814-75ab-4e04-b279-5d5755afe0b9)


**Question 5**
---
![image](https://github.com/user-attachments/assets/2115c1f5-02fa-45ce-86b7-c466f771f295)


```sql
DELETE FROM Customer
WHERE CUST_COUNTRY = 'UK'
AND WORKING_AREA= 'London'
AND GRADE < 3
;
```

**Output:**

![image](https://github.com/user-attachments/assets/1ce619fd-ab47-41b8-b0af-4455d8d817ef)


**Question 6**
---
![image](https://github.com/user-attachments/assets/ddde4c17-3d83-4228-ba44-2df5bfd01f66)


```sql
DELETE FROM Customer
WHERE CUST_CITY != 'New York'
AND OUTSTANDING_AMT > 5000
;
```

**Output:**

![image](https://github.com/user-attachments/assets/99c85b2d-c7d3-40f0-821f-08c71bd8faa8)


**Question 7**
---
![image](https://github.com/user-attachments/assets/a914d1bb-9fa0-4b56-bfe5-3890cef81cce)


```sql
DELETE FROM Doctors
WHERE doctor_id = 1
;
```

**Output:**

![image](https://github.com/user-attachments/assets/f7064aae-3e53-4d51-a190-0ba24d7cc793)


**Question 8**
---
![image](https://github.com/user-attachments/assets/fbaf3f7d-1d61-4228-a6b3-d46f5cf0c56a)


```sql
DELETE FROM Customer
WHERE GRADE >= 2
;
```

**Output:**

![image](https://github.com/user-attachments/assets/0bed664a-79ab-47b8-a2b2-6105cd9dc9d2)


**Question 9**
---
![image](https://github.com/user-attachments/assets/63e51ec0-0b2c-4232-a349-3b74e728f76a)


```sql
DELETE FROM Doctors
WHERE doctor_id BETWEEN 2 AND 4
;
```

**Output:**
![image](https://github.com/user-attachments/assets/118daed3-9465-4c6f-aa42-3ce0bebbd97b)


**Question 10**
---
![image](https://github.com/user-attachments/assets/625fd260-7f51-4b8b-9f6a-40768cda4802)


```sql
SELECT *
FROM customer
WHERE grade > 100
;
```

**Output:**

![image](https://github.com/user-attachments/assets/2cbee4e0-bcd8-4825-b8a7-882f67e27a7f)


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
