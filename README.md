# Ex. No: 6 Creating Cursors using PL/SQL
## Date:

## AIM: 
To create a cursor using PL/SQL.

## Steps:
1. Create employee table with following attributes (empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
2. Create a cursor named as employee_cursor
3. Using cursor read each record and display the result
4. Close the cursor

## Program:
### Create employee table
```
CREATE TABLE customers (Cust_id number,Cust_name varchar(20),Cust_addr varchar(20),mobile number);
```
## Inserting the values:
```
insert into account values(123,'Deepika','New York',9876543210);
insert into account values(456,'Srinivasan','Cairo',8908843210);
insert into account values(789,'Kalyani','California',7894021980);
```
### PLSQL Cursor code
```
SQL> set serveroutput on
SQL> declare
  2        cursor New_Cursor is
  3        select accno, customer_name,city,contact
  4        from account;
  5        accno number;
  6        customer_name varchar(90);
  7        city varchar(90);
  8        contact number;
  9        landline number;
 10        begin
 11        open New_Cursor;
 12        loop
 13        fetch New_Cursor into accno,customer_name,city,contact;
 14        exit when New_Cursor%notfound;
 15        dbms_output.put_line('Account Number: '||accno);
 16        dbms_output.put_line('Customer Name: '||customer_name);
 17        dbms_output.put_line('Address: '||city);
 18        dbms_output.put_line('Contact Number: '||contact);
 19        end loop;
 20        close New_cursor;
 21        end;
 22  /
```
## Output:
![cust01](https://github.com/deepikasrinivasans/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/119393935/2ae8bd46-9890-45a7-942d-cc6470abee42)
![cust2](https://github.com/deepikasrinivasans/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/119393935/1165090b-504b-4fbb-a8e7-ccbffdf18b6b)
## Result:
Thus a cursor is created using PL/SQL successfully.
