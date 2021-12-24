# Python |检查列表中是否有元素满足条件

> 原文:[https://www . geesforgeks . org/python-检查列表中的任何元素是否满足条件/](https://www.geeksforgeeks.org/python-check-if-any-element-in-list-satisfies-a-condition/)

有时，在使用 Python 列表时，我们在过滤列表时会遇到问题。执行此筛选操作的标准之一可以是检查列表中是否存在满足条件的任何元素。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用列表理解**
这个问题可以使用循环很容易地解决。但是这种方法提供了一种解决这个问题的方法。列表理解只是检查任何满足条件的元素。

```
# Python3 code to demonstrate working of
# Check if any element in list satisfies a condition
# Using list comprehension

# initializing list
test_list = [4, 5, 8, 9, 10, 17]

# printing list
print("The original list : " + str(test_list))

# Check if any element in list satisfies a condition
# Using list comprehension
res = True in (ele > 10 for ele in test_list)

# Printing result
print("Does any element satisfy specified condition ? : " + str(res))
```

**Output :**

```

The original list : [4, 5, 8, 9, 10, 17]
Does any element satisfy specified condition ? : True

```