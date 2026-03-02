---
puppeteer:
   displayHeaderFooter: true
html: 
    embed_local_images: true
    embed_svg: true
export_on_save:
    html: true
---


# U11 Introduction to Data Definition Language



建立表格過程中, 若表格名稱已存在, 請先刪除.

## Q1

建立表格 dept_p11:

Column name |  Data type | Length | Constraint | FK Table | FK Column 
--|--|--|--|--|--|
ID | number | 7 | Primary Key | |
Name | varchar2 | 25 | | |


顯示表格結構
```
desc dept_p11
```

## Q2


建立表格 emp_p11:

Column name |  Data type | Length | Constraint | FK Table | FK Column 
--|--|--|--|--|--|
ID | number | 7 | Primary Key | |
Last_Name | varchar2 | 25 | | |
First_Name | varchar2 | 25 | | |
Dept_ID | number | 7 | Foreign Key | dept_p11 | ID

顯示表格結構
```
desc emp_p11
```

## Q3



加入以下欄位到 emp_p11 表格

Column name |  Data type | Length | Constraint | FK Table | FK Column 
--|--|--|--|--|--|
Commission | number(2, 2) |||

顯示表格結構
```
desc emp_p11
```

## Q4

修改 emp_p11 表格中的 Last_Name 欄位, 儲存的字元數由原來的 25 變成 50. 此外, 加入預設值 'Empty'.

顯示表格結構
```
desc emp_p11
```

## Q5

把 emp_p11 表格上的 first_name 設定成 unused.

顯示表格結構
```
desc emp_p11
```

## Q6

刪除 dept_p11 表格.


