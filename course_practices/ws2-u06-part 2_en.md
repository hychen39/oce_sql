---
puppeteer:
   displayHeaderFooter: true
html: 
    embed_local_images: true
    embed_svg: true
export_on_save:
    html: true
---

#  WS2-L6 Retrieving Data using suqueries
- Topic: Recursive queries
## Exercises

### Q1

Use a recursive query to calculate the sum of the following expression:

$ 1 + 2^2 + 3^2 + ... + 10^2 $ 

The generated report is as follows:

![](img-01/ws2-u06-i02.png)

### Q2

Given the shipping costs between cities below, goods can be transshipped to other destinations. For example, route A > B > C has cost $C_{AB}+C_{BC} = 2 + 3 = 5$. Use a recursive query to find all possible shipping routes and total costs.

from\to | A | B | C | D 
--|--|--|--|--
A | | 2 |  | 
B | |  | 3 | 
C | |  |  | 5 
D | |  |  | 


![](img-01/ws2-u06-i03.png)

Execute the following script to create the required table and rows:

```sql {class=line-numbers}
create table trans(src_city varchar2(1), 
        tgt_city varchar2(1), 
        trans_cost number);
insert into trans values('A', 'B', 2);
insert into trans values('B', 'C', 3);
insert into trans values('C', 'D', 5);
commit;
```
