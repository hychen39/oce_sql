---
puppeteer:
   displayHeaderFooter: true
html: 
    embed_local_images: true
    embed_svg: true
export_on_save:
    html: true
---


# U11 資料定義語言（DDL）簡介



建立資料表過程中，若資料表名稱已存在，請先刪除。

## Q1

建立資料表 `dept_p11`：

Column name |  Data type | Length | Constraint | FK Table | FK Column 
--|--|--|--|--|--|
ID | number | 7 | Primary Key | |
Name | varchar2 | 25 | | |


顯示資料表結構
```
desc dept_p11
```

## Q2


建立資料表 `emp_p11`：

Column name |  Data type | Length | Constraint | FK Table | FK Column 
--|--|--|--|--|--|
ID | number | 7 | Primary Key | |
Last_Name | varchar2 | 25 | | |
First_Name | varchar2 | 25 | | |
Dept_ID | number | 7 | Foreign Key | dept_p11 | ID

顯示資料表結構
```
desc emp_p11
```

## Q3



在 `emp_p11` 資料表中加入以下欄位

Column name |  Data type | Length | Constraint | FK Table | FK Column 
--|--|--|--|--|--|
Commission | number(2, 2) |||

顯示資料表結構
```
desc emp_p11
```

## Q4

修改 `emp_p11` 資料表中的 `Last_Name` 欄位，將可儲存字元數由 25 改為 50，並加入預設值 `'Empty'`。

顯示資料表結構
```
desc emp_p11
```

## Q5

將 `emp_p11` 資料表中的 `first_name` 設定為 unused。

顯示資料表結構
```
desc emp_p11
```

## Q6

刪除 `dept_p11` 資料表。


