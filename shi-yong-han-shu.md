# 使用函數

### 函數可以通過關鍵字 `def` 來定義。

```
def 函式名稱 (變數名稱):
    函示區塊
```

`def` 關鍵字是用來定義 (define) 函式。

可以自訂一個函式的名稱。

可加入會使用到的變數名稱。

它的結尾必須加上一個冒號，使 Python 知道編譯器底下向右縮排的程式碼區塊都屬於這個函式。

下面的函式區塊可以打上要執行什麼程式，當呼叫這個函式時，就會執行這個區塊。



讓我們看個例子：

```
import datetime

def printDate ():
    dt = datetime.datetime.now()
    print(f'今天日期: {dt.year}/{dt.month}/{dt.day}')
    print(f'現在時間: {dt.hour}:{dt.minute}:{dt.second}')

printDate()
```

`import datetime` 模組。

這個程式沒有回傳值。

輸出結果如下：

```
今天日期: 2021/11/23
現在時間: 11:22:25
```

####

#### 函式需先定義後才能呼叫使用

一般會把函式定義在程式的開頭，在import模組與主程式之間。



#### 函式如果設有變數或參數，需要有值才能運算

```
def igrade (grade1, grade2):
    avg = (grade1 + grade2)/2
    print(avg)

igrade()
```

未給值，grade1, grade2沒有值無法運算。



```
def igrade (grade1, grade2):
    avg = (grade1 + grade2)/2
    print(avg)

igrade(50, 72)
```

可以直接在呼叫函式時給值。



```
def igrade (grade1 = 50, grade2 = 72):
    avg = (grade1 + grade2)/2
    print(avg)

igrade()
```

也可以在函式中先給定初始值。



```
def igrade (grade1, grade2):
    avg = (grade1 + grade2)/2
    print(avg)

grade1 = int(input('輸入成績1: '))
grade2 = int(input('輸入成績2: '))
igrade(grade1, grade2)
```

也可以讓使用者自行輸入值，再帶入函式中進行運算。



我們來試試看這個例子：

```
def igrade (grade1 = 50, grade2 = 70):
    avg = (grade1 + grade2) / 2
    print('成績平均: ', avg)

grade1 = int(input('輸入成績1: '))
grade2 = int(input('輸入成績2: '))
igrade()
```

輸出結果如下：

```
輸入成績1: 20
輸入成績2: 30
成績平均:  60.0
```

_為什麼會這樣？_



我們再試試看這個例子：

```
def igrade (grade1 = 50, grade2 = 70):
    avg = (grade1 + grade2) / 2
    print('成績平均: ', avg)

grade1 = int(input('輸入成績1: '))
grade2 = int(input('輸入成績2: '))
igrade(grade1, grade2)
```

輸出結果如下：

```
輸入成績1: 20
輸入成績2: 30
成績平均:  25.0
```

_為什麼會這樣？_



我們增加成績的比重：

```
def igrade (grade1, grade2):
    avg = (grade1*2 + grade2*1) / 3
    print('成績平均: ', avg)

grade1 = int(input('輸入成績1: '))
grade2 = int(input('輸入成績2: '))
igrade(grade1, grade2)
```

輸出結果如下：

```
輸入成績1: 20
輸入成績2: 30
成績平均:  23.333333333333332
```



如果取名的變數名稱和函式相同，則無關順序：

```
def igrade (grade1, grade2):
    avg = (grade1*2 + grade2*1) / 3
    print('成績平均: ', avg)

grade1 = int(input('輸入成績1: '))
grade2 = int(input('輸入成績2: '))
igrade(grade2, grade1)
```

輸出結果如下：

```
輸入成績1: 20
輸入成績2: 30
成績平均:  26.666666666666668
```



呼叫函式值時，變數名稱一定要跟函式中的參數名稱相同嗎？

```
def igrade (grade1, grade2):
    avg = (grade1*2 + grade2*1) / 3
    print('成績平均: ', avg)

A = int(input('輸入成績1: '))
B = int(input('輸入成績2: '))
igrade(A, B)
```

輸出結果如下：

```
輸入成績1: 20
輸入成績2: 30
成績平均:  23.333333333333332
```



試著交換一下：

```
def igrade (grade1, grade2):
    avg = (grade1 * 2 + grade2 * 1) / 3
    print('成績平均: ', avg)

A = int(input('輸入成績1: '))
B = int(input('輸入成績2: '))
igrade(B, A)
```

輸出結果如下：

```
輸入成績1: 20
輸入成績2: 30
成績平均:  26.666666666666668
```

B→grade1

A→grade2



試著交換一下：

```
def igrade (grade2, grade1):
    avg = (grade1 * 2 + grade2 * 1) / 3
    print('成績平均: ', avg)

A = int(input('輸入成績1: '))
B = int(input('輸入成績2: '))
igrade(A, B)
```

輸出結果如下：

```
輸入成績1: 20
輸入成績2: 30
成績平均:  26.666666666666668
```

A→grade2

B→grade1



試著交換一下：

```
def igrade (grade2, grade1):
    avg = (grade1 * 2 + grade2 * 1) / 3
    print('成績平均: ', avg)

A = int(input('輸入成績1: '))
B = int(input('輸入成績2: '))
igrade(B, A)
```

輸出結果如下：

```
輸入成績1: 20
輸入成績2: 30
成績平均:  23.333333333333332
```

B→grade2

A→grade1



課堂上講到可能錯誤的情況：參數為字串與數字

```
def igrade (name, grade):
    print(name, '的成績為:', grade)

A = str(input('輸入姓名: '))
B = int(input('輸入成績: '))
igrade(A, B)
```

輸出結果如下：

```
輸入姓名: Jack
輸入成績: 30
Jack 的成績為: 30
```

```
輸入姓名: 30
輸入成績: Jack
Traceback (most recent call last):
  File "c:\Python.py", line 5, in <module>
    B = int(input('輸入成績: '))
ValueError: invalid literal for int() with base 10: 'Jack'
```
