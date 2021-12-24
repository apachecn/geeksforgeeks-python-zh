# Python 中的条件装饰器

> 原文:[https://www . geesforgeks . org/conditional-decorators-in-python/](https://www.geeksforgeeks.org/conditional-decorators-in-python/)

在 Python 中，[装饰器](https://www.geeksforgeeks.org/decorators-in-python/)是通过将函数作为输入并返回一个可调用的来包装函数的函数或类。它们允许创建可重用的构建代码块，这些代码块可以改变或扩展其他函数的行为。

## 条件装饰者

给定一个条件，这里的想法是执行代码，或者如果某个条件满足或为真，则基本上使用装饰器包装函数。有两种方法可以有条件地使用装饰器。

**方法 1:当装饰者决定如何包装一个函数时**

*   在这种情况下，函数通常被传递给装饰器
*   然后根据条件，装饰者决定如何处理代码

下面的程序通常将一个函数传递给装饰器，如果给定的条件为真，则程序以大写形式返回字符串，如果为假，则以小写形式返回字符串。

```
condition = True

def conditional_decorator(func):

    def wrapper():
        oldstring = func()

        if condition:
            newstring = oldstring.upper()
        else:
            newstring = oldstring.lower()

        return newstring

    return wrapper

@conditional_decorator
def func():
    return 'geeKSfoRGEEks'

print(func())
```

**输出:**

```
'GEEKSFORGEEKS'
```

**方法二:在这种情况下，只有满足某个条件，才会调用装饰者。**

在下面的程序中，程序接受用户输入来决定条件。如果用户输入 1，装饰器被调用，字符串以大写形式返回。如果用户输入 2，则再次调用装饰器，并以小写形式返回给定的字符串。除此之外，如果输入任何其他数字，函数将按原样返回，不做任何修改。

```
def decorator1(func):

    def wrapper():
        oldstring = func()
        newstring = oldstring.upper()
        return newstring

    return wrapper

def decorator2(func):

    def wrapper():
        oldstring = func()
        newstring = oldstring.lower()
        return newstring

    return wrapper

cond = 1

if cond == 1:
    @decorator1
    def func():
        return 'GeeksFORGeeKs'
elif cond == 2:
    @decorator2
    def func():
        return 'GeeksFORGeeKs'
else:
    def func():
        return 'GeeksFORGeeKs'

print(func())
```

**输出:**

```
GEEKSFORGEEKS
```