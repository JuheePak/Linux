### 💫 JOIN query in MySQL (2)

---

- 약 100만개 정도 되는 데이터 끼리 JOIN을 쓰다가 속도가 너무 안 나와서 어떻게 하면 좋을지 고민했던 결과

- 원하는 데이터 외에 데이터 rows들을 DELETE 하는 것이 목적

- 쿼리는 정말 간단한데 속도도 빠르다 ~~(ㅠ_ㅠ)~~ ~~이러면서 배우는 거겠지 하는 중~~

- **쿼리의 목적: id와 ename이 존재하는 테이블 emptable에서 중복값이 존재하는 ename 중 가장 빠른(작은) id 값을 제외하고 중복값 제거**

  ```mariadb
  -- 조회
  SELECT id, ename
  FROM emptable
  WHERE id NOT IN (SELECT id FROM emptable GROUP BY ename ORDER BY id ASC) as i);
  
  
  ```

  