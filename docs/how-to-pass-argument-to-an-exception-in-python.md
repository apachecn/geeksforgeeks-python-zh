# 如何在 Python 中将参数传递给异常？

> 原文:[https://www . geesforgeks . org/如何将参数传递给 python 中的异常/](https://www.geeksforgeeks.org/how-to-pass-argument-to-an-exception-in-python/)

可能会出现需要 Python 引发的异常的额外信息的情况。
Python 有两种类型的异常，即[内置异常](https://www.geeksforgeeks.org/built-exceptions-python/)和[用户自定义异常](https://www.geeksforgeeks.org/user-defined-exceptions-python-examples/)。
**为什么要在异常中使用参数？**
在 Python 中使用异常参数非常有用，原因如下:

*   它可用于获取有关遇到的错误的附加信息。

*   由于参数的内容会因 Python 中不同类型的异常而有所不同，因此可以向异常提供变量来捕捉所遇到错误的本质。相同的错误可能由于不同的原因而发生，参数帮助我们使用**除了**子句来识别错误的具体原因。

*   它还可以通过使用变量跟随异常元组来捕获多个异常。

**内置异常中的参数:**

以下代码演示了带有内置异常的参数的使用:
**示例 1:**

## 蟒蛇 3

```
try:
    b = float(100 + 50 / 0)
except Exception as Argument:
    print( 'This is the Argument\n', Argument)
```

**输出:**

```
This is the Argument
 division by zero
```

**例 2:**

## 蟒蛇 3

```
my_string = "GeeksForGeeks"

try:
    b = float(my_string / 20)
except Exception as Argument:
    print( 'This is the Argument\n', Argument)
```

**输出:**

```
This is the Argument
 unsupported operand type(s) for /: 'str' and 'int'
```

**用户定义异常中的参数:**

以下代码演示了带有用户定义异常的参数的使用:
**示例 1:**

## 蟒蛇 3

```
# create user-defined exception 
# derived from super class Exception
class MyError(Exception):

    # Constructor or Initializer
    def __init__(self, value):
        self.value = value

    # __str__ is to print() the value
    def __str__(self):
        return(repr(self.value))

try:
    raise(MyError("Some Error Data"))

# Value of Exception is stored in error
except MyError as Argument:
    print('This is the Argument\n', Argument)
```

**输出:**

```
This is the Argument
 'Some Error Data'
```

**例 2:**

## 蟒蛇 3

```
# class Error is derived from super class Exception
class Error(Exception):

    # Error is derived class for Exception, but
    # Base class for exceptions in this module
    pass

class TransitionError(Error):

    # Raised when an operation attempts a state
    # transition that's not allowed.
    def __init__(self, prev, nex, msg):
        self.prev = prev
        self.next = nex

try:
    raise(TransitionError(2, 3 * 2, "Not Allowed"))

# Value of Exception is stored in error
except TransitionError as Argument:
    print('Exception occurred: ', Argument)
```

**输出:**

```
Exception occurred:  (2, 6, 'Not Allowed')
```