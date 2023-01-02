# 10570 Favorite Number



```python
import sys

input = sys.stdin.readline

N = int(input())
for _ in range(N):
    li = [0] * 1001
    V = int(input())
    for _ in range(V):
        li[int(input())] += 1
    print(li.index(max(li)))
```

