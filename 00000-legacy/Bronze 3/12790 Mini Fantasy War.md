# 12790 Mini Fantasy War



```python
import sys

input = sys.stdin.readline

for T in range(int(input())):
    li = list(map(int, input().split()))
    hp = li[0] + li[4] if li[0] + li[4] > 1 else 1
    mp = li[1] + li[5] if li[1] + li[5] > 1 else 1
    at = li[2] + li[6] if li[2] + li[6] > 0 else 0
    df = li[3] + li[7]
    print(hp + 5*mp + 2*at + 2*df)
```

