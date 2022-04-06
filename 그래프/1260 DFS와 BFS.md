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



### 접근방법

DFS는 재귀, BFS는 큐로 구현했다.

### CODE

```python
import sys
from collections import deque

input = sys.stdin.readline


def search(sv, graph, method):
    def dfs(cv):
        for w in range(len(graph[cv])):
            if 1 == graph[cv][w] and w not in visited:
                visited.append(w)
                dfs(w)

    def bfs(vv):
        q = deque([vv])
        while q:
            cv = q.popleft()
            for w in range(len(graph[cv])):
                if 1 == graph[cv][w] and w not in visited:
                    visited.append(w)
                    q.append(w)

    visited = [sv]
    if 'DFS' == method:
        dfs(sv)
    else:
        bfs(sv)
    print(*visited)


N, M, V = map(int, input().split())
GRAPH = [[0] * (N + 1) for _ in range(N + 1)]
for _ in range(M):
    V1, V2 = map(int, input().split())
    GRAPH[V1][V2] = 1
    GRAPH[V2][V1] = 1
search(V, GRAPH, 'DFS')
search(V, GRAPH, 'BFS')
```

### 해설

탐색 함수를 하나 만든 후, 입력 값에 따라 DFS나 BFS를 수행했다.

`38284KB`, `464ms`

