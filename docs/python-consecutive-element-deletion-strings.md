# Python–连续元素删除字符串

> 原文:[https://www . geesforgeks . org/python-continuous-element-delete-strings/](https://www.geeksforgeeks.org/python-consecutive-element-deletion-strings/)

有时，在使用 Python 时，我们可能会遇到一个问题，即我们有一个字符串，并且希望在一次删除一个连续元素后提取所有可能的单词组合。这在许多领域都有应用。让我们讨论执行这项任务的某些方法。

**方法一:使用列表理解+列表切片**
这是可以执行这个任务的方式之一。在这种情况下，我们迭代列表的元素，并继续使用连续列表切片创建新的字符串。

```
# Python3 code to demonstrate working of 
# Consecutive element deletion strings
# Using list comprehension + list slicing

# initializing string
test_str = 'Geeks4Geeks'

# printing original string
print("The original string is : " + str(test_str))

# Consecutive element deletion strings
# Using list comprehension + list slicing
res =  [test_str[: idx] + test_str[idx + 1:] 
             for idx in range(len(test_str))]

# printing result 
print("Consecutive Elements removal list : " + str(res)) 
```

**Output :**

> 原字符串为:Geeks4Geeks
> 连续元素移除列表:['eeks4Geeks '，' Geks4Geeks '，' Gees4Geeks '，' gees4 geeks '，' gees4 geeks '，' gees4 geeks '，' gees4 geeks '，' gees4 geeks ']