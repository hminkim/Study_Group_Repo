---
UpLoader: 김도균
Date: 21.12.22
Rank: Silver.2
Language: Python
tags: 구현
---

# 백준 2290 LCD Test

[백준 2290 - LCD Test](https://www.acmicpc.net/problem/2290)  
  

### 풀이 과정  

- 7-segment 형식에 맞춰서 숫자에 따라 On/Off를 표시한다.
- 가로 줄 그리기, 세로 줄 그리기 함수를 구현한다.


### 소스 코드

```py
# https://www.acmicpc.net/problem/2290

s, n = map(int, input().split())

segment = [[False] * 7 for _ in range(len(str(n)))]


def set_num():
    global segment
    for idx, i in enumerate(str(n)):
        if i == '0':
            segment[idx][0] = True
            segment[idx][1] = True
            segment[idx][2] = True
            segment[idx][3] = True
            segment[idx][4] = True
            segment[idx][5] = True
        elif i == '1':
            segment[idx][1] = True
            segment[idx][2] = True
        elif i == '2':
            segment[idx][0] = True
            segment[idx][1] = True
            segment[idx][3] = True
            segment[idx][4] = True
            segment[idx][6] = True
        elif i == '3':
            segment[idx][0] = True
            segment[idx][1] = True
            segment[idx][2] = True
            segment[idx][3] = True
            segment[idx][6] = True
        elif i == '4':
            segment[idx][1] = True
            segment[idx][2] = True
            segment[idx][5] = True
            segment[idx][6] = True
        elif i == '5':
            segment[idx][0] = True
            segment[idx][2] = True
            segment[idx][3] = True
            segment[idx][5] = True
            segment[idx][6] = True
        elif i == '6':
            segment[idx][0] = True
            segment[idx][2] = True
            segment[idx][3] = True
            segment[idx][4] = True
            segment[idx][5] = True
            segment[idx][6] = True
        elif i == '7':
            segment[idx][0] = True
            segment[idx][1] = True
            segment[idx][2] = True
        elif i == '8':
            segment[idx][0] = True
            segment[idx][1] = True
            segment[idx][2] = True
            segment[idx][3] = True
            segment[idx][4] = True
            segment[idx][5] = True
            segment[idx][6] = True
        elif i == '9':
            segment[idx][0] = True
            segment[idx][1] = True
            segment[idx][2] = True
            segment[idx][3] = True
            segment[idx][5] = True
            segment[idx][6] = True


def draw_horizon_line(n):
    for num in segment:
        line1 = num[n]
        print(' ', end='')
        if line1:
            print("-" * s, end='')
        else:
            print(" " * s, end='')
        print('  ', end='')
    print()


def draw_vertical_line(a, b):
    for _ in range(s):
        for num in segment:
            line1 = num[a]
            line2 = num[b]
            if line2:
                print('|', end='')
            else:
                print(' ', end='')
            print(' ' * s, end='')
            if line1:
                print('|', end='')
            else:
                print(' ', end='')
            print(' ', end='')
        print()

set_num()

draw_horizon_line(0)
draw_vertical_line(1, 5)
draw_horizon_line(6)
draw_vertical_line(2, 4)
draw_horizon_line(3)
```