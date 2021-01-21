### WSL에서 Ubuntu 설치하기

---

1. #### `WSL`?

- WSL(Windows Subsystem for Linux)는 윈도우에서 경량 가상화 기술을 사용해 리눅스를 구동할 수 있는 기능이다. 그 중에서도 기존의 WSL보다 개선된 WSL2를 설치하여 사용하였다.
- 윈도우에서도 리눅스 개발이나 도커와 같은 도구를 사용할 수 있다.  (사실 난 AWS S3 버킷에 이미지 업로드를 위해 설치하였다...)

2. #### `기본 환경 세팅`

- 기본 환경은 windows 10 이상이어야 하며, 혹시 이 글을 읽을 누군가와 + 내가 다시 WSL 설치할 때의 뻘짓을 막기 위해 우선 환경설정부터 하고 넘어간다.

  (1) Windows powershell을 관리자 모드로 접속한다.

  (2) 아래 명령어 2개를 입력해준다.

  ```
  > dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
  > dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
  ```

  (3) 컴퓨터를 재부팅 시켜주고, powershell을 다시 열어 wsl를 입력해준다.

  (4)  wsl 를 설치하라고 나온다. -> wsl를 설치하러 가면 된다.

