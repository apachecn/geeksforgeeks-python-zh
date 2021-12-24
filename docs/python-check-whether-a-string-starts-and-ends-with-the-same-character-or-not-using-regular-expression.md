# Python–检查字符串是否以相同的字符开始和结束(使用正则表达式)

> 原文:[https://www . geesforgeks . org/python-check-字符串是否以相同字符开头和结尾-使用或不使用-正则表达式/](https://www.geeksforgeeks.org/python-check-whether-a-string-starts-and-ends-with-the-same-character-or-not-using-regular-expression/)

给定一个字符串。任务是写一个[正则表达式](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/)来检查一个字符串是否以相同的字符开始和结束。
**例:**

```py
Input :  
abba
Output :  
Valid

Input :  
a
Output :  
Valid

Input :  
abc
Output :  
Invalid
```

**解:**
输入可分为 2 种情况:

*   **单个字符串:**所有单个字符串满足以同一字符开始和结束的条件。只有 1 个字符的字符串的正则表达式是-

```py
'^[a-z]{content}apos;
```

*   **多字符串:**这里需要检查第一个和最后一个字符是否相同。我们使用\1 来完成。正则表达式将是-

```py
'^([a-z]).*\1{content}apos;
```

这两个正则表达式可以使用|
组合

```py
'^[a-z]$|^([a-z]).*\1{content}apos;
```

在这个程序中，我们将使用 re 模块的 search()方法。
下面是实现。

## 蟒蛇 3

```py
# Python program to check if a string starts
# and ends with the same character

# import re module as it provides
# support for regular expressions
import re

# the regular  expression
regex = r'^[a-z]$|^([a-z]).*\1{content}apos;

# function for checking the string
def check(string):

    # pass the regular expression
    # and the string in the search() method
    if(re.search(regex, string)): 
        print("Valid") 
    else: 
        print("Invalid") 

if __name__ == '__main__' :

    sample1 = "abba"
    sample2 = "a"
    sample3 = "abcd"

    check(sample1)
    check(sample2)
    check(sample3)
```

**输出:**

```py
Valid
Valid
Invalid
```