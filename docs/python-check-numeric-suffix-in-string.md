# Python |检查字符串中的数字后缀

> 原文:[https://www . geesforgeks . org/python-check-numeric-后缀 in-string/](https://www.geeksforgeeks.org/python-check-numeric-suffix-in-string/)

有时，在编程时，我们可能会遇到这样的问题，我们需要检查是否有任何字符串以数字结尾，即它有一个数字后缀。这个问题可能发生在网站开发领域。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用正则表达式**
这个问题可以使用正则表达式解决。如果需要，搜索和分组功能可以执行搜索后缀字符串和打印数字的任务。

```
# Python3 code to demonstrate working of
# Check Numeric Suffix in String 
# Using regex
import re

# initializing string 
test_str = "Geeks4321"

# printing original string 
print("The original string is : " + str(test_str))

# Using regex
# Check Numeric Suffix in String
res = re.search(r'\d+{content}apos;, test_str)

# printing result 
print("Does string contain suffix number ? : " + str(bool(res)))
```

**Output :**

```
The original string is : Geeks4321
Does string contain suffix number ? : True

```