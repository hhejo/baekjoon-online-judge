# 17009 Winning Score



```python
apples = [int(input()) for _ in range(3)][::-1]
bananas = [int(input()) for _ in range(3)][::-1]
apple_score = banana_score = 0
for i, score in enumerate(apples):
    apple_score += score * (i+1)
for i, score in enumerate(bananas):
    banana_score += score * (i+1)
if apple_score > banana_score:
    print('A')
elif apple_score == banana_score:
    print('T')
else:
    print('B')
```

