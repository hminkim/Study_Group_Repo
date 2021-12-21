---
UpLoader: 김형민
Date: 21.12.20
Rank: Level.2
Language: Python
tags: 문자열
---

# 프로그래머스 lv.2 오픈채팅방

[프로그래머스 - 오픈채팅방](https://programmers.co.kr/learn/courses/30/lessons/42888)  
  

### 풀이 과정  

두번의 반복으로 출입 로그를 출력  
  
첫번째 반복  
- record의 원소로 들어온 문자열 데이터를 슬라이싱하여 가공해서 `user` 딕셔너리에 `uid`값을 key로 닉네임을 value로 저장  
  
두번째 반복  
- 문자열 첫번째 문자로 들어오는 `Enter`, `Leave`, `Change`주문을 통해  
- `user` 딕셔너리에 저장되어 있는 `uid`를 key로 받아 `value`인 닉네임의 출입을 문자열 포맷을 통해 출력  


### 소스 코드

```python
def solution(record):
    answer = list()
    user = dict()
    for order in record:
        if order.split()[0] == 'Enter':
            user[order.split()[1]] = order.split()[2]
        if order.split()[0] == 'Change':
            user[order.split()[1]] = order.split()[2]
    
    for printing in record:
        if printing.split()[0] == 'Enter':
            answer.append('{}님이 들어왔습니다.'.format(user[printing.split()[1]]))
        if printing.split()[0] == 'Leave':
            answer.append('{}님이 나갔습니다.'.format(user[printing.split()[1]]))
    
    return answer
```