### 🚲 ROLLUP Query

---

- Oracle에서는 ROLLUP, MySQL에서는 WITH ROLLUP을 사용한다
- ROLLUP은 GROUP BY에서 선택한 기준에 따라 합계가 구해진다.
- 소그룹간의 소계를 계산한다. <-> ~~다차원간의 소계를 계산하는 CUBE~~

``` mysql
SELECT country, product, sum(profit) 
FROM sales 
GROUP BY country, product WITH ROLLUP;
```

- MySQL은 Oracle 처럼 GROUPING 함수를 사용할 수 있다.
- GROUPING은 집계가 위치해야 할 row에서 **1혹은 0**을 리턴한다.