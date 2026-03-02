---
export_on_save:
  html: true
  pdf: true
---


@import "../css/article_01.css"

# Structured Query Language for Databases (114B) - Department of Information Management
Updated on 2026/03/02

## Instructor
- Hung-Yi Chen  hychen39@gm.cyut.edu.tw
- Contact
  - Office: L746
  - Extension: 4556

## Learning Objectives

- Knowledge: Introduce the structured query language required for application development and data processing. Topics include Data Manipulation Language (DML), Data Definition Language (DDL), Data Control Language (DCL), use of the data dictionary, advanced querying, and user access control.
- Skills: Use SQL to write programs for data querying, data maintenance, table maintenance, and user management, and complete database-side tasks required in application development.
- Attitude: Develop professionalism and autonomous learning habits.
- Certification: Course content covers most topics in the Oracle Database SQL Certified Associate (Exam 1Z0-071).

Course Goals:
1. Students will understand the structured query language needed for application development and big data processing.
2. Students will be able to use SQL to write programs for data querying, data maintenance, table maintenance, and user management.
3. Students will be able to perform database-side tasks required in application development.
4. Students will develop professional attitudes and independent learning habits.


## Certification

- [Oracle Database SQL Certified Associate (Exam 1z0-071)](https://education.oracle.com/zh_TW/oracle-database-sql/pexam_1Z0-071)
  - Format: Multiple Choice
  - Duration: 120 minutes
  - Exam Price: NT$7,745
  - Number of Questions: 78
  - Passing Score: 63%

## Material

- WS1: Oracle Database 12c R2: SQL Workshop I, Study Guide, Volume 1, Oracle Corporation, 2017
- WS2: Oracle Database 12c R2: SQL Workshop II, Study Guide, Volume 1, Oracle Corporation, 2017

Download links are available in the later section of this syllabus.

## Course Outline

Topic arrangement strategy:

- Querying and Reporting > Tables and constraints > Data dictionary > Other database objects > Object privilege management

### Querying and Reporting

Basic querying and reporting:

- sorting, single-row functions, conversion functions, conditional expressions, aggregate functions
  - WS1 Unit 01 - 06

Advanced Querying I: 

- joins, subqueries, set operators
  - WS1 Unit 07 - 09

Advanced Querying II: 

- scalar subqueries, pairwise comparison subqueries, correlated subqueries, subquery unnesting, subqueries in DML
  - WS2 Unit 06, 07, 09

- Creating, updating, and deleting table data
  - WS1 Unit 10

### Creating tables and table constraints

- Creating tables and table constraints
  - WS1 Unit 11, WS2 Unit5 Constraint object

### Viewing database objects

- Viewing database objects: Data Dictionary Views
WS2 Unit 02

### Other database objects

- Creating other database objects: sequences, synonyms, indexes, views, and external tables
  - WS2 Unit 03, 04, 05 External Table

### Object privilege management
- Object privilege management
  - WS2 Unit 08



## Weekly Schedule

- Week 01: Introduction to Oracle commercial database and development tools
  - [WS1-U01 Entity Relationship (ER) Model and Table Structure](../course_practices/ws1-u01_en.md)
  - [WS1-U02 Retrieving Data the SQL SELECT statement](../course_practices/ws1-u02_en.md)

- Week 02: Data querying and reporting: sorting, single-row functions, conversion functions, conditional expressions, aggregate functions
  - [WS1-U03 Restricting and Sorting Data](../course_practices/ws1-u03_en.md)
  - [WS1-U04 Using single row functions to customize report](../course_practices/ws1-u04_en.md)


- Week 03: Data querying and reporting: sorting, single-row functions, conversion functions, conditional expressions, aggregate functions
  - Review of U02 - U03 assignments
  - [WS1-U04 Using single row functions to customize report](../course_practices/ws1-u05_en.md)

- Week 04: Day-off for the Spring Break (4/2 - 4/7)

- Week 05: Data querying and reporting: sorting, single-row functions, conversion functions, conditional expressions, aggregate functions
  - Review of U04 exercises
  - [WS1-U04 Using single row functions to customize report](../course_practices/ws1-u04_en.md)
  - [WS1-U05 Using conversion function and conditional expression](../course_practices/ws1-u04_en.md)

- Week 06: Advanced Querying I: joins, subqueries, set operators
  - [WS1-U6 Reporting Aggregated Data Using the Group Functions](../course_practices/ws1-u06_en.md)
  - [WS1-U7 Displaying Data from Multiple Tables Using Joins](../course_practices/ws1-u07_en.md)

- Week 07: Advanced Querying II: joins, subqueries, set operators
  - Review of WS1-U7 assignments
  - [WS1-U8 Using Subqueries to Solve Queries](../course_practices/ws1-u08_en.md)

- Week 08: Advanced Querying II: joins, subqueries, set operators

- Week 09: Midterm Exam


- Week 10: Advanced Subqueries: scalar subqueries, pairwise comparison subqueries, correlated subqueries, subquery unnesting, subqueries in DML
  - Midterm review
  - Review of WS1-U8 assignments
  - [WS1-U9 Using set operators](../course_practices/ws1-u09_en.md)

- Week 11: Advanced Subqueries: scalar subqueries, pairwise comparison subqueries, correlated subqueries, subquery unnesting, subqueries in DML
  - Review of WS1-U9 assignments
  - WS2-U6 Retrieving Data using suqueries
  - Assignment [WS2-u6](../course_practices/ws2-u06_en.md)

- Week 12: Advanced Subqueries: scalar subqueries, pairwise comparison subqueries, correlated subqueries, subquery unnesting, subqueries in DML
  - Review of WS2-U6 assignments
  - WS2-U6 Recursive Query
  - WS1-U10 Managing table using DML statements
  - Assignment [WS1-u10](../course_practices/ws1-u10_en.md)

- Week 13
  - Review of WS1-U10 assignments
  - WS2-U7 Manipulating data by using subqueries.
  - WS2-U9 Manipulating data using advanced queries (Multiple table insert)
  - Assignment [WS2-U7](../course_practices/ws2-u07_en.md)

- Week 14: Creating tables and table constraints
  - Review of WS2-U7 assignments
  - WS2-U9 Manipulating data using advanced queries
  - WS1-U11 Introduction to Data Definition Language (DDL)
  - Assignment [WS1-u11](../course_practices/ws1-u11_en.md)

- Week 15: Viewing database objects: Data Dictionary Views
  - Review of WS1-u11 assignments
  - WS2-U2 Introduction to Data Dictionary View
  - WS2-U5 Part I Managing schema objects: Managing constraints
  - Assignment [WS2-u05](../course_practices/ws2-u05_en.md)

- Week 16: Creating other database objects: sequences, synonyms, indexes, views, and external tables
  - Review of WS1-U5 assignments
  - WS2-U3 Creating sequences, synonyms, and indexes

- Week 17: Final Exam

- Week 18: Final Exam Review


## Grading Policy

- In-class exercises / quizzes / assignments: 50%
- Midterm exam (written/practical): 25%
- Final exam (written/practical): 25%

## Assignment Submission

- Submit on A4 paper
  - Code only; output results are not required

## Course Materials Download

Printing the Study Guide as hard copy is recommended for class use and exam preparation.

The download links is provided on the TronClass course page.


Notes:
- Course materials are copyrighted by Oracle and are for on-campus use only.
- Do not redistribute, share, or provide downloads without authorization.
- Any violation of copyright laws and related regulations is subject to legal liability.



## Other References

- Brumm, B. (2019). Beginning Oracle SQL for Oracle Database 18c : from novice to professional. In Springer eBooks. Apress. https://doi.org/10.1007/978-1-4842-4430-2 (Ebook available at CYUT library)

- Berg Hansen, K. (2020). Practical Oracle SQL : mastering the full power of Oracle database. Apress. (Ebook available at CYUT library)

- [Oracle Database 12c SQL Certified Associate 1Z0-071 @ Udemy](https://www.udemy.com/course/oracle-database-12c-sql-certified-associate-1z0-071/)

- [Information and study materials for 1Z0-071: Oracle Database 12c SQL @ Matthew Morris](http://www.oraclecertificationprep.com/apex/f?p=OCPSG:EXAM_DETAILS:::NO::P2_EXAM:1Z0-071)
