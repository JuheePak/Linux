### ⚔ LOAD DATA LOCAL INFILE command in MySQL

---

#### `LOAD DATA LOCAL INFILE`

- CSV 혹은 TXT 파일을 읽어 테이블로 데이터를 삽입하는 명령어
- 기본 INSERT 구문을 쓰는 것보다 15-20배정도 속도가 빠르다
- DB에서 DB로 마이그레이션 할 때 사용
- 파일 이름은 영어로 되어있어야 하며, 사용하는 파일의 권한을 갖고 있어야 한다



#### `1. 조건`

- LOCAL 옵션으로 DB 서버가 아닌 사용자의 컴퓨터에 존재하는 파일을 삽입할 때 사용한다
- 아래 옵션 명령어를 통해 ON 되어있는지 확인한다

```mariadb
show variavles like '%local%'; # ON 으로 나와야 함
mysql -u 유저이름 -p -h 서버명 DB명 --local-infile=1 # 옵션 ON 으로 설정
```



#### `2. 명령어`

- 나는 내 로컬 C드라이브에 있는 csv 파일을 import 할 것이므로 아래 명령어를 사용한다.

```mariadb
LOAD DATA LOCAL INFILE '파일경로' # 경로는 슬래쉬로
REPLACE INTO TABLE `localtest`.`computervalue`(테이블이름)
COLUMNS TERMINATED BY ',' ENCLOSED BY '"'
LINES TERMINATED BY '\n' IGNORE 1 LINES
(@id, @col1, @col2)
SET `id` = @id, `col1` = @col1, `col2` = @col2;
```



#### `3. 데이터 포맷 오류`

- String 타입을 data에 넣거나 int 타입의 허용 범위를 넘을 때 등 발생하는 오류
- 데이터 형을 칼럼에 맞게 변형후 삽입해야 한다