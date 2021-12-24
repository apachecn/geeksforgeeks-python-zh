# 如何从 Python 对象中检索源代码？

> 原文:[https://www . geesforgeks . org/如何从 python 对象中检索源代码/](https://www.geeksforgeeks.org/how-to-retrieve-source-code-from-python-objects/)

有时候知道一些函数源代码是什么样子是很重要的。在这种情况下，我们在 Python 编程中有**检查模块**一个内置的标准库。它提供了几个有用的函数来跟踪关于活动对象的信息，例如模块、类、方法、函数、回溯、框架对象和代码对象。getsource()方法用于获取 Python 对象的源代码。

> **语法:** inspect.getsource(对象)
> 
> **返回类型:**对象的源代码文本

如果无法检索源代码，将引发 IOError。

**示例:**

```
# import inspect library
import inspect

def test(x):
    return x * 2

print(inspect.getsource(test))
```

**输出:**

```
def test(x):

   return (x+2)*(x-2)

```

**示例:**

```
# import inspect library
import inspect

def far(n):
    factorial = 1
    if int(n) >= 1:
        for i in range (1, int(n)+1):
            factorial = factorial * i
    return factorial

source = inspect.getsource(far)
print(source)
```

**输出:**

```
def far(n):
    factorial = 1
    if int(n) >= 1:
        for i in range (1, int(n)+1):
            factorial = factorial * i
    return factorial

```

**示例:**我们也可以在内置的库函数和对象上使用 inspect。

```
# import inspect library
import inspect
import pandas

source_DF = inspect.getsource(pandas.DataFrame)
print(source_DF[:100])
```

**输出:**

```
class DataFrame(NDFrame):
    """
    Two-dimensional size-mutable, potentially heterogeneous tabula

```