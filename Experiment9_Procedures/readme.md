# Experiment 9: PL/SQL – Procedures and Functions

## AIM
To understand and implement procedures and functions in PL/SQL for performing various operations such as calculations, decision-making, and looping.

---

## THEORY

PL/SQL (Procedural Language/SQL) extends SQL by adding procedural constructs like variables, conditions, loops, procedures, and functions. Procedures and functions are subprograms that help modularize the code and improve reusability.

### **Procedure**
A PL/SQL **procedure** is a subprogram that performs a specific action. It does not return a value directly but can return values using `OUT` parameters.

**Syntax:**
```sql
CREATE OR REPLACE PROCEDURE procedure_name (parameters)
IS
BEGIN
   -- statements
END;
```

To call the procedure

```sql
EXEC procedure_name(arguments);
```

### **Function**
A PL/SQL **function** is a subprogram that returns a single value using the RETURN keyword.

```sql
CREATE OR REPLACE FUNCTION function_name (parameters)
RETURN datatype
IS
BEGIN
   -- statements
   RETURN value;
END;
```

To call the function:

```sql
SELECT function_name(arguments) FROM DUAL;
```

Key Differences:

-A procedure does not return a value, whereas a function must return a value.
-Functions can be called from SQL queries, procedures cannot (in most cases).

## 1. Write a PL/SQL Procedure to Find the Square of a Number

### Steps:
- Create a procedure named `find_square`.
- Declare a parameter to accept a number.
- Inside the procedure, compute the square of the input number.
- Use `DBMS_OUTPUT.PUT_LINE` to display the result.
- Call the procedure with a number as input.
## Program
```
CREATE OR REPLACE PROCEDURE find_square(p_number IN NUMBER) AS
    v_square NUMBER;
BEGIN
    v_square := p_number * p_number;
    DBMS_OUTPUT.PUT_LINE('The square of ' || p_number || ' is: ' || v_square);
END;
/



```
## Output 

Square of 6 is 36

![image](https://github.com/user-attachments/assets/bfaf232d-5b8f-4ac5-a3a2-065d18a56f66)

---

## 2. Write a PL/SQL Function to Return the Factorial of a Number

### Steps:
- Create a function named `get_factorial`.
- Declare a parameter to accept a number.
- Use a loop to calculate the factorial.
- Return the result using the `RETURN` statement.
- Call the function using a `SELECT` statement or in an anonymous block.
## Program
```
CREATE OR REPLACE FUNCTION get_factorial(n IN NUMBER)
RETURN NUMBER
IS
    result NUMBER := 1;
BEGIN
    IF n < 0 THEN
        RAISE_APPLICATION_ERROR(-20001, 'Factorial is not defined for negative numbers.');
    END IF;

    FOR i IN 1..n LOOP
        result := result * i;
    END LOOP;

    RETURN result;
END;
/





```
## Output

Factorial of 5 is 120

![image](https://github.com/user-attachments/assets/7826f0f2-f2db-4fe4-8c10-ccd26d00721e)

---

## 3. Write a PL/SQL Procedure to Check Whether a Number is Even or Odd

### Steps:
- Create a procedure named `check_even_odd`.
- Accept an input parameter.
- Use the `MOD` function to check if the number is divisible by 2.
- Display whether it is Even or Odd using `DBMS_OUTPUT.PUT_LINE`.
## Program

```

CREATE OR REPLACE PROCEDURE check_even_odd(p_number IN NUMBER) AS
BEGIN
    IF MOD(p_number, 2) = 0 THEN
        DBMS_OUTPUT.PUT_LINE(p_number || ' is Even.');
    ELSE
        DBMS_OUTPUT.PUT_LINE(p_number || ' is Odd.');
    END IF;
END;
/

```
## Output:  

12 is Even

![image](https://github.com/user-attachments/assets/ca9827b1-f316-4429-880a-77661c53e7fb)

---

## 4. Write a PL/SQL Function to Return the Reverse of a Number

### Steps:
- Create a function named `reverse_number`.
- Accept an input number as parameter.
- Use a loop to reverse the digits of the number.
- Return the reversed number.
- Call the function and display the output.
## Program
```
CREATE OR REPLACE FUNCTION reverse_number(n IN NUMBER)
RETURN NUMBER
IS
    rev NUMBER := 0;
    temp NUMBER := n;
BEGIN
    WHILE temp > 0 LOOP
        rev := (rev * 10) + MOD(temp, 10);
        temp := FLOOR(temp / 10);
    END LOOP;

    RETURN rev;
END;
/


```
## Output:

Reversed number of 1234 is 4321

![image](https://github.com/user-attachments/assets/f5d71dfd-e05e-4570-8836-91e1dc1445c1)

---

## 5. Write a PL/SQL Procedure to Display the Multiplication Table of a Number

### Steps:
- Create a procedure named `print_table`.
- Accept an input number.
- Use a loop from 1 to 10 to multiply the input number.
- Display the multiplication results using `DBMS_OUTPUT.PUT_LINE`.
## Program

```
CREATE OR REPLACE PROCEDURE multiplication_table(p_number IN NUMBER) AS
BEGIN
    FOR i IN 1..10 LOOP
        DBMS_OUTPUT.PUT_LINE(p_number || ' x ' || i || ' = ' || (p_number * i));
    END LOOP;
END;
/

```
## Output:

Multiplication table of 5:  
5 x 1 = 5  
5 x 2 = 10  
5 x 3 = 15  
...  
5 x 10 = 50

![image](https://github.com/user-attachments/assets/73489b9e-b90f-4e04-950e-16b331cc9f24)



## RESULT
Thus, the PL/SQL programs using procedures and functions were written, compiled, and executed successfully.
