### 🙌 WSL에서 Ubuntu 설치하기

---

### `1. WSL?`

- WSL(Windows Subsystem for Linux)는 윈도우에서 경량 가상화 기술을 사용해 리눅스를 구동할 수 있는 기능이다. 그 중에서도 기존의 WSL보다 개선된 WSL2를 설치하여 사용하였다.
- 윈도우에서도 리눅스 개발이나 도커와 같은 도구를 사용할 수 있다.  (사실 난 AWS S3 버킷에 이미지 업로드를 위해 설치하였다...)

### `2. 기본 환경 세팅`

- 기본 환경은 windows 10 이상이어야 하며, 혹시 이 글을 읽을 누군가와 + 내가 다시 WSL 설치할 때의 뻘짓을 막기 위해 우선 환경설정부터 하고 넘어간다.

  (1) Windows powershell을 관리자 모드로 접속한다.

  (2) 아래 명령어 2개를 입력해준다.

  ```
  > dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
  > dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
  ```

  (3) 컴퓨터를 재부팅 시켜주고, powershell을 다시 열어 wsl를 입력해준다.

  (4)  wsl 를 설치하라고 나온다. -> wsl를 설치하러 가면 된다.

- 내가 고생했던 부분은 바로 아랫 부분!

  wsl을 wsl2로 바꾸기 위해서는 Bios 에서 가상환경을 쓸 수 있게 해줘야 한다.

  컴퓨터를 부팅시길 때 Del 키(혹은 제조사 별로 다름)를 연타하고, Bios로 진입하여 `가상머신을 enable`로 바꿔준다.

- 혹은 아래 사이트에서 프로그램을 다운받아 내 CPU가 VT를 지원하는지 안 하는지 알 수 있다.

  https://leomoon.com/downloads/desktop-apps/leomoon-cpu-v/

- 둘다 초록 체크이면 가능, 오른쪽만 빨간색 X라면 Bios에서 가상머신을 활성화해주면 된다.

  (둘 다 빨간색 X이면 답이 없다...ㅠ)

  ![캡처](https://user-images.githubusercontent.com/69948723/105446827-4799d800-5cb6-11eb-8877-234ec9e7f1e7.PNG)

- 가상머신 활성화가 되었다면 Microsoft store 에서 Ubuntu 최신 버전을 다운 받아 준다.

- 처음에 ID과 PS를 설정하라고 나오는데, 까먹지 않을 비밀번호를 알아서 설정하면 된다.

  (패키지 설치할 때마다 비밀번호 입력해야 함)

### `3. WSL2로 버전 바꾸기`

- WSL를 설치해주면 아래 코드로 버전을 확인했을 때, 1로 나오게 된다.

```
wsl --list --verbose
```

- 아래 명령어를 입력하여 WSL 2를 기본 버전으로 설정해준다.

```
wsl --set-default-version 2
```

- 버전을 다시 확인한다. (아래와 같이 명령어를 입력해도 된다.)

```
wsl -l -v
```



수행 후 다시 버전을 확인했을 때 Version 2라고 나오지 않으면, 재부팅후 원인을 찾아야 한다.

Version 2로 확인 되었다면, 기본 셋팅 및 WSL 설치는 완료된 것이다 (야호! 🤗)

