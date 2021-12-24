# Python–提取大写字符

> 原文:[https://www . geesforgeks . org/python-extract-大写-characters/](https://www.geeksforgeeks.org/python-extract-upper-case-characters/)

有时，在处理字符串时，我们担心字符串的区分大小写，可能需要在一个长字符串中只获取特定大小写的字符。让我们讨论从字符串中只提取大写字母的某些方法。

**方法#1:使用列表理解+ `isupper()`**
列表理解和 isupper 功能可用于执行此特定任务。列表理解主要用于遍历列表，isupper 函数检查大写字符。

```py
# Python3 code to demonstrate working of
# Extract Upper Case Characters 
# Using list comprehension + isupper()

# initializing string 
test_str = "GeeksForGeeKs"

# printing original string 
print("The original string is : " + str(test_str))

# Extract Upper Case Characters 
# Using list comprehension + isupper()
res = [char for char in test_str if char.isupper()]

# printing result 
print("The uppercase characters in string are : " + str(res))
```

**Output :**

```py
The original string is : GeeksForGeeKs
The uppercase characters in string are : ['G', 'F', 'G', 'K']

```