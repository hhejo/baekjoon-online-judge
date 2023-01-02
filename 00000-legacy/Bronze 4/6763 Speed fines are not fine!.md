# 6763 Speed fines are not fine!



### 접근 방법



### CODE

```python
limit = int(input())
speed = int(input())
d = speed - limit
if d <= 0:
    print("Congratulations, you are within the speed limit!")
elif 1 <= d <= 20:
    print('You are speeding and your fine is $100.')
elif 21 <= d <= 30:
    print('You are speeding and your fine is $270.')
else:
    print('You are speeding and your fine is $500.')
```

