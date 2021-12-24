# Python–事件之间的距离

> 原文:[https://www . geesforgeks . org/python-出现间隔距离/](https://www.geeksforgeeks.org/python-distance-between-occurrences/)

有时，在使用 Python Strings 时，我们可能会有一个任务，需要找到特定字符出现之间的索引差异。这可以应用于日常编程等领域。让我们讨论完成这项任务的某些方法。

**方法一:使用`index()`**
这是我们可以解决这个问题的方法之一。在这种情况下，我们使用 index()的幂来获得第 n 个出现的索引，并用初始出现减去。

```
# Python3 code to demonstrate working of 
# Distance between occurrences
# Using index()

# initializing string
test_str = 'geeksforgeeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing K 
K = 'k'

# Distance between occurrences
# Using index()
res = test_str.index(K, test_str.index(K) + 1) - test_str.index(K)

# printing result 
print("The character occurrence difference is : " + str(res)) 
```

**Output :**

```
The original string is : geeksforgeeks
The character occurrence difference is : 8

```