---
puppeteer:
   displayHeaderFooter: true
html: 
    embed_local_images: true
    embed_svg: true
export_on_save:
    html: true
---

#  WS2-L9 Manipulating data using advanced subqueries

## 題目

### Q1

先立以下三個 tables:

```
create table sal_history (
    employee_id number(6),
    hire_date date, 
    salary number(8,2)
)

create table mgr_history (
    employee_id number(6),
    manager_id number(6),
    salary number(8,2)
)

create table special_sal (
    employee_id number(6),
    salary number(8,2)
)
```

撰寫查詢完成以下工作：
- 從 employees 表格取得員工編號小於 125 的員工資料，欄位包括 employee_id, hire_date, salary 及 manager_id. 
- 如果員工的薪水大於 20,000, 將員工資料新增至  special_sal 表格，欄位包括： employee_id 及 salary。
- 如果員工的薪水小於 20,000:
  - 將該員工資料新增至 sal_history 表格，欄位包括： employee_id, hire_date, salary。
  - 將該員工資料新增至 mgr_history，欄位包括： employee_id 及 manager_id 


### Q2 

執行以下程式建立 sales_week_data 表格：

```
create table sales_week_data (
    id number(6),
    week_id number(2),
    qty_mon number(8,2),
    qty_tue number(8,2),
    qty_wed number(8,2),
    qty_thur number(8,2),
    qty_fri number(8,2),
)
```

使用以下程式增加資料到上述表格： 

```
insert into sales_week_data
    values (200, 6, 2050, 2200, 1700, 1200, 3000);
insert into sales_week_data
    values (210, 7, 2070, 2270, 1780, 1270, 3005);
```

執行以下程式建立 emp_sales_info 表格：

```
create table emp_sales_info (
    id number(6),
    week number(2),
    qty_sales number(8,2)
)
```

請將 sales_week_data 表格中的每一筆記錄轉換到 emp_sales_info 表格。提示，使用 Pivoting INSERT 敘述。


### Q3 

建立 bonuses 表格並新增以下資料： 

```
create table bonuses ( employee_id number, bonus number default 100);

--- 有績效獎金的清單，預設獎金每人 100
insert into bonuses(employee_id)
select employee_id from employees where employee_id <= 110;
```

人力資源經理決定對編號 100 ~ 120 的員工調整薪水。規則如下：
1. 工資在 8000 美元或以下的員工應該獲得獎金。
2. 那些沒有做銷售的人(不在 bonuses 表格中的記錄)應得到他們工資的 1% 的獎金。那些已經完成銷售的人(已在 bonuses 表格中的記錄)將額外獲得相當於其工資 1% 的獎金，除現有的獎金外。

使用 Merge Statement 完成上述要求。


### Q4 

建立 emp2 表格 

```
create table emp2 (
    id number(7),
    last_name varchar2(25),
    first_name varchar2(25),
    dept_id number(7)
)
```

1. 刪除(drop)表格 emp2。
2. 查詢 recycle bin, 查看此表格是否出現在 recycle bin。
3. 回復(restore) emp2 表格回到 drop 前的狀態。


### Q5 

執行以下指令，建立 emp3 表格，更新員工資料
```
create table emp3 as 
select * from employees where department_id = 90;

update emp3 set department_id = 60 
where last_name = 'Kochhar';
commit;
update emp3 set department_id = 50 
where last_name = 'Kochhar';
commit;
```

使用 Flashback versions query 查詢 emp3 中 last_name 為 Kochhar 的資料列的 department_id 欄位的版本變化。

![](img-01/ws2-u09-i01.png)


