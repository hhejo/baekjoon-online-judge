# 6764 Sounds fishy!



## 1.

```python
depth = [int(input()) for _ in range(4)]
answer = ''
if depth[0] < depth[1] < depth[2] < depth[3]:
    answer = 'Fish Rising'
elif depth[0] > depth[1] > depth[2] > depth[3]:
    answer = 'Fish Diving'
elif depth[0] == depth[1] == depth[2] == depth[3]:
    answer = 'Fish At Constant Depth'
else:
    answer = 'No Fish'
print(answer)
```



## 2.

```python
a, b, c, d = [int(input()) for _ in range(4)]
answer = 'No Fish'
if a < b < c < d:
    answer = 'Fish Rising'
elif a > b > c > d:
    answer = 'Fish Diving'
elif a == b == c == d:
    answer = 'Fish At Constant Depth'
print(answer)
```

