# Python |检查字符串是否是有效的标识符

> 原文:[https://www . geesforgeks . org/python-检查字符串是否是有效标识符/](https://www.geeksforgeeks.org/python-check-if-string-is-a-valid-identifier/)

给定一个字符串，编写一个 Python 程序来检查它是否是一个有效的标识符。
一个**标识符**必须以字母或下划线开头，它不能以数字或任何其他特殊字符开头，而且数字可以在其后。

```py
gfg : valid identifier
123 : invalid identifier
_abc12 : valid identifier
#abc : invalid identifier
```

在这个程序中，我们使用的是 regex 模块的 search()方法。
**re.search() :** 这个方法要么返回 None(如果模式不匹配)，要么返回 re。包含字符串匹配部分信息的 MatchObject。此方法在第一次匹配后停止，因此这比提取数据更适合测试正则表达式。
我们来看看 Python 程序，判断字符串是否是标识符。

## 蟒蛇 3

```py
# Python program to identify the identifier

# import re module

# re module provides support
# for regular expressions
import re

# Make a regular expression
# for identify valid identifier
regex = '^[A-Za-z_][A-Za-z0-9_]*'

# Define a function for
# identifying valid identifier
def check(string):

     # pass the regular expression
     # and the string in search() method
    if(re.search(regex, string)):
        print("Valid Identifier")

    else:
        print("Invalid Identifier")

# Driver Code
if __name__ == '__main__' :

    # Enter the string
    string = "gfg"

    # calling run function
    check(string)

    string = "123"
    check(string)

    string = "#abc"
    check(string)
```

**输出:**

```py
Valid Identifier
Invalid Identifier
Invalid Identifier
```