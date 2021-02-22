### 🎨 Changing the JupyterLab interface theme

---

- 긴 코드를 짤 때는 Pycharm을 주로 쓰지만, 코드 중간을 수정하거나 여러 블럭으로 나누어야 할 때 씀

- Pycharm처럼 JupyterLab도 테마를 **진한 색으로** 바꿔보기(~~눈을 보호하자~~ 👀)

- `[Anaconda prompt] `에서 아래 명령어 수행

  ```bash
  pip install jupytertheme
  ```

- 아래 명령어로 어떤 테마가 있는지 확인할 수 있다

  ``` bash
  jp - l
  ```

  ![캡처](https://user-images.githubusercontent.com/69948723/108643176-abe5cc80-74ec-11eb-889a-c967dad81ad6.PNG)

- 각 어떤 테마가 어떤 색인지 [여기](https://m.blog.naver.com/jjys9047/221571637230)사이트를 통해 확인 가능하다

- 나는 `chesterish`로 변경하였음

  ``` bash
  jt -t chesterish
  # 혹은
  jt -t {변경 원하는 theme 입력}
  ```

  