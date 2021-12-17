---
UpLoader: 김형민
Date: 21.12.17
Rank: Level.2
Language: Python
tags: 구현
---

# 프로그래머스 lv.2 스킬트리

[프로그래머스 - 스킬트리](https://programmers.co.kr/learn/courses/30/lessons/49993)  
  

### 풀이 과정  

스킬을 순서대로 담은 `arr`안의 스킬들을 순차적으로 `pop()`하여 pop한 스킬과 다음 차례의 스킬이 다르면 `break`함  

`for-else`문을 통해 만약 정상적으로 for문이 끝까지 돌아갔다면 `answer`에 1을 더해줌    

### 소스 코드

```python
def solution(skill, skill_trees):
    answer = 0

    for skills in skill_trees:
        arr = list(skill)

        for skl in skills:
            if skl in skill:
                if skl != arr.pop(0):
                    break
        else:
            answer += 1

    return answer
```