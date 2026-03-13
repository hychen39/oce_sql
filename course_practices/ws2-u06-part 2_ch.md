---
puppeteer:
   displayHeaderFooter: true
html: 
    embed_local_images: true
    embed_svg: true
export_on_save:
    html: true
---

#  WS2-L6 使用子查詢擷取資料
- 主題：遞迴查詢
## 題目

### Q1

請使用遞迴查詢計算下列算式總和：

$ 1 + 2^2 + 3^2 + ... + 10^2 $ 

產生的報表如下：

![](img-01/ws2-u06-i02.png)

### Q2

已知下列城市之間的運送成本，城市之間可以透過轉運送達其他目的地。例如途程 A > B > C，其成本為 $C_{AB}+C_{BC} = 2 + 3 = 5$。請使用遞迴查詢找出所有可能的運送路徑及總成本。

from\to | A | B | C | D 
--|--|--|--|--
A | | 2 |  | 
B | |  | 3 | 
C | |  |  | 5 
D | |  |  | 


![](img-01/ws2-u06-i03.png)

請執行以下程式建立所需資料表與資料列：

```sql {class=line-numbers}
create table trans(src_city varchar2(1), 
        tgt_city varchar2(1), 
        trans_cost number);
insert into trans values('A', 'B', 2);
insert into trans values('B', 'C', 3);
insert into trans values('C', 'D', 5);
commit;
```
