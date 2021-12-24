# Python |组合元组列表中的元组

> 原文:[https://www . geesforgeks . org/python-组合-元组列表中的元组/](https://www.geeksforgeeks.org/python-combining-tuples-in-list-of-tuples/)

有时，我们可能不得不执行与元组相关的某些问题，在这些问题中，我们需要分离元组元素以与复杂元组元素(如列表)的每个元素相结合。这在我们需要将价值组合成一个整体的情况下可能会有应用。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解**
我们可以使用列表理解技术来解决这个特定的问题，在该技术中，我们可以对每个元组列表进行迭代，并将其与其他元组属性连接起来进行连接。

```
# Python3 code to demonstrate
# Combining tuples in list of tuples
# Using list comprehension

# initializing list
test_list = [([1, 2, 3], 'gfg'), ([5, 4, 3], 'cs')]

# printing original list
print("The original list : " + str(test_list))

# Using list comprehension
# Combining tuples in list of tuples
res = [ (tup1, tup2) for i, tup2 in test_list for tup1 in i ]

# print result
print("The list tuple combination : " + str(res))
```

**Output :**

> 原始列表:[([1，2，3]，' gfg ')，([5，4，3]，' cs')]
> 列表元组组合:[(1，' gfg ')，(2，' gfg ')，(3，' gfg ')，(5，' cs ')，(4，' cs ')，(3，' cs')]