---
puppeteer:
   displayHeaderFooter: true
html: 
    embed_local_images: true
    embed_svg: true
export_on_save:
    html: true
---


# U11 Introduction to Data Definition Language



If a table name already exists while creating tables, drop it first.

## Q1

Create table `dept_p11`:

Column name |  Data type | Length | Constraint | FK Table | FK Column 
--|--|--|--|--|--|
ID | number | 7 | Primary Key | |
Name | varchar2 | 25 | | |


Display the table structure.
```
desc dept_p11
```

## Q2


Create table `emp_p11`:

Column name |  Data type | Length | Constraint | FK Table | FK Column 
--|--|--|--|--|--|
ID | number | 7 | Primary Key | |
Last_Name | varchar2 | 25 | | |
First_Name | varchar2 | 25 | | |
Dept_ID | number | 7 | Foreign Key | dept_p11 | ID

Display the table structure.
```
desc emp_p11
```

## Q3



Add the following columns to table `emp_p11`.

Column name |  Data type | Length | Constraint | FK Table | FK Column 
--|--|--|--|--|--|
Commission | number(2, 2) |||

Display the table structure.
```
desc emp_p11
```

## Q4

Modify column `Last_Name` in `emp_p11`: change the size from 25 to 50 characters, and add default value 'Empty'.

Display the table structure.
```
desc emp_p11
```

## Q5

Set column `first_name` in `emp_p11` to unused.

Display the table structure.
```
desc emp_p11
```

## Q6

Drop table `dept_p11`.


