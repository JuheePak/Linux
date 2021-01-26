### 👸 Basic Linux commands

---

#### `1. ls`

- 현재 위치의 파일 목록을 조회하는 명령어

  ```
  ls -1 # 파일의 상세정보
  ls -a # 숨어있는 파일도 표시
  ls -t # 최신 파일부터 표시
  ls -t # 오래된 파일부터 표시
  ```

  

#### `2. cd`

- change directory로 경로를 이동할 때 사용하는 명령어

  ```
  cd ~ # 홈 디렉토리로 바로 이동
  cd .. # 상위 디렉토리로 이동
  cd/dir # 절대 경로 dir로 이동
  cd - # 이동하기 바로 전의 디렉토리로 이동
  ```

  

#### `3. mkdir`

- 새로운 경로를 만들 때 사용하는 명령어

  ```
  mkdir dirname # dirname의 디렉토리를 생성
  mkdir -p dirname/dirname2 # dirname의 디렉토리를 생성하고, 그 하위에 dirname2라는 디렉토리도 생성
  ```

  

#### `4. mv`

- 파일을 이동시키는 명령어

- cp와 비슷하지만 mv는 복사하는 것이 아니라 원본 파일이 남지 않도록 이동시킴

- 이름을 변경할 때에도 쓰인다

  ```
  mv filename1 filename2 # filename1을 filename2로 이름을 변경
  ```

  

#### `5. rm`

- remove로 파일 혹은 디렉토리를 사용할 때 사용하는 명령어

  ```
  rm filename # filename을 삭제
  rm -f filename # filename을 묻지 않고 삭제
  rm -r dir # dir 이라는 경로를 삭제. 경로의 경우 -r 옵션 없이 삭제 불가능
  ```



#### `6. cat`

- catenate로 파일 이름을 인자로 받아 그 내용을 출력하는 명령어

  ```
  cat filename # filename의 내용을 출력
  cat filename1 filename2 # filename1과 filename2를 이어 출력
  cat filename1 filename2 | head # filename1과 filename2를 출력하는데 처음부터 10번째까지만 출력
  cat fileanem1 filename2 | tail # filename1과 fileaname2를 출력하는데 끝에서부터 10번째까지만 출력
  ```




#### `7. vi`

- 편집기 명령어

- 명령 모드, 입력 모드, 마지막 행 모드 3가지로 구성

  - 명령& 입력 모드: 방향기를 사용하여 커서 이동 가능

    ```
    dd # 한 줄 삭제
    yy # 한 줄 붙여넣기
    x # 한 글자 삭제
    u # 방금 한 명령 취소, ctrl+z와 같음
    i # 현재 커서 위치에서 삽입
    G # 파일 끝으로 이동
    o # 줄의 맨 앞 으로 이동
    $ # 줄의 맨 뒤로 이동
    ```

  - 마지막 행 모드: 콜론(:)입력 후 입력하는 명령어

    ```
    w # 현재 파일 명으로 저장. 저장만 되고 창이 종료되지 않음
    w filename # filename으로 저장. 저장만 되고 창이 종료되지 않음
    q # 편집기 종료. 저장 안 됨
    q! # 강제 종료
    wq # 저장 후 종료
    set nu # vi 라인 번호 출력
    ```

    