# 如何用 Python3 写评论？

> 原文:[https://www . geesforgeks . org/how-write-comments-in-python 3/](https://www.geeksforgeeks.org/how-to-write-comments-in-python3/)

注释是添加到程序中的文本注释，用于提供关于源代码的解释性信息。它们在编程语言中用于记录程序，提醒程序员他们刚刚对代码做了什么棘手的事情，并帮助后一代理解和维护代码。编译器认为这些是不可执行的语句。由于注释不执行，当您运行一个程序时，您将在输出中看不到注释的任何指示。
**语法:**
哈希(#)符号表示 Python 中注释的开始。

```py
# This is a comment in Python
```

**示例:**

## 蟒蛇 3

```py
# This is the syntax of a comment in Python
print("GFG")

# Comments dont have any effect on the interpreter / output
```

**输出:**

```py
GFG
```

注释应该在注释代码的同一缩进处进行。

## 蟒蛇 3

```py
# This comment has no indent
def GFG():

  # Since, this comment is inside a function
  # It would have indent same as the function body
  print("GeeksforGeeks")

  for i in range(1, 2):

    # Be careful of indentation
    # This comment is inside the body of for loop
    print("Welcome to Comments in Python")

# This comment is again outside the body
# of function so it wont have any indent.

print("Hello !!")
GFG()
```

**Output**

```py
Hello!!
GeeksforGeeks
Welcome to Comments in Python
```

#### 注释类型:

**1。单行注释**:以“#”和空格开头的注释在 Python 中称为单行注释。这些注释只能延伸到一行，并且是 Python 中注释的唯一方式。例如

```py
# This a single line comment.
```

**2。多行(块)注释**:与其他编程语言不同，Python 不支持开箱即用的多行注释块。然而，我们可以使用连续的#单行注释来注释掉多行代码。一些块注释的例子-

```py
# This type of comments can serve
# both as a single-line as well
# as multi-line (block) in Python.
```

**3。内联样式注释**:内联注释出现在语句的同一行，跟随代码本身。通常，内联注释如下所示:

```py
x = 3        # This is called an inline comment

a = b + c    # Adding value of 'b' and 'c' to 'a'
```

**4。文档字符串注释:** Python 文档字符串(或文档字符串)提供了一种将文档与 Python 模块、函数、类和方法相关联的便捷方式。它是在源代码中指定的，像注释一样，用来记录特定的代码段。与传统的源代码注释不同，docstring 应该描述函数做什么，而不是如何做。
T3】例:

## 蟒蛇 3

```py
def my_function():
    """Demonstrates docstrings and does nothing really."""

    return None

print("Using __doc__:")
print(my_function.__doc__)

print("Using help:")
help(my_function)
```

**输出:**

```py
Using __doc__:
Demonstrates docstrings and does nothing really.
Using help:
Help on function my_function in module __main__:

my_function()
    Demonstrates docstrings and does nothing really.
```

#### 注释的优点和用途:

*   **计划和回顾:**在评论中，我们可以写下在编写源代码之前计划好的伪代码。伪代码是自然语言和高级编程语言的混合。这有助于更容易地检查源代码，因为伪代码比程序更容易理解。

## 蟒蛇 3

```py
# This function is adding two given numbers
def addition(a, b):

  # storing the sum of given numbers in 'c'.
  c = a + b

  # returning the sum here
  return c

# passing the value of a and b to addition()
a = 10
b = 3
sum = addition(a, b)

# printing the sum calculated by above function
print(sum)
```

**输出:**

```py
13
```

*   **调试**:蛮力法是一种常见的调试方法。在这种方法中，在整个程序中插入打印语句来打印中间值，希望一些打印值有助于识别错误。在进行调试之后，我们对那些打印语句进行注释。因此注释也用于调试。

## 蟒蛇 3

```py
a = 12

if(a == 12):
  print("True")

# elif(a == 0):
  # print("False")

else:
  print("Debugging")
```

**输出:**

```py
True
```