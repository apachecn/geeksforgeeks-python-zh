# Python |混合列表中词典最小的字符串

> 原文:[https://www . geeksforgeeks . org/python-按字典顺序排列-混合列表中最小的字符串/](https://www.geeksforgeeks.org/python-lexicographically-smallest-string-in-mixed-list/)

有时，我们也会遇到这样的问题:我们被给定了一个混合列表，并且需要找到列表中出现的字典序最小的字符串。这个问题可以找到它的应用日日编程。让我们讨论一下解决这个问题的某些方法。

**方法一:使用`min() + isinstance()` +列表理解**
该任务可以使用以上功能的组合来执行。在这种情况下，`min()`函数执行查找最小字符串的任务，`isinstance()`用于检查字符串。

```py
# Python3 code to demonstrate working of
# Lexicographically smallest string in mixed list
# Using min() + isinstance() + list comprehension

# initializing list
test_list = [1, 2, 4, "GFG", 5, "IS", 7, "BEST"]

# printing original list
print("The original list is : " + str(test_list))

# Lexicographically smallest string in mixed list
# Using min() + isinstance() + list comprehension
res = min(sub for sub in test_list if isinstance(sub, str))

# printing result 
print("The Lexicographically smallest string is : " + str(res))
```

**Output :**

```py
The original list is : [1, 2, 4, 'GFG', 5, 'IS', 7, 'BEST']
The Lexicographically smallest string is : BEST

```