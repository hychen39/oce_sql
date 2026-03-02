---
html: 
    embed_local_images: true
    embed_svg: true
export_on_save:
    html: true
---

@import "../css/article_01.css"


# U02 - Retrieving Data Using the SQL SELECT Statement

## Concept Map

```mermaid
graph LR;
SelectCol("Select columns from a table")-->ColArithExp("Column arithmetic (Arithmetic operators)")
ColArithExp-->ColAlias("Column alias")
SelectCol-->ColConcate("Column concatenation")
ColConcate-->ColAlias
ColArithExp-->QOperator("Quote Operator q")
```

## Practice
### P1

The HR department wants a query to display the last name, job ID, hire date, and employee ID for each employee, with the employee ID appearing first. 

Provide an alias `STARTDATE` for the `HIRE_DATE` column. 

![](img-01/u02-i01.png)

### P2 

The HR department wants a query to display all unique job IDs from the `EMPLOYEES` table.


![](img-01/u02-i02.png)

### P3

The HR department wants more descriptive column headings for its report on employees.

Based on the query in the P1, name the report columns to `Emp #`, `Employee`, `Job`, and `Hire Date`, respectively.

![](img-01/u02-i03.png)

### P4 
The HR department has requested a report of all employees and their job IDs. 
Display the last name concatenated with the job ID (separated by a comma and space) and name the column `Employee` and `Title`.


![](img-01/u02-i04.png)

### P5 

The HR department wants to display each employee's manager employee ID. Use the following display format:

` [Employee_id] [Last_name]'s manager_id is [manager_id] `

Items in brackets are column names. Name this column `Employee's Manager ID List`.




