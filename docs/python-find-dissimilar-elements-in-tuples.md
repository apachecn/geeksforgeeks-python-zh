# Python |查找元组中的不同元素

> 原文:[https://www . geesforgeks . org/python-find-异种元素-in-tuples/](https://www.geeksforgeeks.org/python-find-dissimilar-elements-in-tuples/)

有时，在使用元组时，我们可能会遇到这样的问题，即我们需要两个记录的不同特征。这种类型的应用可以出现在数据科学领域。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用`set() + "^" operator`**

这个任务可以使用集合上异或运算符提供的对称差分功能来执行。设置的转换由`set()`完成。

```py
# Python3 code to demonstrate working of
# Dissimilar elements in tuples
# Using set() + "^" operator

# initialize tuples
test_tup1 = (3, 4, 5, 6)
test_tup2 = (5, 7, 4, 10)

# printing original tuples
print("The original tuple 1 : " + str(test_tup1))
print("The original tuple 2 : " + str(test_tup2))

# Dissimilar elements in tuples
# Using set() + "^" operator
res = tuple(set(test_tup1) ^ set(test_tup2))

# printing result
print("The Dissimilar elements from tuples are : " + str(res))
```

**Output :**

```py
The original tuple 1 : (3, 4, 5, 6)
The original tuple 2 : (5, 7, 4, 10)
The Dissimilar elements from tuples are : (3, 6, 7, 10)

```

**方法 2:使用`symmetric_difference() + set()`**

这个方法类似于上面的方法，不同的是，我们使用内置函数来执行过滤不同元素的任务，而不是异或运算符。

```py
# Python3 code to demonstrate working of
# Dissimilar elements in tuples
# Using symmetric_difference() + set()

# initialize tuples
test_tup1 = (3, 4, 5, 6)
test_tup2 = (5, 7, 4, 10)

# printing original tuples
print("The original tuple 1 : " + str(test_tup1))
print("The original tuple 2 : " + str(test_tup2))

# Dissimilar elements in tuples
# Using symmetric_difference() + set()
res = tuple(set(test_tup1).symmetric_difference(set(test_tup2)))

# printing result
print("The Dissimilar elements from tuples are : " + str(res))
```

**Output :**

```py
The original tuple 1 : (3, 4, 5, 6)
The original tuple 2 : (5, 7, 4, 10)
The Dissimilar elements from tuples are : (3, 6, 7, 10)

```