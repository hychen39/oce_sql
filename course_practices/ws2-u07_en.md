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

## Exercises

### Q1

<!-- 1z0-147 No.114 Update with subqueries; pairwise assignment (same as No.147) -->

You want to update EMPLOYEES table as follows:

First, execute the following commands to create the required table(s):

```sql {class=line-numbers}
create table emp01 as
select * from employees
```

Update table `emp01` according to the following requirements:

- Update only employees in departments located in Seattle.
- Update each employee's salary to: original salary + 0.1% of the average salary in that employee's department.


### Q2 

First, execute the following commands to create the required table(s):

```sql {class=line-numbers}
create table dept01 as
select * from departments
```


Write an INSERT statement to add data into table `dept01`, but restrict inserts to rows with `location_id = 1400` only.

Test data:
- `values (999, 'test', 103, 1400)`: insert succeeds
- `values (999, 'test', 103, 1500)`: insert fails

### Q3

First, execute the following commands to create the required tables and data:

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

Table `job_rotation` records the start dates of employee job rotations.

Rotation data should keep only the two most recent records. In the current data, some employees have three rotation records.

Use a DELETE statement to remove unnecessary records. For example, for employees 100 and 300, the 2016 and 2015 records should be deleted. 

Assume the data volume is large, so we cannot review and delete row by row.

Reference output:

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

First, execute the following commands to create the required table(s):

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

Use employees with employee IDs less than 125 as the source data, and retrieve: employee_id, hire_date, manager_id, and salary.

From the source data, 
- if an employee salary is less than 10000:
  - insert employee_id, hire_date, and salary into table `sal_history`
  - insert employee_id, manager_id, and salary into table `mgr_history`

- if an employee salary is greater than or equal to 10000:
  - insert employee_id and salary into table `special_sal`

After execution, query the following tables to verify the results.

