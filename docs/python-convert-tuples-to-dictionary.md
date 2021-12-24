# Python |将元组转换为字典

> 原文:[https://www . geesforgeks . org/python-convert-元组-字典/](https://www.geeksforgeeks.org/python-convert-tuples-to-dictionary/)

数据类型之间的转换是非常流行的工具，因此了解它总是非常方便。元组列表到字典的转换在前面已经讨论过，有时，我们可能有一个键和值元组要转换到字典。让我们讨论一下实现这一点的某些方法。

**方法#1:使用字典理解**
这个任务可以使用字典理解来执行，在字典理解中，我们可以使用`enumerate()`同时遍历键和值元组，并构建所需的字典。

```py
# Python3 code to demonstrate working of
# Convert Tuples to Dictionary
# Using Dictionary Comprehension
# Note: For conversion of two tuples into a dictionary, we've to have the same length of tuples. Otherwise, we can not match all the key-value pairs

# initializing tuples
test_tup1 = ('GFG', 'is', 'best')
test_tup2 = (1, 2, 3)

# printing original tuples
print("The original key tuple is : " + str(test_tup1))
print("The original value tuple is : " + str(test_tup2))

# Using Dictionary Comprehension
# Convert Tuples to Dictionary
if len(test_tup1) == len(test_tup2):
    res = {test_tup1[i] : test_tup2[i] for i, _ in enumerate(test_tup2)}

# printing result 
print("Dictionary constructed from tuples : " + str(res))
```

**Output :**

```py
The original key tuple is : ('GFG', 'is', 'best')
The original value tuple is : (1, 2, 3)
Dictionary constructed from tuples : {'best': 3, 'is': 2, 'GFG': 1}

```