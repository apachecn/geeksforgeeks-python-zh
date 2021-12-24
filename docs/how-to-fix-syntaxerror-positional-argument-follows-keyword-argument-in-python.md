# 如何修复:语法错误:Python 中位置参数跟在关键字参数后面

> 原文:[https://www . geesforgeks . org/how-fix-syntaxerror-positional-argument-follow-keyword-argument-in-python/](https://www.geeksforgeeks.org/how-to-fix-syntaxerror-positional-argument-follows-keyword-argument-in-python/)

在本文中，我们将讨论如何修复 Python 中位置参数跟在关键字参数后面的语法错误

参数是调用函数时提供给该函数的值。比如看下面的程序–

## Python

```py
# function
def calculate_square(num):
    return num * num

# call the function
result = calculate_square(10)
print(result)
```

**输出**

```py
100

```