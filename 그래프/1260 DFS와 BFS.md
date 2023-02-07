# 1260 DFS와 BFS

---

### CODE

```python
import sys
from collections import deque


def dfs():
    global N, V, graph
    for li in graph:
        li.sort(reverse=True)
    visited = [False] * (N + 1)
    stk = [V]
    ans = []
    while stk:
        cur = stk.pop()
        if not visited[cur]:
            ans.append(cur)
        visited[cur] = True
        for node in graph[cur]:
            if not visited[node]:
                stk.append(node)
    return ans


def bfs():
    global N, V, graph
    for li in graph:
        li.sort()
    visited = [False] * (N + 1)
    que = deque([V])
    ans = []
    while que:
        cur = que.popleft()
        if not visited[cur]:
            ans.append(cur)
        visited[cur] = True
        for node in graph[cur]:
            if not visited[node]:
                que.append(node)
    return ans


sys.stdin = open('input.txt')

N, M, V = map(int, sys.stdin.readline().split())
edges = [tuple(map(int, sys.stdin.readline().split())) for _ in range(M)]
graph = [[] for _ in range(N + 1)]
for s, e in edges:
    graph[s].append(e)
    graph[e].append(s)
print(*dfs())
print(*bfs())

```

### 해설
