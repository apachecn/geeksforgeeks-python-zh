# Python |删除所有出现的字符

> 原文:[https://www . geesforgeks . org/python-删除所有出现的字符/](https://www.geeksforgeeks.org/python-deleting-all-occurrences-of-character/)

如今，字符串操作在 Python 中非常流行，由于它的不可变特性，有时，知道它的工作和黑客行为变得更加重要。这篇特别的文章解决了从字符串中删除所有字符的问题。让我们讨论一下实现这一目标的方法。

**方法#1:使用`translate()`**
通常这个功能是用来将某个特定的字符转换成其他的字符。通过将结果删除字符转换为“无”，此功能可以执行此任务。该函数仅适用于 Python2

```
# Python code to demonstrate working of
# Deleting all occurrences of character
# Using translate()

# initializing string 
test_str = "GeeksforGeeks"

# initializing removal character
rem_char = "e"

# printing original string 
print("The original string is : " + str(test_str))

# Using translate()
# Deleting all occurrences of character
res = test_str.translate(None, rem_char)

# printing result 
print("The string after character deletion : " + str(res))
```

**Output :**

```
The original string is : GeeksforGeeks
The string after character deletion : GksforGks

```