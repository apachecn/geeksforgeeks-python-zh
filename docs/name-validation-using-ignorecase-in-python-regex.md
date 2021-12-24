# 在 Python Regex 中使用 IGNORECASE 进行名称验证

> 原文:[https://www . geesforgeks . org/name-validation-using-ignore case-in-python-regex/](https://www.geeksforgeeks.org/name-validation-using-ignorecase-in-python-regex/)

在本文中，我们将学习如何使用 Python Regex 来使用 IGNORECASE 验证名称。

**`re.IGNORECASE` :** 该标志允许正则表达式与给定字符串进行不区分大小写的匹配，即像`[A-Z]`这样的表达式也将匹配小写字母。一般来说，它作为可选参数传递给`re.compile()`。

让我们考虑一个表单的例子，其中用户被要求输入他们的名字，我们必须使用正则表达式来验证它。输入名称的格式如下:

*   先生或夫人或女士(任何一个)，后面跟着一个空格
*   名字，后跟一个空格
*   中间名(可选)，后跟一个空格
*   姓氏(可选)

**示例:**

```
Input : Mr. Albus Severus Potter 
Output : Valid

Input : Lily and Mr. Harry Potter
Output : Invalid
```

**注意:**由于我们使用的是 IGNORECASE 标志，因此名字、第二名和姓氏的第一个字符可以是大写，也可以不是大写。

下面是 Python 代码–

```
# Python program to validate name using IGNORECASE in RegEx

# Importing re package
import re

def validating_name(name):

    # RegexObject = re.compile( Regular expression, flag )
    # Compiles a regular expression pattern into a regular expression object
    regex_name = re.compile(r'^(Mr\.|Mrs\.|Ms\.) ([a-z]+)( [a-z]+)*( [a-z]+)*{content}apos;, 
              re.IGNORECASE)

    # RegexObject is matched with the desired 
    # string using search function
    # In case a match is found, search() returns
    # MatchObject Instance
    # If match is not found, it return None
    res = regex_name.search(name)

    # If match is found, the string is valid
    if res: print("Valid")

    # If match is not found, string is invalid
    else: print("Invalid")

# Driver Code
validating_name('Mr. Albus Severus Potter')
validating_name('Lily and Mr. Harry Potter')
validating_name('Mr. Cedric')
validating_name('Mr. sirius black')
```

**输出:**

```
Valid
Invalid
Valid
valid

```