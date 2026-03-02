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

Group rows and calculate aggregates
```mermaid
graph TD;
RestrictRows("Filter rows before grouping (WHERE clause)")
ColToGroup("Columns used for grouping (GROUP BY clause)")
GroupFun(Aggregate functions for each group) 
RestrictGroup("Filter groups (HAVING clause)")
OrderGroup("Sort groups (ORDER BY clause)")

RestrictRows-->ColToGroup
ColToGroup-->GroupFun
GroupFun-->RestrictGroup
RestrictGroup-->OrderGroup
```

Group Functions
```mermaid
graph LR;
GroupFun
AggDistinct("Aggregate distinct values (DISTINCT) ")
IgnoreValue(NULL values ignored by default )
NestGroups("Nested aggregate functions (up to 2 levels)")

GroupFun-->AggDistinct
GroupFun-->IgnoreValue
GroupFun-->NestGroups
```

## Practice

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




