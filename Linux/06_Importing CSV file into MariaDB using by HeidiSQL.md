### 💥 Importing CSV file into MariaDB using by HeidiSQL

---

- `권한 문제`로 LOAD DATA INFILE 명령어를 사용하지 못했다 (하..AWS RDS 너무 싫다)
- 따라서 테이블 구조를 파악할 때 사용했던 HeidiSQL을 사용하여 CSV 파일을 import 한 결과 너무 빠르고! 쉽게! 되었기 때문에 기록으로 남긴다

#### `1. 연결하기`

![제목 없음](https://user-images.githubusercontent.com/69948723/106222932-d7de9c80-6223-11eb-8565-575d6c941570.png)

- 위의 [신규] 버튼을 눌러 세션을 생성하고 세션 이름은 편하게 바꾸어준다
- 호스트명에 나는 사용하고 있는 RDS url을 넣었고, 사용자 이름과 암호도 입력후 열기를 눌러준다
- 제대로 입력했다면 HeidiSQL이 실행된다



#### `2. CSV 파일 Import하기`

- 왼쪽에 보이는 데이터베이스 리스트 중 사용할 데이터 베이스를 눌러 속한 테이블을 파악한다
- 기존에 존재하는 테이블에 CSV 파일을 삽입하는 것이라면 테이블을 생성할 필요는 없지만, 새로운 테이블에 삽입할 경우 미리 테이블을 생성해주어야 한다

``` mariadb
CREATE TABLE 테이블명 (  
칼럼명 VANCHAR(50) NOT NULL
);
```

- 생성된 테이블을 새로고침 버튼(초록색 똥글뱅이)을 눌러 확인한다
- 해당 테이블에 CSV 파일을 아래와 같이 import한다
- 상단 [도구] --> [CSV 파일 가져오기..] 클릭
- 



