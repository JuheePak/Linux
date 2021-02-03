### 🐋 01_Installing Docker on WSL2

---

- 일반적으로는 Docker Desktop for Windows를 설치하여 사용한다

- 만약 Docker Desktop을 설치할 경우, 

  ✅ [Settings] -> [Use the WSL 2 based engine]

  ✅ [Resources] --> [Enable intergration with my default WSL distro]

  위의 두 섹션에 들어가서 체크하고 저장해준다

- WSL로 접속하여 아래 명령어를 입력하고, 잘 수행되는지 체크한다

``` bash
docker --version
docker-compose up
```

- 난ㄴ....난....위의 방식과 다르게 root 경로로 들어가서 docker를 설치하고, `.env`와  `.env.ops`를 옮겨놓았다
- AWS의 RDS로 접근하기 위해서는 관리자에게 따로 위의 파일들을 받아야 한다
- 나는 그냥 수행할 경우 수행이 안 되어 sudo를 꼭 붙여 명령어를 수행시켰다

``` bash
# docker 구동
sudo docker-compose up

# docker server 상태 확인
sudo docker ps

# 새 터미널에서 컨테이너 접속
sudo docker attach {containerID}

# 설치하지 않은 경우 의존성을 설치한다
yarn install
cd server && yarn install && cd ..
cd client && yarn install && cd ..

# 로컬 서버 접속
http://.....
```

- 컨테이너 접속이 잘 될 경우 로컬 서버로 접속하는데 문제 없을 것이다
- docker compose up이 되지 않아 하루를 꼬박 날렸다
- 두서없이 정리되어 있지만 컨테이너와 compose 부분 더 공부하고 정리해야겠다
- 어렵다 docker.... 
- Docker를 수행시키는 순서는 다음과 같다

``` bash
# WSL2 접속
# cmd --> wsl
# 가상환경으로
source {가상환경 경로}
# 다시 루트 경로로
cd {root 경로}
# docker 실행 및 서버 확인
sudo docker-compose up
sudo docker ps
# 혹시나 수행되고 있는 다른 container 서버가 있다면 kill한다
sudo docker kill {containerID}
# 새 터미널에서 위의 root 경로로 이동하는 과정까지 반복하고, docker를 attach 한다
sudo docker attach {containerID}
# 터미널에서 로컬서버로 접속이 된 것을 확인하고, 해당 주소로 가서 잘 수행되는지 확인한다.
```

