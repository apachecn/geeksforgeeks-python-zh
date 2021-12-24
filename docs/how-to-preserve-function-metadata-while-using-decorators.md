# 如何在使用装饰器时保留函数元数据？

> 原文:[https://www . geesforgeks . org/如何在使用装饰器的同时保留功能元数据/](https://www.geeksforgeeks.org/how-to-preserve-function-metadata-while-using-decorators/)

**装饰器**是 Python 中非常强大和有用的工具，因为它允许程序员修改函数或类的行为。装饰器允许我们包装另一个函数，以便扩展包装函数的行为，而无需永久修改它。
**注:**更多信息，请参考 Python 中的[装饰器](https://www.geeksforgeeks.org/decorators-in-python/)

## 如何保存元数据？

这可以使用 functools 的[wrapps()](https://www.geeksforgeeks.org/python-functools-wraps-function/)方法来完成。它通过复制诸如 __name__、__doc__(文档字符串)等属性来更新包装函数，使其看起来像包装函数。
T3】例:

## 蟒蛇 3

```
import time
from functools import wraps

def timethis(func):
    '''Decorator that reports the execution time.'''

    @wraps(func)
    def wrapper(*args, **kwargs):
        start = time.time()
        result = func(*args, **kwargs)
        end = time.time()

        print(func.__name__, end-start)
        return result

    return wrapper

@timethis
def countdown(n:int):
    '''Counts down'''
    while n > 0:
        n -= 1

countdown(100000)
print(countdown.__name__)
print(countdown.__doc__)
print(countdown.__annotations__)
```

**输出:**

```
countdown 0.00827932357788086
countdown
Counts down
{'n': <class 'int'>}
```

**使用 wraps()的优势:**

*   复制装饰器元数据是编写装饰器的一个重要部分。如果忘记使用**@ wrapps**，会发现修饰后的功能失去了各种有用的信息。例如，如果省略，最后一个示例的输出将如下所示:

```
countdown 0.030733823776245117
wrapper
None
{}
```

*   **@ wrapped**装饰器的一个重要特性是，它在 **__wrapped__** 属性中为您提供了 wrapped 功能。例如，如果您想直接访问包装函数，您可以这样做:

```
countdown.__wrapped__(100000)
```

*   **__wrapped__** 属性的存在也使得修饰函数正确地公开了包装函数的底层签名。例如:

## 蟒蛇 3

```
from inspect import signature

print(signature(countdown))
```

*   **输出:**

```
(n:int)
```