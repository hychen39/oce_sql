---
puppeteer:
   displayHeaderFooter: true
html: 
    embed_local_images: true
    embed_svg: true
export_on_save:
    html: true
---

#  WS2-L7 使用子查詢操作資料

## 題目

### Q1

<!-- 1z0-147 No.114 Update with subqueries; pairwise assignment (同 No.147) -->

你要依下列需求更新 `EMPLOYEES` 資料表：

請先執行以下命令，建立所需資料表：

```sql {class=line-numbers}
create table emp01 as
select * from employees
```

請依照下列需求更新 `emp01` 資料表：

- 只更新在 Seattle 城市之部門內任職的員工資料
- 將員工薪資更新為：原薪資 + 該員工所屬部門平均薪資的 0.1%


### Q2 

請先執行以下命令，建立所需資料表：

```sql {class=line-numbers}
create table dept01 as
select * from departments
```


請撰寫一個 `INSERT` 敘述，將資料新增至 `dept01` 資料表，但限制只能新增 `Location_ID = 1400` 的部門資料。

測試資料：
- `values (999, 'test', 103, 1400)`: 新增成功
- `values (999, 'test', 103, 1500)`: 新增失敗

### Q3

請先執行以下命令，建立所需資料表及資料：

```sql
create table job_rotation (emp_id number, start_date date);

insert into job_rotation values (100, '01-Jan-2020');
insert into job_rotation values (100, '01-Jan-2018');
insert into job_rotation values (100, '01-Jan-2016');
insert into job_rotation values (200, '01-Jan-2019');
insert into job_rotation values (200, '01-Jan-2018');
insert into job_rotation values (300, '01-Jan-2017');
insert into job_rotation values (300, '01-Jan-2016');
insert into job_rotation values (300, '01-Jan-2015');

commit;
```

`job_rotation` 資料表記錄員工工作輪調的起始日期。

輪調資料只保留最近兩次紀錄。現有資料中，某些員工的輪調紀錄共有 3 次。

請使用 `DELETE` 敘述刪除不必要的資料。例如，員工 100 與 300 的 2016 年與 2015 年紀錄應被刪除。

假設資料量很大，無法逐筆檢視後再刪除。

參考結果輸出：

```
emp_id  start_date
------  -----------
100	    01-JAN-20
100	    01-JAN-18
200	    01-JAN-19
200	    01-JAN-18
300	    01-JAN-17
300	    01-JAN-16
```

### Q4 

請先執行以下命令，建立所需資料表：

```sql
create table sal_history (
    employee_id number(6),
    hire_date date,
    salary number(8,2)
);

create table mgr_history (
    employee_id number(6),
    manager_id number(6),
    salary number(8,2)
);

create table special_sal(
    employee_id number(6),
    salary number(8,2)
);
```

以員工編號小於 125 的員工資料為來源，取得下列欄位：`employee_id`、`hire_date`、`manager_id` 與 `salary`。

在來源資料中：
- 如果員工薪資小於 10000：
  - 將員工的 `employee_id`、`hire_date` 與 `salary` 新增到 `sal_history` 資料表
  - 將員工的 `employee_id`、`manager_id` 與 `salary` 新增到 `mgr_history` 資料表

- 如果員工薪資大於或等於 10000：
  - 將員工的 `employee_id` 與 `salary` 新增到 `special_sal` 資料表

執行後，請查詢上述資料表內容以確認結果。

