# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**
--
![image](https://github.com/user-attachments/assets/6e5979e3-30c9-4ec1-ac6f-869e595389f4)


```sql
SELECT DoctorID, COUNT(*) AS TotalAppointments
FROM Appointments
GROUP BY DOCTORID
;
```

**Output:**

![image](https://github.com/user-attachments/assets/01d477ce-3cb1-40f5-b807-933bf6b7503d)


**Question 2**
---
![image](https://github.com/user-attachments/assets/4c51c24e-8917-4a80-941a-2704b79de6dd)


```sql
SELECT SUBSTR(EMAIL, INSTR(EMAIL, '@') +1) AS EmailDomain, COUNT(*) AS 'TotalPatients'
FROM Patients
GROUP BY SUBSTR(EMAIL, INSTR(EMAIL, '@')+1)
;
```

**Output:**
![image](https://github.com/user-attachments/assets/66cf7596-70c9-42ba-82f5-3c7e8cb86b65)


**Question 3**
---
![image](https://github.com/user-attachments/assets/2e3ffc01-a285-4d31-9d4f-ea7ba65405d8)


```sql
SELECT PatientID, COUNT(*) AS  TotalRecords
FROM MedicalRecords 
GROUP BY PatientID
;
```

**Output:**
![image](https://github.com/user-attachments/assets/fa31f47b-33a5-44fa-b6a7-ba8d739073e9)


**Question 4**
---
![image](https://github.com/user-attachments/assets/31ae2871-9e62-40e2-86ff-85b46bce1669)


```sql
SELECT SUM(WORKHOUR) AS 'Total working hours'
FROM employee1;
```

**Output:**

![image](https://github.com/user-attachments/assets/bc0c1cb9-fd1a-4079-b93f-df413b8c1af2)


**Question 5**
---
![image](https://github.com/user-attachments/assets/e642f855-4dd0-49c1-b8e3-aea482c591de)


```sql
SELECT AVG(LENGTH(email)) AS avg_email_length_below_30
FROM  customer
WHERE city = 'Mumbai'
;
```

**Output:**
![image](https://github.com/user-attachments/assets/35dd3590-cce1-4a65-acb6-5d8eeb266f8a)


**Question 6**
---
![image](https://github.com/user-attachments/assets/dc668b8b-0f5c-4c5d-af13-68dea43d14d9)


```sql
SELECT MAX(price) - MIN(price) AS price_diff
FROM fruits
;
```

**Output:**
![image](https://github.com/user-attachments/assets/023dd4c4-9bd3-4650-bcb5-2de2bd883093)


**Question 7**
---
![image](https://github.com/user-attachments/assets/97d127bd-8afa-4b9e-b394-a11e34703c7f)


```sql
SELECT COUNT(DISTINCT Salesman_id) AS COUNT
FROM orders
;
```

**Output:**

![image](https://github.com/user-attachments/assets/d6a5f287-fb05-4cf5-bfa8-5a66c0677809)


**Question 8**
---
![image](https://github.com/user-attachments/assets/0f0273bb-fd73-4eb5-aab0-9cb4311f8f0e)


```sql
SELECT jdate, SUM(workhour) AS 'SUM(workhour)'
FROM employee1
GROUP BY jdate
HAVING SUM(workhour) > 40
;
```

**Output:**
![image](https://github.com/user-attachments/assets/2dfa2ee9-ff93-4d0a-9a8d-ca0562d6f527)


**Question 9**
---
![image](https://github.com/user-attachments/assets/26d55d16-35b5-4a4d-ac7e-e338c1d5fe9a)


```sql
SELECT age,max(income) as  'MAX(income)'
from employee
group by age
having max(income)>2000000
```

**Output:**

![image](https://github.com/user-attachments/assets/9a38ea4a-f086-4a54-8d1a-fac2c8c7a6ab)


**Question 10**
---
![image](https://github.com/user-attachments/assets/44677c6a-8640-40d4-b480-58b7d4fb12f2)


```sql
SELECT category_id, COUNT(*) AS 'count(product_name)'
FROM products
GROUP BY category_id
HAVING category_id < 3
;
```

**Output:**
![image](https://github.com/user-attachments/assets/5f8eb786-7c2b-42a9-8f2c-68c96a7cf0af)



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
