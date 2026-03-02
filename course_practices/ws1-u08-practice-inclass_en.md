---
puppeteer:
   displayHeaderFooter: true
html: 
    embed_local_images: true
    embed_svg: true
export_on_save:
    html: true
---


# U08 Using Subqueries to Solve Queries

## In-Class Practice: Pairwise comparison

Please execute the following DML first to generate the required test data.

```sql
update employees
    set department_id = 80
    where employee_id in (125, 126);
```

Then, write a query to complete the following reporting requirement:

Display the details of the employees who are managed by the same manager and work in the same department as the employees with `EMPLOYEE_ID` 180 or 176 (the two employees in the company whose last name is Taylor).

The manager_id and department_id of these two employees are as follows:

```
employee_id manager_id department_id
-------------------------
176	    149	    80
180	    120	    50
```

The report contains the columns of `EMPLOYEE_ID`, `MANAGER_ID` and `DEPARTMENT_ID`.



### Solution

```sql
select * 
from employees
where (manager_id, department_id) 
        in (select manager_id, department_id
               from employees 
               where employee_id in (180, 176))
        and employee_id not in (180, 180)
        order by manager_id, department_id;
```

## In-Class Practice: Non-Pairwise comparison

Display the details of the employees who are managed by the same manager as the employees with `EMPLOYEE_ID` 180 or 176 and work in the same departments as the employees with `EMPLOYEE_ID` 180 or 176.

### Solution

```sql
select * 
from employees
where manager_id in 
                (select manager_id
                    from employees 
                    where employee_id in (180, 176))
      and  department_id in 
                        (select department_id
                            from employees 
                            where employee_id in (180, 176))
      and employee_id not in (180, 176);
```