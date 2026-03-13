---
puppeteer:
   displayHeaderFooter: true
html: 
    embed_local_images: true
    embed_svg: true
export_on_save:
    html: true
---


# WS2-L5 Part I 管理綱要物件：管理限制條件

## Q1


查詢 `Departments` 資料表的限制條件（constraints）資訊，顯示下列欄位：column name、constraint name、constraint type、search condition、status、是否可延遲（`DEFERRABLE`）、延遲狀態（`DEFERRED`）。

## Q2

建立資料表 `dept01`：

Column name |  Data type | Length | Constraint | FK Table | FK Column 
--|--|--|--|--|--|
ID | number |  | Primary Key, 名稱: dept01_pk | |
dept_name | varchar2 | 50 | | |


建立資料表 `emp01`：

Column name |  Data type | Length | Constraint | FK Table | FK Column 
--|--|--|--|--|--|
ID | number |  | Primary Key, 名稱: emp01_pk | |
salary | number | 4 | | |
hire_date | date |  | | |
dept_id | number | | Foreign Key, on delete set null, inline, 名稱: emp01_fk | dept01 | id

資料表層級限制（Out-of-line constraint）
- 名稱：`emp01_ck`
- 條件：`salary > 0 and hire_date > 2000/01/01`
- 此限制需設定為「可延遲（deferrable）」，初始狀態為「每次執行 DML 時檢查」

## Q3

查詢上述兩個資料表所使用的 index 資訊。

## Q4

為 `dept01` 資料表中的 `dept_name` 欄位加入 `not null` 限制。

## Q5

將 `emp01` 資料表中的 `emp01_fk` 限制改成「可延遲」，初始狀態為 `immediate`，且限制名稱不可改變。

## Q6

將 `dept01` 中的 `dept_pk` 限制設為 `disable`，並一併停用所有參照此限制的其他限制，例如 foreign key constraint。

將 `emp01` 中的 `emp01_fk` 限制改為 `disable` 狀態，但仍需確保資料表內資料符合該限制。

