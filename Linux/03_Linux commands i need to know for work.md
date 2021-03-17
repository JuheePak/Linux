### ✅ Linux commands i need to know for work

---

- 업무 중에 원격 컴퓨터와 파일을 pull & push 할 경우 자주  사용하는 명령어를 정리하였다 :)
- 리눅스 정말 하면 할수록 ~~어렵고~~ 신기하고 
- rsync가 없을 경우 설치

``` bash
apt-get install rsync
```



##### `1. 해당 디렉토리에 몇개의 파일이 있는지 확인하는 명령어`

``` bash
ls -l | grep ^- |wc -l
```



##### `2. rsync로 원격 서버에 파일 옮기기(Push)`

``` bash
rsync -avzhP [옮길 파일 명] -e "ssh -p [포트번호가 22가 아닐 경우 입력]" id@ip
```



##### `3. tar 압축 풀기`

``` bash
tar -xzvf [파일 이름.tar] -C [압축 풀 경로]
```



##### `4. 디렉토리 하위에 속한 파일 용량 출력`

``` bash
du -a /[디렉토리 이름]
```



##### `5. tar로 압축하기`

- Tape ARchiverdml의 약자로 파일을 묶거나 푸는데에 사용함
- 데이터 용량을 줄이기 위해 test.tar.gz 이렇게 사용하기도 함

``` bash
tar cvf [파일명][묶을 파일/경로]
rsync -zvh test.tar /home/ububtu/..../test_dir/
```

