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

- 조금 생소할 수도 있는데, 어렵게 생각할 것 없다
- JOIN은 물리적인 테이블 2개를 1개로 생각하고 쿼리문을 짰다면, SELF JOIN은 하나의 물리적인 테이블을 2개의 테이블처럼 쿼리문을 짜면 된다
- 다만 데이터가 클 경우 경우의 수가 많아지기 때문에 잘 고려해서 쓰자

- 아래는 EMP 테이블의 사원의 상사를 구하는 예제이다

``` mariadb
SELECT E.EMPNAME, M.EMPNAME
FROM EMPLOYEE AS E, EMPLOYEE AS M
WHERE E.MANAGER = M.EMPNO;
```



#### `4. Cartesian Product(Cross JOIN)`

- 카티션 곱은 RDBMS에서 사용하는 JOIN의 한 기법 중 하나이다
- WHERE 절이나 ON 절에 JOIN 조건을 주지 않고 수행한다
- FROM 절에서 참조한 테이블들의 행 개수를 각각 모두 곱한 값만큼의 결과가 나온다
- `데이터를 대량으로 복제할 때, 연결고리가 없는 두 테이블의 데이터를 무작위로 합칠 때 쓴다`

``` mariadb
SELECT m.id, m.title, p.id, p.title
FROM main as m, p_main as p;
```

