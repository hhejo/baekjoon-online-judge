# 15059 Hard choice



### 접근 방법



### CODE

```python
Ca, Ba, Pa = map(int, input().split())
Cr, Br, Pr = map(int, input().split())
ans = max(0, Cr - Ca) + max(0, Br - Ba) + max(0, Pr - Pa)
print(ans)
```



### 해설

