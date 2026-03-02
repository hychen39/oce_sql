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
SelectCol("自表格中選取欄位")-->ColArithExp("欄位運算 Arithmetic Op.")
ColArithExp-->ColAlias("欄位命名 Alias ")
SelectCol-->ColConcate("欄位串接 Concatenation")
ColConcate-->ColAlias
ColArithExp-->QOperator("Quote Operator q")
```

## 練習
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

HR 部門要顯示各員工的經理的員工編號. 顯示的格式為:

` [Employee_id] [Last_name]'s manager_id is [manager_id] `

中括號內為欄位名稱。此欄位命名為 `Employee's Manager ID List`





