---
puppeteer:
   displayHeaderFooter: true
html: 
    embed_local_images: true
    embed_svg: true
export_on_save:
    html: true
---


# WS2-L5 Part I Managing Schema Objects: Managing Constraints

## Q1

Query the constraint information of the `Departments` table, and display the following columns: column name, constraint name, constraint type, search condition, status, whether it is deferrable (`DEFERRABLE`), and deferred status (`DEFERRED`).

## Q2

Create table `dept01`:

Column name | Data type | Length | Constraint | FK Table | FK Column
--|--|--|--|--|--
ID | number |  | Primary Key, name: `dept01_pk` | |
dept_name | varchar2 | 50 | | |


Create table `emp01`:

Column name | Data type | Length | Constraint | FK Table | FK Column
--|--|--|--|--|--
ID | number |  | Primary Key, name: `emp01_pk` | |
salary | number | 4 | | |
hire_date | date |  | | |
dept_id | number | | Foreign Key, `ON DELETE SET NULL`, inline, name: `emp01_fk` | dept01 | id

Table-level constraint (out-of-line constraint)
- Name: `emp01_ck`
- Condition: `salary > 0 and hire_date > 2000/01/01`
- This constraint is deferrable, with initial state "checked at each DML execution"

## Q3

Find the index information used by the two tables above.

## Q4

Add a `NOT NULL` constraint to the `dept_name` column in table `dept01`.

## Q5

Change the `emp01_fk` constraint in table `emp01` to deferrable, with initial state `IMMEDIATE`. The constraint name must not be changed.

## Q6

Disable the `dept_pk` constraint in `dept01`, and also disable other constraints that reference it, such as foreign key constraints.

Set the `emp01_fk` constraint in `emp01` to disabled, but still ensure the existing data in the table conforms to the constraint.
