# Python 文档字符串

> 原文:[https://www.geeksforgeeks.org/python-docstrings/](https://www.geeksforgeeks.org/python-docstrings/)

Python 文档字符串(或 docstrings)提供了一种将文档与 Python 模块、函数、类和方法相关联的便捷方式。

它是在源代码中指定的，像注释一样，用来记录特定的代码段。与传统的源代码注释不同，docstring 应该描述函数做什么，而不是如何做。

**docstring 应该是什么样子？**

*   文档字符串行应以大写字母开头，以句点结尾。
*   第一行应该是简短的描述。
*   如果文档字符串中有更多的行，第二行应该是空白的，从视觉上将摘要与描述的其余部分分开。
*   以下几行应该是描述对象的调用约定、副作用等的一个或多个段落。

**声明文档字符串:**在类、方法或函数声明的正下方，使用“‘三重单引号’””或“‘三重双引号’”来声明文档字符串。所有函数都应该有一个 docstring。

**访问文档字符串:**可以使用对象的 __doc__ 方法或使用帮助功能来访问文档字符串。
下面的例子演示了如何声明和访问文档字符串。

**示例 1:** 使用三重单引号

```py
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

```py
Using __doc__:
Demonstrates triple double quotes
    docstrings and does nothing really.
Using help:
Help on function my_function in module __main__:

my_function()
    Demonstrates triple double quotes
    docstrings and does nothing really.

```

**示例 2:** 使用三倍双引号

```py
def my_function():
    """Demonstrates triple double quotes
    docstrings and does nothing really."""

    return None

print("Using __doc__:")
print(my_function.__doc__)

print("Using help:")
help(my_function)
```

**输出:**

```py
Using __doc__:
Demonstrates triple double quotes
    docstrings and does nothing really.
Using help:
Help on function my_function in module __main__:

my_function()
    Demonstrates triple double quotes
    docstrings and does nothing really.

```

**单行文档字符串**

顾名思义，一行文档字符串可以放在一行中。它们用于明显的情况。结束引号和开始引号在同一行。这对单线来说更好看。
例如:

```py
def power(a, b):
    """Returns arg1 raised to power arg2."""

    return a**b

print(power.__doc__)
```

**输出:**

```py
Returns arg1 raised to power arg2.

```

**多行文档字符串**

多行文档字符串由一个摘要行组成，就像单行文档字符串一样，后面是一个空行，后面是更详细的描述。摘要行可能与开始报价在同一行，也可能在下一行。
下面的示例显示了一个多行文档字符串。

```py
def my_function(arg1):
    """
    Summary line.

    Extended description of function.

    Parameters:
    arg1 (int): Description of arg1

    Returns:
    int: Description of return value

    """

    return arg1

print(my_function.__doc__)
```

**输出:**

```py
    Summary line.
    Extended description of function.
    Parameters:
    arg1 (int): Description of arg1

    Returns:
    int: Description of return value

```

**文档字符串中的缩进**

整个文档字符串的缩进与第一行的引号一样。Docstring 处理工具将从 docstring 的第二行和后面的行中去除统一的缩进量，等于第一行之后所有非空白行的最小缩进量。docstring 第一行中的任何缩进(即，直到第一个换行符)都是不重要的，并且会被移除。文档字符串中后面几行的相对缩进被保留。

**类中的文档字符串**

让我们举一个例子来说明如何为一个类及其方法编写文档字符串。**帮助**用于访问文档字符串。

```py
class ComplexNumber:
    """
    This is a class for mathematical operations on complex numbers.

    Attributes:
        real (int): The real part of complex number.
        imag (int): The imaginary part of complex number.
    """

    def __init__(self, real, imag):
        """
        The constructor for ComplexNumber class.

        Parameters:
           real (int): The real part of complex number.
           imag (int): The imaginary part of complex number.   
        """

    def add(self, num):
        """
        The function to add two Complex Numbers.

        Parameters:
            num (ComplexNumber): The complex number to be added.

        Returns:
            ComplexNumber: A complex number which contains the sum.
        """

        re = self.real + num.real
        im = self.imag + num.imag

        return ComplexNumber(re, im)

help(ComplexNumber)  # to access Class docstring
help(ComplexNumber.add)  # to access method's docstring
```

输出:

```py
Help on class ComplexNumber in module __main__:

class ComplexNumber
 |  This is a class for mathematical operations on complex numbers.
 |  
 |  Attributes:
 |          real (int): The real part of complex number.
 |          imag (int): The imaginary part of complex number.
 |  
 |  Methods defined here:
 |  
 |  __init__(self, real, imag)
 |      The constructor for ComplexNumber class.
 |      
 |      Parameters:
 |      real (int): The real part of complex number.
 |      imag (int): The imaginary part of complex number.
 |  
 |  add(self, num)
 |      The function to add two Complex Numbers.
 |      
 |      Parameters:
 |              num (ComplexNumber): The complex number to be added.
 |      
 |      Returns:
 |              ComplexNumber: A complex number which contains the sum.

Help on method add in module __main__:

add(self, num) unbound __main__.ComplexNumber method
    The function to add two Complex Numbers.

    Parameters:
            num (ComplexNumber): The complex number to be added.

    Returns:
            ComplexNumber: A complex number which contains the sum.

```

**Python 注释和文档字符串的区别**

你们一定对 Python 文档字符串有所了解，但是你们有没有想过 Python 注释和文档字符串有什么区别。让我们看看他们。

[Python 注释](https://www.geeksforgeeks.org/comments-in-python/)是开发人员提供的有用信息，用于让读者理解源代码。它解释了代码中使用的逻辑或部分逻辑。使用`#`符号书写。

**示例:**

```py
# Python program to demonstrate comments
print("GFG")
```

**输出:**

```py
GFG
```

而上面提到的 Python 文档字符串提供了一种将文档与 Python 模块、函数、类和方法相关联的便捷方式。

本文由 **Mayank Agrawal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。