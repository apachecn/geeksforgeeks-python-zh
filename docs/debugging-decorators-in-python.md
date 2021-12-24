# 用 Python 调试装饰器

> 原文:[https://www . geeksforgeeks . org/debug-December-in-python/](https://www.geeksforgeeks.org/debugging-decorators-in-python/)

[Python 中的装饰器](https://www.geeksforgeeks.org/decorators-in-python/)真的是一个非常强大的功能。如果你是一个网络开发人员，并且你已经使用了 Django 框架或者其他一些开发框架，你可能已经遇到了装饰者。

总的来说，装饰器是包装现有函数或方法并修改其特性的包装函数。让我们举一个简短的例子。假设您有一个扬声器功能，它会返回中性消息

## 蟒蛇 3

```py
def speak():
    """Returns a neutral message"""
    return "Hi, Geeks!"

# printing the output
print(speak())
```

**输出:**

```py
Hi, Geeks!

```

假设您需要修改函数以愉快的语气返回消息。让我们为此创建一个装饰器。

## 蟒蛇 3

```py
# decorator
def make_geek_happy(func):
    def wrapper():
        neutral_message = func()
        happy_message = neutral_message + " You are happy!"
        return happy_message
    return wrapper

#using the decorator 
@make_geek_happy
def speak():
    """Returns a neutral message"""
    return "Hi, Geeks!"

print(speak())
```

**输出:**

```py
Hi, Geeks! You are happy!

```

## 调试装饰器

这样，装饰者也可以用来修改不同的功能，使它们更有用。然而，这个过程有一些缺点。当我们在装饰器中包装原始函数时，原始函数的元数据会丢失。考虑下面的程序，但这次我们用另一种方式使用装饰器，只是为了让你明白。

如果您试图访问 positive_message 函数的任何元数据，它实际上会在装饰器中返回包装器的元数据。

## 蟒蛇 3

```py
# decorator
def make_geek_happy(func):
    def wrapper():
        neutral_message = func()
        happy_message = neutral_message + " You are happy!"
        return happy_message
    return wrapper

def speak():
    """Returns a neutral message"""
    return "Hi!"

# wrapping the function in the decorator
# and assigning it to positive_message
positive_message = make_geek_happy(speak)

print(positive_message())

print(speak.__name__) 
print(speak.__doc__) 
print(positive_message.__name__)
print(positive_message.__doc__)
```

**输出:**

```py
Hi! You are happy!
speak
Returns a neutral message
wrapper
None

```

这些结果让调试变得非常困难。但是由于 Python，它也有一个解决方案来解决这个问题，而不需要太多的努力。我们只需要使用 Python 标准库中包含的**functools . wrapps()**装饰器。

这里有一个例子:

## 蟒蛇 3

```py
# importing the module
import functools

# decorator
def make_geek_happy(func):
    @functools.wraps(func)
    def wrapper():
        neutral_message = func()
        happy_message = neutral_message + " You are happy!"
        return happy_message
    return wrapper

def speak():
    """Returns a neutral message"""
    return "Hi!"

positive_message = make_geek_happy(speak)
print(positive_message())

print(speak.__name__) 
print(speak.__doc__) 
print(positive_message.__name__)
print(positive_message.__doc__)
```

**输出:**

```py
Hi! You are happy!
speak
Returns a neutral message
speak
Returns a neutral message

```