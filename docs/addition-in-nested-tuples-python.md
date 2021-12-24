# 嵌套元组中的加法–Python

> 原文:[https://www . geesforgeks . org/嵌套元组加法-python/](https://www.geeksforgeeks.org/addition-in-nested-tuples-python/)

有时，在处理记录时，我们会遇到一个问题，即我们需要执行元组元素的索引方式添加。这可能会变得复杂，因为元组元素是元组，内部元素也是元组。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用`zip()` +嵌套生成器表达式**

上述功能的组合可用于执行任务。在本文中，我们使用`zip()`来组合元组中的元素。迭代和求和逻辑由生成器表达式提供。

```py
# Python3 code to demonstrate working of
# Addition in nested tuples
# using zip() + nested generator expression

# initialize tuples
test_tup1 = ((1, 3), (4, 5), (2, 9), (1, 10))
test_tup2 = ((6, 7), (3, 9), (1, 1), (7, 3))

# printing original tuples
print("The original tuple 1 : " + str(test_tup1))
print("The original tuple 2 : " + str(test_tup2))

# Addition in nested tuples
# using zip() + nested generator expression
res = tuple(tuple(a + b for a, b in zip(tup1, tup2))\
      for tup1, tup2 in zip(test_tup1, test_tup2))

# printing result
print("The resultant tuple after summation : " + str(res))
```

**Output :**

```py
The original tuple 1 : ((1, 3), (4, 5), (2, 9), (1, 10))
The original tuple 2 : ((6, 7), (3, 9), (1, 1), (7, 3))
The resultant tuple after summation : ((7, 10), (7, 14), (3, 10), (8, 13))

```

**方法 2:使用`isinstance() + zip()` +循环+列表理解**
以上功能的组合可以用来执行这个特定的任务。在这种情况下，我们检查嵌套类型并执行递归。这种方法可以提供 1 级以上嵌套的灵活性。

```py
# Python3 code to demonstrate working of
# Addition in nested tuples
# using isinstance() + zip() + loop + list comprehension

# function to perform task 
def tup_sum(tup1, tup2):
    if isinstance(tup1, (list, tuple)) and isinstance(tup2, (list, tuple)):
       return tuple(tup_sum(x, y) for x, y in zip(tup1, tup2))
    return tup1 + tup2

# initialize tuples
test_tup1 = ((1, 3), (4, 5), (2, 9), (1, 10))
test_tup2 = ((6, 7), (3, 9), (1, 1), (7, 3))

# printing original tuples
print("The original tuple 1 : " + str(test_tup1))
print("The original tuple 2 : " + str(test_tup2))

# Addition in nested tuples
# using isinstance() + zip() + loop + list comprehension
res = tuple(tup_sum(x, y) for x, y in zip(test_tup1, test_tup2))

# printing result
print("The resultant tuple after summation : " + str(res))
```

**Output :**

```py
The original tuple 1 : ((1, 3), (4, 5), (2, 9), (1, 10))
The original tuple 2 : ((6, 7), (3, 9), (1, 1), (7, 3))
The resultant tuple after summation : ((7, 10), (7, 14), (3, 10), (8, 13))

```