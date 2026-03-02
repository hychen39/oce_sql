---
export_on_save:
  html: true
  pdf: true
---


@import "../css/article_01.css"

# 資料庫結構化查詢語言 (114B) - 資訊管理系
Updated on 2026/03/02

## 授課教師
- 陳宏益 hychen39@gm.cyut.edu.tw
- 聯絡方式
  - 研究室 L746
  - 分機 4556

## 教學目標

- 知識:介紹應用程式開發及資料處理時所需要的資料庫結構化查詢語言。主題包括資料操作語言(Data Manipulation Language)、資料定義語法(Data Definition Language)、資料控制語言(Data Control Language)、資料字典的使用、進階查詢、 及使用者存取控制。
- 技能: 使用結構化查詢語言撰寫查詢資料、維護資料、維護表格、管理使用者等程式，以完成應用程式開發時所需的資料庫端的工作。
- 態度: 培養專業及自主學習的態度。
- 證照： 課程內容涵蓋 Oracle Database SQL Certified Associate (Exam 1z0-071)證照考試的大部份主題

課程目的：
1. 學生能瞭解應用程式開發及大數據資料處理時所需要的資料庫結構化查詢語言。	
2. 學生能使用結構化查詢語言撰寫查詢資料、維護資料、維護表格、管理使用者等程式。	
3. 學生能應用程式開發時所需的資料庫端的工作。	
4. 培養學生專業及自主學習的態度。


## 證照

