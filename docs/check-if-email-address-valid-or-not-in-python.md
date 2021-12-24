# 检查 Python 中的电子邮件地址是否有效

> 原文:[https://www . geesforgeks . org/check-if-email-address-valid-or-not-in-python/](https://www.geeksforgeeks.org/check-if-email-address-valid-or-not-in-python/)

**先决条件:**[Python 中的 Regex](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/)

给定一个字符串，编写一个 Python 程序来检查该字符串是否是有效的电子邮件地址。
电子邮件是由@符号分隔成两部分的字符串(ASCII 字符的子集)，一个是“personal_info”，一个是域，即 personal_info@domain。

**示例:**

```
Input:  ankitrai326@gmail.com
Output: Valid Email

Input: my.ownsite@ourearth.org
Output: Valid Email

Input: ankitrai326.com
Output: Invalid Email 
```

在这个程序中，我们使用的是 re 模块的 search()方法。所以让我们看看对它的描述。
**re.search() :** 这个方法要么返回 None(如果模式不匹配)，要么返回 re。MatchObject 包含关于字符串匹配部分的信息。此方法在第一次匹配后停止，因此这比提取数据更适合测试正则表达式。

让我们看看验证电子邮件的 Python 程序:

## 蟒蛇 3

```
# Python program to validate an Email

# import re module

# re module provides support
# for regular expressions
import re

# Make a regular expression
# for validating an Email
regex = r'\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Z|a-z]{2,}\b'

# Define a function for
# for validating an Email

def check(email):

    # pass the regular expression
    # and the string into the fullmatch() method
    if(re.fullmatch(regex, email)):
        print("Valid Email")

    else:
        print("Invalid Email")

# Driver Code
if __name__ == '__main__':

    # Enter the email
    email = "ankitrai326@gmail.com"

    # calling run function
    check(email)

    email = "my.ownsite@our-earth.org"
    check(email)

    email = "ankitrai326.com"
    check(email)
```

**Output:** 

```
Valid Email
Valid Email
Invalid Email
```