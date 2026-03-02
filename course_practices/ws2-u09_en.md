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

## Exercises

### Q1

First, create the following three tables:

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

Write query statements to complete the following tasks:
- From table `employees`, retrieve data for employees with employee_id < 125. Columns: employee_id, hire_date, salary, manager_id. 
- If an employee's salary is greater than 20,000, insert that employee into table `special_sal` with columns: employee_id and salary.
- If an employee's salary is less than 20,000:
  - insert that employee into table `sal_history` with columns: employee_id, hire_date, salary.
  - insert that employee into table `mgr_history` with columns: employee_id and manager_id. 


### Q2 

Execute the following script to create table `sales_week_data`:

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

Use the following script to insert data into the above table: 

```
insert into sales_week_data
    values (200, 6, 2050, 2200, 1700, 1200, 3000);
insert into sales_week_data
    values (210, 7, 2070, 2270, 1780, 1270, 3005);
```

Execute the following script to create table `emp_sales_info`:

```
create table emp_sales_info (
    id number(6),
    week number(2),
    qty_sales number(8,2)
)
```

Transform each record in table `sales_week_data` into table `emp_sales_info`. Hint: use a pivoting INSERT statement.


### Q3 

Create table `bonuses` and insert the following data: 

```
create table bonuses ( employee_id number, bonus number default 100);

--- List of employees with performance bonuses; default bonus is 100 per person
insert into bonuses(employee_id)
select employee_id from employees where employee_id <= 110;
```

The HR manager decides to adjust salaries for employees with IDs 100 to 120. Rules:
1. Employees with salary of 8000 USD or below should receive a bonus.
2. Those without sales records (not present in table `bonuses`) should receive a bonus equal to 1% of salary. Those with sales records (already in `bonuses`) should receive an additional bonus equal to 1% of salary, on top of their existing bonus.

Use a MERGE statement to implement the requirements above.


### Q4 

Create table `emp2`. 

```
create table emp2 (
    id number(7),
    last_name varchar2(25),
    first_name varchar2(25),
    dept_id number(7)
)
```

1. Drop table `emp2`.
2. Query the recycle bin and check whether this table appears in it.
3. Restore table `emp2` to the state before it was dropped.


### Q5 

Execute the following statements to create table `emp3` and update employee data.
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

Use a Flashback Versions Query to inspect version changes of `department_id` for rows in `emp3` where `last_name` is Kochhar.

![](img-01/ws2-u09-i01.png)


