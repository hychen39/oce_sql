---
puppeteer:
   displayHeaderFooter: true
html: 
    embed_local_images: true
    embed_svg: true
export_on_save:
    html: true
---


# U08 使用子查詢解題

## 課堂練習：成對比較

請先執行以下 DML，產生需要的測試資料。

```sql
update employees
    set department_id = 80
    where employee_id in (125, 126);
```

接著，請撰寫查詢完成以下報表需求：

顯示與 `EMPLOYEE_ID` 180 或 176 的員工（公司內姓氏為 Taylor 的兩位員工）具有相同經理，且位於相同部門之員工詳細資料。

這兩名員工的 `manager_id` 與 `department_id` 如下：

```
employee_id manager_id department_id
-------------------------
176	    149	    80
180	    120	    50
```

報表需包含 `EMPLOYEE_ID`、`MANAGER_ID` 與 `DEPARTMENT_ID` 欄位。



### 參考解答

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

## 課堂練習：非成對比較

顯示與 `EMPLOYEE_ID` 180 或 176 的員工具有相同經理，且也在這兩位員工所在部門工作的員工詳細資料。

### 參考解答

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
