# 如何在 Python 中克隆一个方法代码？

> 原文:[https://www . geesforgeks . org/如何克隆 python 中的方法代码/](https://www.geeksforgeeks.org/how-to-clone-a-method-code-in-python/)

借助`**methodName.__code__.replace()**`方法，我们可以克隆内置方法的代码以及任何其他已定义的方法，并且我们还可以使用`methodName.__code__.replace()`方法固定任何克隆的方法代码中的位置唯一参数。

> **语法:** `methodName.__code__.replace()`
> 
> **返回:**返回新克隆方法的对象，只有很少的位置参数。

**注意:**
要运行下面给出的程序，你必须安装最新版本的 Python，即 Python 3.8.2，否则会显示如下错误。

```py
AttributeError: ‘code’ object has no attribute ‘replace’.

```

**示例#1 :**
在这个示例中，我们可以看到，通过使用`methodName.__code__.replace()`方法，我们能够在该方法的帮助下克隆内置方法以及任何已定义方法的代码。

```py
from statistics import median

# Using methodName.__code__.replace() method
median.__code__ = median.__code__.replace(co_posonlyargcount = 1)

print(median([1, 2, 3]))
```

**输出:**

```py
2
```

**例 2 :**

```py
def multiply(a, b):
    return a * b

# Using methodName.__code__.replace(co_posonlyargcount = 1) method
multiply.__code__ = multiply.__code__.replace(co_posonlyargcount = 2)

print(multiply(5, 6))
```

**输出:**

```py
30
```