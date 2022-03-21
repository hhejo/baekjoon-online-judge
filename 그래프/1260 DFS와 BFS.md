# 1260 DFS와 BFS



```python
from collections import deque


def dfs():
    global N, V, graph
    for li in graph:
        li.sort(reverse=True)
    visited = [False] * (N + 1)
    stk = [V]
    ans = []
    while stk:
        now = stk.pop()
        if not visited[now]:
            ans.append(now)
        visited[now] = True
        for node in graph[now]:
            if not visited[node]:
                stk.append(node)
    return ans


def bfs():
    global N, V, graph
    for li in graph:
        li.sort()
    visited = [False] * (N + 1)
    que = deque()
    que.append(V)
    ans = []
    while que:
        now = que.popleft()
        if not visited[now]:
            ans.append(now)
        visited[now] = True
        for node in graph[now]:
            if not visited[node]:
                que.append(node)
    return ans


N, M, V = map(int, input().split())
edges = [tuple(map(int, input().split())) for _ in range(M)]
graph = [[] for _ in range(N + 1)]
for s, e in edges:
    graph[s].append(e)
    graph[e].append(s)
print(*dfs())
print(*bfs())
```
