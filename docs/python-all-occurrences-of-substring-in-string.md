# Python |字符串中出现的所有子字符串

> 原文:[https://www . geesforgeks . org/python-字符串中所有出现的子字符串/](https://www.geeksforgeeks.org/python-all-occurrences-of-substring-in-string/)

在处理字符串时，我们经常会遇到处理子字符串的问题。这可能包括查找字符串中特定子字符串的所有位置的问题。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ `startswith()`**
这个任务可以使用两个功能来执行。startswith 函数主要执行获取子字符串起始索引的任务，列表理解用于遍历整个目标字符串。

```
# Python3 code to demonstrate working of
# All occurrences of substring in string
# Using list comprehension + startswith()

# initializing string 
test_str = "GeeksforGeeks is best for Geeks"

# initializing substring
test_sub = "Geeks"

# printing original string 
print("The original string is : " + test_str)

# printing substring 
print("The substring to find : " + test_sub)

# using list comprehension + startswith()
# All occurrences of substring in string 
res = [i for i in range(len(test_str)) if test_str.startswith(test_sub, i)]

# printing result 
print("The start indices of the substrings are : " + str(res))
```

**Output :**

```
The original string is : GeeksforGeeks is best for Geeks
The substring to find : Geeks
The start indices of the substrings are : [0, 8, 26]

```