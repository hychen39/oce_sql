---
puppeteer:
   displayHeaderFooter: true
html: 
    embed_local_images: true
    embed_svg: true
export_on_save:
    html: true
---


# U06 使用群組函數製作彙總報表

將資料列分群後，計算各群的彙總資料。
```mermaid
graph TD;
RestrictRows("分群前篩選資料 WHERE clause")
ColToGroup("用來分群的欄位 GROUP BY clause")
GroupFun("各群的彙總資料計算函數 Group Functions") 
RestrictGroup("篩選分群 HAVING clause")
OrderGroup("排序分群 ORDER BY clause")

RestrictRows-->ColToGroup
ColToGroup-->GroupFun
GroupFun-->RestrictGroup
RestrictGroup-->OrderGroup
```

Group Functions
```mermaid
graph LR;
GroupFun
AggDistinct("彙總不同的值 DISTINCT ")
IgnoreValue("預設忽略 Null Value ")
NestGroups("巢狀彙總函數 最多 2 levels")

GroupFun-->AggDistinct
GroupFun-->IgnoreValue
GroupFun-->NestGroups
```

## 練習

### Q1

撰寫查詢，顯示各職務類型的最低薪資、最高薪資、總薪資與平均薪資。結果請四捨五入到最接近的整數。

![](img-01/u06-i01.png)

### Q2 

撰寫查詢，顯示每種職務的人數。

請將查詢泛化，讓 HR 使用者可輸入職務代碼作為查詢條件。

例如，當使用者輸入 `IT_PROG` 時，應得到如下報表：

![](img-01/u06-i02.png)

### Q3

請利用 `employees` 資料表中的 `manager_id` 欄位，計算公司內不同經理的人數。

![](img-01/u06-i03.png)

### Q4

建立一份報表，顯示各經理的編號，以及其所管理員工中最低薪者的薪資。不需列出經理未知的員工；另外，最低薪資為 `$6,000` 或以下的群組也要排除。請依薪資遞減排序。

![](img-01/u06-i04.png)


### Q5

建立查詢，顯示員工總數，以及其中於 2009、2010、2011 與 2012 年到職的員工人數。請設定適當的欄位名稱。

![](img-01/u06-i05.png)





