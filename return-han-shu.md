# Return 函數

### **我們可以決定**函數要不要傳回值至主程式中。

```
def igrade (grade1, grade2):
    avg = (grade1 + grade2) / 2
    print('成績平均: ', avg)

grade1 = int(input('輸入成績1: '))
grade2 = int(input('輸入成績2: '))
igrade(grade1, grade2)
print(avg)
```

輸出結果如下：

```
輸入成績1: 30
輸入成績2: 25
成績平均:  27.5
Traceback (most recent call last):
  File "c:\Python.py", line 8, in <module>
    print(avg)
NameError: name 'avg' is not defined
```

因為沒有傳回值至主程式中，函式中的變數`avg`與主程式不相干，主程式也沒有`avg`的值。



我們試著傳回值至主程式中：

```
def igrade (grade1, grade2):
    return (grade1 + grade2) / 2

grade1 = int(input('輸入成績1: '))
grade2 = int(input('輸入成績2: '))
avg = igrade(grade1, grade2)
print('成績平均: ', avg)
```

輸出結果如下：

```
輸入成績1: 20
輸入成績2: 30
成績平均:  25.0
```



如果想傳回更多值：

```
def igrade (grade1, grade2):
    return (grade1 + grade2) / 2, (grade1 * 2 + grade2 * 1) / 3

grade1 = int(input('輸入成績1: '))
grade2 = int(input('輸入成績2: '))
avg, pr = igrade(grade1, grade2)
print('成績平均: ', avg)
print('比重成績: ', pr)
```

輸出結果如下：

```
輸入成績1: 20
輸入成績2: 30
成績平均:  25.0
比重成績:  23.333333333333332
```



使用判斷式傳回不同的return值：

```
def igrade (grade1, grade2):
    if grade1 < 1 or grade2 < 0:
        return 0
    else:
        return (grade1 + grade2) / 2, (grade1 * 2 + grade2 * 1) / 3

grade1 = int(input('輸入成績1: '))
grade2 = int(input('輸入成績2: '))
avg, pr = igrade(grade1, grade2)
print('成績平均: ', avg)
print('比重成績: ', pr)
```

輸出結果如下：

```
輸入成績1: 20
輸入成績2: 30
成績平均:  25.0
比重成績:  23.333333333333332
```

輸出結果如下：

```
輸入成績1: 20
輸入成績2: -1
Traceback (most recent call last):
  File "c:\Python.py", line 9, in <module>
    avg, pr = igrade(grade1, grade2)
TypeError: cannot unpack non-iterable int object
```
