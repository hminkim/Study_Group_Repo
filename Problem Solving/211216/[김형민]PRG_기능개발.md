---
UpLoader: 김형민
Date: 21.12.15
Rank: Level.2
Language: Python
tags: 스택/큐
---

# 프로그래머스 lv.2 기능 개발

[프로그래머스 - 기능 개발](https://programmers.co.kr/learn/courses/30/lessons/42586)  
  

### 풀이 과정  

하루하루 업무를 진행하여 만약 `progresses`의 원소 중 인덱스가 0인 process가 100을 넘긴다면 일이 마무리 되었다는 이야기므로  
`progresses`와 `speeds`의 왼쪽 원소를 `popleft()`하고 `cnt`에 1을 추가  
만약 그 다음 업무 역시 100을 넘긴다면 그 업무 또한 마무리 되었다는 의미이므로 `progresses`와 `speeds`의 왼쪽 원소를 `popleft()`를 반복하고 `cnt`에 1을 플러스  
  
그렇게 한 싸이클이 끝난다면 그날 배포한 업무의 갯수인 `cnt`를 배열 `answer`에 `appned()`  
  
모든 반복이 끝난다면 `progresses`의 원소가 비었을 것이므로 `answer` 반환  

### 소스 코드

```python
import copy
from collections import deque

def solution(progresses, speeds):
    answer = []
    progresses = deque(progresses)
    speeds = deque(speeds)

    while progresses:
        cnt = 0

        for idx in range(len(progresses)):
            progresses[idx] = progresses[idx] + speeds[idx]

        for work in copy.deepcopy(progresses):
            if progresses.index(work) == 0 and work >= 100:
                progresses.popleft()
                speeds.popleft()
                cnt += 1
        if cnt != 0:
            answer.append(cnt)

    return answer
```