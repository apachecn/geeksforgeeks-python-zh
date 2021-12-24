# 如何打印 Python 异常/错误层次结构？

> 原文:[https://www . geesforgeks . org/如何打印 python-异常-错误-层次结构/](https://www.geeksforgeeks.org/how-to-print-the-python-exception-error-hierarchy/)

在打印错误层次结构之前，让我们了解**什么是真正的异常？**即使我们的代码在语法上是正确的，异常也会发生，但是在执行时它们会抛出一个错误。它们不是无条件致命的，我们在执行时得到的错误被称为异常。Python 中有许多内置的异常，让我们尝试以层次结构打印出来。

为了打印树层次，我们将使用 Python 中的 [**【检查】**](https://docs.python.org/3/library/inspect.html#module-inspect) 模块。 **inspect** 模块提供了有用的功能来获取关于对象的信息，例如模块、类、方法、函数和代码对象。例如，它可以帮助您检查类的内容，提取并格式化函数的参数列表。

为了构建树层次结构，我们将使用 **inspect.getclasstree()。**

> **语法:** inspect.getclasstree(类，唯一=False)

**inspect.getclasstree()** 将给定的类列表排列成嵌套列表的层次结构。当嵌套列表出现时，它包含从其条目紧接在列表前面的类派生的类。

如果唯一参数为真，则给定列表中每个类的返回结构中只出现一个条目。否则，使用多重继承的类及其后代将出现多次。

让我们编写一个代码来打印内置异常的树层次结构:

## 蟒蛇 3

```py
# import inspect module
import inspect

# our treeClass function
def treeClass(cls, ind = 0):

      # print name of the class
    print ('-' * ind, cls.__name__)

    # iterating through subclasses
    for i in cls.__subclasses__():
        treeClass(i, ind + 3)

print("Hierarchy for Built-in exceptions is : ")

# inspect.getmro() Return a tuple 
# of class  cls’s base classes.

# building a tree hierarchy 
inspect.getclasstree(inspect.getmro(BaseException))

# function call
treeClass(BaseException)
```

**输出:**

```py
Hierarchy for Built-in exceptions is : 
 BaseException
--- Exception
------ TypeError
------ StopAsyncIteration
------ StopIteration
------ ImportError
--------- ModuleNotFoundError
--------- ZipImportError
------ OSError
--------- ConnectionError
------------ BrokenPipeError
------------ ConnectionAbortedError
------------ ConnectionRefusedError
------------ ConnectionResetError
--------- BlockingIOError
--------- ChildProcessError
--------- FileExistsError
--------- FileNotFoundError
--------- IsADirectoryError
--------- NotADirectoryError
--------- InterruptedError
--------- PermissionError
--------- ProcessLookupError
--------- TimeoutError
--------- UnsupportedOperation
------ EOFError
------ RuntimeError
--------- RecursionError
--------- NotImplementedError
--------- _DeadlockError
------ NameError
--------- UnboundLocalError
------ AttributeError
------ SyntaxError
--------- IndentationError
------------ TabError
------ LookupError
--------- IndexError
--------- KeyError
--------- CodecRegistryError
------ ValueError
--------- UnicodeError
------------ UnicodeEncodeError
------------ UnicodeDecodeError
------------ UnicodeTranslateError
--------- UnsupportedOperation
------ AssertionError
------ ArithmeticError
--------- FloatingPointError
--------- OverflowError
--------- ZeroDivisionError
------ SystemError
--------- CodecRegistryError
------ ReferenceError
------ MemoryError
------ BufferError
------ Warning
--------- UserWarning
--------- DeprecationWarning
--------- PendingDeprecationWarning
--------- SyntaxWarning
--------- RuntimeWarning
--------- FutureWarning
--------- ImportWarning
--------- UnicodeWarning
--------- BytesWarning
--------- ResourceWarning
------ _OptionError
------ error
------ Verbose
------ Error
------ TokenError
------ StopTokenizing
------ EndOfBlock
--- GeneratorExit
--- SystemExit
--- KeyboardInterrupt

```