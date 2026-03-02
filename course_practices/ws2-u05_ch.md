---
puppeteer:
   displayHeaderFooter: true
html: 
    embed_local_images: true
    embed_svg: true
export_on_save:
    html: true
---


# WS2-L5 Part I Managing schema objects: Managing constraints

## Q1


查詢 `Departments` 表格的限制(constraints)資訊, 顯示以下欄位: column name, constraint name, constraint type, search
condition, status, 是否可延遲(DEFERRABLE), 延遲狀態(DEFERRED).

## Q2

建立表格 dept01:

Column name |  Data type | Length | Constraint | FK Table | FK Column 
--|--|--|--|--|--|
ID | number |  | Primary Key, 名稱: dept01_pk | |
dept_name | varchar2 | 50 | | |


建立表格 emp01:

Column name |  Data type | Length | Constraint | FK Table | FK Column 
--|--|--|--|--|--|
ID | number |  | Primary Key, 名稱: emp01_pk | |
salary | number | 4 | | |
hire_date | date |  | | |
dept_id | number | | Foreign Key, on delete set null, inline, 名稱: emp01_fk | dept01 | id

Table level Constraint (Out-of-line constraint)
- 名稱: emp01_ck
- 條件: salary > 0 and hire_date > 2000/01/01
- 此限制為"可延遲(deferrable)", 初始化狀為 "每次執行 DML 時檢查"

## Q3

查出上述兩個表格所使用的 index 的資訊。

## Q4

為 `dept01` 表格中的 `dept_name` 欄位加入 `not null` 限制

## Q5

將 `emp01` 表格中的 emp01_fk 限制變成"可延遲", 初始狀態為 immediate, 限制的名稱不可改變

## Q6

將 `dept01` 中的 dept_pk 限制 disable, 連帶 disable 參考此限制的其它限制, 例如 Foreign key constraint.

將 `emp01` 中的 emp01_fk 限制變成 disable 的狀態, 但仍要確保表格內的資料符合該限制。

