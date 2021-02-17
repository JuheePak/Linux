### 🎃 Merge multiple CSV files into one using cmd

---

- Python과 같은 프로그래밍 언어로 CSV 파일을 합치는 방법보다 빠르다
- 단, 파일은 다 같은 **csv 확장자이거나 txt 확장자**여야 한다
- 또 합치려는 csv 파일이 **모두 같은 디렉토리**에 존재해야 한다
- 보통 합치려는 파일이 pandas로 만든 dataframe일 경우가 높다. 이때 합쳐지는 파일들의 컬럼명까지 모두 저장된다는 점을 염두해야 한다(6개의 데이터 프레임을 합치면 6개의 컬럼명이 모두 붙여진다)
- 간단하지만 판다스에서 merge 나 concat 함수를 쓰는 것보다 훨씬 훨씬 빠르다 😁



#### `순서`

- Windows의 cmd 창에서 해당 csv 파일 혹은 txt 파일이 있는 경로로 이동한다
- 아래 명령어를 입력해준다. `type *.csv > {합쳐진 csv 파일의 이름.csv}`
- 합치려고 했던 파일을 하나씩 보여주면서 merge가 완료된다

``` bash
cd C:/workspace/myfolder
type *.csv > {all_merge_file.csv}
```

