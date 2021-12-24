# Python–从另一个文件调用函数

> 原文:[https://www . geesforgeks . org/python-从另一个文件调用函数/](https://www.geeksforgeeks.org/python-call-function-from-another-file/)

给定一个 Python 文件，我们需要调用任何其他 Python 文件中定义的函数。
**例:**

> 假设有一个文件 test.py，其中包含函数 displayText()的定义。
> # test . py>
> def display text():
> print(“极客 4 极客！”)
> 我们需要在任何其他 Python 文件中调用函数 displayText()，这样无论我们在哪里调用 displayText()函数，都会显示其中存在的文本。这可以使用 Python 模块来完成。

**进场:**

1.  创建一个包含所需函数的 Python 文件。
2.  创建另一个 Python 文件，并将之前的 Python 文件导入其中。
3.  调用导入文件中定义的函数。

上面的方法已经在下面的示例中使用过:
**示例 1:** 创建了一个 Python 文件 test.py，它包含 displayText()函数。

## 蟒蛇 3

```py
# test.py>

# function
def displayText():
    print( "Geeks 4 Geeks !")
```

现在创建了另一个 Python 文件，它调用在 test.py.
中定义的 displayText()函数

## 蟒蛇 3

```py
# importing  all the
# functions defined in test.py
from test import *

# calling functions
displayText()
```

**输出:**

```py
Geeks 4 Geeks!
```

在上面的程序中，test.py 文件中定义的所有函数都被导入，然后调用一个函数。
**示例 2:** 创建了一个 Python 文件 calc.py，其中包含 addNumbers()、subractNumbers()、multiplyNumbers()、divideNumbers()和 modulusNumbers()。

## 蟒蛇 3

```py
# calc.py>

# functions
def addNumbers(a, b):
    print("Sum is ", a + b)

def subtractNumbers(a, b):
    print("Difference is ", a-b)

def multiplyNumbers(a, b):
    print("Product is ", a * b)

def divideNumbers(a, b):
    print("Division is ", a / b)

def modulusNumbers(a, b):
    print("Remainder is ", a % b)
```

calc.py 中定义的函数在另一个 Python 文件中调用。

## 蟒蛇 3

```py
# importing limited functions
# defined in calc.py
from calc import addNumbers, multiplyNumbers

# calling functions
addNumbers(2, 5)
multiplyNumbers(5, 4)
```

**输出:**

```py
7
20
```

在上面的程序中，calc.py 中定义的所有函数都没有导入。
导入 Python 文件中定义的所有函数:
**语法:**

```py
from file import *
```

仅导入 Python 文件中定义的必需函数:
**语法:**

```py
from file import func1, func2, func3
```

**示例 3:**
下面的 Python 文件 test.py 和 calc.py 是用不同的函数定义创建的。

## 蟒蛇 3

```py
# test.py>

# function defined in test.py
def displayText():
    print("\nGeeks 4 Geeks !")
```

## 蟒蛇 3

```py
# calc.py>

# functions defined in calc.py
def addNumbers(a, b):
    print("Sum is ", a + b)

def subtractNumbers(a, b):
    print("Difference is ", a-b)

def multiplyNumbers(a, b):
    print("Product is ", a * b)

def divideNumbers(a, b):
    print("Division is ", a / b)

def modulusNumbers(a, b):
    print("Remainder is ", a % b)
```

这两个文件都被导入到另一个名为 file.py.
的 Python 文件中

## 蟒蛇 3

```py
# file.py>

# importing all the functions
# defined in calc.py
from calc import *

# importing required functions
# defined in test.py
from test import displayText

# calling functions defined
# in calc.py
addNumbers(25, 6)
subtractNumbers(25, 6)
multiplyNumbers(25, 6)
divideNumbers(25, 6)
modulusNumbers(25, 6)

# calling function defined
# in test.py
displayText()
```

**输出:**

```py
Sum is  31
Difference is  19
Product is  150
Division is  4.166666666666667
Remainder is  1

Geeks 4 Geeks!
```

在上面的程序中，在 test.py 和 calc.py 中定义的函数在不同的文件中调用，该文件是 file . py