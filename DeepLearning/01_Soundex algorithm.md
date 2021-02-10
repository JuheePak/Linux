### 🔠 Soundex algorithm

---

- 1920' 미국에서 영어 인명을 검색할 수 있는 Soundex algorithm을 개발

- 이름 혹은 스펠링이 유사한 내용을 검색할 때 사용

- **알고리즘의 규칙**은 아래와 같다

  - 1: 이름의 첫 번 째 글자를 저장하고, 이를 제외한 나머지 글자들 중 a, e, h, i, o, u, w, y를 제거

  - 2: 이름 안에 존재하는 글자들에 다음과 같은 번호를 부여

    ```
    b, f, p, v — 1
    c, g, j, k, q, s, x, z — 2
    d, t — 3
    l — 4
    m, n — 5
    r — 6
    ```

  - 3: 원래 이름에서 서로 인접하여 연속으로 나타나는 글자는 맨 앞에 하나만 남기고 나머지 제거
  - 4: 최종적인 결과를 **'글자숫자숫자숫자'**의 형태로 만들기 위해 숫자가 3개 이상일 경우 나머지는 생략, 3개 미만일 경우 뒤에 0을 붙여 형태를 통일시킨다.

  

- 코드는 아래와 같다

  ``` python
  """ replaceArr 여러개의 replace를 한꺼번에 처리하기 위한 함수 @param data 문자열 @param arr 바뀔 문자의 배열 @param to 바꿀 문자 @return data 치환 된 결과 """ 
  
  def replaceArr(data, arr, to): 
      for key in arr: 
          data = data.replace(key, to)    
      return data 
  
  """ soundex @param keyword @return String """ 
  
  def soundex(keyword): 
  # 규칙 1 
      # 코드의 첫 문자를 대문자로 저장 
      code = keyword[0].upper() keyword = keyword.lower() # 치환의 편의를 위해 모두 소문자로 치환 
      
      keyword = keyword[1:] # 키워드에서 맨 첫 글자 제외하고 나머지 추출 
      # 제거 할 문자 0으로 치환 
      keyword = replaceArr(keyword, ["a", "e", "h", "i", "o", "u", "w", "y"], "0") 
      
  # 규칙 2 
      keyword = replaceArr(keyword, ["b", "f", "p", "v"], "1") 
      keyword = replaceArr(keyword, ["c", "g", "j", "k", "q", "s", "x", "z"], "2")
      keyword = replaceArr(keyword, ["d", "t"], "3") keyword = keyword.replace("l", "4")
      keyword = replaceArr(keyword, ["m", "n"], "5") keyword = keyword.replace("r", "6") 
      
  # 규칙 3 
      keyword = list(keyword) 
      for i in range(len(keyword)-1, 0, -1): 
          if keyword[i] == keyword[i-1]: 
              del keyword[i] 
              
  # 규칙 4 
  	for i in keyword: 
          code = code + i code = code.replace("0", "") 
          code = code[0:4] # 0-3번째 까지의 문자만 저장 
          # 글자 수가 맞지 않는 경우 0 붙여주기 
      if len(code) < 4: 
          code = code + ("0" * (4 - len(code))) # 결과 반환 
      return code
```
  
  