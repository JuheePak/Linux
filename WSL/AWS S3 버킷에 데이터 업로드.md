### 👍 AWS S3 버킷에 데이터 업로드하기

---

#### `1. 가상환경 활성화`

- 이전에 만들어놓은 가상환경에서 작업을 수행해야 한다.

  ```
  $ source /home/'사용자이름'/workspace/'가상환경이름'/bin/activate
  ```

#### `2. 파이썬 코드 수행`

- AWS S3 버킷에 데이터를 업로드 하기 위해 만들어놓은 코드 파일, 이 경우에는 .py가 있는 경로로 들어간다. (cd 명령어를 사용한다.)

  ```
  $ python '수행할 파이썬 소스 파일' /mnt/'업로드 할 파일 경로 입력'
  ```



하면 수행이 안 된다.

아래 AWS CLI 파일도 추가로 설치해줘야 한다.

https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2-linux.html

```
$ curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
```

시키는 대로 잘 설치하면, AWS를 사용할 때 부여받은 secret key, region 등을 입력하라고 나온다.

필수적으로 입력해야 하는 key 값들이 아니라면 무시하고 넘어가도 좋다.



다시 위의 python 소스가 있는 경로로 들어가, 업로드를 시도한다면 이제 잘 수행 될 것이다 👩‍🦰