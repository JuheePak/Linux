### 🚲 ROLLUP Query

---

- Oracle에서는 ROLLUP, MySQL에서는 WITH ROLLUP을 사용한다

![캡처](https://user-images.githubusercontent.com/69948723/111088679-b1728780-856b-11eb-9a30-1bc1b5181a64.PNG)

- ROLLUP은 GROUP BY에서 선택한 기준에 따라 합계가 구해진다.
- 소그룹간의 소계를 계산한다. <-> ~~다차원간의 소계를 계산하는 CUBE~~

``` mysql
-- ROLLUP 사용하지 않는 경우
SELECT JOB_ID, SUM(SALARY)
FROM EMPLOYEES as e 
GROUP BY JOB_ID
ORDER BY JOB_ID;

-- ROLLUP 사용하는 경우
SELECT JOB_ID, SUM(SALARY)
FROM EMPLOYEES as e
GROUP BY ROLLUP(JOB_ID)
ORDER BY JOB_ID;
```
