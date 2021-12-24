# Python |获取字符串元组中的第一个索引值

> 原文:[https://www . geesforgeks . org/python-get-first-index-values-in-tuple-of-strings/](https://www.geeksforgeeks.org/python-get-first-index-values-in-tuple-of-strings/)

还有一个特殊的问题，可能并不常见，但可能会在 python 编程中使用元组时出现。由于元组是不可变的，它们很难操作，因此了解可能的变化解决方案总是有帮助的。本文解决了仅提取元组中每个字符串的第一个索引元素的问题。让我们讨论一下解决这个问题的某些方法。

**方法一:使用列表理解**

几乎每一个问题都可以用列表理解作为简单方法的简写来解决，这个问题也不例外。在这种情况下，我们只需遍历每个列表，只挑选第 0 个索引元素来构建结果列表。

```py
# Python3 code to demonstrate
# Get first index values in tuple of strings
# using list comprehension

# initializing tuple
test_tuple = ('GfG', 'for', 'Geeks')

# printing original tuple 
print("The original tuple : " + str(test_tuple))

# using list comprehsion
# Get first index values in tuple of strings
res = list(sub[0] for sub in test_tuple)

# print result
print("The first index string character list : " + str(res))
```

**Output :**

```py
The original tuple : ('GfG', 'for', 'Geeks')
The first index string character list : ['G', 'f', 'G']

```

**方法 2:使用`next() + zip()`**

这个特殊的任务也可以使用上面两个的组合以更有效的方式来执行，使用迭代器来完成这个任务。zip 函数可用于将字符串元素绑定在一起。

```py
# Python3 code to demonstrate
# Get first index values in tuple of strings
# using next() + zip()

# initializing tuple
test_tuple = ('GfG', 'for', 'Geeks')

# printing original tuple 
print("The original tuple : " + str(test_tuple))

# using next() + zip()
# Get first index values in tuple of strings
res = list(next(zip(*test_tuple)))

# print result
print("The first index string character list : " + str(res))
```

**Output :**

```py
The original tuple : ('GfG', 'for', 'Geeks')
The first index string character list : ['G', 'f', 'G']

```