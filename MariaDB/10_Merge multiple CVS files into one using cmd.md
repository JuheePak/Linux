### 🎃 Merge multiple CSV files into one using cmd

---

- Python과 같은 프로그래밍 언어로 CSV 파일을 합치는 방법보다 빠르다
- 단, 파일은 다 같은 **csv 확장자이거나 txt 확장자**여야 한다
- 또 합치려는 csv 파일이 **모두 같은 디렉토리**에 존재해야 한다



#### `순서`

- Windows의 cmd 창에서 해당 csv 파일 혹은 txt 파일이 있는 경로로 이동한다
- 아래 명령어를 입력해준다. `type *.csv > {합쳐진 csv 파일의 이름.csv}`
- 합치려고 했던 파일을 하나씩 보여주면서 merge가 완료된다