- [Oracle Database SQL Certified Associate (Exam 1z0-071)](https://education.oracle.com/zh_TW/oracle-database-sql/pexam_1Z0-071)
  - Format: Multiple Choice
  - Duration: 120 minutes
  - Exam Price: NT$7,745
  - Number of Questions: 78
  - Passing Score: 63%


## 課程大綱

主題安排策略: 查詢與報表 > 資料表及限制 > 資料字典 > 資料庫其它物件 > 物件的授權管理

### 查詢與報表

基礎查詢與報表

- 排序、單列函數、轉換函數、條件運算式、聚合函數
  - WS1 Unit 01 - 06

資料查詢進階 1

- 資料表合併查詢、子查詢、合併多合查詢的結果(Set operator)
  - WS1 Unit 07 - 09

資料查詢進階 2

- 純量子查詢、成對比較子查詢、相依子查詢、子查詢的分解、DML 中使用子查詢
  - WS2 Unit 06, 07, 09
- 資料表的內容建立、更新、與刪除
  - WS1 Unit 10

### 建立資料表及表格限制式 

- 建立資料表及表格限制式 
  - WS1 Unit 11, WS2 Unit5 Constraint object

### 檢視資料庫中的物件

- 資料字典視圖(Data Dictionary View)
  - WS2 Unit 02

### 其它資料庫物件

- 建立資料庫其它物件: 序列器、同義詞、索引、及視圖(View)、外部表格
  - WS2 Unit 03, 04, 05 External Table

### 物件的授權管理

- 物件的授權管理
  - WS2 Unit 08



## 教學進度安排

- 第01週 ：	Oracle 商用資料庫及開發工具介紹	
  - [WS1-U01 Entity Relationship (ER) Model and Table Structure](../course_practices/ws1-u01_ch.md)
  - [WS1-U02 Retrieving Data the SQL SELECT statement](../course_practices/ws1-u02_ch.md)

- 第02週：	資料查詢與報表: 排序、單列函數、轉換函數、條件運算式、聚合函數
  - [WS1-U03 Restricting and Sorting Data](../course_practices/ws1-u03_ch.md)
  - [WS1-U04 Using single row functions to customize report](../course_practices/ws1-u04_ch.md)


- 第03週：	資料查詢與報表: 排序、單列函數、轉換函數、條件運算式、聚合函數
  - U02 - U03 作業檢討
  - [WS1-U04 Using single row functions to customize report](../course_practices/ws1-u05_ch.md)
  
- 第04週：	資料查詢與報表: 排序、單列函數、轉換函數、條件運算式、聚合函數
  - u04 練習檢討
  - [WS1-U04 Using single row functions to customize report](../course_practices/ws1-u04_ch.md)
  - [WS1-U05 Using conversion function and conditional expression](../course_practices/ws1-u04_ch.md)

- 第05週： 放假(春假 4/2 - 4/7)
  
- 第06週： 資料查詢進階 1: 資料表合併查詢、子查詢、合併多合查詢的結果(Set operator)
  - [WS1-U6 Reporting Aggregated Data Using the Group Functions](../course_practices/ws1-u06_ch.md)
  - [WS1-U7 Displaying Data from Multiple Tables Using Joins](../course_practices/ws1-u07_ch.md)


- 第07週： 資料查詢進階 2: 資料表合併查詢、子查詢、合併多合查詢的結果(Set operator)
  -  WS1-U7 作業檢討
  - [WS1-U8 Using Subqueries to Solve Queries](../course_practices/ws1-u08_ch.md)

- 第08週： 資料查詢進階 2: 資料表合併查詢、子查詢、合併多合查詢的結果(Set operator)
  
- 第09週: 放假(5/1 勞動節)

- 第10週: 期中考
  
- 第11週: 子查詢進階: 純量子查詢、成對比較子查詢、相依子查詢、子查詢的分解、DML 中使用子查詢
  - 檢討期中考
  - WS1-U8 作業檢討 
  - [WS1-U9 Using set operators](../course_practices/ws1-u09_ch.md)

- 第12週: 子查詢進階: 純量子查詢、成對比較子查詢、相依子查詢、子查詢的分解、DML 中使用子查詢
  - WS1-U9 作業檢討
  - WS2-U6 Retrieving Data using suqueries
  - Assignment [WS2-u6](../course_practices/ws2-u06_ch.md)

- 第13週: 子查詢進階: 純量子查詢、成對比較子查詢、相依子查詢、子查詢的分解、DML 中使用子查詢
  - WS2-U6 作業檢討
  - WS2-U6 Recursive Query
  - WS1-U10 Managing table using DML statements
  - Assignment [WS1-u10](../course_practices/ws1-u10_ch.md)
  
- 第14週  
  - WS1-U10 作業檢討
  - WS2-U7 Manipulating data by using subqueries.
  - WS2-U9 Manipulating data using advanced queries (Multiple table insert)
  - Assignment [WS2-U7](../course_practices/ws2-u07_ch.md)

- 第15週：	建立資料表及表格限制式
  - WS2-U7 作業檢討
  - WS2-U9 Manipulating data using advanced queries
  - WS1-U11 Introduction to Data Definition Language (DDL)
  - Assignment [WS1-u11](../course_practices/ws1-u11_ch.md)
  
- 第16週：放假(6/19 端午節)

- 第17週：	期末考
    
- 第18週：	期末考檢討


## 評分方式

- 課堂練習/小考/作業 50%
- 期中考(筆試/術科) 25%
- 期末考(筆試/術科) 25%

## 作業繳交方式

- A4 紙本繳交
  - 只撰寫程式碼，不需附輸出結果

## 教材下載

建議輸出 Study Guide 檔案為紙本, 以利上課及考試準備.

- [Study guides Volume 1 and 2 下載](https://o365cyut-my.sharepoint.com/:u:/g/personal/t2005022_o365_cyut_edu_tw/Ea-pRMN02fRNiD3-7FmLRFABob6DOBmLx0i2WWAFbsMtTw?e=pVgb0d)


注意:
- 教材版權為 Oracle 公司, 限校園內使用. 
- 請勿任意轉傳、分享、供下載等。
- 若有違反著作權等相關法令之行為者請自負法律責任。



## 其它參考資料

- Brumm, B. (2019). Beginning Oracle SQL for Oracle Database 18c : from novice to professional. In Springer eBooks. Apress. https://doi.org/10.1007/978-1-4842-4430-2 (Ebook available at CYUT library)

- Berg Hansen, K. (2020). Practical Oracle SQL : mastering the full power of Oracle database. Apress. (Ebook available at CYUT library)

- [Oracle Database 12c SQL Certified Associate 1Z0-071 @ Udemy](https://www.udemy.com/course/oracle-database-12c-sql-certified-associate-1z0-071/)

- [Information and study materials for 1Z0-071: Oracle Database 12c SQL @  Matthew Morris](http://www.oraclecertificationprep.com/apex/f?p=OCPSG:EXAM_DETAILS:::NO::P2_EXAM:1Z0-071)


