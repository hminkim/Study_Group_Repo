---
UpLoader: 김형민
Date: 21.12.22
Rank: Level.2
Language: Python
tags: 문자열
---

# 프로그래머스 lv.2 JadenCase 문자열 만들기

[프로그래머스 - JadenCase 문자열 만들기](https://programmers.co.kr/learn/courses/30/lessons/12951)  
  

### 풀이 과정  

반복문을 통해 바로 직전 인덱스의 값이 빈칸(띄어쓰기)이거나 인덱스가 0(가장 첫 글자)일 때  
`upper()`함수를 통해 대문자화 하여 빈 문자열 `answer`에 더해주고  
나머지 모든 문자들은  
`lower()`함수를 통해 소문자화 하여 빈 문자열 `answer`에 더해준 뒤  
`answer` 반환

### 소스 코드

```python
def solution(s):
    answer = ''

    for idx, str in enumerate(s):
        if s[idx-1] == " " or idx == 0:
            answer += s[idx].upper()
        else:
            answer += s[idx].lower()
    return answer
```