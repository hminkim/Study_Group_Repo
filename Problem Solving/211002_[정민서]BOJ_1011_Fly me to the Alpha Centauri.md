---
UpLoader: 정민서
Date: 21.10.02
Rank: Silver.5
Language: c
tags: 
---

# 백준 1011 Fly me to the Alpha Centauri

[백준 1011 - Fly me to the Alpha Centauri](https://www.acmicpc.net/problem/1011)  
 
 
### 풀이 과정
처음에는 [거리당 횟수들] 간의 규칙을 찾아서 코드를 짜보려고 했지만 제곱근까지 생각해내다가 실패함. 

이동거리(move)가 1, 2, 3, , ,  n, , , 3, 2, 1 규칙을 가지는 것을 알게 됨.
증가하다가 감소하는 중간지점이 n.
양 끝에서 이동거리가 같게 1 증가, 감소하므로 한번에 계산하기 위해 이동거리가 하나 증가하면 횟수(count)는 두번 증가. 
남은 거리는 거리 - 이동거리 *2.

더이상 좌우대칭으로 이동거리가 나올 수 없는 중간지점쯤 오면
이동거리가 남은거리보다 크거나 같을 경우, 횟수 +1
이동거리가 남은거리보다 작은 경우, 횟수 +2 

### 소스 코드

```c
#include <stdio.h>

int main()
{
    int t;
    scanf("%d", &t);
    
    for(int i=0; i<t; i++)
    {
        int x;
        int y;
        scanf("%d %d", &x, &y);
        int distance = y-x;
        int move = 1;
        int count = 0;
        
        while(distance/2 >= move)
        {
            distance = distance - move*2;
            count += 2; 
            move++; 
        }
        
        if(1<=distance && distance <= move)
        {
            count++;
        }
        else if(distance > move)
        {
            count += 2;
        }
        
        printf("%d\n", count);
    }
    return 0;
}
```
