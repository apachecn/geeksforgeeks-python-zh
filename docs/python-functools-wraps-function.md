# Python | functools . wrapps()函数

> 原文:[https://www . geesforgeks . org/python-func tools-wrapps-func/](https://www.geeksforgeeks.org/python-functools-wraps-function/)

**functools** 是一个标准的 Python 模块，用于高阶函数(作用于或返回其他函数的函数)。wraps()是应用于装饰器的包装函数的装饰器。它通过复制诸如 __name__、__doc__(文档字符串)等属性来更新包装函数，使其看起来像包装函数。

> **语法:**@ functools . wrapps(wrapped，assigned = WRAPPER_ASSIGNMENTS，updated = WRAPPER _ UPDATES)
> **参数:**
> **wrapped** :要由 WRAPPER 函数修饰的函数名。
> **赋值** : Tuple 指定将原函数的哪些属性直接赋给包装函数上的匹配属性。默认设置为 wrapper_ASSIGNMENTS(分配给 WRAPPER 函数的 __module__、__name__、__qualname__、__annotations__ 和 __doc__，文档字符串)
> **更新后的** : Tuple 指定用原始函数的相应属性更新 WRAPPER 函数的哪些属性。默认设置为 WRAPPER_UPDATES(更新包装函数的 __dict__，即实例字典)。

**示例 1:** 不带 functools . wrapps()

## 蟒蛇 3

```py
def a_decorator(func):
    def wrapper(*args, **kwargs):
        """A wrapper function"""
        # Extend some capabilities of func
        func()
    return wrapper

@a_decorator
def first_function():
    """This is docstring for first function"""
    print("first function")

@a_decorator
def second_function(a):
    """This is docstring for second function"""
    print("second function")

print(first_function.__name__)
print(first_function.__doc__)
print(second_function.__name__)
print(second_function.__doc__)
```

**Output:**

```py
wrapper
A wrapper function
wrapper
A wrapper function
```

现在如果我们写 help(first_function)和 help(second_function)
会发生什么

## 蟒蛇 3

```py
print("First Function")
help(first_function)

print("\nSecond Function")
help(second_function)
```

**Output:** 

```py
First Function
Help on function wrapper in module __main__:

wrapper(*args, **kwargs)
    A wrapper function

Second Function
Help on function wrapper in module __main__:

wrapper(*args, **kwargs)
    A wrapper function
```

虽然上面的代码在逻辑上运行良好，但是如果您正在编写一个应用编程接口或库，并且有人想知道您的函数是做什么的，它的名称或者简单地键入 help(yoursfunction)，它将总是显示包装函数的名称和文档字符串。如果您对不同的函数使用相同的包装函数，这将变得更加令人困惑，因为它将为每个函数显示相同的细节。
理想情况下应该显示包装函数的名称和文档字符串，而不是包装函数。手动解决方案是在包装函数中分配 __name__ 和 __doc__ 属性，然后再返回它。

## 蟒蛇 3

```py
def a_decorator(func):
    def wrapper(*args, **kwargs):
        """A wrapper function"""
        # Extend some capabilities of func
        func()
    wrapper.__name__ = func.__name__
    wrapper.__doc__ = func.__doc__
    return wrapper

@a_decorator
def first_function():
    """This is docstring for first function"""
    print("first function")

@a_decorator
def second_function(a):
    """This is docstring for second function"""
    print("second function")

print(first_function.__name__)
print(first_function.__doc__)
print(second_function.__name__)
print(second_function.__doc__)
```

**Output:**

```py
first_function
This is docstring for first function
second_function
This is docstring for second function
```

这就解决了问题，但是如果我们再次输入帮助(your function)
呢

## 蟒蛇 3

```py
print("First Function")
help(first_function)

print("\nSecond Function")
help(second_function)
```

对于 first_function:帮助(first_function)

**Output:** 

```py
First Function
Help on function first_function in module __main__:

first_function(*args, **kwargs)
    This is docstring for first function

Second Function
Help on function second_function in module __main__:

second_function(*args, **kwargs)
    This is docstring for second function
```

正如您所看到的，它仍然有一个问题，即函数的签名，它显示了包装函数为每个函数使用的签名(这里是通用签名)。此外，如果您正在实现许多装饰器，那么您必须为它们中的每一个编写这些行。
所以为了节省时间和增加可读性，我们可以使用**functools . wrapps()作为修饰器来包装函数**。
**示例(带 func tools . wrapps())**

## 蟒蛇 3

```py
from functools import wraps

def a_decorator(func):
    @wraps(func)
    def wrapper(*args, **kwargs):
        """A wrapper function"""

        # Extend some capabilities of func
        func()
    return wrapper

@a_decorator
def first_function():
    """This is docstring for first function"""
    print("first function")

@a_decorator
def second_function(a):
    """This is docstring for second function"""
    print("second function")

print(first_function.__name__)
print(first_function.__doc__)
print(second_function.__name__)
print(second_function.__doc__)
```

**Output:** 

```py
first_function
This is docstring for first function
second_function
This is docstring for second function
```

现在，如果我们键入帮助(first _ function)–

## 蟒蛇 3

```py
print("First Function")
help(first_function)

print("\nSecond Function")
help(second_function)
```

**Output:** 

```py
First Function
Help on function first_function in module __main__:

first_function()
    This is docstring for first function

Second Function
Help on function second_function in module __main__:

second_function(a)
    This is docstring for second function
```