# [17521 Byte Coin](https://www.acmicpc.net/problem/17521)

### 🥈 4

### 분류

- 그리디 알고리즘

### 풀이 날짜

- 230914 목

---

## CODE 1

```python
import sys

input = sys.stdin.readline

n, w = map(int, input().split())
a = [int(input()) for _ in range(n)]

amount, count = w, 0
for i in range(n - 1):
    if a[i] < a[i + 1]:
        if amount // a[i] > 0:
            count = amount // a[i]
            amount = amount % a[i]
    elif a[i] > a[i - 1]:
        amount += a[i] * count
        count = 0

ans = amount
if count > 0:
    ans += count * a[-1]

print(ans)
```

## 해설 1

`31256KB`, `44ms`
