# 區域變數與全域變數

### 如果說主程式是一個地區，那函數可以說是另一個地區。

```
rate = 2

def igrade (grade, rate):
    print('成績變更:', grade * rate)

grade = int(input('輸入成績: '))

igrade(grade, rate)
```

輸出結果如下：

```
輸入成績: 30
成績變更: 60
```



如果在函式裡面也加上自己的`rate`呢？

```
rate = 2

def igrade (grade):
    rate = 1.5
    print('成績變更:', grade * rate)

grade = int(input('輸入成績: '))

igrade(grade)
```

輸出結果如下：

```
輸入成績: 30
成績變更: 45.0
```



如果使用`return`呢？

主程式跟函式算出來的結果會有差嗎？

```
rate = 2

def igrade (grade):
    rate = 1.5
    print('函式中 - 成績變更:', grade * rate)

grade = int(input('輸入成績: '))

igrade(grade)

print('主程式中 - 成績變更:', grade * rate)
```

輸出結果如下：

```
輸入成績: 30
函式中 - 成績變更: 45.0
主程式中 - 成績變更: 60
```



在函數中加入`global`，讓函式中的變數與主程式的全域變數連通：

```
rate = 1.5

def igrade (grade):
    global rate
    rate = 2
    print('函式中 - 成績變更:', grade * rate)

grade = int(input('輸入成績: '))

print('主程式函式執行前 - 成績變更:', grade * rate)

igrade(grade)

print('主程式中函式執行後 - 成績變更:', grade * rate)
```

輸出結果如下：

```
輸入成績: 30
主程式函式執行前 - 成績變更: 45.0
函式中 - 成績變更: 60
主程式中函式執行後 - 成績變更: 60
```



global 語句用來聲明 變數 `rate` 是一個全域變數。

當我們在函數中給 變數`rate`另一個值時，同時也會變更到主程式中的 變數`rate` 的值。

&#x20;

你可以在同一句 global 語句中指派不止一個的全域變數。

例如：

```
global name, grade, rate
```



**補充>> 與其他程式語言不同的地方**

在 Python 中，沒有所謂 **常數 Const** 的概念，所以變數值都是處在一個可被變更的狀態。
