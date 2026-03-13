---
html: 
    embed_local_images: true
    embed_svg: true
export_on_save:
    html: true
---

@import "../css/article_01.css"


# U02 - 使用 SQL SELECT 敘述擷取資料

## 概念圖

```mermaid
graph LR;
SelectCol("從資料表中選取欄位")-->ColArithExp("欄位運算 Arithmetic Op.")
ColArithExp-->ColAlias("欄位別名 Alias ")
SelectCol-->ColConcate("欄位串接 Concatenation")
ColConcate-->ColAlias
ColArithExp-->QOperator("Quote Operator q")
```

## 練習
### P1

人力資源部門希望撰寫一個查詢，顯示每位員工的姓氏、職務代碼、到職日與員工編號，且員工編號需放在最前面。

請為 `HIRE_DATE` 欄位指定別名 `STARTDATE`。

![](img-01/u02-i01.png)

### P2 

人力資源部門希望查詢 `EMPLOYEES` 資料表中所有不重複的職務代碼。


![](img-01/u02-i02.png)

### P3

人力資源部門希望員工報表的欄位標題更具描述性。

請以上一題 P1 的查詢為基礎，將報表欄位名稱依序命名為 `Emp #`、`Employee`、`Job` 與 `Hire Date`。

![](img-01/u02-i03.png)

### P4 
人力資源部門要求一份列出所有員工及其職務代碼的報表。
請將姓氏與職務代碼串接後顯示（中間以逗號加空白分隔），並將欄位命名為 `Employee` 和 `Title`。


![](img-01/u02-i04.png)

### P5 

HR 部門要顯示各員工之經理的員工編號。顯示格式如下：

` [Employee_id] [Last_name]'s manager_id is [manager_id] `

中括號內為欄位名稱。請將此欄位命名為 `Employee's Manager ID List`。





