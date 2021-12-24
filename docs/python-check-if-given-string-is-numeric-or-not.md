# Python |检查给定字符串是否为数字

> 原文:[https://www . geesforgeks . org/python-check-if-given-string-is-numeric-or-not/](https://www.geeksforgeeks.org/python-check-if-given-string-is-numeric-or-not/)

给定一个字符串，编写一个 Python 程序来检查该字符串是否是数字。
**例:**

```py
Input:  28
Output: digit

Input: a
Output: not a digit. 

Input: 21ab
Output: not a digit. 
```

**代码#1:** 使用 Python 正则表达式
**re.search() :** 该方法要么返回 None(如果模式不匹配)，要么返回 re。包含字符串匹配部分信息的 MatchObject。此方法在第一次匹配后停止，因此这比提取数据更适合测试正则表达式。

## 蟒蛇 3

```py
# Python program to identify the Digit

# import re module

# re module provides support
# for regular expressions
import re

# Make a regular expression
# for identifying a digit
regex = '^[0-9]+{content}apos;

# Define a function for
# identifying a Digit
def check(string):

     # pass the regular expression
     # and the string in search() method
    if(re.search(regex, string)):
        print("Digit")

    else:
        print("Not a Digit")

# Driver Code
if __name__ == '__main__' :

    # Enter the string
    string = "28"

    # calling run function
    check(string)

    string = "a"
    check(string)

    string = "21ab"
    check(string)

    string = "12ab12"
    check(string)
```

**Output:** 

```py
Digit
Not a Digit
Not a Digit
Not a Digit
```

**代码#2:** 使用[字符串. isnumeric()](https://www.geeksforgeeks.org/python-string-isnumeric-application/) 功能

## 蟒蛇 3

```py
# Python code to check if string is numeric or not

# checking for numeric characters
string = '123ayu456'
print(string.isnumeric())

string = '123456'
print(string.isnumeric())
```

**Output:** 

```py
False
True
```