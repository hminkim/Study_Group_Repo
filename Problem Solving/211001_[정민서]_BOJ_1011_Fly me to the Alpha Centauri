---
UpLoader: 정민서
Date: 21.10.01
Rank: Silver.5
Language: c
tags: 
---

# 백준 1011 Fly me to the Alpha Centauri

[백준 4673 - Fly me to the Alpha Centauri](https://www.acmicpc.net/problem/1011)  
  

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
