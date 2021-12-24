# 在 Python 中实现 IsNumber()函数

> 原文:[https://www . geesforgeks . org/implement-is number-function-in-python/](https://www.geeksforgeeks.org/implement-isnumber-function-in-python/)

在本文中，我们将看到如何使用 Python 实现 **isNumber()** 方法。此方法接受一个字符串作为输入，并根据该字符串是否为数字返回真或假。
**例:**

```
Input :  "12345"
Output :  True

Input : "-12345" 
Output : True 

Input : "abc"
Output : False
```

**方法:**
这里我们将利用 Python 中可用的 [int()](https://www.geeksforgeeks.org/python-int-function/) 内置函数。同样通过这种方法，我们将看到 [**【异常处理】**](https://www.geeksforgeeks.org/python-set-5-exception-handling/) 是如何帮助我们的。使用 try-catch 构造，我们尝试将字符串转换为整数。如果字符串无法转换，处理程序将捕获引发的异常。
**下面是实现:**

## 蟒蛇 3

```
# Implementation of isNumber() function
def isNumber(s):

    # handle for negative values
    negative = False
    if(s[0] =='-'):
        negative = True

    if negative == True:
        s = s[1:]

    # try to convert the string to int
    try:
        n = int(s)
        return True
    # catch exception if cannot be converted
    except ValueError:
        return False

s1 = "9748513"
s2 = "-9748513"
s3 = "GeeksforGeeks"

print("For input '{}' isNumber() returned : {}".format(s1, isNumber(s1)))
print("For input '{}' isNumber() returned : {}".format(s2, isNumber(s2)))
print("For input '{}' isNumber() returned : {}".format(s3, isNumber(s3)))
```

**输出:**

```
For input '9748513' isNumber() returned : True
For input '-9748513' isNumber() returned : True
For input 'GeeksforGeeks' isNumber() returned : False
```

**注意:**这不是实现 isNumber()函数的唯一方法，但可以说是最快的方法。Try/Catch 不会引入太多开销，因为最常见的异常是在没有大量搜索堆栈帧的情况下捕获的。