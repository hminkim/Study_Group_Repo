---
UpLoader: 김형민
Date: 21.12.21
Rank: Level.2
Language: Python
tags: 스택, 큐
---

# 프로그래머스 lv.2 프린트

[프로그래머스 - 프린트](https://programmers.co.kr/learn/courses/30/lessons/42587)  
  

### 풀이 과정  

`location`을 확인 할 문서 인덱스를 담은 배열을 생성 한 뒤  

`priorities`의 원소가 우선 순위가 가장 높은지를 확인하기 위해 `max()` 함수를 통한 비교로 우선순위가 가장 높은 지 반복하여 확인  
- 만약 우선순위가 가장 높다면  
    - `doc_loc` 배열을 확인해서 `location`과 일치한지 확인  
        - 일치한다면 반복문을 종료  
        - 일치하지 않는다면 `priorities`와 `doc_loc`의 0번째 인덱스의 값을 `pop()` 한 후 `answer`에 1을 더함  
    - `doc_loc` 배열을 확인해서 `location`과 일치하지 않는다면 
        - `priorities`와 `doc_loc`의 0번째 인덱스의 값을 `pop()` 한 후 `append()` 하여 가장 뒤에 붙여줌  
모든 과정이 반복되어 끝나거나 중간에 `location`과 일치한 인덱스의 값이 나와 break 된다면 `answer` 반환
  
### 소스 코드

```python
def solution(priorities, location):
    answer = 1
    doc_loc = list()

    # 문서 인덱스를 담은 배열 생성
    for idx, p in enumerate(priorities):
        doc_loc.append(idx)

    while priorities:
        if priorities[0] == max(priorities):
            if doc_loc[0] == location:
                break
            else:
                priorities.pop(0)
                doc_loc.pop(0)
                answer += 1
        elif priorities[0] != max(priorities):
            priorities.append(priorities.pop(0))
            doc_loc.append(doc_loc.pop(0))

    return answer
```