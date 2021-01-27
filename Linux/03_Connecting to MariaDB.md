### ⚙ Connecting to MariaDB

---

#### `1. mariaDB에 저장된 데이터 불러오기`

- 관리자모드로 cmd 창을 열어 WSL 접속
- 아래 명령어를 입력
- 만약 에러가 난다면 mysql을 sudo 명령어로 입력하여 설치하고 다시 아래 명령어 수행

```mariadb
mysql -h 호스트입력 -P 포트번호입력 -u 유저이름입력 -p db이름입력
```

- 비밀번호를 입력하라고 나오는데, DB 계정의 비밀번호를 입력한다
- 아래와 같은 창이 보인다면 성공! ✨

```mariadb
Welcome to the MariaDB monitor. blahblah
```

- 아래와 같은 명령어를 입력하여 호스트와 유저 정보를 확인하고 데이터베이스를 모두 읽는다

```mariadb
SELECT Host, User, Plugin FROM mysql.user;
show databases; # 명령어의 끝에 ; 혹은 \G 를 붙여준다
```

- 데이터 베이스의 목록이 보인다. 사용하고자 하는 데이터베이스의 이름을 아래와 같이 입력한다

```mariadb
use mydatabase;
Database changed # 잘 연결됨
```

- `MariaDB [mydatabase] >  ` 로 다음 입력창이 보여진다면 잘 연결 된 것이다.

``` mariadb
show tables; # mydatabase의 데이터 테이블을 볼 수 있다.
```

- 연습으로 하나의 테이블을 불러와본다

``` mariadb
select * from mytable where id = '1';
select * from mytable where id = '1' limit 10; # 10개만
```



#### `2. 데이터 테이블의 상태를 확인하기`

- auto commit 기능을 해제하기 위해 어떤 Engine을 사용하는지 확인한다
- mysql 최신 버전의 경우 InnoDB를 쓰고 있다 하지만, 그래도 확인해본다

``` mariadb
show table status; # engine 칼럼에서 확인할 수 있다
```

- InnoDB임을 확인했다면, 아래 명령어를 입력하여 auto commit을 꺼준다

``` mariadb
set autocommit = 0; # ON
set autocommit = 1; # OFF
Qeury OK... # 성공적으로 수행됨
```



#### `3. transaction 사용하기`

- auto commit  기능을 위에서 해제하였기에 transaction을 수행하고, 내 마음대로 rollback과 commit을 쓸 수 있다
- `단, Drop과 alter table은 rollback이 되지 않으니 주의한다`
- transaction은 아래 명령어로 시작하며, 이후 rollback과 commit 명령어를 입력하고 다시 test를 원한다면 아래의 명령어를 재입력해야 한다

``` mariadb
start transaction; # 혹은 start begin;
>>> Query Ok... # 잘 된 것
```

- 명령어 수행 후 rollback과 commit 명령어는 아래와 같다

``` mariadb
rollback;
commit; #꼭 주의하여 사용한다!!!!!!!!!!
```

