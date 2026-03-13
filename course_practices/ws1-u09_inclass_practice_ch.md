---
puppeteer:
   displayHeaderFooter: true
html: 
    embed_local_images: true
    embed_svg: true
export_on_save:
    html: true
---

# U09 使用集合運算子 課堂練習

## Q1

找出曾在公司內擔任過 `ST_CLERK` 職務的員工。顯示欄位包括：
`employee_id`、`last_name`、`hire_date`、`start_date` 與 `end_date`。

結果請依 `employee_id` 排序。

員工現職可於 `employees` 資料表中查得。
員工職務歷史資料可於 `job_history` 資料表中找到。

參考輸出如下：

![](img-01/u09-i03.png)


### 參考解答

```sql
select employee_id, last_name, hire_date, to_date(null) start_date, to_date(null) end_date
from employees
where job_id = 'ST_CLERK'
UNION
select employee_id, last_name, to_date(null), start_date, end_date
from job_history j join employees e USING (employee_id)
where j.job_id = 'ST_CLERK' /*注意 column ambiguity 的問題*/
order by 1;
```
