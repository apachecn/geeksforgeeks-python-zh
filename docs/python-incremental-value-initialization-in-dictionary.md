# Python–字典中的增量值初始化

> 原文:[https://www . geesforgeks . org/python-增量-值-字典中初始化/](https://www.geeksforgeeks.org/python-incremental-value-initialization-in-dictionary/)

数据类型之间的相互转换非常流行，因此已经写了许多文章来演示不同类型的问题及其解决方案。本文讨论了另一个类似的问题，即把一个列表转换成字典，用 K 差作为索引增量。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用字典理解+ `enumerate()`**
使用上述函数的组合可以轻松解决这个问题，字典理解可以执行构造字典的任务，枚举函数可以用来访问索引值以及元素。

```
# Python3 code to demonstrate
# Incremental value initialization in Dictionary
# using Dictionary comprehension + enumerate()

# initializing list
test_list = ['Nikhil', 'Akshat', 'Akash', 'Manjeet']

# printing original list
print("The original list : " + str(test_list))

# initialization K 
K = 4

# using Dictionary comprehension + enumerate()
# Incremental value initialization in Dictionary
res = {val : (K * (idx + 1)) for idx, val in enumerate(test_list)}

# print result
print("The Dictionary after index keys : " + str(res))
```

**Output :**

```
The original list : ['Nikhil', 'Akshat', 'Akash', 'Manjeet']
The Dictionary after index keys : {'Akash': 12, 'Nikhil': 4, 'Manjeet': 16, 'Akshat': 8}

```