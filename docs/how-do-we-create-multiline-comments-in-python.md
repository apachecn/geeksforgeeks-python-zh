# 如何在 Python 中创建多行注释？

> 原文:[https://www . geesforgeks . org/how-do-we-create-multiline-comments-in-python/](https://www.geeksforgeeks.org/how-do-we-create-multiline-comments-in-python/)

注释是存在于代码中间的信息片段，允许开发人员向其他开发人员解释他的工作。它们使代码更易读，因此更容易调试。

## **内联评论**

内联注释是*单行注释*，与语句在同一行。它们是通过在文本前放一个“#”符号来创建的。

**语法:**

```py
# This is a single line comment
```

**示例:**

## 蟒蛇 3

```py
def my_fun():

    # prints Geeksforgeeks on the console
    print("GeeksforGeeks")

# function call
my_fun()
```

**输出:**

```py
GeeksforGeeks
```

**注意:**虽然不是必须的，但是根据 Python，#符号和注释文本之间应该有一个空格，注释和语句之间至少有 2 个空格。

## **阻止评论**

Python 中的块注释通常引用它们后面的代码，并且旨在与该代码处于同一级别。块注释的每一行都以“#”符号开始。

**语法:**

```py
# This is a block comment 
# Each line of a block comment is intended to the same level
```

**示例:**

## 蟒蛇 3

```py
def my_fun(i):

    # prints GFG on the console until i
    # is greater than zero dercrements i
    # by one on each iteration
    while i > 0:
        print("GFG")
        i = i-1

# calling my_fun
# it will print GFG 5 times on the console
my_fun(5)
```

**输出:**

```py
GFG
GFG
GFG
GFG
GFG
```

## **文档字符串**

文档字符串是在模块、函数、类或方法定义中作为第一个*语句出现的字符串。它们解释了这段代码可以实现什么，但不应该包含代码背后的逻辑信息。Docstrings 成为该对象的 __doc__ 特殊属性，这使得它们可以作为运行时对象属性进行访问。它们可以用两种方式编写:*

**1。单行文档字符串:**

**语法:**

```py
"""This is a one-line docstring."""
```

或者

```py
'''This is one-line docstring.'''
```

**示例:**

## 蟒蛇 3

```py
def my_fun():
    """Greets the user."""
    print("Hello Geek!")

# function call
my_fun()

# help function on my_fun
help(my_fun)
```

**输出:**

```py
Hello Geek!
Help on function my_fun in module __main__:

my_fun()
    Greets the user.
```

请注意，对于单行文档字符串，结束引号与开始引号在同一行。

**2。多行文档字符串:**

**语法:**

```py
"""This is a multi-line docstring.

The first line of a multi-line doscstring consist of a summary.
It is followed by one or more elaborate description.
"""
```

**示例:**

## 蟒蛇 3

```py
def my_fun(user):
    """Greets the user

    Keyword arguments:
    user -- name of user
    """
    print("Hello", user+"!")

# function call
my_fun("Geek")

# help function on my_fun
help(my_fun)
```

**输出:**

```py
Hello Geek!
Help on function my_fun in module __main__:

my_fun(user)
    Greets the user

    Keyword arguments:
    user -- name of user
```

结束引号必须单独在一行上，而开始引号可以与摘要行在同一行上。

**编写文档字符串的一些最佳实践:**

*   为了一致性，使用*三倍*双引号。
*   docstring 前后没有多余的空格。
*   与注释不同，它应该以句点结尾。