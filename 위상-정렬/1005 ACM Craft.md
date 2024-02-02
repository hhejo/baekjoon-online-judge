# [1005 ACM Craft](https://www.acmicpc.net/problem/1005)

### 🥇 3

### 분류

- 다이나믹 프로그래밍
- 그래프 이론
- 위상 정렬

### 풀이 날짜

- 230405 수

---

## CODE 1

```python
import sys
from collections import deque

input = sys.stdin.readline

#


def topology_sort():
    global g, d, ind, W
    que = deque()
    dp = [0] * (N + 1)
    for i in range(1, N + 1):
        if ind[i] == 0:
            que.append(i)
            dp[i] = d[i]
    while que:
        cur = que.popleft()
        for nxt in g[cur]:
            dp[nxt] = max(dp[nxt], dp[cur] + d[nxt])
            ind[nxt] -= 1
            if ind[nxt] == 0:
                que.append(nxt)
    return dp[W]


for test_case in range(int(input())):
    N, K = map(int, input().split())
    g = [[] for _ in range(N + 1)]
    d = [0] + list(map(int, input().split()))
    ind = [0] * (N + 1)
    for _ in range(K):
        X, Y = map(int, input().split())
        g[X].append(Y)
        ind[Y] += 1
    W = int(input())
    ans = topology_sort()
    print(ans)

```

## 해설 1

`d[i]` : i 건물만 짓는데 필요한 시간

`dp[i]` : i 건물을 짓는데 필요한 전체 최소 시간 (다른 필요 건물까지 다 지은 시간 필요)

`34544KB`, `1148ms`

