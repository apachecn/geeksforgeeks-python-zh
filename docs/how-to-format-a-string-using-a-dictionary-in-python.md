# 如何在 Python 中使用字典格式化字符串

> 原文:[https://www . geesforgeks . org/如何使用 python 字典格式化字符串/](https://www.geeksforgeeks.org/how-to-format-a-string-using-a-dictionary-in-python/)

在本文中，我们将讨论如何使用 Python 中的字典来格式化字符串。

## **方法 1:** 通过使用 **[str.format()](https://www.geeksforgeeks.org/python-string-format-method/)** 功能

**str.format()** 函数用于使用字典格式化指定的字符串。

> **语法:**字符串。格式(值)
> 
> **参数:**该函数接受如下所示的参数:
> 
> *   **值:**这是指定的值，可以是整数、浮点数字常量、字符串、字符甚至变量。
> 
> **返回值:**这个函数使用字典返回一个格式化的字符串。

### **示例:使用字典格式化字符串**

## 蟒蛇 3

```py
# Python program to illustrate the
# formatting of a string using a dictionary

# Initializing a value
value = {"Company": "GeeksforGeeks", 
         "Department": "Computer Science"}

# Calling the .format() function
# over the above given value
print("{Company} is a {Department} Portal.".format(**value))
```

**输出:**

```py
GeeksforGeeks is a Computer Science Portal.
```

## **方法二:**使用 [%算子](https://www.geeksforgeeks.org/string-formatting-in-python-using/)

%–格式化是 Python 提供的一项功能，可以使用%运算符进行访问。这类似于 c 语言中的 printf style 函数。在这种方法中，使用字典，其中您需要在%和转换字符之间的括号中提供键。

### **示例:使用字典格式化字符串**

## 蟒蛇 3

```py
# Python program to illustrate the
# formatting of a string using a dictionary

# String formatting in dictionary
print('%(Company)s is a %(Department)s Portal.'  
          %{'Company': "GFG", 'Department': "CS"})
```

**输出:**

```py
GFG is a CS Portal.
```