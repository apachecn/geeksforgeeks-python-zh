# 调用 Python 中的()装饰器

> 原文:[https://www.geeksforgeeks.org/call-decorator-in-python/](https://www.geeksforgeeks.org/call-decorator-in-python/)

**[Python 装饰器](https://www.geeksforgeeks.org/decorators-in-python/)** 是该语言的重要特性，允许程序员修改类的行为。这些特性在功能上被添加到现有代码中。这是一种在编译时修改程序的**元编程**。装饰器可以用来在函数或类中注入修改过的代码。装饰者允许修改程序来添加任何有特殊作用的代码。装饰者在定义你所装饰的函数之前被调用。

装饰者的使用可以用下面的例子来解释。假设我们编写一个程序，使用另一个函数来“装饰”一个函数。代码是这样的:

```
# Code to explain Decorators
def decorating(function):
    def item():
        print("The function was decorated.")
        function()
    return item

def my_function():
    print("This is my function.")

my_function()

decorate = decorating(my_function)
decorate()
```

**输出**

```
This is my function.
The function was decorated.
This is my function.

```

首先，出现“这是我的函数”是因为函数调用 my_function()。第二组输出是因为装饰功能。

同样的事情也可以通过使用装饰者来完成。下面的代码解释了这一点。请注意，修饰语句是在要修饰的函数之上定义的。

```
# Code to implement the usage
# of decorators
def decorating(function):
    def item():
        print("The function was decorated.")
        function()
    return item

# using the "@" sign to signify 
# that a decorator is used. 
@decorating
def my_function():
    print("This is my function.")

# Driver's Code
my_function()
```

**输出**

```
The function was decorated.
This is my function.

```

#### 调用()装饰器

**使用 call()装饰器代替助手函数**。在 python 或任何其他语言中，我们使用助手函数有三个主要目的:

1.  确定方法的目的。
2.  一旦助手函数的工作完成，它就会被删除。和
3.  助手函数的目的与装饰函数的目的相匹配。

下面的例子将说明调用装饰器方法的重要性。在本例中，我们将使用一个助手函数来构建第一个“n”个数字的双精度列表。
代码如下:

```
# Helper function to build a
# list of numbers
def list_of_numbers(n):
    element = []
    for i in range(n):
        element.append(i * 2)
    return element

list_of_numbers = list_of_numbers(6)

# Output command
print(len(list_of_numbers),
      list_of_numbers[2])
```

**输出**

```
6, 4

```

上面的代码也可以使用 call()装饰器编写:

```
# Defining the decorator function
def call(*argv, **kwargs):
    def call_fn(function):
        return function(*argv, **kwargs)
    return call_fn

# Using the decorator function
@call(6)
def list_of_numbers(n):
    element = []
    for i in range(n):
        element.append(i * 2)
    return element

# Output command
print(len(list_of_numbers),
      list_of_numbers[2])
```

**输出**

```
6, 4

```

据观察，输出与之前相同，这意味着 call()装饰器的工作方式几乎与 helper 函数完全一样。