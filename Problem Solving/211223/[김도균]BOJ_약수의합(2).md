---
UpLoader: 김도균
Date: 21.12.22
Rank: Silver.2
Language: Python
tags: 수학
---

# 백준 17427 약수의 합 (2)

[백준 17427 - 약수의 합 (2)](https://www.acmicpc.net/problem/17427)  
  

### 풀이 과정  

- 범위가 1,000,000이고 시간제한 1초(파이썬)이므로 `O(N)` 복잡도로 풀어야한다.
- 약수의 원리는 어떤 숫자 A의 배수들은 A를 반드시 약수로 가지게 된다.
- N 이하의 숫자라면 1을 약수로 가지는 수는 N개, 2를 약수로 가지는 수는 `N // 2`개, 3을 약수로 가지는 수는 `N // 3`개이다.
- 이를 일반화해보면 숫자 i를 약수로 가지는 N 이하의 숫자의 합은 `(N // i) * i`가 된다. 

### 소스 코드

```py
# https://www.acmicpc.net/problem/17427

N = int(input())

answer = 0
for i in range(1, N + 1):
    answer += (N // i) * i

print(answer)
```