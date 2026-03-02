---
puppeteer:
   displayHeaderFooter: true
html: 
    embed_local_images: true
    embed_svg: true
export_on_save:
    html: true
---


# U10 Managing Tables using DML Statement

## Exercises

### Q1

Execute the following SQL to create the required table:

```sql {class=line-numbers}
create table my_employee (
    emp_id number, 
    first_name varchar2(100), 
    dept_id number, 
    dept_name varchar2(100), 
    salary number);
```

Copy data for employees with employee IDs less than 200 from the `employees` table into the `my_employee` table.
The columns to copy are:
- `emp_id`: employee_id
- `first_name`: first_name
- `dept_id`: department_id

Partial result after execution:

![](img-01/u10-i01.png)

After completion, commit the transaction.

### Q2

Update records in table `Q1`: find each employee's department name and salary, and fill them into `dept_name` and `salary`. After completion, commit the transaction.

Partial table after update:

![](img-01/u10-i02.png)


