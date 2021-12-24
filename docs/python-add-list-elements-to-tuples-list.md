# Python–向元组列表添加列表元素

> 原文:[https://www . geesforgeks . org/python-add-list-elements-to-tuples-list/](https://www.geeksforgeeks.org/python-add-list-elements-to-tuples-list/)

有时，在使用 Python 元组时，我们会遇到一个问题，即我们需要将特定列表的所有元素添加到列表的所有元组中。这种问题可能出现在诸如网络开发和日常编程等领域。让我们讨论一下完成这项任务的某些方法。

> **输入** : test_list = [(5，6)，(2，4)，(5，7)，(2，5)]，sub_list = [5，4]
> **输出** : [(5，6，5，4)，(2，4，5，4)，(5，7，5，4)，(2，5，5，4)]
> **输入** : test_list = [(5，6)，(2，4)，(5，7)，(2，5)]，sub_list = [5]

**方法#1:使用列表理解+“+”运算符**
以上功能的组合可以用来解决这个问题。在这种情况下，我们使用“+”运算符执行向列表添加元组的任务，并使用列表理解对所有元组进行迭代。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Add list elements to tuples list
# Using list comprehension + "+" operator

# initializing list
test_list = [(5, 6), (2, 4), (5, 7), (2, 5)]

# printing original list
print("The original list is : " + str(test_list))

# initializing list
sub_list = [7, 2, 4, 6]

# Add list elements to tuples list
# Using list comprehension + "+" operator
res = [sub + tuple(sub_list) for sub in test_list]

# printing result
print("The modified list : " + str(res))
```

**Output : **

```py
The original list is : [(5, 6), (2, 4), (5, 7), (2, 5)]
The modified list : [(5, 6, 7, 2, 4, 6), (2, 4, 7, 2, 4, 6), (5, 7, 7, 2, 4, 6), (2, 5, 7, 2, 4, 6)]
```

**方法 2:使用列表理解+“*”运算符**
以上功能的组合可以用来解决这个问题。在本文中，我们使用 pack-unpack 运算符“*”执行向元组添加列表的任务。这是比上述方法更有效的方法。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Add list elements to tuples list
# Using list comprehension + "*" operator

# initializing list
test_list = [(5, 6), (2, 4), (5, 7), (2, 5)]

# printing original list
print("The original list is : " + str(test_list))

# initializing list
sub_list = [7, 2, 4, 6]

# Add list elements to tuples list
# Using list comprehension + "*" operator
res = [(*sub, *sub_list) for sub in test_list]

# printing result
print("The modified list : " + str(res))
```

**Output : **

```py
The original list is : [(5, 6), (2, 4), (5, 7), (2, 5)]
The modified list : [(5, 6, 7, 2, 4, 6), (2, 4, 7, 2, 4, 6), (5, 7, 7, 2, 4, 6), (2, 5, 7, 2, 4, 6)]
```