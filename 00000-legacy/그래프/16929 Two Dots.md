# 16929 Two Dots



### 접근방법

사이클을 DFS로 찾는다. 사이클은 적어도 네 점으로 이루어져야 하기 때문에, 현재 DFS 진행중인 점의 깊이 단계를 따로 저장했다.

그리고 탐색을 진행하려면 진행중인 모든 점은 색깔이 같아야 하기 때문에 이전 점의 정보를 따로 저장했다.

또, 사이클이 만들어지려면 맨 처음 출발했던 점의 좌표도 알아야 하기 때문에 따로 저장했다.

### CODE

```python
def is_cycle(graph):
    def dfs(cx, cy, frm, prev_clr, dpt):
        if cx < 0 or cx >= len(graph) or cy < 0 or cy >= len(graph[0]) or prev_clr != graph[cx][cy]:
            return False
        if visited[cx][cy]:
            if cx == frm[0] and cy == frm[1] and dpt > 3:
                return True
            return False
        visited[cx][cy] = True
        res = False
        for dx, dy in ((-1, 0), (0, 1), (1, 0), (0, -1)):
            nx, ny = cx + dx, cy + dy
            res = res or dfs(nx, ny, frm, graph[cx][cy], dpt + 1)
        return res

    for sx in range(len(graph)):
        for sy in range(len(graph[0])):
            visited = [[False] * len(graph[0]) for _ in range(len(graph))]
            if dfs(sx, sy, (sx, sy), graph[sx][sy], 0):
                return 'Yes'
    return 'No'


N, M = map(int, input().split())
GRAPH = [list(input()) for _ in range(N)]
ans = is_cycle(GRAPH)
print(ans)
```

### 해설

모든 점에 대해 DFS를 한 번씩 수행한다.

DFS의 결과가 `True`이면 바로 정답을 출력할 수 있게 리턴한다.

`dfs()`함수에서는 현재 점의 좌표, 출발점의 좌표, 이전 점의 색깔, 현재 깊이 단계를 매개변수로 받는다.

현재 좌표가 범위를 벗어나거나 현재 색깔이 이전 색깔과 다르면 바로 `False`를 리턴하고 종료한다.

만약 방문한 점이면, 깊이 단계가 4 이상인지 확인한다. 방문한 점인데 깊이 단계가 4 이상이면 출발점으로 돌아온 것이므로 `True`를 리턴한다.

해당하지 않으면 `False`를 리턴한다.

현재 점을 방문 처리하고 네 방향에 대해 DFS를 진행한다.

네 방향에 대해 하나라도 `True`를 받으면 결과로 `True`를 리턴할 수 있게 `or`연산을 활용했다.



`30892KB`, `112ms`

