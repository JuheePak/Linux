### 🗨 02_Levenshtein distance

---

- 단어 혹은 문장과 같은 string 문자열 간의 형태적 유사성을 정의하는 방법 중 하나
- Edit distance라고도 불리는 Levenshtein distance는 한국어와 같이 초, 중, 종성으로 이루어진 언어를 고려한 metric은 아니다
- 단어 간 거리는 `형태적 거리`와 `의미적 거리`로 나눌 수 있다
  - `의미적 거리`: word embedding과 같은 방법으로 학습 가능. 단어 간 의미적 유사성(거리)를 벡터로 표현
  - 벡터 간 cosine distance는 매우 작으며 형태적 유사성은 없다
  - e.g.) Word2Vec