---
UpLoader: 정민서
Date: 21.12.20
Rank: 
Language: Python
tags:
---

# 백준 2530번 인공지능시계

[백준 2530번 인공지능시계](https://www.acmicpc.net/problem/2530)  
  

### 소스 코드

```py
hour, min, sec = map(int, input().split())
digit = int(input())

result = hour*3600 + min*60 + sec + digit
hour = result // 3600 % 24
min = result % 3600 // 60
sec = result % 3600 % 60

print(hour, min, sec)
```
