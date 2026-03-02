---
puppeteer:
   displayHeaderFooter: true
html: 
    embed_local_images: true
    embed_svg: true
export_on_save:
    html: true
---

#  WS2-L7 Manipulating data using subqueries

## 題目

### Q1

<!-- 1z0-147 No.114 Update with subqueries; pairwise assignment (同 No.147) -->

You want to update EMPLOYEES table as follows:

請先執行以下命令, 建立需要的表格:

```sql {class=line-numbers}
create table emp01 as
select * from employees
```

請依照以下的要求更新 emp01 表格:

- 只對在 Seattle 城市的部門的內員工更新資料
- 更新員工的薪水為: 原本薪水 + 0.1% 該員工所在部門平均薪水


### Q2 

請先執行以下命令, 建立需要的表格:

```sql {class=line-numbers}
create table dept01 as
select * from departments
```


請寫一個 Insert statement, 新增資料到 dept01 table 中. 但限制只能新增 Location_ID = 1400 的部門資料.

測試資料:
- `values (999, 'test', 103, 1400)`: 新增成功
- `values (999, 'test', 103, 1500)`: 新增失敗

### Q3

請先執行以下命令, 建立需要的表格及資料:

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

`job_rotation` 表格記錄員工工作輪調的起始日期.

輪調資料只保留最近兩次的記錄. 現在的記錄中, 某些員工的輪調記錄有 3 次.

請使用 Delete statement 刪除不必要的資料. 例如, 員工 100 及 300 的 2016 及 2015 年的記錄應該被刪除. 

假設資料量很大, 我們無法逐筆檢視進行刪除。

參考結果輸出:

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

請先執行以下命令, 建立需要的表格:

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

以編號 125 (不含)之前的員工資料為資料來源, 取得以下欄位: employee_id, hire_date, manager_id, 及 salary.

在資料來源中, 
- 如果員工薪水小於 10000 元:
  - 新增員工的 employee_id, hire_date, 及 salary 到 sal_history 表格
  - 新增員工的 employee_id, manager_id, 及 salary 到 mgr_history 表格

- 如果員工薪水等於或大於 10000 元:
  - 新增員工的 employee_id, 及 salary 到 special_sal 表格

執行後, 請查詢以下表格內容以確認結果.

