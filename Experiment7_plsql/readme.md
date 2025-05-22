# Experiment 7: PL/SQL – Variables, Control Structures and Loops

## AIM
To write and execute simple PL/SQL programs using variables, loops, and conditional statements.


## THEORY

PL/SQL, which stands for Procedural Language extensions to the Structured Query Language (SQL). It is a combination of SQL along with the procedural features of programming languages.

**Syntax:**
```sql
DECLARE 
   <declarations section> 
BEGIN 
   <executable command(s)>
EXCEPTION 
   <exception handling> 
END;
```

### Basic Components of PL/SQL Block:
- DECLARE: Section to declare variables and constants.
- BEGIN: The execution section that contains PL/SQL statements.
- EXCEPTION: Handles errors or exceptions that occur in the program.
- END: Marks the end of the PL/SQL block.

# PL/SQL Programs – Steps and Expected Output

## 1. Write a PL/SQL program to find the Greatest of Two Numbers

### Steps:
- Declare two numeric variables and initialize them.
- Use an `IF` statement to compare the values.
- Display the greater number using `DBMS_OUTPUT.PUT_LINE`.

## Pragram
```
DECLARE
   num1 NUMBER := 25;  -- You can change the values
   num2 NUMBER := 40;
   greatest NUMBER;
BEGIN
   IF num1 > num2 THEN
      greatest := num1;
   ELSE
      greatest := num2;
   END IF;

   DBMS_OUTPUT.PUT_LINE('The greatest number is: ' || greatest);
END;



```
## Output:  

![image](https://github.com/user-attachments/assets/99013897-3652-4edb-bdc9-0627063cdb03)


---

## 2. Write a PL/SQL program to Calculate Sum of First N Natural Numbers

### Steps:
- Declare a variable `n` and assign a value (e.g., 10).
- Initialize a `sum` variable to 0.
- Use a `WHILE` loop to iterate from 1 to `n`, adding each number to the sum.
- Display the result using `DBMS_OUTPUT.PUT_LINE`.

## Pragram:

```
DECLARE
   n NUMBER := 10;      -- You can change this value
   i NUMBER := 1;
   sum NUMBER := 0;
BEGIN
   WHILE i <= n LOOP
      sum := sum + i;
      i := i + 1;
   END LOOP;

   DBMS_OUTPUT.PUT_LINE('The sum of first ' || n || ' natural numbers is: ' || sum);
END;




```
## Output:

Sum of first 10 natural numbers is: 55

![image](https://github.com/user-attachments/assets/f9a3e1bf-9d34-4557-9c9c-4a5acd6456f1)


---

## 3. Write a PL/SQL program to generate Fibonacci series

### Steps:
- Declare the variable `n` to indicate how many terms to generate.
- Initialize the first two Fibonacci numbers (0 and 1).
- Use a loop to generate the next terms using the formula `c = a + b`.
- Print each term in the series.
## Program:

```
DECLARE
   n NUMBER := 10;  -- Number of terms to generate
   a NUMBER := 0;
   b NUMBER := 1;
   temp NUMBER;
   i NUMBER := 1;
BEGIN
   DBMS_OUTPUT.PUT_LINE('Fibonacci Series up to ' || n || ' terms:');

   WHILE i <= n LOOP
      DBMS_OUTPUT.PUT_LINE(a);
      temp := a + b;
      a := b;
      b := temp;
      i := i + 1;
   END LOOP;
END;





```
## Output:

n = 7  
Fibonacci sequence: 0, 1, 1, 2, 3, 5, 8


![image](https://github.com/user-attachments/assets/155a0f55-91a8-4c3f-8f6e-a02037055011)


---

## 4. Write a PL/SQL Program to display the number in Reverse Order

### Steps:
- Declare a variable `n` and assign a value (e.g., 1535).
- Use a loop to extract each digit using modulo and reverse the number.
- Display the reversed number.
## Program
```
DECLARE
   num NUMBER := 12345;  -- Original number
   reversed NUMBER := 0;
   remainder NUMBER;
BEGIN
   DBMS_OUTPUT.PUT_LINE('Original number: ' || num);

   WHILE num > 0 LOOP
      remainder := MOD(num, 10);           -- Get last digit
      reversed := (reversed * 10) + remainder;  -- Append to reversed
      num := TRUNC(num / 10);              -- Remove last digit
   END LOOP;

   DBMS_OUTPUT.PUT_LINE('Reversed number: ' || reversed);
END;




```
## Output: 

n = 1535  
Reversed number is 5351

![image](https://github.com/user-attachments/assets/4e7a3d23-64f8-4d1a-947d-cc8ef48468d4)

---

## 5. Write a PL/SQL program to find the largest of three numbers

### Steps:
- Declare three numeric variables `a`, `b`, and `c`.
- Use nested `IF-ELSIF-ELSE` conditions to find the largest among the three.
- Display the largest number.
## Program

```
DECLARE
   num1 NUMBER := 45;   -- You can change these values
   num2 NUMBER := 78;
   num3 NUMBER := 63;
   largest NUMBER;
BEGIN
   IF (num1 >= num2) AND (num1 >= num3) THEN
      largest := num1;
   ELSIF (num2 >= num1) AND (num2 >= num3) THEN
      largest := num2;
   ELSE
      largest := num3;
   END IF;

   DBMS_OUTPUT.PUT_LINE('The largest number is: ' || largest);
END;



```
## Output: 

a = 10, b = 9, c = 15  
Largest of three number is 15

![image](https://github.com/user-attachments/assets/7d4259bd-f134-4de3-841d-c18b87594f5b)



## RESULT
Thus, the PL/SQL programs using variables, conditionals, and loops were executed successfully.
