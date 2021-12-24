# Python |检查字符串是否重复

> 原文:[https://www . geesforgeks . org/python-check-if-string-repeats-self/](https://www.geeksforgeeks.org/python-check-if-string-repeats-itself/)

在处理字符串时，很多时候，我们会遇到一个用例，在这个用例中，我们需要找到一个字符串中是否有重复的子字符串，这个子字符串在整个字符串中重复，因此是根子字符串的倍数。让我们讨论获取字符串的根子串的某些方法。

**方法#1:使用列表理解+蛮力**
我们可以使用选择性切片和蛮力的方式来执行这个任务。这是一种寻找字符串的简单方法，在这种方法中，我们试图通过重复分割字符串来获得根字符串。

```py
# Python3 code to demonstrate working of
# Check if string repeats itself
# Using List comprehension + Brute Force

# initializing string 
test_str = "GeeksforGeeksGeeksforGeeksGeeksforGeeks"

# printing original string 
print("The original string is : " + test_str)

# using List comprehension + Brute Force
# Check if string repeats itself
res = None
for i in range(1, len(test_str)//2 + 1):
    if (not len(test_str) % len(test_str[0:i]) and test_str[0:i] *
           (len(test_str)//len(test_str[0:i])) == test_str):
        res = test_str[0:i]

# printing result 
print("The root substring of string : " + res)
```

**Output :**

```py
The original string is : GeeksforGeeksGeeksforGeeksGeeksforGeeks
The root substring of string : GeeksforGeeks

```