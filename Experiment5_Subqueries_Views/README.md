# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**
--
![image](https://github.com/user-attachments/assets/ac246087-e48f-4827-a8c3-9fae841e2204)


```sql
SELECT *
FROM Medications
WHERE dosage = (
    SELECT MAX(dosage)
    FROM Medications
);

```

**Output:**

![image](https://github.com/user-attachments/assets/cd81bb45-8abd-43a2-978c-39dc9a993e45)


**Question 2**
---
![image](https://github.com/user-attachments/assets/f5c85777-ff37-4075-9bed-0c331b4fbf03)


```sql
SELECT o.ord_no, o.purch_amt, o.ord_date, o.customer_id, o.salesman_id
FROM orders o
JOIN salesman s ON o.salesman_id = s.salesman_id
WHERE s.name = 'Paul Adam';

```

**Output:**

![image](https://github.com/user-attachments/assets/6f136012-6a0d-410a-ac81-07146e926f59)


**Question 3**
---
![image](https://github.com/user-attachments/assets/9c572444-dd08-4882-8663-113744f65455)


```sql
select *
from CUSTOMERS
where ADDRESS = 'Delhi'
;
```

**Output:**

![image](https://github.com/user-attachments/assets/f4a67a58-572c-4ef4-9a56-0f469bc9386d)


**Question 4**
---
![image](https://github.com/user-attachments/assets/8f6fa549-3074-45ab-830c-83afd3748ba3)


```sql
SELECT 
    ord_no, 
    purch_amt, 
    ord_date, 
    customer_id, 
    salesman_id
FROM 
    orders
WHERE 
    purch_amt > (
        SELECT AVG(purch_amt)
        FROM orders
        WHERE ord_date = '2012-10-10'
    );

```

**Output:**
![image](https://github.com/user-attachments/assets/6d317a9e-cc96-4b1f-9027-1cfc97ab277f)


**Question 5**
---
![image](https://github.com/user-attachments/assets/aab7d0e0-8d39-416a-9d42-95b49aed528f)


```sql
SELECT 
    student_name, 
    grade
FROM 
    GRADES g
WHERE 
    grade = (
        SELECT MAX(grade)
        FROM GRADES
        WHERE subject = g.subject
    );

```

**Output:**

![image](https://github.com/user-attachments/assets/fcd3244c-7cfc-4018-8927-eeb92ca3a0a8)


**Question 6**
---
![image](https://github.com/user-attachments/assets/a6f10823-9fcf-4261-b65c-8357569e89c1)


```sql
SELECT 
    grade, 
    COUNT(*) 
FROM 
    customer
WHERE grade > (
        SELECT AVG(grade)
        FROM customer
        WHERE city = 'New York'
    )
GROUP BY 
    grade;

```

**Output:**
![image](https://github.com/user-attachments/assets/490e3000-85b0-46df-8aa6-319bc42f17f8)

**Question 7**
---

![image](https://github.com/user-attachments/assets/2ae06c92-6918-423a-9f2d-bedb801ce654)

```
select medication_id,medication_name,dosage from Medications
where dosage=(
      select min(dosage) from Medications);
```

**Output:**


![image](https://github.com/user-attachments/assets/c9c6118c-6ca8-4e31-a4b9-b4328502f470)


**Question 8**
---
![image](https://github.com/user-attachments/assets/02696d1d-d0b5-42c3-a082-67e547348d94)


```sql
SELECT o.ord_no, o.purch_amt, o.ord_date, o.customer_id, o.salesman_id
FROM orders o
JOIN salesman s ON o.salesman_id = s.salesman_id
WHERE s.city = 'New York';

```

**Output:**
![image](https://github.com/user-attachments/assets/84362d3e-9ae3-4071-a66b-58ea1a01478b)


**Question 9**
---
![image](https://github.com/user-attachments/assets/9fb93b3f-1857-4eca-8489-b49e81a779f0)


```sql
SELECT *
FROM GRADES
WHERE grade IN (
    SELECT MAX(grade)
    FROM GRADES AS g
    WHERE g.subject = GRADES.subject
);


```

**Output:**

![image](https://github.com/user-attachments/assets/70afcf0e-0cfa-417c-b1fd-733851a5e20e)


**Question 10**
---
![image](https://github.com/user-attachments/assets/a106295e-004a-421f-851e-c11bec5e69d7)


```sql
SELECT 
    name
FROM 
    customer
WHERE 
    phone IN (
        SELECT 
            phone
        FROM 
            customer
        GROUP BY 
            phone
        HAVING 
            COUNT(*) = 1
    );

```

**Output:**
![image](https://github.com/user-attachments/assets/6ef79dbc-b2bf-41e3-a738-5319fddc88bc)



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
