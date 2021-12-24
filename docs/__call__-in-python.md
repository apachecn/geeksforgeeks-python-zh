# _ _ 在 Python 中调用 _ _

> 原文:[https://www.geeksforgeeks.org/__call__-in-python/](https://www.geeksforgeeks.org/__call__-in-python/)

Python 有一套内置的方法，`__call__`就是其中之一。`__call__` 方法使 Python 程序员能够编写类，其中实例的行为类似于函数，并且可以像函数一样被调用。当实例作为函数调用时；如果定义了这个方法，`x(arg1, arg2, ...)`是`x.__call__(arg1, arg2, ...)`的简写。

```
object() is shorthand for object.__call__()
```

**例 1:**

```
class Example:
    def __init__(self):
        print("Instance Created")

    # Defining __call__ method
    def __call__(self):
        print("Instance is called via special method")

# Instance created
e = Example()

# __call__ method will be called
e()
```

**输出:**

```
Instance Created
Instance is called via special method

```

**例 2:**

```
class Product:
    def __init__(self):
        print("Instance Created")

    # Defining __call__ method
    def __call__(self, a, b):
        print(a * b)

# Instance created
ans = Product()

# __call__ method will be called
ans(10, 20)
```

**输出:**

```
Instance Created
200

```