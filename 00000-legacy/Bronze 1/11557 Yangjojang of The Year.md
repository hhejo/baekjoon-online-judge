# 11557 Yangjojang of The Year



```python
for T in range(int(input())):
    N = int(input())
    li = []
    for _ in range(N):
        S, L = input().split()
        li.append((S, int(L)))
    print(sorted(li, key=lambda x: -x[1])[0][0])
```


