### 🎊 Inserting multiple rows in MySQL

---

#### ` 대용량 데이터 삽입하는(insert) 방법 `

- 대용량 데이터를 삽입하는 방법은 아래 4가지가 있다
  - One transaction
  - Insert - select
  - Bulk insert
  - LOAD DATA INFILE

#### `1. One transaction`

- 하나의 transaction으로 묶어 처리하는 방법

``` mariadb
start transaction;
insert into myt (a, b, c) values (1, 2, 3);
insert into myt (a, b, c) values (1, 2, 3);
insert into myt (a, b, c) values (1, 2, 3);
commit transaction;
```

#### `2. Insert - select`

- SELECT Query로 여러 행을  한 번에 insert 하는 방법이다
- One transaction보다 간단하고 빠르지만, READ_LOCK이 잡혀야 한다

```mariadb
insert into myt(a, b, c)
select d, e, f
from yourt
where {조건};
```

#### `3. Bulk insert`

- 필수값을 지키지 않는 경우 rollback 된다
- 다량의 values를 한번의 transaction에서 처리가 된다
- row의 개수는 아래와 같이 1GB 로 설정 가능하다

``` mariadb
show variables like ‘max_allowed_packet’; # max값 확인
set global max_allowed_packet=1073741824; # 1GB로 설정
```

- 만약 삽입 대상 테이블에 자동 index 설정하는 auto increment 칼럼이 존재한다면 해제하는 것을 권장한다

#### `4.LOAD DATA INFILE (다들 얘만 대문자로 쓰는데 소리지르는 느낌ㅎ)`

- 데이터 파일을 로딩하여 테이블을 생성하면서 insert 하는 방법
- 구분자를 잘 사용하여야 한다
- INTO TABLE 아래의 출력 형태를 유의하여 작성해야 한다

``` mariadb
LOAD DATA INFILE '절대경로'
INTO TABLE '테이블명'
FIELDS TERMINATED BY '\t' ENCLOSED BY "" ESCAPED BY '\\'
LINES STARTING BY '' TERMINATED BY '\n'
```

