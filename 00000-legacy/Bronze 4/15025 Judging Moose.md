# 15025 Judging Moose



### 접근 방법



### CODE

```python
L, R = map(int, input().split())
if 0 == L == R:
    print("Not a moose")
elif L != R:
    print(f"Odd {max(L, R) * 2}")
elif L == R:
    print(f"Even {R * 2}")
```



### 해설

