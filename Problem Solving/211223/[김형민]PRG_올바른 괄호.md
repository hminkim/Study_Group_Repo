---
UpLoader: 김형민
Date: 21.12.23
Rank: Level.2
Language: Python
tags: 스택
---

# 프로그래머스 lv.2 올바른 괄호

[프로그래머스 - 올바른 괄호](https://programmers.co.kr/learn/courses/30/lessons/12909)  
  

### 풀이 과정  

전형적인 Stack으로 괄호 짝 맞추기 문제
  
### 소스 코드

```python
def solution(s):
    stack = list()
    for i in s:
        if i == "(":
            stack.append(i)
        elif i == ")":
            if stack and stack[-1] == "(":
                stack.pop()
            else:
                return False
    if len(stack) == 0:
        return True
    else:
        return False
```