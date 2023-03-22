# [15881 Pen Pineapple Apple Pen](https://www.acmicpc.net/problem/15881)

### 🥉 1

### 분류

- 문자열
- 그리디 알고리즘

### 풀이 날짜

- 230305 일

---

## CODE

```python
import sys

input = sys.stdin.readline


# 입력
N = int(input())  # 물건의 총 개수
S = input().strip()  # 물체의 목록


# 풀이
def solve():
    global N, S

    i = cnt = 0  # 인덱스, pPAp의 개수
    # i가 N - 4까지
    while i < (N - 3):
        # pPAp가 아니면 인덱스 1 증가
        if S[i:i+4] != 'pPAp':
            i += 1
            continue
        # pPAp이면 개수 1 증가, 인덱스 4 증가
        cnt += 1
        i += 4

    # 정답 출력
    print(cnt)
    return


# 풀이
solve()

```

## 해설
