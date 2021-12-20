---
UpLoader: 정민서
Date: 21.12.20
Rank: 
Language: Python
tags:
---

# 백준 2525번 오븐시계

[백준 2525번 오븐시계](https://www.acmicpc.net/problem/2525)  
  

### 소스 코드

```py
hour, minut = map(int, input().split())
time = int(input())

result = hour*60 + minut + time
hour = result//60%24
minut = result%60
print("%d %d" %(hour, minut))
```
