# [9663 N-Queen](https://www.acmicpc.net/problem/9663)

### 🥇 4

### 분류

- 브루트포스 알고리즘
- 백트래킹

### 풀이 날짜

- 230324 금

---

## CODE

```python
import sys

input = sys.stdin.readline
sys.setrecursionlimit(10 ** 6)


def set_queen(row):
    global N, ans, is_col, is_right, is_left
    if row == N:
        ans += 1
        return
    for col in range(N):
        if not (is_col[col] or is_right[row + col] or is_left[row - col + N]):
            is_col[col] = is_right[row + col] = is_left[row - col + N] = True
            set_queen(row + 1)
            is_col[col] = is_right[row + col] = is_left[row - col + N] = False
    return


N = int(input())

is_col = [False] * 15
is_right = [False] * 40
is_left = [False] * 40

ans = 0
set_queen(0)
print(ans)

```

## 해설

시간 초과에 막히다가 겨우 통과했다.

PyPy3로는 계속 메모리 초과가 나왔다.

함수 호출도 줄여서 시간 초과를 뚫었다.

`31256KB`, `21556ms`
