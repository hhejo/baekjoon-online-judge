# 6764 Sounds fishy!



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

