# Python 中的函数装饰器|第 1 集(简介)

> 原文:[https://www . geesforgeks . org/function-decorators-in-python-set-1-introduction/](https://www.geeksforgeeks.org/function-decorators-in-python-set-1-introduction/)

<center>**Background**</center>

Following are important facts about functions in Python that are useful to understand decorator functions.

1.  在 Python 中，我们可以在另一个函数中定义一个函数。
2.  在 Python 中，一个函数可以作为参数传递给另一个函数(一个函数也可以返回另一个函数)。

```py
# A Python program to demonstrate that a function
# can be defined inside another function and a
# function can be passed as parameter.

# Adds a welcome message to the string
def messageWithWelcome(str):

    # Nested function
    def addWelcome():
        return "Welcome to "

    # Return concatenation of addWelcome()
    # and str.
    return  addWelcome() + str

# To get site name to which welcome is added
def site(site_name):
    return site_name

print messageWithWelcome(site("GeeksforGeeks"))
```

输出:

```py
Welcome to GeeksforGeeks
```

<center>**Function Decorator**</center>

A decorator is a function that takes a function as its only parameter and returns a function. This is helpful to “wrap” functionality with the same code over and over again. For example, above code can be re-written as following.

我们使用@func_name 来指定要应用于另一个函数的装饰器。

```py
# Adds a welcome message to the string
# returned by fun(). Takes fun() as
# parameter and returns welcome().
def decorate_message(fun):

    # Nested function
    def addWelcome(site_name):
        return "Welcome to " + fun(site_name)

    # Decorator returns a function
    return addWelcome

@decorate_message
def site(site_name):
    return site_name;

# Driver code

# This call is equivalent to call to
# decorate_message() with function
# site("GeeksforGeeks") as parameter
print site("GeeksforGeeks")
```

输出:

```py
Welcome to GeeksforGeeks
```

装饰者也可以将数据(或添加属性)附加到函数中。

```py
# A Python example to demonstrate that
# decorators can be useful attach data

# A decorator function to attach
# data to func
def attach_data(func):
       func.data = 3
       return func

@attach_data
def add (x, y):
       return x + y

# Driver code

# This call is equivalent to attach_data()
# with add() as parameter
print(add(2, 3))

print(add.data)
```

输出:

```py
5
3
```

“add()”返回作为参数传递的 x 和 y 的和，但是它被装饰函数包装，调用 add(2，3)将简单地给出两个数字的和，但是当我们调用 add.data 时，然后将“add”函数作为参数传递给装饰函数“attach_data ”,并且该函数返回带有属性“data”的“add”函数，该属性设置为 3，因此打印它。

Python 装饰器是消除冗余的强大工具。

更多详情请参考 Python 中的[装饰器](https://www.geeksforgeeks.org/decorators-in-python/)。

本文由 **Shwetanshu Rohatgi** 供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论