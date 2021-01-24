### Python3 및 가상환경 설치하기 🎶

---

##### `1. python3 설치`

- 기본적으로 python이 내장되어 있으나 최신 버전인 python 3.8로 업데이트 해준다.

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
  $ sudo apt-get install python3.8
  $ python3 --version # 잘 설치 되었는지 확인한다.
  ```



##### `2. 가상환경 설치`

- 이제 가상환경도 만들어준다.

  ```
  $ sudo apt install python3.8-venv
  $ python -m venv '가상환경이름'
  $ source myvenv/bin/activate # 가상환경 열기
  ```



가상환경까지 잘 들어가진다면, 설치가 완료 된 것이다!

pip까지 설치하면  편하겠지만 우선 파이썬과 가상환경을 설치하는 것으로 마친다.