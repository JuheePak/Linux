### 🗨 02_Levenshtein distance - 작성중

---

- 단어 혹은 문장과 같은 string 문자열 간의 형태적 유사성을 정의하는 방법 중 하나

- <u>**한 string s1에서 다른 string s2로 교정하는데 드는 최소 횟수를 두 strings 간의 거리로 정의함**</u>

- Edit distance라고도 불리는 Levenshtein distance는 한국어와 같이 초, 중, 종성으로 이루어진 언어를 고려한 metric은 아니다

- 단어 간 거리는 `형태적 거리`와 `의미적 거리`로 나눌 수 있다

  - `의미적 거리`: word embedding과 같은 방법으로 학습 가능. 단어 간 의미적 유사성(거리)를 벡터로 표현
  - 벡터 간 cosine distance는 매우 작으며 형태적 유사성은 없다
  - e.g.) Word2Vec

  - `형태적 거리`: string distance.
  - e.g.) Jaro-winkler, Levenshtein (string 이용하여 정의), Hamming, Cosine, TF-IDF distance(string 을 벡터로 표현하여 거리를 정의)

- 그 중 Levenshtein distance는 edit 방법을 `3가지`로 나눈다

  - Delete: 집**에**가고싶다 --> 집가고싶다 '**에**' 삭제
  - Insert: 집가자 --> 집**에**가자 **'에'** 추가
  - Substitution: 집에가자 --> 집에가**장** **자를 장으로 치환**

  

