# python 中作为装饰器的类

> 原文:[https://www.geeksforgeeks.org/class-as-decorator-in-python/](https://www.geeksforgeeks.org/class-as-decorator-in-python/)

装饰器是 Python 中非常强大和有用的工具，因为它允许程序员修改函数或类的行为。装饰器允许我们包装另一个函数，以便扩展包装函数的行为，而无需永久修改它。
我们可以将装饰器定义为类为了做到这一点，我们必须使用类的 __call__ 方法。当用户需要创建一个充当函数的对象时，函数装饰器需要返回一个充当函数的对象，因此 __call__ 可能很有用。例如

## 蟒蛇 3

```
# Python program showing
# use of __call__() method

class MyDecorator:
    def __init__(self, function):
        self.function = function

    def __call__(self):

        # We can add some code
        # before function call

        self.function()

        # We can also add some code
        # after function call.

# adding class decorator to the function
@MyDecorator
def function():
    print("GeeksforGeeks")

function()
```

**Output:** 

```
GeeksforGeeks
```

**带有*args 和**kwargs 的类装饰器:**
为了使用带有*args 和**kwargs 参数的类装饰器，我们使用了一个 __call__ 函数，并在给定的函数中传递了这两个参数

## 蟒蛇 3

```
# Python program showing
# class decorator with *args
# and **kwargs

class MyDecorator:
    def __init__(self, function):
        self.function = function

    def __call__(self, *args, **kwargs):

        # We can add some code
        # before function call

        self.function(*args, **kwargs)

        # We can also add some code
        # after function call.

# adding class decorator to the function
@MyDecorator
def function(name, message ='Hello'):
    print("{}, {}".format(message, name))

function("geeks_for_geeks", "hello")
```

**Output:** 

```
hello, geeks_for_geeks
```

**带有返回语句的类装饰器:**
在给定的示例中，函数没有返回任何东西，因此没有任何问题，但是可能需要返回值。所以我们使用 return 语句和类装饰器。

## 蟒蛇 3

```
# Python program showing
# class decorator with
# return statement

class SquareDecorator:

    def __init__(self, function):
        self.function = function

    def __call__(self, *args, **kwargs):

        # before function
        result = self.function(*args, **kwargs)

        # after function
        return result

 # adding class decorator to the function
@SquareDecorator
def get_square(n):
    print("given number is:", n)
    return n * n

print("Square of number is:", get_square(195))
```

**Output:** 

```
given number is: 195
Square of number is: 38025
```

**使用类装饰器打印执行程序所需的时间:**
为了打印执行程序所需的时间，我们使用 __call__ 函数并使用一个时间模块，这样就可以得到一个程序的执行时间

## 蟒蛇 3

```
# Python program to execute
# time of a program

# importing time module
from time import time
class Timer:

    def __init__(self, func):
        self.function = func

    def __call__(self, *args, **kwargs):
        start_time = time()
        result = self.function(*args, **kwargs)
        end_time = time()
        print("Execution took {} seconds".format(end_time-start_time))
        return result

# adding a decorator to the function
@Timer
def some_function(delay):
    from time import sleep

    # Introducing some time delay to
    # simulate a time taking function.
    sleep(delay)

some_function(3)
```

**Output:** 

```
Execution took 3.003122091293335 seconds
```

**使用类修饰器检查错误参数:**
这类类修饰器使用最频繁。这个装饰器在执行函数之前检查参数，防止函数过载，并使它能够只存储逻辑和必要的语句。

## 蟒蛇 3

```
# Python program checking
# error parameter using
# class decorator

class ErrorCheck:

    def __init__(self, function):
        self.function = function

    def __call__(self, *params):
        if any([isinstance(i, str) for i in params]):
            raise TypeError("parameter cannot be a string !!")
        else:
            return self.function(*params)

@ErrorCheck
def add_numbers(*numbers):
    return sum(numbers)

#  returns 6
print(add_numbers(1, 2, 3))

# raises Error. 
print(add_numbers(1, '2', 3)) 
```

**输出:**

```
6
TypeError: parameter cannot be a string !!
```