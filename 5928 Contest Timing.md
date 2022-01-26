# 5928 Contest Timing



```python
d, h, m = map(int, input().split())
start_time = 11*24*60 + 11*60 + 11
end_time = d*24*60 + h*60 + m
answer = end_time - start_time
if answer < 0:
    answer = -1
print(answer)
```

