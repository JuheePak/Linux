### 🤝 JOIN in MySQL

---

이전에 학부때 배운 DBA 수업은 Oracle SQL을 썼는데, MySQL과는 큰 차이는 없는 것 같다

그래도 근소한 차이는 존재하기에 정리하고 넘어간다

#### `1. INNER JOIN`

- A table과 B table의 교집합으로 생각하면 된다
- WHERE절에서 조건을 주어도 되고, ON 으로 조건을 주어도 된다
- LEFT JOIN, RIGHT JOIN보다 속도가 빠르다고 한다

```mariadb
SELECT a.tableA b.tableB 
FROM tableA AS a JOIN tableB as b ON a._id = b._id;
```



#### `2. LEFT (OUTER) JOIN, RIGHT (OUTER) JOIN`

- 차집합을 생각하면 된다
- 각 왼쪽 집합의 차집합, 오른쪽 집합의 차집합을 구한다
- A LEFT JOIN B 와 B RIGHT JOIN A는 같은 식이다
- OUTER는 생략해도 된다

``` mariadb
-- LEFT OUTER JOIN의 예
SELECT n.id, n.name, 
FROM new_table as n LEFT OUTER JOIN main as m ON (n.id = m.id) 
WHERE m.id IS NULL;
```



#### `3. SELF JOIN`