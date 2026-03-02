---
puppeteer:
   displayHeaderFooter: true
html: 
    embed_local_images: true
    embed_svg: true
export_on_save:
    html: true
---

# U09 Using Set Operators - In-Class Practice

## Q1

Find employees who have held the `ST_CLERK` position in the company. Display the following columns:
employee_id, last_name, hire_date, start_date, and end_date.

Sort the result by `employee_id`.

Current employee positions are in the `employees` table. 
Employee job history can be found in the `job_history` table.

Reference output:

![](img-01/u09-i03.png)


### Solution

```sql
select employee_id, last_name, hire_date, to_date(null) start_date, to_date(null) end_date
from employees
where job_id = 'ST_CLERK'
UNION
select employee_id, last_name, to_date(null), start_date, end_date
from job_history j join employees e USING (employee_id)
where j.job_id = 'ST_CLERK' /*Note the column ambiguity issue*/
order by 1;
```