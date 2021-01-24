### Python3 및 가상환경 설치하기 🎶

---

##### `1. python3 설치`

- 기본적으로 python이 내장되어 있으나 최신 버전인 python 3.8.5로 업데이트 해준다.

- wsl로 접속하여, 아래의 명령어를 입력해준다.

  ```
  $ sudo apt-get update
  $ sudo apt-get upgrade python3
  ```

- 디렉토리를 하나 만들어주고 파이썬과 가상환경을 설치할 것이다.

  ```
  cd /home/'username'
  mkdir '내가 만들 경로 이름 = workspace'
  cd workspace # 만든 디렉토리로 이동
  ```

- python3 최신버전을 설치한다.

  ```
  $ sudo apt-get install python3.8.5
  $ python3 --version # 잘 설치 되었는지 확인한다.
  ```

  