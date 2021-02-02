### 🔠 특정 문자 포함 또는 제외한 DB 검색 in MySQL

---

#### `1. 특정 키워드와 일치하는 텍스트 검색`

```mariadb
SELECT * 
FROM myt
WHERE mycol = '검색할텍스트';
```



#### `2. 특정 키워드로 시작하는/끝나는 텍스트 검색`

```mariadb
SELECT * 
FROM myt
WHERE mycol LIKE '%끝나는텍스트';
WHERE mycol LIKE '시작하는텍스트%';
WHERE mycol LIKE '%시작이든끝이든포함하는텍스트';
```



#### `3. 특정 키워드가 없는 텍스트 검색`

```mariadb
SELECT * 
FROM myt
WHERE NOT mycol='키워드';
```



#### `4. 여러개의 검색어를 하나의 칼럼에서 검색할 경우`

```mariadb
SELECT *
FROM myt
WHERE mycol LIKE '%키워드1%키워드2%';
```

