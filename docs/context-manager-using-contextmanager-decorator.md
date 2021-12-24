# 使用@contextmanager 装饰器的上下文管理器

> 原文:[https://www . geesforgeks . org/context-manager-use-context manager-decorator/](https://www.geeksforgeeks.org/context-manager-using-contextmanager-decorator/)

装饰器是 Python 中非常强大和有用的工具，因为它允许程序员修改函数或类的行为。装饰器允许我们包装另一个函数，以便扩展包装函数的行为，而无需永久修改它。

**语法:**

```
@decorator
def function(args):
    statements(s)
```

**示例:**

## 蟒蛇 3

```
# Python program to demonstrate
# decorators

def msg_decorator(func):

    # Inner function
    def msg_wrapper(msg):
        print("A decorated line:", func(msg))

    return msg_wrapper

# Using the decorator
@msg_decorator
def print_name(name):
    return name

print_name("Pooventhiran")
```

**Output:** 

```
A decorated line: Pooventhiran
```

在本例中，每当调用 print_name()时，首先调用 *msg_decorator* ，参数为 print_name。在 msg_decorator 内部，返回 msg_wrapper，它只调用传递给 msg_decorator 的函数，参数传递给它。虽然这个例子很简单，但在实际使用中，比如检查边界/特殊条件、预处理等，这些功能非常强大。
**注:**更多信息请参考 Python 中的[装饰器](https://www.geeksforgeeks.org/decorators-in-python/)。

## 上下文管理器

**上下文管理器**是 Python 的资源管理器。在大多数情况下，我们使用文件作为资源(一种简单的资源)。我们通常不关心在执行结束时关闭文件。这是一种糟糕的编码实践，并且当打开太多文件时，或者当程序由于资源没有正确释放而失败时，这也会导致问题。上下文管理器通过自动管理资源来解决这个问题。在 Python 中，使用了 with 关键字。

**示例:**

## 蟒蛇 3

```
# Python program to demonstrate
# Context Manager

with open('testfile.txt') as in_file:
    print(''.join(in_file.readlines()))
```

在上面显示的例子中，使用的文件由 ContextManager 自己管理，因为即使程序失败，它也会关闭文件。这个上下文管理器功能也可以内置到我们的程序中。用户需要确保该类具有方法:_ _ _ enter _ _()和 __exit__()。让我们看看一个有这些特殊方法的模板。

## 蟒蛇 3

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

# Driver code
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

在上面的代码中，__enter__ 将在 control with 进入时执行，__exit__ 将在 control with 子句离开时执行。我们可以在**context lib . context manager**装饰器的帮助下，简单地将任何函数作为上下文管理器，而无需编写单独的类或 __enter__ 和 __exit__ 函数。

#### 使用@contextmanager

我们必须使用 contextlib.contextmanager 来修饰一个生成函数，该函数只产生**一次**。屈服前的一切都被认为是 __ 进入 __ 部分，屈服后的一切都被认为是 _ _ 退出 _ _ 部分。生成器函数应该产生资源。

**示例:**让我们用这个装饰器重写上面的示例

## 蟒蛇 3

```
# Python program for creating a
# context manager using @contextmanager
# decorator

from contextlib import contextmanager

@contextmanager
def ContextManager():

    # Before yield as the enter method
    print("Enter method called")
    yield

    # After yield as the exit method
    print("Exit method called")

with ContextManager() as manager:
    print('with statement block')
```

**输出:**

```
Enter method called
with statement block
Exit method called 
```