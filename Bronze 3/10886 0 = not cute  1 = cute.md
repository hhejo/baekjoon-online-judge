# 10886 0 = not cute / 1 = cute



## 1.

```python
n = int(input())
cnt_0 = cnt_1 = 0
for _ in range(n):
    x = int(input())
    if x == 0:
        cnt_0 += 1
    else:
        cnt_1 += 1
if cnt_0 > cnt_1:
    print('Junhee is not cute!')
else:
    print('Junhee is cute!')
```



## 2.

```python
n = int(input())
survey = [int(input()) for _ in range(n)]
if survey.count(0) > survey.count(1):
    print('Junhee is not cute!')
else:
    print('Junhee is cute!')
```

