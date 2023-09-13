# [20044 Project Teams](https://www.acmicpc.net/problem/20044)

### 🥈 4

### 분류

- 그리디 알고리즘
- 정렬

### 풀이 날짜

- 230913 수

---

## CODE 1

```python
import sys

input = sys.stdin.readline

n = int(input())
a = list(map(int, input().split()))
a.sort()

ans = 200_000
for i in range(n):
    ans = min(ans, a[i] + a[(2 * n - 1) - i])

print(ans)
```

## 해설 1

`32276KB`, `48ms`
