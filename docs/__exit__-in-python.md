# _ _ Python 中的 exit _ _

> 原文:[https://www.geeksforgeeks.org/__exit__-in-python/](https://www.geeksforgeeks.org/__exit__-in-python/)

上下文管理器用于管理程序使用的资源。使用完成后，我们必须释放内存并终止文件之间的连接。如果它们没有被释放，那么它将导致资源泄漏，并可能导致系统变慢或崩溃。即使我们不释放资源，上下文管理器也会隐式地执行这个任务。

> 参考下面的文章，了解上下文管理器的基础知识。
> 
> *   [上下文管理器](https://www.geeksforgeeks.org/context-manager-in-python/)

## __exit__()方法

这是`ContextManager`类的一个方法。`__exit__` 方法负责释放当前代码片段占用的资源。无论我们使用完资源后做什么，都必须执行这个方法。此方法包含正确关闭资源处理程序的指令，以便释放资源供操作系统中的其他程序进一步使用。

如果引发异常；它的类型、值和回溯作为参数传递给`__exit__()`。否则，提供三个`None` 参数。如果异常被抑制，则`__exit__()`方法的返回值为`True`，否则为`False`。

> **语法:** __exit__(self，exception_type，exception_value，exception_traceback)
> 
> **参数:**
> **异常 _ 类型:**表示异常类别。
> **异常 _ 值:**表示异常类型。像被零除错误、浮点错误，这些都是算术异常的类型。
> **exception _ trace back:**trace back 是包含解决异常所需的所有信息的报告。

**#例 1:** 。

```
# Python program creating a 
# context manager 

class ContextManager(): 
    def __init__(self): 
        print('init method called') 

    def __enter__(self): 
        print('enter method called') 
        return self

    def __exit__(self, exc_type, exc_value, exc_traceback): 
        print('exit method called') 

with ContextManager() as manager: 
    print('with statement block')
```

**输出:**

```
init method called
enter method called
with statement block
exit method called

```

**#例 2:** 了解`__exit__()`参数。我们将创建一个上下文管理器，用于划分两个数字。如果

```
# Python program to demonstrate
# __exit__ method

class Divide:
    def __init__(self, num1, num2):
        self.num1 = num1
        self.num2 = num2

    def __enter__(self):
        print("Inside __enter__")
        return self

    def __exit__(self, exc_type, exc_value, traceback):
        print("\nInside __exit__")
        print("\nExecution type:", exc_type)
        print("\nExecution value:", exc_value)
        print("\nTraceback:", traceback)

    def divide_by_zero(self):
        # causes ZeroDivisionError exception
        print(self.num1 / self.num2)

# Driver's code
with Divide(3, 1) as r:
    r.divide_by_zero()

print("................................................")

# will raise a ZeroDivisionError
with Divide(3, 0) as r:
    r.divide_by_zero()
```

**输出:**

```
Inside __enter__
3.0

Inside __exit__

Execution type: None

Execution value: None

Traceback: None
................................................
Inside __enter__

Inside __exit__

Execution type: 

Execution value: division by zero

Traceback: 
Traceback (most recent call last):
  File "gfg.py", line 32, in 
    r.divide_by_zero()
  File "gfg.py", line 21, in divide_by_zero
    print(self.num1 / self.num2)
ZeroDivisionError: division by zero

```