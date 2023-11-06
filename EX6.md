# Ex. No: 6 Creating Cursors using PL/SQL

##DATE:


### AIM: To create a cursor using PL/SQL.

### Steps:
1. Create employee table with following attributes (empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
2. Create a cursor named as employee_cursor
3. Using cursor read each record and display the result
4. Close the cursor

### Program:

### Create employee table
```
CREATE TABLE employee6 (
  empid NUMBER,
  empname VARCHAR(10),
  dept VARCHAR(10),
  salary NUMBER
);
select * from employee6;
INSERT INTO employee6 VALUES (101, 'Arya', 'HR', 80000);
INSERT INTO employee6 VALUES (102, 'Varshini', 'Manager', 700000);
INSERT INTO employee6 VALUES (103, 'Amrutha', 'Sales', 900000);
```

### PLSQL Cursor code
```
DECLARE
   CURSOR employee6cursor IS
   SELECT empid,empname,dept,salary
   FROM employd;
   emp_id NUMBER;
   emp_name VARCHAR(50);
   emp_dept VARCHAR(50);
   emp_salary NUMBER;
BEGIN
  OPEN employee6_cursor;

  LOOP
    FETCH employee6_cursor INTO emp_id, emp_name, emp_dept, emp_salary;

    EXIT WHEN employee6_cursor%NOTFOUND;

    DBMS_OUTPUT.PUT_LINE('Employee ID: ' || emp_id);
    DBMS_OUTPUT.PUT_LINE('Employee Name: ' || emp_name);
    DBMS_OUTPUT.PUT_LINE('Department: ' || emp_dept);
    DBMS_OUTPUT.PUT_LINE('Salary: ' || emp_salary);
  END LOOP;

  CLOSE employee6_cursor;
END;
/
```

OUTPUT:

![dbms ex06 out](https://github.com/aryabaisakhiya/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/119393645/afb0e8a5-49ee-49e2-9747-a1d08b09490f)


### Result:
THE PROGRAM HAS BEEN IMPLEMENTED SUCCESSFULLY
