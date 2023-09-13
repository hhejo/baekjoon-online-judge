# [12018 Yonsei TOTO](https://www.acmicpc.net/problem/12018)

### 🥈 3

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

n, m = map(int, input().split())

arr = []
for _ in range(n):
    p, l = map(int, input().split())
    a = list(map(int, input().split()))
    a.sort(reverse=True)
    if p < l:
        arr.append(1)
    else:
        arr.append(a[l - 1])
arr.sort()

milage, ans = m, 0
for i in range(n):
    milage -= arr[i]
    if milage < 0:
        break
    ans += 1

print(ans)
```

## 해설 1

`31256KB`, `40ms`
