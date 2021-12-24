# Python 中的多种方法

> 原文:[https://www.geeksforgeeks.org/multimethods-in-python/](https://www.geeksforgeeks.org/multimethods-in-python/)

**Multimethod** 基本上是指具有多个版本的函数，通过参数的类型来区分。为了更好地理解，考虑下面的例子。

```
@multimethod
def sum(x: int, y: int):
    return x + y

@multimethod
def sum(x: str, y: str):
    return x+" "+y

The above example is similar to

def sum(x, y):

    if isinstance(x, int) and isinstance(y, int):
        return x + y

    elif isinstance(x, str) and isinstance(y, str):
        return x + ' ' + y

```

### 装置

在语法层面，Python 不支持多次调度，但是可以使用库扩展`multimethod`添加多次调度。要安装此库，请在终端中键入以下命令。

```
pip install multimethod
```

**例 1:**

```
# Python program to demonstrate
# multimethods

from multimethod import multimethod

# Function that will be called
# for integer addition
@multimethod
def sum(x: int, y: int):
    return x + y

# Function that will be called
# for string addition
@multimethod
def sum(x: str, y: str):
    return x+" "+y

# Driver's code
print(sum(2, 3))
print(sum("Hello", "World"))
```

**输出:**

```
5
Hello World
```

**例 2:**

```
# Python program to demonstrate
# multimethods

from multimethod import multimethod

class GFG(object):

    @multimethod
    def double(self, x: int):
        print(2 * x)

    @multimethod
    def double(self, x: complex):
        print("sorry, I don't like complex numbers")

# Driver Code
obj = GFG()
obj.double(3)
obj.double(6j)
```

**输出:**

```
6
sorry, I don't like complex numbers
```