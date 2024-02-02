# [17626 Four Squares](https://www.acmicpc.net/problem/17626)

### 🥈 3

### 분류

- 다이나믹 프로그래밍
- 브루트포스 알고리즘

### 풀이 날짜

- 230327 월

---

## CODE

```python
import sys

input = sys.stdin.readline

N = int(input())

dp = [50001] * (N + 1)
dp[0] = 0

for i in range(1, N + 1):
    for j in range(1, int(i ** 0.5) + 1):
        dp[i] = min(dp[i], dp[i - j * j] + 1)

print(dp[N])

```

## 해설

`115368KB`, `144ms`
