# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
--

![image](https://github.com/user-attachments/assets/5635425c-15b5-4303-ba61-b0453e393ffe)

```sql
INSERT INTO Student_details(RollNo,Name,Gender,Subject,MARKS)
VALUES(202,"Ella King","F","Chemistry",87),
(203,"James Bond","M","Literature",78);
```

**Output:**

![image](https://github.com/user-attachments/assets/e1b43ff5-667c-47de-87dc-1a146f37d76a)


**Question 2**
---
![image](https://github.com/user-attachments/assets/ffdad72e-a8c2-4b4e-a2d4-c7493d7c00e0)



```sql
INSERT INTO Products(ProductID,Name,Category,Price,Stock)
VALUES(104,"Tablet","Electronics",100,50);
```

**Output:**

![image](https://github.com/user-attachments/assets/3713a8cd-2aa8-4d2f-be8e-6a8716bf86fa)


**Question 3**
---
![image](https://github.com/user-attachments/assets/7666ca39-ef27-406c-9455-c561ee5ba229)


```sql
select * from Out_of_print_books
UNION ALL
select * from  Books
```

**Output:**
![image](https://github.com/user-attachments/assets/d48d54b4-96f9-419d-9e19-44440f86efce)


**Question 4**
---
![image](https://github.com/user-attachments/assets/ad555761-0a74-4556-827f-c1f143b3f79c)


```sql
CREATE TABLE Events(
EventID INTEGER,
EventName TEXT,
EventDate DATE);
```

**Output:**

![image](https://github.com/user-attachments/assets/e28b01b0-7bef-4fa1-b5de-8919519145f7)


**Question 5**
---
![image](https://github.com/user-attachments/assets/f06d17f9-827a-4cee-8946-b8412be9424f)


```sql
CREATE TABLE ProjectAssignments(
AssignmentID INTEGER PRIMARY KEY,
EmployeeID INTEGER,
ProjectID INTEGER,
AssignmentDate DATE NOT NULL,
FOREIGN KEY(EmployeeID) references Employees(EmployeeID),
FOREIGN KEY(ProjectID) references Projects(ProjectID)
);
```

**Output:**

![image](https://github.com/user-attachments/assets/cc79001a-63eb-458a-965f-fef3250c196f)


**Question 6**
---
![image](https://github.com/user-attachments/assets/dfeae7c3-27a0-4faf-a1a6-0fb9cc001fdf)


```sql
CREATE TABLE Orders(
OrderID  INTEGER PRIMARY KEY,
OrderDate  DATE NOT NULL,
CustomerID  INTEGER,
FOREIGN KEY(CustomerID) references Customers(CustomerID)
);
```

**Output:**
![image](https://github.com/user-attachments/assets/52d0bf29-b381-499f-a51b-150f2e9367dc)


**Question 7**
---
![image](https://github.com/user-attachments/assets/3232579f-5ada-4456-bfbb-6eb3cc89001a)


```sql
CREATE TABLE contacts(
contact_id  INTEGER PRIMARY KEY,
first_name TEXT NOT NULL,
last_name TEXT NOT NULL,
email TEXT,
phone TEXT NOT NULL check(length(phone)=10)

);
```

**Output:**

![image](https://github.com/user-attachments/assets/193002df-4beb-4983-aa22-cc95fdcf27d3)


**Question 8**
---
![image](https://github.com/user-attachments/assets/a555e095-a034-45b8-b220-0bbf533fe664)


```sql
ALTER TABLE Student_details
ADD COLUMN "Mobilenumber" number;
```

**Output:**

![image](https://github.com/user-attachments/assets/67adef89-c773-4883-a2db-c46c06d3f42d)


**Question 9**
---
![image](https://github.com/user-attachments/assets/5655e690-4e40-4d75-b9ae-02a0b1f8bfe5)


```sql
ALTER TABLE Companies
RENAME name to first_name;

ALTER TABLE Companies
ADD COLUMN "mobilenumber" number;


ALTER TABLE Companies
ADD COLUMN "DOB" Date;

ALTER TABLE Companies
ADD COLUMN "State" varchar(30);
```

**Output:**

![image](https://github.com/user-attachments/assets/b3659a28-312c-4dc1-b4a6-96fb97e31b93)


**Question 10**
---
![image](https://github.com/user-attachments/assets/c222da16-d080-4897-8d0d-d4f48037241d)


```sql
ALTER TABLE Student_details
ADD COLUMN "Country" TEXT;
```

**Output:**

![image](https://github.com/user-attachments/assets/ee0bef0a-26b9-482f-9db2-692012253932)



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
