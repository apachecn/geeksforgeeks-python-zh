# Python 中的帮助功能

> 原文:[https://www.geeksforgeeks.org/help-function-in-python/](https://www.geeksforgeeks.org/help-function-in-python/)

**Python 帮助功能**用于显示模块、函数、类、关键词等文档。

### 帮助函数具有以下语法:

```
help([object])
```

### Python help()函数参数

```
object: Call help of the given object.
```

如果传递的帮助函数没有参数，那么交互式帮助实用程序将在控制台上启动。

## Python 帮助()示例

让我们查看 python 控制台中打印功能的文档。

## 蟒蛇 3

```
help(print)
```

**输出:**

```
Help on built-in function print in module builtins:

print(...)
    print(value, ..., sep=' ', end='\n', file=sys.stdout, flush=False)

    Prints the values to a stream, or to sys.stdout by default.
    Optional keyword arguments:
    file:  a file-like object (stream); defaults to the current sys.stdout.
    sep:   string inserted between values, default a space.
    end:   string appended after the last value, default a newline.
    flush: whether to forcibly flush the stream.
```

还可以为用户定义的函数和类定义帮助函数输出。docstring(文档字符串)用于文档。它嵌套在三重引号中，是类、函数或模块中的第一条语句。

让我们用函数定义一个类:

## 蟒蛇 3

```
class Helper:
    def __init__(self):
        '''The helper class is initialized'''

    def print_help(self):
        '''Returns the help description'''
        print('helper description')

help(Helper)
help(Helper.print_help)
```

在运行上述程序时，我们得到如下所示的第一个帮助函数的输出:

```
Help on class Helper in module __main__:

class Helper(builtins.object)
 |  Methods defined here:
 |  
 |  __init__(self)
 |      The helper class is initialized
 |  
 |  print_help(self)
 |      Returns the help description
 |  
 |  ----------------------------------------------------------------------
 |  Data descriptors defined here:
 |  
 |  __dict__
 |      dictionary for instance variables (if defined)
 |  
 |  __weakref__
 |      list of weak references to the object (if defined)

Help on function print_help in module __main__:

print_help(self)
    Returns the help description
```

## Python 帮助()函数 docstring

文档字符串在类、方法或函数声明的正下方使用“‘三重单引号’或“‘三重双引号’”来声明。所有函数都应该有一个 docstring。

**访问文档字符串:**可以使用对象的 __doc__ 方法或使用帮助功能来访问文档字符串。

## 蟒蛇 3

```
def my_function():
    '''Demonstrates triple double quotes
    docstrings and does nothing really.'''

    return None

print("Using __doc__:")
print(my_function.__doc__)

print("Using help:")
help(my_function)
```

**输出:**

```
Using __doc__:
Demonstrates triple double quotes
    docstrings and does nothing really.
Using help:
Help on function my_function in module __main__:

my_function()
    Demonstrates triple double quotes
    docstrings and does nothing really.
```