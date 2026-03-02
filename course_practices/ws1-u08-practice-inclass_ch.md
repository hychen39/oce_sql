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

## 課堂練習: Pairwise comparison

請先執行以下 DML 產生需要的測試資料

```sql
update employees
    set department_id = 80
    where employee_id in (125, 126);
```

接著, 請撰寫 Query 完成以下的 reporting 要求:

Display the details of the employees who are managed by the same manager and work in the same department as the employees with `EMPLOYEE_ID` 180 or 176 (公司內 last name 為 Taylor 的兩位員工).

這兩名員工的 manager_id 及 department_id 如下:

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

## 課堂練習: Non-Pairwise comparison

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