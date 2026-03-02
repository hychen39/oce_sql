---
puppeteer:
   displayHeaderFooter: true
html: 
    embed_local_images: true
    embed_svg: true
export_on_save:
    html: true
---


# U10 Managing Tables using DML Statement

## 題目

### Q1

執行以下 SQL 建立所需表格:

```sql {class=line-numbers}
create table my_employee (
    emp_id number, 
    first_name varchar2(100), 
    dept_id number, 
    dept_name varchar2(100), 
    salary number);
```

複製 employees 表格中員工編號 200 號(不含)前的資料到 `my_employee` 表格中。
要複製的欄位包括:
- `emp_id`: employee_id
- `first_name`: first_name
- `dept_id`: department_id

執行後的部份結果如下:

![](img-01/u10-i01.png)

完成後請 commit 確認交易。

### Q2

請更新 Q1 表格內的記錄, 找出每位員工的部門名稱及薪水, 填入到 `dept_name` 及 `salary` 欄位. 完成後請 commit 確認交易。

更新後的部份表格如下:

![](img-01/u10-i02.png)


