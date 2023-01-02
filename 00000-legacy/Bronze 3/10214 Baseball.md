# 10214 Baseball



```python
for T in range(int(input())):
    y = k = 0
    for _ in range(9):
        Y, K = map(int, input().split())
        y += Y
        k += K
    if y > k:
        print('Yonsei')
    elif k > y:
        print('Korea')
    else:
        print('Draw')
```

