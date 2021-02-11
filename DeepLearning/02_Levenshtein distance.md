### 🗨 02_Levenshtein distance

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

- 기본적인 Levenshtein distance code는 구글이나 wikipedia에서 구현되어 있으니 쉽게 찾을 수 있다



``` python
def levenshtein(s1, s2, debug=False):
    if len(s1) < len(s2):
        return levenshtein(s2, s1, debug)

    if len(s2) == 0:
        return len(s1)

    previous_row = range(len(s2) + 1)
    for i, c1 in enumerate(s1):
        current_row = [i + 1]
        for j, c2 in enumerate(s2):
            insertions = previous_row[j + 1] + 1
            deletions = current_row[j] + 1
            substitutions = previous_row[j] + (c1 != c2)
            current_row.append(min(insertions, deletions, substitutions))

        if debug:
            print(current_row[1:])

        previous_row = current_row

    return previous_row[-1]
```



- 구체적인 처리 과정은 생략하지만, 아래 사이트를 통해 참고할 수 있다:)  [여기](https://lovit.github.io/nlp/2018/08/28/levenshtein_hangle/)
- 위의 코드는 deletion, substitution insertion 모두 비용을 같게 적용하였으나, 그 비용을 각각 다르게 적용할 수 있다. 아래 코드는 cost라는 변수를 추가하여 각 케이스의 비용을 다르게 처리하였다



``` python
def levenshtein(s1, s2, cost=None, debug=False): # cose 변수 추가
    if len(s1) < len(s2):
        return levenshtein(s2, s1, debug=debug)

    if len(s2) == 0:
        return len(s1)

    if cost is None:
        cost = {}

    # changed
    def substitution_cost(c1, c2):
        if c1 == c2:
            return 0
        return cost.get((c1, c2), 1)

    previous_row = range(len(s2) + 1)
    for i, c1 in enumerate(s1):
        current_row = [i + 1]
        for j, c2 in enumerate(s2):
            insertions = previous_row[j + 1] + 1
            deletions = current_row[j] + 1
            # Changed
            substitutions = previous_row[j] + substitution_cost(c1, c2)
            current_row.append(min(insertions, deletions, substitutions))

        if debug:
            print(current_row[1:])

        previous_row = current_row

    return previous_row[-1]
```



- 한글은 영어와 다르게 초/중/종성으로 나누어져 있으니,  그 부분을 고려하여 글자를 쪼개서 적용할 수 있다. 혹은 한글을 영어 이니셜로 변환하여 Levenshtein distance를 구하는 것도 한 가지 방법일 것이다.....!