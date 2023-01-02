# 3613 Java vs C++



### 접근 방법

Java인 경우, C++인 경우로 나눠 진행한다.

Java인 경우에 밑줄이 있거나, 맨 처음이 대문자이면 에러이다.

C++인 경우에 대문자가 있거나, 맨 처음이 밑줄이거나, 밑줄이 연속이거나, 맨 마지막이 밑줄인 경우 에러이다.



### CODE

```python
name = input()
converted = ''
java = True
cpp = False

# Java
prev = ''
for now in name:
    if '_' == now:
        java = False
        cpp = True
        break
    elif now.islower():
        converted += now
    elif now.isupper():
        if '' == prev:
            java = False
            cpp = True
            break
        elif prev.islower() or prev.isupper():
            converted += '_' + now.lower()
    prev = now

# C++
if cpp:
    converted = ''
    prev = ''
    for idx, now in enumerate(name):
        if now.isupper():
            cpp = False
            break
        elif now.islower():
            if '' == prev or prev.islower():
                converted += now
            elif '_' == prev:
                converted += now.upper()
        elif '_' == now:
            if '' == prev or '_' == prev:
                cpp = False
                break
            if idx == len(name) - 1:
                cpp = False
                break
        prev = now

if java or cpp:
    print(converted)
else:
    print('Error!')
```

