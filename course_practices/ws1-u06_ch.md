---
puppeteer:
   displayHeaderFooter: true
html: 
    embed_local_images: true
    embed_svg: true
export_on_save:
    html: true
---


# U06 Reporting Aggregated Data Using the Group Functions

資料列分群並計算分群後的彙總資料
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

Write a query to display the minimum, maximum, sum, and average salary for each job type. Round your results to the nearest whole number.

![](img-01/u06-i01.png)

### Q2 

Write a query to display the number of people with the same job. 

Generalize the query so that a user in the HR department is prompted for a job title.

For example, when the user enters `IT_PROG`, he gets the following report:

![](img-01/u06-i02.png)

### Q3

Determine the number of distinct managers in the company. Use the `manager_id` column in the `employees` table to determine.

![](img-01/u06-i03.png)

### Q4

Create a report to display the manager id and the salary of the lowest-paid employee for that manager. Exclude anyone whose manager is not known. Exclude any groups where the minimum salary is $6,000 or less. Sort the output in descending order of salary.

![](img-01/u06-i04.png)


### Q5

Create a query that displays the total number of employees and, of that total, the number of employees hired in 2009, 2010, 2011, and 2012. Create appropriate column headings.

![](img-01/u06-i05.png)





