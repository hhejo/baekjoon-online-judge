# 13136 Do Not Touch Anything



```python
r, c, n = map(int, input().split())
row = c // n + (1 if c % n else 0)  # 행에서 cctv 범위에 벗어나면 cctv 하나 추가
col = r // n + (1 if r % n else 0)  # 열에서 cctv 범위에 벗어나면 cctv 하나 추가
cnt = row * col
print(cnt)
```

