---
UpLoader: 김형민  
Date: 21.09.30  
Rank: Gole.5  
Language: Python  
tags: 수학  
---

# 백준 1011 Fly me to the Alpha Centauri

[백준 1011 - Fly me to the Alpha Centauri](https://www.acmicpc.net/problem/1011)  
  
### 풀이 과정  
  
![1011 풀이](https://user-images.githubusercontent.com/45965405/135484328-86a9fe6f-9ec7-4101-b9bc-c18ff8633b98.png)    

사진에서 보듯 기준이 되는 `standard`는 2의 배수만큼 증가  
매번 더해주는 양을 변수 `sum`에 저장하고  
y와 x 사이의 거리 `distance`가 기준점 `standard`를 초과할 때까지 `standard`와`sum`의 증가 반복  
  
(`distance`가 기준점 `standard`를 초과 할 때 바로 반복문이 끝나는 것이 아니기 때문에 아래 연산에서는 `sum-2`를 대입)  
  
만약 `standard`에서 `sum-2`를 반으로 나눈 값을 뺀 값이 `distance`보다 크거나 같으면  
`sum-2`에서 1을 뺀 값을 출력
아니라면  
`sum-2`를 출력  
  
### 소스 코드

```python
import sys

T = int(sys.stdin.readline())

for _ in range(T):
    x, y = map(int, sys.stdin.readline().split())

    distance = y - x
    standard = 0
    sum = 0

    while distance > standard:
        standard += sum
        sum += 2

    if (standard - ((sum-2)/2)) >= distance:
        print((sum-2)-1)
    else:
        print(sum-2)
```

