# Python 注释

> 原文:[https://www.geeksforgeeks.org/python-comments/](https://www.geeksforgeeks.org/python-comments/)

**Python 中的注释**是程序执行过程中被编译器忽略的代码行。注释增强了代码的可读性，并帮助程序员非常仔细地理解代码。Python 中有三种类型的注释–

*   单行注释
*   多行注释
*   文档字符串注释

### **示例:**Python 中的注释

## 蟒蛇 3

```
# Python program to demonstrate comments

# sample comment
name = "geeksforgeeks"
print(name)
```

**输出:**

```
geeksforgeeks
```

在上面的例子中，可以看到编译器在程序执行过程中忽略了注释。

**注释一般用于以下目的:**

*   代码可读性
*   项目代码或元数据的说明
*   阻止代码的执行
*   包括资源

## Python 中的注释类型

Python 中有三种主要的注释。它们是:

## 单线**备注**

Python 单行注释以没有白色空格的 hashtag 符号(#)开始，一直持续到行尾。如果注释超过一行，那么在下一行放一个标签并继续注释。Python 的单行注释对于提供变量、函数声明和表达式的简短解释非常有用。请参见下面演示单行注释的代码片段:

**示例:**

## 蟒蛇 3

```
# Print “GeeksforGeeks !” to console
print("GeeksforGeeks")
```

**Output**

```
GeeksforGeeks

```

## **多行评论**

Python 不提供[多行注释](https://www.geeksforgeeks.org/multiline-comments-in-python/)的选项。然而，我们可以通过不同的方式编写多行注释。

### 使用多个标签(#)

我们可以使用多个 hashtags)在 Python 中编写多行注释。每一行都将被视为单行注释。

### **示例:使用多个**标签的多行注释 **(#)**

## 蟒蛇 3

```
# Python program to demonstrate
# multiline comments
print("Multiline comments")
```

**Output**

```
Multiline comments

```

### 使用字符串文字

Python 忽略了没有赋给变量的字符串文字，所以我们可以将这些字符串文字用作注释**。**

### **例 1:**

## 蟒蛇 3

```
'This will be ignored by Python'
```

在执行上述代码时，我们可以看到不会有任何输出，因此我们使用带三引号(" ")的字符串作为多行注释。

### 示例 2:使用字符串文字的多行注释

## 蟒蛇 3

```
""" Python program to demonstrate
 multiline comments"""
print("Multiline comments")
```

**Output**

```
Multiline comments

```

## **Python 文档字符串**

[**Python 文档字符串**](https://www.geeksforgeeks.org/python-docstrings/) 是出现在函数后面的带三重引号的字符串。它用于将已经编写的文档与 Python 模块、函数、类和方法相关联。它被添加到函数、模块或类的正下方，以描述它们的功能。在 Python 中，文档字符串通过 __doc__ 属性变得可用。

**示例:**

## 蟒蛇 3

```
def multiply(a, b):
    """Multiplies the value of a and b"""
    return a*b

# Print the docstring of multiply function
print(multiply.__doc__)
```

**输出:**

```
Multiplies the value of a and b
```